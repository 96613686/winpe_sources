# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x180034d84`
- end: `0x180035102`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `894`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180035a78`

## callees

- `0x180034d84`
- `0x180037790`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180034e0f`
- `msvcrt!wcspbrk` at `0x180034e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fc4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035078`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035088`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003509c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800350ac`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800350c0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800350d0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035078`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035088`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003509c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800350ac`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800350c0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800350d0`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180034dc3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180034dd3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180034dc3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180034dd3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034e7f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034e92`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034f4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034f61`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034fe9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034e7f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034e92`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034f4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034f61`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180034fe9`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034e57`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034e6a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034f26`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034f39`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034e57`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034e6a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034f26`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180034f39`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180034ef1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180034f0e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180034ef1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180034f0e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034ffe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003502e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180035062`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180034ffe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003502e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180035062`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18003503f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18003503f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180034ec1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180034f90`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180034ec1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180034f90`

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
0x180034d84  push    rbp
0x180034d86  push    rbx
0x180034d87  push    rsi
0x180034d88  push    rdi
0x180034d89  push    r12
0x180034d8b  push    r13
0x180034d8d  push    r14
0x180034d8f  push    r15
0x180034d91  lea     rbp, [rsp-0Fh]
0x180034d96  sub     rsp, 0C8h
0x180034d9d  mov     rax, cs:__security_cookie
0x180034da4  xor     rax, rsp
0x180034da7  mov     [rbp+47h+var_50], rax
0x180034dab  mov     r14, [rbp+47h+arg_20]
0x180034daf  mov     r15, rcx
0x180034db2  mov     r12, [rbp+47h+arg_28]
0x180034db6  lea     rcx, [rbp+47h+var_80]
0x180034dba  mov     r13, r9
0x180034dbd  mov     rdi, r8
0x180034dc0  mov     rsi, rdx
0x180034dc3  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180034dca  nop     dword ptr [rax+rax+00h]
0x180034dcf  lea     rcx, [rbp+47h+var_B0]
0x180034dd3  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180034dda  nop     dword ptr [rax+rax+00h]
0x180034ddf  xor     eax, eax
0x180034de1  mov     [rbp+47h+cbSid], eax
0x180034de4  mov     [rbp+47h+var_C0], eax
0x180034de7  mov     [rbp+47h+var_B8], eax
0x180034dea  test    r13, r13
0x180034ded  jz      loc_1800350BC
0x180034df3  test    r14, r14
0x180034df6  jz      loc_1800350BC
0x180034dfc  test    r12, r12
0x180034dff  jz      loc_1800350BC
0x180034e05  lea     rdx, asc_18003FF14; "/\\"
0x180034e0c  mov     rcx, rsi; String
0x180034e0f  call    cs:__imp_wcspbrk
0x180034e16  nop     dword ptr [rax+rax+00h]
0x180034e1b  mov     rbx, rax
0x180034e1e  test    rax, rax
0x180034e21  jnz     loc_180035016
0x180034e27  test    rdi, rdi
0x180034e2a  jz      short loc_180034E34
0x180034e2c  movzx   eax, word ptr [rdi]
0x180034e2f  test    ax, ax
0x180034e32  jnz     short loc_180034E3B
0x180034e34  movzx   eax, word ptr [r15]
0x180034e38  mov     rdi, r15
0x180034e3b  xor     r15d, r15d
0x180034e3e  cmp     ax, 5Ch ; '\'
0x180034e42  jnz     loc_180034FF8
0x180034e48  cmp     [rdi+2], r15w
0x180034e4d  jnz     loc_180034FF8
0x180034e53  lea     rcx, [rbp+47h+var_80]
0x180034e57  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180034e5e  nop     dword ptr [rax+rax+00h]
0x180034e63  lea     rcx, [rbp+47h+var_B0]
0x180034e67  mov     [rbp+47h+cbSid], eax
0x180034e6a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180034e71  nop     dword ptr [rax+rax+00h]
0x180034e76  shr     eax, 1
0x180034e78  lea     rcx, [rbp+47h+var_B0]
0x180034e7c  mov     [rbp+47h+var_C0], eax
0x180034e7f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180034e86  nop     dword ptr [rax+rax+00h]
0x180034e8b  lea     rcx, [rbp+47h+var_80]
0x180034e8f  mov     rbx, rax
0x180034e92  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180034e99  nop     dword ptr [rax+rax+00h]
0x180034e9e  lea     rcx, [rbp+47h+var_B8]
0x180034ea2  mov     rdx, rsi; lpAccountName
0x180034ea5  mov     [rsp+100h+peUse], rcx; peUse
0x180034eaa  lea     r9, [rbp+47h+cbSid]; cbSid
0x180034eae  lea     rcx, [rbp+47h+var_C0]
0x180034eb2  mov     r8, rax; Sid
0x180034eb5  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180034eba  xor     ecx, ecx; lpSystemName
0x180034ebc  mov     [rsp+100h+ReferencedDomainName], rbx; ReferencedDomainName
0x180034ec1  call    cs:__imp_LookupAccountNameW
0x180034ec8  nop     dword ptr [rax+rax+00h]
0x180034ecd  test    eax, eax
0x180034ecf  jnz     loc_180034FE5
0x180034ed5  call    cs:__imp_GetLastError
0x180034edc  nop     dword ptr [rax+rax+00h]
0x180034ee1  cmp     eax, 7Ah ; 'z'
0x180034ee4  jnz     loc_180034FC4
0x180034eea  mov     edx, [rbp+47h+cbSid]
0x180034eed  lea     rcx, [rbp+47h+var_80]
0x180034ef1  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180034ef8  nop     dword ptr [rax+rax+00h]
0x180034efd  test    al, al
0x180034eff  jz      loc_180034FC4
0x180034f05  mov     edx, [rbp+47h+var_C0]
0x180034f08  lea     rcx, [rbp+47h+var_B0]
0x180034f0c  add     edx, edx
0x180034f0e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180034f15  nop     dword ptr [rax+rax+00h]
0x180034f1a  test    al, al
0x180034f1c  jz      loc_180034FC4
0x180034f22  lea     rcx, [rbp+47h+var_80]
0x180034f26  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180034f2d  nop     dword ptr [rax+rax+00h]
0x180034f32  lea     rcx, [rbp+47h+var_B0]
0x180034f36  mov     [rbp+47h+cbSid], eax
0x180034f39  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180034f40  nop     dword ptr [rax+rax+00h]
0x180034f45  shr     eax, 1
0x180034f47  lea     rcx, [rbp+47h+var_B0]
0x180034f4b  mov     [rbp+47h+var_C0], eax
0x180034f4e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180034f55  nop     dword ptr [rax+rax+00h]
0x180034f5a  lea     rcx, [rbp+47h+var_80]
0x180034f5e  mov     rbx, rax
0x180034f61  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180034f68  nop     dword ptr [rax+rax+00h]
0x180034f6d  lea     rcx, [rbp+47h+var_B8]
0x180034f71  mov     rdx, rsi; lpAccountName
0x180034f74  mov     [rsp+100h+peUse], rcx; peUse
0x180034f79  lea     r9, [rbp+47h+cbSid]; cbSid
0x180034f7d  lea     rcx, [rbp+47h+var_C0]
0x180034f81  mov     r8, rax; Sid
0x180034f84  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180034f89  xor     ecx, ecx; lpSystemName
0x180034f8b  mov     [rsp+100h+ReferencedDomainName], rbx; ReferencedDomainName
0x180034f90  call    cs:__imp_LookupAccountNameW
0x180034f97  nop     dword ptr [rax+rax+00h]
0x180034f9c  test    eax, eax
0x180034f9e  jnz     short loc_180034FE5
0x180034fa0  call    cs:__imp_GetLastError
0x180034fa7  nop     dword ptr [rax+rax+00h]
0x180034fac  mov     ebx, eax
0x180034fae  test    eax, eax
0x180034fb0  jle     loc_180035074
0x180034fb6  movzx   ebx, ax
0x180034fb9  or      ebx, 80070000h
0x180034fbf  jmp     loc_180035074
0x180034fc4  call    cs:__imp_GetLastError
0x180034fcb  nop     dword ptr [rax+rax+00h]
0x180034fd0  test    eax, eax
0x180034fd2  jle     loc_180035072
0x180034fd8  movzx   eax, ax
0x180034fdb  or      eax, 80070000h
0x180034fe0  jmp     loc_180035072
0x180034fe5  lea     rcx, [rbp+47h+var_B0]
0x180034fe9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180034ff0  nop     dword ptr [rax+rax+00h]
0x180034ff5  mov     rdi, rax
0x180034ff8  mov     rdx, rdi
0x180034ffb  mov     rcx, r14
0x180034ffe  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180035005  nop     dword ptr [rax+rax+00h]
0x18003500a  test    eax, eax
0x18003500c  js      short loc_180035072
0x18003500e  mov     rbx, rsi
0x180035011  mov     eax, r15d
0x180035014  jmp     short loc_180035058
0x180035016  mov     r8, rbx
0x180035019  mov     rcx, r14
0x18003501c  sub     r8, rsi
0x18003501f  sar     r8, 1
0x180035022  test    r8d, r8d
0x180035025  jnz     short loc_18003503C
0x180035027  lea     rdx, asc_18003FF1C; "."
0x18003502e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180035035  nop     dword ptr [rax+rax+00h]
0x18003503a  jmp     short loc_18003504B
0x18003503c  mov     rdx, rsi
0x18003503f  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180035046  nop     dword ptr [rax+rax+00h]
0x18003504b  test    eax, eax
0x18003504d  js      short loc_180035072
0x18003504f  add     rbx, 2
0x180035053  mov     eax, 1
0x180035058  mov     rdx, rbx
0x18003505b  mov     [r12], eax
0x18003505f  mov     rcx, r13
0x180035062  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180035069  nop     dword ptr [rax+rax+00h]
0x18003506e  test    eax, eax
0x180035070  jns     short loc_180035098
0x180035072  mov     ebx, eax
0x180035074  lea     rcx, [rbp+47h+var_B0]
0x180035078  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003507f  nop     dword ptr [rax+rax+00h]
0x180035084  lea     rcx, [rbp+47h+var_80]
0x180035088  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003508f  nop     dword ptr [rax+rax+00h]
0x180035094  mov     eax, ebx
0x180035096  jmp     short loc_1800350E1
0x180035098  lea     rcx, [rbp+47h+var_B0]
0x18003509c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800350a3  nop     dword ptr [rax+rax+00h]
0x1800350a8  lea     rcx, [rbp+47h+var_80]
0x1800350ac  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800350b3  nop     dword ptr [rax+rax+00h]
0x1800350b8  xor     eax, eax
0x1800350ba  jmp     short loc_1800350E1
0x1800350bc  lea     rcx, [rbp+47h+var_B0]
0x1800350c0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800350c7  nop     dword ptr [rax+rax+00h]
0x1800350cc  lea     rcx, [rbp+47h+var_80]
0x1800350d0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800350d7  nop     dword ptr [rax+rax+00h]
0x1800350dc  mov     eax, 80070057h
0x1800350e1  mov     rcx, [rbp+47h+var_50]
0x1800350e5  xor     rcx, rsp; StackCookie
0x1800350e8  call    __security_check_cookie
0x1800350ed  add     rsp, 0C8h
0x1800350f4  pop     r15
0x1800350f6  pop     r14
0x1800350f8  pop     r13
0x1800350fa  pop     r12
0x1800350fc  pop     rdi
0x1800350fd  pop     rsi
0x1800350fe  pop     rbx
0x1800350ff  pop     rbp
0x180035100  retn
```
