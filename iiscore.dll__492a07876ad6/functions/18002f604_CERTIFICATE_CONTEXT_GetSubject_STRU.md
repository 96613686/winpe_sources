# CERTIFICATE_CONTEXT::GetSubject(STRU *)

- ea: `0x18002f604`
- end: `0x18002f78b`
- name: `?GetSubject@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(CERTIFICATE_CONTEXT *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002c3e0`

## callees

- `0x18002ee74`
- `0x18002f604`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002f759`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002f759`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f686`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f6ef`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f701`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f734`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f686`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f6ef`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f701`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002f734`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002f6da`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002f6da`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002f6be`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002f6be`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002f746`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002f746`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002f64c`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002f64c`
- `CRYPT32!CertNameToStrW` at `0x18002f6aa`
- `CRYPT32!CertNameToStrW` at `0x18002f723`
- `CRYPT32!CertNameToStrW` at `0x18002f6aa`
- `CRYPT32!CertNameToStrW` at `0x18002f723`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_CONTEXT::GetSubject(CERTIFICATE_CONTEXT *this, struct STRU *a2)
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
      v7 = CertNameToStrW(0x10001u, Ptr + 5, 3u, 0, 0);
      if ( BUFFER::Resize((BUFFER *)v13, 2 * v7) )
      {
        csz = BUFFER::QuerySize((BUFFER *)v13) >> 1;
        v9 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v13);
        v10 = (struct _CRYPTOAPI_BLOB *)BUFFER::QueryPtr(v5);
        CertNameToStrW(0x10001u, v10 + 5, 3u, v9, csz);
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
0x18002f604  mov     [rsp+arg_10], rbx
0x18002f609  push    rbp
0x18002f60a  push    rsi
0x18002f60b  push    rdi
0x18002f60c  sub     rsp, 170h
0x18002f613  mov     rax, cs:__security_cookie
0x18002f61a  xor     rax, rsp
0x18002f61d  mov     [rsp+188h+var_28], rax
0x18002f625  mov     rsi, rdx
0x18002f628  mov     rdi, rcx
0x18002f62b  mov     ebx, 100h
0x18002f630  lea     rcx, [rsp+188h+var_128]; void *
0x18002f635  mov     r8d, ebx; Size
0x18002f638  xor     edx, edx; Val
0x18002f63a  call    memset_0
0x18002f63f  mov     r8d, ebx
0x18002f642  lea     rdx, [rsp+188h+var_128]
0x18002f647  lea     rcx, [rsp+188h+var_158]
0x18002f64c  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002f653  nop     dword ptr [rax+rax+00h]
0x18002f658  test    rsi, rsi
0x18002f65b  jnz     short loc_18002F667
0x18002f65d  mov     ebx, 80070057h
0x18002f662  jmp     loc_18002F754
0x18002f667  cmp     dword ptr [rdi+10h], 0
0x18002f66b  jnz     short loc_18002F67F
0x18002f66d  mov     rcx, rdi; this
0x18002f670  call    ?DecodeCert@CERTIFICATE_CONTEXT@@AEAAJXZ; CERTIFICATE_CONTEXT::DecodeCert(void)
0x18002f675  mov     ebx, eax
0x18002f677  test    eax, eax
0x18002f679  js      loc_18002F754
0x18002f67f  lea     rbp, [rdi+18h]
0x18002f683  mov     rcx, rbp
0x18002f686  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f68d  nop     dword ptr [rax+rax+00h]
0x18002f692  xor     r9d, r9d; psz
0x18002f695  mov     [rsp+188h+csz], 0; csz
0x18002f69d  mov     ecx, 10001h; dwCertEncodingType
0x18002f6a2  lea     rdx, [rax+50h]; pName
0x18002f6a6  lea     r8d, [r9+3]; dwStrType
0x18002f6aa  call    cs:__imp_CertNameToStrW
0x18002f6b1  nop     dword ptr [rax+rax+00h]
0x18002f6b6  lea     rcx, [rsp+188h+var_158]
0x18002f6bb  lea     edx, [rax+rax]
0x18002f6be  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002f6c5  nop     dword ptr [rax+rax+00h]
0x18002f6ca  test    al, al
0x18002f6cc  jnz     short loc_18002F6D5
0x18002f6ce  mov     ebx, 8007000Eh
0x18002f6d3  jmp     short loc_18002F754
0x18002f6d5  lea     rcx, [rsp+188h+var_158]
0x18002f6da  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002f6e1  nop     dword ptr [rax+rax+00h]
0x18002f6e6  mov     edi, eax
0x18002f6e8  lea     rcx, [rsp+188h+var_158]
0x18002f6ed  shr     edi, 1
0x18002f6ef  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f6f6  nop     dword ptr [rax+rax+00h]
0x18002f6fb  mov     rcx, rbp
0x18002f6fe  mov     rbx, rax
0x18002f701  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f708  nop     dword ptr [rax+rax+00h]
0x18002f70d  mov     r9, rbx; psz
0x18002f710  mov     [rsp+188h+csz], edi; csz
0x18002f714  mov     ecx, 10001h; dwCertEncodingType
0x18002f719  mov     r8d, 3; dwStrType
0x18002f71f  lea     rdx, [rax+50h]; pName
0x18002f723  call    cs:__imp_CertNameToStrW
0x18002f72a  nop     dword ptr [rax+rax+00h]
0x18002f72f  lea     rcx, [rsp+188h+var_158]
0x18002f734  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002f73b  nop     dword ptr [rax+rax+00h]
0x18002f740  mov     rdx, rax
0x18002f743  mov     rcx, rsi
0x18002f746  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002f74d  nop     dword ptr [rax+rax+00h]
0x18002f752  mov     ebx, eax
0x18002f754  lea     rcx, [rsp+188h+var_158]
0x18002f759  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002f760  nop     dword ptr [rax+rax+00h]
0x18002f765  mov     eax, ebx
0x18002f767  mov     rcx, [rsp+188h+var_28]
0x18002f76f  xor     rcx, rsp; StackCookie
0x18002f772  call    __security_check_cookie
0x18002f777  mov     rbx, [rsp+188h+arg_10]
0x18002f77f  add     rsp, 170h
0x18002f786  pop     rdi
0x18002f787  pop     rsi
0x18002f788  pop     rbp
0x18002f789  retn
```
