# CERTIFICATE_CONTEXT::GetCookie(STRU *)

- ea: `0x18002c768`
- end: `0x18002ca56`
- name: `?GetCookie@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z`
- size: `750`
- prototype: `__int64 __fastcall(CERTIFICATE_CONTEXT *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180029ae0`

## callees

- `0x18002c664`
- `0x18002c768`
- `0x18002ca5c`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8e2`
- `CRYPTSP!CryptDestroyHash` at `0x18002c8fc`
- `CRYPTSP!CryptDestroyHash` at `0x18002c980`
- `CRYPTSP!CryptDestroyHash` at `0x18002c8fc`
- `CRYPTSP!CryptDestroyHash` at `0x18002c980`
- `CRYPTSP!CryptGetHashParam` at `0x18002c96d`
- `CRYPTSP!CryptGetHashParam` at `0x18002c96d`
- `CRYPTSP!CryptCreateHash` at `0x18002c88a`
- `CRYPTSP!CryptCreateHash` at `0x18002c88a`
- `CRYPTSP!CryptHashData` at `0x18002c8d8`
- `CRYPTSP!CryptHashData` at `0x18002c92f`
- `CRYPTSP!CryptHashData` at `0x18002c8d8`
- `CRYPTSP!CryptHashData` at `0x18002c92f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002ca13`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002ca13`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ca28`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ca28`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c90e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c91a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c94d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c98b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c90e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c91a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c94d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002c98b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002c93e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002c93e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002c850`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002c850`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002c7ca`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002c7ca`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002c7fc`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002c7fc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002c7dc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002c7dc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ca1e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002ca1e`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002c8c4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002c8c4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002c9c6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002c9fc`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002c9c6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002c9fc`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002c8b7`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002c8b7`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18002c85e`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18002c85e`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_CONTEXT::GetCookie(CERTIFICATE_CONTEXT *this, struct STRU *a2)
{
  signed int Issuer; // ebx
  const unsigned __int16 *Str; // rax
  signed int v6; // eax
  DWORD CCH; // ebx
  const BYTE *v8; // rax
  signed int LastError; // eax
  _DWORD *v10; // rax
  BUFFER *v11; // rcx
  DWORD v12; // edi
  const BYTE **v13; // rax
  BYTE *v14; // rax
  _BYTE *Ptr; // rsi
  __int64 i; // rdi
  char v17; // al
  unsigned __int8 v18; // cl
  char v19; // al
  unsigned __int8 v20; // cl
  unsigned __int16 v22[4]; // [rsp+30h] [rbp-D0h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pdwDataLen; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[48]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v27[56]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v28[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v29[256]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v30[256]; // [rsp+210h] [rbp+110h] BYREF

  hHash = 0;
  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v27, v30, 0x100u);
  STRA::STRA((STRA *)v26, v29, 0x100u);
  memset(v28, 0, sizeof(v28));
  BUFFER::BUFFER((BUFFER *)v25, (unsigned __int8 *)v28, 0x20u);
  pdwDataLen = 0;
  *(_DWORD *)v22 = 0;
  if ( a2 )
  {
    if ( *((_DWORD *)this + 4) || (Issuer = CERTIFICATE_CONTEXT::DecodeCert(this), Issuer >= 0) )
    {
      Issuer = CERTIFICATE_CONTEXT::GetIssuer(this, (struct STRU *)v27);
      if ( Issuer >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v27);
        Issuer = STRA::CopyW((STRA *)v26, Str);
        if ( Issuer >= 0 )
        {
          if ( CryptCreateHash(CERTIFICATE_CONTEXT::sm_CryptProvider, 0x800Cu, 0, 0, &hHash) )
          {
            CCH = STRA::QueryCCH((STRA *)v26);
            v8 = (const BYTE *)STRA::QueryStr((STRA *)v26);
            if ( CryptHashData(hHash, v8, CCH, 0)
              && (v10 = BUFFER::QueryPtr((CERTIFICATE_CONTEXT *)((char *)this + 24)),
                  v11 = (CERTIFICATE_CONTEXT *)((char *)this + 24),
                  v12 = v10[2],
                  v13 = (const BYTE **)BUFFER::QueryPtr(v11),
                  CryptHashData(hHash, v13[2], v12, 0))
              && (pdwDataLen = BUFFER::QuerySize((BUFFER *)v25),
                  v14 = (BYTE *)BUFFER::QueryPtr((BUFFER *)v25),
                  CryptGetHashParam(hHash, 2u, v14, &pdwDataLen, 0)) )
            {
              CryptDestroyHash(hHash);
              Ptr = BUFFER::QueryPtr((BUFFER *)v25);
              for ( i = 0; (unsigned int)i < pdwDataLen; i = (unsigned int)(i + 1) )
              {
                v17 = 87;
                v18 = Ptr[i] >> 4;
                if ( v18 <= 9u )
                  v17 = 48;
                v22[0] = (unsigned __int8)(v18 + v17);
                Issuer = STRU::Append(a2, v22, 1u);
                if ( Issuer < 0 )
                  goto LABEL_26;
                v19 = 87;
                v20 = Ptr[i] & 0xF;
                if ( v20 <= 9u )
                  v19 = 48;
                v22[0] = (unsigned __int8)(v20 + v19);
                Issuer = STRU::Append(a2, v22, 1u);
                if ( Issuer < 0 )
                  goto LABEL_26;
              }
              Issuer = 0;
            }
            else
            {
              LastError = GetLastError();
              Issuer = LastError;
              if ( LastError > 0 )
                Issuer = (unsigned __int16)LastError | 0x80070000;
              CryptDestroyHash(hHash);
            }
          }
          else
          {
            v6 = GetLastError();
            Issuer = v6;
            if ( v6 > 0 )
              Issuer = (unsigned __int16)v6 | 0x80070000;
          }
        }
      }
    }
  }
  else
  {
    Issuer = -2147024809;
  }
LABEL_26:
  BUFFER::~BUFFER((BUFFER *)v25);
  STRA::~STRA((STRA *)v26);
  STRU::~STRU((STRU *)v27);
  return (unsigned int)Issuer;
}

```

## disassembly

```asm
0x18002c768  mov     [rsp-8+arg_10], rbx
0x18002c76d  push    rbp
0x18002c76e  push    rsi
0x18002c76f  push    rdi
0x18002c770  push    r14
0x18002c772  push    r15
0x18002c774  lea     rbp, [rsp-320h]
0x18002c77c  sub     rsp, 420h
0x18002c783  mov     rax, cs:__security_cookie
0x18002c78a  xor     rax, rsp
0x18002c78d  mov     [rbp+340h+var_30], rax
0x18002c794  mov     r15, rdx
0x18002c797  mov     [rsp+440h+hHash], 0
0x18002c7a0  mov     rdi, rcx
0x18002c7a3  xor     edx, edx; Val
0x18002c7a5  lea     rcx, [rbp+340h+var_230]; void *
0x18002c7ac  mov     r8d, 200h; Size
0x18002c7b2  call    memset_0
0x18002c7b7  mov     ebx, 100h
0x18002c7bc  lea     rdx, [rbp+340h+var_230]
0x18002c7c3  mov     r8d, ebx
0x18002c7c6  lea     rcx, [rbp+340h+var_390]
0x18002c7ca  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002c7d0  mov     r8d, ebx
0x18002c7d3  lea     rdx, [rbp+340h+var_330]
0x18002c7d7  lea     rcx, [rsp+440h+var_3C8]
0x18002c7dc  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002c7e2  xorps   xmm0, xmm0
0x18002c7e5  lea     rdx, [rbp+340h+var_358]
0x18002c7e9  mov     r8d, 20h ; ' '
0x18002c7ef  lea     rcx, [rsp+440h+var_3F8]
0x18002c7f4  movups  [rbp+340h+var_358], xmm0
0x18002c7f8  movups  [rbp+340h+var_348], xmm0
0x18002c7fc  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002c802  xor     eax, eax
0x18002c804  mov     [rsp+440h+pdwDataLen], 0
0x18002c80c  mov     dword ptr [rsp+440h+var_410], eax
0x18002c810  test    r15, r15
0x18002c813  jnz     short loc_18002C81F
0x18002c815  mov     ebx, 80070057h
0x18002c81a  jmp     loc_18002CA0E
0x18002c81f  cmp     [rdi+10h], eax
0x18002c822  jnz     short loc_18002C836
0x18002c824  mov     rcx, rdi; this
0x18002c827  call    ?DecodeCert@CERTIFICATE_CONTEXT@@AEAAJXZ; CERTIFICATE_CONTEXT::DecodeCert(void)
0x18002c82c  mov     ebx, eax
0x18002c82e  test    eax, eax
0x18002c830  js      loc_18002CA0E
0x18002c836  lea     rdx, [rbp+340h+var_390]; struct STRU *
0x18002c83a  mov     rcx, rdi; this
0x18002c83d  call    ?GetIssuer@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetIssuer(STRU *)
0x18002c842  mov     ebx, eax
0x18002c844  test    eax, eax
0x18002c846  js      loc_18002CA0E
0x18002c84c  lea     rcx, [rbp+340h+var_390]
0x18002c850  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002c856  mov     rdx, rax
0x18002c859  lea     rcx, [rsp+440h+var_3C8]
0x18002c85e  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18002c864  mov     ebx, eax
0x18002c866  test    eax, eax
0x18002c868  js      loc_18002CA0E
0x18002c86e  mov     rcx, cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; hProv
0x18002c875  lea     rax, [rsp+440h+hHash]
0x18002c87a  xor     r9d, r9d; dwFlags
0x18002c87d  mov     [rsp+440h+phHash], rax; phHash
0x18002c882  xor     r8d, r8d; hKey
0x18002c885  mov     edx, 800Ch; Algid
0x18002c88a  call    cs:__imp_CryptCreateHash
0x18002c890  test    eax, eax
0x18002c892  jnz     short loc_18002C8B2
0x18002c894  call    cs:__imp_GetLastError
0x18002c89a  mov     ebx, eax
0x18002c89c  test    eax, eax
0x18002c89e  jle     loc_18002CA0E
0x18002c8a4  movzx   ebx, ax
0x18002c8a7  or      ebx, 80070000h
0x18002c8ad  jmp     loc_18002CA0E
0x18002c8b2  lea     rcx, [rsp+440h+var_3C8]
0x18002c8b7  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002c8bd  lea     rcx, [rsp+440h+var_3C8]
0x18002c8c2  mov     ebx, eax
0x18002c8c4  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002c8ca  mov     rcx, [rsp+440h+hHash]; hHash
0x18002c8cf  xor     r9d, r9d; dwFlags
0x18002c8d2  mov     rdx, rax; pbData
0x18002c8d5  mov     r8d, ebx; dwDataLen
0x18002c8d8  call    cs:__imp_CryptHashData
0x18002c8de  test    eax, eax
0x18002c8e0  jnz     short loc_18002C907
0x18002c8e2  call    cs:__imp_GetLastError
0x18002c8e8  mov     ebx, eax
0x18002c8ea  test    eax, eax
0x18002c8ec  jle     short loc_18002C8F7
0x18002c8ee  movzx   ebx, ax
0x18002c8f1  or      ebx, 80070000h
0x18002c8f7  mov     rcx, [rsp+440h+hHash]; hHash
0x18002c8fc  call    cs:__imp_CryptDestroyHash
0x18002c902  jmp     loc_18002CA0E
0x18002c907  lea     rbx, [rdi+18h]
0x18002c90b  mov     rcx, rbx
0x18002c90e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002c914  mov     rcx, rbx
0x18002c917  mov     edi, [rax+8]
0x18002c91a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002c920  mov     rcx, [rsp+440h+hHash]; hHash
0x18002c925  xor     r9d, r9d; dwFlags
0x18002c928  mov     r8d, edi; dwDataLen
0x18002c92b  mov     rdx, [rax+10h]; pbData
0x18002c92f  call    cs:__imp_CryptHashData
0x18002c935  test    eax, eax
0x18002c937  jz      short loc_18002C8E2
0x18002c939  lea     rcx, [rsp+440h+var_3F8]
0x18002c93e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002c944  lea     rcx, [rsp+440h+var_3F8]
0x18002c949  mov     [rsp+440h+pdwDataLen], eax
0x18002c94d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002c953  mov     rcx, [rsp+440h+hHash]; hHash
0x18002c958  lea     r9, [rsp+440h+pdwDataLen]; pdwDataLen
0x18002c95d  mov     r8, rax; pbData
0x18002c960  mov     dword ptr [rsp+440h+phHash], 0; dwFlags
0x18002c968  mov     edx, 2; dwParam
0x18002c96d  call    cs:__imp_CryptGetHashParam
0x18002c973  test    eax, eax
0x18002c975  jz      loc_18002C8E2
0x18002c97b  mov     rcx, [rsp+440h+hHash]; hHash
0x18002c980  call    cs:__imp_CryptDestroyHash
0x18002c986  lea     rcx, [rsp+440h+var_3F8]
0x18002c98b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002c991  mov     rsi, rax
0x18002c994  xor     edi, edi
0x18002c996  mov     edx, 30h ; '0'
0x18002c99b  cmp     edi, [rsp+440h+pdwDataLen]
0x18002c99f  jnb     short loc_18002CA0C
0x18002c9a1  mov     cl, [rdi+rsi]
0x18002c9a4  lea     eax, [rdx+27h]
0x18002c9a7  shr     cl, 4
0x18002c9aa  lea     r8d, [rdx-2Fh]
0x18002c9ae  cmp     cl, 9
0x18002c9b1  cmovbe  eax, edx
0x18002c9b4  lea     rdx, [rsp+440h+var_410]
0x18002c9b9  add     al, cl
0x18002c9bb  mov     rcx, r15
0x18002c9be  movzx   eax, al
0x18002c9c1  mov     [rsp+440h+var_410], ax
0x18002c9c6  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18002c9cc  mov     ebx, eax
0x18002c9ce  test    eax, eax
0x18002c9d0  js      short loc_18002CA0E
0x18002c9d2  mov     cl, [rdi+rsi]
0x18002c9d5  mov     eax, 57h ; 'W'
0x18002c9da  and     cl, 0Fh
0x18002c9dd  cmp     cl, 9
0x18002c9e0  lea     edx, [rax-27h]
0x18002c9e3  cmovbe  eax, edx
0x18002c9e6  lea     r8d, [rdx-2Fh]
0x18002c9ea  add     al, cl
0x18002c9ec  lea     rdx, [rsp+440h+var_410]
0x18002c9f1  movzx   eax, al
0x18002c9f4  mov     rcx, r15
0x18002c9f7  mov     [rsp+440h+var_410], ax
0x18002c9fc  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18002ca02  mov     ebx, eax
0x18002ca04  test    eax, eax
0x18002ca06  js      short loc_18002CA0E
0x18002ca08  inc     edi
0x18002ca0a  jmp     short loc_18002C996
0x18002ca0c  xor     ebx, ebx
0x18002ca0e  lea     rcx, [rsp+440h+var_3F8]
0x18002ca13  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002ca19  lea     rcx, [rsp+440h+var_3C8]
0x18002ca1e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002ca24  lea     rcx, [rbp+340h+var_390]
0x18002ca28  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ca2e  mov     eax, ebx
0x18002ca30  mov     rcx, [rbp+340h+var_30]
0x18002ca37  xor     rcx, rsp; StackCookie
0x18002ca3a  call    __security_check_cookie
0x18002ca3f  mov     rbx, [rsp+440h+arg_10]
0x18002ca47  add     rsp, 420h
0x18002ca4e  pop     r15
0x18002ca50  pop     r14
0x18002ca52  pop     rdi
0x18002ca53  pop     rsi
0x18002ca54  pop     rbp
0x18002ca55  retn
```
