# KerbUpdateOldLogonSession(_KERB_LOGON_SESSION *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,_LUID *,_KERB_TICKET_CACHE_ENTRY *,_UNICODE_STRING *)

- ea: `0x1800acc7c`
- end: `0x1800ace7a`
- name: `?KerbUpdateOldLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@PEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAU_LUID@@PEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_UNICODE_STRING@@@Z`
- size: `510`
- prototype: `void __usercall(struct _KERB_LOGON_SESSION *@<rcx>, struct _SECPKG_PRIMARY_CRED *@<rdx>, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *@<r8>, struct _LUID *@<r9>, struct _KERB_TICKET_CACHE_ENTRY *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025680`
- `0x18005b210`

## callees

- `0x1800069a0`
- `0x180009afc`
- `0x18000a630`
- `0x18004f220`
- `0x180060774`
- `0x18006557c`
- `0x180066ee0`
- `0x18006e61c`
- `0x18008b70c`
- `0x180097fdc`
- `0x1800ac4b4`
- `0x1800acc7c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800acd57`
- `ntdll!RtlEqualSid` at `0x1800acd57`
- `ntdll!RtlEnterCriticalSection` at `0x1800acd0f`
- `ntdll!RtlEnterCriticalSection` at `0x1800acd21`
- `ntdll!RtlEnterCriticalSection` at `0x1800acd0f`
- `ntdll!RtlEnterCriticalSection` at `0x1800acd21`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ace2c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ace36`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ace2c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ace36`
- `LSASRV!LsaIEfsAcceptSmartcardCredentials` at `0x1800acdd0`
- `LSASRV!LsaIEfsAcceptSmartcardCredentials` at `0x1800acdd0`

## string_xrefs

- `0x1800accf2`: `KerbUpdateOldLogonSession`

## pseudocode

```c
void __fastcall KerbUpdateOldLogonSession(
        struct _RTL_CRITICAL_SECTION *a1,
        struct _SECPKG_PRIMARY_CRED *a2,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *a3,
        struct _LUID *a4,
        struct _KERB_TICKET_CACHE_ENTRY *a5,
        struct _UNICODE_STRING *a6)
{
  struct _KERB_LOGON_SESSION *LogonSession; // rax
  struct _KERB_LOGON_SESSION *v10; // rbx
  BOOLEAN v11; // bp
  int PrimaryPrincipalSid; // r12d
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  int LockSemaphore; // eax
  int v15; // edx
  unsigned int v16; // eax
  struct _KERB_TICKET_CACHE_ENTRY *v17; // rdi
  LONG HighPart; // [rsp+20h] [rbp-68h]
  DWORD LowPart; // [rsp+28h] [rbp-60h]
  struct _RTL_CRITICAL_SECTION *CriticalSection; // [rsp+50h] [rbp-38h]
  PSID Sid2; // [rsp+A0h] [rbp+18h] BYREF

  Sid2 = a3;
  LogonSession = KerbLocateLogonSession(a4, 0);
  v10 = LogonSession;
  if ( LogonSession )
  {
    v11 = 0;
    LowPart = a4->LowPart;
    HighPart = a4->HighPart;
    KerbTracerT::Log(
      10,
      "KerbUpdateOldLogonSession",
      8779,
      "refreshing old logon session %#x:%#x for %wZ\\%wZ, to match with %wZ\\%wZ\n",
      HighPart,
      LowPart,
      (char *)LogonSession + 136,
      (char *)LogonSession + 120,
      &a1[3].OwningThread,
      &a1[3]);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v10 + 2);
    CriticalSection = a1 + 2;
    RtlEnterCriticalSection(a1 + 2);
    Sid2 = 0;
    PrimaryPrincipalSid = GetPrimaryPrincipalSid((struct _LUID *)v10 + 8, &Sid2);
    if ( PrimaryPrincipalSid >= 0 )
      v11 = RtlEqualSid(a2->UserSid, Sid2);
    if ( Sid2 )
      KerbFree(Sid2);
    if ( PrimaryPrincipalSid >= 0 && v11 )
    {
      if ( a6 )
      {
        DebugInfo = a1[10].DebugInfo;
        if ( DebugInfo )
        {
          if ( !KerbIsIumCert(*(const struct _CERT_CONTEXT **)&DebugInfo->EntryCount)
            && ((__int64)a1[22].LockSemaphore & 0x1000000) == 0 )
          {
            LsaIEfsAcceptSmartcardCredentials(*(_QWORD *)&a1[10].DebugInfo->EntryCount, a6, a4);
          }
        }
      }
      LockSemaphore = (int)a1[22].LockSemaphore;
      v15 = LockSemaphore | 0x80;
      v16 = LockSemaphore & 0xFFFFFF7F;
      if ( (a2->Flags & 8) == 0 )
        v15 = v16;
      LODWORD(a1[22].LockSemaphore) = v15;
      if ( (int)KerbUpdateCredentials(v10, (struct _KERB_LOGON_SESSION *)a1) >= 0 )
      {
        v17 = a5;
        if ( a5 )
        {
          KerbRemoveTicketCacheEntry(a5);
          KerbInsertTicketCacheEntry((struct _KERB_LOGON_SESSION *)((char *)v10 + 280), v17);
        }
      }
    }
    RtlLeaveCriticalSection(CriticalSection);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v10 + 2);
    if ( *((_DWORD *)v10 + 16) == 999 && !*((_DWORD *)v10 + 17) )
    {
      KerbPurgeCompoundedTickets();
      KerbFreeGlobalKdcProxyClientCertContext(v10);
    }
    KerbDereferenceLogonSession(v10);
  }
}

```

## disassembly

```asm
0x1800acc7c  mov     [rsp+arg_0], rbx
0x1800acc81  mov     [rsp+arg_8], rbp
0x1800acc86  mov     [rsp+Sid2], r8
0x1800acc8b  push    rdi
0x1800acc8c  push    r12
0x1800acc8e  push    r13
0x1800acc90  push    r14
0x1800acc92  push    r15
0x1800acc94  sub     rsp, 60h
0x1800acc98  mov     r15, rdx
0x1800acc9b  mov     rdi, rcx
0x1800acc9e  xor     edx, edx; unsigned __int8
0x1800acca0  mov     rcx, r9; struct _LUID *
0x1800acca3  mov     r14, r9
0x1800acca6  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800accab  mov     rbx, rax
0x1800accae  test    rax, rax
0x1800accb1  jz      loc_1800ACE60
0x1800accb7  mov     ecx, [r14]
0x1800accba  lea     r9, [rax+78h]
0x1800accbe  mov     eax, [r14+4]
0x1800accc2  lea     rdx, [r9+10h]
0x1800accc6  lea     r10, [rdi+78h]
0x1800accca  xor     bpl, bpl
0x1800acccd  mov     [rsp+88h+var_40], r10
0x1800accd2  lea     r8, [r10+10h]
0x1800accd6  mov     [rsp+88h+var_48], r8
0x1800accdb  mov     r8d, 224Bh
0x1800acce1  mov     [rsp+88h+var_50], r9
0x1800acce6  lea     r9, aRefreshingOldL; "refreshing old logon session %#x:%#x fo"...
0x1800acced  mov     [rsp+88h+var_58], rdx
0x1800accf2  lea     rdx, aKerbupdateoldl; "KerbUpdateOldLogonSession"
0x1800accf9  mov     [rsp+88h+var_60], ecx
0x1800accfd  mov     ecx, 0Ah
0x1800acd02  mov     [rsp+88h+var_68], eax
0x1800acd06  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800acd0b  lea     rcx, [rbx+50h]; CriticalSection
0x1800acd0f  call    cs:__imp_RtlEnterCriticalSection
0x1800acd15  lea     rax, [rdi+50h]
0x1800acd19  mov     rcx, rax; CriticalSection
0x1800acd1c  mov     [rsp+88h+CriticalSection], rax
0x1800acd21  call    cs:__imp_RtlEnterCriticalSection
0x1800acd27  lea     rcx, [rbx+40h]; struct _LUID *
0x1800acd2b  mov     [rsp+88h+Sid2], 0
0x1800acd37  lea     rdx, [rsp+88h+Sid2]; void **
0x1800acd3f  call    ?GetPrimaryPrincipalSid@@YAJPEAU_LUID@@PEAPEAX@Z; GetPrimaryPrincipalSid(_LUID *,void * *)
0x1800acd44  mov     r12d, eax
0x1800acd47  test    eax, eax
0x1800acd49  js      short loc_1800ACD60
0x1800acd4b  mov     rdx, [rsp+88h+Sid2]; Sid2
0x1800acd53  mov     rcx, [r15+48h]; Sid1
0x1800acd57  call    cs:__imp_RtlEqualSid
0x1800acd5d  mov     bpl, al
0x1800acd60  cmp     [rsp+88h+Sid2], 0
0x1800acd69  jz      short loc_1800ACD78
0x1800acd6b  mov     rcx, [rsp+88h+Sid2]
0x1800acd73  call    KerbFree
0x1800acd78  test    r12d, r12d
0x1800acd7b  js      loc_1800ACE27
0x1800acd81  test    bpl, bpl
0x1800acd84  jz      loc_1800ACE27
0x1800acd8a  cmp     [rsp+88h+arg_28], 0
0x1800acd93  jz      short loc_1800ACDD6
0x1800acd95  mov     rcx, [rdi+190h]
0x1800acd9c  test    rcx, rcx
0x1800acd9f  jz      short loc_1800ACDD6
0x1800acda1  mov     rcx, [rcx+20h]; struct _CERT_CONTEXT *
0x1800acda5  call    ?KerbIsIumCert@@YAEPEBU_CERT_CONTEXT@@@Z; KerbIsIumCert(_CERT_CONTEXT const *)
0x1800acdaa  test    al, al
0x1800acdac  jnz     short loc_1800ACDD6
0x1800acdae  test    dword ptr [rdi+388h], 1000000h
0x1800acdb8  jnz     short loc_1800ACDD6
0x1800acdba  mov     rcx, [rdi+190h]
0x1800acdc1  mov     r8, r14
0x1800acdc4  mov     rdx, [rsp+88h+arg_28]
0x1800acdcc  mov     rcx, [rcx+20h]
0x1800acdd0  call    cs:__imp_LsaIEfsAcceptSmartcardCredentials
0x1800acdd6  mov     edx, [rdi+388h]
0x1800acddc  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x1800acddf  mov     eax, edx
0x1800acde1  bts     edx, 7
0x1800acde5  btr     eax, 7
0x1800acde9  test    byte ptr [r15+50h], 8
0x1800acdee  cmovz   edx, eax
0x1800acdf1  mov     [rdi+388h], edx
0x1800acdf7  mov     rdx, rdi; struct _KERB_LOGON_SESSION *
0x1800acdfa  call    ?KerbUpdateCredentials@@YAJPEAU_KERB_LOGON_SESSION@@0@Z; KerbUpdateCredentials(_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *)
0x1800acdff  test    eax, eax
0x1800ace01  js      short loc_1800ACE27
0x1800ace03  mov     rdi, [rsp+88h+arg_20]
0x1800ace0b  test    rdi, rdi
0x1800ace0e  jz      short loc_1800ACE27
0x1800ace10  mov     rcx, rdi; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ace13  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800ace18  lea     rcx, [rbx+118h]; struct _KERB_TICKET_CACHE *
0x1800ace1f  mov     rdx, rdi; struct _KERB_TICKET_CACHE_ENTRY *
0x1800ace22  call    ?KerbInsertTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE@@PEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbInsertTicketCacheEntry(_KERB_TICKET_CACHE *,_KERB_TICKET_CACHE_ENTRY *)
0x1800ace27  mov     rcx, [rsp+88h+CriticalSection]; CriticalSection
0x1800ace2c  call    cs:__imp_RtlLeaveCriticalSection
0x1800ace32  lea     rcx, [rbx+50h]; CriticalSection
0x1800ace36  call    cs:__imp_RtlLeaveCriticalSection
0x1800ace3c  cmp     dword ptr [rbx+40h], 3E7h
0x1800ace43  jnz     short loc_1800ACE58
0x1800ace45  cmp     dword ptr [rbx+44h], 0
0x1800ace49  jnz     short loc_1800ACE58
0x1800ace4b  call    ?KerbPurgeCompoundedTickets@@YAJXZ; KerbPurgeCompoundedTickets(void)
0x1800ace50  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x1800ace53  call    ?KerbFreeGlobalKdcProxyClientCertContext@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbFreeGlobalKdcProxyClientCertContext(_KERB_LOGON_SESSION *)
0x1800ace58  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x1800ace5b  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x1800ace60  lea     r11, [rsp+88h+var_28]
0x1800ace65  mov     rbx, [r11+30h]
0x1800ace69  mov     rbp, [r11+38h]
0x1800ace6d  mov     rsp, r11
0x1800ace70  pop     r15
0x1800ace72  pop     r14
0x1800ace74  pop     r13
0x1800ace76  pop     r12
0x1800ace78  pop     rdi
0x1800ace79  retn
```
