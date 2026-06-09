# CCipher::Initialize(std::vector<uchar,std::allocator<uchar>> const &,uint,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800c5894`
- end: `0x1800c5b74`
- name: `?Initialize@CCipher@@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@IAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@1@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800854d8`

## callees

- `0x1800087d4`
- `0x18000933c`
- `0x1800c5894`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5a17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5b25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5a17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5b25`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c5a6c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c5a82`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c5a6c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c5a82`
- `bcrypt!BCryptGetProperty` at `0x1800c5ab3`
- `bcrypt!BCryptGetProperty` at `0x1800c5ab3`
- `bcrypt!BCryptSetProperty` at `0x1800c59e1`
- `bcrypt!BCryptSetProperty` at `0x1800c59e1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c59a9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c59a9`
- `bcrypt!BCryptDestroyKey` at `0x1800c5a0f`
- `bcrypt!BCryptDestroyKey` at `0x1800c5b1d`
- `bcrypt!BCryptDestroyKey` at `0x1800c5b48`
- `bcrypt!BCryptDestroyKey` at `0x1800c5a0f`
- `bcrypt!BCryptDestroyKey` at `0x1800c5b1d`
- `bcrypt!BCryptDestroyKey` at `0x1800c5b48`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c594f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c5a39`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c594f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c5a39`

## pseudocode

```c
__int64 __fastcall CCipher::Initialize(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  UCHAR *v5; // r10
  __int64 v7; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  const WCHAR *v11; // rdx
  unsigned int v12; // r12d
  UCHAR *v13; // rbx
  NTSTATUS Property; // eax
  __int64 v15; // rdx
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // ecx
  __int64 v20; // rdx
  BCRYPT_KEY_HANDLE v21; // rsi
  BCRYPT_KEY_HANDLE v22; // r14
  DWORD LastError; // ebx
  int pbSecret; // [rsp+20h] [rbp-50h]
  int pbSecreta; // [rsp+20h] [rbp-50h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-30h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v5 = *(UCHAR **)a2;
  v7 = *(_QWORD *)(a2 + 8);
  if ( *(_QWORD *)a2 == v7 )
  {
    v9 = 9;
LABEL_3:
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Cipher.cpp",
      (const char *)0x80070057LL,
      pbSecret);
    return v10;
  }
  if ( a3 > 0x100000 )
  {
    v9 = 10;
    goto LABEL_3;
  }
  v11 = L"AES";
  phKey = 0;
  v12 = 0x10000;
  v13 = (UCHAR *)L"ChainingModeCBC";
  if ( a3 )
    v12 = a3;
  if ( *(_QWORD *)(a4 + 16) )
  {
    v11 = (const WCHAR *)a4;
    if ( *(_QWORD *)(a4 + 24) > 7u )
      v11 = *(const WCHAR **)a4;
    if ( !*(_QWORD *)(a5 + 16) )
    {
LABEL_18:
      phAlgorithm = 0;
      v16 = BCryptOpenAlgorithmProvider(&phAlgorithm, v11, 0, 0);
      if ( v16 >= 0 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&v13[2 * v18] );
        v16 = BCryptSetProperty(phAlgorithm, L"ChainingMode", v13, 2 * v18, 0);
        if ( v16 >= 0 )
        {
          v16 = BCryptGenerateSymmetricKey(
                  phAlgorithm,
                  &phKey,
                  0,
                  0,
                  *(PUCHAR *)a2,
                  *(_DWORD *)(a2 + 8) - *(_QWORD *)a2,
                  0);
          if ( v16 >= 0 )
          {
            if ( phAlgorithm )
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
            goto LABEL_30;
          }
          v17 = 55;
        }
        else
        {
          v17 = 52;
        }
      }
      else
      {
        v17 = 45;
      }
      v10 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v17,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Cipher.cpp",
              (const char *)(unsigned int)v16,
              pbSecret);
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      goto LABEL_42;
    }
LABEL_16:
    v13 = (UCHAR *)a5;
    if ( *(_QWORD *)(a5 + 24) > 7u )
      v13 = *(UCHAR **)a5;
    goto LABEL_18;
  }
  if ( *(_QWORD *)(a5 + 16) )
    goto LABEL_16;
  Property = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x1A1, &phKey, 0, 0, v5, v7 - (_DWORD)v5, 0);
  if ( Property < 0 )
  {
    v15 = 28;
LABEL_12:
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v15,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Cipher.cpp",
            (const char *)(unsigned int)Property,
            pbSecreta);
    goto LABEL_42;
  }
LABEL_30:
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  Property = BCryptGetProperty(phKey, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v15 = 65;
    goto LABEL_12;
  }
  v19 = *(_DWORD *)pbOutput;
  if ( *(_DWORD *)pbOutput )
  {
    if ( !(v12 % *(_DWORD *)pbOutput) )
    {
      if ( (BCRYPT_KEY_HANDLE *)a1 != &phKey )
      {
        v21 = *(BCRYPT_KEY_HANDLE *)a1;
        v22 = phKey;
        if ( *(_QWORD *)a1 )
        {
          LastError = GetLastError();
          BCryptDestroyKey(v21);
          SetLastError(LastError);
          v19 = *(_DWORD *)pbOutput;
        }
        *(_QWORD *)a1 = v22;
        phKey = 0;
      }
      *(_DWORD *)(a1 + 8) = v19;
      v10 = 0;
      *(_DWORD *)(a1 + 12) = v12;
      goto LABEL_42;
    }
    v20 = 68;
  }
  else
  {
    v20 = 67;
  }
  v10 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\Cipher.cpp",
    (const char *)0x80070057LL,
    pbSecreta);
LABEL_42:
  if ( phKey )
    BCryptDestroyKey(phKey);
  return v10;
}

```

## disassembly

```asm
0x1800c5894  mov     [rsp-38h+arg_10], rbx
0x1800c5899  push    rbp
0x1800c589a  push    rsi
0x1800c589b  push    rdi
0x1800c589c  push    r12
0x1800c589e  push    r13
0x1800c58a0  push    r14
0x1800c58a2  push    r15
0x1800c58a4  mov     rbp, rsp
0x1800c58a7  sub     rsp, 70h
0x1800c58ab  mov     rax, cs:__security_cookie
0x1800c58b2  xor     rax, rsp
0x1800c58b5  mov     [rbp+var_10], rax
0x1800c58b9  mov     r10, [rdx]
0x1800c58bc  mov     rdi, rcx
0x1800c58bf  mov     rcx, [rdx+8]
0x1800c58c3  mov     rsi, rdx
0x1800c58c6  mov     rax, [rbp+arg_20]
0x1800c58ca  cmp     r10, rcx
0x1800c58cd  jnz     short loc_1800C58F1
0x1800c58cf  mov     edx, 9; void *
0x1800c58d4  mov     rcx, [rbp+38h]; this
0x1800c58d8  lea     r8, aCW1SSrcDeliver_11; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c58df  mov     ebx, 80070057h
0x1800c58e4  mov     r9d, ebx; char *
0x1800c58e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c58ec  jmp     loc_1800C5B4E
0x1800c58f1  cmp     r8d, 100000h
0x1800c58f8  jbe     short loc_1800C5901
0x1800c58fa  mov     edx, 0Ah
0x1800c58ff  jmp     short loc_1800C58D4
0x1800c5901  xor     r13d, r13d
0x1800c5904  lea     rdx, aAes; "AES"
0x1800c590b  test    r8d, r8d
0x1800c590e  mov     [rbp+phKey], r13
0x1800c5912  mov     r12d, 10000h
0x1800c5918  lea     rbx, pbInput; "ChainingModeCBC"
0x1800c591f  cmovnz  r12d, r8d
0x1800c5923  cmp     [r9+10h], r13
0x1800c5927  jnz     short loc_1800C597B
0x1800c5929  cmp     [rax+10h], r13
0x1800c592d  jnz     short loc_1800C598E
0x1800c592f  sub     ecx, r10d
0x1800c5932  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x1800c5937  mov     [rsp+70h+cbSecret], ecx; cbSecret
0x1800c593b  lea     rdx, [rbp+phKey]; phKey
0x1800c593f  mov     ecx, 1A1h; hAlgorithm
0x1800c5944  mov     [rsp+70h+pbSecret], r10; int
0x1800c5949  xor     r9d, r9d; cbKeyObject
0x1800c594c  xor     r8d, r8d; pbKeyObject
0x1800c594f  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800c5955  test    eax, eax
0x1800c5957  jns     loc_1800C5A88
0x1800c595d  lea     edx, [r13+1Ch]; void *
0x1800c5961  mov     rcx, [rbp+38h]; this
0x1800c5965  lea     r8, aCW1SSrcDeliver_11; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c596c  mov     r9d, eax; char *
0x1800c596f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800c5974  mov     ebx, eax
0x1800c5976  jmp     loc_1800C5B3F
0x1800c597b  cmp     qword ptr [r9+18h], 7
0x1800c5980  mov     rdx, r9
0x1800c5983  jbe     short loc_1800C5988
0x1800c5985  mov     rdx, [r9]; pszAlgId
0x1800c5988  cmp     [rax+10h], r13
0x1800c598c  jz      short loc_1800C599B
0x1800c598e  cmp     qword ptr [rax+18h], 7
0x1800c5993  mov     rbx, rax
0x1800c5996  jbe     short loc_1800C599B
0x1800c5998  mov     rbx, [rax]
0x1800c599b  xor     r9d, r9d; dwFlags
0x1800c599e  mov     [rbp+phAlgorithm], r13
0x1800c59a2  xor     r8d, r8d; pszImplementation
0x1800c59a5  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800c59a9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c59af  test    eax, eax
0x1800c59b1  jns     short loc_1800C59BD
0x1800c59b3  mov     edx, 2Dh ; '-'
0x1800c59b8  jmp     loc_1800C5A48
0x1800c59bd  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800c59c1  inc     r9
0x1800c59c4  cmp     [rbx+r9*2], r13w
0x1800c59c9  jnz     short loc_1800C59C1
0x1800c59cb  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800c59cf  lea     rdx, aChainingmode_0; "ChainingMode"
0x1800c59d6  add     r9d, r9d; cbInput
0x1800c59d9  mov     dword ptr [rsp+70h+pbSecret], r13d; dwFlags
0x1800c59de  mov     r8, rbx; pbInput
0x1800c59e1  call    cs:__imp_BCryptSetProperty
0x1800c59e7  test    eax, eax
0x1800c59e9  jns     short loc_1800C59F2
0x1800c59eb  mov     edx, 34h ; '4'
0x1800c59f0  jmp     short loc_1800C5A48
0x1800c59f2  mov     r15, [rsi]
0x1800c59f5  mov     esi, [rsi+8]
0x1800c59f8  mov     r14, [rbp+phKey]
0x1800c59fc  sub     esi, r15d
0x1800c59ff  test    r14, r14
0x1800c5a02  jz      short loc_1800C5A1D
0x1800c5a04  call    cs:__imp_GetLastError
0x1800c5a0a  mov     rcx, r14; hKey
0x1800c5a0d  mov     ebx, eax
0x1800c5a0f  call    cs:__imp_BCryptDestroyKey
0x1800c5a15  mov     ecx, ebx; dwErrCode
0x1800c5a17  call    cs:__imp_SetLastError
0x1800c5a1d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c5a21  lea     rdx, [rbp+phKey]; phKey
0x1800c5a25  mov     [rsp+70h+dwFlags], r13d; dwFlags
0x1800c5a2a  xor     r9d, r9d; cbKeyObject
0x1800c5a2d  mov     [rsp+70h+cbSecret], esi; cbSecret
0x1800c5a31  xor     r8d, r8d; pbKeyObject
0x1800c5a34  mov     [rsp+70h+pbSecret], r15; int
0x1800c5a39  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800c5a3f  test    eax, eax
0x1800c5a41  jns     short loc_1800C5A77
0x1800c5a43  mov     edx, 37h ; '7'; void *
0x1800c5a48  mov     rcx, [rbp+38h]; this
0x1800c5a4c  lea     r8, aCW1SSrcDeliver_11; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5a53  mov     r9d, eax; char *
0x1800c5a56  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800c5a5b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c5a5f  mov     ebx, eax
0x1800c5a61  test    rcx, rcx
0x1800c5a64  jz      loc_1800C5B3F
0x1800c5a6a  xor     edx, edx; dwFlags
0x1800c5a6c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c5a72  jmp     loc_1800C5B3F
0x1800c5a77  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c5a7b  test    rcx, rcx
0x1800c5a7e  jz      short loc_1800C5A88
0x1800c5a80  xor     edx, edx; dwFlags
0x1800c5a82  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c5a88  mov     rcx, [rbp+phKey]; hObject
0x1800c5a8c  lea     rax, [rbp+pcbResult]
0x1800c5a90  mov     [rsp+70h+cbSecret], r13d; dwFlags
0x1800c5a95  lea     r8, [rbp+pbOutput]; pbOutput
0x1800c5a99  mov     r9d, 4; cbOutput
0x1800c5a9f  mov     [rsp+70h+pbSecret], rax; int
0x1800c5aa4  lea     rdx, aBlocklength; "BlockLength"
0x1800c5aab  mov     [rbp+pcbResult], r13d
0x1800c5aaf  mov     dword ptr [rbp+pbOutput], r13d
0x1800c5ab3  call    cs:__imp_BCryptGetProperty
0x1800c5ab9  test    eax, eax
0x1800c5abb  jns     short loc_1800C5AC7
0x1800c5abd  mov     edx, 41h ; 'A'
0x1800c5ac2  jmp     loc_1800C5961
0x1800c5ac7  mov     ecx, dword ptr [rbp+pbOutput]
0x1800c5aca  test    ecx, ecx
0x1800c5acc  jnz     short loc_1800C5AD3
0x1800c5ace  lea     edx, [rcx+43h]
0x1800c5ad1  jmp     short loc_1800C5AE3
0x1800c5ad3  xor     edx, edx
0x1800c5ad5  mov     eax, r12d
0x1800c5ad8  div     ecx
0x1800c5ada  test    edx, edx
0x1800c5adc  jz      short loc_1800C5AFD
0x1800c5ade  mov     edx, 44h ; 'D'; void *
0x1800c5ae3  mov     rcx, [rbp+38h]; this
0x1800c5ae7  lea     r8, aCW1SSrcDeliver_11; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c5aee  mov     ebx, 80070057h
0x1800c5af3  mov     r9d, ebx; char *
0x1800c5af6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5afb  jmp     short loc_1800C5B3F
0x1800c5afd  lea     rax, [rbp+phKey]
0x1800c5b01  cmp     rdi, rax
0x1800c5b04  jz      short loc_1800C5B35
0x1800c5b06  mov     rsi, [rdi]
0x1800c5b09  mov     r14, [rbp+phKey]
0x1800c5b0d  test    rsi, rsi
0x1800c5b10  jz      short loc_1800C5B2E
0x1800c5b12  call    cs:__imp_GetLastError
0x1800c5b18  mov     rcx, rsi; hKey
0x1800c5b1b  mov     ebx, eax
0x1800c5b1d  call    cs:__imp_BCryptDestroyKey
0x1800c5b23  mov     ecx, ebx; dwErrCode
0x1800c5b25  call    cs:__imp_SetLastError
0x1800c5b2b  mov     ecx, dword ptr [rbp+pbOutput]
0x1800c5b2e  mov     [rdi], r14
0x1800c5b31  mov     [rbp+phKey], r13
0x1800c5b35  mov     [rdi+8], ecx
0x1800c5b38  mov     ebx, r13d
0x1800c5b3b  mov     [rdi+0Ch], r12d
0x1800c5b3f  mov     rcx, [rbp+phKey]; hKey
0x1800c5b43  test    rcx, rcx
0x1800c5b46  jz      short loc_1800C5B4E
0x1800c5b48  call    cs:__imp_BCryptDestroyKey
0x1800c5b4e  mov     eax, ebx
0x1800c5b50  mov     rcx, [rbp+var_10]
0x1800c5b54  xor     rcx, rsp; StackCookie
0x1800c5b57  call    __security_check_cookie
0x1800c5b5c  mov     rbx, [rsp+70h+arg_10]
0x1800c5b64  add     rsp, 70h
0x1800c5b68  pop     r15
0x1800c5b6a  pop     r14
0x1800c5b6c  pop     r13
0x1800c5b6e  pop     r12
0x1800c5b70  pop     rdi
0x1800c5b71  pop     rsi
0x1800c5b72  pop     rbp
0x1800c5b73  retn
```
