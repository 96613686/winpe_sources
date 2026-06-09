# PrpWriteLogsToRegistry

- ea: `0x1404c60ac`
- end: `0x1404c65e9`
- name: `PrpWriteLogsToRegistry`
- size: `1341`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1404c5fc4`

## callees

- `0x1403f2d50`
- `0x1404c60ac`
- `0x14053ea40`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406db490`

## string_xrefs

- `0x1404c652f`: `Previous Update Revision`
- `0x1404c6488`: `Update Environment`
- `0x1404c64df`: `Update Revision`
- `0x1404c63d8`: `Patch Configuration Used`
- `0x1404c6431`: `Update Status`
- `0x1404c6111`: `Microcode Runtime Update Latency (x100s ns)`

## pseudocode

```c
NTSTATUS __fastcall PrpWriteLogsToRegistry(__int64 a1, UNICODE_STRING *a2)
{
  NTSTATUS result; // eax
  size_t v3; // rax
  size_t v4; // rax
  size_t v5; // rax
  size_t v6; // rax
  size_t v7; // rax
  size_t v8; // rax
  size_t v9; // rax
  size_t v10; // rax
  size_t v11; // rax
  size_t v12; // rax
  size_t v13; // rax
  size_t v14; // rax
  size_t v15; // rax
  size_t v16; // rax
  NTSTATUS v17; // ebx
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+C0h] [rbp+48h] BYREF

  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( CmpCallbackListLock.Timer.TimerListEntry.Blink )
    {
      RtlInitUnicodeString(&DestinationString, L"Microcode Runtime Update Latency (x100s ns)");
      ZwSetValueKey(KeyHandle, &DestinationString, 0, 0xBu, &CmpCallbackListLock.Timer.TimerListEntry.Blink, 8u);
      CmpCallbackListLock.Timer.TimerListEntry.Blink = 0;
    }
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Patch Source";
    v3 = 2 * wcslen(L"Patch Source");
    if ( v3 >= 0xFFFE )
      LOWORD(v3) = -4;
    DestinationString.Length = v3;
    DestinationString.MaximumLength = v3 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &CmpCallbackListLock.ApcStateFill[40], 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Record Type";
    v4 = 2 * wcslen(L"Record Type");
    if ( v4 >= 0xFFFE )
      LOWORD(v4) = -4;
    DestinationString.Length = v4;
    DestinationString.MaximumLength = v4 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (PVOID)&CmpCallbackListLock.UserIdealProcessor, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"CPU Family Model Stepping";
    v5 = 2 * wcslen(L"CPU Family Model Stepping");
    if ( v5 >= 0xFFFE )
      LOWORD(v5) = -4;
    DestinationString.Length = v5;
    DestinationString.MaximumLength = v5 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (PVOID)&CmpCallbackListLock.WaitStatus, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"CPU Meta Data";
    v6 = 2 * wcslen(L"CPU Meta Data");
    if ( v6 >= 0xFFFE )
      LOWORD(v6) = -4;
    DestinationString.Length = v6;
    DestinationString.MaximumLength = v6 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&CmpCallbackListLock.WaitStatus + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Firmware Record Version";
    v7 = 2 * wcslen(L"Firmware Record Version");
    if ( v7 >= 0xFFFE )
      LOWORD(v7) = -4;
    DestinationString.Length = v7;
    DestinationString.MaximumLength = v7 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &CmpCallbackListLock.WaitBlockList, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Previous Record Version";
    v8 = 2 * wcslen(L"Previous Record Version");
    if ( v8 >= 0xFFFE )
      LOWORD(v8) = -4;
    DestinationString.Length = v8;
    DestinationString.MaximumLength = v8 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&CmpCallbackListLock.WaitBlockList + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Current Record Version";
    v9 = 2 * wcslen(L"Current Record Version");
    if ( v9 >= 0xFFFE )
      LOWORD(v9) = -4;
    DestinationString.Length = v9;
    DestinationString.MaximumLength = v9 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &CmpCallbackListLock.216, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Preferred Record Version";
    v10 = 2 * wcslen(L"Preferred Record Version");
    if ( v10 >= 0xFFFE )
      LOWORD(v10) = -4;
    DestinationString.Length = v10;
    DestinationString.MaximumLength = v10 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&CmpCallbackListLock.SwapListEntry.Next + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Patch Configuration Used";
    v11 = 2 * wcslen(L"Patch Configuration Used");
    if ( v11 >= 0xFFFE )
      LOWORD(v11) = -4;
    DestinationString.Length = v11;
    DestinationString.MaximumLength = v11 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, &CmpCallbackListLock.SwapListEntry + 1, 1u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Update Status";
    v12 = 2 * wcslen(L"Update Status");
    if ( v12 >= 0xFFFE )
      LOWORD(v12) = -4;
    DestinationString.Length = v12;
    DestinationString.MaximumLength = v12 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&CmpCallbackListLock.SwapListEntry + 12, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Update Environment";
    v13 = 2 * wcslen(L"Update Environment");
    if ( v13 >= 0xFFFE )
      LOWORD(v13) = -4;
    DestinationString.Length = v13;
    DestinationString.MaximumLength = v13 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (PVOID)&CmpCallbackListLock.Queue, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Update Revision";
    v14 = 2 * wcslen(L"Update Revision");
    if ( v14 >= 0xFFFE )
      LOWORD(v14) = -4;
    DestinationString.Length = v14;
    DestinationString.MaximumLength = v14 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, &CmpCallbackListLock.216, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Previous Update Revision";
    v15 = 2 * wcslen(L"Previous Update Revision");
    if ( v15 >= 0xFFFE )
      LOWORD(v15) = -4;
    DestinationString.Length = v15;
    DestinationString.MaximumLength = v15 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, (char *)&CmpCallbackListLock.WaitBlockList + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Platform Specific Field 1";
    v16 = 2 * wcslen(L"Platform Specific Field 1");
    if ( v16 >= 0xFFFE )
      LOWORD(v16) = -4;
    DestinationString.Length = v16;
    DestinationString.MaximumLength = v16 + 2;
    v17 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&CmpCallbackListLock.WaitStatus + 4, 4u);
    ZwClose(KeyHandle);
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x1404c60ac  mov     [rsp-40h+KeyHandle], rcx
0x1404c60b1  push    rbp
0x1404c60b2  push    rbx
0x1404c60b3  push    rsi
0x1404c60b4  push    rdi
0x1404c60b5  push    r12
0x1404c60b7  push    r13
0x1404c60b9  push    r14
0x1404c60bb  push    r15
0x1404c60bd  mov     rbp, rsp
0x1404c60c0  sub     rsp, 78h
0x1404c60c4  xorps   xmm0, xmm0
0x1404c60c7  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1404c60cb  xor     edi, edi
0x1404c60cd  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1404c60d5  mov     edx, 2001Fh; DesiredAccess
0x1404c60da  mov     [rbp+KeyHandle], rdi
0x1404c60de  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1404c60e2  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x1404c60e6  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c60ea  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1404c60f2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1404c60f6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1404c60fb  call    ZwOpenKey
0x1404c6100  test    eax, eax
0x1404c6102  js      loc_1404C65D7
0x1404c6108  cmp     cs:CmpCallbackListLock.Timer.TimerListEntry.Blink, rdi
0x1404c610f  jz      short loc_1404C6150
0x1404c6111  lea     rdx, aMicrocodeRunti; "Microcode Runtime Update Latency (x100s"...
0x1404c6118  lea     rcx, [rbp+DestinationString]; DestinationString
0x1404c611c  call    RtlInitUnicodeString
0x1404c6121  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6125  lea     rax, CmpCallbackListLock.Timer.TimerListEntry.Blink
0x1404c612c  mov     [rsp+78h+DataSize], 8; DataSize
0x1404c6134  lea     r9d, [rdi+0Bh]; Type
0x1404c6138  xor     r8d, r8d; TitleIndex
0x1404c613b  mov     [rsp+78h+Data], rax; Data
0x1404c6140  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6144  call    ZwSetValueKey
0x1404c6149  mov     cs:CmpCallbackListLock.Timer.TimerListEntry.Blink, rdi
0x1404c6150  lea     rcx, aPatchSource; "Patch Source"
0x1404c6157  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c615b  mov     [rbp+DestinationString.Buffer], rcx
0x1404c615f  call    wcslen
0x1404c6164  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6168  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c616c  add     rax, rax
0x1404c616f  mov     ebx, 0FFFCh
0x1404c6174  mov     r13d, 4
0x1404c617a  mov     r15w, 2
0x1404c617f  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c6184  mov     r9d, r13d; Type
0x1404c6187  lea     r12d, [rbx+2]
0x1404c618b  cmp     rax, r12
0x1404c618e  cmovnb  rax, rbx
0x1404c6192  xor     r8d, r8d; TitleIndex
0x1404c6195  mov     [rbp+DestinationString.Length], ax
0x1404c6199  add     ax, r15w
0x1404c619d  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c61a1  lea     rax, CmpCallbackListLock.___u25+28h
0x1404c61a8  mov     [rsp+78h+Data], rax; Data
0x1404c61ad  call    ZwSetValueKey
0x1404c61b2  lea     rcx, aRecordType; "Record Type"
0x1404c61b9  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c61bd  mov     [rbp+DestinationString.Buffer], rcx
0x1404c61c1  call    wcslen
0x1404c61c6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c61ca  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c61ce  add     rax, rax
0x1404c61d1  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c61d6  cmp     rax, r12
0x1404c61d9  mov     r9d, r13d; Type
0x1404c61dc  cmovnb  rax, rbx
0x1404c61e0  xor     r8d, r8d; TitleIndex
0x1404c61e3  mov     [rbp+DestinationString.Length], ax
0x1404c61e7  add     ax, r15w
0x1404c61eb  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c61ef  lea     rax, CmpCallbackListLock.___u25+2Ch
0x1404c61f6  mov     [rsp+78h+Data], rax; Data
0x1404c61fb  call    ZwSetValueKey
0x1404c6200  lea     rcx, aCpuFamilyModel; "CPU Family Model Stepping"
0x1404c6207  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c620b  mov     [rbp+DestinationString.Buffer], rcx
0x1404c620f  call    wcslen
0x1404c6214  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6218  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c621c  add     rax, rax
0x1404c621f  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c6224  cmp     rax, r12
0x1404c6227  mov     r9d, r13d; Type
0x1404c622a  cmovnb  rax, rbx
0x1404c622e  xor     r8d, r8d; TitleIndex
0x1404c6231  mov     [rbp+DestinationString.Length], ax
0x1404c6235  add     ax, r15w
0x1404c6239  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c623d  lea     rax, CmpCallbackListLock.WaitStatus
0x1404c6244  mov     [rsp+78h+Data], rax; Data
0x1404c6249  call    ZwSetValueKey
0x1404c624e  lea     rcx, aCpuMetaData; "CPU Meta Data"
0x1404c6255  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c6259  mov     [rbp+DestinationString.Buffer], rcx
0x1404c625d  call    wcslen
0x1404c6262  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6266  lea     r14, CmpCallbackListLock.WaitStatus+4
0x1404c626d  add     rax, rax
0x1404c6270  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c6275  cmp     rax, r12
0x1404c6278  mov     [rsp+78h+Data], r14; Data
0x1404c627d  mov     r9d, r13d; Type
0x1404c6280  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6284  cmovnb  rax, rbx
0x1404c6288  xor     r8d, r8d; TitleIndex
0x1404c628b  mov     [rbp+DestinationString.Length], ax
0x1404c628f  add     ax, r15w
0x1404c6293  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c6297  call    ZwSetValueKey
0x1404c629c  lea     rcx, aFirmwareRecord; "Firmware Record Version"
0x1404c62a3  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c62a7  mov     [rbp+DestinationString.Buffer], rcx
0x1404c62ab  call    wcslen
0x1404c62b0  add     rax, rax
0x1404c62b3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c62b7  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c62bb  cmp     rax, r12
0x1404c62be  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c62c3  mov     r9d, r13d; Type
0x1404c62c6  cmovnb  rax, rbx
0x1404c62ca  xor     r8d, r8d; TitleIndex
0x1404c62cd  mov     [rbp+DestinationString.Length], ax
0x1404c62d1  add     ax, r15w
0x1404c62d5  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c62d9  lea     rax, CmpCallbackListLock.WaitBlockList
0x1404c62e0  mov     [rsp+78h+Data], rax; Data
0x1404c62e5  call    ZwSetValueKey
0x1404c62ea  lea     rcx, aPreviousRecord; "Previous Record Version"
0x1404c62f1  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c62f5  mov     [rbp+DestinationString.Buffer], rcx
0x1404c62f9  call    wcslen
0x1404c62fe  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6302  lea     rsi, CmpCallbackListLock.WaitBlockList+4
0x1404c6309  add     rax, rax
0x1404c630c  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c6311  cmp     rax, r12
0x1404c6314  mov     [rsp+78h+Data], rsi; Data
0x1404c6319  mov     r9d, r13d; Type
0x1404c631c  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6320  cmovnb  rax, rbx
0x1404c6324  xor     r8d, r8d; TitleIndex
0x1404c6327  mov     [rbp+DestinationString.Length], ax
0x1404c632b  add     ax, r15w
0x1404c632f  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c6333  call    ZwSetValueKey
0x1404c6338  lea     rcx, aCurrentRecordV; "Current Record Version"
0x1404c633f  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404c6343  mov     [rbp+DestinationString.Buffer], rcx
0x1404c6347  call    wcslen
0x1404c634c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6350  lea     rdi, CmpCallbackListLock.___u28
0x1404c6357  add     rax, rax
0x1404c635a  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c635f  cmp     rax, r12
0x1404c6362  mov     [rsp+78h+Data], rdi; Data
0x1404c6367  mov     r9d, r13d; Type
0x1404c636a  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c636e  cmovnb  rax, rbx
0x1404c6372  xor     r8d, r8d; TitleIndex
0x1404c6375  mov     [rbp+DestinationString.Length], ax
0x1404c6379  add     ax, r15w
0x1404c637d  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c6381  call    ZwSetValueKey
0x1404c6386  lea     rcx, aPreferredRecor; "Preferred Record Version"
0x1404c638d  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c6395  mov     [rbp+DestinationString.Buffer], rcx
0x1404c6399  call    wcslen
0x1404c639e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c63a2  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c63a6  add     rax, rax
0x1404c63a9  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c63ae  cmp     rax, r12
0x1404c63b1  mov     r9d, r13d; Type
0x1404c63b4  cmovnb  rax, rbx
0x1404c63b8  xor     r8d, r8d; TitleIndex
0x1404c63bb  mov     [rbp+DestinationString.Length], ax
0x1404c63bf  add     ax, r15w
0x1404c63c3  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c63c7  lea     rax, CmpCallbackListLock.___u28+4
0x1404c63ce  mov     [rsp+78h+Data], rax; Data
0x1404c63d3  call    ZwSetValueKey
0x1404c63d8  lea     rcx, aPatchConfigura; "Patch Configuration Used"
0x1404c63df  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c63e7  mov     [rbp+DestinationString.Buffer], rcx
0x1404c63eb  call    wcslen
0x1404c63f0  add     rax, rax
0x1404c63f3  mov     [rsp+78h+DataSize], 1; DataSize
0x1404c63fb  cmp     rax, r12
0x1404c63fe  cmovnb  rax, rbx
0x1404c6402  lea     ebx, [r13-1]
0x1404c6406  mov     [rbp+DestinationString.Length], ax
0x1404c640a  add     ax, r15w
0x1404c640e  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c6412  lea     rax, CmpCallbackListLock.___u28+8
0x1404c6419  mov     [rsp+78h+Data], rax; Data
0x1404c641e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6422  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6426  mov     r9d, ebx; Type
0x1404c6429  xor     r8d, r8d; TitleIndex
0x1404c642c  call    ZwSetValueKey
0x1404c6431  lea     rcx, aUpdateStatus; "Update Status"
0x1404c6438  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c6440  mov     [rbp+DestinationString.Buffer], rcx
0x1404c6444  call    wcslen
0x1404c6449  add     rax, rax
0x1404c644c  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c6451  cmp     rax, r12
0x1404c6454  lea     ecx, [r12-2]
0x1404c6459  mov     r9d, r13d; Type
0x1404c645c  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6460  cmovnb  rax, rcx
0x1404c6464  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c6468  mov     [rbp+DestinationString.Length], ax
0x1404c646c  xor     r8d, r8d; TitleIndex
0x1404c646f  add     ax, r15w
0x1404c6473  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c6477  lea     rax, CmpCallbackListLock.___u28+0Ch
0x1404c647e  mov     [rsp+78h+Data], rax; Data
0x1404c6483  call    ZwSetValueKey
0x1404c6488  lea     rcx, aUpdateEnvironm; "Update Environment"
0x1404c648f  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c6497  mov     [rbp+DestinationString.Buffer], rcx
0x1404c649b  call    wcslen
0x1404c64a0  add     rax, rax
0x1404c64a3  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c64a8  cmp     rax, r12
0x1404c64ab  lea     ecx, [r12-2]
0x1404c64b0  mov     r9d, r13d; Type
0x1404c64b3  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c64b7  cmovnb  rax, rcx
0x1404c64bb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c64bf  mov     [rbp+DestinationString.Length], ax
0x1404c64c3  xor     r8d, r8d; TitleIndex
0x1404c64c6  add     ax, r15w
0x1404c64ca  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c64ce  lea     rax, CmpCallbackListLock.Queue
0x1404c64d5  mov     [rsp+78h+Data], rax; Data
0x1404c64da  call    ZwSetValueKey
0x1404c64df  lea     rcx, aUpdateRevision; "Update Revision"
0x1404c64e6  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c64ee  mov     [rbp+DestinationString.Buffer], rcx
0x1404c64f2  call    wcslen
0x1404c64f7  add     rax, rax
0x1404c64fa  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c64ff  cmp     rax, r12
0x1404c6502  mov     [rsp+78h+Data], rdi; Data
0x1404c6507  lea     ecx, [r12-2]
0x1404c650c  mov     r9d, ebx; Type
0x1404c650f  cmovnb  rax, rcx
0x1404c6513  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6517  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c651b  xor     r8d, r8d; TitleIndex
0x1404c651e  mov     [rbp+DestinationString.Length], ax
0x1404c6522  add     ax, r15w
0x1404c6526  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c652a  call    ZwSetValueKey
0x1404c652f  lea     rcx, aPreviousUpdate; "Previous Update Revision"
0x1404c6536  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c653e  mov     [rbp+DestinationString.Buffer], rcx
0x1404c6542  call    wcslen
0x1404c6547  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c654b  lea     edi, [r12-2]
0x1404c6550  add     rax, rax
0x1404c6553  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c6558  cmp     rax, r12
0x1404c655b  mov     [rsp+78h+Data], rsi; Data
0x1404c6560  mov     r9d, ebx; Type
0x1404c6563  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c6567  cmovnb  rax, rdi
0x1404c656b  xor     r8d, r8d; TitleIndex
0x1404c656e  mov     [rbp+DestinationString.Length], ax
0x1404c6572  add     ax, r15w
0x1404c6576  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c657a  call    ZwSetValueKey
0x1404c657f  lea     rcx, aPlatformSpecif; "Platform Specific Field 1"
0x1404c6586  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404c658e  mov     [rbp+DestinationString.Buffer], rcx
0x1404c6592  call    wcslen
0x1404c6597  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404c659b  lea     rdx, [rbp+DestinationString]; ValueName
0x1404c659f  add     rax, rax
0x1404c65a2  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404c65a7  cmp     rax, r12
0x1404c65aa  mov     [rsp+78h+Data], r14; Data
0x1404c65af  mov     r9d, r13d; Type
0x1404c65b2  cmovnb  rax, rdi
0x1404c65b6  xor     r8d, r8d; TitleIndex
0x1404c65b9  mov     [rbp+DestinationString.Length], ax
0x1404c65bd  add     ax, r15w
0x1404c65c1  mov     [rbp+DestinationString.MaximumLength], ax
0x1404c65c5  call    ZwSetValueKey
0x1404c65ca  mov     rcx, [rbp+KeyHandle]; Handle
0x1404c65ce  mov     ebx, eax
  ... truncated ...
```
