# CProxySinkSecurity::EnsureInitialized(void)

- ea: `0x180044590`
- end: `0x1800447b2`
- name: `?EnsureInitialized@CProxySinkSecurity@@AEAAJXZ`
- size: `546`
- prototype: `__int64 __fastcall(CProxySinkSecurity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003e4e0`

## callees

- `0x180044590`
- `0x1800447b8`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180044615`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180044615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800446dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800446dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004471c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004471c`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800446f1`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800446f1`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800445be`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800445be`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800446b6`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800446b6`
- `wbemcomn!??4CNtSid@@QEAAAEAV0@AEBV0@@Z` at `0x1800446aa`
- `wbemcomn!??4CNtSid@@QEAAAEAV0@AEBV0@@Z` at `0x1800446aa`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18004469a`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18004469a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800446cd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004478f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800447a6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800446cd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004478f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800447a6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004472b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004474e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004472b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004474e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18004467c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180044783`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18004467c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180044783`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProxySinkSecurity::EnsureInitialized(CProxySinkSecurity *this)
{
  WCHAR *v2; // rsi
  BOOL v3; // r15d
  _BYTE *v4; // rbx
  unsigned int v5; // ebx
  WCHAR *v7; // rax
  WCHAR *v8; // r14
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pwAuthnSvc; // [rsp+4Ch] [rbp-B4h] BYREF
  LPOLESTR pServerPrincName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Sid[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ReferencedDomainName[64]; // [rsp+B0h] [rbp-50h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v14, (struct _RTL_CRITICAL_SECTION *)this);
  if ( *((_DWORD *)this + 10) )
  {
    v5 = 1;
    goto LABEL_14;
  }
  pwAuthnSvc = 0;
  pServerPrincName = 0;
  if ( CoQueryProxyBlanket(*((IUnknown **)this + 8), &pwAuthnSvc, 0, &pServerPrincName, 0, 0, 0, 0) < 0 )
    goto LABEL_11;
  if ( pServerPrincName )
  {
    v2 = PrincNameToCompAccount(pServerPrincName);
    if ( !v2 )
      goto LABEL_11;
    cbSid = 64;
    cchReferencedDomainName = 64;
    peUse = 0;
    v3 = LookupAccountNameLocalW(v2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    if ( v3 )
    {
      v4 = Sid;
    }
    else
    {
      if ( GetLastError() != 122 )
      {
LABEL_10:
        CWin32DefaultArena::WbemMemFree(v2);
LABEL_11:
        if ( pServerPrincName )
          CoTaskMemFree(pServerPrincName);
        goto LABEL_13;
      }
      v4 = CWin32DefaultArena::WbemMemAlloc(cbSid);
      v7 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchReferencedDomainName, 2u));
      v8 = v7;
      if ( v4 && v7 )
        v3 = LookupAccountNameLocalW(v2, v4, &cbSid, v7, &cchReferencedDomainName, &peUse);
      CWin32DefaultArena::WbemMemFree(v8);
      if ( !v3 )
      {
LABEL_8:
        if ( v4 != Sid )
          CWin32DefaultArena::WbemMemFree(v4);
        goto LABEL_10;
      }
    }
    CNtSid::CNtSid((CNtSid *)v15, v4);
    CNtSid::operator=((char *)this + 48, v15);
    CNtSid::~CNtSid((CNtSid *)v15);
    goto LABEL_8;
  }
LABEL_13:
  *((_DWORD *)this + 10) = 1;
  v5 = 0;
LABEL_14:
  CInCritSec::~CInCritSec((CInCritSec *)v14);
  return v5;
}

```

## disassembly

```asm
0x180044590  push    rbp
0x180044592  push    rbx
0x180044593  push    rsi
0x180044594  push    rdi
0x180044595  push    r14
0x180044597  push    r15
0x180044599  lea     rbp, [rsp-48h]
0x18004459e  sub     rsp, 148h
0x1800445a5  mov     rax, cs:__security_cookie
0x1800445ac  xor     rax, rsp
0x1800445af  mov     [rbp+70h+var_40], rax
0x1800445b3  mov     rdi, rcx
0x1800445b6  mov     rdx, rcx
0x1800445b9  lea     rcx, [rsp+170h+var_118]
0x1800445be  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800445c4  nop
0x1800445c5  cmp     dword ptr [rdi+28h], 0
0x1800445c9  jnz     loc_180044715
0x1800445cf  mov     [rsp+170h+pwAuthnSvc], 0
0x1800445d7  mov     [rsp+170h+pServerPrincName], 0
0x1800445e0  mov     [rsp+170h+pCapabilites], 0; pCapabilites
0x1800445e9  mov     [rsp+170h+pAuthInfo], 0; pAuthInfo
0x1800445f2  mov     [rsp+170h+pImpLevel], 0; pImpLevel
0x1800445fb  mov     [rsp+170h+pAuthnLevel], 0; pAuthnLevel
0x180044604  lea     r9, [rsp+170h+pServerPrincName]; pServerPrincName
0x180044609  xor     r8d, r8d; pAuthzSvc
0x18004460c  lea     rdx, [rsp+170h+pwAuthnSvc]; pwAuthnSvc
0x180044611  mov     rcx, [rdi+40h]; pProxy
0x180044615  call    cs:__imp_CoQueryProxyBlanket
0x18004461b  test    eax, eax
0x18004461d  js      loc_1800446D3
0x180044623  mov     rcx, [rsp+170h+pServerPrincName]; Src
0x180044628  test    rcx, rcx
0x18004462b  jz      loc_1800446E3
0x180044631  call    ?PrincNameToCompAccount@@YAPEAGPEBG@Z; PrincNameToCompAccount(ushort const *)
0x180044636  mov     rsi, rax
0x180044639  test    rax, rax
0x18004463c  jz      loc_1800446D3
0x180044642  mov     eax, 40h ; '@'
0x180044647  mov     [rsp+170h+cbSid], eax
0x18004464b  mov     [rsp+170h+cchReferencedDomainName], eax
0x18004464f  mov     [rsp+170h+peUse], 0
0x180044657  lea     rax, [rsp+170h+peUse]
0x18004465c  mov     [rsp+170h+pImpLevel], rax; peUse
0x180044661  lea     rax, [rsp+170h+cchReferencedDomainName]
0x180044666  mov     [rsp+170h+pAuthnLevel], rax; cchReferencedDomainName
0x18004466b  lea     r9, [rbp+70h+ReferencedDomainName]; ReferencedDomainName
0x18004466f  lea     r8, [rsp+170h+cbSid]; cbSid
0x180044674  lea     rdx, [rsp+170h+Sid]; Sid
0x180044679  mov     rcx, rsi; lpAccountName
0x18004467c  call    cs:__imp_LookupAccountNameLocalW
0x180044682  mov     r15d, eax
0x180044685  test    eax, eax
0x180044687  jz      loc_18004471C
0x18004468d  lea     rbx, [rsp+170h+Sid]
0x180044692  mov     rdx, rbx
0x180044695  lea     rcx, [rsp+170h+var_110]
0x18004469a  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x1800446a0  nop
0x1800446a1  lea     rcx, [rdi+30h]
0x1800446a5  lea     rdx, [rsp+170h+var_110]
0x1800446aa  call    cs:__imp_??4CNtSid@@QEAAAEAV0@AEBV0@@Z; CNtSid::operator=(CNtSid const &)
0x1800446b0  nop
0x1800446b1  lea     rcx, [rsp+170h+var_110]
0x1800446b6  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x1800446bc  lea     rax, [rsp+170h+Sid]
0x1800446c1  cmp     rbx, rax
0x1800446c4  jnz     loc_1800447A3
0x1800446ca  mov     rcx, rsi
0x1800446cd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800446d3  mov     rcx, [rsp+170h+pServerPrincName]; pv
0x1800446d8  test    rcx, rcx
0x1800446db  jz      short loc_1800446E3
0x1800446dd  call    cs:__imp_CoTaskMemFree
0x1800446e3  mov     dword ptr [rdi+28h], 1
0x1800446ea  xor     ebx, ebx
0x1800446ec  lea     rcx, [rsp+170h+var_118]
0x1800446f1  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800446f7  mov     eax, ebx
0x1800446f9  mov     rcx, [rbp+70h+var_40]
0x1800446fd  xor     rcx, rsp; StackCookie
0x180044700  call    __security_check_cookie
0x180044705  add     rsp, 148h
0x18004470c  pop     r15
0x18004470e  pop     r14
0x180044710  pop     rdi
0x180044711  pop     rsi
0x180044712  pop     rbx
0x180044713  pop     rbp
0x180044714  retn
0x180044715  mov     ebx, 1
0x18004471a  jmp     short loc_1800446EC
0x18004471c  call    cs:__imp_GetLastError
0x180044722  cmp     eax, 7Ah ; 'z'
0x180044725  jnz     short loc_1800446CA
0x180044727  mov     ecx, [rsp+170h+cbSid]
0x18004472b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180044731  mov     rbx, rax
0x180044734  mov     ecx, [rsp+170h+cchReferencedDomainName]
0x180044738  mov     eax, 2
0x18004473d  mul     rcx
0x180044740  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180044747  cmovb   rax, rcx
0x18004474b  mov     rcx, rax
0x18004474e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180044754  mov     r14, rax
0x180044757  test    rbx, rbx
0x18004475a  jz      short loc_18004478C
0x18004475c  test    rax, rax
0x18004475f  jz      short loc_18004478C
0x180044761  lea     rax, [rsp+170h+peUse]
0x180044766  mov     [rsp+170h+pImpLevel], rax; peUse
0x18004476b  lea     rax, [rsp+170h+cchReferencedDomainName]
0x180044770  mov     [rsp+170h+pAuthnLevel], rax; cchReferencedDomainName
0x180044775  mov     r9, r14; ReferencedDomainName
0x180044778  lea     r8, [rsp+170h+cbSid]; cbSid
0x18004477d  mov     rdx, rbx; Sid
0x180044780  mov     rcx, rsi; lpAccountName
0x180044783  call    cs:__imp_LookupAccountNameLocalW
0x180044789  mov     r15d, eax
0x18004478c  mov     rcx, r14
0x18004478f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180044795  test    r15d, r15d
0x180044798  jz      loc_1800446BC
0x18004479e  jmp     loc_180044692
0x1800447a3  mov     rcx, rbx
0x1800447a6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800447ac  jmp     loc_1800446CA
```
