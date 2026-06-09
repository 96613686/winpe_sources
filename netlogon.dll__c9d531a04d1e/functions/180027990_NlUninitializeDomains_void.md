# NlUninitializeDomains(void)

- ea: `0x180027990`
- end: `0x180027aad`
- name: `?NlUninitializeDomains@@YAXXZ`
- size: `285`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180028834`

## callees

- `0x18000bd98`
- `0x18000d710`
- `0x180025698`
- `0x180025708`
- `0x180027990`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027a2e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027a2e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800279fe`
- `ntdll!RtlLeaveCriticalSection` at `0x180027a0f`
- `ntdll!RtlLeaveCriticalSection` at `0x180027a49`
- `ntdll!RtlLeaveCriticalSection` at `0x180027a95`
- `ntdll!RtlLeaveCriticalSection` at `0x1800279fe`
- `ntdll!RtlLeaveCriticalSection` at `0x180027a0f`
- `ntdll!RtlLeaveCriticalSection` at `0x180027a49`
- `ntdll!RtlLeaveCriticalSection` at `0x180027a95`
- `ntdll!RtlDeleteCriticalSection` at `0x180027a9e`
- `ntdll!RtlDeleteCriticalSection` at `0x180027a9e`
- `ntdll!RtlEnterCriticalSection` at `0x1800279ba`
- `ntdll!RtlEnterCriticalSection` at `0x180027a37`
- `ntdll!RtlEnterCriticalSection` at `0x180027a7c`
- `ntdll!RtlEnterCriticalSection` at `0x1800279ba`
- `ntdll!RtlEnterCriticalSection` at `0x180027a37`
- `ntdll!RtlEnterCriticalSection` at `0x180027a7c`

## string_xrefs

- `0x180027a5e`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`

## pseudocode

```c
void NlUninitializeDomains(void)
{
  unsigned int i; // edi
  struct _DOMAIN_INFO **v1; // rsi
  struct _DOMAIN_INFO *v2; // rbx
  char *v3; // r9

  if ( NlGlobalDomainsInitialized )
  {
    NlGlobalDomainsInitialized = 0;
    RtlEnterCriticalSection(&NlGlobalDomainCritSect);
    for ( i = 0; i < 2; ++i )
    {
      v1 = (struct _DOMAIN_INFO **)&NlGlobalServicedDomains;
      if ( i )
        v1 = &NlGlobalServicedNdncs;
      while ( 1 )
      {
        v2 = *v1;
        if ( *v1 == (struct _DOMAIN_INFO *)v1 )
          break;
        if ( *((char *)v2 + 592) >= 0 )
          NlDeleteDomain(*v1);
        else
          ++*((_DWORD *)v2 + 146);
        RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
        if ( *((_DWORD *)v2 + 146) != 1 )
        {
          while ( 1 )
          {
            RtlEnterCriticalSection(&NlGlobalDomainCritSect);
            if ( *((_DWORD *)v2 + 146) == 1 )
              break;
            RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
            NlPrintDomRoutine(
              0x100u,
              v2,
              L"NlUnitializeDomains: Sleeping a second waiting for Domain RefCount to zero.\n");
            Sleep(0x3E8u);
          }
          RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
          if ( *((_DWORD *)v2 + 146) != 1 )
            NlAssertFailed(
              "DomainInfo->ReferenceCount == 1",
              "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx",
              4855,
              v3);
        }
        NlDereferenceDomain(v2);
        RtlEnterCriticalSection(&NlGlobalDomainCritSect);
      }
    }
    RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
    RtlDeleteCriticalSection(&NlGlobalDomainCritSect);
  }
}

```

## disassembly

```asm
0x180027990  push    rbx
0x180027992  push    rbp
0x180027993  push    rsi
0x180027994  push    rdi
0x180027995  sub     rsp, 28h
0x180027999  cmp     cs:?NlGlobalDomainsInitialized@@3HA, 0; int NlGlobalDomainsInitialized
0x1800279a0  jz      loc_180027AA4
0x1800279a6  lea     rbp, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDomainCritSect
0x1800279ad  mov     cs:?NlGlobalDomainsInitialized@@3HA, 0; int NlGlobalDomainsInitialized
0x1800279b7  mov     rcx, rbp; CriticalSection
0x1800279ba  call    cs:__imp_RtlEnterCriticalSection
0x1800279c0  xor     edi, edi
0x1800279c2  test    edi, edi
0x1800279c4  lea     rax, ?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedNdncs
0x1800279cb  lea     rsi, ?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedDomains
0x1800279d2  cmovnz  rsi, rax
0x1800279d6  mov     rbx, [rsi]
0x1800279d9  cmp     rbx, rsi
0x1800279dc  jz      loc_180027A87
0x1800279e2  test    byte ptr [rbx+250h], 80h
0x1800279e9  jz      short loc_1800279F3
0x1800279eb  inc     dword ptr [rbx+248h]
0x1800279f1  jmp     short loc_1800279FB
0x1800279f3  mov     rcx, rbx; struct _DOMAIN_INFO *
0x1800279f6  call    ?NlDeleteDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDeleteDomain(_DOMAIN_INFO *)
0x1800279fb  mov     rcx, rbp; CriticalSection
0x1800279fe  call    cs:__imp_RtlLeaveCriticalSection
0x180027a04  cmp     dword ptr [rbx+248h], 1
0x180027a0b  jz      short loc_180027A71
0x180027a0d  jmp     short loc_180027A34
0x180027a0f  call    cs:__imp_RtlLeaveCriticalSection
0x180027a15  lea     r8, aNlunitializedo; "NlUnitializeDomains: Sleeping a second "...
0x180027a1c  mov     rdx, rbx; struct _DOMAIN_INFO *
0x180027a1f  mov     ecx, 100h; unsigned int
0x180027a24  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027a29  mov     ecx, 3E8h; dwMilliseconds
0x180027a2e  call    cs:__imp_Sleep
0x180027a34  mov     rcx, rbp; CriticalSection
0x180027a37  call    cs:__imp_RtlEnterCriticalSection
0x180027a3d  cmp     dword ptr [rbx+248h], 1
0x180027a44  mov     rcx, rbp; CriticalSection
0x180027a47  jnz     short loc_180027A0F
0x180027a49  call    cs:__imp_RtlLeaveCriticalSection
0x180027a4f  cmp     dword ptr [rbx+248h], 1
0x180027a56  jz      short loc_180027A71
0x180027a58  mov     r8d, 12F7h; unsigned int
0x180027a5e  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180027a65  lea     rcx, aDomaininfoRefe; "DomainInfo->ReferenceCount == 1"
0x180027a6c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180027a71  mov     rcx, rbx; struct _DOMAIN_INFO *
0x180027a74  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x180027a79  mov     rcx, rbp; CriticalSection
0x180027a7c  call    cs:__imp_RtlEnterCriticalSection
0x180027a82  jmp     loc_1800279D6
0x180027a87  inc     edi
0x180027a89  cmp     edi, 2
0x180027a8c  jb      loc_1800279C2
0x180027a92  mov     rcx, rbp; CriticalSection
0x180027a95  call    cs:__imp_RtlLeaveCriticalSection
0x180027a9b  mov     rcx, rbp; CriticalSection
0x180027a9e  call    cs:__imp_RtlDeleteCriticalSection
0x180027aa4  add     rsp, 28h
0x180027aa8  pop     rdi
0x180027aa9  pop     rsi
0x180027aaa  pop     rbp
0x180027aab  pop     rbx
0x180027aac  retn
```
