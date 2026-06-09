# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x180010cd4`
- end: `0x180010f98`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `708`
- prototype: `int(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800117cc`

## callees

- `0x180010cd4`
- `0x1800124c0`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180010d53`
- `msvcrt!wcspbrk` at `0x180010d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eaa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010db1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010dbe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010e4c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010e59`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010ec2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010db1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010dbe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010e4c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010e59`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010ec2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f33`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f3d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f4b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f55`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f63`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f6d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f33`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f3d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f4b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f55`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f63`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010f6d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010ed1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010efb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010f23`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010ed1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010efb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010f23`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010d95`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010da2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010e30`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010e3d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010d95`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010da2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010e30`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180010e3d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180010e0b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180010e22`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180010e0b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180010e22`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180010d13`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180010d1d`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180010d13`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180010d1d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180010f06`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180010f06`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180010de7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180010e82`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180010de7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180010e82`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::DetermineUserAndDomain(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct STRU *a4,
        struct STRU *a5,
        int *a6)
{
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  unsigned __int16 v12; // ax
  WCHAR *ReferencedDomainName; // rbx
  void *Ptr; // rax
  WCHAR *v15; // rbx
  void *v16; // rax
  signed int v17; // eax
  unsigned int v18; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v20; // rbx
  int v21; // eax
  __int64 v22; // r8
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-79h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-75h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v27[48]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v28[48]; // [rsp+80h] [rbp-39h] BYREF

  BUFFER::BUFFER((BUFFER *)v28);
  BUFFER::BUFFER((BUFFER *)v27);
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( a4 && a5 && a6 )
  {
    v10 = wcspbrk(a2, L"/\\");
    v11 = v10;
    if ( v10 )
    {
      v22 = v10 - a2;
      if ( (_DWORD)v22 )
        LastError = STRU::Copy(a5, a2, v22);
      else
        LastError = STRU::Copy(a5, L".");
      if ( LastError < 0 )
        goto LABEL_28;
      v20 = v11 + 1;
      v21 = 1;
    }
    else
    {
      if ( !a3 || (v12 = *a3) == 0 )
      {
        v12 = *(_WORD *)this;
        a3 = (unsigned __int16 *)this;
      }
      if ( v12 == 92 && !a3[1] )
      {
        cbSid = BUFFER::QuerySize((BUFFER *)v28);
        cchReferencedDomainName = BUFFER::QuerySize((BUFFER *)v27) >> 1;
        ReferencedDomainName = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v27);
        Ptr = BUFFER::QueryPtr((BUFFER *)v28);
        if ( !LookupAccountNameW(0, a2, Ptr, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          if ( GetLastError() != 122
            || !BUFFER::Resize((BUFFER *)v28, cbSid)
            || !BUFFER::Resize((BUFFER *)v27, 2 * cchReferencedDomainName) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_28;
          }
          cbSid = BUFFER::QuerySize((BUFFER *)v28);
          cchReferencedDomainName = BUFFER::QuerySize((BUFFER *)v27) >> 1;
          v15 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v27);
          v16 = BUFFER::QueryPtr((BUFFER *)v28);
          if ( !LookupAccountNameW(0, a2, v16, &cbSid, v15, &cchReferencedDomainName, &peUse) )
          {
            v17 = GetLastError();
            v18 = v17;
            if ( v17 > 0 )
              v18 = (unsigned __int16)v17 | 0x80070000;
            goto LABEL_29;
          }
        }
        a3 = (unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v27);
      }
      LastError = STRU::Copy(a5, a3);
      if ( LastError < 0 )
      {
LABEL_28:
        v18 = LastError;
LABEL_29:
        BUFFER::~BUFFER((BUFFER *)v27);
        BUFFER::~BUFFER((BUFFER *)v28);
        return v18;
      }
      v20 = a2;
      v21 = 0;
    }
    *a6 = v21;
    LastError = STRU::Copy(a4, v20);
    if ( LastError < 0 )
      goto LABEL_28;
    BUFFER::~BUFFER((BUFFER *)v27);
    BUFFER::~BUFFER((BUFFER *)v28);
    return 0;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v27);
    BUFFER::~BUFFER((BUFFER *)v28);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180010cd4  push    rbp
0x180010cd6  push    rbx
0x180010cd7  push    rsi
0x180010cd8  push    rdi
0x180010cd9  push    r12
0x180010cdb  push    r13
0x180010cdd  push    r14
0x180010cdf  push    r15
0x180010ce1  lea     rbp, [rsp-0Fh]
0x180010ce6  sub     rsp, 0C8h
0x180010ced  mov     rax, cs:__security_cookie
0x180010cf4  xor     rax, rsp
0x180010cf7  mov     [rbp+47h+var_50], rax
0x180010cfb  mov     r14, [rbp+47h+arg_20]
0x180010cff  mov     r15, rcx
0x180010d02  mov     r12, [rbp+47h+arg_28]
0x180010d06  lea     rcx, [rbp+47h+var_80]
0x180010d0a  mov     r13, r9
0x180010d0d  mov     rdi, r8
0x180010d10  mov     rsi, rdx
0x180010d13  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180010d19  lea     rcx, [rbp+47h+var_B0]
0x180010d1d  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180010d23  xor     eax, eax
0x180010d25  mov     [rbp+47h+cbSid], eax
0x180010d28  mov     [rbp+47h+var_C0], eax
0x180010d2b  mov     [rbp+47h+var_B8], eax
0x180010d2e  test    r13, r13
0x180010d31  jz      loc_180010F5F
0x180010d37  test    r14, r14
0x180010d3a  jz      loc_180010F5F
0x180010d40  test    r12, r12
0x180010d43  jz      loc_180010F5F
0x180010d49  lea     rdx, asc_18001C514; "/\\"
0x180010d50  mov     rcx, rsi; String
0x180010d53  call    cs:__imp_wcspbrk
0x180010d59  mov     rbx, rax
0x180010d5c  test    rax, rax
0x180010d5f  jnz     loc_180010EE3
0x180010d65  test    rdi, rdi
0x180010d68  jz      short loc_180010D72
0x180010d6a  movzx   eax, word ptr [rdi]
0x180010d6d  test    ax, ax
0x180010d70  jnz     short loc_180010D79
0x180010d72  movzx   eax, word ptr [r15]
0x180010d76  mov     rdi, r15
0x180010d79  xor     r15d, r15d
0x180010d7c  cmp     ax, 5Ch ; '\'
0x180010d80  jnz     loc_180010ECB
0x180010d86  cmp     [rdi+2], r15w
0x180010d8b  jnz     loc_180010ECB
0x180010d91  lea     rcx, [rbp+47h+var_80]
0x180010d95  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180010d9b  lea     rcx, [rbp+47h+var_B0]
0x180010d9f  mov     [rbp+47h+cbSid], eax
0x180010da2  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180010da8  shr     eax, 1
0x180010daa  lea     rcx, [rbp+47h+var_B0]
0x180010dae  mov     [rbp+47h+var_C0], eax
0x180010db1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010db7  lea     rcx, [rbp+47h+var_80]
0x180010dbb  mov     rbx, rax
0x180010dbe  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010dc4  lea     rcx, [rbp+47h+var_B8]
0x180010dc8  mov     rdx, rsi; lpAccountName
0x180010dcb  mov     [rsp+100h+peUse], rcx; peUse
0x180010dd0  lea     r9, [rbp+47h+cbSid]; cbSid
0x180010dd4  lea     rcx, [rbp+47h+var_C0]
0x180010dd8  mov     r8, rax; Sid
0x180010ddb  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180010de0  xor     ecx, ecx; lpSystemName
0x180010de2  mov     [rsp+100h+ReferencedDomainName], rbx; ReferencedDomainName
0x180010de7  call    cs:__imp_LookupAccountNameW
0x180010ded  test    eax, eax
0x180010def  jnz     loc_180010EBE
0x180010df5  call    cs:__imp_GetLastError
0x180010dfb  cmp     eax, 7Ah ; 'z'
0x180010dfe  jnz     loc_180010EAA
0x180010e04  mov     edx, [rbp+47h+cbSid]
0x180010e07  lea     rcx, [rbp+47h+var_80]
0x180010e0b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180010e11  test    al, al
0x180010e13  jz      loc_180010EAA
0x180010e19  mov     edx, [rbp+47h+var_C0]
0x180010e1c  lea     rcx, [rbp+47h+var_B0]
0x180010e20  add     edx, edx
0x180010e22  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180010e28  test    al, al
0x180010e2a  jz      short loc_180010EAA
0x180010e2c  lea     rcx, [rbp+47h+var_80]
0x180010e30  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180010e36  lea     rcx, [rbp+47h+var_B0]
0x180010e3a  mov     [rbp+47h+cbSid], eax
0x180010e3d  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180010e43  shr     eax, 1
0x180010e45  lea     rcx, [rbp+47h+var_B0]
0x180010e49  mov     [rbp+47h+var_C0], eax
0x180010e4c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010e52  lea     rcx, [rbp+47h+var_80]
0x180010e56  mov     rbx, rax
0x180010e59  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010e5f  lea     rcx, [rbp+47h+var_B8]
0x180010e63  mov     rdx, rsi; lpAccountName
0x180010e66  mov     [rsp+100h+peUse], rcx; peUse
0x180010e6b  lea     r9, [rbp+47h+cbSid]; cbSid
0x180010e6f  lea     rcx, [rbp+47h+var_C0]
0x180010e73  mov     r8, rax; Sid
0x180010e76  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180010e7b  xor     ecx, ecx; lpSystemName
0x180010e7d  mov     [rsp+100h+ReferencedDomainName], rbx; ReferencedDomainName
0x180010e82  call    cs:__imp_LookupAccountNameW
0x180010e88  test    eax, eax
0x180010e8a  jnz     short loc_180010EBE
0x180010e8c  call    cs:__imp_GetLastError
0x180010e92  mov     ebx, eax
0x180010e94  test    eax, eax
0x180010e96  jle     loc_180010F2F
0x180010e9c  movzx   ebx, ax
0x180010e9f  or      ebx, 80070000h
0x180010ea5  jmp     loc_180010F2F
0x180010eaa  call    cs:__imp_GetLastError
0x180010eb0  test    eax, eax
0x180010eb2  jle     short loc_180010F2D
0x180010eb4  movzx   eax, ax
0x180010eb7  or      eax, 80070000h
0x180010ebc  jmp     short loc_180010F2D
0x180010ebe  lea     rcx, [rbp+47h+var_B0]
0x180010ec2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010ec8  mov     rdi, rax
0x180010ecb  mov     rdx, rdi
0x180010ece  mov     rcx, r14
0x180010ed1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010ed7  test    eax, eax
0x180010ed9  js      short loc_180010F2D
0x180010edb  mov     rbx, rsi
0x180010ede  mov     eax, r15d
0x180010ee1  jmp     short loc_180010F19
0x180010ee3  mov     r8, rbx
0x180010ee6  mov     rcx, r14
0x180010ee9  sub     r8, rsi
0x180010eec  sar     r8, 1
0x180010eef  test    r8d, r8d
0x180010ef2  jnz     short loc_180010F03
0x180010ef4  lea     rdx, asc_18001C844; "."
0x180010efb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010f01  jmp     short loc_180010F0C
0x180010f03  mov     rdx, rsi
0x180010f06  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180010f0c  test    eax, eax
0x180010f0e  js      short loc_180010F2D
0x180010f10  add     rbx, 2
0x180010f14  mov     eax, 1
0x180010f19  mov     rdx, rbx
0x180010f1c  mov     [r12], eax
0x180010f20  mov     rcx, r13
0x180010f23  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010f29  test    eax, eax
0x180010f2b  jns     short loc_180010F47
0x180010f2d  mov     ebx, eax
0x180010f2f  lea     rcx, [rbp+47h+var_B0]
0x180010f33  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010f39  lea     rcx, [rbp+47h+var_80]
0x180010f3d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010f43  mov     eax, ebx
0x180010f45  jmp     short loc_180010F78
0x180010f47  lea     rcx, [rbp+47h+var_B0]
0x180010f4b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010f51  lea     rcx, [rbp+47h+var_80]
0x180010f55  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010f5b  xor     eax, eax
0x180010f5d  jmp     short loc_180010F78
0x180010f5f  lea     rcx, [rbp+47h+var_B0]
0x180010f63  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010f69  lea     rcx, [rbp+47h+var_80]
0x180010f6d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010f73  mov     eax, 80070057h
0x180010f78  mov     rcx, [rbp+47h+var_50]
0x180010f7c  xor     rcx, rsp; StackCookie
0x180010f7f  call    __security_check_cookie
0x180010f84  add     rsp, 0C8h
0x180010f8b  pop     r15
0x180010f8d  pop     r14
0x180010f8f  pop     r13
0x180010f91  pop     r12
0x180010f93  pop     rdi
0x180010f94  pop     rsi
0x180010f95  pop     rbx
0x180010f96  pop     rbp
0x180010f97  retn
```
