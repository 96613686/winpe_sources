# PrpWriteLogsToRegistry

- ea: `0x1404d54fc`
- end: `0x1404d5a39`
- name: `PrpWriteLogsToRegistry`
- size: `1341`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1404d5414`

## callees

- `0x140403380`
- `0x1404d54fc`
- `0x140546100`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406ddfe0`

## string_xrefs

- `0x1404d597f`: `Previous Update Revision`
- `0x1404d58d8`: `Update Environment`
- `0x1404d592f`: `Update Revision`
- `0x1404d5828`: `Patch Configuration Used`
- `0x1404d5881`: `Update Status`
- `0x1404d5561`: `Microcode Runtime Update Latency (x100s ns)`

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
    if ( MicrocodeLatencyTime )
    {
      RtlInitUnicodeString(&DestinationString, L"Microcode Runtime Update Latency (x100s ns)");
      ZwSetValueKey(KeyHandle, &DestinationString, 0, 0xBu, &MicrocodeLatencyTime, 8u);
      MicrocodeLatencyTime = 0;
    }
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Patch Source";
    v3 = 2 * wcslen(L"Patch Source");
    if ( v3 >= 0xFFFE )
      LOWORD(v3) = -4;
    DestinationString.Length = v3;
    DestinationString.MaximumLength = v3 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &MCUpdateRegistryData, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Record Type";
    v4 = 2 * wcslen(L"Record Type");
    if ( v4 >= 0xFFFE )
      LOWORD(v4) = -4;
    DestinationString.Length = v4;
    DestinationString.MaximumLength = v4 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&MCUpdateRegistryData + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"CPU Family Model Stepping";
    v5 = 2 * wcslen(L"CPU Family Model Stepping");
    if ( v5 >= 0xFFFE )
      LOWORD(v5) = -4;
    DestinationString.Length = v5;
    DestinationString.MaximumLength = v5 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&MCUpdateRegistryData + 8, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"CPU Meta Data";
    v6 = 2 * wcslen(L"CPU Meta Data");
    if ( v6 >= 0xFFFE )
      LOWORD(v6) = -4;
    DestinationString.Length = v6;
    DestinationString.MaximumLength = v6 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&MCUpdateRegistryData + 12, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Firmware Record Version";
    v7 = 2 * wcslen(L"Firmware Record Version");
    if ( v7 >= 0xFFFE )
      LOWORD(v7) = -4;
    DestinationString.Length = v7;
    DestinationString.MaximumLength = v7 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &xmmword_140EE1A50, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Previous Record Version";
    v8 = 2 * wcslen(L"Previous Record Version");
    if ( v8 >= 0xFFFE )
      LOWORD(v8) = -4;
    DestinationString.Length = v8;
    DestinationString.MaximumLength = v8 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&xmmword_140EE1A50 + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Current Record Version";
    v9 = 2 * wcslen(L"Current Record Version");
    if ( v9 >= 0xFFFE )
      LOWORD(v9) = -4;
    DestinationString.Length = v9;
    DestinationString.MaximumLength = v9 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&xmmword_140EE1A50 + 8, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Preferred Record Version";
    v10 = 2 * wcslen(L"Preferred Record Version");
    if ( v10 >= 0xFFFE )
      LOWORD(v10) = -4;
    DestinationString.Length = v10;
    DestinationString.MaximumLength = v10 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&xmmword_140EE1A50 + 12, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Patch Configuration Used";
    v11 = 2 * wcslen(L"Patch Configuration Used");
    if ( v11 >= 0xFFFE )
      LOWORD(v11) = -4;
    DestinationString.Length = v11;
    DestinationString.MaximumLength = v11 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, &byte_140EE1A60, 1u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Update Status";
    v12 = 2 * wcslen(L"Update Status");
    if ( v12 >= 0xFFFE )
      LOWORD(v12) = -4;
    DestinationString.Length = v12;
    DestinationString.MaximumLength = v12 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &dword_140EE1A64, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Update Environment";
    v13 = 2 * wcslen(L"Update Environment");
    if ( v13 >= 0xFFFE )
      LOWORD(v13) = -4;
    DestinationString.Length = v13;
    DestinationString.MaximumLength = v13 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &dword_140EE1A68, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Update Revision";
    v14 = 2 * wcslen(L"Update Revision");
    if ( v14 >= 0xFFFE )
      LOWORD(v14) = -4;
    DestinationString.Length = v14;
    DestinationString.MaximumLength = v14 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, (char *)&xmmword_140EE1A50 + 8, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Previous Update Revision";
    v15 = 2 * wcslen(L"Previous Update Revision");
    if ( v15 >= 0xFFFE )
      LOWORD(v15) = -4;
    DestinationString.Length = v15;
    DestinationString.MaximumLength = v15 + 2;
    ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, (char *)&xmmword_140EE1A50 + 4, 4u);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = (wchar_t *)L"Platform Specific Field 1";
    v16 = 2 * wcslen(L"Platform Specific Field 1");
    if ( v16 >= 0xFFFE )
      LOWORD(v16) = -4;
    DestinationString.Length = v16;
    DestinationString.MaximumLength = v16 + 2;
    v17 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, (char *)&MCUpdateRegistryData + 12, 4u);
    ZwClose(KeyHandle);
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x1404d54fc  mov     [rsp-40h+KeyHandle], rcx
0x1404d5501  push    rbp
0x1404d5502  push    rbx
0x1404d5503  push    rsi
0x1404d5504  push    rdi
0x1404d5505  push    r12
0x1404d5507  push    r13
0x1404d5509  push    r14
0x1404d550b  push    r15
0x1404d550d  mov     rbp, rsp
0x1404d5510  sub     rsp, 78h
0x1404d5514  xorps   xmm0, xmm0
0x1404d5517  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1404d551b  xor     edi, edi
0x1404d551d  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1404d5525  mov     edx, 2001Fh; DesiredAccess
0x1404d552a  mov     [rbp+KeyHandle], rdi
0x1404d552e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1404d5532  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x1404d5536  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d553a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1404d5542  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1404d5546  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1404d554b  call    ZwOpenKey
0x1404d5550  test    eax, eax
0x1404d5552  js      loc_1404D5A27
0x1404d5558  cmp     cs:MicrocodeLatencyTime, rdi
0x1404d555f  jz      short loc_1404D55A0
0x1404d5561  lea     rdx, aMicrocodeRunti; "Microcode Runtime Update Latency (x100s"...
0x1404d5568  lea     rcx, [rbp+DestinationString]; DestinationString
0x1404d556c  call    RtlInitUnicodeString
0x1404d5571  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d5575  lea     rax, MicrocodeLatencyTime
0x1404d557c  mov     [rsp+78h+DataSize], 8; DataSize
0x1404d5584  lea     r9d, [rdi+0Bh]; Type
0x1404d5588  xor     r8d, r8d; TitleIndex
0x1404d558b  mov     [rsp+78h+Data], rax; Data
0x1404d5590  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d5594  call    ZwSetValueKey
0x1404d5599  mov     cs:MicrocodeLatencyTime, rdi
0x1404d55a0  lea     rcx, aPatchSource; "Patch Source"
0x1404d55a7  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d55ab  mov     [rbp+DestinationString.Buffer], rcx
0x1404d55af  call    wcslen
0x1404d55b4  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d55b8  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d55bc  add     rax, rax
0x1404d55bf  mov     ebx, 0FFFCh
0x1404d55c4  mov     r13d, 4
0x1404d55ca  mov     r15w, 2
0x1404d55cf  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d55d4  mov     r9d, r13d; Type
0x1404d55d7  lea     r12d, [rbx+2]
0x1404d55db  cmp     rax, r12
0x1404d55de  cmovnb  rax, rbx
0x1404d55e2  xor     r8d, r8d; TitleIndex
0x1404d55e5  mov     [rbp+DestinationString.Length], ax
0x1404d55e9  add     ax, r15w
0x1404d55ed  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d55f1  lea     rax, MCUpdateRegistryData
0x1404d55f8  mov     [rsp+78h+Data], rax; Data
0x1404d55fd  call    ZwSetValueKey
0x1404d5602  lea     rcx, aRecordType; "Record Type"
0x1404d5609  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d560d  mov     [rbp+DestinationString.Buffer], rcx
0x1404d5611  call    wcslen
0x1404d5616  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d561a  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d561e  add     rax, rax
0x1404d5621  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d5626  cmp     rax, r12
0x1404d5629  mov     r9d, r13d; Type
0x1404d562c  cmovnb  rax, rbx
0x1404d5630  xor     r8d, r8d; TitleIndex
0x1404d5633  mov     [rbp+DestinationString.Length], ax
0x1404d5637  add     ax, r15w
0x1404d563b  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d563f  lea     rax, MCUpdateRegistryData+4
0x1404d5646  mov     [rsp+78h+Data], rax; Data
0x1404d564b  call    ZwSetValueKey
0x1404d5650  lea     rcx, aCpuFamilyModel; "CPU Family Model Stepping"
0x1404d5657  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d565b  mov     [rbp+DestinationString.Buffer], rcx
0x1404d565f  call    wcslen
0x1404d5664  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d5668  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d566c  add     rax, rax
0x1404d566f  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d5674  cmp     rax, r12
0x1404d5677  mov     r9d, r13d; Type
0x1404d567a  cmovnb  rax, rbx
0x1404d567e  xor     r8d, r8d; TitleIndex
0x1404d5681  mov     [rbp+DestinationString.Length], ax
0x1404d5685  add     ax, r15w
0x1404d5689  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d568d  lea     rax, MCUpdateRegistryData+8
0x1404d5694  mov     [rsp+78h+Data], rax; Data
0x1404d5699  call    ZwSetValueKey
0x1404d569e  lea     rcx, aCpuMetaData; "CPU Meta Data"
0x1404d56a5  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d56a9  mov     [rbp+DestinationString.Buffer], rcx
0x1404d56ad  call    wcslen
0x1404d56b2  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d56b6  lea     r14, MCUpdateRegistryData+0Ch
0x1404d56bd  add     rax, rax
0x1404d56c0  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d56c5  cmp     rax, r12
0x1404d56c8  mov     [rsp+78h+Data], r14; Data
0x1404d56cd  mov     r9d, r13d; Type
0x1404d56d0  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d56d4  cmovnb  rax, rbx
0x1404d56d8  xor     r8d, r8d; TitleIndex
0x1404d56db  mov     [rbp+DestinationString.Length], ax
0x1404d56df  add     ax, r15w
0x1404d56e3  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d56e7  call    ZwSetValueKey
0x1404d56ec  lea     rcx, aFirmwareRecord; "Firmware Record Version"
0x1404d56f3  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d56f7  mov     [rbp+DestinationString.Buffer], rcx
0x1404d56fb  call    wcslen
0x1404d5700  add     rax, rax
0x1404d5703  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d5707  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d570b  cmp     rax, r12
0x1404d570e  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d5713  mov     r9d, r13d; Type
0x1404d5716  cmovnb  rax, rbx
0x1404d571a  xor     r8d, r8d; TitleIndex
0x1404d571d  mov     [rbp+DestinationString.Length], ax
0x1404d5721  add     ax, r15w
0x1404d5725  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d5729  lea     rax, xmmword_140EE1A50
0x1404d5730  mov     [rsp+78h+Data], rax; Data
0x1404d5735  call    ZwSetValueKey
0x1404d573a  lea     rcx, aPreviousRecord; "Previous Record Version"
0x1404d5741  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d5745  mov     [rbp+DestinationString.Buffer], rcx
0x1404d5749  call    wcslen
0x1404d574e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d5752  lea     rsi, xmmword_140EE1A50+4
0x1404d5759  add     rax, rax
0x1404d575c  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d5761  cmp     rax, r12
0x1404d5764  mov     [rsp+78h+Data], rsi; Data
0x1404d5769  mov     r9d, r13d; Type
0x1404d576c  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d5770  cmovnb  rax, rbx
0x1404d5774  xor     r8d, r8d; TitleIndex
0x1404d5777  mov     [rbp+DestinationString.Length], ax
0x1404d577b  add     ax, r15w
0x1404d577f  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d5783  call    ZwSetValueKey
0x1404d5788  lea     rcx, aCurrentRecordV; "Current Record Version"
0x1404d578f  mov     qword ptr [rbp+DestinationString.Length], rdi
0x1404d5793  mov     [rbp+DestinationString.Buffer], rcx
0x1404d5797  call    wcslen
0x1404d579c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d57a0  lea     rdi, xmmword_140EE1A50+8
0x1404d57a7  add     rax, rax
0x1404d57aa  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d57af  cmp     rax, r12
0x1404d57b2  mov     [rsp+78h+Data], rdi; Data
0x1404d57b7  mov     r9d, r13d; Type
0x1404d57ba  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d57be  cmovnb  rax, rbx
0x1404d57c2  xor     r8d, r8d; TitleIndex
0x1404d57c5  mov     [rbp+DestinationString.Length], ax
0x1404d57c9  add     ax, r15w
0x1404d57cd  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d57d1  call    ZwSetValueKey
0x1404d57d6  lea     rcx, aPreferredRecor; "Preferred Record Version"
0x1404d57dd  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d57e5  mov     [rbp+DestinationString.Buffer], rcx
0x1404d57e9  call    wcslen
0x1404d57ee  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d57f2  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d57f6  add     rax, rax
0x1404d57f9  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d57fe  cmp     rax, r12
0x1404d5801  mov     r9d, r13d; Type
0x1404d5804  cmovnb  rax, rbx
0x1404d5808  xor     r8d, r8d; TitleIndex
0x1404d580b  mov     [rbp+DestinationString.Length], ax
0x1404d580f  add     ax, r15w
0x1404d5813  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d5817  lea     rax, xmmword_140EE1A50+0Ch
0x1404d581e  mov     [rsp+78h+Data], rax; Data
0x1404d5823  call    ZwSetValueKey
0x1404d5828  lea     rcx, aPatchConfigura; "Patch Configuration Used"
0x1404d582f  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d5837  mov     [rbp+DestinationString.Buffer], rcx
0x1404d583b  call    wcslen
0x1404d5840  add     rax, rax
0x1404d5843  mov     [rsp+78h+DataSize], 1; DataSize
0x1404d584b  cmp     rax, r12
0x1404d584e  cmovnb  rax, rbx
0x1404d5852  lea     ebx, [r13-1]
0x1404d5856  mov     [rbp+DestinationString.Length], ax
0x1404d585a  add     ax, r15w
0x1404d585e  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d5862  lea     rax, byte_140EE1A60
0x1404d5869  mov     [rsp+78h+Data], rax; Data
0x1404d586e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d5872  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d5876  mov     r9d, ebx; Type
0x1404d5879  xor     r8d, r8d; TitleIndex
0x1404d587c  call    ZwSetValueKey
0x1404d5881  lea     rcx, aUpdateStatus; "Update Status"
0x1404d5888  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d5890  mov     [rbp+DestinationString.Buffer], rcx
0x1404d5894  call    wcslen
0x1404d5899  add     rax, rax
0x1404d589c  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d58a1  cmp     rax, r12
0x1404d58a4  lea     ecx, [r12-2]
0x1404d58a9  mov     r9d, r13d; Type
0x1404d58ac  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d58b0  cmovnb  rax, rcx
0x1404d58b4  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d58b8  mov     [rbp+DestinationString.Length], ax
0x1404d58bc  xor     r8d, r8d; TitleIndex
0x1404d58bf  add     ax, r15w
0x1404d58c3  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d58c7  lea     rax, dword_140EE1A64
0x1404d58ce  mov     [rsp+78h+Data], rax; Data
0x1404d58d3  call    ZwSetValueKey
0x1404d58d8  lea     rcx, aUpdateEnvironm; "Update Environment"
0x1404d58df  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d58e7  mov     [rbp+DestinationString.Buffer], rcx
0x1404d58eb  call    wcslen
0x1404d58f0  add     rax, rax
0x1404d58f3  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d58f8  cmp     rax, r12
0x1404d58fb  lea     ecx, [r12-2]
0x1404d5900  mov     r9d, r13d; Type
0x1404d5903  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d5907  cmovnb  rax, rcx
0x1404d590b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d590f  mov     [rbp+DestinationString.Length], ax
0x1404d5913  xor     r8d, r8d; TitleIndex
0x1404d5916  add     ax, r15w
0x1404d591a  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d591e  lea     rax, dword_140EE1A68
0x1404d5925  mov     [rsp+78h+Data], rax; Data
0x1404d592a  call    ZwSetValueKey
0x1404d592f  lea     rcx, aUpdateRevision; "Update Revision"
0x1404d5936  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d593e  mov     [rbp+DestinationString.Buffer], rcx
0x1404d5942  call    wcslen
0x1404d5947  add     rax, rax
0x1404d594a  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d594f  cmp     rax, r12
0x1404d5952  mov     [rsp+78h+Data], rdi; Data
0x1404d5957  lea     ecx, [r12-2]
0x1404d595c  mov     r9d, ebx; Type
0x1404d595f  cmovnb  rax, rcx
0x1404d5963  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d5967  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d596b  xor     r8d, r8d; TitleIndex
0x1404d596e  mov     [rbp+DestinationString.Length], ax
0x1404d5972  add     ax, r15w
0x1404d5976  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d597a  call    ZwSetValueKey
0x1404d597f  lea     rcx, aPreviousUpdate; "Previous Update Revision"
0x1404d5986  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d598e  mov     [rbp+DestinationString.Buffer], rcx
0x1404d5992  call    wcslen
0x1404d5997  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d599b  lea     edi, [r12-2]
0x1404d59a0  add     rax, rax
0x1404d59a3  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d59a8  cmp     rax, r12
0x1404d59ab  mov     [rsp+78h+Data], rsi; Data
0x1404d59b0  mov     r9d, ebx; Type
0x1404d59b3  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d59b7  cmovnb  rax, rdi
0x1404d59bb  xor     r8d, r8d; TitleIndex
0x1404d59be  mov     [rbp+DestinationString.Length], ax
0x1404d59c2  add     ax, r15w
0x1404d59c6  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d59ca  call    ZwSetValueKey
0x1404d59cf  lea     rcx, aPlatformSpecif; "Platform Specific Field 1"
0x1404d59d6  mov     qword ptr [rbp+DestinationString.Length], 0
0x1404d59de  mov     [rbp+DestinationString.Buffer], rcx
0x1404d59e2  call    wcslen
0x1404d59e7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1404d59eb  lea     rdx, [rbp+DestinationString]; ValueName
0x1404d59ef  add     rax, rax
0x1404d59f2  mov     [rsp+78h+DataSize], r13d; DataSize
0x1404d59f7  cmp     rax, r12
0x1404d59fa  mov     [rsp+78h+Data], r14; Data
0x1404d59ff  mov     r9d, r13d; Type
0x1404d5a02  cmovnb  rax, rdi
0x1404d5a06  xor     r8d, r8d; TitleIndex
0x1404d5a09  mov     [rbp+DestinationString.Length], ax
0x1404d5a0d  add     ax, r15w
0x1404d5a11  mov     [rbp+DestinationString.MaximumLength], ax
0x1404d5a15  call    ZwSetValueKey
0x1404d5a1a  mov     rcx, [rbp+KeyHandle]; Handle
0x1404d5a1e  mov     ebx, eax
  ... truncated ...
```
