# KerbGetTgtForService(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY * *,uchar *)

- ea: `0x180041178`
- end: `0x18004174f`
- name: `?KerbGetTgtForService@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@5KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAE@Z`
- size: `1495`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, struct _KERB_CREDENTIAL *@<rdx>, struct _KERB_CREDMAN_CRED *@<r8>, struct _KERB_EXTRA_CRED *@<r9>, struct _KERB_PROXY_LOGON_CRED *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, struct _KERB_TICKET_CACHE_ENTRY **, unsigned __int8 *)`
- caller_count: `7`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bd40`
- `0x18003e488`
- `0x18003eb80`
- `0x180054c88`
- `0x180057f58`
- `0x1800640b0`
- `0x180086d4c`

## callees

- `0x1800063e8`
- `0x18000b5c0`
- `0x18002a150`
- `0x180032964`
- `0x180037aa0`
- `0x180041178`
- `0x18006557c`
- `0x18006ba6c`
- `0x180088264`
- `0x18008b70c`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800414ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800415e1`
- `ntdll!RtlEnterCriticalSection` at `0x1800414ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800415e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18004144a`
- `ntdll!RtlLeaveCriticalSection` at `0x18004144a`

## string_xrefs

- `0x1800411e9`: `KerbGetTgtForService TargetFlags %#x, SuppRealm %wZ, TargetDomain %wZ\n`
- `0x1800411f6`: `KerbGetTgtForService`
- `0x180041262`: `KerbGetTgtForService`
- `0x1800412f0`: `KerbGetTgtForService`
- `0x18004136e`: `KerbGetTgtForService`
- `0x1800413d1`: `KerbGetTgtForService`
- `0x180041414`: `KerbGetTgtForService`
- `0x180041432`: `KerbGetTgtForService`
- `0x180041525`: `KerbGetTgtForService`
- `0x180041572`: `KerbGetTgtForService`
- `0x1800415ff`: `KerbGetTgtForService`
- `0x18004168c`: `KerbGetTgtForService`
- `0x1800416fb`: `KerbGetTgtForService`
- `0x180041255`: `KerbGetTgtForService updating the primary TGT for %#x:%#x\n`
- `0x180041361`: `couldn't find a cross-realm TGT for a target that hit in the SPN oracle - we're probably doomed`
- `0x180041425`: `KerbGetTgtForService refreshing primary TGT for account\n`
- `0x1800415f2`: `KerbGetTgtForService failed to refresh primary TGT: %#x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KerbGetTgtForService(
        struct _RTL_CRITICAL_SECTION *a1,
        struct _KERB_CREDENTIAL *a2,
        struct _KERB_CREDMAN_CRED *a3,
        struct _KERB_EXTRA_CRED *a4,
        struct _KERB_PROXY_LOGON_CRED *a5,
        struct _UNICODE_STRING *a6,
        struct _UNICODE_STRING *a7,
        unsigned int a8,
        struct _KERB_TICKET_CACHE_ENTRY **a9,
        struct _KERB_TICKET_CACHE_ENTRY *a10)
{
  struct _KERB_TICKET_CACHE_ENTRY **v14; // rbx
  unsigned int v16; // esi
  struct _RTL_CRITICAL_SECTION *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *TicketCacheEntryByRealm; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v22; // rax
  Ntlmless::Kerberos *v23; // rcx
  int v24; // r15d
  Ntlmless::Kerberos *v25; // rcx
  int refreshed; // edi
  __int64 v27; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *v28; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *v29; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v30; // rax
  char v31; // [rsp+50h] [rbp-20h]
  struct _KERB_TICKET_CACHE_ENTRY *v32[2]; // [rsp+58h] [rbp-18h] BYREF
  char v33; // [rsp+68h] [rbp-8h]
  struct _KERB_TICKET_CACHE *v37; // [rsp+E0h] [rbp+70h]

  v32[0] = 0;
  v31 = 1;
  v32[1] = (struct _KERB_TICKET_CACHE_ENTRY *)v32;
  v33 = 1;
  *(_BYTE *)a10 = 0;
  v14 = a9;
  *a9 = 0;
  v16 = a8;
  KerbTracerT::Log(
    3,
    "KerbGetTgtForService",
    492,
    "KerbGetTgtForService TargetFlags %#x, SuppRealm %wZ, TargetDomain %wZ\n",
    a8,
    a6,
    a7);
  if ( a4 )
  {
    v17 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a4 + 8);
  }
  else if ( !a2 || (v17 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a2 + 9)) == 0 )
  {
    if ( a3 )
    {
      v17 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a3 + 8);
    }
    else
    {
      v17 = a1 + 3;
      if ( SLOBYTE(a1[22].LockSemaphore) < 0 )
      {
        v16 = a8 | 0x40000;
        v31 = 0;
        KerbTracerT::Log(
          2,
          "KerbGetTgtForService",
          520,
          "KerbGetTgtForService updating the primary TGT for %#x:%#x\n",
          HIDWORD(a1[1].LockSemaphore),
          LODWORD(a1[1].LockSemaphore));
      }
    }
  }
  v18 = 1200000000LL * (KerbGlobalTgtRenewalTime / 0x3C);
  v19 = 10066329000000000LL;
  if ( (v16 & 0x40000) != 0 )
    v18 = 10066329000000000LL;
  a9 = (struct _KERB_TICKET_CACHE_ENTRY **)v18;
  if ( a7->Length )
  {
    TicketCacheEntryByRealm = KerbLocateTicketCacheEntryByRealm((struct _KERB_TICKET_CACHE *)&v17[6], a7, 0);
    v32[0] = TicketCacheEntryByRealm;
    if ( TicketCacheEntryByRealm )
    {
      if ( !KerbTicketIsExpiring(TicketCacheEntryByRealm, (union _LARGE_INTEGER *)&a9) )
      {
        *v14 = v32[0];
        return 0;
      }
      if ( (*((_DWORD *)v32[0] + 41) & 0x400) != 0 )
      {
        KerbTracerT::Log(
          2,
          "KerbGetTgtForService",
          556,
          "is using an expiring cross-realm TGT because it came from an AS_REP callback");
        *v14 = v32[0];
        return 0;
      }
      KerbTracerT::Log(2, "KerbGetTgtForService", 564, "found and rejected a cross-realm TGT because it's too old");
      KerbDereferenceTicketCacheEntry(v32[0]);
      TicketCacheEntryByRealm = 0;
      v32[0] = 0;
    }
  }
  else
  {
    TicketCacheEntryByRealm = v32[0];
  }
  if ( (v16 & 0x10000000) != 0 )
  {
    if ( !a7->Length || !TicketCacheEntryByRealm )
      MicrosoftTelemetryAssertTriggeredNoArgs(v19);
    KerbTracerT::Log(
      2,
      "KerbGetTgtForService",
      573,
      "couldn't find a cross-realm TGT for a target that hit in the SPN oracle - we're probably doomed");
  }
  v37 = (struct _KERB_TICKET_CACHE *)&v17[6];
  v22 = KerbLocateTicketCacheEntryByRealm((struct _KERB_TICKET_CACHE *)&v17[6], a6, 1u);
  v32[0] = v22;
  if ( v22 && !KerbTicketIsExpiring(v22, (union _LARGE_INTEGER *)&a9) )
  {
    if ( a7->Length || (v16 & 0x1000) != 0 )
    {
      KerbTracerT::Log(
        2,
        "KerbGetTgtForService",
        595,
        "is using the primary TGT even though we know this is a cross-realm target");
      *(_BYTE *)a10 = 1;
    }
    *v14 = v32[0];
    return 0;
  }
  if ( (v16 & 0x80000) != 0 && (v16 & 0x40000) != 0 )
  {
    v31 = 0;
    KerbTracerT::Log(16, "KerbGetTgtForService", 614, "Probe extended policies by requesting a fresh primary TGT\n");
  }
  KerbTracerT::Log(2, "KerbGetTgtForService", 617, "KerbGetTgtForService refreshing primary TGT for account\n");
  RtlLeaveCriticalSection(a1 + 2);
  v24 = (Ntlmless::Kerberos::IsEnabled(v23) << 29) + 0x80000;
  if ( !Ntlmless::Kerberos::IsEnabled(v25) || (v17[10].LockCount & 0x1000000) == 0 )
  {
    refreshed = KerbRefreshPrimaryTgt(
                  (struct _KERB_LOGON_SESSION *)a1,
                  a2,
                  a3,
                  a4,
                  a5,
                  a6,
                  v16 & v24,
                  (PRTL_CRITICAL_SECTION)((unsigned __int64)v32[0] & -(__int64)(v31 != 0)),
                  1);
    RtlEnterCriticalSection(a1 + 2);
    if ( refreshed < 0 )
      KerbTracerT::Log(
        2,
        "KerbGetTgtForService",
        683,
        "KerbGetTgtForService failed to refresh primary TGT: %#x\n",
        refreshed);
    v28 = v32[0];
    if ( v32[0] )
    {
      if ( refreshed >= 0 )
      {
        KerbRemoveTicketCacheEntry(v32[0]);
        v28 = v32[0];
      }
      KerbDereferenceTicketCacheEntry(v28);
      v32[0] = 0;
    }
    if ( a7->Length )
    {
      v29 = KerbLocateTicketCacheEntryByRealm(v37, a7, 0);
      v32[0] = v29;
      if ( v29 )
      {
        if ( !KerbTicketIsExpiring(v29, (union _LARGE_INTEGER *)&a9) )
        {
          *v14 = v32[0];
          return 0;
        }
        if ( (*((_DWORD *)v32[0] + 41) & 0x400) != 0 )
        {
          KerbTracerT::Log(
            2,
            "KerbGetTgtForService",
            726,
            "is using an expiring cross-realm TGT because it came from an AS_REP callback");
          *v14 = v32[0];
          return 0;
        }
        KerbDereferenceTicketCacheEntry(v32[0]);
        v32[0] = 0;
      }
    }
    v30 = KerbLocateTicketCacheEntryByRealm(v37, a6, 1u);
    v32[0] = v30;
    if ( v30 )
    {
      *v14 = v30;
      if ( a7->Length || (v16 & 0x1000) != 0 )
        *(_BYTE *)a10 = 1;
      return 0;
    }
    KerbTracerT::Log(1, "KerbGetTgtForService", 759, "didn't manage to find any TGTs at all");
    if ( refreshed >= 0 )
    {
      if ( v32[0] )
        KerbDereferenceTicketCacheEntry(v32[0]);
      return 2148074254LL;
    }
    if ( v32[0] )
      KerbDereferenceTicketCacheEntry(v32[0]);
    return (unsigned int)refreshed;
  }
  a10 = 0;
  refreshed = KerbGetTicketForCredential((struct _KERB_LOGON_SESSION *)a1, a2, a3, a4, a5, a6, v16 & v24, &a10);
  RtlEnterCriticalSection(a1 + 2);
  if ( refreshed < 0 )
  {
    KerbTracerT::Log(
      1,
      "KerbGetTgtForService",
      654,
      "KerbGetTicketForCredential failed to get TGT for local user. Status: %#x. Tgt present? %i.",
      refreshed,
      a10 != 0);
    if ( v32[0] )
      KerbDereferenceTicketCacheEntry(v32[0]);
    return (unsigned int)refreshed;
  }
  if ( a10 )
  {
    *v14 = a10;
    a10 = 0;
    if ( v32[0] )
      KerbDereferenceTicketCacheEntry(v32[0]);
    return 0;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v27);
  KerbTracerT::Log(
    1,
    "KerbGetTgtForService",
    661,
    "KerbGetTicketForCredential succeeded, but no TGT for local user. Status: %#x. Tgt present? %i.",
    refreshed,
    a10 != 0);
  if ( v32[0] )
    KerbDereferenceTicketCacheEntry(v32[0]);
  return 2148074244LL;
}

```

## disassembly

```asm
0x180041178  mov     r11, rsp
0x18004117b  mov     [r11+8], rbx
0x18004117f  mov     [r11+20h], r9
0x180041183  mov     [r11+18h], r8
0x180041187  mov     [r11+10h], rdx
0x18004118b  push    rbp
0x18004118c  push    rsi
0x18004118d  push    rdi
0x18004118e  push    r12
0x180041190  push    r13
0x180041192  push    r14
0x180041194  push    r15
0x180041196  mov     rbp, rsp
0x180041199  sub     rsp, 70h
0x18004119d  mov     r12, r9
0x1800411a0  mov     r15, r8
0x1800411a3  mov     rdi, rdx
0x1800411a6  mov     r13, rcx
0x1800411a9  xor     edx, edx
0x1800411ab  mov     [rbp+var_18], rdx
0x1800411af  mov     [rbp+var_20], 1
0x1800411b3  lea     rcx, [rbp+var_18]
0x1800411b7  mov     [rbp+var_10], rcx
0x1800411bb  mov     [rbp+var_8], 1
0x1800411bf  mov     rax, [rbp+arg_48]
0x1800411c6  mov     [rax], dl
0x1800411c8  mov     rbx, qword ptr [rbp+arg_40]
0x1800411cf  mov     [rbx], rdx
0x1800411d2  mov     r14, [rbp+arg_30]
0x1800411d6  mov     [r11-78h], r14
0x1800411da  mov     rax, [rbp+arg_28]
0x1800411de  mov     [r11-80h], rax
0x1800411e2  mov     esi, [rbp+arg_38]
0x1800411e5  mov     dword ptr [rsp+70h+var_50], esi
0x1800411e9  lea     r9, aKerbgettgtfors; "KerbGetTgtForService TargetFlags %#x, S"...
0x1800411f0  mov     r8d, 1ECh
0x1800411f6  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x1800411fd  mov     ecx, 3
0x180041202  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041207  test    r12, r12
0x18004120a  jz      short loc_180041216
0x18004120c  mov     rdi, [r12+40h]
0x180041211  xor     r12d, r12d
0x180041214  jmp     short loc_180041273
0x180041216  test    rdi, rdi
0x180041219  jz      short loc_180041224
0x18004121b  mov     rdi, [rdi+48h]
0x18004121f  test    rdi, rdi
0x180041222  jnz     short loc_180041273
0x180041224  test    r15, r15
0x180041227  jz      short loc_18004122F
0x180041229  mov     rdi, [r15+40h]
0x18004122d  jmp     short loc_180041273
0x18004122f  lea     rdi, [r13+78h]
0x180041233  test    byte ptr [r13+388h], 80h
0x18004123b  jz      short loc_180041273
0x18004123d  bts     esi, 12h
0x180041241  mov     [rbp+var_20], r12b
0x180041245  mov     eax, [r13+40h]
0x180041249  mov     dword ptr [rsp+70h+var_48], eax
0x18004124d  mov     eax, [r13+44h]
0x180041251  mov     dword ptr [rsp+70h+var_50], eax
0x180041255  lea     r9, aKerbgettgtfors_2; "KerbGetTgtForService updating the prima"...
0x18004125c  mov     r8d, 208h
0x180041262  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x180041269  mov     ecx, 2
0x18004126e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041273  mov     eax, 88888889h
0x180041278  mul     cs:?KerbGlobalTgtRenewalTime@@3KA; ulong KerbGlobalTgtRenewalTime
0x18004127e  shr     edx, 5
0x180041281  lea     eax, [rdx+rdx]
0x180041284  imul    rax, 23C34600h
0x18004128b  mov     r15d, esi
0x18004128e  and     r15d, 40000h
0x180041295  mov     rcx, 23C345DC3CBA00h
0x18004129f  cmovnz  rax, rcx
0x1800412a3  mov     qword ptr [rbp+arg_40], rax
0x1800412aa  cmp     [r14], r12w
0x1800412ae  jz      loc_180041347
0x1800412b4  lea     rcx, [rdi+0F0h]; struct _KERB_TICKET_CACHE *
0x1800412bb  xor     r8d, r8d; unsigned int
0x1800412be  mov     rdx, r14; struct _UNICODE_STRING *
0x1800412c1  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x1800412c6  mov     [rbp+var_18], rax
0x1800412ca  test    rax, rax
0x1800412cd  jz      short loc_18004134B
0x1800412cf  lea     rdx, [rbp+arg_40]; union _LARGE_INTEGER *
0x1800412d6  mov     rcx, rax; struct _KERB_TICKET_CACHE_ENTRY *
0x1800412d9  call    ?KerbTicketIsExpiring@@YAEPEAU_KERB_TICKET_CACHE_ENTRY@@PEAT_LARGE_INTEGER@@@Z; KerbTicketIsExpiring(_KERB_TICKET_CACHE_ENTRY *,_LARGE_INTEGER *)
0x1800412de  test    al, al
0x1800412e0  mov     rax, [rbp+var_18]
0x1800412e4  jnz     short loc_1800412F0
0x1800412e6  mov     [rbx], rax
0x1800412e9  xor     eax, eax
0x1800412eb  jmp     loc_180041737
0x1800412f0  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x1800412f7  mov     ecx, 2
0x1800412fc  test    dword ptr [rax+0A4h], 400h
0x180041306  jz      short loc_180041323
0x180041308  lea     r9, aIsUsingAnExpir; "is using an expiring cross-realm TGT be"...
0x18004130f  mov     r8d, 22Ch
0x180041315  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004131a  mov     rax, [rbp+var_18]
0x18004131e  mov     [rbx], rax
0x180041321  jmp     short loc_1800412E9
0x180041323  lea     r9, aFoundAndReject; "found and rejected a cross-realm TGT be"...
0x18004132a  mov     r8d, 234h
0x180041330  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041335  mov     rcx, [rbp+var_18]; struct _KERB_TICKET_CACHE_ENTRY *
0x180041339  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004133e  mov     rax, r12
0x180041341  mov     [rbp+var_18], rax
0x180041345  jmp     short loc_18004134B
0x180041347  mov     rax, [rbp+var_18]
0x18004134b  bt      esi, 1Ch
0x18004134f  jnb     short loc_18004137F
0x180041351  cmp     [r14], r12w
0x180041355  jz      short loc_18004135C
0x180041357  test    rax, rax
0x18004135a  jnz     short loc_180041361
0x18004135c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041361  lea     r9, aCouldnTFindACr; "couldn't find a cross-realm TGT for a t"...
0x180041368  mov     r8d, 23Dh
0x18004136e  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x180041375  mov     ecx, 2
0x18004137a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18004137f  lea     rax, [rdi+0F0h]
0x180041386  mov     [rbp+arg_30], rax
0x18004138a  mov     r8d, 1; unsigned int
0x180041390  mov     rdx, [rbp+arg_28]; struct _UNICODE_STRING *
0x180041394  mov     rcx, rax; struct _KERB_TICKET_CACHE *
0x180041397  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x18004139c  mov     [rbp+var_18], rax
0x1800413a0  test    rax, rax
0x1800413a3  jz      short loc_1800413F8
0x1800413a5  lea     rdx, [rbp+arg_40]; union _LARGE_INTEGER *
0x1800413ac  mov     rcx, rax; struct _KERB_TICKET_CACHE_ENTRY *
0x1800413af  call    ?KerbTicketIsExpiring@@YAEPEAU_KERB_TICKET_CACHE_ENTRY@@PEAT_LARGE_INTEGER@@@Z; KerbTicketIsExpiring(_KERB_TICKET_CACHE_ENTRY *,_LARGE_INTEGER *)
0x1800413b4  test    al, al
0x1800413b6  jnz     short loc_1800413F8
0x1800413b8  cmp     [r14], r12w
0x1800413bc  jnz     short loc_1800413C4
0x1800413be  bt      esi, 0Ch
0x1800413c2  jnb     short loc_1800413EC
0x1800413c4  lea     r9, aIsUsingThePrim; "is using the primary TGT even though we"...
0x1800413cb  mov     r8d, 253h
0x1800413d1  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x1800413d8  mov     ecx, 2
0x1800413dd  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800413e2  mov     rax, [rbp+arg_48]
0x1800413e9  mov     byte ptr [rax], 1
0x1800413ec  mov     rax, [rbp+var_18]
0x1800413f0  mov     [rbx], rax
0x1800413f3  jmp     loc_1800412E9
0x1800413f8  bt      esi, 13h
0x1800413fc  jnb     short loc_180041425
0x1800413fe  test    r15d, r15d
0x180041401  jz      short loc_180041425
0x180041403  mov     [rbp+var_20], r12b
0x180041407  lea     r9, aProbeExtendedP_0; "Probe extended policies by requesting a"...
0x18004140e  mov     r8d, 266h
0x180041414  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x18004141b  mov     ecx, 10h
0x180041420  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041425  lea     r9, aKerbgettgtfors_4; "KerbGetTgtForService refreshing primary"...
0x18004142c  mov     r8d, 269h
0x180041432  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x180041439  mov     ecx, 2
0x18004143e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041443  lea     r12, [r13+50h]
0x180041447  mov     rcx, r12; CriticalSection
0x18004144a  call    cs:__imp_RtlLeaveCriticalSection
0x180041450  call    ?IsEnabled@Kerberos@Ntlmless@@YA_NXZ; Ntlmless::Kerberos::IsEnabled(void)
0x180041455  movzx   r15d, al
0x180041459  shl     r15d, 1Dh
0x18004145d  add     r15d, 80000h
0x180041464  call    ?IsEnabled@Kerberos@Ntlmless@@YA_NXZ; Ntlmless::Kerberos::IsEnabled(void)
0x180041469  test    al, al
0x18004146b  jz      loc_18004159A
0x180041471  test    dword ptr [rdi+198h], 1000000h
0x18004147b  jz      loc_18004159A
0x180041481  xor     r14d, r14d
0x180041484  mov     [rbp+arg_48], r14
0x18004148b  and     r15d, esi
0x18004148e  lea     rax, [rbp+arg_48]
0x180041495  mov     [rsp+70h+var_38], rax; struct _KERB_TICKET_CACHE_ENTRY **
0x18004149a  mov     [rsp+70h+var_40], r15d; unsigned int
0x18004149f  mov     rax, [rbp+arg_28]
0x1800414a3  mov     [rsp+70h+var_48], rax; struct _UNICODE_STRING *
0x1800414a8  mov     rax, [rbp+arg_20]
0x1800414ac  mov     [rsp+70h+var_50], rax; struct _KERB_PROXY_LOGON_CRED *
0x1800414b1  mov     r9, [rbp+arg_18]; struct _KERB_EXTRA_CRED *
0x1800414b5  mov     r8, [rbp+arg_10]; struct _KERB_CREDMAN_CRED *
0x1800414b9  mov     rdx, [rbp+arg_8]; struct _KERB_CREDENTIAL *
0x1800414bd  mov     rcx, r13; struct _KERB_LOGON_SESSION *
0x1800414c0  call    ?KerbGetTicketForCredential@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbGetTicketForCredential(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY * *)
0x1800414c5  mov     edi, eax
0x1800414c7  mov     rcx, r12; CriticalSection
0x1800414ca  call    cs:__imp_RtlEnterCriticalSection
0x1800414d0  test    edi, edi
0x1800414d2  js      short loc_180041550
0x1800414d4  mov     rax, [rbp+arg_48]
0x1800414db  test    rax, rax
0x1800414de  jz      short loc_1800414FE
0x1800414e0  mov     [rbx], rax
0x1800414e3  mov     [rbp+arg_48], r14
0x1800414ea  mov     rcx, [rbp+var_18]; struct _KERB_TICKET_CACHE_ENTRY *
0x1800414ee  test    rcx, rcx
0x1800414f1  jz      short loc_1800414F9
0x1800414f3  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x1800414f8  nop
0x1800414f9  jmp     loc_1800412E9
0x1800414fe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180041503  mov     eax, r14d
0x180041506  cmp     [rbp+arg_48], r14
0x18004150d  setnz   al
0x180041510  mov     dword ptr [rsp+70h+var_48], eax
0x180041514  mov     dword ptr [rsp+70h+var_50], edi
0x180041518  lea     r9, aKerbgetticketf_3; "KerbGetTicketForCredential succeeded, b"...
0x18004151f  mov     r8d, 295h
0x180041525  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x18004152c  mov     ecx, 1
0x180041531  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041536  nop
0x180041537  mov     rcx, [rbp+var_18]; struct _KERB_TICKET_CACHE_ENTRY *
0x18004153b  test    rcx, rcx
0x18004153e  jz      short loc_180041546
0x180041540  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180041545  nop
0x180041546  mov     eax, 80090304h
0x18004154b  jmp     loc_180041737
0x180041550  mov     eax, r14d
0x180041553  cmp     [rbp+arg_48], r14
0x18004155a  setnz   al
0x18004155d  mov     dword ptr [rsp+70h+var_48], eax
0x180041561  mov     dword ptr [rsp+70h+var_50], edi
0x180041565  lea     r9, aKerbgetticketf_0; "KerbGetTicketForCredential failed to ge"...
0x18004156c  mov     r8d, 28Eh
0x180041572  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x180041579  mov     ecx, 1
0x18004157e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041583  nop
0x180041584  mov     rcx, [rbp+var_18]; struct _KERB_TICKET_CACHE_ENTRY *
0x180041588  test    rcx, rcx
0x18004158b  jz      short loc_180041593
0x18004158d  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180041592  nop
0x180041593  mov     eax, edi
0x180041595  jmp     loc_180041737
0x18004159a  neg     [rbp+var_20]
0x18004159d  sbb     rax, rax
0x1800415a0  and     rax, [rbp+var_18]
0x1800415a4  and     r15d, esi
0x1800415a7  mov     [rsp+70h+var_30], 1; char
0x1800415ac  mov     [rsp+70h+var_38], rax; PRTL_CRITICAL_SECTION
0x1800415b1  mov     [rsp+70h+var_40], r15d; unsigned int
0x1800415b6  mov     rax, [rbp+arg_28]
0x1800415ba  mov     [rsp+70h+var_48], rax; struct _UNICODE_STRING *
0x1800415bf  mov     rax, [rbp+arg_20]
0x1800415c3  mov     [rsp+70h+var_50], rax; struct _KERB_PROXY_LOGON_CRED *
0x1800415c8  mov     r9, [rbp+arg_18]; struct _KERB_EXTRA_CRED *
0x1800415cc  mov     r8, [rbp+arg_10]; struct _KERB_CREDMAN_CRED *
0x1800415d0  mov     rdx, [rbp+arg_8]; struct _KERB_CREDENTIAL *
0x1800415d4  mov     rcx, r13; struct _KERB_LOGON_SESSION *
0x1800415d7  call    ?KerbRefreshPrimaryTgt@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_CREDMAN_CRED@@PEAU_KERB_EXTRA_CRED@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_UNICODE_STRING@@KPEAU_KERB_TICKET_CACHE_ENTRY@@E@Z; KerbRefreshPrimaryTgt(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_CREDMAN_CRED *,_KERB_EXTRA_CRED *,_KERB_PROXY_LOGON_CRED *,_UNICODE_STRING *,ulong,_KERB_TICKET_CACHE_ENTRY *,uchar)
0x1800415dc  mov     edi, eax
0x1800415de  mov     rcx, r12; CriticalSection
0x1800415e1  call    cs:__imp_RtlEnterCriticalSection
0x1800415e7  xor     r12d, r12d
0x1800415ea  test    edi, edi
0x1800415ec  jns     short loc_180041610
0x1800415ee  mov     dword ptr [rsp+70h+var_50], edi
0x1800415f2  lea     r9, aKerbgettgtfors_1; "KerbGetTgtForService failed to refresh "...
0x1800415f9  mov     r8d, 2ABh
0x1800415ff  lea     rdx, aKerbgettgtfors_3; "KerbGetTgtForService"
0x180041606  lea     ecx, [r12+2]
0x18004160b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180041610  mov     rcx, [rbp+var_18]; struct _KERB_TICKET_CACHE_ENTRY *
0x180041614  test    rcx, rcx
0x180041617  jz      short loc_18004162F
0x180041619  test    edi, edi
0x18004161b  js      short loc_180041626
0x18004161d  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180041622  mov     rcx, [rbp+var_18]; struct _KERB_TICKET_CACHE_ENTRY *
0x180041626  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18004162b  mov     [rbp+var_18], r12
0x18004162f  mov     r15, [rbp+arg_30]
0x180041633  cmp     [r14], r12w
0x180041637  jz      short loc_1800416B2
0x180041639  xor     r8d, r8d; unsigned int
0x18004163c  mov     rdx, r14; struct _UNICODE_STRING *
0x18004163f  mov     rcx, r15; struct _KERB_TICKET_CACHE *
0x180041642  call    ?KerbLocateTicketCacheEntryByRealm@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_UNICODE_STRING@@K@Z; KerbLocateTicketCacheEntryByRealm(_KERB_TICKET_CACHE *,_UNICODE_STRING *,ulong)
0x180041647  mov     [rbp+var_18], rax
0x18004164b  test    rax, rax
0x18004164e  jz      short loc_1800416B2
0x180041650  lea     rdx, [rbp+arg_40]; union _LARGE_INTEGER *
0x180041657  mov     rcx, rax; struct _KERB_TICKET_CACHE_ENTRY *
0x18004165a  call    ?KerbTicketIsExpiring@@YAEPEAU_KERB_TICKET_CACHE_ENTRY@@PEAT_LARGE_INTEGER@@@Z; KerbTicketIsExpiring(_KERB_TICKET_CACHE_ENTRY *,_LARGE_INTEGER *)
0x18004165f  test    al, al
  ... truncated ...
```
