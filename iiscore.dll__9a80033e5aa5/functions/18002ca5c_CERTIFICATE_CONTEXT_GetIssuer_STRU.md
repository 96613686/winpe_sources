# CERTIFICATE_CONTEXT::GetIssuer(STRU *)

- ea: `0x18002ca5c`
- end: `0x18002cba0`
- name: `?GetIssuer@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(CERTIFICATE_CONTEXT *__hidden this, struct STRU *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180029c70`
- `0x18002c768`

## callees

- `0x18002c664`
- `0x18002ca5c`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002cb75`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002cb75`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cad8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cb29`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cb35`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cb5c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cad8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cb29`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cb35`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cb5c`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002cb1a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002cb1a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002cb04`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002cb04`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002cb68`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002cb68`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002caa4`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002caa4`
- `CRYPT32!CertNameToStrW` at `0x18002caf6`
- `CRYPT32!CertNameToStrW` at `0x18002cb51`
- `CRYPT32!CertNameToStrW` at `0x18002caf6`
- `CRYPT32!CertNameToStrW` at `0x18002cb51`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_CONTEXT::GetIssuer(CERTIFICATE_CONTEXT *this, struct STRU *a2)
{
  int v4; // ebx
  BUFFER *v5; // rbp
  struct _CRYPTOAPI_BLOB *Ptr; // rax
  DWORD v7; // eax
  DWORD csz; // edi
  WCHAR *v9; // rbx
  struct _CRYPTOAPI_BLOB *v10; // rax
  const unsigned __int16 *v11; // rax
  _BYTE v13[48]; // [rsp+30h] [rbp-158h] BYREF
  unsigned __int8 v14[256]; // [rsp+60h] [rbp-128h] BYREF

  memset_0(v14, 0, sizeof(v14));
  BUFFER::BUFFER((BUFFER *)v13, v14, 0x100u);
  if ( a2 )
  {
    if ( *((_DWORD *)this + 4) || (v4 = CERTIFICATE_CONTEXT::DecodeCert(this), v4 >= 0) )
    {
      v5 = (CERTIFICATE_CONTEXT *)((char *)this + 24);
      Ptr = (struct _CRYPTOAPI_BLOB *)BUFFER::QueryPtr((CERTIFICATE_CONTEXT *)((char *)this + 24));
      v7 = CertNameToStrW(0x10001u, Ptr + 3, 3u, 0, 0);
      if ( BUFFER::Resize((BUFFER *)v13, 2 * v7) )
      {
        csz = BUFFER::QuerySize((BUFFER *)v13) >> 1;
        v9 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v13);
        v10 = (struct _CRYPTOAPI_BLOB *)BUFFER::QueryPtr(v5);
        CertNameToStrW(0x10001u, v10 + 3, 3u, v9, csz);
        v11 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v13);
        v4 = STRU::Copy(a2, v11);
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002ca5c  mov     [rsp+arg_10], rbx
0x18002ca61  push    rbp
0x18002ca62  push    rsi
0x18002ca63  push    rdi
0x18002ca64  sub     rsp, 170h
0x18002ca6b  mov     rax, cs:__security_cookie
0x18002ca72  xor     rax, rsp
0x18002ca75  mov     [rsp+188h+var_28], rax
0x18002ca7d  mov     rsi, rdx
0x18002ca80  mov     rdi, rcx
0x18002ca83  mov     ebx, 100h
0x18002ca88  lea     rcx, [rsp+188h+var_128]; void *
0x18002ca8d  mov     r8d, ebx; Size
0x18002ca90  xor     edx, edx; Val
0x18002ca92  call    memset_0
0x18002ca97  mov     r8d, ebx
0x18002ca9a  lea     rdx, [rsp+188h+var_128]
0x18002ca9f  lea     rcx, [rsp+188h+var_158]
0x18002caa4  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002caaa  test    rsi, rsi
0x18002caad  jnz     short loc_18002CAB9
0x18002caaf  mov     ebx, 80070057h
0x18002cab4  jmp     loc_18002CB70
0x18002cab9  cmp     dword ptr [rdi+10h], 0
0x18002cabd  jnz     short loc_18002CAD1
0x18002cabf  mov     rcx, rdi; this
0x18002cac2  call    ?DecodeCert@CERTIFICATE_CONTEXT@@AEAAJXZ; CERTIFICATE_CONTEXT::DecodeCert(void)
0x18002cac7  mov     ebx, eax
0x18002cac9  test    eax, eax
0x18002cacb  js      loc_18002CB70
0x18002cad1  lea     rbp, [rdi+18h]
0x18002cad5  mov     rcx, rbp
0x18002cad8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cade  xor     r9d, r9d; psz
0x18002cae1  mov     [rsp+188h+csz], 0; csz
0x18002cae9  mov     ecx, 10001h; dwCertEncodingType
0x18002caee  lea     rdx, [rax+30h]; pName
0x18002caf2  lea     r8d, [r9+3]; dwStrType
0x18002caf6  call    cs:__imp_CertNameToStrW
0x18002cafc  lea     rcx, [rsp+188h+var_158]
0x18002cb01  lea     edx, [rax+rax]
0x18002cb04  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002cb0a  test    al, al
0x18002cb0c  jnz     short loc_18002CB15
0x18002cb0e  mov     ebx, 8007000Eh
0x18002cb13  jmp     short loc_18002CB70
0x18002cb15  lea     rcx, [rsp+188h+var_158]
0x18002cb1a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002cb20  mov     edi, eax
0x18002cb22  lea     rcx, [rsp+188h+var_158]
0x18002cb27  shr     edi, 1
0x18002cb29  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cb2f  mov     rcx, rbp
0x18002cb32  mov     rbx, rax
0x18002cb35  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cb3b  mov     r9, rbx; psz
0x18002cb3e  mov     [rsp+188h+csz], edi; csz
0x18002cb42  mov     ecx, 10001h; dwCertEncodingType
0x18002cb47  mov     r8d, 3; dwStrType
0x18002cb4d  lea     rdx, [rax+30h]; pName
0x18002cb51  call    cs:__imp_CertNameToStrW
0x18002cb57  lea     rcx, [rsp+188h+var_158]
0x18002cb5c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cb62  mov     rdx, rax
0x18002cb65  mov     rcx, rsi
0x18002cb68  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002cb6e  mov     ebx, eax
0x18002cb70  lea     rcx, [rsp+188h+var_158]
0x18002cb75  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002cb7b  mov     eax, ebx
0x18002cb7d  mov     rcx, [rsp+188h+var_28]
0x18002cb85  xor     rcx, rsp; StackCookie
0x18002cb88  call    __security_check_cookie
0x18002cb8d  mov     rbx, [rsp+188h+arg_10]
0x18002cb95  add     rsp, 170h
0x18002cb9c  pop     rdi
0x18002cb9d  pop     rsi
0x18002cb9e  pop     rbp
0x18002cb9f  retn
```
