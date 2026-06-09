# SIPolicyPmBuildPathFromPolicyID

- ea: `0x18007c434`
- end: `0x18007c6b2`
- name: `SIPolicyPmBuildPathFromPolicyID`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007ccdc`

## callees

- `0x18001f75c`
- `0x18005a7dc`
- `0x18005b47c`
- `0x180077f98`
- `0x180078398`
- `0x18007c1cc`
- `0x18007c250`
- `0x18007c434`
- `0x18007cf1c`
- `0x1800a0fd0`
- `0x1800e1aac`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c63a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c64a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c65b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c66b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c63a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c64a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c65b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c66b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007c609`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007c629`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007c609`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007c629`

## string_xrefs

- `0x18007c4af`: `Tokens\Staged`
- `0x18007c480`: `Tokens\Active`

## pseudocode

```c
__int64 __fastcall SIPolicyPmBuildPathFromPolicyID(
        _QWORD *a1,
        __int64 a2,
        char a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5)
{
  char IsLegacyPolicyID; // si
  int ExpectedFilename; // ebx
  _QWORD *v10; // rdi
  __int64 v11; // rax
  int OsDataPartitionPolicyFolder; // eax
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  int VirtESPPartitionPolicyFolder; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-B9h] BYREF
  _QWORD v18[2]; // [rsp+30h] [rbp-A9h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-99h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-89h] BYREF
  struct _UNICODE_STRING v21; // [rsp+60h] [rbp-79h] BYREF
  UNICODE_STRING Source; // [rsp+70h] [rbp-69h] BYREF
  __int64 v23; // [rsp+80h] [rbp-59h]
  __int64 v24; // [rsp+88h] [rbp-51h]
  const wchar_t *v25; // [rsp+90h] [rbp-49h]
  __int64 v26; // [rsp+98h] [rbp-41h]
  const wchar_t *v27; // [rsp+A0h] [rbp-39h]
  UNICODE_STRING v28; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-21h]
  struct _UNICODE_STRING v30; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v31; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v32; // [rsp+E0h] [rbp+7h]

  v18[0] = 2359330;
  v23 = 0;
  v19[0] = 1835034;
  v24 = 2359330;
  v18[1] = L"CiPolicies\\Active";
  v26 = 1835034;
  v19[1] = L"Tokens\\Active";
  v32 = 0;
  v29 = 0;
  v25 = L"CiPolicies\\Staged";
  v27 = L"Tokens\\Staged";
  Source = 0;
  DestinationString = 0;
  v21 = 0;
  v30 = 0;
  UnicodeString = 0;
  v31 = 0;
  v28 = 0;
  if ( a1 )
  {
    IsLegacyPolicyID = SIPolicyIsLegacyPolicyID(a1);
    ExpectedFilename = SIPolicyGetExpectedFilename(a1, &UnicodeString);
    if ( ExpectedFilename < 0 )
      goto LABEL_37;
    v10 = v18;
  }
  else
  {
    ExpectedFilename = SIPolicyPmGetTokenFileName(0, &UnicodeString);
    if ( ExpectedFilename < 0 )
      goto LABEL_37;
    IsLegacyPolicyID = 0;
    v10 = v19;
  }
  if ( !a4 )
    goto LABEL_21;
  if ( !a1 )
    goto LABEL_12;
  v11 = *a1 - 0x4D3DE0B55951A96ALL;
  if ( *a1 == 0x4D3DE0B55951A96ALL )
    v11 = a1[1] + 0x7BF8FC9EA4C14771LL;
  if ( v11 )
  {
LABEL_12:
    v13 = 0;
    if ( a3 )
    {
      if ( !IsLegacyPolicyID )
        v13 = v10;
      OsDataPartitionPolicyFolder = SIPolicyPmGetOsDataPartitionPolicyFolder(&Source, v13);
    }
    else
    {
      if ( !IsLegacyPolicyID )
        v13 = v10;
      OsDataPartitionPolicyFolder = SIPolicyPmGetBootPartitionPolicyFolder(&Source, v13);
    }
  }
  else
  {
    OsDataPartitionPolicyFolder = SIPolicyPmGetBootPartitionPolicyFolder10S(&Source);
  }
  ExpectedFilename = OsDataPartitionPolicyFolder;
  if ( OsDataPartitionPolicyFolder >= 0 )
  {
    ExpectedFilename = SIPolicyBuildPath(&Source, &UnicodeString);
    if ( ExpectedFilename >= 0 )
    {
LABEL_21:
      if ( a5 )
      {
        v14 = 0;
        if ( a3 )
        {
          if ( !IsLegacyPolicyID )
            v14 = v10;
          VirtESPPartitionPolicyFolder = SIPolicyPmGetVirtESPPartitionPolicyFolder(&v28, v14);
        }
        else
        {
          if ( !IsLegacyPolicyID )
            v14 = v10;
          VirtESPPartitionPolicyFolder = SIPolicyPmGetSystemPartitionPolicyFolder(&v28, v14);
        }
        ExpectedFilename = VirtESPPartitionPolicyFolder;
        if ( VirtESPPartitionPolicyFolder >= 0 )
        {
          ExpectedFilename = SIPolicyBuildPath(&v28, &UnicodeString);
          if ( ExpectedFilename < 0 )
            goto LABEL_37;
        }
        else
        {
          if ( VirtESPPartitionPolicyFolder != -1073741275 )
            goto LABEL_37;
          ExpectedFilename = 0;
        }
      }
      if ( a4 )
      {
        *a4 = DestinationString;
        RtlInitUnicodeString(&DestinationString, 0);
      }
      if ( a5 )
      {
        *a5 = v21;
        RtlInitUnicodeString(&v21, 0);
      }
    }
  }
LABEL_37:
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v30);
  RtlFreeUnicodeString(&DestinationString);
  RtlFreeUnicodeString(&v21);
  SIPolicyPmFreeFileItems(&Source, 1);
  SIPolicyPmFreeFileItems(&v28, 1);
  SIPolicyPmFreeFileItems(&v31, 1);
  return (unsigned int)ExpectedFilename;
}

```

## disassembly

```asm
0x18007c434  push    rbp
0x18007c436  push    rbx
0x18007c437  push    rsi
0x18007c438  push    rdi
0x18007c439  push    r12
0x18007c43b  push    r14
0x18007c43d  push    r15
0x18007c43f  lea     rbp, [rsp-17h]
0x18007c444  sub     rsp, 0F0h
0x18007c44b  xor     eax, eax
0x18007c44d  mov     [rsp+120h+var_F0], 240022h
0x18007c456  mov     [rbp+47h+var_A0], rax
0x18007c45a  xorps   xmm0, xmm0
0x18007c45d  xorps   xmm1, xmm1
0x18007c460  mov     [rsp+120h+var_E0], 1C001Ah
0x18007c469  lea     rax, aCipoliciesActi; "CiPolicies\\Active"
0x18007c470  mov     [rbp+47h+var_98], 240022h
0x18007c478  mov     [rsp+120h+var_E8], rax
0x18007c47d  mov     r15, r9
0x18007c480  lea     rax, aTokensActive; "Tokens\\Active"
0x18007c487  mov     [rbp+47h+var_88], 1C001Ah
0x18007c48f  mov     [rsp+120h+var_D8], rax
0x18007c494  mov     r12b, r8b
0x18007c497  xor     eax, eax
0x18007c499  mov     r14, rcx
0x18007c49c  mov     [rbp+47h+var_40], rax
0x18007c4a0  mov     [rbp+47h+var_68], rax
0x18007c4a4  lea     rax, aCipoliciesStag; "CiPolicies\\Staged"
0x18007c4ab  mov     [rbp+47h+var_90], rax
0x18007c4af  lea     rax, aTokensStaged; "Tokens\\Staged"
0x18007c4b6  mov     [rbp+47h+var_80], rax
0x18007c4ba  movups  xmmword ptr [rbp+47h+Source.Length], xmm0
0x18007c4be  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x18007c4c3  movups  xmmword ptr [rbp+47h+var_C0.Length], xmm1
0x18007c4c7  movups  xmmword ptr [rbp+47h+var_60.Length], xmm0
0x18007c4cb  movups  xmmword ptr [rsp+120h+UnicodeString.Length], xmm1
0x18007c4d0  movups  [rbp+47h+var_50], xmm0
0x18007c4d4  movups  xmmword ptr [rbp+47h+var_78.Length], xmm1
0x18007c4d8  test    rcx, rcx
0x18007c4db  jz      short loc_18007C503
0x18007c4dd  call    SIPolicyIsLegacyPolicyID
0x18007c4e2  lea     rdx, [rsp+120h+UnicodeString]
0x18007c4e7  mov     rcx, r14
0x18007c4ea  mov     sil, al
0x18007c4ed  call    SIPolicyGetExpectedFilename
0x18007c4f2  mov     ebx, eax
0x18007c4f4  test    eax, eax
0x18007c4f6  js      loc_18007C635
0x18007c4fc  lea     rdi, [rsp+120h+var_F0]
0x18007c501  jmp     short loc_18007C51F
0x18007c503  lea     rdx, [rsp+120h+UnicodeString]
0x18007c508  call    SIPolicyPmGetTokenFileName
0x18007c50d  mov     ebx, eax
0x18007c50f  test    eax, eax
0x18007c511  js      loc_18007C635
0x18007c517  xor     sil, sil
0x18007c51a  lea     rdi, [rsp+120h+var_E0]
0x18007c51f  test    r15, r15
0x18007c522  jz      short loc_18007C59C
0x18007c524  test    r14, r14
0x18007c527  jz      short loc_18007C550
0x18007c529  mov     rax, [r14]
0x18007c52c  sub     rax, cs:qword_180032800
0x18007c533  jnz     short loc_18007C540
0x18007c535  mov     rax, [r14+8]
0x18007c539  sub     rax, cs:qword_180032808
0x18007c540  test    rax, rax
0x18007c543  jnz     short loc_18007C550
0x18007c545  lea     rcx, [rbp+47h+Source]
0x18007c549  call    SIPolicyPmGetBootPartitionPolicyFolder10S
0x18007c54e  jmp     short loc_18007C575
0x18007c550  xor     edx, edx
0x18007c552  lea     rcx, [rbp+47h+Source]
0x18007c556  test    r12b, r12b
0x18007c559  jnz     short loc_18007C569
0x18007c55b  test    sil, sil
0x18007c55e  cmovz   rdx, rdi
0x18007c562  call    SIPolicyPmGetBootPartitionPolicyFolder
0x18007c567  jmp     short loc_18007C575
0x18007c569  test    sil, sil
0x18007c56c  cmovz   rdx, rdi
0x18007c570  call    SIPolicyPmGetOsDataPartitionPolicyFolder
0x18007c575  mov     ebx, eax
0x18007c577  test    eax, eax
0x18007c579  js      loc_18007C635
0x18007c57f  lea     r8, [rsp+120h+DestinationString]
0x18007c584  lea     rdx, [rsp+120h+UnicodeString]; PCUNICODE_STRING
0x18007c589  lea     rcx, [rbp+47h+Source]; Source
0x18007c58d  call    SIPolicyBuildPath
0x18007c592  mov     ebx, eax
0x18007c594  test    eax, eax
0x18007c596  js      loc_18007C635
0x18007c59c  mov     r14, [rbp+47h+arg_20]
0x18007c5a0  test    r14, r14
0x18007c5a3  jz      short loc_18007C5F3
0x18007c5a5  xor     edx, edx
0x18007c5a7  lea     rcx, [rbp+47h+var_78]
0x18007c5ab  test    r12b, r12b
0x18007c5ae  jnz     short loc_18007C5BE
0x18007c5b0  test    sil, sil
0x18007c5b3  cmovz   rdx, rdi
0x18007c5b7  call    SIPolicyPmGetSystemPartitionPolicyFolder
0x18007c5bc  jmp     short loc_18007C5CA
0x18007c5be  test    sil, sil
0x18007c5c1  cmovz   rdx, rdi
0x18007c5c5  call    SIPolicyPmGetVirtESPPartitionPolicyFolder
0x18007c5ca  mov     ebx, eax
0x18007c5cc  test    eax, eax
0x18007c5ce  jns     short loc_18007C5DB
0x18007c5d0  cmp     eax, 0C0000225h
0x18007c5d5  jnz     short loc_18007C635
0x18007c5d7  xor     ebx, ebx
0x18007c5d9  jmp     short loc_18007C5F3
0x18007c5db  lea     r8, [rbp+47h+var_C0]
0x18007c5df  lea     rdx, [rsp+120h+UnicodeString]; PCUNICODE_STRING
0x18007c5e4  lea     rcx, [rbp+47h+var_78]; Source
0x18007c5e8  call    SIPolicyBuildPath
0x18007c5ed  mov     ebx, eax
0x18007c5ef  test    eax, eax
0x18007c5f1  js      short loc_18007C635
0x18007c5f3  test    r15, r15
0x18007c5f6  jz      short loc_18007C615
0x18007c5f8  movups  xmm0, xmmword ptr [rsp+120h+DestinationString.Length]
0x18007c5fd  xor     edx, edx; SourceString
0x18007c5ff  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18007c604  movdqu  xmmword ptr [r15], xmm0
0x18007c609  call    cs:__imp_RtlInitUnicodeString
0x18007c610  nop     dword ptr [rax+rax+00h]
0x18007c615  test    r14, r14
0x18007c618  jz      short loc_18007C635
0x18007c61a  movups  xmm0, xmmword ptr [rbp+47h+var_C0.Length]
0x18007c61e  xor     edx, edx; SourceString
0x18007c620  lea     rcx, [rbp+47h+var_C0]; DestinationString
0x18007c624  movdqu  xmmword ptr [r14], xmm0
0x18007c629  call    cs:__imp_RtlInitUnicodeString
0x18007c630  nop     dword ptr [rax+rax+00h]
0x18007c635  lea     rcx, [rsp+120h+UnicodeString]; UnicodeString
0x18007c63a  call    cs:__imp_RtlFreeUnicodeString
0x18007c641  nop     dword ptr [rax+rax+00h]
0x18007c646  lea     rcx, [rbp+47h+var_60]; UnicodeString
0x18007c64a  call    cs:__imp_RtlFreeUnicodeString
0x18007c651  nop     dword ptr [rax+rax+00h]
0x18007c656  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x18007c65b  call    cs:__imp_RtlFreeUnicodeString
0x18007c662  nop     dword ptr [rax+rax+00h]
0x18007c667  lea     rcx, [rbp+47h+var_C0]; UnicodeString
0x18007c66b  call    cs:__imp_RtlFreeUnicodeString
0x18007c672  nop     dword ptr [rax+rax+00h]
0x18007c677  mov     edi, 1
0x18007c67c  lea     rcx, [rbp+47h+Source]
0x18007c680  mov     edx, edi
0x18007c682  call    SIPolicyPmFreeFileItems
0x18007c687  mov     edx, edi
0x18007c689  lea     rcx, [rbp+47h+var_78]
0x18007c68d  call    SIPolicyPmFreeFileItems
0x18007c692  mov     edx, edi
0x18007c694  lea     rcx, [rbp+47h+var_50]
0x18007c698  call    SIPolicyPmFreeFileItems
0x18007c69d  mov     eax, ebx
0x18007c69f  add     rsp, 0F0h
0x18007c6a6  pop     r15
0x18007c6a8  pop     r14
0x18007c6aa  pop     r12
0x18007c6ac  pop     rdi
0x18007c6ad  pop     rsi
0x18007c6ae  pop     rbx
0x18007c6af  pop     rbp
0x18007c6b0  retn
```
