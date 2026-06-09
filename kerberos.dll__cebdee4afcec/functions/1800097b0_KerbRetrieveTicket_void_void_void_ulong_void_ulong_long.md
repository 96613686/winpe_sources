# KerbRetrieveTicket(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800097b0`
- end: `0x180009af6`
- name: `?KerbRetrieveTicket@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `838`
- prototype: `__int64 __fastcall(void **, char *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800063e8`
- `0x1800097b0`
- `0x180009afc`
- `0x180009c60`
- `0x180009fe4`
- `0x18000a650`
- `0x18002a150`
- `0x18006557c`
- `0x180066994`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000989c`
- `ntdll!RtlReleaseResource` at `0x18000989c`
- `ntdll!RtlAcquireResourceShared` at `0x180009867`
- `ntdll!RtlAcquireResourceShared` at `0x180009867`
- `ntdll!NtQueryInformationToken` at `0x1800098fa`
- `ntdll!NtQueryInformationToken` at `0x1800098fa`
- `ntdll!RtlEnterCriticalSection` at `0x18000984e`
- `ntdll!RtlEnterCriticalSection` at `0x180009a09`
- `ntdll!RtlEnterCriticalSection` at `0x18000984e`
- `ntdll!RtlEnterCriticalSection` at `0x180009a09`
- `ntdll!RtlLeaveCriticalSection` at `0x1800098c9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800099af`
- `ntdll!RtlLeaveCriticalSection` at `0x180009a49`
- `ntdll!RtlLeaveCriticalSection` at `0x180009a68`
- `ntdll!RtlLeaveCriticalSection` at `0x1800098c9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800099af`
- `ntdll!RtlLeaveCriticalSection` at `0x180009a49`
- `ntdll!RtlLeaveCriticalSection` at `0x180009a68`

## pseudocode

```c
__int64 __fastcall KerbRetrieveTicket(
        void **a1,
        char *a2,
        void *a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  unsigned __int8 *v8; // rbp
  NTSTATUS v9; // edi
  const struct _LUID *v10; // rcx
  struct _RTL_CRITICAL_SECTION *LogonSession; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v14; // rbx
  volatile signed __int32 *SpinCount; // r14
  PRTL_CRITICAL_SECTION_DEBUG i; // r13
  int v17; // r15d
  bool v18; // di
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  int v20; // r8d
  BOOL v21; // r8d
  int Flink_high; // eax
  unsigned int v24; // [rsp+30h] [rbp-98h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-94h] BYREF
  unsigned __int8 *v26; // [rsp+38h] [rbp-90h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+40h] [rbp-88h]
  __int128 v28; // [rsp+50h] [rbp-78h] BYREF
  HANDLE TokenHandle[2]; // [rsp+60h] [rbp-68h]
  int TokenInformation; // [rsp+E8h] [rbp+20h] BYREF

  v28 = 0;
  *(_OWORD *)TokenHandle = 0;
  v8 = 0;
  v26 = 0;
  v24 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( a4 < 0xC )
  {
    v9 = -1073741811;
    goto LABEL_28;
  }
  v9 = ((__int64 (__fastcall *)(__int128 *, char *, void *))LsaFunctions->GetClientInfo)(&v28, a2, a3);
  if ( v9 >= 0 )
  {
    v10 = (const struct _LUID *)(a2 + 4);
    if ( *(_QWORD *)(a2 + 4) )
    {
      if ( !LOBYTE(TokenHandle[0]) )
      {
        v9 = -1073741727;
        goto LABEL_28;
      }
    }
    else
    {
      v10 = (const struct _LUID *)&v28;
    }
    LogonSession = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(v10, 0);
    v12 = LogonSession;
    if ( !LogonSession )
    {
      v9 = -1073741729;
      goto LABEL_28;
    }
    RtlEnterCriticalSection(LogonSession + 2);
    v13 = v12 + 9;
    v14 = 0;
    RtlAcquireResourceShared(&KerberosTicketCacheLock, 1u);
    SpinCount = (volatile signed __int32 *)v12[9].SpinCount;
    if ( SpinCount )
    {
      _InterlockedIncrement(SpinCount + 2);
      _InterlockedIncrement(SpinCount + 2);
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)SpinCount);
    }
    for ( i = v13->DebugInfo; ; i = *(PRTL_CRITICAL_SECTION_DEBUG *)&i->Type )
    {
      LOBYTE(v17) = 0;
      if ( i == (PRTL_CRITICAL_SECTION_DEBUG)v13 )
      {
        v18 = 0;
        goto LABEL_11;
      }
      v14 = i;
      CriticalSection = (PRTL_CRITICAL_SECTION)&i[7].EntryCount;
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&i[7].EntryCount);
      Flink_high = HIDWORD(i[3].ProcessLocksList.Flink);
      if ( (Flink_high & 1) != 0 && (Flink_high & 2) == 0 )
        break;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&i[7].EntryCount);
    }
    if ( KerbTicketIsExpiring((struct _KERB_TICKET_CACHE_ENTRY *)i, 0) )
    {
      v17 = HIDWORD(i[3].ProcessLocksList.Flink) & 1;
      v18 = !(BYTE4(i[3].ProcessLocksList.Flink) & 1);
    }
    else
    {
      LOBYTE(v17) = 1;
      v18 = 0;
    }
    _InterlockedIncrement((volatile signed __int32 *)&i->ProcessLocksList);
    RtlLeaveCriticalSection(CriticalSection);
LABEL_11:
    RtlReleaseResource(&KerberosTicketCacheLock);
    if ( SpinCount )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)SpinCount);
    if ( v18 )
    {
      KerbRemoveTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v14);
      KerbDereferenceTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v14);
    }
    v19 = v12 + 2;
    if ( (_BYTE)v17 )
    {
      _InterlockedIncrement(&KerbTicketCacheHits);
      RtlLeaveCriticalSection(v19);
      if ( v14 )
      {
        v9 = NtQueryInformationToken(TokenHandle[1], TokenElevationType, &TokenInformation, 4u, &ReturnLength);
        if ( v9 >= 0 )
        {
          KerbTelemetry::KerbRetrieveTicket(*(KerbTelemetry **)&v14->EntryCount, 0, v20);
          v21 = LOBYTE(TokenHandle[0]) || KerbGlobalAllowTgtSessionKey;
          v9 = KerbPackExternalTicket((struct _KERB_TICKET_CACHE_ENTRY *)v14, 0, v21, TokenInformation == 3, &v24, &v26);
          if ( v9 >= 0 )
          {
            *a5 = v26;
            v8 = 0;
            *a6 = v24;
          }
          else
          {
            v8 = v26;
          }
        }
        goto LABEL_22;
      }
    }
    else
    {
      v14 = 0;
      _InterlockedIncrement(&KerbTicketCacheMisses);
      RtlLeaveCriticalSection(v19);
    }
    v9 = -2146893042;
LABEL_22:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12, 0xFFFFFFFF) == 1 )
      KerbFreeLogonSession(v12);
    if ( v14 )
      KerbDereferenceTicketCacheEntry((struct _KERB_TICKET_CACHE_ENTRY *)v14);
    if ( v8 )
      ((void (__fastcall *)(_QWORD, unsigned __int8 *))LsaFunctions->FreeClientBuffer)(0, v8);
  }
LABEL_28:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x1800097b0  push    rbx
0x1800097b2  push    rbp
0x1800097b3  push    rsi
0x1800097b4  push    rdi
0x1800097b5  push    r12
0x1800097b7  push    r13
0x1800097b9  push    r14
0x1800097bb  push    r15
0x1800097bd  sub     rsp, 88h
0x1800097c4  mov     rbx, rdx
0x1800097c7  xor     r14d, r14d
0x1800097ca  xorps   xmm0, xmm0
0x1800097cd  movups  [rsp+0C8h+var_78], xmm0
0x1800097d2  movups  xmmword ptr [rsp+0C8h+TokenHandle], xmm0
0x1800097d7  mov     ebp, r14d
0x1800097da  mov     [rsp+0C8h+var_90], r14
0x1800097df  mov     [rsp+0C8h+var_98], r14d
0x1800097e4  mov     [rsp+0C8h+TokenInformation], r14d
0x1800097ec  mov     [rsp+0C8h+var_94], r14d
0x1800097f1  cmp     r9d, 0Ch
0x1800097f5  jb      loc_1800099BC
0x1800097fb  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180009802  lea     rcx, [rsp+0C8h+var_78]
0x180009807  mov     rax, [rax+80h]
0x18000980e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009813  mov     edi, eax
0x180009815  test    eax, eax
0x180009817  js      loc_180009986
0x18000981d  lea     rcx, [rbx+4]; struct _LUID *
0x180009821  mov     eax, [rbx+8]
0x180009824  or      eax, [rcx]
0x180009826  jz      loc_1800099C3
0x18000982c  cmp     byte ptr [rsp+0C8h+TokenHandle], bpl
0x180009831  jz      loc_1800099CD
0x180009837  xor     edx, edx; unsigned __int8
0x180009839  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x18000983e  mov     rsi, rax
0x180009841  test    rax, rax
0x180009844  jz      loc_1800099D4
0x18000984a  lea     rcx, [rax+50h]; CriticalSection
0x18000984e  call    cs:__imp_RtlEnterCriticalSection
0x180009854  lea     rdi, [rsi+168h]
0x18000985b  mov     rbx, r14
0x18000985e  mov     dl, 1; Wait
0x180009860  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180009867  call    cs:__imp_RtlAcquireResourceShared
0x18000986d  mov     r14, [rdi+20h]
0x180009871  test    r14, r14
0x180009874  jnz     loc_1800099DB
0x18000987a  test    r14, r14
0x18000987d  jnz     loc_1800099EA
0x180009883  mov     r13, [rdi]
0x180009886  xor     r15b, r15b
0x180009889  cmp     r13, rdi
0x18000988c  jnz     loc_1800099F7
0x180009892  xor     dil, dil
0x180009895  lea     rcx, ?KerberosTicketCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18000989c  call    cs:__imp_RtlReleaseResource
0x1800098a2  nop
0x1800098a3  test    r14, r14
0x1800098a6  jnz     loc_180009A73
0x1800098ac  test    dil, dil
0x1800098af  jnz     loc_180009A80
0x1800098b5  lea     rcx, [rsi+50h]; CriticalSection
0x1800098b9  test    r15b, r15b
0x1800098bc  jz      loc_1800099A6
0x1800098c2  lock inc cs:?KerbTicketCacheHits@@3JA; long KerbTicketCacheHits
0x1800098c9  call    cs:__imp_RtlLeaveCriticalSection
0x1800098cf  test    rbx, rbx
0x1800098d2  jz      loc_1800099B5
0x1800098d8  lea     rax, [rsp+0C8h+var_94]
0x1800098dd  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x1800098e2  mov     r9d, 4; TokenInformationLength
0x1800098e8  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x1800098f0  mov     edx, 12h; TokenInformationClass
0x1800098f5  mov     rcx, [rsp+0C8h+TokenHandle+8]; TokenHandle
0x1800098fa  call    cs:__imp_NtQueryInformationToken
0x180009900  mov     edi, eax
0x180009902  test    eax, eax
0x180009904  js      short loc_18000995E
0x180009906  xor     edx, edx; struct _KERB_INTERNAL_NAME *
0x180009908  mov     rcx, [rbx+20h]; this
0x18000990c  call    ?KerbRetrieveTicket@KerbTelemetry@@YAXPEAU_KERB_INTERNAL_NAME@@H@Z; KerbTelemetry::KerbRetrieveTicket(_KERB_INTERNAL_NAME *,int)
0x180009911  xor     r9d, r9d
0x180009914  cmp     [rsp+0C8h+TokenInformation], 3
0x18000991c  setz    r9b; int
0x180009920  cmp     byte ptr [rsp+0C8h+TokenHandle], 0
0x180009925  jz      loc_180009A95
0x18000992b  mov     r8d, 1; int
0x180009931  lea     rax, [rsp+0C8h+var_90]
0x180009936  mov     [rsp+0C8h+var_A0], rax; unsigned __int8 **
0x18000993b  lea     rax, [rsp+0C8h+var_98]
0x180009940  mov     [rsp+0C8h+ReturnLength], rax; unsigned int *
0x180009945  xor     edx, edx; int
0x180009947  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x18000994a  call    ?KerbPackExternalTicket@@YAJPEAU_KERB_TICKET_CACHE_ENTRY@@HHHPEAKPEAPEAE@Z; KerbPackExternalTicket(_KERB_TICKET_CACHE_ENTRY *,int,int,int,ulong *,uchar * *)
0x18000994f  mov     edi, eax
0x180009951  test    eax, eax
0x180009953  jns     loc_180009AAA
0x180009959  mov     rbp, [rsp+0C8h+var_90]
0x18000995e  mov     eax, 0FFFFFFFFh
0x180009963  lock xadd [rsi], eax
0x180009967  cmp     eax, 1
0x18000996a  jnz     short loc_180009974
0x18000996c  mov     rcx, rsi; hMem
0x18000996f  call    ?KerbFreeLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbFreeLogonSession(_KERB_LOGON_SESSION *)
0x180009974  test    rbx, rbx
0x180009977  jnz     loc_180009ACF
0x18000997d  test    rbp, rbp
0x180009980  jnz     loc_180009ADC
0x180009986  mov     rax, [rsp+0C8h+arg_30]
0x18000998e  mov     [rax], edi
0x180009990  xor     eax, eax
0x180009992  add     rsp, 88h
0x180009999  pop     r15
0x18000999b  pop     r14
0x18000999d  pop     r13
0x18000999f  pop     r12
0x1800099a1  pop     rdi
0x1800099a2  pop     rsi
0x1800099a3  pop     rbp
0x1800099a4  pop     rbx
0x1800099a5  retn
0x1800099a6  xor     ebx, ebx
0x1800099a8  lock inc cs:?KerbTicketCacheMisses@@3JA; long KerbTicketCacheMisses
0x1800099af  call    cs:__imp_RtlLeaveCriticalSection
0x1800099b5  mov     edi, 8009030Eh
0x1800099ba  jmp     short loc_18000995E
0x1800099bc  mov     edi, 0C000000Dh
0x1800099c1  jmp     short loc_180009986
0x1800099c3  lea     rcx, [rsp+0C8h+var_78]
0x1800099c8  jmp     loc_180009837
0x1800099cd  mov     edi, 0C0000061h
0x1800099d2  jmp     short loc_180009986
0x1800099d4  mov     edi, 0C000005Fh
0x1800099d9  jmp     short loc_180009986
0x1800099db  lock inc dword ptr [r14+8]
0x1800099e0  lock inc dword ptr [r14+8]
0x1800099e5  jmp     loc_18000987A
0x1800099ea  mov     rcx, r14; this
0x1800099ed  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800099f2  jmp     loc_180009883
0x1800099f7  mov     rbx, r13
0x1800099fa  lea     r15, [r13+170h]
0x180009a01  mov     [rsp+0C8h+CriticalSection], r15
0x180009a06  mov     rcx, r15; CriticalSection
0x180009a09  call    cs:__imp_RtlEnterCriticalSection
0x180009a0f  mov     eax, [r13+0A4h]
0x180009a16  test    al, 1
0x180009a18  jz      short loc_180009A46
0x180009a1a  test    al, 2
0x180009a1c  jnz     short loc_180009A46
0x180009a1e  xor     edx, edx; union _LARGE_INTEGER *
0x180009a20  mov     rcx, r13; struct _KERB_TICKET_CACHE_ENTRY *
0x180009a23  call    ?KerbTicketIsExpiring@@YAEPEAU_KERB_TICKET_CACHE_ENTRY@@PEAT_LARGE_INTEGER@@@Z; KerbTicketIsExpiring(_KERB_TICKET_CACHE_ENTRY *,_LARGE_INTEGER *)
0x180009a28  test    al, al
0x180009a2a  mov     eax, 10h
0x180009a2f  jz      short loc_180009A58
0x180009a31  mov     r15d, [r13+0A4h]
0x180009a38  and     r15d, 1
0x180009a3c  movzx   edi, r15b
0x180009a40  xor     dil, 1
0x180009a44  jmp     short loc_180009A5E
0x180009a46  mov     rcx, r15; CriticalSection
0x180009a49  call    cs:__imp_RtlLeaveCriticalSection
0x180009a4f  mov     r13, [r13+0]
0x180009a53  jmp     loc_180009886
0x180009a58  mov     r15b, 1
0x180009a5b  xor     dil, dil
0x180009a5e  lock inc dword ptr [rax+r13]
0x180009a63  mov     rcx, [rsp+0C8h+CriticalSection]; CriticalSection
0x180009a68  call    cs:__imp_RtlLeaveCriticalSection
0x180009a6e  jmp     loc_180009895
0x180009a73  mov     rcx, r14; this
0x180009a76  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180009a7b  jmp     loc_1800098AC
0x180009a80  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x180009a83  call    ?KerbRemoveTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbRemoveTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180009a88  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x180009a8b  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180009a90  jmp     loc_1800098B5
0x180009a95  cmp     cs:?KerbGlobalAllowTgtSessionKey@@3KA, 0; ulong KerbGlobalAllowTgtSessionKey
0x180009a9c  jnz     loc_18000992B
0x180009aa2  xor     r8d, r8d
0x180009aa5  jmp     loc_180009931
0x180009aaa  mov     rcx, [rsp+0C8h+arg_20]
0x180009ab2  mov     rax, [rsp+0C8h+var_90]
0x180009ab7  mov     [rcx], rax
0x180009aba  xor     ebp, ebp
0x180009abc  mov     rcx, [rsp+0C8h+arg_28]
0x180009ac4  mov     eax, [rsp+0C8h+var_98]
0x180009ac8  mov     [rcx], eax
0x180009aca  jmp     loc_18000995E
0x180009acf  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x180009ad2  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x180009ad7  jmp     loc_18000997D
0x180009adc  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180009ae3  mov     rdx, rbp
0x180009ae6  xor     ecx, ecx
0x180009ae8  mov     rax, [rax+40h]
0x180009aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009af1  jmp     loc_180009986
```
