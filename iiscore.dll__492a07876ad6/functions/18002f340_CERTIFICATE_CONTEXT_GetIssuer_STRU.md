# CERTIFICATE_CONTEXT::GetIssuer(STRU *)

- ea: `0x18002f340`
- end: `0x18002f4c7`
- name: `?GetIssuer@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(CERTIFICATE_CONTEXT *__hidden this, struct STRU *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002c180`
- `0x18002efb0`

## callees

- `0x18002ee74`
- `0x18002f340`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002f495`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002f495`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f3c2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f42b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f43d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f470`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f3c2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f42b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f43d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f470`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002f416`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002f416`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002f3fa`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002f3fa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002f482`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002f482`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002f388`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002f388`
- `CRYPT32!CertNameToStrW` at `0x18002f3e6`
- `CRYPT32!CertNameToStrW` at `0x18002f45f`
- `CRYPT32!CertNameToStrW` at `0x18002f3e6`
- `CRYPT32!CertNameToStrW` at `0x18002f45f`

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
0x18002f340  mov     [rsp+arg_10], rbx
0x18002f345  push    rbp
0x18002f346  push    rsi
0x18002f347  push    rdi
0x18002f348  sub     rsp, 170h
0x18002f34f  mov     rax, cs:__security_cookie
0x18002f356  xor     rax, rsp
0x18002f359  mov     [rsp+188h+var_28], rax
0x18002f361  mov     rsi, rdx
0x18002f364  mov     rdi, rcx
0x18002f367  mov     ebx, 100h
0x18002f36c  lea     rcx, [rsp+188h+var_128]; void *
0x18002f371  mov     r8d, ebx; Size
0x18002f374  xor     edx, edx; Val
0x18002f376  call    memset_0
0x18002f37b  mov     r8d, ebx
0x18002f37e  lea     rdx, [rsp+188h+var_128]
0x18002f383  lea     rcx, [rsp+188h+var_158]
0x18002f388  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002f38f  nop     dword ptr [rax+rax+00h]
0x18002f394  test    rsi, rsi
0x18002f397  jnz     short loc_18002F3A3
0x18002f399  mov     ebx, 80070057h
0x18002f39e  jmp     loc_18002F490
0x18002f3a3  cmp     dword ptr [rdi+10h], 0
0x18002f3a7  jnz     short loc_18002F3BB
0x18002f3a9  mov     rcx, rdi; this
0x18002f3ac  call    ?DecodeCert@CERTIFICATE_CONTEXT@@AEAAJXZ; CERTIFICATE_CONTEXT::DecodeCert(void)
0x18002f3b1  mov     ebx, eax
0x18002f3b3  test    eax, eax
0x18002f3b5  js      loc_18002F490
0x18002f3bb  lea     rbp, [rdi+18h]
0x18002f3bf  mov     rcx, rbp
0x18002f3c2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f3c9  nop     dword ptr [rax+rax+00h]
0x18002f3ce  xor     r9d, r9d; psz
0x18002f3d1  mov     [rsp+188h+csz], 0; csz
0x18002f3d9  mov     ecx, 10001h; dwCertEncodingType
0x18002f3de  lea     rdx, [rax+30h]; pName
0x18002f3e2  lea     r8d, [r9+3]; dwStrType
0x18002f3e6  call    cs:__imp_CertNameToStrW
0x18002f3ed  nop     dword ptr [rax+rax+00h]
0x18002f3f2  lea     rcx, [rsp+188h+var_158]
0x18002f3f7  lea     edx, [rax+rax]
0x18002f3fa  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002f401  nop     dword ptr [rax+rax+00h]
0x18002f406  test    al, al
0x18002f408  jnz     short loc_18002F411
0x18002f40a  mov     ebx, 8007000Eh
0x18002f40f  jmp     short loc_18002F490
0x18002f411  lea     rcx, [rsp+188h+var_158]
0x18002f416  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002f41d  nop     dword ptr [rax+rax+00h]
0x18002f422  mov     edi, eax
0x18002f424  lea     rcx, [rsp+188h+var_158]
0x18002f429  shr     edi, 1
0x18002f42b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f432  nop     dword ptr [rax+rax+00h]
0x18002f437  mov     rcx, rbp
0x18002f43a  mov     rbx, rax
0x18002f43d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f444  nop     dword ptr [rax+rax+00h]
0x18002f449  mov     r9, rbx; psz
0x18002f44c  mov     [rsp+188h+csz], edi; csz
0x18002f450  mov     ecx, 10001h; dwCertEncodingType
0x18002f455  mov     r8d, 3; dwStrType
0x18002f45b  lea     rdx, [rax+30h]; pName
0x18002f45f  call    cs:__imp_CertNameToStrW
0x18002f466  nop     dword ptr [rax+rax+00h]
0x18002f46b  lea     rcx, [rsp+188h+var_158]
0x18002f470  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f477  nop     dword ptr [rax+rax+00h]
0x18002f47c  mov     rdx, rax
0x18002f47f  mov     rcx, rsi
0x18002f482  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002f489  nop     dword ptr [rax+rax+00h]
0x18002f48e  mov     ebx, eax
0x18002f490  lea     rcx, [rsp+188h+var_158]
0x18002f495  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002f49c  nop     dword ptr [rax+rax+00h]
0x18002f4a1  mov     eax, ebx
0x18002f4a3  mov     rcx, [rsp+188h+var_28]
0x18002f4ab  xor     rcx, rsp; StackCookie
0x18002f4ae  call    __security_check_cookie
0x18002f4b3  mov     rbx, [rsp+188h+arg_10]
0x18002f4bb  add     rsp, 170h
0x18002f4c2  pop     rdi
0x18002f4c3  pop     rsi
0x18002f4c4  pop     rbp
0x18002f4c5  retn
```
