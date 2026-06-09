# BCryptImportKeyPair

- ea: `0x180063830`
- end: `0x180063b86`
- name: `BCryptImportKeyPair`
- size: `854`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_KEY_HANDLE hImportKey, LPCWSTR pszBlobType, BCRYPT_KEY_HANDLE *phKey, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000daf0`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18003f910`
- `0x180050500`
- `0x180063830`
- `0x180065954`
- `0x1800a4232`
- `0x1800a4300`

## string_xrefs

- `0x180063903`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180063b07`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180063b5f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptImportKeyPair(
        BCRYPT_ALG_HANDLE hAlgorithm,
        BCRYPT_KEY_HANDLE hImportKey,
        LPCWSTR pszBlobType,
        BCRYPT_KEY_HANDLE *phKey,
        PUCHAR pbInput,
        ULONG cbInput,
        ULONG dwFlags)
{
  BCRYPT_KEY_HANDLE *v7; // r13
  const wchar_t *v8; // rbx
  __int64 v11; // rdx
  __int64 v12; // rdi
  NTSTATUS v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // r14
  UCHAR *v18; // rsi
  __int64 (__fastcall *v19)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // rax
  __int64 v20; // rax
  __int64 v21; // r13
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r12
  int v25; // ecx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  ULONG v29; // ecx
  PUCHAR v30; // rax
  ULONG v32; // [rsp+50h] [rbp-68h] BYREF
  __int64 (__fastcall *v33)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG); // [rsp+58h] [rbp-60h]
  __int64 v34; // [rsp+60h] [rbp-58h]

  v7 = phKey;
  v32 = 0;
  v8 = pszBlobType;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqSqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)hImportKey,
      (_DWORD)pszBlobType,
      (_DWORD)hAlgorithm,
      (char)hImportKey,
      (__int64)pszBlobType,
      (char)phKey,
      (char)pbInput,
      cbInput,
      dwFlags);
  v12 = ValidateBaseAlgHandle(hAlgorithm);
  if ( !v12 )
  {
    v13 = -1073741816;
    v14 = 4858;
    v15 = 3221225480LL;
LABEL_47:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v14);
    return v13;
  }
  if ( !v7 || !v8 )
  {
    v13 = -1073741811;
    v14 = 4866;
    v15 = 3221225485LL;
    goto LABEL_47;
  }
  v16 = MSCryptAlloc(32, v11);
  v17 = (char *)v16;
  if ( !v16 )
  {
    v13 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 4892);
    return v13;
  }
  *(_DWORD *)v16 = 32;
  v18 = 0;
  *(_DWORD *)(v16 + 4) = 1431655762;
  *(_QWORD *)(v16 + 8) = v12;
  if ( *(_DWORD *)(v12 + 36) != 3 )
  {
    if ( *(_DWORD *)(v12 + 36) == 4 )
    {
      v19 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v12 + 128);
      goto LABEL_17;
    }
    if ( *(_DWORD *)(v12 + 36) != 5 && *(_DWORD *)(v12 + 36) != 8 )
    {
      v13 = -1073741637;
LABEL_41:
      MSCryptFree(v17);
      goto LABEL_43;
    }
  }
  v19 = *(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, char *, PUCHAR, ULONG, ULONG))(v12 + 120);
LABEL_17:
  v33 = v19;
  v34 = 0;
  if ( hImportKey )
  {
    v20 = ValidateBaseKeyHandle(hImportKey);
    v21 = v20;
    if ( !v20 )
    {
      v22 = 4934;
LABEL_20:
      v13 = -1073741816;
      v23 = 3221225480LL;
LABEL_40:
      DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v22);
      goto LABEL_41;
    }
    v24 = *(_QWORD *)(v20 + 8);
    v25 = wcscmp_0(v8, L"PKCS11RsaAesWrapBlob") != 0 ? 1 : 3;
    if ( !v24 )
    {
      v13 = -1073739510;
      v22 = 4946;
      v23 = 3221227786LL;
      goto LABEL_40;
    }
    if ( *(_DWORD *)(v24 + 36) != v25 )
    {
      v22 = 4953;
      goto LABEL_20;
    }
    if ( *(_QWORD *)(v24 + 40) != *(_QWORD *)(v12 + 40) )
    {
      v13 = -1073741788;
      v22 = 4960;
      v23 = 3221225508LL;
      goto LABEL_40;
    }
    v26 = *(_QWORD *)(v21 + 16);
    v7 = phKey;
    v34 = v26;
  }
  if ( !wcscmp_0(v8, L"RSAFULLPRIVATEBLOB") )
  {
    v27 = ConvertRsaFullPrivateBlob(pbInput, cbInput, 0, 0, &v32);
    v13 = v27;
    if ( v27 < 0 )
    {
      v22 = 4981;
LABEL_39:
      v23 = (unsigned int)v27;
      goto LABEL_40;
    }
    v18 = (UCHAR *)MSCryptAlloc(v32, v28);
    if ( !v18 )
    {
      v13 = -1073741801;
      v22 = 4990;
      v23 = 3221225495LL;
      goto LABEL_40;
    }
    v27 = ConvertRsaFullPrivateBlob(pbInput, cbInput, v18, v32, &v32);
    v13 = v27;
    if ( v27 < 0 )
    {
      v22 = 5002;
      goto LABEL_39;
    }
    v29 = v32;
    v8 = L"RSAPRIVATEBLOB";
    v30 = v18;
  }
  else
  {
    v29 = cbInput;
    v30 = pbInput;
  }
  v27 = v33(*(_QWORD *)(v12 + 24), v34, v8, v17 + 16, v30, v29, dwFlags);
  v13 = v27;
  if ( v27 < 0 )
  {
    v22 = 5210;
    goto LABEL_39;
  }
  *v7 = v17;
  _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
  v13 = 0;
LABEL_43:
  if ( v18 )
    MSCryptFree(v18);
  return v13;
}

```

## disassembly

```asm
0x180063830  mov     [rsp+arg_18], r9
0x180063835  push    rbx
0x180063836  push    rbp
0x180063837  push    rsi
0x180063838  push    rdi
0x180063839  push    r12
0x18006383b  push    r13
0x18006383d  push    r14
0x18006383f  push    r15
0x180063841  sub     rsp, 78h
0x180063845  mov     r13, r9
0x180063848  mov     [rsp+0B8h+var_68], 0
0x180063850  mov     rbx, r8
0x180063853  mov     r12, rdx
0x180063856  mov     rdi, rcx
0x180063859  mov     rcx, cs:WPP_GLOBAL_Control
0x180063860  lea     rax, WPP_GLOBAL_Control
0x180063867  mov     rbp, [rsp+0B8h+pbInput]
0x18006386f  cmp     rcx, rax
0x180063872  jz      short loc_1800638B1
0x180063874  mov     eax, [rcx+2Ch]
0x180063877  test    al, 4
0x180063879  jz      short loc_1800638B1
0x18006387b  mov     eax, [rsp+0B8h+dwFlags]
0x180063882  mov     rcx, [rcx+18h]
0x180063886  mov     [rsp+0B8h+var_70], eax
0x18006388a  mov     eax, [rsp+0B8h+cbInput]
0x180063891  mov     [rsp+0B8h+var_78], eax
0x180063895  mov     [rsp+0B8h+var_80], rbp
0x18006389a  mov     [rsp+0B8h+var_88], r9
0x18006389f  mov     r9, rdi
0x1800638a2  mov     [rsp+0B8h+var_90], rbx
0x1800638a7  mov     [rsp+0B8h+var_98], rdx
0x1800638ac  call    WPP_SF_qqSqqdD
0x1800638b1  mov     rcx, rdi
0x1800638b4  call    ValidateBaseAlgHandle
0x1800638b9  mov     rdi, rax
0x1800638bc  test    rax, rax
0x1800638bf  jnz     short loc_1800638D6
0x1800638c1  mov     ebx, 0C0000008h
0x1800638c6  mov     r9d, 12FAh
0x1800638cc  mov     ecx, 0C0000008h
0x1800638d1  jmp     loc_180063B5F
0x1800638d6  test    r13, r13
0x1800638d9  jz      loc_180063B4F
0x1800638df  test    rbx, rbx
0x1800638e2  jz      loc_180063B4F
0x1800638e8  mov     ecx, 20h ; ' '
0x1800638ed  mov     r15, rbp
0x1800638f0  call    MSCryptAlloc
0x1800638f5  mov     r14, rax
0x1800638f8  test    rax, rax
0x1800638fb  jnz     short loc_180063925
0x1800638fd  mov     r9d, 131Ch
0x180063903  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006390a  lea     rdx, aStatus; "Status"
0x180063911  mov     ecx, 0C0000017h
0x180063916  mov     ebx, 0C0000017h
0x18006391b  call    DebugTraceError
0x180063920  jmp     loc_180063B3B
0x180063925  mov     dword ptr [rax], 20h ; ' '
0x18006392b  xor     esi, esi
0x18006392d  mov     dword ptr [rax+4], 55555552h
0x180063934  mov     [rax+8], rdi
0x180063938  mov     ecx, [rdi+24h]
0x18006393b  sub     ecx, 3
0x18006393e  jz      short loc_180063962
0x180063940  sub     ecx, 1
0x180063943  jz      short loc_180063959
0x180063945  sub     ecx, 1
0x180063948  jz      short loc_180063962
0x18006394a  cmp     ecx, 3
0x18006394d  jz      short loc_180063962
0x18006394f  mov     ebx, 0C00000BBh
0x180063954  jmp     loc_180063B1A
0x180063959  mov     rax, [rdi+80h]
0x180063960  jmp     short loc_180063966
0x180063962  mov     rax, [rdi+78h]
0x180063966  mov     [rsp+0B8h+var_60], rax
0x18006396b  mov     [rsp+0B8h+var_58], rsi
0x180063970  test    r12, r12
0x180063973  jz      loc_180063A15
0x180063979  mov     rcx, r12
0x18006397c  call    ValidateBaseKeyHandle
0x180063981  mov     r13, rax
0x180063984  test    rax, rax
0x180063987  jnz     short loc_18006399E
0x180063989  mov     r9d, 1346h
0x18006398f  mov     ebx, 0C0000008h
0x180063994  mov     ecx, 0C0000008h
0x180063999  jmp     loc_180063B07
0x18006399e  mov     r12, [rax+8]
0x1800639a2  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x1800639a9  mov     rcx, rbx; Str1
0x1800639ac  call    wcscmp_0
0x1800639b1  neg     eax
0x1800639b3  sbb     ecx, ecx
0x1800639b5  and     ecx, 0FFFFFFFEh
0x1800639b8  add     ecx, 3
0x1800639bb  test    r12, r12
0x1800639be  jnz     short loc_1800639D5
0x1800639c0  mov     ebx, 0C000090Ah
0x1800639c5  mov     r9d, 1352h
0x1800639cb  mov     ecx, 0C000090Ah
0x1800639d0  jmp     loc_180063B07
0x1800639d5  cmp     [r12+24h], ecx
0x1800639da  jz      short loc_1800639E4
0x1800639dc  mov     r9d, 1359h
0x1800639e2  jmp     short loc_18006398F
0x1800639e4  mov     rax, [rdi+28h]
0x1800639e8  cmp     [r12+28h], rax
0x1800639ed  jz      short loc_180063A04
0x1800639ef  mov     ebx, 0C0000024h
0x1800639f4  mov     r9d, 1360h
0x1800639fa  mov     ecx, 0C0000024h
0x1800639ff  jmp     loc_180063B07
0x180063a04  mov     rax, [r13+10h]
0x180063a08  mov     r13, [rsp+0B8h+arg_18]
0x180063a10  mov     [rsp+0B8h+var_58], rax
0x180063a15  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x180063a1c  mov     rcx, rbx; Str1
0x180063a1f  call    wcscmp_0
0x180063a24  test    eax, eax
0x180063a26  jnz     loc_180063AC1
0x180063a2c  mov     r12d, [rsp+0B8h+cbInput]
0x180063a34  lea     rax, [rsp+0B8h+var_68]
0x180063a39  mov     edx, r12d
0x180063a3c  mov     [rsp+0B8h+var_98], rax
0x180063a41  xor     r9d, r9d
0x180063a44  xor     r8d, r8d
0x180063a47  mov     rcx, rbp
0x180063a4a  call    ConvertRsaFullPrivateBlob
0x180063a4f  mov     ebx, eax
0x180063a51  test    eax, eax
0x180063a53  jns     short loc_180063A60
0x180063a55  mov     r9d, 1375h
0x180063a5b  jmp     loc_180063B05
0x180063a60  mov     ecx, [rsp+0B8h+var_68]
0x180063a64  call    MSCryptAlloc
0x180063a69  mov     rsi, rax
0x180063a6c  test    rax, rax
0x180063a6f  jnz     short loc_180063A86
0x180063a71  mov     ebx, 0C0000017h
0x180063a76  mov     r9d, 137Eh
0x180063a7c  mov     ecx, 0C0000017h
0x180063a81  jmp     loc_180063B07
0x180063a86  mov     r9d, [rsp+0B8h+var_68]
0x180063a8b  lea     rax, [rsp+0B8h+var_68]
0x180063a90  mov     r8, rsi
0x180063a93  mov     [rsp+0B8h+var_98], rax
0x180063a98  mov     edx, r12d
0x180063a9b  mov     rcx, rbp
0x180063a9e  call    ConvertRsaFullPrivateBlob
0x180063aa3  mov     ebx, eax
0x180063aa5  test    eax, eax
0x180063aa7  jns     short loc_180063AB1
0x180063aa9  mov     r9d, 138Ah
0x180063aaf  jmp     short loc_180063B05
0x180063ab1  mov     ecx, [rsp+0B8h+var_68]
0x180063ab5  lea     rbx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180063abc  mov     rax, rsi
0x180063abf  jmp     short loc_180063ACB
0x180063ac1  mov     ecx, [rsp+0B8h+cbInput]
0x180063ac8  mov     rax, rbp
0x180063acb  mov     edx, [rsp+0B8h+dwFlags]
0x180063ad2  lea     r9, [r14+10h]
0x180063ad6  mov     dword ptr [rsp+0B8h+var_88], edx
0x180063ada  mov     r8, rbx
0x180063add  mov     rdx, [rsp+0B8h+var_58]
0x180063ae2  mov     dword ptr [rsp+0B8h+var_90], ecx
0x180063ae6  mov     rcx, [rdi+18h]
0x180063aea  mov     [rsp+0B8h+var_98], rax
0x180063aef  mov     rax, [rsp+0B8h+var_60]
0x180063af4  call    _guard_dispatch_icall
0x180063af9  mov     ebx, eax
0x180063afb  test    eax, eax
0x180063afd  jns     short loc_180063B24
0x180063aff  mov     r9d, 145Ah
0x180063b05  mov     ecx, eax
0x180063b07  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063b0e  lea     rdx, aStatus; "Status"
0x180063b15  call    DebugTraceError
0x180063b1a  mov     rcx, r14; P
0x180063b1d  call    MSCryptFree
0x180063b22  jmp     short loc_180063B2E
0x180063b24  mov     [r13+0], r14
0x180063b28  lock inc dword ptr [rdi+10h]
0x180063b2c  xor     ebx, ebx
0x180063b2e  test    rsi, rsi
0x180063b31  jz      short loc_180063B3B
0x180063b33  mov     rcx, rsi; P
0x180063b36  call    MSCryptFree
0x180063b3b  test    r15, r15
0x180063b3e  jz      short loc_180063B72
0x180063b40  cmp     r15, rbp
0x180063b43  jz      short loc_180063B72
0x180063b45  mov     rcx, r15; P
0x180063b48  call    MSCryptFree
0x180063b4d  jmp     short loc_180063B72
0x180063b4f  mov     ebx, 0C000000Dh
0x180063b54  mov     r9d, 1302h
0x180063b5a  mov     ecx, 0C000000Dh
0x180063b5f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063b66  lea     rdx, aStatus; "Status"
0x180063b6d  call    DebugTraceError
0x180063b72  mov     eax, ebx
0x180063b74  add     rsp, 78h
0x180063b78  pop     r15
0x180063b7a  pop     r14
0x180063b7c  pop     r13
0x180063b7e  pop     r12
0x180063b80  pop     rdi
0x180063b81  pop     rsi
0x180063b82  pop     rbp
0x180063b83  pop     rbx
0x180063b84  retn
```
