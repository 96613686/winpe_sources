# CERTIFICATE_CONTEXT::GetSubject(STRU *)

- ea: `0x18002ccc0`
- end: `0x18002ce04`
- name: `?GetSubject@CERTIFICATE_CONTEXT@@QEAAJPEAVSTRU@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(CERTIFICATE_CONTEXT *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180029e90`

## callees

- `0x18002c664`
- `0x18002ccc0`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002cdd9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002cdd9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cd3c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cd8d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cd99`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cdc0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cd3c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cd8d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cd99`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002cdc0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002cd7e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002cd7e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002cd68`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002cd68`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002cdcc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002cdcc`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002cd08`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002cd08`
- `CRYPT32!CertNameToStrW` at `0x18002cd5a`
- `CRYPT32!CertNameToStrW` at `0x18002cdb5`
- `CRYPT32!CertNameToStrW` at `0x18002cd5a`
- `CRYPT32!CertNameToStrW` at `0x18002cdb5`

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
0x18002ccc0  mov     [rsp+arg_10], rbx
0x18002ccc5  push    rbp
0x18002ccc6  push    rsi
0x18002ccc7  push    rdi
0x18002ccc8  sub     rsp, 170h
0x18002cccf  mov     rax, cs:__security_cookie
0x18002ccd6  xor     rax, rsp
0x18002ccd9  mov     [rsp+188h+var_28], rax
0x18002cce1  mov     rsi, rdx
0x18002cce4  mov     rdi, rcx
0x18002cce7  mov     ebx, 100h
0x18002ccec  lea     rcx, [rsp+188h+var_128]; void *
0x18002ccf1  mov     r8d, ebx; Size
0x18002ccf4  xor     edx, edx; Val
0x18002ccf6  call    memset_0
0x18002ccfb  mov     r8d, ebx
0x18002ccfe  lea     rdx, [rsp+188h+var_128]
0x18002cd03  lea     rcx, [rsp+188h+var_158]
0x18002cd08  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002cd0e  test    rsi, rsi
0x18002cd11  jnz     short loc_18002CD1D
0x18002cd13  mov     ebx, 80070057h
0x18002cd18  jmp     loc_18002CDD4
0x18002cd1d  cmp     dword ptr [rdi+10h], 0
0x18002cd21  jnz     short loc_18002CD35
0x18002cd23  mov     rcx, rdi; this
0x18002cd26  call    ?DecodeCert@CERTIFICATE_CONTEXT@@AEAAJXZ; CERTIFICATE_CONTEXT::DecodeCert(void)
0x18002cd2b  mov     ebx, eax
0x18002cd2d  test    eax, eax
0x18002cd2f  js      loc_18002CDD4
0x18002cd35  lea     rbp, [rdi+18h]
0x18002cd39  mov     rcx, rbp
0x18002cd3c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cd42  xor     r9d, r9d; psz
0x18002cd45  mov     [rsp+188h+csz], 0; csz
0x18002cd4d  mov     ecx, 10001h; dwCertEncodingType
0x18002cd52  lea     rdx, [rax+50h]; pName
0x18002cd56  lea     r8d, [r9+3]; dwStrType
0x18002cd5a  call    cs:__imp_CertNameToStrW
0x18002cd60  lea     rcx, [rsp+188h+var_158]
0x18002cd65  lea     edx, [rax+rax]
0x18002cd68  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002cd6e  test    al, al
0x18002cd70  jnz     short loc_18002CD79
0x18002cd72  mov     ebx, 8007000Eh
0x18002cd77  jmp     short loc_18002CDD4
0x18002cd79  lea     rcx, [rsp+188h+var_158]
0x18002cd7e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002cd84  mov     edi, eax
0x18002cd86  lea     rcx, [rsp+188h+var_158]
0x18002cd8b  shr     edi, 1
0x18002cd8d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cd93  mov     rcx, rbp
0x18002cd96  mov     rbx, rax
0x18002cd99  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cd9f  mov     r9, rbx; psz
0x18002cda2  mov     [rsp+188h+csz], edi; csz
0x18002cda6  mov     ecx, 10001h; dwCertEncodingType
0x18002cdab  mov     r8d, 3; dwStrType
0x18002cdb1  lea     rdx, [rax+50h]; pName
0x18002cdb5  call    cs:__imp_CertNameToStrW
0x18002cdbb  lea     rcx, [rsp+188h+var_158]
0x18002cdc0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002cdc6  mov     rdx, rax
0x18002cdc9  mov     rcx, rsi
0x18002cdcc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002cdd2  mov     ebx, eax
0x18002cdd4  lea     rcx, [rsp+188h+var_158]
0x18002cdd9  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002cddf  mov     eax, ebx
0x18002cde1  mov     rcx, [rsp+188h+var_28]
0x18002cde9  xor     rcx, rsp; StackCookie
0x18002cdec  call    __security_check_cookie
0x18002cdf1  mov     rbx, [rsp+188h+arg_10]
0x18002cdf9  add     rsp, 170h
0x18002ce00  pop     rdi
0x18002ce01  pop     rsi
0x18002ce02  pop     rbp
0x18002ce03  retn
```
