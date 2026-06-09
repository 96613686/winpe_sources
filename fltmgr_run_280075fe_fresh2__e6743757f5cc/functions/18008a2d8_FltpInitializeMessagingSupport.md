# FltpInitializeMessagingSupport

- ea: `0x18008a2d8`
- end: `0x18008a612`
- name: `FltpInitializeMessagingSupport`
- size: `826`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180089078`

## callees

- `0x180009f20`
- `0x180020180`
- `0x1800247a0`
- `0x180024c00`
- `0x18008a2d8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18008a5a9`
- `ntoskrnl!ObfDereferenceObject` at `0x18008a5df`
- `ntoskrnl!ObfDereferenceObject` at `0x18008a5a9`
- `ntoskrnl!ObfDereferenceObject` at `0x18008a5df`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a36f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a42f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a500`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a36f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a42f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008a500`
- `ntoskrnl!IoCreateDevice` at `0x18008a4ba`
- `ntoskrnl!IoCreateDevice` at `0x18008a4ba`
- `ntoskrnl!IoDeleteDevice` at `0x18008a573`
- `ntoskrnl!IoDeleteDevice` at `0x18008a573`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008a517`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008a517`
- `ntoskrnl!ObCreateObjectType` at `0x18008a38d`
- `ntoskrnl!ObCreateObjectType` at `0x18008a44d`
- `ntoskrnl!ObCreateObjectType` at `0x18008a38d`
- `ntoskrnl!ObCreateObjectType` at `0x18008a44d`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008a596`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008a5cc`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008a596`
- `ntoskrnl!ObMakeTemporaryObject` at `0x18008a5cc`

## string_xrefs

- `0x18008a3f4`: `FilterCommunicationPort`

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
  v2 = (unsigned int)ObCreateObjectType(&DestinationString, v8, 0, &qword_18003E9A8);
  if ( (int)FltpDbgStatus(v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3335, 0) < 0 )
  {
    if ( (byte_1800404C1 & 0x40) == 0 )
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
  LODWORD(v2) = ObCreateObjectType(&DestinationString, v8, 0, &qword_18003E9B0);
  if ( (int)FltpDbgStatus((unsigned int)v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3400, 0) < 0 )
  {
    if ( (byte_1800404C1 & 0x40) == 0 )
      goto LABEL_14;
    v4 = MessageSup_c3402;
    goto LABEL_13;
  }
  LODWORD(v2) = IoCreateDevice(DriverObject, 0, (PUNICODE_STRING)&FltMgrMsgDeviceName, 0x40u, 0, 0, &qword_18003E9B8);
  if ( (int)FltpDbgStatus((unsigned int)v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3422, 0) < 0 )
  {
    if ( (byte_1800404C1 & 0x40) == 0 )
      goto LABEL_14;
    v4 = MessageSup_c3424;
    goto LABEL_13;
  }
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\FltMgrMsg");
  LODWORD(v2) = IoCreateSymbolicLink(&SymbolicLinkName, (PUNICODE_STRING)&FltMgrMsgDeviceName);
  if ( (int)FltpDbgStatus((unsigned int)v2, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 3440, 0) < 0
    && (byte_1800404C1 & 0x40) != 0 )
  {
    v4 = MessageSup_c3442;
LABEL_13:
    McTemplateU0sd_EtwWriteTransfer(v3, v4, "FltpInitializeMessagingSupport", (unsigned int)v2);
  }
LABEL_14:
  if ( (int)v2 < 0 )
  {
    if ( qword_18003E9B8 )
    {
      IoDeleteDevice(qword_18003E9B8);
      qword_18003E9B8 = 0;
    }
    if ( qword_18003E9B0 )
    {
      ObMakeTemporaryObject(qword_18003E9B0);
      ObfDereferenceObject(qword_18003E9B0);
      qword_18003E9B0 = 0;
    }
    if ( qword_18003E9A8 )
    {
      ObMakeTemporaryObject(qword_18003E9A8);
      ObfDereferenceObject(qword_18003E9A8);
      qword_18003E9A8 = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18008a2d8  push    rbp
0x18008a2da  push    rbx
0x18008a2db  push    rdi
0x18008a2dc  push    r15
0x18008a2de  lea     rbp, [rsp-3Fh]
0x18008a2e3  sub     rsp, 0F8h
0x18008a2ea  mov     rax, cs:__security_cookie
0x18008a2f1  xor     rax, rsp
0x18008a2f4  mov     [rbp+57h+var_30], rax
0x18008a2f8  mov     rdi, rcx
0x18008a2fb  xorps   xmm0, xmm0
0x18008a2fe  xorps   xmm1, xmm1
0x18008a301  lea     rcx, [rbp+57h+var_B0]; void *
0x18008a305  mov     r15d, 78h ; 'x'
0x18008a30b  xor     edx, edx; Val
0x18008a30d  mov     r8d, r15d; Size
0x18008a310  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008a314  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm1
0x18008a318  call    memset
0x18008a31d  movups  xmm0, cs:FltpPortGenericMapping
0x18008a324  lea     rax, FltpServerPortDelete
0x18008a32b  mov     [rbp+57h+var_B0], r15w
0x18008a330  mov     [rbp+57h+var_68], rax
0x18008a334  lea     rdx, aFilterconnecti; "FilterConnectionPort"
0x18008a33b  lea     rax, FltpServerPortClose
0x18008a342  mov     [rbp+57h+var_A8], 100h
0x18008a349  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008a34d  mov     [rbp+57h+var_70], rax
0x18008a351  movdqu  [rbp+57h+var_A4], xmm0
0x18008a356  mov     [rbp+57h+var_94], 1F0001h
0x18008a35d  mov     [rbp+57h+var_AE], 0Ch
0x18008a361  mov     [rbp+57h+var_8C], 200h
0x18008a368  mov     [rbp+57h+var_84], 158h
0x18008a36f  call    cs:__imp_RtlInitUnicodeString
0x18008a376  nop     dword ptr [rax+rax+00h]
0x18008a37b  lea     r9, qword_18003E9A8
0x18008a382  xor     r8d, r8d
0x18008a385  lea     rdx, [rbp+57h+var_B0]
0x18008a389  lea     rcx, [rbp+57h+DestinationString]
0x18008a38d  call    cs:__imp_ObCreateObjectType
0x18008a394  nop     dword ptr [rax+rax+00h]
0x18008a399  mov     r8d, 0D07h
0x18008a39f  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008a3a6  mov     ecx, eax
0x18008a3a8  xor     r9d, r9d
0x18008a3ab  mov     ebx, eax
0x18008a3ad  call    FltpDbgStatus
0x18008a3b2  test    eax, eax
0x18008a3b4  jns     short loc_18008A3CF
0x18008a3b6  test    cs:byte_1800404C1, 40h
0x18008a3bd  jz      loc_18008A55F
0x18008a3c3  lea     rdx, MessageSup_c3337
0x18008a3ca  jmp     loc_18008A550
0x18008a3cf  mov     r8, r15; Size
0x18008a3d2  lea     rcx, [rbp+57h+var_B0]; void *
0x18008a3d6  xor     edx, edx; Val
0x18008a3d8  call    memset
0x18008a3dd  movups  xmm0, cs:FltpPortGenericMapping
0x18008a3e4  lea     rax, FltpClientPortDelete
0x18008a3eb  mov     [rbp+57h+var_B0], r15w
0x18008a3f0  mov     [rbp+57h+var_68], rax
0x18008a3f4  lea     rdx, aFiltercommunic; "FilterCommunicationPort"
0x18008a3fb  lea     rax, FltpClientPortClose
0x18008a402  mov     [rbp+57h+var_A8], 100h
0x18008a409  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008a40d  mov     [rbp+57h+var_70], rax
0x18008a411  movdqu  [rbp+57h+var_A4], xmm0
0x18008a416  mov     [rbp+57h+var_94], 1F0001h
0x18008a41d  mov     [rbp+57h+var_AE], 4
0x18008a421  mov     [rbp+57h+var_8C], 200h
0x18008a428  mov     [rbp+57h+var_84], 158h
0x18008a42f  call    cs:__imp_RtlInitUnicodeString
0x18008a436  nop     dword ptr [rax+rax+00h]
0x18008a43b  lea     r9, qword_18003E9B0
0x18008a442  xor     r8d, r8d
0x18008a445  lea     rdx, [rbp+57h+var_B0]
0x18008a449  lea     rcx, [rbp+57h+DestinationString]
0x18008a44d  call    cs:__imp_ObCreateObjectType
0x18008a454  nop     dword ptr [rax+rax+00h]
0x18008a459  mov     r8d, 0D48h
0x18008a45f  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008a466  mov     ecx, eax
0x18008a468  xor     r9d, r9d
0x18008a46b  mov     ebx, eax
0x18008a46d  call    FltpDbgStatus
0x18008a472  test    eax, eax
0x18008a474  jns     short loc_18008A48F
0x18008a476  test    cs:byte_1800404C1, 40h
0x18008a47d  jz      loc_18008A55F
0x18008a483  lea     rdx, MessageSup_c3402
0x18008a48a  jmp     loc_18008A550
0x18008a48f  lea     rax, qword_18003E9B8
0x18008a496  mov     r9d, 40h ; '@'; DeviceType
0x18008a49c  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x18008a4a1  lea     r8, FltMgrMsgDeviceName; DeviceName
0x18008a4a8  mov     [rsp+110h+Exclusive], 0; Exclusive
0x18008a4ad  xor     edx, edx; DeviceExtensionSize
0x18008a4af  mov     rcx, rdi; DriverObject
0x18008a4b2  mov     [rsp+110h+DeviceCharacteristics], 0; DeviceCharacteristics
0x18008a4ba  call    cs:__imp_IoCreateDevice
0x18008a4c1  nop     dword ptr [rax+rax+00h]
0x18008a4c6  mov     r8d, 0D5Eh
0x18008a4cc  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008a4d3  mov     ecx, eax
0x18008a4d5  xor     r9d, r9d
0x18008a4d8  mov     ebx, eax
0x18008a4da  call    FltpDbgStatus
0x18008a4df  test    eax, eax
0x18008a4e1  jns     short loc_18008A4F5
0x18008a4e3  test    cs:byte_1800404C1, 40h
0x18008a4ea  jz      short loc_18008A55F
0x18008a4ec  lea     rdx, MessageSup_c3424
0x18008a4f3  jmp     short loc_18008A550
0x18008a4f5  lea     rdx, aDosdevicesFltm; "\\DosDevices\\FltMgrMsg"
0x18008a4fc  lea     rcx, [rbp+57h+SymbolicLinkName]; DestinationString
0x18008a500  call    cs:__imp_RtlInitUnicodeString
0x18008a507  nop     dword ptr [rax+rax+00h]
0x18008a50c  lea     rdx, FltMgrMsgDeviceName; DeviceName
0x18008a513  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x18008a517  call    cs:__imp_IoCreateSymbolicLink
0x18008a51e  nop     dword ptr [rax+rax+00h]
0x18008a523  mov     r8d, 0D70h
0x18008a529  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18008a530  mov     ecx, eax
0x18008a532  xor     r9d, r9d
0x18008a535  mov     ebx, eax
0x18008a537  call    FltpDbgStatus
0x18008a53c  test    eax, eax
0x18008a53e  jns     short loc_18008A55F
0x18008a540  test    cs:byte_1800404C1, 40h
0x18008a547  jz      short loc_18008A55F
0x18008a549  lea     rdx, MessageSup_c3442
0x18008a550  mov     r9d, ebx
0x18008a553  lea     r8, aFltpinitialize; "FltpInitializeMessagingSupport"
0x18008a55a  call    McTemplateU0sd_EtwWriteTransfer
0x18008a55f  test    ebx, ebx
0x18008a561  jns     loc_18008A5F6
0x18008a567  mov     rcx, cs:qword_18003E9B8; DeviceObject
0x18008a56e  test    rcx, rcx
0x18008a571  jz      short loc_18008A58A
0x18008a573  call    cs:__imp_IoDeleteDevice
0x18008a57a  nop     dword ptr [rax+rax+00h]
0x18008a57f  mov     cs:qword_18003E9B8, 0
0x18008a58a  mov     rcx, cs:qword_18003E9B0; Object
0x18008a591  test    rcx, rcx
0x18008a594  jz      short loc_18008A5C0
0x18008a596  call    cs:__imp_ObMakeTemporaryObject
0x18008a59d  nop     dword ptr [rax+rax+00h]
0x18008a5a2  mov     rcx, cs:qword_18003E9B0; Object
0x18008a5a9  call    cs:__imp_ObfDereferenceObject
0x18008a5b0  nop     dword ptr [rax+rax+00h]
0x18008a5b5  mov     cs:qword_18003E9B0, 0
0x18008a5c0  mov     rcx, cs:qword_18003E9A8; Object
0x18008a5c7  test    rcx, rcx
0x18008a5ca  jz      short loc_18008A5F6
0x18008a5cc  call    cs:__imp_ObMakeTemporaryObject
0x18008a5d3  nop     dword ptr [rax+rax+00h]
0x18008a5d8  mov     rcx, cs:qword_18003E9A8; Object
0x18008a5df  call    cs:__imp_ObfDereferenceObject
0x18008a5e6  nop     dword ptr [rax+rax+00h]
0x18008a5eb  mov     cs:qword_18003E9A8, 0
0x18008a5f6  mov     eax, ebx
0x18008a5f8  mov     rcx, [rbp+57h+var_30]
0x18008a5fc  xor     rcx, rsp; StackCookie
0x18008a5ff  call    __security_check_cookie
0x18008a604  add     rsp, 0F8h
0x18008a60b  pop     r15
0x18008a60d  pop     rdi
0x18008a60e  pop     rbx
0x18008a60f  pop     rbp
0x18008a610  retn
```
