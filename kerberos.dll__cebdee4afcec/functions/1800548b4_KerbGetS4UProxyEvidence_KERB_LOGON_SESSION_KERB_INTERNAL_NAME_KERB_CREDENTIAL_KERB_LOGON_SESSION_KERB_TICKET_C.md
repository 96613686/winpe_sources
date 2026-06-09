# KerbGetS4UProxyEvidence(_KERB_LOGON_SESSION *,_KERB_INTERNAL_NAME *,_KERB_CREDENTIAL *,_KERB_LOGON_SESSION * *,_KERB_TICKET_CACHE_ENTRY * *)

- ea: `0x1800548b4`
- end: `0x180054c7f`
- name: `?KerbGetS4UProxyEvidence@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_INTERNAL_NAME@@PEAU_KERB_CREDENTIAL@@PEAPEAU1@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(struct _KERB_LOGON_SESSION *, struct _KERB_INTERNAL_NAME *, struct _KERB_CREDENTIAL *, struct _KERB_LOGON_SESSION **, struct _KERB_TICKET_CACHE_ENTRY **)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x180021574`
- `0x1800cc8a8`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x180054508`
- `0x1800548b4`
- `0x180054c88`
- `0x180058380`
- `0x18005de50`
- `0x180066ee0`
- `0x18008b70c`
- `0x180090d08`
- `0x18009e288`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180054951`
- `ntdll!RtlCopyLuid` at `0x180054951`
- `ntdll!RtlEnterCriticalSection` at `0x1800549d3`
- `ntdll!RtlEnterCriticalSection` at `0x180054a8a`
- `ntdll!RtlEnterCriticalSection` at `0x180054baa`
- `ntdll!RtlEnterCriticalSection` at `0x1800549d3`
- `ntdll!RtlEnterCriticalSection` at `0x180054a8a`
- `ntdll!RtlEnterCriticalSection` at `0x180054baa`
- `ntdll!RtlLeaveCriticalSection` at `0x180054a0b`
- `ntdll!RtlLeaveCriticalSection` at `0x180054af4`
- `ntdll!RtlLeaveCriticalSection` at `0x180054bcc`
- `ntdll!RtlLeaveCriticalSection` at `0x180054c4a`
- `ntdll!RtlLeaveCriticalSection` at `0x180054a0b`
- `ntdll!RtlLeaveCriticalSection` at `0x180054af4`
- `ntdll!RtlLeaveCriticalSection` at `0x180054bcc`
- `ntdll!RtlLeaveCriticalSection` at `0x180054c4a`

## pseudocode

```c
__int64 __fastcall KerbGetS4UProxyEvidence(
        struct _KERB_LOGON_SESSION *a1,
        struct _KERB_INTERNAL_NAME *a2,
        struct _KERB_CREDENTIAL *a3,
        struct _KERB_LOGON_SESSION **a4,
        struct _KERB_TICKET_CACHE_ENTRY **a5)
{
  struct _LSA_SECPKG_FUNCTION_TABLE *v5; // rax
  char v8; // r12
  struct _KERB_LOGON_SESSION *v9; // rdi
  void (__fastcall *GetExtendedCallFlags)(int *); // rax
  int CallingLuid; // ebx
  int v12; // r12d
  struct _KERB_TICKET_CACHE_ENTRY *v13; // rax
  unsigned __int8 v14; // r8
  int S4USelfServiceTicket; // eax
  const char *v16; // r9
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // rcx
  struct _KERB_TICKET_CACHE_ENTRY *v20; // rdx
  struct _KERB_INTERNAL_NAME *v22; // [rsp+28h] [rbp-61h]
  struct _UNICODE_STRING *v23; // [rsp+30h] [rbp-59h]
  unsigned int v24; // [rsp+68h] [rbp-21h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v25; // [rsp+70h] [rbp-19h] BYREF
  struct _LUID DestinationLuid; // [rsp+78h] [rbp-11h] BYREF
  struct _KERB_INTERNAL_NAME *v27; // [rsp+80h] [rbp-9h] BYREF
  struct _LUID SourceLuid; // [rsp+88h] [rbp-1h] BYREF
  struct _UNICODE_STRING v29; // [rsp+90h] [rbp+7h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v30; // [rsp+F0h] [rbp+67h] BYREF
  int v31; // [rsp+F8h] [rbp+6Fh] BYREF
  struct _KERB_LOGON_SESSION **v32; // [rsp+100h] [rbp+77h]

  v32 = a4;
  v30 = a2;
  v5 = LsaFunctions;
  v24 = 0;
  DestinationLuid = 0;
  v8 = 0;
  v25 = 0;
  v29 = 0;
  *a5 = 0;
  v9 = 0;
  *a4 = 0;
  GetExtendedCallFlags = (void (__fastcall *)(int *))v5->GetExtendedCallFlags;
  v27 = 0;
  SourceLuid = (struct _LUID)999LL;
  v31 = 0;
  GetExtendedCallFlags(&v31);
  if ( (*((_BYTE *)a3 + 64) & 0x10) != 0 || (v31 & 4) != 0 )
  {
    v16 = "KerbGetS4UProxyEvidence autologon restricted for %#x:%#x\n";
    LODWORD(v23) = *((_DWORD *)a1 + 16);
    v17 = 7358;
    v18 = *((_DWORD *)a1 + 17);
    v19 = 1;
    goto LABEL_26;
  }
  if ( *((_BYTE *)a3 + 120) )
  {
    CallingLuid = 0;
    RtlCopyLuid(&DestinationLuid, &SourceLuid);
    goto LABEL_6;
  }
  CallingLuid = KerbGetCallingLuid(&DestinationLuid, (void *)*((int *)a3 + 17));
  if ( CallingLuid >= 0 )
  {
LABEL_6:
    if ( !KerbAllowedForS4U2Proxy(&DestinationLuid) )
    {
      CallingLuid = -1073741637;
      KerbTracerT::Log(
        1,
        "KerbGetS4UProxyEvidence",
        7385,
        "KerbGetS4UProxyEvidence not supported %#x:%#x\n",
        DestinationLuid.HighPart,
        DestinationLuid.LowPart);
      goto LABEL_27;
    }
    v9 = KerbLocateLogonSession(&DestinationLuid, 0);
    if ( !v9 )
    {
      CallingLuid = -1073741729;
      goto LABEL_27;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
    v12 = *((_DWORD *)a1 + 226);
    v25 = KerbLocateS4UTicketCacheEntry((struct _KERB_LOGON_SESSION *)((char *)a1 + 320), &DestinationLuid, 0, 0, 0, 1u);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
    v13 = v25;
    if ( !v25 )
      goto LABEL_14;
    if ( (*((_BYTE *)v25 + 164) & 0x10) != 0 )
    {
      KerbTracerT::Log(
        2,
        "KerbGetS4UProxyEvidence",
        7425,
        "KerbGetS4UProxyEvidence does not allow evidence ticket encrypted in SKEY\n");
      KerbDereferenceTicketCacheEntry(v25);
      v13 = 0;
      v25 = 0;
    }
    if ( !v13 )
    {
LABEL_14:
      if ( (v12 & 0x100) == 0 )
      {
        KerbTracerT::Log(1, "KerbGetS4UProxyEvidence", 7438, "Non Fwdable logon session used in S4u\n");
        CallingLuid = -1073741729;
        v8 = 0;
        goto LABEL_27;
      }
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
      v8 = 1;
      CallingLuid = KerbProcessTargetNames(
                      (const struct _UNICODE_STRING *)((char *)a1 + 120),
                      0,
                      0,
                      1u,
                      0,
                      &v24,
                      &v27,
                      &v29);
      if ( CallingLuid < 0 )
        goto LABEL_27;
      KerbFreeString(&v29);
      CallingLuid = KerbDuplicateStringEx(&v29, (const struct _UNICODE_STRING *)((char *)a1 + 136), v14);
      if ( CallingLuid < 0 )
        goto LABEL_27;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
      v8 = 0;
      S4USelfServiceTicket = KerbGetS4USelfServiceTicket(v9, a1, 0, &v27, 0, &v29, &v25, 0, 0, 0, 0, 0);
      CallingLuid = S4USelfServiceTicket;
      if ( S4USelfServiceTicket < 0 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetS4UProxyEvidence",
          7496,
          "KerbGetS4UProxyEvidence failed to get S4U ticket - %x\n",
          S4USelfServiceTicket);
        goto LABEL_27;
      }
      if ( (*((_BYTE *)v25 + 164) & 0x10) != 0 )
      {
        v16 = "KerbGetS4UProxyEvidence does not allow u2u evidence key, caller %#x:%#x\n";
        LODWORD(v23) = *((_DWORD *)v9 + 16);
        v17 = 7504;
        v18 = *((_DWORD *)v9 + 17);
        v19 = 2;
LABEL_26:
        LODWORD(v22) = v18;
        KerbTracerT::Log(v19, "KerbGetS4UProxyEvidence", v17, v16, v22, v23);
        CallingLuid = -2146893042;
        goto LABEL_27;
      }
      v30 = 0;
      CallingLuid = KerbDuplicateTicketCacheEntry(v25, &v30);
      if ( CallingLuid < 0 )
        goto LABEL_27;
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
      v20 = v30;
      *((_DWORD *)a1 + 226) |= 0x100u;
      KerbInsertTicketCacheEntry((struct _KERB_LOGON_SESSION *)((char *)a1 + 320), v20);
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
      KerbDereferenceTicketCacheEntry(v30);
      v13 = v25;
    }
    v25 = 0;
    *v32 = v9;
    *a5 = v13;
    goto LABEL_33;
  }
LABEL_27:
  if ( v25 )
    KerbDereferenceTicketCacheEntry(v25);
  if ( v9 )
    KerbDereferenceLogonSession(v9);
  if ( v8 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 2);
LABEL_33:
  KerbFreeKdcName(&v27);
  KerbFreeString(&v29);
  return (unsigned int)CallingLuid;
}

```

## disassembly

```asm
0x1800548b4  mov     rax, rsp
0x1800548b7  mov     [rax+8], rbx
0x1800548bb  mov     [rax+20h], r9
0x1800548bf  mov     [rax+10h], rdx
0x1800548c3  push    rbp
0x1800548c4  push    rsi
0x1800548c5  push    rdi
0x1800548c6  push    r12
0x1800548c8  push    r13
0x1800548ca  push    r14
0x1800548cc  push    r15
0x1800548ce  lea     rbp, [rax-57h]
0x1800548d2  sub     rsp, 0A0h
0x1800548d9  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800548e0  xor     r13d, r13d
0x1800548e3  mov     r14, rcx
0x1800548e6  mov     [rbp+4Fh+var_70], r13d
0x1800548ea  mov     rcx, [rbp+4Fh+arg_20]
0x1800548ee  xorps   xmm0, xmm0
0x1800548f1  mov     rbx, r8
0x1800548f4  mov     qword ptr [rbp+4Fh+DestinationLuid.LowPart], r13
0x1800548f8  mov     r12b, r13b
0x1800548fb  mov     [rbp+4Fh+var_68], r13
0x1800548ff  movups  xmmword ptr [rbp+4Fh+var_48.Length], xmm0
0x180054903  mov     [rcx], r13
0x180054906  mov     edi, r13d
0x180054909  mov     [r9], r13
0x18005490c  lea     rcx, [rbp+4Fh+arg_10]
0x180054910  mov     rax, [rax+1B0h]
0x180054917  mov     [rbp+4Fh+var_58], r13
0x18005491b  mov     qword ptr [rbp+4Fh+SourceLuid.LowPart], 3E7h
0x180054923  mov     [rbp+4Fh+arg_10], r13d
0x180054927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005492c  test    byte ptr [rbx+40h], 10h
0x180054930  jnz     loc_180054BF3
0x180054936  test    byte ptr [rbp+4Fh+arg_10], 4
0x18005493a  jnz     loc_180054BF3
0x180054940  lea     rcx, [rbp+4Fh+DestinationLuid]; DestinationLuid
0x180054944  cmp     [rbx+78h], r13b
0x180054948  jz      short loc_180054959
0x18005494a  lea     rdx, [rbp+4Fh+SourceLuid]; SourceLuid
0x18005494e  mov     ebx, r13d
0x180054951  call    cs:__imp_RtlCopyLuid
0x180054957  jmp     short loc_18005496C
0x180054959  movsxd  rdx, dword ptr [rbx+44h]; void *
0x18005495d  call    ?KerbGetCallingLuid@@YAJPEAU_LUID@@PEAX@Z; KerbGetCallingLuid(_LUID *,void *)
0x180054962  mov     ebx, eax
0x180054964  test    eax, eax
0x180054966  js      loc_180054C26
0x18005496c  lea     rcx, [rbp+4Fh+DestinationLuid]; struct _LUID *
0x180054970  call    ?KerbAllowedForS4U2Proxy@@YAEPEAU_LUID@@@Z; KerbAllowedForS4U2Proxy(_LUID *)
0x180054975  test    al, al
0x180054977  jnz     short loc_1800549AF
0x180054979  mov     eax, [rbp+4Fh+DestinationLuid.LowPart]
0x18005497c  lea     r9, aKerbgets4uprox_2; "KerbGetS4UProxyEvidence not supported %"...
0x180054983  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180054987  lea     rdx, aKerbgets4uprox_6; "KerbGetS4UProxyEvidence"
0x18005498e  mov     eax, [rbp+4Fh+DestinationLuid.HighPart]
0x180054991  mov     r8d, 1CD9h
0x180054997  mov     ecx, 1
0x18005499c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800549a0  mov     ebx, 0C00000BBh
0x1800549a5  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800549aa  jmp     loc_180054C26
0x1800549af  xor     edx, edx; unsigned __int8
0x1800549b1  lea     rcx, [rbp+4Fh+DestinationLuid]; struct _LUID *
0x1800549b5  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800549ba  mov     rdi, rax
0x1800549bd  test    rax, rax
0x1800549c0  jnz     short loc_1800549CC
0x1800549c2  mov     ebx, 0C000005Fh
0x1800549c7  jmp     loc_180054C26
0x1800549cc  lea     r15, [r14+50h]
0x1800549d0  mov     rcx, r15; CriticalSection
0x1800549d3  call    cs:__imp_RtlEnterCriticalSection
0x1800549d9  mov     r12d, [r14+388h]
0x1800549e0  lea     rcx, [r14+140h]; struct _KERB_TICKET_CACHE *
0x1800549e7  mov     esi, 1
0x1800549ec  lea     rdx, [rbp+4Fh+DestinationLuid]; struct _LUID *
0x1800549f0  mov     dword ptr [rsp+0D0h+var_A8], esi; unsigned int
0x1800549f4  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800549f7  xor     r8d, r8d; struct _KERB_INTERNAL_NAME *
0x1800549fa  mov     [rsp+0D0h+var_B0], r13; struct _KERB_INTERNAL_NAME *
0x1800549ff  call    ?KerbLocateS4UTicketCacheEntry@@YAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_TICKET_CACHE@@PEAU_LUID@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@2K@Z; KerbLocateS4UTicketCacheEntry(_KERB_TICKET_CACHE *,_LUID *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,ulong)
0x180054a04  mov     rcx, r15; CriticalSection
0x180054a07  mov     [rbp+4Fh+var_68], rax
0x180054a0b  call    cs:__imp_RtlLeaveCriticalSection
0x180054a11  mov     rax, [rbp+4Fh+var_68]
0x180054a15  test    rax, rax
0x180054a18  jz      short loc_180054A58
0x180054a1a  test    byte ptr [rax+0A4h], 10h
0x180054a21  jz      short loc_180054A4F
0x180054a23  lea     r9, aKerbgets4uprox_1; "KerbGetS4UProxyEvidence does not allow "...
0x180054a2a  mov     r8d, 1D01h
0x180054a30  lea     rdx, aKerbgets4uprox_6; "KerbGetS4UProxyEvidence"
0x180054a37  lea     ecx, [rsi+1]
0x180054a3a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180054a3f  mov     rcx, [rbp+4Fh+var_68]; struct _KERB_TICKET_CACHE_ENTRY *
0x180054a43  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180054a48  mov     rax, r13
0x180054a4b  mov     [rbp+4Fh+var_68], rax
0x180054a4f  test    rax, rax
0x180054a52  jnz     loc_180054BDF
0x180054a58  bt      r12d, 8
0x180054a5d  jb      short loc_180054A87
0x180054a5f  lea     r9, aNonFwdableLogo; "Non Fwdable logon session used in S4u\n"
0x180054a66  mov     r8d, 1D0Eh
0x180054a6c  lea     rdx, aKerbgets4uprox_6; "KerbGetS4UProxyEvidence"
0x180054a73  mov     ecx, esi
0x180054a75  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180054a7a  mov     ebx, 0C000005Fh
0x180054a7f  mov     r12b, r13b
0x180054a82  jmp     loc_180054C26
0x180054a87  mov     rcx, r15; CriticalSection
0x180054a8a  call    cs:__imp_RtlEnterCriticalSection
0x180054a90  lea     rax, [rbp+4Fh+var_48]
0x180054a94  mov     r9d, esi; unsigned int
0x180054a97  mov     [rsp+0D0h+var_98], rax; struct _UNICODE_STRING *
0x180054a9c  lea     rcx, [r14+78h]; struct _UNICODE_STRING *
0x180054aa0  lea     rax, [rbp+4Fh+var_58]
0x180054aa4  xor     r8d, r8d; PCUNICODE_STRING
0x180054aa7  mov     [rsp+0D0h+var_A0], rax; struct _KERB_INTERNAL_NAME **
0x180054aac  xor     edx, edx; String
0x180054aae  lea     rax, [rbp+4Fh+var_70]
0x180054ab2  mov     r12b, sil
0x180054ab5  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x180054aba  mov     byte ptr [rsp+0D0h+var_B0], r13b; char
0x180054abf  call    ?KerbProcessTargetNames@@YAJPEBU_UNICODE_STRING@@00KEPEAKPEAPEAU_KERB_INTERNAL_NAME@@PEAU1@@Z; KerbProcessTargetNames(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong,uchar,ulong *,_KERB_INTERNAL_NAME * *,_UNICODE_STRING *)
0x180054ac4  mov     ebx, eax
0x180054ac6  test    eax, eax
0x180054ac8  js      loc_180054C26
0x180054ace  lea     rcx, [rbp+4Fh+var_48]
0x180054ad2  call    KerbFreeString
0x180054ad7  lea     rdx, [r14+88h]; struct _UNICODE_STRING *
0x180054ade  lea     rcx, [rbp+4Fh+var_48]; struct _UNICODE_STRING *
0x180054ae2  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x180054ae7  mov     ebx, eax
0x180054ae9  test    eax, eax
0x180054aeb  js      loc_180054C26
0x180054af1  mov     rcx, r15; CriticalSection
0x180054af4  call    cs:__imp_RtlLeaveCriticalSection
0x180054afa  mov     [rsp+58h], r13; unsigned __int8 *
0x180054aff  lea     rax, [rbp+4Fh+var_68]
0x180054b03  mov     [rsp+0D0h+var_80], r13d; unsigned int
0x180054b08  lea     r9, [rbp+4Fh+var_58]; struct _KERB_INTERNAL_NAME **
0x180054b0c  mov     [rsp+0D0h+var_88], r13d; unsigned int
0x180054b11  xor     r8d, r8d; struct _KERB_CREDENTIAL *
0x180054b14  mov     dword ptr [rsp+0D0h+var_90], r13d; char
0x180054b19  mov     rdx, r14; struct _KERB_LOGON_SESSION *
0x180054b1c  mov     dword ptr [rsp+0D0h+var_98], r13d; unsigned int
0x180054b21  mov     rcx, rdi; struct _KERB_LOGON_SESSION *
0x180054b24  mov     [rsp+0D0h+var_A0], rax; struct _KERB_TICKET_CACHE_ENTRY **
0x180054b29  mov     r12b, r13b
0x180054b2c  lea     rax, [rbp+4Fh+var_48]
0x180054b30  mov     [rsp+0D0h+var_A8], rax; struct _UNICODE_STRING *
0x180054b35  mov     [rsp+0D0h+var_B0], r13; struct _KERB_INTERNAL_NAME *
0x180054b3a  call    ?KerbGetS4USelfServiceTicket@@YAJPEAU_KERB_LOGON_SESSION@@0PEAU_KERB_CREDENTIAL@@PEAPEAU_KERB_INTERNAL_NAME@@PEAU3@PEAU_UNICODE_STRING@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@KKKKPEAE@Z; KerbGetS4USelfServiceTicket(_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_INTERNAL_NAME * *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY * *,ulong,ulong,ulong,ulong,uchar *)
0x180054b3f  mov     ebx, eax
0x180054b41  test    eax, eax
0x180054b43  jns     short loc_180054B69
0x180054b45  lea     r9, aKerbgets4uprox_0; "KerbGetS4UProxyEvidence failed to get S"...
0x180054b4c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180054b50  mov     r8d, 1D48h
0x180054b56  lea     rdx, aKerbgets4uprox_6; "KerbGetS4UProxyEvidence"
0x180054b5d  mov     ecx, esi
0x180054b5f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180054b64  jmp     loc_180054C26
0x180054b69  mov     rcx, [rbp+4Fh+var_68]; struct _KERB_TICKET_CACHE_ENTRY *
0x180054b6d  test    byte ptr [rcx+0A4h], 10h
0x180054b74  jz      short loc_180054B94
0x180054b76  mov     eax, [rdi+40h]
0x180054b79  lea     r9, aKerbgets4uprox_5; "KerbGetS4UProxyEvidence does not allow "...
0x180054b80  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180054b84  mov     r8d, 1D50h
0x180054b8a  mov     eax, [rdi+44h]
0x180054b8d  mov     ecx, 2
0x180054b92  jmp     short loc_180054C11
0x180054b94  lea     rdx, [rbp+4Fh+arg_8]; struct _KERB_TICKET_CACHE_ENTRY **
0x180054b98  mov     [rbp+4Fh+arg_8], r13
0x180054b9c  call    ?KerbDuplicateTicketCacheEntry@@YAJPEAU_KERB_TICKET_CACHE_ENTRY@@PEAPEAU1@@Z; KerbDuplicateTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *,_KERB_TICKET_CACHE_ENTRY * *)
0x180054ba1  mov     ebx, eax
0x180054ba3  test    eax, eax
0x180054ba5  js      short loc_180054C26
0x180054ba7  mov     rcx, r15; CriticalSection
0x180054baa  call    cs:__imp_RtlEnterCriticalSection
0x180054bb0  mov     rdx, [rbp+4Fh+arg_8]; struct _KERB_TICKET_CACHE_ENTRY *
0x180054bb4  lea     rcx, [r14+140h]; struct _KERB_TICKET_CACHE *
0x180054bbb  bts     dword ptr [r14+388h], 8
0x180054bc4  call    ?KerbInsertTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE@@PEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbInsertTicketCacheEntry(_KERB_TICKET_CACHE *,_KERB_TICKET_CACHE_ENTRY *)
0x180054bc9  mov     rcx, r15; CriticalSection
0x180054bcc  call    cs:__imp_RtlLeaveCriticalSection
0x180054bd2  mov     rcx, [rbp+4Fh+arg_8]; struct _KERB_TICKET_CACHE_ENTRY *
0x180054bd6  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180054bdb  mov     rax, [rbp+4Fh+var_68]
0x180054bdf  mov     rcx, [rbp+4Fh+arg_18]
0x180054be3  mov     [rbp+4Fh+var_68], r13
0x180054be7  mov     [rcx], rdi
0x180054bea  mov     rcx, [rbp+4Fh+arg_20]
0x180054bee  mov     [rcx], rax
0x180054bf1  jmp     short loc_180054C50
0x180054bf3  mov     eax, [r14+40h]
0x180054bf7  lea     r9, aKerbgets4uprox_4; "KerbGetS4UProxyEvidence autologon restr"...
0x180054bfe  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180054c02  mov     r8d, 1CBEh
0x180054c08  mov     eax, [r14+44h]
0x180054c0c  mov     ecx, 1
0x180054c11  lea     rdx, aKerbgets4uprox_6; "KerbGetS4UProxyEvidence"
0x180054c18  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180054c1c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180054c21  mov     ebx, 8009030Eh
0x180054c26  mov     rcx, [rbp+4Fh+var_68]; struct _KERB_TICKET_CACHE_ENTRY *
0x180054c2a  test    rcx, rcx
0x180054c2d  jz      short loc_180054C34
0x180054c2f  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180054c34  test    rdi, rdi
0x180054c37  jz      short loc_180054C41
0x180054c39  mov     rcx, rdi; struct _KERB_LOGON_SESSION *
0x180054c3c  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x180054c41  test    r12b, r12b
0x180054c44  jz      short loc_180054C50
0x180054c46  lea     rcx, [r14+50h]; CriticalSection
0x180054c4a  call    cs:__imp_RtlLeaveCriticalSection
0x180054c50  lea     rcx, [rbp+4Fh+var_58]; struct _KERB_INTERNAL_NAME **
0x180054c54  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x180054c59  lea     rcx, [rbp+4Fh+var_48]
0x180054c5d  call    KerbFreeString
0x180054c62  mov     eax, ebx
0x180054c64  mov     rbx, [rsp+0D0h+arg_0]
0x180054c6c  add     rsp, 0A0h
0x180054c73  pop     r15
0x180054c75  pop     r14
0x180054c77  pop     r13
0x180054c79  pop     r12
0x180054c7b  pop     rdi
0x180054c7c  pop     rsi
0x180054c7d  pop     rbp
0x180054c7e  retn
```
