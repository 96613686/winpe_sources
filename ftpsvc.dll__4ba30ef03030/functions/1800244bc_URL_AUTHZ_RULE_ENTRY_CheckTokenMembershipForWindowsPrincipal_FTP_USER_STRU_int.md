# URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(FTP_USER *,STRU *,int *)

- ea: `0x1800244bc`
- end: `0x18002475e`
- name: `?CheckTokenMembershipForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVFTP_USER@@PEAVSTRU@@PEAH@Z`
- size: `674`
- prototype: `__int64 __fastcall(struct FTP_USER *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024174`

## callees

- `0x1800244bc`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024598`
- `KERNEL32!GetLastError` at `0x1800245a3`
- `KERNEL32!GetLastError` at `0x1800245f3`
- `KERNEL32!GetLastError` at `0x18002465c`
- `KERNEL32!GetLastError` at `0x1800246bf`
- `KERNEL32!GetLastError` at `0x180024598`
- `KERNEL32!GetLastError` at `0x1800245a3`
- `KERNEL32!GetLastError` at `0x1800245f3`
- `KERNEL32!GetLastError` at `0x18002465c`
- `KERNEL32!GetLastError` at `0x1800246bf`
- `ADVAPI32!LookupAccountNameW` at `0x18002458a`
- `ADVAPI32!LookupAccountNameW` at `0x180024652`
- `ADVAPI32!LookupAccountNameW` at `0x18002458a`
- `ADVAPI32!LookupAccountNameW` at `0x180024652`
- `ADVAPI32!CheckTokenMembership` at `0x1800246b5`
- `ADVAPI32!CheckTokenMembership` at `0x1800246b5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024728`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024733`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024728`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024733`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800245e9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002461b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800245e9`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002461b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002453e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002453e`
- `iisutil!PuDbgPrintError` at `0x180024711`
- `iisutil!PuDbgPrintError` at `0x180024711`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002471c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002471c`

## string_xrefs

- `0x1800246fc`: `URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal`
- `0x1800246e6`: `Failed to call CheckTokenMembership() for %S \n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(
        struct FTP_USER *a1,
        struct STRU *a2,
        int *a3)
{
  signed int v6; // eax
  unsigned int v7; // edi
  signed int v8; // eax
  signed int v9; // eax
  PSID v10; // rbx
  void *v11; // rax
  signed int LastError; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  __int16 v20; // [rsp+7Ch] [rbp-84h]
  _BYTE v21[32]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+A0h] [rbp-60h]
  unsigned int v23; // [rsp+A8h] [rbp-58h]
  _BYTE v24[32]; // [rsp+B8h] [rbp-48h] BYREF
  char *v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+E0h] [rbp-20h]
  __int16 v27; // [rsp+E4h] [rbp-1Ch]
  char v28; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v29[127]; // [rsp+F1h] [rbp-Fh] BYREF

  memset_0(v29, 0, sizeof(v29));
  v28 = 0;
  v25 = &v28;
  v26 = 128;
  v27 = 256;
  v17[0] = 0;
  Sid = v17;
  v19 = 32;
  v20 = 256;
  cbSid = 32;
  STRU::STRU(v21);
  peUse = 0;
  cchReferencedDomainName = v23 >> 1;
  *a3 = 0;
  if ( LookupAccountNameW(0, *((LPCWSTR *)a2 + 4), Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
LABEL_16:
    v7 = 0;
    v10 = Sid;
    v11 = (void *)(*(__int64 (__fastcall **)(struct FTP_USER *))(*(_QWORD *)a1 + 56LL))(a1);
    if ( !CheckTokenMembership(v11, v10, a3) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_url_authz\\url_authz_rule_list.cxx",
          863,
          "URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal",
          v7,
          "Failed to call CheckTokenMembership() for %S \n",
          *((_QWORD *)a2 + 4));
    }
    goto LABEL_21;
  }
  if ( GetLastError() != 122 )
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_url_authz\\url_authz_rule_list.cxx",
        806,
        "URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal",
        v7,
        "Failed to Lookup account %S (LookupAccountNameW() failed)\n",
        *((_QWORD *)a2 + 4));
    goto LABEL_21;
  }
  if ( BUFFER::Resize((BUFFER *)v17, cbSid) && BUFFER::Resize((BUFFER *)v21, 2 * cchReferencedDomainName) )
  {
    if ( !LookupAccountNameW(
            0,
            *((LPCWSTR *)a2 + 4),
            Sid,
            &cbSid,
            ReferencedDomainName,
            &cchReferencedDomainName,
            &peUse) )
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_url_authz\\url_authz_rule_list.cxx",
          843,
          "URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal",
          v7,
          "Failed to Lookup account %S (LookupAccountNameW() failed)\n",
          *((_QWORD *)a2 + 4));
      goto LABEL_21;
    }
    goto LABEL_16;
  }
  v8 = GetLastError();
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
LABEL_21:
  STRU::~STRU(v21);
  BUFFER::~BUFFER((BUFFER *)v17);
  BUFFER::~BUFFER((BUFFER *)v24);
  return v7;
}

```

## disassembly

```asm
0x1800244bc  mov     [rsp-8+arg_18], rbx
0x1800244c1  push    rbp
0x1800244c2  push    rsi
0x1800244c3  push    rdi
0x1800244c4  push    r14
0x1800244c6  push    r15
0x1800244c8  lea     rbp, [rsp-80h]
0x1800244cd  sub     rsp, 180h
0x1800244d4  mov     rax, cs:__security_cookie
0x1800244db  xor     rax, rsp
0x1800244de  mov     [rbp+0A0h+var_30], rax
0x1800244e2  mov     r15, r8
0x1800244e5  mov     rsi, rdx
0x1800244e8  mov     r14, rcx
0x1800244eb  xor     edx, edx; Val
0x1800244ed  lea     r8d, [rdx+7Fh]; Size
0x1800244f1  lea     rcx, [rbp+0A0h+var_AF]; void *
0x1800244f5  call    memset_0
0x1800244fa  mov     [rbp+0A0h+var_B0], 0
0x1800244fe  lea     rax, [rbp+0A0h+var_B0]
0x180024502  mov     [rbp+0A0h+var_C8], rax
0x180024506  mov     [rbp+0A0h+var_C0], 80h
0x18002450d  mov     [rbp+0A0h+var_BC], 100h
0x180024513  mov     [rsp+1A0h+var_150], 0
0x18002451c  lea     rax, [rsp+1A0h+var_150]
0x180024521  mov     [rsp+1A0h+Sid], rax
0x180024526  mov     eax, 20h ; ' '
0x18002452b  mov     [rsp+1A0h+var_128], eax
0x18002452f  mov     [rsp+1A0h+var_124], 100h
0x180024536  mov     [rsp+1A0h+cbSid], eax
0x18002453a  lea     rcx, [rbp+0A0h+var_120]
0x18002453e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180024544  nop
0x180024545  mov     [rsp+1A0h+var_158], 0
0x18002454d  mov     eax, [rbp+0A0h+var_F8]
0x180024550  shr     eax, 1
0x180024552  mov     [rsp+1A0h+var_160], eax
0x180024556  mov     dword ptr [r15], 0
0x18002455d  mov     rax, [rbp+0A0h+var_100]
0x180024561  lea     rcx, [rsp+1A0h+var_158]
0x180024566  mov     [rsp+1A0h+peUse], rcx; peUse
0x18002456b  lea     rcx, [rsp+1A0h+var_160]
0x180024570  mov     [rsp+1A0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180024575  mov     [rsp+1A0h+ReferencedDomainName], rax; ReferencedDomainName
0x18002457a  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18002457f  mov     r8, [rsp+1A0h+Sid]; Sid
0x180024584  mov     rdx, [rsi+20h]; lpAccountName
0x180024588  xor     ecx, ecx; lpSystemName
0x18002458a  call    cs:__imp_LookupAccountNameW
0x180024590  test    eax, eax
0x180024592  jnz     loc_180024696
0x180024598  call    cs:__imp_GetLastError
0x18002459e  cmp     eax, 7Ah ; 'z'
0x1800245a1  jz      short loc_1800245E0
0x1800245a3  call    cs:__imp_GetLastError
0x1800245a9  mov     edi, eax
0x1800245ab  test    eax, eax
0x1800245ad  jle     short loc_1800245B8
0x1800245af  movzx   edi, ax
0x1800245b2  or      edi, 80070000h
0x1800245b8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800245bf  jz      loc_180024718
0x1800245c5  mov     rax, [rsi+20h]
0x1800245c9  mov     [rsp+1A0h+peUse], rax
0x1800245ce  lea     rax, aFailedToLookup; "Failed to Lookup account %S (LookupAcco"...
0x1800245d5  mov     r8d, 326h
0x1800245db  jmp     loc_1800246F3
0x1800245e0  mov     edx, [rsp+1A0h+cbSid]
0x1800245e4  lea     rcx, [rsp+1A0h+var_150]
0x1800245e9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800245ef  test    al, al
0x1800245f1  jnz     short loc_180024611
0x1800245f3  call    cs:__imp_GetLastError
0x1800245f9  mov     edi, eax
0x1800245fb  test    eax, eax
0x1800245fd  jle     loc_180024718
0x180024603  movzx   edi, ax
0x180024606  or      edi, 80070000h
0x18002460c  jmp     loc_180024718
0x180024611  mov     edx, [rsp+1A0h+var_160]
0x180024615  add     edx, edx
0x180024617  lea     rcx, [rbp+0A0h+var_120]
0x18002461b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024621  test    al, al
0x180024623  jz      short loc_1800245F3
0x180024625  mov     rax, [rbp+0A0h+var_100]
0x180024629  lea     rcx, [rsp+1A0h+var_158]
0x18002462e  mov     [rsp+1A0h+peUse], rcx; peUse
0x180024633  lea     rcx, [rsp+1A0h+var_160]
0x180024638  mov     [rsp+1A0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18002463d  mov     [rsp+1A0h+ReferencedDomainName], rax; ReferencedDomainName
0x180024642  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x180024647  mov     r8, [rsp+1A0h+Sid]; Sid
0x18002464c  mov     rdx, [rsi+20h]; lpAccountName
0x180024650  xor     ecx, ecx; lpSystemName
0x180024652  call    cs:__imp_LookupAccountNameW
0x180024658  test    eax, eax
0x18002465a  jnz     short loc_180024696
0x18002465c  call    cs:__imp_GetLastError
0x180024662  mov     edi, eax
0x180024664  test    eax, eax
0x180024666  jle     short loc_180024671
0x180024668  movzx   edi, ax
0x18002466b  or      edi, 80070000h
0x180024671  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024678  jz      loc_180024718
0x18002467e  mov     rax, [rsi+20h]
0x180024682  mov     [rsp+1A0h+peUse], rax
0x180024687  lea     rax, aFailedToLookup; "Failed to Lookup account %S (LookupAcco"...
0x18002468e  mov     r8d, 34Bh
0x180024694  jmp     short loc_1800246F3
0x180024696  xor     edi, edi
0x180024698  mov     rbx, [rsp+1A0h+Sid]
0x18002469d  mov     rax, [r14]
0x1800246a0  mov     rcx, r14
0x1800246a3  mov     rax, [rax+38h]
0x1800246a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246ac  mov     r8, r15; IsMember
0x1800246af  mov     rdx, rbx; SidToCheck
0x1800246b2  mov     rcx, rax; TokenHandle
0x1800246b5  call    cs:__imp_CheckTokenMembership
0x1800246bb  test    eax, eax
0x1800246bd  jnz     short loc_180024718
0x1800246bf  call    cs:__imp_GetLastError
0x1800246c5  mov     edi, eax
0x1800246c7  test    eax, eax
0x1800246c9  jle     short loc_1800246D4
0x1800246cb  movzx   edi, ax
0x1800246ce  or      edi, 80070000h
0x1800246d4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800246db  jz      short loc_180024718
0x1800246dd  mov     rax, [rsi+20h]
0x1800246e1  mov     [rsp+1A0h+peUse], rax
0x1800246e6  lea     rax, aFailedToCallCh; "Failed to call CheckTokenMembership() f"...
0x1800246ed  mov     r8d, 35Fh
0x1800246f3  mov     [rsp+1A0h+cchReferencedDomainName], rax
0x1800246f8  mov     dword ptr [rsp+1A0h+ReferencedDomainName], edi
0x1800246fc  lea     r9, aUrlAuthzRuleEn_1; "URL_AUTHZ_RULE_ENTRY::CheckTokenMembers"...
0x180024703  lea     rdx, aInetsrvIisIisr_33; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18002470a  mov     rcx, cs:g_pDebug
0x180024711  call    cs:__imp_PuDbgPrintError
0x180024717  nop
0x180024718  lea     rcx, [rbp+0A0h+var_120]
0x18002471c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180024722  nop
0x180024723  lea     rcx, [rsp+1A0h+var_150]
0x180024728  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002472e  nop
0x18002472f  lea     rcx, [rbp+0A0h+var_E8]
0x180024733  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024739  mov     eax, edi
0x18002473b  mov     rcx, [rbp+0A0h+var_30]
0x18002473f  xor     rcx, rsp; StackCookie
0x180024742  call    __security_check_cookie
0x180024747  mov     rbx, [rsp+1A0h+arg_18]
0x18002474f  add     rsp, 180h
0x180024756  pop     r15
0x180024758  pop     r14
0x18002475a  pop     rdi
0x18002475b  pop     rsi
0x18002475c  pop     rbp
0x18002475d  retn
```
