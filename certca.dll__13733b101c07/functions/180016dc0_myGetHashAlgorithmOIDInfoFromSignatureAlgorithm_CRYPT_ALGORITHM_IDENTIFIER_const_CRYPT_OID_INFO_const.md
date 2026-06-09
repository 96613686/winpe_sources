# myGetHashAlgorithmOIDInfoFromSignatureAlgorithm(_CRYPT_ALGORITHM_IDENTIFIER const *,_CRYPT_OID_INFO const * *)

- ea: `0x180016dc0`
- end: `0x1800170f5`
- name: `?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z`
- size: `821`
- prototype: `__int64 __fastcall(const struct _CRYPT_ALGORITHM_IDENTIFIER *, const struct _CRYPT_OID_INFO **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callees

- `0x180008400`
- `0x18000d520`
- `0x180012450`
- `0x180016dc0`
- `0x1800172b0`
- `0x18001e080`
- `0x18003826e`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170e0`
- `CRYPT32!CryptFindOIDInfo` at `0x180016e0d`
- `CRYPT32!CryptFindOIDInfo` at `0x18001701b`
- `CRYPT32!CryptFindOIDInfo` at `0x180017074`
- `CRYPT32!CryptFindOIDInfo` at `0x180016e0d`
- `CRYPT32!CryptFindOIDInfo` at `0x18001701b`
- `CRYPT32!CryptFindOIDInfo` at `0x180017074`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x180016e8a`
- `CRYPT32!CryptInitOIDFunctionSet` at `0x180016e8a`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180016eb9`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180016eb9`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x1800170c2`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x1800170c2`

## string_xrefs

- `0x180016e83`: `CryptDllExtractEncodedSignatureParameters`

## pseudocode

```c
__int64 __fastcall myGetHashAlgorithmOIDInfoFromSignatureAlgorithm(
        const struct _CRYPT_ALGORITHM_IDENTIFIER *a1,
        const struct _CRYPT_OID_INFO **a2)
{
  LPSTR pszObjId; // rdx
  const struct _CRYPT_OID_INFO *v5; // rbx
  PCCRYPT_OID_INFO OIDInfo; // rax
  unsigned int v7; // ebx
  int v8; // edx
  unsigned int v9; // ecx
  const unsigned __int16 *v10; // rdx
  bool v11; // zf
  int v12; // eax
  HCRYPTOIDFUNCSET inited; // rax
  unsigned int v14; // edx
  unsigned int OIDInfoForAlgorithm; // eax
  int v16; // eax
  unsigned int v17; // ecx
  void **v18; // rdx
  void *p_dwValue; // rdx
  DWORD v20; // ecx
  CRYPT_OID_INFO *v21; // rax
  const unsigned __int16 *v22; // rcx
  unsigned int v23; // eax
  HCRYPTOIDFUNCADDR *phFuncAddr; // [rsp+28h] [rbp-40h]
  HLOCAL v26; // [rsp+40h] [rbp-28h] BYREF
  void *ppvFuncAddr; // [rsp+48h] [rbp-20h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+50h] [rbp-18h] BYREF
  HLOCAL v29[2]; // [rsp+58h] [rbp-10h] BYREF
  DWORD v30; // [rsp+A0h] [rbp+38h] BYREF
  struct _CRYPT_OID_INFO *v31; // [rsp+A8h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp+48h] BYREF
  HLOCAL v33; // [rsp+B8h] [rbp+50h] BYREF

  *a2 = 0;
  pszObjId = a1->pszObjId;
  v5 = 0;
  v30 = 0;
  v31 = 0;
  ppvFuncAddr = 0;
  hFuncAddr = 0;
  v26 = 0;
  v29[0] = 0;
  hMem = 0;
  v33 = 0;
  OIDInfo = CryptFindOIDInfo(1u, pszObjId, 4u);
  if ( !OIDInfo )
  {
    v7 = -2146885628;
    CSPrintErrorLineFile(0xF1C01A4u, -2146885628);
    v8 = -2146885628;
    v9 = 60883364;
LABEL_3:
    CSPrintErrorLineFile(v9, v8);
    goto LABEL_44;
  }
  if ( OIDInfo->cbSize < 0x38
    || (v10 = *(const unsigned __int16 **)&OIDInfo[1].cbSize) == 0
    || (v11 = (unsigned int)mylstrcmpNLSub(L"CryptOIDInfoHashParameters", v10, -1, 1) == 0, v12 = 1, !v11) )
  {
    v12 = 0;
  }
  if ( v12 )
  {
    if ( !a1->Parameters.cbData || !a1->Parameters.pbData )
    {
LABEL_22:
      if ( !strcmp_0("1.2.840.10045.4.3", a1->pszObjId) )
      {
        if ( !myDecodeObjectEx(
                0x10001u,
                "1.2.840.10045.4.3",
                a1->Parameters.pbData,
                a1->Parameters.cbData,
                0,
                (__int64)phFuncAddr,
                &v33,
                &v30) )
        {
          v7 = myHLastError();
          v8 = v7;
          v9 = 65143204;
          goto LABEL_3;
        }
        v18 = (void **)v33;
      }
      else
      {
        if ( strcmp_0("1.2.840.113549.1.1.10", a1->pszObjId) )
        {
          v8 = -2146889726;
          v9 = 67305892;
          v7 = -2146889726;
          goto LABEL_3;
        }
        if ( !myDecodeObjectEx(
                0x10001u,
                (const CHAR *)0x4B,
                a1->Parameters.pbData,
                a1->Parameters.cbData,
                0,
                (__int64)phFuncAddr,
                &hMem,
                &v30) )
        {
          v7 = myHLastError();
          v8 = v7;
          v9 = 66584996;
          goto LABEL_3;
        }
        v18 = (void **)hMem;
      }
      p_dwValue = *v18;
      v20 = 1;
      goto LABEL_40;
    }
    inited = CryptInitOIDFunctionSet("CryptDllExtractEncodedSignatureParameters", 0);
    if ( inited )
    {
      if ( CryptGetOIDFunctionAddress(inited, 0x10001u, a1->pszObjId, 0, &ppvFuncAddr, &hFuncAddr) )
      {
        if ( ((unsigned int (__fastcall *)(__int64, const struct _CRYPT_ALGORITHM_IDENTIFIER *, HLOCAL *, HLOCAL *))ppvFuncAddr)(
               65537,
               a1,
               v29,
               &v26) )
        {
          OIDInfoForAlgorithm = myGetOIDInfoForAlgorithm(
                                  (const unsigned __int16 *)v26,
                                  v14,
                                  (const struct _CRYPT_OID_INFO **)&v31);
          v7 = OIDInfoForAlgorithm;
          if ( OIDInfoForAlgorithm )
          {
            v8 = OIDInfoForAlgorithm;
            v9 = 63046052;
            goto LABEL_3;
          }
          v5 = v31;
LABEL_21:
          if ( v5 )
            goto LABEL_43;
          goto LABEL_22;
        }
        v16 = myHLastError();
        v17 = 63242660;
      }
      else
      {
        v16 = myHLastError();
        v17 = 63504804;
      }
    }
    else
    {
      v16 = myHLastError();
      v17 = 63766948;
    }
    CSPrintErrorLineFile(v17, v16);
    goto LABEL_21;
  }
  v21 = (CRYPT_OID_INFO *)CryptFindOIDInfo(1u, a1->pszObjId, 4u);
  v31 = v21;
  v5 = v21;
  if ( !v21 )
    goto LABEL_41;
  p_dwValue = &v21->dwValue;
  if ( ((v21->dwValue + 3) & 0xFFFFFFFD) == 0 && v21->cbSize >= 0x38 )
  {
    v22 = *(const unsigned __int16 **)&v21[1].cbSize;
    if ( v22 )
    {
      v23 = myGetOIDInfoForAlgorithm(v22, (unsigned int)p_dwValue, (const struct _CRYPT_OID_INFO **)&v31);
      v7 = v23;
      if ( v23 )
      {
        v8 = v23;
        v9 = 68682148;
        goto LABEL_3;
      }
      v5 = v31;
      goto LABEL_41;
    }
  }
  v20 = 3;
LABEL_40:
  v5 = CryptFindOIDInfo(v20, p_dwValue, 1u);
LABEL_41:
  if ( !v5 )
  {
    v8 = -2146889726;
    v9 = 69534116;
    v7 = -2146889726;
    goto LABEL_3;
  }
LABEL_43:
  *a2 = v5;
  v7 = 0;
LABEL_44:
  if ( hMem )
    LocalFree(hMem);
  if ( v33 )
    LocalFree(v33);
  if ( hFuncAddr )
    CryptFreeOIDFunctionAddress(hFuncAddr, 0);
  if ( v26 )
    LocalFree(v26);
  if ( v29[0] )
    LocalFree(v29[0]);
  return v7;
}

```

## disassembly

```asm
0x180016dc0  push    rbp
0x180016dc2  push    rbx
0x180016dc3  push    rsi
0x180016dc4  push    rdi
0x180016dc5  push    r14
0x180016dc7  push    r15
0x180016dc9  mov     rbp, rsp
0x180016dcc  sub     rsp, 68h
0x180016dd0  xor     r14d, r14d
0x180016dd3  mov     rsi, rdx
0x180016dd6  mov     [rdx], r14
0x180016dd9  mov     rdi, rcx
0x180016ddc  mov     rdx, [rcx]; pvKey
0x180016ddf  mov     ebx, r14d
0x180016de2  mov     [rbp+arg_0], r14d
0x180016de6  lea     r15d, [r14+1]
0x180016dea  mov     [rbp+arg_8], rbx
0x180016dee  mov     ecx, r15d; dwKeyType
0x180016df1  mov     [rbp+var_20], r14
0x180016df5  lea     r8d, [r14+4]; dwGroupId
0x180016df9  mov     [rbp+hFuncAddr], r14
0x180016dfd  mov     [rbp+var_28], r14
0x180016e01  mov     [rbp+var_10], r14
0x180016e05  mov     [rbp+hMem], r14
0x180016e09  mov     [rbp+arg_18], r14
0x180016e0d  call    cs:__imp_CryptFindOIDInfo
0x180016e13  test    rax, rax
0x180016e16  jnz     short loc_180016E3A
0x180016e18  mov     ebx, 80092004h
0x180016e1d  mov     ecx, 0F1C01A4h; unsigned int
0x180016e22  mov     edx, ebx; int
0x180016e24  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180016e29  mov     edx, ebx; int
0x180016e2b  mov     ecx, 3A101A4h; unsigned int
0x180016e30  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180016e35  jmp     loc_180017099
0x180016e3a  cmp     dword ptr [rax], 38h ; '8'
0x180016e3d  jb      short loc_180016E62
0x180016e3f  mov     rdx, [rax+30h]; unsigned __int16 *
0x180016e43  test    rdx, rdx
0x180016e46  jz      short loc_180016E62
0x180016e48  mov     r9b, r15b; bool
0x180016e4b  lea     rcx, aCryptoidinfoha; "CryptOIDInfoHashParameters"
0x180016e52  or      r8d, 0FFFFFFFFh; int
0x180016e56  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180016e5b  test    eax, eax
0x180016e5d  mov     eax, r15d
0x180016e60  jz      short loc_180016E65
0x180016e62  mov     eax, r14d
0x180016e65  test    eax, eax
0x180016e67  jz      loc_18001700F
0x180016e6d  cmp     [rdi+8], r14d
0x180016e71  jz      loc_180016F37
0x180016e77  cmp     [rdi+10h], r14
0x180016e7b  jz      loc_180016F37
0x180016e81  xor     edx, edx; dwFlags
0x180016e83  lea     rcx, pszFuncName; "CryptDllExtractEncodedSignatureParamete"...
0x180016e8a  call    cs:__imp_CryptInitOIDFunctionSet
0x180016e90  test    rax, rax
0x180016e93  jz      loc_180016F1D
0x180016e99  mov     r8, [rdi]; pszOID
0x180016e9c  lea     rcx, [rbp+hFuncAddr]
0x180016ea0  mov     [rsp+68h+phFuncAddr], rcx; phFuncAddr
0x180016ea5  xor     r9d, r9d; dwFlags
0x180016ea8  lea     rcx, [rbp+var_20]
0x180016eac  mov     edx, 10001h; dwEncodingType
0x180016eb1  mov     [rsp+68h+ppvFuncAddr], rcx; ppvFuncAddr
0x180016eb6  mov     rcx, rax; hFuncSet
0x180016eb9  call    cs:__imp_CryptGetOIDFunctionAddress
0x180016ebf  test    eax, eax
0x180016ec1  jz      short loc_180016F11
0x180016ec3  mov     rax, [rbp+var_20]
0x180016ec7  lea     r9, [rbp+var_28]
0x180016ecb  lea     r8, [rbp+var_10]
0x180016ecf  mov     rdx, rdi
0x180016ed2  mov     ecx, 10001h
0x180016ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016edc  test    eax, eax
0x180016ede  jz      short loc_180016F05
0x180016ee0  mov     rcx, [rbp+var_28]; unsigned __int16 *
0x180016ee4  lea     r8, [rbp+arg_8]; struct _CRYPT_OID_INFO **
0x180016ee8  call    ?myGetOIDInfoForAlgorithm@@YAJPEBGKPEAPEBU_CRYPT_OID_INFO@@@Z; myGetOIDInfoForAlgorithm(ushort const *,ulong,_CRYPT_OID_INFO const * *)
0x180016eed  mov     ebx, eax
0x180016eef  test    eax, eax
0x180016ef1  jz      short loc_180016EFF
0x180016ef3  mov     edx, eax
0x180016ef5  mov     ecx, 3C201A4h
0x180016efa  jmp     loc_180016E30
0x180016eff  mov     rbx, [rbp+arg_8]
0x180016f03  jmp     short loc_180016F2E
0x180016f05  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180016f0a  mov     ecx, 3C501A4h
0x180016f0f  jmp     short loc_180016F27
0x180016f11  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180016f16  mov     ecx, 3C901A4h
0x180016f1b  jmp     short loc_180016F27
0x180016f1d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180016f22  mov     ecx, 3CD01A4h; unsigned int
0x180016f27  mov     edx, eax; int
0x180016f29  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180016f2e  test    rbx, rbx
0x180016f31  jnz     loc_180017093
0x180016f37  mov     rdx, [rdi]; Str2
0x180016f3a  lea     rcx, a128401004543; "1.2.840.10045.4.3"
0x180016f41  call    strcmp_0
0x180016f46  test    eax, eax
0x180016f48  jnz     short loc_180016FA0
0x180016f4a  mov     r9d, [rdi+8]
0x180016f4e  lea     rax, [rbp+arg_0]
0x180016f52  mov     r8, [rdi+10h]
0x180016f56  lea     rdx, a128401004543; "1.2.840.10045.4.3"
0x180016f5d  mov     [rsp+68h+var_30], rax
0x180016f62  mov     ecx, 10001h
0x180016f67  lea     rax, [rbp+arg_18]
0x180016f6b  mov     [rsp+68h+var_38], rax
0x180016f70  mov     dword ptr [rsp+68h+ppvFuncAddr], r14d
0x180016f75  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x180016f7a  test    eax, eax
0x180016f7c  jnz     short loc_180016F91
0x180016f7e  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180016f83  mov     ebx, eax
0x180016f85  mov     edx, eax
0x180016f87  mov     ecx, 3E201A4h
0x180016f8c  jmp     loc_180016E30
0x180016f91  mov     rdx, [rbp+arg_18]
0x180016f95  mov     rdx, [rdx]
0x180016f98  mov     ecx, r15d
0x180016f9b  jmp     loc_180017071
0x180016fa0  mov     rdx, [rdi]; Str2
0x180016fa3  lea     rcx, a12840113549111_2; "1.2.840.113549.1.1.10"
0x180016faa  call    strcmp_0
0x180016faf  test    eax, eax
0x180016fb1  jnz     short loc_180016FFE
0x180016fb3  mov     r9d, [rdi+8]
0x180016fb7  lea     rax, [rbp+arg_0]
0x180016fbb  mov     r8, [rdi+10h]
0x180016fbf  mov     edx, 4Bh ; 'K'
0x180016fc4  mov     [rsp+68h+var_30], rax
0x180016fc9  mov     ecx, 10001h
0x180016fce  lea     rax, [rbp+hMem]
0x180016fd2  mov     [rsp+68h+var_38], rax
0x180016fd7  mov     dword ptr [rsp+68h+ppvFuncAddr], r14d
0x180016fdc  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x180016fe1  test    eax, eax
0x180016fe3  jnz     short loc_180016FF8
0x180016fe5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180016fea  mov     ebx, eax
0x180016fec  mov     edx, eax
0x180016fee  mov     ecx, 3F801A4h
0x180016ff3  jmp     loc_180016E30
0x180016ff8  mov     rdx, [rbp+hMem]
0x180016ffc  jmp     short loc_180016F95
0x180016ffe  mov     edx, 80091002h
0x180017003  mov     ecx, 40301A4h
0x180017008  mov     ebx, edx
0x18001700a  jmp     loc_180016E30
0x18001700f  mov     rdx, [rdi]; pvKey
0x180017012  mov     r8d, 4; dwGroupId
0x180017018  mov     ecx, r15d; dwKeyType
0x18001701b  call    cs:__imp_CryptFindOIDInfo
0x180017021  mov     [rbp+arg_8], rax
0x180017025  mov     rbx, rax
0x180017028  test    rax, rax
0x18001702b  jz      short loc_18001707D
0x18001702d  lea     rdx, [rax+1Ch]; unsigned int
0x180017031  mov     eax, [rdx]
0x180017033  add     eax, 3
0x180017036  test    eax, 0FFFFFFFDh
0x18001703b  jnz     short loc_18001706C
0x18001703d  cmp     dword ptr [rbx], 38h ; '8'
0x180017040  jb      short loc_18001706C
0x180017042  mov     rcx, [rbx+30h]; unsigned __int16 *
0x180017046  test    rcx, rcx
0x180017049  jz      short loc_18001706C
0x18001704b  lea     r8, [rbp+arg_8]; struct _CRYPT_OID_INFO **
0x18001704f  call    ?myGetOIDInfoForAlgorithm@@YAJPEBGKPEAPEBU_CRYPT_OID_INFO@@@Z; myGetOIDInfoForAlgorithm(ushort const *,ulong,_CRYPT_OID_INFO const * *)
0x180017054  mov     ebx, eax
0x180017056  test    eax, eax
0x180017058  jz      short loc_180017066
0x18001705a  mov     edx, eax
0x18001705c  mov     ecx, 41801A4h
0x180017061  jmp     loc_180016E30
0x180017066  mov     rbx, [rbp+arg_8]
0x18001706a  jmp     short loc_18001707D
0x18001706c  mov     ecx, 3; dwKeyType
0x180017071  mov     r8d, r15d; dwGroupId
0x180017074  call    cs:__imp_CryptFindOIDInfo
0x18001707a  mov     rbx, rax
0x18001707d  test    rbx, rbx
0x180017080  jnz     short loc_180017093
0x180017082  mov     edx, 80091002h
0x180017087  mov     ecx, 42501A4h
0x18001708c  mov     ebx, edx
0x18001708e  jmp     loc_180016E30
0x180017093  mov     [rsi], rbx
0x180017096  mov     ebx, r14d
0x180017099  mov     rcx, [rbp+hMem]; hMem
0x18001709d  test    rcx, rcx
0x1800170a0  jz      short loc_1800170A8
0x1800170a2  call    cs:__imp_LocalFree
0x1800170a8  mov     rcx, [rbp+arg_18]; hMem
0x1800170ac  test    rcx, rcx
0x1800170af  jz      short loc_1800170B7
0x1800170b1  call    cs:__imp_LocalFree
0x1800170b7  mov     rcx, [rbp+hFuncAddr]; hFuncAddr
0x1800170bb  test    rcx, rcx
0x1800170be  jz      short loc_1800170C8
0x1800170c0  xor     edx, edx; dwFlags
0x1800170c2  call    cs:__imp_CryptFreeOIDFunctionAddress
0x1800170c8  mov     rcx, [rbp+var_28]; hMem
0x1800170cc  test    rcx, rcx
0x1800170cf  jz      short loc_1800170D7
0x1800170d1  call    cs:__imp_LocalFree
0x1800170d7  mov     rcx, [rbp+var_10]; hMem
0x1800170db  test    rcx, rcx
0x1800170de  jz      short loc_1800170E6
0x1800170e0  call    cs:__imp_LocalFree
0x1800170e6  mov     eax, ebx
0x1800170e8  add     rsp, 68h
0x1800170ec  pop     r15
0x1800170ee  pop     r14
0x1800170f0  pop     rdi
0x1800170f1  pop     rsi
0x1800170f2  pop     rbx
0x1800170f3  pop     rbp
0x1800170f4  retn
```
