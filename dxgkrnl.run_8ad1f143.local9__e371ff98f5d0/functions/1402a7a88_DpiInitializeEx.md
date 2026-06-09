# DpiInitializeEx

- ea: `0x1402a7a88`
- end: `0x1402a82c9`
- name: `DpiInitializeEx`
- size: `2113`
- prototype: `__int64 __usercall@<rax>(PVOID ClientIdentificationAddress@<rcx>, PCUNICODE_STRING SourceString@<rdx>, void *Src@<r8>, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007ffc8`
- `0x1400800c0`

## callees

- `0x140040908`
- `0x14004094c`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x14019d3f8`
- `0x1402a7a88`
- `0x1403cfdc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402a7f8f`
- `ntoskrnl!ExAllocatePool2` at `0x1402a7f8f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a826d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a826d`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a81e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a81e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a816d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a816d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a7b95`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a7b95`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402a7ff4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402a7ff4`
- `ntoskrnl!KeInitializeMutex` at `0x1402a800b`
- `ntoskrnl!KeInitializeMutex` at `0x1402a800b`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1402a7b0b`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1402a7b0b`
- `ntoskrnl!ExCreateCallback` at `0x1402a81a9`
- `ntoskrnl!ExCreateCallback` at `0x1402a81a9`
- `ntoskrnl!ExRegisterCallback` at `0x1402a81cb`
- `ntoskrnl!ExRegisterCallback` at `0x1402a81cb`
- `watchdog!WdLogSingleEntry1` at `0x1402a7b25`
- `watchdog!WdLogSingleEntry1` at `0x1402a7beb`
- `watchdog!WdLogSingleEntry1` at `0x1402a7fc1`
- `watchdog!WdLogSingleEntry1` at `0x1402a8068`
- `watchdog!WdLogSingleEntry1` at `0x1402a8210`
- `watchdog!WdLogSingleEntry1` at `0x1402a7b25`
- `watchdog!WdLogSingleEntry1` at `0x1402a7beb`
- `watchdog!WdLogSingleEntry1` at `0x1402a7fc1`
- `watchdog!WdLogSingleEntry1` at `0x1402a8068`
- `watchdog!WdLogSingleEntry1` at `0x1402a8210`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1402a8127`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1402a8127`

## pseudocode

```c
__int64 __fastcall DpiInitializeEx(
        struct _DRIVER_OBJECT *ClientIdentificationAddress,
        PCUNICODE_STRING SourceString,
        unsigned int *Src,
        __int64 a4,
        char a5)
{
  NTSTATUS DriverDataSizeFromVersion; // ebx
  __int64 v10; // rdx
  _WORD *v11; // rcx
  __int64 Pool2; // rax
  void *v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  PVOID DriverObjectExtension; // [rsp+30h] [rbp-81h] BYREF
  size_t Size; // [rsp+38h] [rbp-79h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-71h] BYREF
  __int64 v21; // [rsp+50h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-49h] BYREF
  _OWORD v24[2]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+7h]

  v24[0] = *(_OWORD *)L"\\Driver\\IndirectKmd";
  v25 = *(_QWORD *)L"Kmd";
  DriverObjectExtension = 0;
  LODWORD(Size) = 0;
  v24[1] = *(_OWORD *)L"IndirectKmd";
  *(_QWORD *)&String1.Length = 2621478;
  String1.Buffer = (wchar_t *)v24;
  DriverDataSizeFromVersion = IoAllocateDriverObjectExtension(
                                ClientIdentificationAddress,
                                ClientIdentificationAddress,
                                0x698u,
                                &DriverObjectExtension);
  if ( DriverDataSizeFromVersion < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 3377;
    goto LABEL_31;
  }
  *((_DWORD *)DriverObjectExtension + 4) = 1953656900;
  *((_DWORD *)DriverObjectExtension + 5) = 1;
  *((_DWORD *)DriverObjectExtension + 6) = 2;
  *((_QWORD *)DriverObjectExtension + 4) = ClientIdentificationAddress;
  *((_BYTE *)DriverObjectExtension + 132) = a5;
  *((_BYTE *)DriverObjectExtension + 134) = 0;
  if ( !RtlCompareUnicodeString(&String1, &ClientIdentificationAddress->DriverName, 1u) )
    *((_BYTE *)DriverObjectExtension + 134) = 1;
  if ( Src )
  {
    *((_BYTE *)DriverObjectExtension + 133) = 0;
    v10 = *Src;
    *((_DWORD *)DriverObjectExtension + 7) = v10;
    DriverDataSizeFromVersion = DpiGetDriverDataSizeFromVersion(0, v10, 1544, &Size);
    if ( DriverDataSizeFromVersion < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 3418;
      goto LABEL_31;
    }
    memmove((char *)DriverObjectExtension + 136, Src, (unsigned int)Size);
    *((_QWORD *)DriverObjectExtension + 210) = 0;
    goto LABEL_18;
  }
  *((_BYTE *)DriverObjectExtension + 133) = 1;
  memset((char *)DriverObjectExtension + 136, 0, 0x610u);
  *((_DWORD *)DriverObjectExtension + 7) = *(_DWORD *)a4;
  *((_DWORD *)DriverObjectExtension + 34) = *(_DWORD *)a4;
  *((_QWORD *)DriverObjectExtension + 18) = *(_QWORD *)(a4 + 8);
  *((_QWORD *)DriverObjectExtension + 19) = *(_QWORD *)(a4 + 16);
  *((_QWORD *)DriverObjectExtension + 20) = *(_QWORD *)(a4 + 24);
  *((_QWORD *)DriverObjectExtension + 21) = *(_QWORD *)(a4 + 32);
  *((_QWORD *)DriverObjectExtension + 22) = *(_QWORD *)(a4 + 40);
  *((_QWORD *)DriverObjectExtension + 23) = *(_QWORD *)(a4 + 48);
  *((_QWORD *)DriverObjectExtension + 24) = *(_QWORD *)(a4 + 56);
  *((_QWORD *)DriverObjectExtension + 25) = *(_QWORD *)(a4 + 64);
  *((_QWORD *)DriverObjectExtension + 26) = *(_QWORD *)(a4 + 72);
  *((_QWORD *)DriverObjectExtension + 27) = *(_QWORD *)(a4 + 80);
  *((_QWORD *)DriverObjectExtension + 28) = *(_QWORD *)(a4 + 88);
  *((_QWORD *)DriverObjectExtension + 29) = *(_QWORD *)(a4 + 96);
  *((_QWORD *)DriverObjectExtension + 30) = *(_QWORD *)(a4 + 104);
  *((_QWORD *)DriverObjectExtension + 31) = *(_QWORD *)(a4 + 112);
  *((_QWORD *)DriverObjectExtension + 32) = *(_QWORD *)(a4 + 120);
  *((_QWORD *)DriverObjectExtension + 33) = *(_QWORD *)(a4 + 128);
  *((_QWORD *)DriverObjectExtension + 34) = *(_QWORD *)(a4 + 136);
  *((_QWORD *)DriverObjectExtension + 46) = *(_QWORD *)(a4 + 144);
  *((_QWORD *)DriverObjectExtension + 47) = *(_QWORD *)(a4 + 152);
  *((_QWORD *)DriverObjectExtension + 48) = *(_QWORD *)(a4 + 160);
  *((_QWORD *)DriverObjectExtension + 51) = *(_QWORD *)(a4 + 168);
  *((_QWORD *)DriverObjectExtension + 52) = *(_QWORD *)(a4 + 176);
  *((_QWORD *)DriverObjectExtension + 54) = *(_QWORD *)(a4 + 184);
  *((_QWORD *)DriverObjectExtension + 55) = *(_QWORD *)(a4 + 192);
  *((_QWORD *)DriverObjectExtension + 56) = *(_QWORD *)(a4 + 200);
  *((_QWORD *)DriverObjectExtension + 58) = *(_QWORD *)(a4 + 208);
  *((_QWORD *)DriverObjectExtension + 59) = *(_QWORD *)(a4 + 216);
  *((_QWORD *)DriverObjectExtension + 60) = *(_QWORD *)(a4 + 224);
  *((_QWORD *)DriverObjectExtension + 61) = *(_QWORD *)(a4 + 232);
  *((_QWORD *)DriverObjectExtension + 63) = *(_QWORD *)(a4 + 240);
  *((_QWORD *)DriverObjectExtension + 87) = *(_QWORD *)(a4 + 248);
  *((_QWORD *)DriverObjectExtension + 210) = *(_QWORD *)(a4 + 256);
  *((_QWORD *)DriverObjectExtension + 92) = *(_QWORD *)(a4 + 264);
  *((_QWORD *)DriverObjectExtension + 93) = *(_QWORD *)(a4 + 272);
  *((_QWORD *)DriverObjectExtension + 94) = *(_QWORD *)(a4 + 280);
  if ( *(_DWORD *)a4 >= 0x3005u )
    *((_QWORD *)DriverObjectExtension + 96) = *(_QWORD *)(a4 + 288);
  if ( *(_DWORD *)a4 < 0x3007u )
    *((_QWORD *)DriverObjectExtension + 63) = 0;
  else
    *((_QWORD *)DriverObjectExtension + 65) = *(_QWORD *)(a4 + 296);
  if ( *(_DWORD *)a4 >= 0x3009u )
  {
    *((_QWORD *)DriverObjectExtension + 88) = *(_QWORD *)(a4 + 304);
    *((_QWORD *)DriverObjectExtension + 97) = *(_QWORD *)(a4 + 312);
  }
  v11 = DriverObjectExtension;
  if ( *((_DWORD *)DriverObjectExtension + 7) >= 0x5006u )
  {
    *((_QWORD *)DriverObjectExtension + 118) = *(_QWORD *)(a4 + 328);
LABEL_18:
    v11 = DriverObjectExtension;
  }
  v11[21] = SourceString->Length + 2;
  *((_WORD *)DriverObjectExtension + 20) = SourceString->Length;
  Pool2 = ExAllocatePool2(256, *((unsigned __int16 *)DriverObjectExtension + 21), 1953656900);
  *((_QWORD *)DriverObjectExtension + 6) = Pool2;
  v13 = (void *)*((_QWORD *)DriverObjectExtension + 6);
  if ( !v13 )
  {
    DriverDataSizeFromVersion = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 3530;
LABEL_31:
    if ( DriverObjectExtension && *((_QWORD *)DriverObjectExtension + 6) )
      RtlFreeUnicodeString((PUNICODE_STRING)((char *)DriverObjectExtension + 40));
    DxgCreateLiveDumpWithWdLogs(403, 2048, DriverDataSizeFromVersion, 0, 0, 0);
    return (unsigned int)DriverDataSizeFromVersion;
  }
  memset(v13, 0, *((unsigned __int16 *)DriverObjectExtension + 21));
  RtlCopyUnicodeString((PUNICODE_STRING)((char *)DriverObjectExtension + 40), SourceString);
  KeInitializeMutex((PRKMUTEX)((char *)DriverObjectExtension + 72), 0);
  v14 = (char *)DriverObjectExtension + 56;
  *((_QWORD *)DriverObjectExtension + 8) = (char *)DriverObjectExtension + 56;
  *v14 = v14;
  AcquireMiniportListMutex();
  v15 = (_QWORD *)qword_140162E90;
  if ( *(__int64 **)qword_140162E90 != &qword_140162E88 )
    __fastfail(3u);
  v16 = DriverObjectExtension;
  *(_QWORD *)DriverObjectExtension = &qword_140162E88;
  v16[1] = v15;
  *v15 = v16;
  qword_140162E90 = (__int64)v16;
  ReleaseMiniportListMutex();
  WdLogSingleEntry1(4);
  WdLogGlobalForLineNumber = 3556;
  if ( *((_BYTE *)DriverObjectExtension + 134) == 1 )
    memset64(ClientIdentificationAddress->MajorFunction, (unsigned __int64)&DpiDispatchDefault, 0x1Cu);
  ClientIdentificationAddress->MajorFunction[0] = (PDRIVER_DISPATCH)&DpiDispatchCreate;
  ClientIdentificationAddress->MajorFunction[27] = (PDRIVER_DISPATCH)&DpiDispatchPnp;
  ClientIdentificationAddress->MajorFunction[22] = (PDRIVER_DISPATCH)&DpiDispatchPower;
  ClientIdentificationAddress->MajorFunction[14] = (PDRIVER_DISPATCH)&DpiDispatchIoctl;
  ClientIdentificationAddress->MajorFunction[15] = (PDRIVER_DISPATCH)&DpiDispatchInternalIoctl;
  ClientIdentificationAddress->MajorFunction[23] = (PDRIVER_DISPATCH)&DpiDispatchSystemControl;
  ClientIdentificationAddress->MajorFunction[2] = (PDRIVER_DISPATCH)&DpiDispatchCleanupAndClose;
  ClientIdentificationAddress->MajorFunction[18] = (PDRIVER_DISPATCH)&DpiDispatchCleanupAndClose;
  ClientIdentificationAddress->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)DpiAddDevice;
  ClientIdentificationAddress->DriverUnload = (PDRIVER_UNLOAD)DpiDriverUnload;
  v21 = 0;
  if ( (int)KsrGetFirmwareInformation(&v21) >= 0 && !qword_1401633F0 )
  {
    Size = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    RtlInitUnicodeString(&DestinationString, L"\\Callback\\SoftRestart");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 80;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ExCreateCallback((PCALLBACK_OBJECT *)&Size, &ObjectAttributes, 0, 1u) >= 0 )
    {
      qword_1401633F0 = (__int64)ExRegisterCallback((PCALLBACK_OBJECT)Size, DpiKsrCallback, &DpGlobals);
      ObfDereferenceObject((PVOID)Size);
      word_1401633F8 = 0;
      dword_14016340C = 0;
    }
    if ( !qword_1401633F0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 3625;
    }
  }
  return (unsigned int)DriverDataSizeFromVersion;
}

```

## disassembly

```asm
0x1402a7a88  mov     [rsp-8+arg_18], rbx
0x1402a7a8d  push    rbp
0x1402a7a8e  push    rsi
0x1402a7a8f  push    rdi
0x1402a7a90  push    r12
0x1402a7a92  push    r13
0x1402a7a94  push    r14
0x1402a7a96  push    r15
0x1402a7a98  lea     rbp, [rsp-1Fh]
0x1402a7a9d  sub     rsp, 0D0h
0x1402a7aa4  mov     rax, cs:__security_cookie
0x1402a7aab  xor     rax, rsp
0x1402a7aae  mov     [rbp+4Fh+var_40], rax
0x1402a7ab2  movups  xmm0, xmmword ptr cs:aDriverIndirect; "\\Driver\\IndirectKmd"
0x1402a7ab9  mov     rdi, r9
0x1402a7abc  mov     r15, r8
0x1402a7abf  movups  xmm1, xmmword ptr cs:aDriverIndirect+10h; "IndirectKmd"
0x1402a7ac6  mov     r12, rdx
0x1402a7ac9  xor     r13d, r13d
0x1402a7acc  movups  [rbp+4Fh+var_68], xmm0
0x1402a7ad0  lea     rax, [rbp+4Fh+var_68]
0x1402a7ad4  mov     r8d, 698h; DriverObjectExtensionSize
0x1402a7ada  movsd   xmm0, qword ptr cs:aDriverIndirect+20h; "Kmd"
0x1402a7ae2  lea     r9, [rsp+100h+DriverObjectExtension]; DriverObjectExtension
0x1402a7ae7  mov     rdx, rcx; ClientIdentificationAddress
0x1402a7aea  movsd   [rbp+4Fh+var_48], xmm0
0x1402a7aef  mov     rsi, rcx
0x1402a7af2  mov     [rsp+100h+DriverObjectExtension], r13
0x1402a7af7  mov     dword ptr [rbp+4Fh+Size], r13d
0x1402a7afb  movups  [rbp+4Fh+var_58], xmm1
0x1402a7aff  mov     qword ptr [rbp+4Fh+String1.Length], 280026h
0x1402a7b07  mov     [rbp+4Fh+String1.Buffer], rax
0x1402a7b0b  call    cs:__imp_IoAllocateDriverObjectExtension
0x1402a7b12  nop     dword ptr [rax+rax+00h]
0x1402a7b17  movsxd  rbx, eax
0x1402a7b1a  test    eax, eax
0x1402a7b1c  jns     short loc_1402A7B40
0x1402a7b1e  mov     rdx, rbx
0x1402a7b21  lea     ecx, [r13+2]
0x1402a7b25  call    cs:__imp_WdLogSingleEntry1
0x1402a7b2c  nop     dword ptr [rax+rax+00h]
0x1402a7b31  mov     cs:WdLogGlobalForLineNumber, 0D31h
0x1402a7b3b  jmp     loc_1402A8259
0x1402a7b40  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7b45  lea     rdx, [rsi+38h]; String2
0x1402a7b49  mov     r14d, 2
0x1402a7b4f  mov     r8b, 1; CaseInSensitive
0x1402a7b52  mov     dword ptr [rax+10h], 74727044h
0x1402a7b59  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7b5e  mov     dword ptr [rax+14h], 1
0x1402a7b65  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7b6a  mov     [rax+18h], r14d
0x1402a7b6e  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7b73  mov     [rax+20h], rsi
0x1402a7b77  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7b7c  mov     al, [rbp+4Fh+arg_20]
0x1402a7b7f  mov     [rcx+84h], al
0x1402a7b85  lea     rcx, [rbp+4Fh+String1]; String1
0x1402a7b89  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7b8e  mov     [rax+86h], r13b
0x1402a7b95  call    cs:__imp_RtlCompareUnicodeString
0x1402a7b9c  nop     dword ptr [rax+rax+00h]
0x1402a7ba1  test    eax, eax
0x1402a7ba3  jnz     short loc_1402A7BB1
0x1402a7ba5  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7baa  mov     byte ptr [rax+86h], 1
0x1402a7bb1  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7bb6  test    r15, r15
0x1402a7bb9  jz      short loc_1402A7C2F
0x1402a7bbb  mov     [rax+85h], r13b
0x1402a7bc2  lea     r9, [rbp+4Fh+Size]
0x1402a7bc6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7bcb  xor     ecx, ecx
0x1402a7bcd  mov     edx, [r15]
0x1402a7bd0  mov     r8d, 608h
0x1402a7bd6  mov     [rax+1Ch], edx
0x1402a7bd9  call    DpiGetDriverDataSizeFromVersion
0x1402a7bde  movsxd  rbx, eax
0x1402a7be1  test    eax, eax
0x1402a7be3  jns     short loc_1402A7C06
0x1402a7be5  mov     rdx, rbx
0x1402a7be8  mov     ecx, r14d
0x1402a7beb  call    cs:__imp_WdLogSingleEntry1
0x1402a7bf2  nop     dword ptr [rax+rax+00h]
0x1402a7bf7  mov     cs:WdLogGlobalForLineNumber, 0D5Ah
0x1402a7c01  jmp     loc_1402A8259
0x1402a7c06  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7c0b  mov     rdx, r15; Src
0x1402a7c0e  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x1402a7c12  add     rcx, 88h; void *
0x1402a7c19  call    memmove
0x1402a7c1e  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c23  mov     [rax+690h], r13
0x1402a7c2a  jmp     loc_1402A7F5B
0x1402a7c2f  mov     byte ptr [rax+85h], 1
0x1402a7c36  xor     edx, edx; Val
0x1402a7c38  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7c3d  mov     r8d, 610h; Size
0x1402a7c43  add     rcx, 88h; void *
0x1402a7c4a  call    memset
0x1402a7c4f  mov     ecx, [rdi]
0x1402a7c51  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c56  mov     [rax+1Ch], ecx
0x1402a7c59  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c5e  mov     ecx, [rdi]
0x1402a7c60  mov     [rax+88h], ecx
0x1402a7c66  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c6b  mov     rcx, [rdi+8]
0x1402a7c6f  mov     [rax+90h], rcx
0x1402a7c76  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c7b  mov     rcx, [rdi+10h]
0x1402a7c7f  mov     [rax+98h], rcx
0x1402a7c86  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c8b  mov     rcx, [rdi+18h]
0x1402a7c8f  mov     [rax+0A0h], rcx
0x1402a7c96  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7c9b  mov     rcx, [rdi+20h]
0x1402a7c9f  mov     [rax+0A8h], rcx
0x1402a7ca6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7cab  mov     rcx, [rdi+28h]
0x1402a7caf  mov     [rax+0B0h], rcx
0x1402a7cb6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7cbb  mov     rcx, [rdi+30h]
0x1402a7cbf  mov     [rax+0B8h], rcx
0x1402a7cc6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7ccb  mov     rcx, [rdi+38h]
0x1402a7ccf  mov     [rax+0C0h], rcx
0x1402a7cd6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7cdb  mov     rcx, [rdi+40h]
0x1402a7cdf  mov     [rax+0C8h], rcx
0x1402a7ce6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7ceb  mov     rcx, [rdi+48h]
0x1402a7cef  mov     [rax+0D0h], rcx
0x1402a7cf6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7cfb  mov     rcx, [rdi+50h]
0x1402a7cff  mov     [rax+0D8h], rcx
0x1402a7d06  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d0b  mov     rcx, [rdi+58h]
0x1402a7d0f  mov     [rax+0E0h], rcx
0x1402a7d16  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d1b  mov     rcx, [rdi+60h]
0x1402a7d1f  mov     [rax+0E8h], rcx
0x1402a7d26  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d2b  mov     rcx, [rdi+68h]
0x1402a7d2f  mov     [rax+0F0h], rcx
0x1402a7d36  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d3b  mov     rcx, [rdi+70h]
0x1402a7d3f  mov     [rax+0F8h], rcx
0x1402a7d46  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d4b  mov     rcx, [rdi+78h]
0x1402a7d4f  mov     [rax+100h], rcx
0x1402a7d56  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d5b  mov     rcx, [rdi+80h]
0x1402a7d62  mov     [rax+108h], rcx
0x1402a7d69  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d6e  mov     rcx, [rdi+88h]
0x1402a7d75  mov     [rax+110h], rcx
0x1402a7d7c  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d81  mov     rcx, [rdi+90h]
0x1402a7d88  mov     [rax+170h], rcx
0x1402a7d8f  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7d94  mov     rcx, [rdi+98h]
0x1402a7d9b  mov     [rax+178h], rcx
0x1402a7da2  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7da7  mov     rcx, [rdi+0A0h]
0x1402a7dae  mov     [rax+180h], rcx
0x1402a7db5  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7dba  mov     rcx, [rdi+0A8h]
0x1402a7dc1  mov     [rax+198h], rcx
0x1402a7dc8  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7dcd  mov     rcx, [rdi+0B0h]
0x1402a7dd4  mov     [rax+1A0h], rcx
0x1402a7ddb  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7de0  mov     rcx, [rdi+0B8h]
0x1402a7de7  mov     [rax+1B0h], rcx
0x1402a7dee  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7df3  mov     rcx, [rdi+0C0h]
0x1402a7dfa  mov     [rax+1B8h], rcx
0x1402a7e01  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e06  mov     rcx, [rdi+0C8h]
0x1402a7e0d  mov     [rax+1C0h], rcx
0x1402a7e14  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e19  mov     rcx, [rdi+0D0h]
0x1402a7e20  mov     [rax+1D0h], rcx
0x1402a7e27  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e2c  mov     rcx, [rdi+0D8h]
0x1402a7e33  mov     [rax+1D8h], rcx
0x1402a7e3a  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e3f  mov     rcx, [rdi+0E0h]
0x1402a7e46  mov     [rax+1E0h], rcx
0x1402a7e4d  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e52  mov     rcx, [rdi+0E8h]
0x1402a7e59  mov     [rax+1E8h], rcx
0x1402a7e60  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e65  mov     rcx, [rdi+0F0h]
0x1402a7e6c  mov     [rax+1F8h], rcx
0x1402a7e73  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e78  mov     rcx, [rdi+0F8h]
0x1402a7e7f  mov     [rax+2B8h], rcx
0x1402a7e86  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e8b  mov     rcx, [rdi+100h]
0x1402a7e92  mov     [rax+690h], rcx
0x1402a7e99  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7e9e  mov     rcx, [rdi+108h]
0x1402a7ea5  mov     [rax+2E0h], rcx
0x1402a7eac  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7eb1  mov     rcx, [rdi+110h]
0x1402a7eb8  mov     [rax+2E8h], rcx
0x1402a7ebf  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7ec4  mov     rcx, [rdi+118h]
0x1402a7ecb  mov     [rax+2F0h], rcx
0x1402a7ed2  cmp     dword ptr [rdi], 3005h
0x1402a7ed8  jb      short loc_1402A7EED
0x1402a7eda  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7edf  mov     rcx, [rdi+120h]
0x1402a7ee6  mov     [rax+300h], rcx
0x1402a7eed  cmp     dword ptr [rdi], 3007h
0x1402a7ef3  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7ef8  jb      short loc_1402A7F0A
0x1402a7efa  mov     rcx, [rdi+128h]
0x1402a7f01  mov     [rax+208h], rcx
0x1402a7f08  jmp     short loc_1402A7F11
0x1402a7f0a  mov     [rax+1F8h], r13
0x1402a7f11  cmp     dword ptr [rdi], 3009h
0x1402a7f17  jb      short loc_1402A7F3F
0x1402a7f19  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7f1e  mov     rcx, [rdi+130h]
0x1402a7f25  mov     [rax+2C0h], rcx
0x1402a7f2c  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7f31  mov     rcx, [rdi+138h]
0x1402a7f38  mov     [rax+308h], rcx
0x1402a7f3f  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7f44  cmp     dword ptr [rcx+1Ch], 5006h
0x1402a7f4b  jb      short loc_1402A7F60
0x1402a7f4d  mov     rax, [rdi+148h]
0x1402a7f54  mov     [rcx+3B0h], rax
0x1402a7f5b  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7f60  movzx   eax, word ptr [r12]
0x1402a7f65  mov     r8d, 74727044h
0x1402a7f6b  add     ax, r14w
0x1402a7f6f  mov     [rcx+2Ah], ax
0x1402a7f73  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7f78  movzx   ecx, word ptr [r12]
0x1402a7f7d  mov     [rax+28h], cx
0x1402a7f81  mov     ecx, 100h
0x1402a7f86  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7f8b  movzx   edx, word ptr [rax+2Ah]
0x1402a7f8f  call    cs:__imp_ExAllocatePool2
0x1402a7f96  nop     dword ptr [rax+rax+00h]
0x1402a7f9b  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7fa0  mov     [rcx+30h], rax
0x1402a7fa4  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a7fa9  mov     rcx, [rax+30h]; void *
0x1402a7fad  test    rcx, rcx
0x1402a7fb0  jnz     short loc_1402A7FDC
0x1402a7fb2  mov     rbx, 0FFFFFFFFC0000017h
0x1402a7fb9  mov     rdx, rbx
0x1402a7fbc  mov     ecx, 6
0x1402a7fc1  call    cs:__imp_WdLogSingleEntry1
0x1402a7fc8  nop     dword ptr [rax+rax+00h]
0x1402a7fcd  mov     cs:WdLogGlobalForLineNumber, 0DCAh
0x1402a7fd7  jmp     loc_1402A8259
0x1402a7fdc  movzx   r8d, word ptr [rax+2Ah]; Size
0x1402a7fe1  xor     edx, edx; Val
0x1402a7fe3  call    memset
0x1402a7fe8  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a7fed  mov     rdx, r12; SourceString
0x1402a7ff0  add     rcx, 28h ; '('; DestinationString
0x1402a7ff4  call    cs:__imp_RtlCopyUnicodeString
0x1402a7ffb  nop     dword ptr [rax+rax+00h]
0x1402a8000  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a8005  xor     edx, edx; Level
0x1402a8007  add     rcx, 48h ; 'H'; Mutex
0x1402a800b  call    cs:__imp_KeInitializeMutex
0x1402a8012  nop     dword ptr [rax+rax+00h]
0x1402a8017  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a801c  add     rax, 38h ; '8'
0x1402a8020  mov     [rax+8], rax
0x1402a8024  mov     [rax], rax
0x1402a8027  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402a802c  mov     rcx, cs:qword_140162E90
0x1402a8033  lea     rdx, qword_140162E88
0x1402a803a  cmp     [rcx], rdx
0x1402a803d  jnz     loc_1402A82C2
0x1402a8043  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a8048  mov     [rax], rdx
0x1402a804b  mov     [rax+8], rcx
0x1402a804f  mov     [rcx], rax
0x1402a8052  mov     cs:qword_140162E90, rax
0x1402a8059  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402a805e  mov     rdx, [rsp+100h+DriverObjectExtension]
0x1402a8063  mov     ecx, 4
0x1402a8068  call    cs:__imp_WdLogSingleEntry1
0x1402a806f  nop     dword ptr [rax+rax+00h]
0x1402a8074  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a8079  mov     cs:WdLogGlobalForLineNumber, 0DE4h
0x1402a8083  cmp     byte ptr [rax+86h], 1
0x1402a808a  jnz     short loc_1402A809F
0x1402a808c  lea     rdi, [rsi+70h]
0x1402a8090  mov     ecx, 1Ch
  ... truncated ...
```
