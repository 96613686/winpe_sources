# ComputeHashFromEntryName

- ea: `0x1800aeec0`
- end: `0x1800af485`
- name: `ComputeHashFromEntryName`
- size: `1477`
- prototype: `__int64 __fastcall(LPCWSTR pszString, HGLOBAL *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008a200`
- `0x18008b360`

## callees

- `0x18004e580`
- `0x1800aeec0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800af291`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800af291`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800af42e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800af42e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aef32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af23e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aef32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af01b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af23e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af2f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aef89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af16b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af33c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aef89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af16b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af33c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800af405`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800af413`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aef9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af17f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aef9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af17f`
- `CRYPT32!CryptStringToBinaryW` at `0x1800aef21`
- `CRYPT32!CryptStringToBinaryW` at `0x1800af011`
- `CRYPT32!CryptStringToBinaryW` at `0x1800aef21`
- `CRYPT32!CryptStringToBinaryW` at `0x1800af011`
- `CRYPT32!CryptBinaryToStringW` at `0x1800af234`
- `CRYPT32!CryptBinaryToStringW` at `0x1800af2ec`
- `CRYPT32!CryptBinaryToStringW` at `0x1800af234`
- `CRYPT32!CryptBinaryToStringW` at `0x1800af2ec`
- `bcrypt!BCryptFinishHash` at `0x1800af1db`
- `bcrypt!BCryptFinishHash` at `0x1800af1db`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800af36c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800af36c`
- `bcrypt!BCryptCreateHash` at `0x1800af0d5`
- `bcrypt!BCryptCreateHash` at `0x1800af0d5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800af074`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800af074`
- `bcrypt!BCryptHashData` at `0x1800af127`
- `bcrypt!BCryptHashData` at `0x1800af127`
- `bcrypt!BCryptDestroyHash` at `0x1800af3bc`
- `bcrypt!BCryptDestroyHash` at `0x1800af3bc`

## pseudocode

```c
__int64 __fastcall ComputeHashFromEntryName(LPCWSTR pszString, HGLOBAL *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rdx
  BYTE *v6; // r14
  DWORD LastError; // eax
  DWORD v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v14; // rax
  UCHAR *v15; // r15
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  HANDLE v18; // rax
  UCHAR *v19; // rax
  __int64 v20; // r9
  WCHAR *v21; // rax
  HANDLE v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  HANDLE v25; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbInput; // [rsp+98h] [rbp+48h] BYREF
  DWORD pcchString; // [rsp+A0h] [rbp+50h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+A8h] [rbp+58h] BYREF

  v3 = -1;
  *a2 = 0;
  v4 = -1;
  phAlgorithm = 0;
  phHash = 0;
  cbInput = 0;
  v6 = 0;
  pcchString = 0;
  do
    ++v4;
  while ( pszString[v4] );
  if ( !CryptStringToBinaryW(pszString, v4, 2u, 0, &cbInput, 0, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( !LastError )
    {
LABEL_68:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_69;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 28;
      v11 = LastError;
LABEL_9:
      WPP_SF_d(v9[2], v10, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, v11);
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  v12 = cbInput;
  ProcessHeap = GetProcessHeap();
  v14 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v12);
  v15 = v14;
  if ( v14 )
  {
    do
      ++v3;
    while ( pszString[v3] );
    if ( !CryptStringToBinaryW(pszString, v3, 2u, v14, &cbInput, 0, 0) )
    {
      v8 = GetLastError();
      if ( !v8 )
        goto LABEL_67;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 30;
      goto LABEL_65;
    }
    v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 0);
    if ( v8 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 31;
      goto LABEL_65;
    }
    v8 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v8 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 32;
      goto LABEL_65;
    }
    v8 = BCryptHashData(phHash, v15, cbInput, 0);
    if ( v8 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 33;
      goto LABEL_65;
    }
    v18 = GetProcessHeap();
    v19 = (UCHAR *)HeapAlloc(v18, 8u, 0x10u);
    v6 = v19;
    if ( !v19 )
    {
      v8 = -1073741801;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 34;
      goto LABEL_42;
    }
    v8 = BCryptFinishHash(phHash, v19, 0x10u, 0);
    if ( v8 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 35;
    }
    else if ( CryptBinaryToStringW(v6, 0x10u, 2u, 0, &pcchString) )
    {
      v21 = (WCHAR *)GlobalAlloc(0x40u, 2LL * pcchString);
      *a2 = v21;
      if ( !v21 )
      {
        v8 = -1073741801;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_67;
        }
        v17 = 37;
LABEL_42:
        v20 = 3221225495LL;
LABEL_66:
        WPP_SF_d(v16[2], v17, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, v20);
LABEL_67:
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v15);
        goto LABEL_68;
      }
      if ( CryptBinaryToStringW(v6, 0x10u, 2u, v21, &pcchString) )
        goto LABEL_67;
      v8 = GetLastError();
      if ( !v8 )
        goto LABEL_67;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 38;
    }
    else
    {
      v8 = GetLastError();
      if ( !v8 )
        goto LABEL_67;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v17 = 36;
    }
LABEL_65:
    v20 = v8;
    goto LABEL_66;
  }
  v8 = -1073741801;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 29;
    v11 = 3221225495LL;
    goto LABEL_9;
  }
LABEL_69:
  if ( !phAlgorithm )
    goto LABEL_76;
  v23 = BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( !v23 )
    goto LABEL_75;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, v23);
LABEL_75:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_76:
  if ( !phHash )
    goto LABEL_83;
  v24 = BCryptDestroyHash(phHash);
  if ( !v24 )
    goto LABEL_82;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, v24);
LABEL_82:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_83:
  if ( v6 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v6);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 && *a2 )
  {
    GlobalFree(*a2);
    *a2 = 0;
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 41, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800aeec0  mov     [rsp-38h+arg_0], rbx
0x1800aeec5  push    rbp
0x1800aeec6  push    rsi
0x1800aeec7  push    rdi
0x1800aeec8  push    r12
0x1800aeeca  push    r13
0x1800aeecc  push    r14
0x1800aeece  push    r15
0x1800aeed0  mov     rbp, rsp
0x1800aeed3  sub     rsp, 50h
0x1800aeed7  xor     r13d, r13d
0x1800aeeda  mov     r12, rdx
0x1800aeedd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800aeee1  mov     [rdx], r13
0x1800aeee4  mov     rdx, rdi
0x1800aeee7  mov     [rbp+phAlgorithm], r13
0x1800aeeeb  mov     rsi, rcx
0x1800aeeee  mov     [rbp+phHash], r13
0x1800aeef2  mov     [rbp+cbInput], r13d
0x1800aeef6  mov     r14d, r13d
0x1800aeef9  mov     [rbp+pcchString], r13d
0x1800aeefd  inc     rdx; cchString
0x1800aef00  cmp     [rcx+rdx*2], r13w
0x1800aef05  jnz     short loc_1800AEEFD
0x1800aef07  xor     r9d, r9d; pbBinary
0x1800aef0a  mov     [rsp+50h+pdwFlags], r13; pdwFlags
0x1800aef0f  lea     rax, [rbp+cbInput]
0x1800aef13  mov     [rsp+50h+pdwSkip], r13; pdwSkip
0x1800aef18  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x1800aef1d  lea     r8d, [r9+2]; dwFlags
0x1800aef21  call    cs:__imp_CryptStringToBinaryW
0x1800aef27  lea     r15, WPP_GLOBAL_Control
0x1800aef2e  test    eax, eax
0x1800aef30  jnz     short loc_1800AEF86
0x1800aef32  call    cs:__imp_GetLastError
0x1800aef38  mov     ebx, eax
0x1800aef3a  test    eax, eax
0x1800aef3c  jz      loc_1800AF357
0x1800aef42  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aef49  cmp     rcx, r15
0x1800aef4c  jz      loc_1800AF35E
0x1800aef52  test    dword ptr [rcx+1Ch], 800h
0x1800aef59  jz      loc_1800AF35E
0x1800aef5f  cmp     byte ptr [rcx+19h], 2
0x1800aef63  jb      loc_1800AF35E
0x1800aef69  mov     edx, 1Ch
0x1800aef6e  mov     r9d, eax
0x1800aef71  mov     rcx, [rcx+10h]
0x1800aef75  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800aef7c  call    WPP_SF_d
0x1800aef81  jmp     loc_1800AF357
0x1800aef86  mov     ebx, [rbp+cbInput]
0x1800aef89  call    cs:__imp_GetProcessHeap
0x1800aef8f  mov     r8d, ebx; dwBytes
0x1800aef92  mov     edx, 8; dwFlags
0x1800aef97  mov     rcx, rax; hHeap
0x1800aef9a  call    cs:__imp_HeapAlloc
0x1800aefa0  mov     r15, rax
0x1800aefa3  test    rax, rax
0x1800aefa6  jnz     short loc_1800AEFE6
0x1800aefa8  mov     ebx, 0C0000017h
0x1800aefad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aefb4  lea     r15, WPP_GLOBAL_Control
0x1800aefbb  cmp     rcx, r15
0x1800aefbe  jz      loc_1800AF35E
0x1800aefc4  test    dword ptr [rcx+1Ch], 800h
0x1800aefcb  jz      loc_1800AF35E
0x1800aefd1  cmp     byte ptr [rcx+19h], 2
0x1800aefd5  jb      loc_1800AF35E
0x1800aefdb  lea     edx, [rax+1Dh]
0x1800aefde  mov     r9d, 0C0000017h
0x1800aefe4  jmp     short loc_1800AEF71
0x1800aefe6  inc     rdi
0x1800aefe9  cmp     [rsi+rdi*2], r13w
0x1800aefee  jnz     short loc_1800AEFE6
0x1800aeff0  mov     [rsp+50h+pdwFlags], r13; pdwFlags
0x1800aeff5  lea     rax, [rbp+cbInput]
0x1800aeff9  mov     [rsp+50h+pdwSkip], r13; pdwSkip
0x1800aeffe  mov     r9, r15; pbBinary
0x1800af001  mov     r8d, 2; dwFlags
0x1800af007  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x1800af00c  mov     edx, edi; cchString
0x1800af00e  mov     rcx, rsi; pszString
0x1800af011  call    cs:__imp_CryptStringToBinaryW
0x1800af017  test    eax, eax
0x1800af019  jnz     short loc_1800AF063
0x1800af01b  call    cs:__imp_GetLastError
0x1800af021  mov     ebx, eax
0x1800af023  test    eax, eax
0x1800af025  jz      loc_1800AF33C
0x1800af02b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af032  lea     rax, WPP_GLOBAL_Control
0x1800af039  cmp     rcx, rax
0x1800af03c  jz      loc_1800AF33C
0x1800af042  test    dword ptr [rcx+1Ch], 800h
0x1800af049  jz      loc_1800AF33C
0x1800af04f  cmp     byte ptr [rcx+19h], 2
0x1800af053  jb      loc_1800AF33C
0x1800af059  mov     edx, 1Eh
0x1800af05e  jmp     loc_1800AF329
0x1800af063  xor     r9d, r9d; dwFlags
0x1800af066  lea     rdx, pszAlgId; "MD5"
0x1800af06d  xor     r8d, r8d; pszImplementation
0x1800af070  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800af074  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800af07a  mov     ebx, eax
0x1800af07c  test    eax, eax
0x1800af07e  jz      short loc_1800AF0B8
0x1800af080  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af087  lea     rax, WPP_GLOBAL_Control
0x1800af08e  cmp     rcx, rax
0x1800af091  jz      loc_1800AF33C
0x1800af097  test    dword ptr [rcx+1Ch], 800h
0x1800af09e  jz      loc_1800AF33C
0x1800af0a4  cmp     byte ptr [rcx+19h], 2
0x1800af0a8  jb      loc_1800AF33C
0x1800af0ae  mov     edx, 1Fh
0x1800af0b3  jmp     loc_1800AF329
0x1800af0b8  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800af0bc  lea     rdx, [rbp+phHash]; phHash
0x1800af0c0  mov     dword ptr [rsp+50h+pdwFlags], r13d; dwFlags
0x1800af0c5  xor     r9d, r9d; cbHashObject
0x1800af0c8  mov     dword ptr [rsp+50h+pdwSkip], r13d; cbSecret
0x1800af0cd  xor     r8d, r8d; pbHashObject
0x1800af0d0  mov     [rsp+50h+pcbBinary], r13; pbSecret
0x1800af0d5  call    cs:__imp_BCryptCreateHash
0x1800af0db  mov     ebx, eax
0x1800af0dd  test    eax, eax
0x1800af0df  jz      short loc_1800AF119
0x1800af0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af0e8  lea     rax, WPP_GLOBAL_Control
0x1800af0ef  cmp     rcx, rax
0x1800af0f2  jz      loc_1800AF33C
0x1800af0f8  test    dword ptr [rcx+1Ch], 800h
0x1800af0ff  jz      loc_1800AF33C
0x1800af105  cmp     byte ptr [rcx+19h], 2
0x1800af109  jb      loc_1800AF33C
0x1800af10f  mov     edx, 20h ; ' '
0x1800af114  jmp     loc_1800AF329
0x1800af119  mov     r8d, [rbp+cbInput]; cbInput
0x1800af11d  xor     r9d, r9d; dwFlags
0x1800af120  mov     rcx, [rbp+phHash]; hHash
0x1800af124  mov     rdx, r15; pbInput
0x1800af127  call    cs:__imp_BCryptHashData
0x1800af12d  mov     ebx, eax
0x1800af12f  test    eax, eax
0x1800af131  jz      short loc_1800AF16B
0x1800af133  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af13a  lea     rax, WPP_GLOBAL_Control
0x1800af141  cmp     rcx, rax
0x1800af144  jz      loc_1800AF33C
0x1800af14a  test    dword ptr [rcx+1Ch], 800h
0x1800af151  jz      loc_1800AF33C
0x1800af157  cmp     byte ptr [rcx+19h], 2
0x1800af15b  jb      loc_1800AF33C
0x1800af161  mov     edx, 21h ; '!'
0x1800af166  jmp     loc_1800AF329
0x1800af16b  call    cs:__imp_GetProcessHeap
0x1800af171  mov     edi, 10h
0x1800af176  mov     rcx, rax; hHeap
0x1800af179  mov     r8d, edi; dwBytes
0x1800af17c  lea     edx, [rdi-8]; dwFlags
0x1800af17f  call    cs:__imp_HeapAlloc
0x1800af185  mov     r14, rax
0x1800af188  test    rax, rax
0x1800af18b  jnz     short loc_1800AF1CE
0x1800af18d  mov     ebx, 0C0000017h
0x1800af192  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af199  lea     rax, WPP_GLOBAL_Control
0x1800af1a0  cmp     rcx, rax
0x1800af1a3  jz      loc_1800AF33C
0x1800af1a9  test    dword ptr [rcx+1Ch], 800h
0x1800af1b0  jz      loc_1800AF33C
0x1800af1b6  cmp     byte ptr [rcx+19h], 2
0x1800af1ba  jb      loc_1800AF33C
0x1800af1c0  lea     edx, [rdi+12h]
0x1800af1c3  mov     r9d, 0C0000017h
0x1800af1c9  jmp     loc_1800AF32C
0x1800af1ce  mov     rcx, [rbp+phHash]; hHash
0x1800af1d2  xor     r9d, r9d; dwFlags
0x1800af1d5  mov     r8d, edi; cbOutput
0x1800af1d8  mov     rdx, r14; pbOutput
0x1800af1db  call    cs:__imp_BCryptFinishHash
0x1800af1e1  mov     ebx, eax
0x1800af1e3  test    eax, eax
0x1800af1e5  jz      short loc_1800AF21F
0x1800af1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af1ee  lea     rax, WPP_GLOBAL_Control
0x1800af1f5  cmp     rcx, rax
0x1800af1f8  jz      loc_1800AF33C
0x1800af1fe  test    dword ptr [rcx+1Ch], 800h
0x1800af205  jz      loc_1800AF33C
0x1800af20b  cmp     byte ptr [rcx+19h], 2
0x1800af20f  jb      loc_1800AF33C
0x1800af215  mov     edx, 23h ; '#'
0x1800af21a  jmp     loc_1800AF329
0x1800af21f  xor     r9d, r9d; pszString
0x1800af222  lea     rax, [rbp+pcchString]
0x1800af226  mov     edx, edi; cbBinary
0x1800af228  mov     [rsp+50h+pcbBinary], rax; pcchString
0x1800af22d  mov     rcx, r14; pbBinary
0x1800af230  lea     r8d, [r9+2]; dwFlags
0x1800af234  call    cs:__imp_CryptBinaryToStringW
0x1800af23a  test    eax, eax
0x1800af23c  jnz     short loc_1800AF286
0x1800af23e  call    cs:__imp_GetLastError
0x1800af244  mov     ebx, eax
0x1800af246  test    eax, eax
0x1800af248  jz      loc_1800AF33C
0x1800af24e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af255  lea     rax, WPP_GLOBAL_Control
0x1800af25c  cmp     rcx, rax
0x1800af25f  jz      loc_1800AF33C
0x1800af265  test    dword ptr [rcx+1Ch], 800h
0x1800af26c  jz      loc_1800AF33C
0x1800af272  cmp     byte ptr [rcx+19h], 2
0x1800af276  jb      loc_1800AF33C
0x1800af27c  mov     edx, 24h ; '$'
0x1800af281  jmp     loc_1800AF329
0x1800af286  mov     edx, [rbp+pcchString]
0x1800af289  mov     ecx, 40h ; '@'; uFlags
0x1800af28e  add     rdx, rdx; dwBytes
0x1800af291  call    cs:__imp_GlobalAlloc
0x1800af297  mov     [r12], rax
0x1800af29b  test    rax, rax
0x1800af29e  jnz     short loc_1800AF2D5
0x1800af2a0  mov     ebx, 0C0000017h
0x1800af2a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af2ac  lea     rax, WPP_GLOBAL_Control
0x1800af2b3  cmp     rcx, rax
0x1800af2b6  jz      loc_1800AF33C
0x1800af2bc  test    dword ptr [rcx+1Ch], 800h
0x1800af2c3  jz      short loc_1800AF33C
0x1800af2c5  cmp     byte ptr [rcx+19h], 2
0x1800af2c9  jb      short loc_1800AF33C
0x1800af2cb  mov     edx, 25h ; '%'
0x1800af2d0  jmp     loc_1800AF1C3
0x1800af2d5  lea     rcx, [rbp+pcchString]
0x1800af2d9  mov     r9, rax; pszString
0x1800af2dc  mov     [rsp+50h+pcbBinary], rcx; pcchString
0x1800af2e1  mov     r8d, 2; dwFlags
0x1800af2e7  mov     rcx, r14; pbBinary
0x1800af2ea  mov     edx, edi; cbBinary
0x1800af2ec  call    cs:__imp_CryptBinaryToStringW
0x1800af2f2  test    eax, eax
0x1800af2f4  jnz     short loc_1800AF33C
0x1800af2f6  call    cs:__imp_GetLastError
0x1800af2fc  mov     ebx, eax
0x1800af2fe  test    eax, eax
0x1800af300  jz      short loc_1800AF33C
0x1800af302  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af309  lea     rax, WPP_GLOBAL_Control
0x1800af310  cmp     rcx, rax
0x1800af313  jz      short loc_1800AF33C
0x1800af315  test    dword ptr [rcx+1Ch], 800h
0x1800af31c  jz      short loc_1800AF33C
0x1800af31e  cmp     byte ptr [rcx+19h], 2
0x1800af322  jb      short loc_1800AF33C
0x1800af324  mov     edx, 26h ; '&'
0x1800af329  mov     r9d, ebx
0x1800af32c  mov     rcx, [rcx+10h]
0x1800af330  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af337  call    WPP_SF_d
0x1800af33c  call    cs:__imp_GetProcessHeap
0x1800af342  mov     r8, r15; lpMem
0x1800af345  xor     edx, edx; dwFlags
0x1800af347  mov     rcx, rax; hHeap
0x1800af34a  call    cs:__imp_HeapFree
0x1800af350  lea     r15, WPP_GLOBAL_Control
0x1800af357  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af35e  mov     rax, [rbp+phAlgorithm]
0x1800af362  test    rax, rax
0x1800af365  jz      short loc_1800AF3B0
0x1800af367  xor     edx, edx; dwFlags
0x1800af369  mov     rcx, rax; hAlgorithm
0x1800af36c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800af372  test    eax, eax
0x1800af374  jz      short loc_1800AF3A9
0x1800af376  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af37d  cmp     rcx, r15
0x1800af380  jz      short loc_1800AF3B0
0x1800af382  test    dword ptr [rcx+1Ch], 800h
0x1800af389  jz      short loc_1800AF3B0
0x1800af38b  cmp     byte ptr [rcx+19h], 2
0x1800af38f  jb      short loc_1800AF3B0
0x1800af391  mov     rcx, [rcx+10h]
0x1800af395  lea     r8, WPP_a755c749419c30f1eb8370c53189fcc7_Traceguids
0x1800af39c  mov     edx, 27h ; '''
0x1800af3a1  mov     r9d, eax
0x1800af3a4  call    WPP_SF_d
0x1800af3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af3b0  mov     rax, [rbp+phHash]
0x1800af3b4  test    rax, rax
0x1800af3b7  jz      short loc_1800AF400
0x1800af3b9  mov     rcx, rax; hHash
0x1800af3bc  call    cs:__imp_BCryptDestroyHash
0x1800af3c2  test    eax, eax
0x1800af3c4  jz      short loc_1800AF3F9
0x1800af3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af3cd  cmp     rcx, r15
  ... truncated ...
```
