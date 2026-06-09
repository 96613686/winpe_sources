# SIPolicyPmBuildPathFromPolicyID

- ea: `0x18007d9e4`
- end: `0x18007dc62`
- name: `SIPolicyPmBuildPathFromPolicyID`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007e28c`

## callees

- `0x18001f69c`
- `0x18005b4ec`
- `0x18005c18c`
- `0x180079548`
- `0x180079948`
- `0x18007d77c`
- `0x18007d800`
- `0x18007d9e4`
- `0x18007e4cc`
- `0x1800a2600`
- `0x1800e2a9c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dbea`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dbfa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dc0b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dc1b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dbea`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dbfa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dc0b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007dc1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007dbb9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007dbd9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007dbb9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007dbd9`

## string_xrefs

- `0x18007da30`: `Tokens\Active`
- `0x18007da5f`: `Tokens\Staged`

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
0x18007d9e4  push    rbp
0x18007d9e6  push    rbx
0x18007d9e7  push    rsi
0x18007d9e8  push    rdi
0x18007d9e9  push    r12
0x18007d9eb  push    r14
0x18007d9ed  push    r15
0x18007d9ef  lea     rbp, [rsp-17h]
0x18007d9f4  sub     rsp, 0F0h
0x18007d9fb  xor     eax, eax
0x18007d9fd  mov     [rsp+120h+var_F0], 240022h
0x18007da06  mov     [rbp+47h+var_A0], rax
0x18007da0a  xorps   xmm0, xmm0
0x18007da0d  xorps   xmm1, xmm1
0x18007da10  mov     [rsp+120h+var_E0], 1C001Ah
0x18007da19  lea     rax, aCipoliciesActi; "CiPolicies\\Active"
0x18007da20  mov     [rbp+47h+var_98], 240022h
0x18007da28  mov     [rsp+120h+var_E8], rax
0x18007da2d  mov     r15, r9
0x18007da30  lea     rax, aTokensActive; "Tokens\\Active"
0x18007da37  mov     [rbp+47h+var_88], 1C001Ah
0x18007da3f  mov     [rsp+120h+var_D8], rax
0x18007da44  mov     r12b, r8b
0x18007da47  xor     eax, eax
0x18007da49  mov     r14, rcx
0x18007da4c  mov     [rbp+47h+var_40], rax
0x18007da50  mov     [rbp+47h+var_68], rax
0x18007da54  lea     rax, aCipoliciesStag; "CiPolicies\\Staged"
0x18007da5b  mov     [rbp+47h+var_90], rax
0x18007da5f  lea     rax, aTokensStaged; "Tokens\\Staged"
0x18007da66  mov     [rbp+47h+var_80], rax
0x18007da6a  movups  xmmword ptr [rbp+47h+Source.Length], xmm0
0x18007da6e  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x18007da73  movups  xmmword ptr [rbp+47h+var_C0.Length], xmm1
0x18007da77  movups  xmmword ptr [rbp+47h+var_60.Length], xmm0
0x18007da7b  movups  xmmword ptr [rsp+120h+UnicodeString.Length], xmm1
0x18007da80  movups  [rbp+47h+var_50], xmm0
0x18007da84  movups  xmmword ptr [rbp+47h+var_78.Length], xmm1
0x18007da88  test    rcx, rcx
0x18007da8b  jz      short loc_18007DAB3
0x18007da8d  call    SIPolicyIsLegacyPolicyID
0x18007da92  lea     rdx, [rsp+120h+UnicodeString]
0x18007da97  mov     rcx, r14
0x18007da9a  mov     sil, al
0x18007da9d  call    SIPolicyGetExpectedFilename
0x18007daa2  mov     ebx, eax
0x18007daa4  test    eax, eax
0x18007daa6  js      loc_18007DBE5
0x18007daac  lea     rdi, [rsp+120h+var_F0]
0x18007dab1  jmp     short loc_18007DACF
0x18007dab3  lea     rdx, [rsp+120h+UnicodeString]
0x18007dab8  call    SIPolicyPmGetTokenFileName
0x18007dabd  mov     ebx, eax
0x18007dabf  test    eax, eax
0x18007dac1  js      loc_18007DBE5
0x18007dac7  xor     sil, sil
0x18007daca  lea     rdi, [rsp+120h+var_E0]
0x18007dacf  test    r15, r15
0x18007dad2  jz      short loc_18007DB4C
0x18007dad4  test    r14, r14
0x18007dad7  jz      short loc_18007DB00
0x18007dad9  mov     rax, [r14]
0x18007dadc  sub     rax, cs:qword_1800337F0
0x18007dae3  jnz     short loc_18007DAF0
0x18007dae5  mov     rax, [r14+8]
0x18007dae9  sub     rax, cs:qword_1800337F8
0x18007daf0  test    rax, rax
0x18007daf3  jnz     short loc_18007DB00
0x18007daf5  lea     rcx, [rbp+47h+Source]
0x18007daf9  call    SIPolicyPmGetBootPartitionPolicyFolder10S
0x18007dafe  jmp     short loc_18007DB25
0x18007db00  xor     edx, edx
0x18007db02  lea     rcx, [rbp+47h+Source]
0x18007db06  test    r12b, r12b
0x18007db09  jnz     short loc_18007DB19
0x18007db0b  test    sil, sil
0x18007db0e  cmovz   rdx, rdi
0x18007db12  call    SIPolicyPmGetBootPartitionPolicyFolder
0x18007db17  jmp     short loc_18007DB25
0x18007db19  test    sil, sil
0x18007db1c  cmovz   rdx, rdi
0x18007db20  call    SIPolicyPmGetOsDataPartitionPolicyFolder
0x18007db25  mov     ebx, eax
0x18007db27  test    eax, eax
0x18007db29  js      loc_18007DBE5
0x18007db2f  lea     r8, [rsp+120h+DestinationString]
0x18007db34  lea     rdx, [rsp+120h+UnicodeString]; PCUNICODE_STRING
0x18007db39  lea     rcx, [rbp+47h+Source]; Source
0x18007db3d  call    SIPolicyBuildPath
0x18007db42  mov     ebx, eax
0x18007db44  test    eax, eax
0x18007db46  js      loc_18007DBE5
0x18007db4c  mov     r14, [rbp+47h+arg_20]
0x18007db50  test    r14, r14
0x18007db53  jz      short loc_18007DBA3
0x18007db55  xor     edx, edx
0x18007db57  lea     rcx, [rbp+47h+var_78]
0x18007db5b  test    r12b, r12b
0x18007db5e  jnz     short loc_18007DB6E
0x18007db60  test    sil, sil
0x18007db63  cmovz   rdx, rdi
0x18007db67  call    SIPolicyPmGetSystemPartitionPolicyFolder
0x18007db6c  jmp     short loc_18007DB7A
0x18007db6e  test    sil, sil
0x18007db71  cmovz   rdx, rdi
0x18007db75  call    SIPolicyPmGetVirtESPPartitionPolicyFolder
0x18007db7a  mov     ebx, eax
0x18007db7c  test    eax, eax
0x18007db7e  jns     short loc_18007DB8B
0x18007db80  cmp     eax, 0C0000225h
0x18007db85  jnz     short loc_18007DBE5
0x18007db87  xor     ebx, ebx
0x18007db89  jmp     short loc_18007DBA3
0x18007db8b  lea     r8, [rbp+47h+var_C0]
0x18007db8f  lea     rdx, [rsp+120h+UnicodeString]; PCUNICODE_STRING
0x18007db94  lea     rcx, [rbp+47h+var_78]; Source
0x18007db98  call    SIPolicyBuildPath
0x18007db9d  mov     ebx, eax
0x18007db9f  test    eax, eax
0x18007dba1  js      short loc_18007DBE5
0x18007dba3  test    r15, r15
0x18007dba6  jz      short loc_18007DBC5
0x18007dba8  movups  xmm0, xmmword ptr [rsp+120h+DestinationString.Length]
0x18007dbad  xor     edx, edx; SourceString
0x18007dbaf  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18007dbb4  movdqu  xmmword ptr [r15], xmm0
0x18007dbb9  call    cs:__imp_RtlInitUnicodeString
0x18007dbc0  nop     dword ptr [rax+rax+00h]
0x18007dbc5  test    r14, r14
0x18007dbc8  jz      short loc_18007DBE5
0x18007dbca  movups  xmm0, xmmword ptr [rbp+47h+var_C0.Length]
0x18007dbce  xor     edx, edx; SourceString
0x18007dbd0  lea     rcx, [rbp+47h+var_C0]; DestinationString
0x18007dbd4  movdqu  xmmword ptr [r14], xmm0
0x18007dbd9  call    cs:__imp_RtlInitUnicodeString
0x18007dbe0  nop     dword ptr [rax+rax+00h]
0x18007dbe5  lea     rcx, [rsp+120h+UnicodeString]; UnicodeString
0x18007dbea  call    cs:__imp_RtlFreeUnicodeString
0x18007dbf1  nop     dword ptr [rax+rax+00h]
0x18007dbf6  lea     rcx, [rbp+47h+var_60]; UnicodeString
0x18007dbfa  call    cs:__imp_RtlFreeUnicodeString
0x18007dc01  nop     dword ptr [rax+rax+00h]
0x18007dc06  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x18007dc0b  call    cs:__imp_RtlFreeUnicodeString
0x18007dc12  nop     dword ptr [rax+rax+00h]
0x18007dc17  lea     rcx, [rbp+47h+var_C0]; UnicodeString
0x18007dc1b  call    cs:__imp_RtlFreeUnicodeString
0x18007dc22  nop     dword ptr [rax+rax+00h]
0x18007dc27  mov     edi, 1
0x18007dc2c  lea     rcx, [rbp+47h+Source]
0x18007dc30  mov     edx, edi
0x18007dc32  call    SIPolicyPmFreeFileItems
0x18007dc37  mov     edx, edi
0x18007dc39  lea     rcx, [rbp+47h+var_78]
0x18007dc3d  call    SIPolicyPmFreeFileItems
0x18007dc42  mov     edx, edi
0x18007dc44  lea     rcx, [rbp+47h+var_50]
0x18007dc48  call    SIPolicyPmFreeFileItems
0x18007dc4d  mov     eax, ebx
0x18007dc4f  add     rsp, 0F0h
0x18007dc56  pop     r15
0x18007dc58  pop     r14
0x18007dc5a  pop     r12
0x18007dc5c  pop     rdi
0x18007dc5d  pop     rsi
0x18007dc5e  pop     rbx
0x18007dc5f  pop     rbp
0x18007dc60  retn
```
