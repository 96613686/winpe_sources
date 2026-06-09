# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x180031eb4`
- end: `0x180032178`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `708`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180032994`

## callees

- `0x180031eb4`
- `0x1800343f0`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180031f33`
- `msvcrt!wcspbrk` at `0x180031f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003206c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003208a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003206c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003208a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032113`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003211d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003212b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032135`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032143`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003214d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032113`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003211d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003212b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032135`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180032143`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18003214d`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180031ef3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180031efd`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180031ef3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180031efd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180031f91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180031f9e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003202c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180032039`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800320a2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180031f91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180031f9e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003202c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180032039`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800320a2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180031f75`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180031f82`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180032010`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18003201d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180031f75`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180031f82`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180032010`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18003201d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180031feb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180032002`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180031feb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180032002`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800320b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800320db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180032103`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800320b1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800320db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180032103`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800320e6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800320e6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031fc7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180032062`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031fc7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180032062`

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
0x180031eb4  push    rbp
0x180031eb6  push    rbx
0x180031eb7  push    rsi
0x180031eb8  push    rdi
0x180031eb9  push    r12
0x180031ebb  push    r13
0x180031ebd  push    r14
0x180031ebf  push    r15
0x180031ec1  lea     rbp, [rsp-0Fh]
0x180031ec6  sub     rsp, 0C8h
0x180031ecd  mov     rax, cs:__security_cookie
0x180031ed4  xor     rax, rsp
0x180031ed7  mov     [rbp+47h+var_50], rax
0x180031edb  mov     r14, [rbp+47h+arg_20]
0x180031edf  mov     r15, rcx
0x180031ee2  mov     r12, [rbp+47h+arg_28]
0x180031ee6  lea     rcx, [rbp+47h+var_80]
0x180031eea  mov     r13, r9
0x180031eed  mov     rdi, r8
0x180031ef0  mov     rsi, rdx
0x180031ef3  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180031ef9  lea     rcx, [rbp+47h+var_B0]
0x180031efd  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180031f03  xor     eax, eax
0x180031f05  mov     [rbp+47h+cbSid], eax
0x180031f08  mov     [rbp+47h+var_C0], eax
0x180031f0b  mov     [rbp+47h+var_B8], eax
0x180031f0e  test    r13, r13
0x180031f11  jz      loc_18003213F
0x180031f17  test    r14, r14
0x180031f1a  jz      loc_18003213F
0x180031f20  test    r12, r12
0x180031f23  jz      loc_18003213F
0x180031f29  lea     rdx, asc_18003CF14; "/\\"
0x180031f30  mov     rcx, rsi; String
0x180031f33  call    cs:__imp_wcspbrk
0x180031f39  mov     rbx, rax
0x180031f3c  test    rax, rax
0x180031f3f  jnz     loc_1800320C3
0x180031f45  test    rdi, rdi
0x180031f48  jz      short loc_180031F52
0x180031f4a  movzx   eax, word ptr [rdi]
0x180031f4d  test    ax, ax
0x180031f50  jnz     short loc_180031F59
0x180031f52  movzx   eax, word ptr [r15]
0x180031f56  mov     rdi, r15
0x180031f59  xor     r15d, r15d
0x180031f5c  cmp     ax, 5Ch ; '\'
0x180031f60  jnz     loc_1800320AB
0x180031f66  cmp     [rdi+2], r15w
0x180031f6b  jnz     loc_1800320AB
0x180031f71  lea     rcx, [rbp+47h+var_80]
0x180031f75  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180031f7b  lea     rcx, [rbp+47h+var_B0]
0x180031f7f  mov     [rbp+47h+cbSid], eax
0x180031f82  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180031f88  shr     eax, 1
0x180031f8a  lea     rcx, [rbp+47h+var_B0]
0x180031f8e  mov     [rbp+47h+var_C0], eax
0x180031f91  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180031f97  lea     rcx, [rbp+47h+var_80]
0x180031f9b  mov     rbx, rax
0x180031f9e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180031fa4  lea     rcx, [rbp+47h+var_B8]
0x180031fa8  mov     rdx, rsi; lpAccountName
0x180031fab  mov     [rsp+100h+peUse], rcx; peUse
0x180031fb0  lea     r9, [rbp+47h+cbSid]; cbSid
0x180031fb4  lea     rcx, [rbp+47h+var_C0]
0x180031fb8  mov     r8, rax; Sid
0x180031fbb  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180031fc0  xor     ecx, ecx; lpSystemName
0x180031fc2  mov     [rsp+100h+ReferencedDomainName], rbx; ReferencedDomainName
0x180031fc7  call    cs:__imp_LookupAccountNameW
0x180031fcd  test    eax, eax
0x180031fcf  jnz     loc_18003209E
0x180031fd5  call    cs:__imp_GetLastError
0x180031fdb  cmp     eax, 7Ah ; 'z'
0x180031fde  jnz     loc_18003208A
0x180031fe4  mov     edx, [rbp+47h+cbSid]
0x180031fe7  lea     rcx, [rbp+47h+var_80]
0x180031feb  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180031ff1  test    al, al
0x180031ff3  jz      loc_18003208A
0x180031ff9  mov     edx, [rbp+47h+var_C0]
0x180031ffc  lea     rcx, [rbp+47h+var_B0]
0x180032000  add     edx, edx
0x180032002  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180032008  test    al, al
0x18003200a  jz      short loc_18003208A
0x18003200c  lea     rcx, [rbp+47h+var_80]
0x180032010  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180032016  lea     rcx, [rbp+47h+var_B0]
0x18003201a  mov     [rbp+47h+cbSid], eax
0x18003201d  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180032023  shr     eax, 1
0x180032025  lea     rcx, [rbp+47h+var_B0]
0x180032029  mov     [rbp+47h+var_C0], eax
0x18003202c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180032032  lea     rcx, [rbp+47h+var_80]
0x180032036  mov     rbx, rax
0x180032039  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18003203f  lea     rcx, [rbp+47h+var_B8]
0x180032043  mov     rdx, rsi; lpAccountName
0x180032046  mov     [rsp+100h+peUse], rcx; peUse
0x18003204b  lea     r9, [rbp+47h+cbSid]; cbSid
0x18003204f  lea     rcx, [rbp+47h+var_C0]
0x180032053  mov     r8, rax; Sid
0x180032056  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18003205b  xor     ecx, ecx; lpSystemName
0x18003205d  mov     [rsp+100h+ReferencedDomainName], rbx; ReferencedDomainName
0x180032062  call    cs:__imp_LookupAccountNameW
0x180032068  test    eax, eax
0x18003206a  jnz     short loc_18003209E
0x18003206c  call    cs:__imp_GetLastError
0x180032072  mov     ebx, eax
0x180032074  test    eax, eax
0x180032076  jle     loc_18003210F
0x18003207c  movzx   ebx, ax
0x18003207f  or      ebx, 80070000h
0x180032085  jmp     loc_18003210F
0x18003208a  call    cs:__imp_GetLastError
0x180032090  test    eax, eax
0x180032092  jle     short loc_18003210D
0x180032094  movzx   eax, ax
0x180032097  or      eax, 80070000h
0x18003209c  jmp     short loc_18003210D
0x18003209e  lea     rcx, [rbp+47h+var_B0]
0x1800320a2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800320a8  mov     rdi, rax
0x1800320ab  mov     rdx, rdi
0x1800320ae  mov     rcx, r14
0x1800320b1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800320b7  test    eax, eax
0x1800320b9  js      short loc_18003210D
0x1800320bb  mov     rbx, rsi
0x1800320be  mov     eax, r15d
0x1800320c1  jmp     short loc_1800320F9
0x1800320c3  mov     r8, rbx
0x1800320c6  mov     rcx, r14
0x1800320c9  sub     r8, rsi
0x1800320cc  sar     r8, 1
0x1800320cf  test    r8d, r8d
0x1800320d2  jnz     short loc_1800320E3
0x1800320d4  lea     rdx, asc_18003CF1C; "."
0x1800320db  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800320e1  jmp     short loc_1800320EC
0x1800320e3  mov     rdx, rsi
0x1800320e6  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800320ec  test    eax, eax
0x1800320ee  js      short loc_18003210D
0x1800320f0  add     rbx, 2
0x1800320f4  mov     eax, 1
0x1800320f9  mov     rdx, rbx
0x1800320fc  mov     [r12], eax
0x180032100  mov     rcx, r13
0x180032103  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180032109  test    eax, eax
0x18003210b  jns     short loc_180032127
0x18003210d  mov     ebx, eax
0x18003210f  lea     rcx, [rbp+47h+var_B0]
0x180032113  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180032119  lea     rcx, [rbp+47h+var_80]
0x18003211d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180032123  mov     eax, ebx
0x180032125  jmp     short loc_180032158
0x180032127  lea     rcx, [rbp+47h+var_B0]
0x18003212b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180032131  lea     rcx, [rbp+47h+var_80]
0x180032135  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18003213b  xor     eax, eax
0x18003213d  jmp     short loc_180032158
0x18003213f  lea     rcx, [rbp+47h+var_B0]
0x180032143  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180032149  lea     rcx, [rbp+47h+var_80]
0x18003214d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180032153  mov     eax, 80070057h
0x180032158  mov     rcx, [rbp+47h+var_50]
0x18003215c  xor     rcx, rsp; StackCookie
0x18003215f  call    __security_check_cookie
0x180032164  add     rsp, 0C8h
0x18003216b  pop     r15
0x18003216d  pop     r14
0x18003216f  pop     r13
0x180032171  pop     r12
0x180032173  pop     rdi
0x180032174  pop     rsi
0x180032175  pop     rbx
0x180032176  pop     rbp
0x180032177  retn
```
