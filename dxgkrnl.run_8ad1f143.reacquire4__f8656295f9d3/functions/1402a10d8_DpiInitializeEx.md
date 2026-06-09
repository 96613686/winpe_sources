# DpiInitializeEx

- ea: `0x1402a10d8`
- end: `0x1402a1919`
- name: `DpiInitializeEx`
- size: `2113`
- prototype: `__int64 __usercall@<rax>(PVOID ClientIdentificationAddress@<rcx>, PCUNICODE_STRING SourceString@<rdx>, void *Src@<r8>, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007f6c8`
- `0x14007f7c0`

## callees

- `0x1400406a8`
- `0x1400406ec`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x1401993f8`
- `0x1402a10d8`
- `0x1403cf9a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402a15df`
- `ntoskrnl!ExAllocatePool2` at `0x1402a15df`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a18bd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a18bd`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a1832`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a1832`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a17bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a17bd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a11e5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1402a11e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402a1644`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402a1644`
- `ntoskrnl!KeInitializeMutex` at `0x1402a165b`
- `ntoskrnl!KeInitializeMutex` at `0x1402a165b`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1402a115b`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1402a115b`
- `ntoskrnl!ExCreateCallback` at `0x1402a17f9`
- `ntoskrnl!ExCreateCallback` at `0x1402a17f9`
- `ntoskrnl!ExRegisterCallback` at `0x1402a181b`
- `ntoskrnl!ExRegisterCallback` at `0x1402a181b`
- `watchdog!WdLogSingleEntry1` at `0x1402a1175`
- `watchdog!WdLogSingleEntry1` at `0x1402a123b`
- `watchdog!WdLogSingleEntry1` at `0x1402a1611`
- `watchdog!WdLogSingleEntry1` at `0x1402a16b8`
- `watchdog!WdLogSingleEntry1` at `0x1402a1860`
- `watchdog!WdLogSingleEntry1` at `0x1402a1175`
- `watchdog!WdLogSingleEntry1` at `0x1402a123b`
- `watchdog!WdLogSingleEntry1` at `0x1402a1611`
- `watchdog!WdLogSingleEntry1` at `0x1402a16b8`
- `watchdog!WdLogSingleEntry1` at `0x1402a1860`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1402a1777`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrGetFirmwareInformation` at `0x1402a1777`

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
  v15 = (_QWORD *)qword_14015EE10;
  if ( *(__int64 **)qword_14015EE10 != &qword_14015EE08 )
    __fastfail(3u);
  v16 = DriverObjectExtension;
  *(_QWORD *)DriverObjectExtension = &qword_14015EE08;
  v16[1] = v15;
  *v15 = v16;
  qword_14015EE10 = (__int64)v16;
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
  if ( (int)KsrGetFirmwareInformation(&v21) >= 0 && !qword_14015F370 )
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
      qword_14015F370 = (__int64)ExRegisterCallback((PCALLBACK_OBJECT)Size, DpiKsrCallback, &DpGlobals);
      ObfDereferenceObject((PVOID)Size);
      word_14015F378 = 0;
      dword_14015F38C = 0;
    }
    if ( !qword_14015F370 )
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
0x1402a10d8  mov     [rsp-8+arg_18], rbx
0x1402a10dd  push    rbp
0x1402a10de  push    rsi
0x1402a10df  push    rdi
0x1402a10e0  push    r12
0x1402a10e2  push    r13
0x1402a10e4  push    r14
0x1402a10e6  push    r15
0x1402a10e8  lea     rbp, [rsp-1Fh]
0x1402a10ed  sub     rsp, 0D0h
0x1402a10f4  mov     rax, cs:__security_cookie
0x1402a10fb  xor     rax, rsp
0x1402a10fe  mov     [rbp+4Fh+var_40], rax
0x1402a1102  movups  xmm0, xmmword ptr cs:aDriverIndirect; "\\Driver\\IndirectKmd"
0x1402a1109  mov     rdi, r9
0x1402a110c  mov     r15, r8
0x1402a110f  movups  xmm1, xmmword ptr cs:aDriverIndirect+10h; "IndirectKmd"
0x1402a1116  mov     r12, rdx
0x1402a1119  xor     r13d, r13d
0x1402a111c  movups  [rbp+4Fh+var_68], xmm0
0x1402a1120  lea     rax, [rbp+4Fh+var_68]
0x1402a1124  mov     r8d, 698h; DriverObjectExtensionSize
0x1402a112a  movsd   xmm0, qword ptr cs:aDriverIndirect+20h; "Kmd"
0x1402a1132  lea     r9, [rsp+100h+DriverObjectExtension]; DriverObjectExtension
0x1402a1137  mov     rdx, rcx; ClientIdentificationAddress
0x1402a113a  movsd   [rbp+4Fh+var_48], xmm0
0x1402a113f  mov     rsi, rcx
0x1402a1142  mov     [rsp+100h+DriverObjectExtension], r13
0x1402a1147  mov     dword ptr [rbp+4Fh+Size], r13d
0x1402a114b  movups  [rbp+4Fh+var_58], xmm1
0x1402a114f  mov     qword ptr [rbp+4Fh+String1.Length], 280026h
0x1402a1157  mov     [rbp+4Fh+String1.Buffer], rax
0x1402a115b  call    cs:__imp_IoAllocateDriverObjectExtension
0x1402a1162  nop     dword ptr [rax+rax+00h]
0x1402a1167  movsxd  rbx, eax
0x1402a116a  test    eax, eax
0x1402a116c  jns     short loc_1402A1190
0x1402a116e  mov     rdx, rbx
0x1402a1171  lea     ecx, [r13+2]
0x1402a1175  call    cs:__imp_WdLogSingleEntry1
0x1402a117c  nop     dword ptr [rax+rax+00h]
0x1402a1181  mov     cs:WdLogGlobalForLineNumber, 0D31h
0x1402a118b  jmp     loc_1402A18A9
0x1402a1190  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1195  lea     rdx, [rsi+38h]; String2
0x1402a1199  mov     r14d, 2
0x1402a119f  mov     r8b, 1; CaseInSensitive
0x1402a11a2  mov     dword ptr [rax+10h], 74727044h
0x1402a11a9  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a11ae  mov     dword ptr [rax+14h], 1
0x1402a11b5  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a11ba  mov     [rax+18h], r14d
0x1402a11be  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a11c3  mov     [rax+20h], rsi
0x1402a11c7  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a11cc  mov     al, [rbp+4Fh+arg_20]
0x1402a11cf  mov     [rcx+84h], al
0x1402a11d5  lea     rcx, [rbp+4Fh+String1]; String1
0x1402a11d9  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a11de  mov     [rax+86h], r13b
0x1402a11e5  call    cs:__imp_RtlCompareUnicodeString
0x1402a11ec  nop     dword ptr [rax+rax+00h]
0x1402a11f1  test    eax, eax
0x1402a11f3  jnz     short loc_1402A1201
0x1402a11f5  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a11fa  mov     byte ptr [rax+86h], 1
0x1402a1201  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1206  test    r15, r15
0x1402a1209  jz      short loc_1402A127F
0x1402a120b  mov     [rax+85h], r13b
0x1402a1212  lea     r9, [rbp+4Fh+Size]
0x1402a1216  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a121b  xor     ecx, ecx
0x1402a121d  mov     edx, [r15]
0x1402a1220  mov     r8d, 608h
0x1402a1226  mov     [rax+1Ch], edx
0x1402a1229  call    DpiGetDriverDataSizeFromVersion
0x1402a122e  movsxd  rbx, eax
0x1402a1231  test    eax, eax
0x1402a1233  jns     short loc_1402A1256
0x1402a1235  mov     rdx, rbx
0x1402a1238  mov     ecx, r14d
0x1402a123b  call    cs:__imp_WdLogSingleEntry1
0x1402a1242  nop     dword ptr [rax+rax+00h]
0x1402a1247  mov     cs:WdLogGlobalForLineNumber, 0D5Ah
0x1402a1251  jmp     loc_1402A18A9
0x1402a1256  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a125b  mov     rdx, r15; Src
0x1402a125e  mov     r8d, dword ptr [rbp+4Fh+Size]; Size
0x1402a1262  add     rcx, 88h; void *
0x1402a1269  call    memmove
0x1402a126e  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1273  mov     [rax+690h], r13
0x1402a127a  jmp     loc_1402A15AB
0x1402a127f  mov     byte ptr [rax+85h], 1
0x1402a1286  xor     edx, edx; Val
0x1402a1288  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a128d  mov     r8d, 610h; Size
0x1402a1293  add     rcx, 88h; void *
0x1402a129a  call    memset
0x1402a129f  mov     ecx, [rdi]
0x1402a12a1  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12a6  mov     [rax+1Ch], ecx
0x1402a12a9  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12ae  mov     ecx, [rdi]
0x1402a12b0  mov     [rax+88h], ecx
0x1402a12b6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12bb  mov     rcx, [rdi+8]
0x1402a12bf  mov     [rax+90h], rcx
0x1402a12c6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12cb  mov     rcx, [rdi+10h]
0x1402a12cf  mov     [rax+98h], rcx
0x1402a12d6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12db  mov     rcx, [rdi+18h]
0x1402a12df  mov     [rax+0A0h], rcx
0x1402a12e6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12eb  mov     rcx, [rdi+20h]
0x1402a12ef  mov     [rax+0A8h], rcx
0x1402a12f6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a12fb  mov     rcx, [rdi+28h]
0x1402a12ff  mov     [rax+0B0h], rcx
0x1402a1306  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a130b  mov     rcx, [rdi+30h]
0x1402a130f  mov     [rax+0B8h], rcx
0x1402a1316  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a131b  mov     rcx, [rdi+38h]
0x1402a131f  mov     [rax+0C0h], rcx
0x1402a1326  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a132b  mov     rcx, [rdi+40h]
0x1402a132f  mov     [rax+0C8h], rcx
0x1402a1336  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a133b  mov     rcx, [rdi+48h]
0x1402a133f  mov     [rax+0D0h], rcx
0x1402a1346  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a134b  mov     rcx, [rdi+50h]
0x1402a134f  mov     [rax+0D8h], rcx
0x1402a1356  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a135b  mov     rcx, [rdi+58h]
0x1402a135f  mov     [rax+0E0h], rcx
0x1402a1366  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a136b  mov     rcx, [rdi+60h]
0x1402a136f  mov     [rax+0E8h], rcx
0x1402a1376  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a137b  mov     rcx, [rdi+68h]
0x1402a137f  mov     [rax+0F0h], rcx
0x1402a1386  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a138b  mov     rcx, [rdi+70h]
0x1402a138f  mov     [rax+0F8h], rcx
0x1402a1396  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a139b  mov     rcx, [rdi+78h]
0x1402a139f  mov     [rax+100h], rcx
0x1402a13a6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a13ab  mov     rcx, [rdi+80h]
0x1402a13b2  mov     [rax+108h], rcx
0x1402a13b9  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a13be  mov     rcx, [rdi+88h]
0x1402a13c5  mov     [rax+110h], rcx
0x1402a13cc  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a13d1  mov     rcx, [rdi+90h]
0x1402a13d8  mov     [rax+170h], rcx
0x1402a13df  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a13e4  mov     rcx, [rdi+98h]
0x1402a13eb  mov     [rax+178h], rcx
0x1402a13f2  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a13f7  mov     rcx, [rdi+0A0h]
0x1402a13fe  mov     [rax+180h], rcx
0x1402a1405  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a140a  mov     rcx, [rdi+0A8h]
0x1402a1411  mov     [rax+198h], rcx
0x1402a1418  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a141d  mov     rcx, [rdi+0B0h]
0x1402a1424  mov     [rax+1A0h], rcx
0x1402a142b  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1430  mov     rcx, [rdi+0B8h]
0x1402a1437  mov     [rax+1B0h], rcx
0x1402a143e  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1443  mov     rcx, [rdi+0C0h]
0x1402a144a  mov     [rax+1B8h], rcx
0x1402a1451  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1456  mov     rcx, [rdi+0C8h]
0x1402a145d  mov     [rax+1C0h], rcx
0x1402a1464  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1469  mov     rcx, [rdi+0D0h]
0x1402a1470  mov     [rax+1D0h], rcx
0x1402a1477  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a147c  mov     rcx, [rdi+0D8h]
0x1402a1483  mov     [rax+1D8h], rcx
0x1402a148a  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a148f  mov     rcx, [rdi+0E0h]
0x1402a1496  mov     [rax+1E0h], rcx
0x1402a149d  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a14a2  mov     rcx, [rdi+0E8h]
0x1402a14a9  mov     [rax+1E8h], rcx
0x1402a14b0  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a14b5  mov     rcx, [rdi+0F0h]
0x1402a14bc  mov     [rax+1F8h], rcx
0x1402a14c3  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a14c8  mov     rcx, [rdi+0F8h]
0x1402a14cf  mov     [rax+2B8h], rcx
0x1402a14d6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a14db  mov     rcx, [rdi+100h]
0x1402a14e2  mov     [rax+690h], rcx
0x1402a14e9  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a14ee  mov     rcx, [rdi+108h]
0x1402a14f5  mov     [rax+2E0h], rcx
0x1402a14fc  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1501  mov     rcx, [rdi+110h]
0x1402a1508  mov     [rax+2E8h], rcx
0x1402a150f  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1514  mov     rcx, [rdi+118h]
0x1402a151b  mov     [rax+2F0h], rcx
0x1402a1522  cmp     dword ptr [rdi], 3005h
0x1402a1528  jb      short loc_1402A153D
0x1402a152a  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a152f  mov     rcx, [rdi+120h]
0x1402a1536  mov     [rax+300h], rcx
0x1402a153d  cmp     dword ptr [rdi], 3007h
0x1402a1543  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1548  jb      short loc_1402A155A
0x1402a154a  mov     rcx, [rdi+128h]
0x1402a1551  mov     [rax+208h], rcx
0x1402a1558  jmp     short loc_1402A1561
0x1402a155a  mov     [rax+1F8h], r13
0x1402a1561  cmp     dword ptr [rdi], 3009h
0x1402a1567  jb      short loc_1402A158F
0x1402a1569  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a156e  mov     rcx, [rdi+130h]
0x1402a1575  mov     [rax+2C0h], rcx
0x1402a157c  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1581  mov     rcx, [rdi+138h]
0x1402a1588  mov     [rax+308h], rcx
0x1402a158f  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a1594  cmp     dword ptr [rcx+1Ch], 5006h
0x1402a159b  jb      short loc_1402A15B0
0x1402a159d  mov     rax, [rdi+148h]
0x1402a15a4  mov     [rcx+3B0h], rax
0x1402a15ab  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a15b0  movzx   eax, word ptr [r12]
0x1402a15b5  mov     r8d, 74727044h
0x1402a15bb  add     ax, r14w
0x1402a15bf  mov     [rcx+2Ah], ax
0x1402a15c3  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a15c8  movzx   ecx, word ptr [r12]
0x1402a15cd  mov     [rax+28h], cx
0x1402a15d1  mov     ecx, 100h
0x1402a15d6  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a15db  movzx   edx, word ptr [rax+2Ah]
0x1402a15df  call    cs:__imp_ExAllocatePool2
0x1402a15e6  nop     dword ptr [rax+rax+00h]
0x1402a15eb  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a15f0  mov     [rcx+30h], rax
0x1402a15f4  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a15f9  mov     rcx, [rax+30h]; void *
0x1402a15fd  test    rcx, rcx
0x1402a1600  jnz     short loc_1402A162C
0x1402a1602  mov     rbx, 0FFFFFFFFC0000017h
0x1402a1609  mov     rdx, rbx
0x1402a160c  mov     ecx, 6
0x1402a1611  call    cs:__imp_WdLogSingleEntry1
0x1402a1618  nop     dword ptr [rax+rax+00h]
0x1402a161d  mov     cs:WdLogGlobalForLineNumber, 0DCAh
0x1402a1627  jmp     loc_1402A18A9
0x1402a162c  movzx   r8d, word ptr [rax+2Ah]; Size
0x1402a1631  xor     edx, edx; Val
0x1402a1633  call    memset
0x1402a1638  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a163d  mov     rdx, r12; SourceString
0x1402a1640  add     rcx, 28h ; '('; DestinationString
0x1402a1644  call    cs:__imp_RtlCopyUnicodeString
0x1402a164b  nop     dword ptr [rax+rax+00h]
0x1402a1650  mov     rcx, [rsp+100h+DriverObjectExtension]
0x1402a1655  xor     edx, edx; Level
0x1402a1657  add     rcx, 48h ; 'H'; Mutex
0x1402a165b  call    cs:__imp_KeInitializeMutex
0x1402a1662  nop     dword ptr [rax+rax+00h]
0x1402a1667  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a166c  add     rax, 38h ; '8'
0x1402a1670  mov     [rax+8], rax
0x1402a1674  mov     [rax], rax
0x1402a1677  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402a167c  mov     rcx, cs:qword_14015EE10
0x1402a1683  lea     rdx, qword_14015EE08
0x1402a168a  cmp     [rcx], rdx
0x1402a168d  jnz     loc_1402A1912
0x1402a1693  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a1698  mov     [rax], rdx
0x1402a169b  mov     [rax+8], rcx
0x1402a169f  mov     [rcx], rax
0x1402a16a2  mov     cs:qword_14015EE10, rax
0x1402a16a9  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402a16ae  mov     rdx, [rsp+100h+DriverObjectExtension]
0x1402a16b3  mov     ecx, 4
0x1402a16b8  call    cs:__imp_WdLogSingleEntry1
0x1402a16bf  nop     dword ptr [rax+rax+00h]
0x1402a16c4  mov     rax, [rsp+100h+DriverObjectExtension]
0x1402a16c9  mov     cs:WdLogGlobalForLineNumber, 0DE4h
0x1402a16d3  cmp     byte ptr [rax+86h], 1
0x1402a16da  jnz     short loc_1402A16EF
0x1402a16dc  lea     rdi, [rsi+70h]
0x1402a16e0  mov     ecx, 1Ch
  ... truncated ...
```
