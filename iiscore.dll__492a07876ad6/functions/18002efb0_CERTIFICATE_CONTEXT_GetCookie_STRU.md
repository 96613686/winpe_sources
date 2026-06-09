# CERTIFICATE_CONTEXT::GetCookie(STRU *)

- ea: `0x18002efb0`
- end: `0x18002f338`
- name: `?GetCookie@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z`
- size: `904`
- prototype: `__int64 __fastcall(CERTIFICATE_CONTEXT *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002bfd0`

## callees

- `0x18002ee74`
- `0x18002efb0`
- `0x18002f340`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f166`
- `CRYPTSP!CryptDestroyHash` at `0x18002f186`
- `CRYPTSP!CryptDestroyHash` at `0x18002f234`
- `CRYPTSP!CryptDestroyHash` at `0x18002f186`
- `CRYPTSP!CryptDestroyHash` at `0x18002f234`
- `CRYPTSP!CryptGetHashParam` at `0x18002f21b`
- `CRYPTSP!CryptGetHashParam` at `0x18002f21b`
- `CRYPTSP!CryptCreateHash` at `0x18002f0f0`
- `CRYPTSP!CryptCreateHash` at `0x18002f0f0`
- `CRYPTSP!CryptHashData` at `0x18002f156`
- `CRYPTSP!CryptHashData` at `0x18002f1cb`
- `CRYPTSP!CryptHashData` at `0x18002f156`
- `CRYPTSP!CryptHashData` at `0x18002f1cb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002f2e2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002f2e2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f303`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002f303`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f19e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f1b0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f1f5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f245`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f19e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f1b0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f1f5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f245`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002f1e0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002f1e0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002f0aa`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002f0aa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002f012`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002f012`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002f050`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002f050`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002f02a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002f02a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002f2f3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002f2f3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002f13c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002f13c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002f286`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002f2c2`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002f286`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18002f2c2`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002f129`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002f129`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18002f0be`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18002f0be`

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
0x18002efb0  mov     [rsp-8+arg_10], rbx
0x18002efb5  push    rbp
0x18002efb6  push    rsi
0x18002efb7  push    rdi
0x18002efb8  push    r14
0x18002efba  push    r15
0x18002efbc  lea     rbp, [rsp-320h]
0x18002efc4  sub     rsp, 420h
0x18002efcb  mov     rax, cs:__security_cookie
0x18002efd2  xor     rax, rsp
0x18002efd5  mov     [rbp+340h+var_30], rax
0x18002efdc  mov     r15, rdx
0x18002efdf  mov     [rsp+440h+hHash], 0
0x18002efe8  mov     rdi, rcx
0x18002efeb  xor     edx, edx; Val
0x18002efed  lea     rcx, [rbp+340h+var_230]; void *
0x18002eff4  mov     r8d, 200h; Size
0x18002effa  call    memset_0
0x18002efff  mov     ebx, 100h
0x18002f004  lea     rdx, [rbp+340h+var_230]
0x18002f00b  mov     r8d, ebx
0x18002f00e  lea     rcx, [rbp+340h+var_390]
0x18002f012  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002f019  nop     dword ptr [rax+rax+00h]
0x18002f01e  mov     r8d, ebx
0x18002f021  lea     rdx, [rbp+340h+var_330]
0x18002f025  lea     rcx, [rsp+440h+var_3C8]
0x18002f02a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002f031  nop     dword ptr [rax+rax+00h]
0x18002f036  xorps   xmm0, xmm0
0x18002f039  lea     rdx, [rbp+340h+var_358]
0x18002f03d  mov     r8d, 20h ; ' '
0x18002f043  lea     rcx, [rsp+440h+var_3F8]
0x18002f048  movups  [rbp+340h+var_358], xmm0
0x18002f04c  movups  [rbp+340h+var_348], xmm0
0x18002f050  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002f057  nop     dword ptr [rax+rax+00h]
0x18002f05c  xor     eax, eax
0x18002f05e  mov     [rsp+440h+pdwDataLen], 0
0x18002f066  mov     dword ptr [rsp+440h+var_410], eax
0x18002f06a  test    r15, r15
0x18002f06d  jnz     short loc_18002F079
0x18002f06f  mov     ebx, 80070057h
0x18002f074  jmp     loc_18002F2DD
0x18002f079  cmp     [rdi+10h], eax
0x18002f07c  jnz     short loc_18002F090
0x18002f07e  mov     rcx, rdi; this
0x18002f081  call    ?DecodeCert@CERTIFICATE_CONTEXT@@AEAAJXZ; CERTIFICATE_CONTEXT::DecodeCert(void)
0x18002f086  mov     ebx, eax
0x18002f088  test    eax, eax
0x18002f08a  js      loc_18002F2DD
0x18002f090  lea     rdx, [rbp+340h+var_390]; struct STRU *
0x18002f094  mov     rcx, rdi; this
0x18002f097  call    ?GetIssuer@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z; CERTIFICATE_CONTEXT::GetIssuer(STRU *)
0x18002f09c  mov     ebx, eax
0x18002f09e  test    eax, eax
0x18002f0a0  js      loc_18002F2DD
0x18002f0a6  lea     rcx, [rbp+340h+var_390]
0x18002f0aa  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002f0b1  nop     dword ptr [rax+rax+00h]
0x18002f0b6  mov     rdx, rax
0x18002f0b9  lea     rcx, [rsp+440h+var_3C8]
0x18002f0be  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18002f0c5  nop     dword ptr [rax+rax+00h]
0x18002f0ca  mov     ebx, eax
0x18002f0cc  test    eax, eax
0x18002f0ce  js      loc_18002F2DD
0x18002f0d4  mov     rcx, cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; hProv
0x18002f0db  lea     rax, [rsp+440h+hHash]
0x18002f0e0  xor     r9d, r9d; dwFlags
0x18002f0e3  mov     [rsp+440h+phHash], rax; phHash
0x18002f0e8  xor     r8d, r8d; hKey
0x18002f0eb  mov     edx, 800Ch; Algid
0x18002f0f0  call    cs:__imp_CryptCreateHash
0x18002f0f7  nop     dword ptr [rax+rax+00h]
0x18002f0fc  test    eax, eax
0x18002f0fe  jnz     short loc_18002F124
0x18002f100  call    cs:__imp_GetLastError
0x18002f107  nop     dword ptr [rax+rax+00h]
0x18002f10c  mov     ebx, eax
0x18002f10e  test    eax, eax
0x18002f110  jle     loc_18002F2DD
0x18002f116  movzx   ebx, ax
0x18002f119  or      ebx, 80070000h
0x18002f11f  jmp     loc_18002F2DD
0x18002f124  lea     rcx, [rsp+440h+var_3C8]
0x18002f129  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002f130  nop     dword ptr [rax+rax+00h]
0x18002f135  lea     rcx, [rsp+440h+var_3C8]
0x18002f13a  mov     ebx, eax
0x18002f13c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002f143  nop     dword ptr [rax+rax+00h]
0x18002f148  mov     rcx, [rsp+440h+hHash]; hHash
0x18002f14d  xor     r9d, r9d; dwFlags
0x18002f150  mov     rdx, rax; pbData
0x18002f153  mov     r8d, ebx; dwDataLen
0x18002f156  call    cs:__imp_CryptHashData
0x18002f15d  nop     dword ptr [rax+rax+00h]
0x18002f162  test    eax, eax
0x18002f164  jnz     short loc_18002F197
0x18002f166  call    cs:__imp_GetLastError
0x18002f16d  nop     dword ptr [rax+rax+00h]
0x18002f172  mov     ebx, eax
0x18002f174  test    eax, eax
0x18002f176  jle     short loc_18002F181
0x18002f178  movzx   ebx, ax
0x18002f17b  or      ebx, 80070000h
0x18002f181  mov     rcx, [rsp+440h+hHash]; hHash
0x18002f186  call    cs:__imp_CryptDestroyHash
0x18002f18d  nop     dword ptr [rax+rax+00h]
0x18002f192  jmp     loc_18002F2DD
0x18002f197  lea     rbx, [rdi+18h]
0x18002f19b  mov     rcx, rbx
0x18002f19e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f1a5  nop     dword ptr [rax+rax+00h]
0x18002f1aa  mov     rcx, rbx
0x18002f1ad  mov     edi, [rax+8]
0x18002f1b0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f1b7  nop     dword ptr [rax+rax+00h]
0x18002f1bc  mov     rcx, [rsp+440h+hHash]; hHash
0x18002f1c1  xor     r9d, r9d; dwFlags
0x18002f1c4  mov     r8d, edi; dwDataLen
0x18002f1c7  mov     rdx, [rax+10h]; pbData
0x18002f1cb  call    cs:__imp_CryptHashData
0x18002f1d2  nop     dword ptr [rax+rax+00h]
0x18002f1d7  test    eax, eax
0x18002f1d9  jz      short loc_18002F166
0x18002f1db  lea     rcx, [rsp+440h+var_3F8]
0x18002f1e0  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002f1e7  nop     dword ptr [rax+rax+00h]
0x18002f1ec  lea     rcx, [rsp+440h+var_3F8]
0x18002f1f1  mov     [rsp+440h+pdwDataLen], eax
0x18002f1f5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f1fc  nop     dword ptr [rax+rax+00h]
0x18002f201  mov     rcx, [rsp+440h+hHash]; hHash
0x18002f206  lea     r9, [rsp+440h+pdwDataLen]; pdwDataLen
0x18002f20b  mov     r8, rax; pbData
0x18002f20e  mov     dword ptr [rsp+440h+phHash], 0; dwFlags
0x18002f216  mov     edx, 2; dwParam
0x18002f21b  call    cs:__imp_CryptGetHashParam
0x18002f222  nop     dword ptr [rax+rax+00h]
0x18002f227  test    eax, eax
0x18002f229  jz      loc_18002F166
0x18002f22f  mov     rcx, [rsp+440h+hHash]; hHash
0x18002f234  call    cs:__imp_CryptDestroyHash
0x18002f23b  nop     dword ptr [rax+rax+00h]
0x18002f240  lea     rcx, [rsp+440h+var_3F8]
0x18002f245  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f24c  nop     dword ptr [rax+rax+00h]
0x18002f251  mov     rsi, rax
0x18002f254  xor     edi, edi
0x18002f256  mov     edx, 30h ; '0'
0x18002f25b  cmp     edi, [rsp+440h+pdwDataLen]
0x18002f25f  jnb     short loc_18002F2DB
0x18002f261  mov     cl, [rdi+rsi]
0x18002f264  lea     eax, [rdx+27h]
0x18002f267  shr     cl, 4
0x18002f26a  lea     r8d, [rdx-2Fh]
0x18002f26e  cmp     cl, 9
0x18002f271  cmovbe  eax, edx
0x18002f274  lea     rdx, [rsp+440h+var_410]
0x18002f279  add     al, cl
0x18002f27b  mov     rcx, r15
0x18002f27e  movzx   eax, al
0x18002f281  mov     [rsp+440h+var_410], ax
0x18002f286  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18002f28d  nop     dword ptr [rax+rax+00h]
0x18002f292  mov     ebx, eax
0x18002f294  test    eax, eax
0x18002f296  js      short loc_18002F2DD
0x18002f298  mov     cl, [rdi+rsi]
0x18002f29b  mov     eax, 57h ; 'W'
0x18002f2a0  and     cl, 0Fh
0x18002f2a3  cmp     cl, 9
0x18002f2a6  lea     edx, [rax-27h]
0x18002f2a9  cmovbe  eax, edx
0x18002f2ac  lea     r8d, [rdx-2Fh]
0x18002f2b0  add     al, cl
0x18002f2b2  lea     rdx, [rsp+440h+var_410]
0x18002f2b7  movzx   eax, al
0x18002f2ba  mov     rcx, r15
0x18002f2bd  mov     [rsp+440h+var_410], ax
0x18002f2c2  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18002f2c9  nop     dword ptr [rax+rax+00h]
0x18002f2ce  mov     ebx, eax
0x18002f2d0  test    eax, eax
0x18002f2d2  js      short loc_18002F2DD
0x18002f2d4  inc     edi
0x18002f2d6  jmp     loc_18002F256
0x18002f2db  xor     ebx, ebx
0x18002f2dd  lea     rcx, [rsp+440h+var_3F8]
0x18002f2e2  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002f2e9  nop     dword ptr [rax+rax+00h]
0x18002f2ee  lea     rcx, [rsp+440h+var_3C8]
0x18002f2f3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002f2fa  nop     dword ptr [rax+rax+00h]
0x18002f2ff  lea     rcx, [rbp+340h+var_390]
0x18002f303  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002f30a  nop     dword ptr [rax+rax+00h]
0x18002f30f  mov     eax, ebx
0x18002f311  mov     rcx, [rbp+340h+var_30]
0x18002f318  xor     rcx, rsp; StackCookie
0x18002f31b  call    __security_check_cookie
0x18002f320  mov     rbx, [rsp+440h+arg_10]
0x18002f328  add     rsp, 420h
0x18002f32f  pop     r15
0x18002f331  pop     r14
0x18002f333  pop     rdi
0x18002f334  pop     rsi
0x18002f335  pop     rbp
0x18002f336  retn
```
