# FltpInitializeMessagingSupport

- ea: `0x18008d2d8`
- end: `0x18008d612`
- name: `FltpInitializeMessagingSupport`
- size: `826`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18008c078`

## callees

- `0x180009f20`
- `0x180020180`
- `0x180024800`
- `0x180024c40`
- `0x18008d2d8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18008d5a9`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d5df`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d5a9`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d5df`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d36f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d42f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d500`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d36f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d42f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008d500`
- `ntoskrnl!IoCreateDevice` at `0x18008d4ba`
- `ntoskrnl!IoCreateDevice` at `0x18008d4ba`
- `ntoskrnl!IoDeleteDevice` at `0x18008d573`
- `ntoskrnl!IoDeleteDevice` at `0x18008d573`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008d517`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008d517`
- `ntoskrnl!ObCreateObjectType` at `0x18008d38d`
- `ntoskrnl!ObCreateObjectType` at `0x18008d44d`
- `ntoskrnl!ObCreateObjectType` at `0x18008d38d`
- `ntoskrnl!ObCreateObjectType` at `0x18008d44d`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008d596`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008d5cc`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008d596`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008d5cc`

## string_xrefs

- `0x18008d3f4`: `FilterCommunicationPort`

## pseudocode

```c
__int64 __fastcall FltpInitializeMessagingSupport(PDRIVER_OBJECT DriverObject)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 *v4; // rdx
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-79h] BYREF
  UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v8[16]; // [rsp+60h] [rbp-59h] BYREF

  DestinationString = 0;
  SymbolicLinkName = 0;
  memset(v8, 0, 0x78u);
  LOWORD(v8[0]) = 120;
  v8[9] = FltpServerPortDelete;
  LODWORD(v8[1]) = 256;
  v8[8] = FltpServerPortClose;
  *(_OWORD *)((char *)&v8[1] + 4) = FltpPortGenericMapping;
  HIDWORD(v8[3]) = 2031617;
  BYTE2(v8[0]) = 12;
  HIDWORD(v8[4]) = 512;
  HIDWORD(v8[5]) = 344;
  RtlInitUnicodeString(&DestinationString, L"FilterConnectionPort");
  v2 = (unsigned int)ObCreateObjectType(&DestinationString, v8, 0, &qword_18003EF28);
  if ( (int)FltpDbgStatus(v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3335, 0) < 0 )
  {
    if ( (byte_180040A41 & 0x40) == 0 )
      goto LABEL_14;
    v4 = MessageSup_c3337;
    goto LABEL_13;
  }
  memset(v8, 0, 0x78u);
  LOWORD(v8[0]) = 120;
  v8[9] = FltpClientPortDelete;
  LODWORD(v8[1]) = 256;
  v8[8] = FltpClientPortClose;
  *(_OWORD *)((char *)&v8[1] + 4) = FltpPortGenericMapping;
  HIDWORD(v8[3]) = 2031617;
  BYTE2(v8[0]) = 4;
  HIDWORD(v8[4]) = 512;
  HIDWORD(v8[5]) = 344;
  RtlInitUnicodeString(&DestinationString, L"FilterCommunicationPort");
  LODWORD(v2) = ObCreateObjectType(&DestinationString, v8, 0, &qword_18003EF30);
  if ( (int)FltpDbgStatus((unsigned int)v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3400, 0) < 0 )
  {
    if ( (byte_180040A41 & 0x40) == 0 )
      goto LABEL_14;
    v4 = MessageSup_c3402;
    goto LABEL_13;
  }
  LODWORD(v2) = IoCreateDevice(DriverObject, 0, (PUNICODE_STRING)&FltMgrMsgDeviceName, 0x40u, 0, 0, &qword_18003EF38);
  if ( (int)FltpDbgStatus((unsigned int)v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3422, 0) < 0 )
  {
    if ( (byte_180040A41 & 0x40) == 0 )
      goto LABEL_14;
    v4 = MessageSup_c3424;
    goto LABEL_13;
  }
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\FltMgrMsg");
  LODWORD(v2) = IoCreateSymbolicLink(&SymbolicLinkName, (PUNICODE_STRING)&FltMgrMsgDeviceName);
  if ( (int)FltpDbgStatus((unsigned int)v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3440, 0) < 0
    && (byte_180040A41 & 0x40) != 0 )
  {
    v4 = MessageSup_c3442;
LABEL_13:
    McTemplateU0sd_EtwWriteTransfer(v3, v4, "FltpInitializeMessagingSupport", (unsigned int)v2);
  }
LABEL_14:
  if ( (int)v2 < 0 )
  {
    if ( qword_18003EF38 )
    {
      IoDeleteDevice(qword_18003EF38);
      qword_18003EF38 = 0;
    }
    if ( qword_18003EF30 )
    {
      ObMakeTemporaryObject(qword_18003EF30);
      ObfDereferenceObject(qword_18003EF30);
      qword_18003EF30 = 0;
    }
    if ( qword_18003EF28 )
    {
      ObMakeTemporaryObject(qword_18003EF28);
      ObfDereferenceObject(qword_18003EF28);
      qword_18003EF28 = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008d2d8  push    rbp
0x18008d2da  push    rbx
0x18008d2db  push    rdi
0x18008d2dc  push    r15
0x18008d2de  lea     rbp, [rsp-3Fh]
0x18008d2e3  sub     rsp, 0F8h
0x18008d2ea  mov     rax, cs:__security_cookie
0x18008d2f1  xor     rax, rsp
0x18008d2f4  mov     [rbp+57h+var_30], rax
0x18008d2f8  mov     rdi, rcx
0x18008d2fb  xorps   xmm0, xmm0
0x18008d2fe  xorps   xmm1, xmm1
0x18008d301  lea     rcx, [rbp+57h+var_B0]; void *
0x18008d305  mov     r15d, 78h ; 'x'
0x18008d30b  xor     edx, edx; Val
0x18008d30d  mov     r8d, r15d; Size
0x18008d310  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008d314  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x18008d318  call    memset
0x18008d31d  movups  xmm0, cs:FltpPortGenericMapping
0x18008d324  lea     rax, FltpServerPortDelete
0x18008d32b  mov     [rbp+57h+var_B0], r15w
0x18008d330  mov     [rbp+57h+var_68], rax
0x18008d334  lea     rdx, aFilterconnecti; "FilterConnectionPort"
0x18008d33b  lea     rax, FltpServerPortClose
0x18008d342  mov     [rbp+57h+var_A8], 100h
0x18008d349  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008d34d  mov     [rbp+57h+var_70], rax
0x18008d351  movdqu  [rbp+57h+var_A4], xmm0
0x18008d356  mov     [rbp+57h+var_94], 1F0001h
0x18008d35d  mov     [rbp+57h+var_AE], 0Ch
0x18008d361  mov     [rbp+57h+var_8C], 200h
0x18008d368  mov     [rbp+57h+var_84], 158h
0x18008d36f  call    cs:__imp_RtlInitUnicodeString
0x18008d376  nop     dword ptr [rax+rax+00h]
0x18008d37b  lea     r9, qword_18003EF28
0x18008d382  xor     r8d, r8d
0x18008d385  lea     rdx, [rbp+57h+var_B0]
0x18008d389  lea     rcx, [rbp+57h+DestinationString]
0x18008d38d  call    cs:__imp_ObCreateObjectType
0x18008d394  nop     dword ptr [rax+rax+00h]
0x18008d399  mov     r8d, 0D07h
0x18008d39f  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008d3a6  mov     ecx, eax
0x18008d3a8  xor     r9d, r9d
0x18008d3ab  mov     ebx, eax
0x18008d3ad  call    FltpDbgStatus
0x18008d3b2  test    eax, eax
0x18008d3b4  jns     short loc_18008D3CF
0x18008d3b6  test    cs:byte_180040A41, 40h
0x18008d3bd  jz      loc_18008D55F
0x18008d3c3  lea     rdx, MessageSup_c3337
0x18008d3ca  jmp     loc_18008D550
0x18008d3cf  mov     r8, r15; Size
0x18008d3d2  lea     rcx, [rbp+57h+var_B0]; void *
0x18008d3d6  xor     edx, edx; Val
0x18008d3d8  call    memset
0x18008d3dd  movups  xmm0, cs:FltpPortGenericMapping
0x18008d3e4  lea     rax, FltpClientPortDelete
0x18008d3eb  mov     [rbp+57h+var_B0], r15w
0x18008d3f0  mov     [rbp+57h+var_68], rax
0x18008d3f4  lea     rdx, aFiltercommunic; "FilterCommunicationPort"
0x18008d3fb  lea     rax, FltpClientPortClose
0x18008d402  mov     [rbp+57h+var_A8], 100h
0x18008d409  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008d40d  mov     [rbp+57h+var_70], rax
0x18008d411  movdqu  [rbp+57h+var_A4], xmm0
0x18008d416  mov     [rbp+57h+var_94], 1F0001h
0x18008d41d  mov     [rbp+57h+var_AE], 4
0x18008d421  mov     [rbp+57h+var_8C], 200h
0x18008d428  mov     [rbp+57h+var_84], 158h
0x18008d42f  call    cs:__imp_RtlInitUnicodeString
0x18008d436  nop     dword ptr [rax+rax+00h]
0x18008d43b  lea     r9, qword_18003EF30
0x18008d442  xor     r8d, r8d
0x18008d445  lea     rdx, [rbp+57h+var_B0]
0x18008d449  lea     rcx, [rbp+57h+DestinationString]
0x18008d44d  call    cs:__imp_ObCreateObjectType
0x18008d454  nop     dword ptr [rax+rax+00h]
0x18008d459  mov     r8d, 0D48h
0x18008d45f  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008d466  mov     ecx, eax
0x18008d468  xor     r9d, r9d
0x18008d46b  mov     ebx, eax
0x18008d46d  call    FltpDbgStatus
0x18008d472  test    eax, eax
0x18008d474  jns     short loc_18008D48F
0x18008d476  test    cs:byte_180040A41, 40h
0x18008d47d  jz      loc_18008D55F
0x18008d483  lea     rdx, MessageSup_c3402
0x18008d48a  jmp     loc_18008D550
0x18008d48f  lea     rax, qword_18003EF38
0x18008d496  mov     r9d, 40h ; '@'; DeviceType
0x18008d49c  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x18008d4a1  lea     r8, FltMgrMsgDeviceName; DeviceName
0x18008d4a8  mov     [rsp+110h+Exclusive], 0; Exclusive
0x18008d4ad  xor     edx, edx; DeviceExtensionSize
0x18008d4af  mov     rcx, rdi; DriverObject
0x18008d4b2  mov     [rsp+110h+DeviceCharacteristics], 0; DeviceCharacteristics
0x18008d4ba  call    cs:__imp_IoCreateDevice
0x18008d4c1  nop     dword ptr [rax+rax+00h]
0x18008d4c6  mov     r8d, 0D5Eh
0x18008d4cc  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008d4d3  mov     ecx, eax
0x18008d4d5  xor     r9d, r9d
0x18008d4d8  mov     ebx, eax
0x18008d4da  call    FltpDbgStatus
0x18008d4df  test    eax, eax
0x18008d4e1  jns     short loc_18008D4F5
0x18008d4e3  test    cs:byte_180040A41, 40h
0x18008d4ea  jz      short loc_18008D55F
0x18008d4ec  lea     rdx, MessageSup_c3424
0x18008d4f3  jmp     short loc_18008D550
0x18008d4f5  lea     rdx, aDosdevicesFltm; "\\DosDevices\\FltMgrMsg"
0x18008d4fc  lea     rcx, [rbp+57h+SymbolicLinkName]; DestinationString
0x18008d500  call    cs:__imp_RtlInitUnicodeString
0x18008d507  nop     dword ptr [rax+rax+00h]
0x18008d50c  lea     rdx, FltMgrMsgDeviceName; DeviceName
0x18008d513  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x18008d517  call    cs:__imp_IoCreateSymbolicLink
0x18008d51e  nop     dword ptr [rax+rax+00h]
0x18008d523  mov     r8d, 0D70h
0x18008d529  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008d530  mov     ecx, eax
0x18008d532  xor     r9d, r9d
0x18008d535  mov     ebx, eax
0x18008d537  call    FltpDbgStatus
0x18008d53c  test    eax, eax
0x18008d53e  jns     short loc_18008D55F
0x18008d540  test    cs:byte_180040A41, 40h
0x18008d547  jz      short loc_18008D55F
0x18008d549  lea     rdx, MessageSup_c3442
0x18008d550  mov     r9d, ebx
0x18008d553  lea     r8, aFltpinitialize; "FltpInitializeMessagingSupport"
0x18008d55a  call    McTemplateU0sd_EtwWriteTransfer
0x18008d55f  test    ebx, ebx
0x18008d561  jns     loc_18008D5F6
0x18008d567  mov     rcx, cs:qword_18003EF38; DeviceObject
0x18008d56e  test    rcx, rcx
0x18008d571  jz      short loc_18008D58A
0x18008d573  call    cs:__imp_IoDeleteDevice
0x18008d57a  nop     dword ptr [rax+rax+00h]
0x18008d57f  mov     cs:qword_18003EF38, 0
0x18008d58a  mov     rcx, cs:qword_18003EF30; Object
0x18008d591  test    rcx, rcx
0x18008d594  jz      short loc_18008D5C0
0x18008d596  call    cs:__imp_ObMakeTemporaryObject
0x18008d59d  nop     dword ptr [rax+rax+00h]
0x18008d5a2  mov     rcx, cs:qword_18003EF30; Object
0x18008d5a9  call    cs:__imp_ObfDereferenceObject
0x18008d5b0  nop     dword ptr [rax+rax+00h]
0x18008d5b5  mov     cs:qword_18003EF30, 0
0x18008d5c0  mov     rcx, cs:qword_18003EF28; Object
0x18008d5c7  test    rcx, rcx
0x18008d5ca  jz      short loc_18008D5F6
0x18008d5cc  call    cs:__imp_ObMakeTemporaryObject
0x18008d5d3  nop     dword ptr [rax+rax+00h]
0x18008d5d8  mov     rcx, cs:qword_18003EF28; Object
0x18008d5df  call    cs:__imp_ObfDereferenceObject
0x18008d5e6  nop     dword ptr [rax+rax+00h]
0x18008d5eb  mov     cs:qword_18003EF28, 0
0x18008d5f6  mov     eax, ebx
0x18008d5f8  mov     rcx, [rbp+57h+var_30]
0x18008d5fc  xor     rcx, rsp; StackCookie
0x18008d5ff  call    __security_check_cookie
0x18008d604  add     rsp, 0F8h
0x18008d60b  pop     r15
0x18008d60d  pop     rdi
0x18008d60e  pop     rbx
0x18008d60f  pop     rbp
0x18008d610  retn
```
