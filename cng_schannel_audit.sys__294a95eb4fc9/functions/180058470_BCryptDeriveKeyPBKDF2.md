# BCryptDeriveKeyPBKDF2

- ea: `0x180058470`
- end: `0x18005873c`
- name: `BCryptDeriveKeyPBKDF2`
- size: `716`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hPrf, PUCHAR pbPassword, ULONG cbPassword, PUCHAR pbSalt, ULONG cbSalt, ULONGLONG cIterations, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001ab0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180058470`
- `0x18009da40`

## string_xrefs

- `0x18005864a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005867a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058714`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKeyPBKDF2(
        BCRYPT_ALG_HANDLE hPrf,
        PUCHAR pbPassword,
        ULONG cbPassword,
        PUCHAR pbSalt,
        ULONG cbSalt,
        ULONGLONG cIterations,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG dwFlags)
{
  NTSTATUS Property; // eax
  NTSTATUS v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  ULONG v14; // edi
  __int64 v15; // rdx
  _BYTE *v16; // rsi
  __int64 v17; // rdx
  void *v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rax
  char *v21; // rdi
  ULONG i; // ecx
  int PBKDF2Block; // eax
  _BYTE *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  _BYTE *v27; // rcx
  UCHAR v29[4]; // [rsp+60h] [rbp-20h] BYREF
  ULONG pcbResult; // [rsp+64h] [rbp-1Ch] BYREF
  UCHAR v31[4]; // [rsp+68h] [rbp-18h] BYREF
  UCHAR pbOutput[4]; // [rsp+6Ch] [rbp-14h] BYREF
  ULONG v33; // [rsp+70h] [rbp-10h]
  ULONG v34; // [rsp+74h] [rbp-Ch]

  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  *(_DWORD *)v31 = 0;
  *(_DWORD *)v29 = 0;
  if ( !cIterations || dwFlags || !pbPassword && cbPassword || !pbSalt && cbSalt || !pbDerivedKey || !cbDerivedKey )
  {
    v11 = -1073741811;
    v12 = 7530;
    v13 = 3221225485LL;
    goto LABEL_37;
  }
  if ( BCryptGetProperty(hPrf, L"IsKeyedHash", pbOutput, 4u, &pcbResult, 0) < 0 || !*(_DWORD *)pbOutput )
  {
    v11 = -1073741816;
    v12 = 7543;
    v13 = 3221225480LL;
    goto LABEL_37;
  }
  Property = BCryptGetProperty(hPrf, L"HashDigestLength", v29, 4u, &pcbResult, 0);
  v11 = Property;
  if ( Property < 0 )
  {
    v12 = 7555;
LABEL_13:
    v13 = (unsigned int)Property;
LABEL_37:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
    return v11;
  }
  v14 = (cbDerivedKey + *(_DWORD *)v29 - 1) / *(_DWORD *)v29;
  v33 = v14;
  Property = BCryptGetProperty(hPrf, L"ObjectLength", v31, 4u, &pcbResult, 0);
  v11 = Property;
  if ( Property < 0 )
  {
    v12 = 7572;
    goto LABEL_13;
  }
  v16 = (_BYTE *)MSCryptAlloc(*(unsigned int *)v29, v15);
  v18 = (void *)MSCryptAlloc(*(unsigned int *)v31, v17);
  v20 = MSCryptAlloc(v14 * *(_DWORD *)v29, v19);
  v21 = (char *)v20;
  if ( v16 && v18 && v20 )
  {
    for ( i = 0; i < v33; i = v34 )
    {
      v34 = i + 1;
      PBKDF2Block = GetPBKDF2Block(
                      hPrf,
                      pbPassword,
                      cbPassword,
                      pbSalt,
                      cbSalt,
                      cIterations,
                      i + 1,
                      v18,
                      *(_DWORD *)v31,
                      v16,
                      &v21[*(_DWORD *)v29 * i],
                      *(_DWORD *)v29);
      v11 = PBKDF2Block;
      if ( PBKDF2Block < 0 )
      {
        DebugTraceError(
          (unsigned int)PBKDF2Block,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          7609);
        goto LABEL_26;
      }
    }
    memmove(pbDerivedKey, v21, cbDerivedKey);
    v11 = 0;
    goto LABEL_26;
  }
  DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 7589);
  v11 = -1073741801;
  if ( v21 )
  {
LABEL_26:
    v24 = v21;
    v25 = v33 * *(_DWORD *)v29;
    if ( v33 * *(_DWORD *)v29 )
    {
      do
      {
        *v24++ = 0;
        --v25;
      }
      while ( v25 );
    }
    MSCryptFree(v21);
  }
  if ( v18 )
    MSCryptFree(v18);
  if ( v16 )
  {
    v26 = *(unsigned int *)v29;
    v27 = v16;
    if ( *(_DWORD *)v29 )
    {
      do
      {
        *v27++ = 0;
        --v26;
      }
      while ( v26 );
    }
    MSCryptFree(v16);
  }
  return v11;
}

```

## disassembly

```asm
0x180058470  mov     [rsp-38h+arg_18], r9
0x180058475  mov     [rsp-38h+arg_10], r8d
0x18005847a  mov     [rsp-38h+arg_8], rdx
0x18005847f  push    rbp
0x180058480  push    rbx
0x180058481  push    rsi
0x180058482  push    rdi
0x180058483  push    r12
0x180058485  push    r14
0x180058487  push    r15
0x180058489  mov     rbp, rsp
0x18005848c  sub     rsp, 80h
0x180058493  xor     esi, esi
0x180058495  mov     eax, r8d
0x180058498  mov     r12, rcx
0x18005849b  mov     dword ptr [rbp+pbOutput], esi
0x18005849e  mov     [rbp+var_1C], esi
0x1800584a1  mov     dword ptr [rbp+var_18], esi
0x1800584a4  mov     dword ptr [rbp+var_20], esi
0x1800584a7  cmp     [rbp+cIterations], rsi
0x1800584ab  jz      loc_180058704
0x1800584b1  cmp     [rbp+dwFlags], esi
0x1800584b7  jnz     loc_180058704
0x1800584bd  test    rdx, rdx
0x1800584c0  jnz     short loc_1800584CA
0x1800584c2  test    eax, eax
0x1800584c4  jnz     loc_180058704
0x1800584ca  test    r9, r9
0x1800584cd  jnz     short loc_1800584D8
0x1800584cf  cmp     [rbp+cbSalt], esi
0x1800584d2  jnz     loc_180058704
0x1800584d8  cmp     [rbp+pbDerivedKey], rsi
0x1800584dc  jz      loc_180058704
0x1800584e2  mov     r15d, [rbp+cbDerivedKey]
0x1800584e6  test    r15d, r15d
0x1800584e9  jz      loc_180058704
0x1800584ef  lea     rax, [rbp+var_1C]
0x1800584f3  mov     [rsp+80h+var_58], esi; dwFlags
0x1800584f7  mov     r14d, 4
0x1800584fd  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180058502  mov     r9d, r14d; cbOutput
0x180058505  lea     r8, [rbp+pbOutput]; pbOutput
0x180058509  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x180058510  call    BCryptGetProperty
0x180058515  test    eax, eax
0x180058517  js      loc_1800586F2
0x18005851d  cmp     dword ptr [rbp+pbOutput], esi
0x180058520  jz      loc_1800586F2
0x180058526  lea     rax, [rbp+var_1C]
0x18005852a  mov     [rsp+80h+var_58], esi; dwFlags
0x18005852e  mov     r9d, r14d; cbOutput
0x180058531  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180058536  lea     r8, [rbp+var_20]; pbOutput
0x18005853a  mov     rcx, r12; hObject
0x18005853d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180058544  call    BCryptGetProperty
0x180058549  mov     ebx, eax
0x18005854b  test    eax, eax
0x18005854d  jns     short loc_18005855C
0x18005854f  mov     r9d, 1D83h
0x180058555  mov     ecx, eax
0x180058557  jmp     loc_180058714
0x18005855c  mov     ecx, dword ptr [rbp+var_20]
0x18005855f  lea     r8, [rbp+var_18]; pbOutput
0x180058563  xor     edx, edx
0x180058565  mov     [rsp+80h+var_58], esi; dwFlags
0x180058569  mov     r9d, r14d; cbOutput
0x18005856c  lea     eax, [rcx-1]
0x18005856f  add     eax, r15d
0x180058572  div     ecx
0x180058574  lea     rdx, aObjectlength; "ObjectLength"
0x18005857b  mov     rcx, r12; hObject
0x18005857e  mov     edi, eax
0x180058580  mov     [rbp+var_10], eax
0x180058583  lea     rax, [rbp+var_1C]
0x180058587  mov     [rsp+80h+pcbResult], rax; pcbResult
0x18005858c  call    BCryptGetProperty
0x180058591  mov     ebx, eax
0x180058593  test    eax, eax
0x180058595  jns     short loc_18005859F
0x180058597  mov     r9d, 1D94h
0x18005859d  jmp     short loc_180058555
0x18005859f  mov     ecx, dword ptr [rbp+var_20]
0x1800585a2  call    MSCryptAlloc
0x1800585a7  mov     ecx, dword ptr [rbp+var_18]
0x1800585aa  mov     rsi, rax
0x1800585ad  call    MSCryptAlloc
0x1800585b2  mov     ecx, dword ptr [rbp+var_20]
0x1800585b5  mov     r14, rax
0x1800585b8  imul    ecx, edi
0x1800585bb  call    MSCryptAlloc
0x1800585c0  mov     rdi, rax
0x1800585c3  test    rsi, rsi
0x1800585c6  jz      loc_180058674
0x1800585cc  test    r14, r14
0x1800585cf  jz      loc_180058674
0x1800585d5  test    rax, rax
0x1800585d8  jz      loc_180058674
0x1800585de  xor     ecx, ecx
0x1800585e0  cmp     ecx, [rbp+var_10]
0x1800585e3  jnb     short loc_180058661
0x1800585e5  mov     edx, dword ptr [rbp+var_20]
0x1800585e8  lea     r8d, [rcx+1]
0x1800585ec  mov     eax, dword ptr [rbp+var_18]
0x1800585ef  mov     r9, [rbp+arg_18]
0x1800585f3  mov     [rsp+80h+var_28], edx
0x1800585f7  imul    ecx, edx
0x1800585fa  mov     rdx, [rbp+arg_8]
0x1800585fe  mov     [rbp+var_C], r8d
0x180058602  add     rcx, rdi
0x180058605  mov     [rsp+80h+var_30], rcx
0x18005860a  mov     rcx, r12
0x18005860d  mov     [rsp+80h+var_38], rsi
0x180058612  mov     [rsp+80h+var_40], eax
0x180058616  mov     rax, [rbp+cIterations]
0x18005861a  mov     [rsp+80h+var_48], r14
0x18005861f  mov     [rsp+80h+var_50], r8d
0x180058624  mov     r8d, [rbp+arg_10]
0x180058628  mov     qword ptr [rsp+80h+var_58], rax
0x18005862d  mov     eax, [rbp+cbSalt]
0x180058630  mov     dword ptr [rsp+80h+pcbResult], eax
0x180058634  call    GetPBKDF2Block
0x180058639  mov     ebx, eax
0x18005863b  test    eax, eax
0x18005863d  js      short loc_180058644
0x18005863f  mov     ecx, [rbp+var_C]
0x180058642  jmp     short loc_1800585E0
0x180058644  mov     r9d, 1DB9h
0x18005864a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058651  lea     rdx, aStatus; "Status"
0x180058658  mov     ecx, eax
0x18005865a  call    DebugTraceError
0x18005865f  jmp     short loc_18005869C
0x180058661  mov     rcx, [rbp+pbDerivedKey]; void *
0x180058665  mov     r8, r15; Size
0x180058668  mov     rdx, rdi; Src
0x18005866b  call    memmove
0x180058670  xor     ebx, ebx
0x180058672  jmp     short loc_18005869C
0x180058674  mov     r9d, 1DA5h
0x18005867a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058681  lea     rdx, aStatus; "Status"
0x180058688  mov     ecx, 0C0000017h
0x18005868d  call    DebugTraceError
0x180058692  mov     ebx, 0C0000017h
0x180058697  test    rdi, rdi
0x18005869a  jz      short loc_1800586BF
0x18005869c  mov     ecx, dword ptr [rbp+var_20]
0x18005869f  mov     rax, rdi
0x1800586a2  imul    ecx, [rbp+var_10]
0x1800586a6  test    rcx, rcx
0x1800586a9  jz      short loc_1800586B7
0x1800586ab  mov     byte ptr [rax], 0
0x1800586ae  inc     rax
0x1800586b1  sub     rcx, 1
0x1800586b5  jnz     short loc_1800586AB
0x1800586b7  mov     rcx, rdi; P
0x1800586ba  call    MSCryptFree
0x1800586bf  test    r14, r14
0x1800586c2  jz      short loc_1800586CC
0x1800586c4  mov     rcx, r14; P
0x1800586c7  call    MSCryptFree
0x1800586cc  test    rsi, rsi
0x1800586cf  jz      short loc_180058727
0x1800586d1  mov     eax, dword ptr [rbp+var_20]
0x1800586d4  mov     rcx, rsi
0x1800586d7  test    rax, rax
0x1800586da  jz      short loc_1800586E8
0x1800586dc  mov     byte ptr [rcx], 0
0x1800586df  inc     rcx
0x1800586e2  sub     rax, 1
0x1800586e6  jnz     short loc_1800586DC
0x1800586e8  mov     rcx, rsi; P
0x1800586eb  call    MSCryptFree
0x1800586f0  jmp     short loc_180058727
0x1800586f2  mov     ebx, 0C0000008h
0x1800586f7  mov     r9d, 1D77h
0x1800586fd  mov     ecx, 0C0000008h
0x180058702  jmp     short loc_180058714
0x180058704  mov     ebx, 0C000000Dh
0x180058709  mov     r9d, 1D6Ah
0x18005870f  mov     ecx, 0C000000Dh
0x180058714  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005871b  lea     rdx, aStatus; "Status"
0x180058722  call    DebugTraceError
0x180058727  mov     eax, ebx
0x180058729  add     rsp, 80h
0x180058730  pop     r15
0x180058732  pop     r14
0x180058734  pop     r12
0x180058736  pop     rdi
0x180058737  pop     rsi
0x180058738  pop     rbx
0x180058739  pop     rbp
0x18005873a  retn
```
