# BCryptDeriveKeyPBKDF2

- ea: `0x180062640`
- end: `0x18006290c`
- name: `BCryptDeriveKeyPBKDF2`
- size: `716`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hPrf, PUCHAR pbPassword, ULONG cbPassword, PUCHAR pbSalt, ULONG cbSalt, ULONGLONG cIterations, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000bbd0`
- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180062640`
- `0x1800a45c0`

## string_xrefs

- `0x18006281a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18006284a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800628e4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180062640  mov     [rsp-38h+arg_18], r9
0x180062645  mov     [rsp-38h+arg_10], r8d
0x18006264a  mov     [rsp-38h+arg_8], rdx
0x18006264f  push    rbp
0x180062650  push    rbx
0x180062651  push    rsi
0x180062652  push    rdi
0x180062653  push    r12
0x180062655  push    r14
0x180062657  push    r15
0x180062659  mov     rbp, rsp
0x18006265c  sub     rsp, 80h
0x180062663  xor     esi, esi
0x180062665  mov     eax, r8d
0x180062668  mov     r12, rcx
0x18006266b  mov     dword ptr [rbp+pbOutput], esi
0x18006266e  mov     [rbp+var_1C], esi
0x180062671  mov     dword ptr [rbp+var_18], esi
0x180062674  mov     dword ptr [rbp+var_20], esi
0x180062677  cmp     [rbp+cIterations], rsi
0x18006267b  jz      loc_1800628D4
0x180062681  cmp     [rbp+dwFlags], esi
0x180062687  jnz     loc_1800628D4
0x18006268d  test    rdx, rdx
0x180062690  jnz     short loc_18006269A
0x180062692  test    eax, eax
0x180062694  jnz     loc_1800628D4
0x18006269a  test    r9, r9
0x18006269d  jnz     short loc_1800626A8
0x18006269f  cmp     [rbp+cbSalt], esi
0x1800626a2  jnz     loc_1800628D4
0x1800626a8  cmp     [rbp+pbDerivedKey], rsi
0x1800626ac  jz      loc_1800628D4
0x1800626b2  mov     r15d, [rbp+cbDerivedKey]
0x1800626b6  test    r15d, r15d
0x1800626b9  jz      loc_1800628D4
0x1800626bf  lea     rax, [rbp+var_1C]
0x1800626c3  mov     [rsp+80h+var_58], esi; dwFlags
0x1800626c7  mov     r14d, 4
0x1800626cd  mov     [rsp+80h+pcbResult], rax; pcbResult
0x1800626d2  mov     r9d, r14d; cbOutput
0x1800626d5  lea     r8, [rbp+pbOutput]; pbOutput
0x1800626d9  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x1800626e0  call    BCryptGetProperty
0x1800626e5  test    eax, eax
0x1800626e7  js      loc_1800628C2
0x1800626ed  cmp     dword ptr [rbp+pbOutput], esi
0x1800626f0  jz      loc_1800628C2
0x1800626f6  lea     rax, [rbp+var_1C]
0x1800626fa  mov     [rsp+80h+var_58], esi; dwFlags
0x1800626fe  mov     r9d, r14d; cbOutput
0x180062701  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180062706  lea     r8, [rbp+var_20]; pbOutput
0x18006270a  mov     rcx, r12; hObject
0x18006270d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180062714  call    BCryptGetProperty
0x180062719  mov     ebx, eax
0x18006271b  test    eax, eax
0x18006271d  jns     short loc_18006272C
0x18006271f  mov     r9d, 1D83h
0x180062725  mov     ecx, eax
0x180062727  jmp     loc_1800628E4
0x18006272c  mov     ecx, dword ptr [rbp+var_20]
0x18006272f  lea     r8, [rbp+var_18]; pbOutput
0x180062733  xor     edx, edx
0x180062735  mov     [rsp+80h+var_58], esi; dwFlags
0x180062739  mov     r9d, r14d; cbOutput
0x18006273c  lea     eax, [rcx-1]
0x18006273f  add     eax, r15d
0x180062742  div     ecx
0x180062744  lea     rdx, aObjectlength; "ObjectLength"
0x18006274b  mov     rcx, r12; hObject
0x18006274e  mov     edi, eax
0x180062750  mov     [rbp+var_10], eax
0x180062753  lea     rax, [rbp+var_1C]
0x180062757  mov     [rsp+80h+pcbResult], rax; pcbResult
0x18006275c  call    BCryptGetProperty
0x180062761  mov     ebx, eax
0x180062763  test    eax, eax
0x180062765  jns     short loc_18006276F
0x180062767  mov     r9d, 1D94h
0x18006276d  jmp     short loc_180062725
0x18006276f  mov     ecx, dword ptr [rbp+var_20]
0x180062772  call    MSCryptAlloc
0x180062777  mov     ecx, dword ptr [rbp+var_18]
0x18006277a  mov     rsi, rax
0x18006277d  call    MSCryptAlloc
0x180062782  mov     ecx, dword ptr [rbp+var_20]
0x180062785  mov     r14, rax
0x180062788  imul    ecx, edi
0x18006278b  call    MSCryptAlloc
0x180062790  mov     rdi, rax
0x180062793  test    rsi, rsi
0x180062796  jz      loc_180062844
0x18006279c  test    r14, r14
0x18006279f  jz      loc_180062844
0x1800627a5  test    rax, rax
0x1800627a8  jz      loc_180062844
0x1800627ae  xor     ecx, ecx
0x1800627b0  cmp     ecx, [rbp+var_10]
0x1800627b3  jnb     short loc_180062831
0x1800627b5  mov     edx, dword ptr [rbp+var_20]
0x1800627b8  lea     r8d, [rcx+1]
0x1800627bc  mov     eax, dword ptr [rbp+var_18]
0x1800627bf  mov     r9, [rbp+arg_18]
0x1800627c3  mov     [rsp+80h+var_28], edx
0x1800627c7  imul    ecx, edx
0x1800627ca  mov     rdx, [rbp+arg_8]
0x1800627ce  mov     [rbp+var_C], r8d
0x1800627d2  add     rcx, rdi
0x1800627d5  mov     [rsp+80h+var_30], rcx
0x1800627da  mov     rcx, r12
0x1800627dd  mov     [rsp+80h+var_38], rsi
0x1800627e2  mov     [rsp+80h+var_40], eax
0x1800627e6  mov     rax, [rbp+cIterations]
0x1800627ea  mov     [rsp+80h+var_48], r14
0x1800627ef  mov     [rsp+80h+var_50], r8d
0x1800627f4  mov     r8d, [rbp+arg_10]
0x1800627f8  mov     qword ptr [rsp+80h+var_58], rax
0x1800627fd  mov     eax, [rbp+cbSalt]
0x180062800  mov     dword ptr [rsp+80h+pcbResult], eax
0x180062804  call    GetPBKDF2Block
0x180062809  mov     ebx, eax
0x18006280b  test    eax, eax
0x18006280d  js      short loc_180062814
0x18006280f  mov     ecx, [rbp+var_C]
0x180062812  jmp     short loc_1800627B0
0x180062814  mov     r9d, 1DB9h
0x18006281a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180062821  lea     rdx, aStatus; "Status"
0x180062828  mov     ecx, eax
0x18006282a  call    DebugTraceError
0x18006282f  jmp     short loc_18006286C
0x180062831  mov     rcx, [rbp+pbDerivedKey]; void *
0x180062835  mov     r8, r15; Size
0x180062838  mov     rdx, rdi; Src
0x18006283b  call    memmove
0x180062840  xor     ebx, ebx
0x180062842  jmp     short loc_18006286C
0x180062844  mov     r9d, 1DA5h
0x18006284a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180062851  lea     rdx, aStatus; "Status"
0x180062858  mov     ecx, 0C0000017h
0x18006285d  call    DebugTraceError
0x180062862  mov     ebx, 0C0000017h
0x180062867  test    rdi, rdi
0x18006286a  jz      short loc_18006288F
0x18006286c  mov     ecx, dword ptr [rbp+var_20]
0x18006286f  mov     rax, rdi
0x180062872  imul    ecx, [rbp+var_10]
0x180062876  test    rcx, rcx
0x180062879  jz      short loc_180062887
0x18006287b  mov     byte ptr [rax], 0
0x18006287e  inc     rax
0x180062881  sub     rcx, 1
0x180062885  jnz     short loc_18006287B
0x180062887  mov     rcx, rdi; P
0x18006288a  call    MSCryptFree
0x18006288f  test    r14, r14
0x180062892  jz      short loc_18006289C
0x180062894  mov     rcx, r14; P
0x180062897  call    MSCryptFree
0x18006289c  test    rsi, rsi
0x18006289f  jz      short loc_1800628F7
0x1800628a1  mov     eax, dword ptr [rbp+var_20]
0x1800628a4  mov     rcx, rsi
0x1800628a7  test    rax, rax
0x1800628aa  jz      short loc_1800628B8
0x1800628ac  mov     byte ptr [rcx], 0
0x1800628af  inc     rcx
0x1800628b2  sub     rax, 1
0x1800628b6  jnz     short loc_1800628AC
0x1800628b8  mov     rcx, rsi; P
0x1800628bb  call    MSCryptFree
0x1800628c0  jmp     short loc_1800628F7
0x1800628c2  mov     ebx, 0C0000008h
0x1800628c7  mov     r9d, 1D77h
0x1800628cd  mov     ecx, 0C0000008h
0x1800628d2  jmp     short loc_1800628E4
0x1800628d4  mov     ebx, 0C000000Dh
0x1800628d9  mov     r9d, 1D6Ah
0x1800628df  mov     ecx, 0C000000Dh
0x1800628e4  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800628eb  lea     rdx, aStatus; "Status"
0x1800628f2  call    DebugTraceError
0x1800628f7  mov     eax, ebx
0x1800628f9  add     rsp, 80h
0x180062900  pop     r15
0x180062902  pop     r14
0x180062904  pop     r12
0x180062906  pop     rdi
0x180062907  pop     rsi
0x180062908  pop     rbx
0x180062909  pop     rbp
0x18006290a  retn
```
