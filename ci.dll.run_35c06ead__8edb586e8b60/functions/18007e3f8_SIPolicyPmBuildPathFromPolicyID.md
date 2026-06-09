# SIPolicyPmBuildPathFromPolicyID

- ea: `0x18007e3f8`
- end: `0x18007e676`
- name: `SIPolicyPmBuildPathFromPolicyID`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007eca0`

## callees

- `0x18001f76c`
- `0x18005b41c`
- `0x18005c0bc`
- `0x180079858`
- `0x180079c58`
- `0x18007e190`
- `0x18007e214`
- `0x18007e3f8`
- `0x18007eee0`
- `0x1800e2a68`
- `0x1800e3568`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e5fe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e60e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e61f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e62f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e5fe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e60e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e61f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e62f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e5cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e5ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e5cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e5ed`

## string_xrefs

- `0x18007e473`: `Tokens\Staged`
- `0x18007e444`: `Tokens\Active`

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
0x18007e3f8  push    rbp
0x18007e3fa  push    rbx
0x18007e3fb  push    rsi
0x18007e3fc  push    rdi
0x18007e3fd  push    r12
0x18007e3ff  push    r14
0x18007e401  push    r15
0x18007e403  lea     rbp, [rsp-17h]
0x18007e408  sub     rsp, 0F0h
0x18007e40f  xor     eax, eax
0x18007e411  mov     [rsp+120h+var_F0], 240022h
0x18007e41a  mov     [rbp+47h+var_A0], rax
0x18007e41e  xorps   xmm0, xmm0
0x18007e421  xorps   xmm1, xmm1
0x18007e424  mov     [rsp+120h+var_E0], 1C001Ah
0x18007e42d  lea     rax, aCipoliciesActi; "CiPolicies\\Active"
0x18007e434  mov     [rbp+47h+var_98], 240022h
0x18007e43c  mov     [rsp+120h+var_E8], rax
0x18007e441  mov     r15, r9
0x18007e444  lea     rax, aTokensActive; "Tokens\\Active"
0x18007e44b  mov     [rbp+47h+var_88], 1C001Ah
0x18007e453  mov     [rsp+120h+var_D8], rax
0x18007e458  mov     r12b, r8b
0x18007e45b  xor     eax, eax
0x18007e45d  mov     r14, rcx
0x18007e460  mov     [rbp+47h+var_40], rax
0x18007e464  mov     [rbp+47h+var_68], rax
0x18007e468  lea     rax, aCipoliciesStag; "CiPolicies\\Staged"
0x18007e46f  mov     [rbp+47h+var_90], rax
0x18007e473  lea     rax, aTokensStaged; "Tokens\\Staged"
0x18007e47a  mov     [rbp+47h+var_80], rax
0x18007e47e  movups  xmmword ptr [rbp+47h+Source.Length], xmm0
0x18007e482  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x18007e487  movups  xmmword ptr [rbp+47h+var_C0.Length], xmm1
0x18007e48b  movups  xmmword ptr [rbp+47h+var_60.Length], xmm0
0x18007e48f  movups  xmmword ptr [rsp+120h+UnicodeString.Length], xmm1
0x18007e494  movups  [rbp+47h+var_50], xmm0
0x18007e498  movups  xmmword ptr [rbp+47h+var_78.Length], xmm1
0x18007e49c  test    rcx, rcx
0x18007e49f  jz      short loc_18007E4C7
0x18007e4a1  call    SIPolicyIsLegacyPolicyID
0x18007e4a6  lea     rdx, [rsp+120h+UnicodeString]
0x18007e4ab  mov     rcx, r14
0x18007e4ae  mov     sil, al
0x18007e4b1  call    SIPolicyGetExpectedFilename
0x18007e4b6  mov     ebx, eax
0x18007e4b8  test    eax, eax
0x18007e4ba  js      loc_18007E5F9
0x18007e4c0  lea     rdi, [rsp+120h+var_F0]
0x18007e4c5  jmp     short loc_18007E4E3
0x18007e4c7  lea     rdx, [rsp+120h+UnicodeString]
0x18007e4cc  call    SIPolicyPmGetTokenFileName
0x18007e4d1  mov     ebx, eax
0x18007e4d3  test    eax, eax
0x18007e4d5  js      loc_18007E5F9
0x18007e4db  xor     sil, sil
0x18007e4de  lea     rdi, [rsp+120h+var_E0]
0x18007e4e3  test    r15, r15
0x18007e4e6  jz      short loc_18007E560
0x18007e4e8  test    r14, r14
0x18007e4eb  jz      short loc_18007E514
0x18007e4ed  mov     rax, [r14]
0x18007e4f0  sub     rax, cs:qword_180033650
0x18007e4f7  jnz     short loc_18007E504
0x18007e4f9  mov     rax, [r14+8]
0x18007e4fd  sub     rax, cs:qword_180033658
0x18007e504  test    rax, rax
0x18007e507  jnz     short loc_18007E514
0x18007e509  lea     rcx, [rbp+47h+Source]
0x18007e50d  call    SIPolicyPmGetBootPartitionPolicyFolder10S
0x18007e512  jmp     short loc_18007E539
0x18007e514  xor     edx, edx
0x18007e516  lea     rcx, [rbp+47h+Source]
0x18007e51a  test    r12b, r12b
0x18007e51d  jnz     short loc_18007E52D
0x18007e51f  test    sil, sil
0x18007e522  cmovz   rdx, rdi
0x18007e526  call    SIPolicyPmGetBootPartitionPolicyFolder
0x18007e52b  jmp     short loc_18007E539
0x18007e52d  test    sil, sil
0x18007e530  cmovz   rdx, rdi
0x18007e534  call    SIPolicyPmGetOsDataPartitionPolicyFolder
0x18007e539  mov     ebx, eax
0x18007e53b  test    eax, eax
0x18007e53d  js      loc_18007E5F9
0x18007e543  lea     r8, [rsp+120h+DestinationString]
0x18007e548  lea     rdx, [rsp+120h+UnicodeString]; PCUNICODE_STRING
0x18007e54d  lea     rcx, [rbp+47h+Source]; Source
0x18007e551  call    SIPolicyBuildPath
0x18007e556  mov     ebx, eax
0x18007e558  test    eax, eax
0x18007e55a  js      loc_18007E5F9
0x18007e560  mov     r14, [rbp+47h+arg_20]
0x18007e564  test    r14, r14
0x18007e567  jz      short loc_18007E5B7
0x18007e569  xor     edx, edx
0x18007e56b  lea     rcx, [rbp+47h+var_78]
0x18007e56f  test    r12b, r12b
0x18007e572  jnz     short loc_18007E582
0x18007e574  test    sil, sil
0x18007e577  cmovz   rdx, rdi
0x18007e57b  call    SIPolicyPmGetSystemPartitionPolicyFolder
0x18007e580  jmp     short loc_18007E58E
0x18007e582  test    sil, sil
0x18007e585  cmovz   rdx, rdi
0x18007e589  call    SIPolicyPmGetVirtESPPartitionPolicyFolder
0x18007e58e  mov     ebx, eax
0x18007e590  test    eax, eax
0x18007e592  jns     short loc_18007E59F
0x18007e594  cmp     eax, 0C0000225h
0x18007e599  jnz     short loc_18007E5F9
0x18007e59b  xor     ebx, ebx
0x18007e59d  jmp     short loc_18007E5B7
0x18007e59f  lea     r8, [rbp+47h+var_C0]
0x18007e5a3  lea     rdx, [rsp+120h+UnicodeString]; PCUNICODE_STRING
0x18007e5a8  lea     rcx, [rbp+47h+var_78]; Source
0x18007e5ac  call    SIPolicyBuildPath
0x18007e5b1  mov     ebx, eax
0x18007e5b3  test    eax, eax
0x18007e5b5  js      short loc_18007E5F9
0x18007e5b7  test    r15, r15
0x18007e5ba  jz      short loc_18007E5D9
0x18007e5bc  movups  xmm0, xmmword ptr [rsp+120h+DestinationString.Length]
0x18007e5c1  xor     edx, edx; SourceString
0x18007e5c3  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18007e5c8  movdqu  xmmword ptr [r15], xmm0
0x18007e5cd  call    cs:__imp_RtlInitUnicodeString
0x18007e5d4  nop     dword ptr [rax+rax+00h]
0x18007e5d9  test    r14, r14
0x18007e5dc  jz      short loc_18007E5F9
0x18007e5de  movups  xmm0, xmmword ptr [rbp+47h+var_C0.Length]
0x18007e5e2  xor     edx, edx; SourceString
0x18007e5e4  lea     rcx, [rbp+47h+var_C0]; DestinationString
0x18007e5e8  movdqu  xmmword ptr [r14], xmm0
0x18007e5ed  call    cs:__imp_RtlInitUnicodeString
0x18007e5f4  nop     dword ptr [rax+rax+00h]
0x18007e5f9  lea     rcx, [rsp+120h+UnicodeString]; UnicodeString
0x18007e5fe  call    cs:__imp_RtlFreeUnicodeString
0x18007e605  nop     dword ptr [rax+rax+00h]
0x18007e60a  lea     rcx, [rbp+47h+var_60]; UnicodeString
0x18007e60e  call    cs:__imp_RtlFreeUnicodeString
0x18007e615  nop     dword ptr [rax+rax+00h]
0x18007e61a  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x18007e61f  call    cs:__imp_RtlFreeUnicodeString
0x18007e626  nop     dword ptr [rax+rax+00h]
0x18007e62b  lea     rcx, [rbp+47h+var_C0]; UnicodeString
0x18007e62f  call    cs:__imp_RtlFreeUnicodeString
0x18007e636  nop     dword ptr [rax+rax+00h]
0x18007e63b  mov     edi, 1
0x18007e640  lea     rcx, [rbp+47h+Source]
0x18007e644  mov     edx, edi
0x18007e646  call    SIPolicyPmFreeFileItems
0x18007e64b  mov     edx, edi
0x18007e64d  lea     rcx, [rbp+47h+var_78]
0x18007e651  call    SIPolicyPmFreeFileItems
0x18007e656  mov     edx, edi
0x18007e658  lea     rcx, [rbp+47h+var_50]
0x18007e65c  call    SIPolicyPmFreeFileItems
0x18007e661  mov     eax, ebx
0x18007e663  add     rsp, 0F0h
0x18007e66a  pop     r15
0x18007e66c  pop     r14
0x18007e66e  pop     r12
0x18007e670  pop     rdi
0x18007e671  pop     rsi
0x18007e672  pop     rbx
0x18007e673  pop     rbp
0x18007e674  retn
```
