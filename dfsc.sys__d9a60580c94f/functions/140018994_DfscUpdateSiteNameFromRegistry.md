# DfscUpdateSiteNameFromRegistry

- ea: `0x140018994`
- end: `0x140018ba9`
- name: `DfscUpdateSiteNameFromRegistry`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400186bc`
- `0x1400188c0`

## callees

- `0x140001744`
- `0x140006080`
- `0x140018994`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400189c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400189d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018b61`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400189c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400189d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018b61`
- `ntoskrnl!ZwQueryValueKey` at `0x140018a02`
- `ntoskrnl!ZwQueryValueKey` at `0x140018a68`
- `ntoskrnl!ZwQueryValueKey` at `0x140018a02`
- `ntoskrnl!ZwQueryValueKey` at `0x140018a68`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018ae7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018ae7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b8f`
- `ntoskrnl!ExAllocatePool2` at `0x140018a2e`
- `ntoskrnl!ExAllocatePool2` at `0x140018a2e`

## pseudocode

```c
void DfscUpdateSiteNameFromRegistry()
{
  NTSTATUS v0; // eax
  _DWORD *Pool2; // rbx
  unsigned int v2; // edi
  unsigned __int64 v3; // rsi
  UNICODE_STRING String2; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+90h] [rbp+38h] BYREF

  DestinationString = 0;
  ResultLength = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, L"SiteName");
  RtlInitUnicodeString(&String2, 0);
  v0 = ZwQueryValueKey(SiteNameRegKeyMonitor, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v0 != -1073741789 )
  {
    Pool2 = 0;
    if ( v0 >= 0 )
      return;
    goto LABEL_16;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(258, ResultLength + 2LL, 1262708292);
  if ( !Pool2
    || ZwQueryValueKey(
         SiteNameRegKeyMonitor,
         &DestinationString,
         KeyValueFullInformation,
         Pool2,
         ResultLength,
         &ResultLength) < 0
    || Pool2[1] != 1
    || (v2 = Pool2[3], (v2 & 1) != 0) )
  {
LABEL_16:
    if ( !::DestinationString.Buffer )
      goto LABEL_19;
    ExFreePoolWithTag(::DestinationString.Buffer, 0);
    RtlInitUnicodeString(&::DestinationString, 0);
LABEL_18:
    DfscCachePurge((PUNICODE_PREFIX_TABLE)WPP_MAIN_CB.SecurityDescriptor);
    DfscCachePurge(*(PUNICODE_PREFIX_TABLE *)&WPP_MAIN_CB.ActiveThreadCount);
LABEL_19:
    if ( !Pool2 )
      return;
    goto LABEL_20;
  }
  memmove(Pool2, (char *)Pool2 + (unsigned int)Pool2[2], v2);
  if ( v2 < 2 )
    goto LABEL_11;
  v3 = (unsigned __int64)v2 >> 1;
  if ( *((_WORD *)Pool2 + v3 - 1) )
  {
    *((_WORD *)Pool2 + v3) = 0;
  }
  else
  {
    v2 -= 2;
    if ( v2 < 2 )
      goto LABEL_11;
  }
  String2.Length = v2;
  String2.MaximumLength = ResultLength + 2;
  String2.Buffer = (PWSTR)Pool2;
LABEL_11:
  if ( !RtlEqualUnicodeString(&::DestinationString, &String2, 1u) )
  {
    if ( ::DestinationString.Buffer )
      ExFreePoolWithTag(::DestinationString.Buffer, 0);
    ::DestinationString.Buffer = (PWSTR)Pool2;
    ::DestinationString.MaximumLength = ResultLength + 2;
    Pool2 = 0;
    ::DestinationString.Length = v2;
    goto LABEL_18;
  }
LABEL_20:
  ExFreePoolWithTag(Pool2, 0);
}

```

## disassembly

```asm
0x140018994  push    rbp
0x140018996  push    rbx
0x140018997  push    rsi
0x140018998  push    rdi
0x140018999  push    r14
0x14001899b  push    r15
0x14001899d  mov     rbp, rsp
0x1400189a0  sub     rsp, 58h
0x1400189a4  xorps   xmm0, xmm0
0x1400189a7  lea     rdx, aSitename; "SiteName"
0x1400189ae  xorps   xmm1, xmm1
0x1400189b1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400189b5  xor     r14d, r14d
0x1400189b8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400189bc  mov     [rbp+arg_0], r14d
0x1400189c0  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1400189c4  call    cs:__imp_RtlInitUnicodeString
0x1400189cb  nop     dword ptr [rax+rax+00h]
0x1400189d0  xor     edx, edx; SourceString
0x1400189d2  lea     rcx, [rbp+String2]; DestinationString
0x1400189d6  call    cs:__imp_RtlInitUnicodeString
0x1400189dd  nop     dword ptr [rax+rax+00h]
0x1400189e2  mov     rcx, cs:SiteNameRegKeyMonitor; KeyHandle
0x1400189e9  lea     rax, [rbp+arg_0]
0x1400189ed  mov     [rsp+58h+ResultLength], rax; ResultLength
0x1400189f2  lea     r8d, [r14+1]; KeyValueInformationClass
0x1400189f6  xor     r9d, r9d; KeyValueInformation
0x1400189f9  mov     [rsp+58h+Length], r14d; Length
0x1400189fe  lea     rdx, [rbp+DestinationString]; ValueName
0x140018a02  call    cs:__imp_ZwQueryValueKey
0x140018a09  nop     dword ptr [rax+rax+00h]
0x140018a0e  cmp     eax, 0C0000023h
0x140018a13  jnz     loc_140018B37
0x140018a19  mov     edx, [rbp+arg_0]
0x140018a1c  lea     r15d, [r14+2]
0x140018a20  add     rdx, r15
0x140018a23  mov     ecx, 102h
0x140018a28  mov     r8d, 4B436644h
0x140018a2e  call    cs:__imp_ExAllocatePool2
0x140018a35  nop     dword ptr [rax+rax+00h]
0x140018a3a  mov     rbx, rax
0x140018a3d  test    rax, rax
0x140018a40  jz      loc_140018B3E
0x140018a46  mov     ecx, [rbp+arg_0]
0x140018a49  lea     rax, [rbp+arg_0]
0x140018a4d  mov     [rsp+58h+ResultLength], rax; ResultLength
0x140018a52  lea     r8d, [r14+1]; KeyValueInformationClass
0x140018a56  mov     [rsp+58h+Length], ecx; Length
0x140018a5a  lea     rdx, [rbp+DestinationString]; ValueName
0x140018a5e  mov     rcx, cs:SiteNameRegKeyMonitor; KeyHandle
0x140018a65  mov     r9, rbx; KeyValueInformation
0x140018a68  call    cs:__imp_ZwQueryValueKey
0x140018a6f  nop     dword ptr [rax+rax+00h]
0x140018a74  test    eax, eax
0x140018a76  js      loc_140018B3E
0x140018a7c  cmp     dword ptr [rbx+4], 1
0x140018a80  jnz     loc_140018B3E
0x140018a86  mov     edi, [rbx+0Ch]
0x140018a89  test    dil, 1
0x140018a8d  jnz     loc_140018B3E
0x140018a93  mov     edx, [rbx+8]
0x140018a96  mov     r8d, edi; Size
0x140018a99  add     rdx, rbx; Src
0x140018a9c  mov     rcx, rbx; void *
0x140018a9f  mov     esi, edi
0x140018aa1  call    memmove
0x140018aa6  cmp     edi, r15d
0x140018aa9  jb      short loc_140018AD9
0x140018aab  shr     rsi, 1
0x140018aae  cmp     [rbx+rsi*2-2], r14w
0x140018ab4  jz      short loc_140018ABD
0x140018ab6  mov     [rbx+rsi*2], r14w
0x140018abb  jmp     short loc_140018AC5
0x140018abd  add     edi, 0FFFFFFFEh
0x140018ac0  cmp     edi, r15d
0x140018ac3  jb      short loc_140018AD9
0x140018ac5  movzx   eax, word ptr [rbp+arg_0]
0x140018ac9  add     ax, r15w
0x140018acd  mov     [rbp+String2.Length], di
0x140018ad1  mov     [rbp+String2.MaximumLength], ax
0x140018ad5  mov     [rbp+String2.Buffer], rbx
0x140018ad9  mov     r8b, 1; CaseInSensitive
0x140018adc  lea     rdx, [rbp+String2]; String2
0x140018ae0  lea     rcx, DestinationString; String1
0x140018ae7  call    cs:__imp_RtlEqualUnicodeString
0x140018aee  nop     dword ptr [rax+rax+00h]
0x140018af3  test    al, al
0x140018af5  jnz     loc_140018B8A
0x140018afb  mov     rcx, cs:DestinationString.Buffer; P
0x140018b02  test    rcx, rcx
0x140018b05  jz      short loc_140018B15
0x140018b07  xor     edx, edx; Tag
0x140018b09  call    cs:__imp_ExFreePoolWithTag
0x140018b10  nop     dword ptr [rax+rax+00h]
0x140018b15  movzx   eax, word ptr [rbp+arg_0]
0x140018b19  add     ax, r15w
0x140018b1d  mov     cs:DestinationString.Buffer, rbx
0x140018b24  mov     cs:DestinationString.MaximumLength, ax
0x140018b2b  mov     rbx, r14
0x140018b2e  mov     cs:DestinationString.Length, di
0x140018b35  jmp     short loc_140018B6D
0x140018b37  mov     rbx, r14
0x140018b3a  test    eax, eax
0x140018b3c  jns     short loc_140018B9B
0x140018b3e  mov     rcx, cs:DestinationString.Buffer; P
0x140018b45  test    rcx, rcx
0x140018b48  jz      short loc_140018B85
0x140018b4a  xor     edx, edx; Tag
0x140018b4c  call    cs:__imp_ExFreePoolWithTag
0x140018b53  nop     dword ptr [rax+rax+00h]
0x140018b58  xor     edx, edx; SourceString
0x140018b5a  lea     rcx, DestinationString; DestinationString
0x140018b61  call    cs:__imp_RtlInitUnicodeString
0x140018b68  nop     dword ptr [rax+rax+00h]
0x140018b6d  mov     rcx, cs:WPP_MAIN_CB.SecurityDescriptor; PrefixTable
0x140018b74  call    DfscCachePurge
0x140018b79  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount; PrefixTable
0x140018b80  call    DfscCachePurge
0x140018b85  test    rbx, rbx
0x140018b88  jz      short loc_140018B9B
0x140018b8a  xor     edx, edx; Tag
0x140018b8c  mov     rcx, rbx; P
0x140018b8f  call    cs:__imp_ExFreePoolWithTag
0x140018b96  nop     dword ptr [rax+rax+00h]
0x140018b9b  add     rsp, 58h
0x140018b9f  pop     r15
0x140018ba1  pop     r14
0x140018ba3  pop     rdi
0x140018ba4  pop     rsi
0x140018ba5  pop     rbx
0x140018ba6  pop     rbp
0x140018ba7  retn
```
