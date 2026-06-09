# NlUninitializeDomains(void)

- ea: `0x180028dbc`
- end: `0x180028f10`
- name: `?NlUninitializeDomains@@YAXXZ`
- size: `340`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180029d5c`

## callees

- `0x18000c440`
- `0x18000dd00`
- `0x180026774`
- `0x1800267ec`
- `0x180028dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028e6c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028e6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e30`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e47`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e93`
- `ntdll!RtlLeaveCriticalSection` at `0x180028eeb`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e30`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e47`
- `ntdll!RtlLeaveCriticalSection` at `0x180028e93`
- `ntdll!RtlLeaveCriticalSection` at `0x180028eeb`
- `ntdll!RtlDeleteCriticalSection` at `0x180028efa`
- `ntdll!RtlDeleteCriticalSection` at `0x180028efa`
- `ntdll!RtlEnterCriticalSection` at `0x180028de6`
- `ntdll!RtlEnterCriticalSection` at `0x180028e7b`
- `ntdll!RtlEnterCriticalSection` at `0x180028ecc`
- `ntdll!RtlEnterCriticalSection` at `0x180028de6`
- `ntdll!RtlEnterCriticalSection` at `0x180028e7b`
- `ntdll!RtlEnterCriticalSection` at `0x180028ecc`

## string_xrefs

- `0x180028eae`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`

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
              0x12F7u,
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
0x180028dbc  push    rbx
0x180028dbe  push    rbp
0x180028dbf  push    rsi
0x180028dc0  push    rdi
0x180028dc1  sub     rsp, 28h
0x180028dc5  cmp     cs:?NlGlobalDomainsInitialized@@3HA, 0; int NlGlobalDomainsInitialized
0x180028dcc  jz      loc_180028F06
0x180028dd2  lea     rbp, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDomainCritSect
0x180028dd9  mov     cs:?NlGlobalDomainsInitialized@@3HA, 0; int NlGlobalDomainsInitialized
0x180028de3  mov     rcx, rbp; CriticalSection
0x180028de6  call    cs:__imp_RtlEnterCriticalSection
0x180028ded  nop     dword ptr [rax+rax+00h]
0x180028df2  xor     edi, edi
0x180028df4  test    edi, edi
0x180028df6  lea     rax, ?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedNdncs
0x180028dfd  lea     rsi, ?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedDomains
0x180028e04  cmovnz  rsi, rax
0x180028e08  mov     rbx, [rsi]
0x180028e0b  cmp     rbx, rsi
0x180028e0e  jz      loc_180028EDD
0x180028e14  test    byte ptr [rbx+250h], 80h
0x180028e1b  jz      short loc_180028E25
0x180028e1d  inc     dword ptr [rbx+248h]
0x180028e23  jmp     short loc_180028E2D
0x180028e25  mov     rcx, rbx; struct _DOMAIN_INFO *
0x180028e28  call    ?NlDeleteDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDeleteDomain(_DOMAIN_INFO *)
0x180028e2d  mov     rcx, rbp; CriticalSection
0x180028e30  call    cs:__imp_RtlLeaveCriticalSection
0x180028e37  nop     dword ptr [rax+rax+00h]
0x180028e3c  cmp     dword ptr [rbx+248h], 1
0x180028e43  jz      short loc_180028EC1
0x180028e45  jmp     short loc_180028E78
0x180028e47  call    cs:__imp_RtlLeaveCriticalSection
0x180028e4e  nop     dword ptr [rax+rax+00h]
0x180028e53  lea     r8, aNlunitializedo; "NlUnitializeDomains: Sleeping a second "...
0x180028e5a  mov     rdx, rbx; struct _DOMAIN_INFO *
0x180028e5d  mov     ecx, 100h; unsigned int
0x180028e62  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028e67  mov     ecx, 3E8h; dwMilliseconds
0x180028e6c  call    cs:__imp_Sleep
0x180028e73  nop     dword ptr [rax+rax+00h]
0x180028e78  mov     rcx, rbp; CriticalSection
0x180028e7b  call    cs:__imp_RtlEnterCriticalSection
0x180028e82  nop     dword ptr [rax+rax+00h]
0x180028e87  cmp     dword ptr [rbx+248h], 1
0x180028e8e  mov     rcx, rbp; CriticalSection
0x180028e91  jnz     short loc_180028E47
0x180028e93  call    cs:__imp_RtlLeaveCriticalSection
0x180028e9a  nop     dword ptr [rax+rax+00h]
0x180028e9f  cmp     dword ptr [rbx+248h], 1
0x180028ea6  jz      short loc_180028EC1
0x180028ea8  mov     r8d, 12F7h; unsigned int
0x180028eae  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180028eb5  lea     rcx, aDomaininfoRefe; "DomainInfo->ReferenceCount == 1"
0x180028ebc  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180028ec1  mov     rcx, rbx; struct _DOMAIN_INFO *
0x180028ec4  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x180028ec9  mov     rcx, rbp; CriticalSection
0x180028ecc  call    cs:__imp_RtlEnterCriticalSection
0x180028ed3  nop     dword ptr [rax+rax+00h]
0x180028ed8  jmp     loc_180028E08
0x180028edd  inc     edi
0x180028edf  cmp     edi, 2
0x180028ee2  jb      loc_180028DF4
0x180028ee8  mov     rcx, rbp; CriticalSection
0x180028eeb  call    cs:__imp_RtlLeaveCriticalSection
0x180028ef2  nop     dword ptr [rax+rax+00h]
0x180028ef7  mov     rcx, rbp; CriticalSection
0x180028efa  call    cs:__imp_RtlDeleteCriticalSection
0x180028f01  nop     dword ptr [rax+rax+00h]
0x180028f06  add     rsp, 28h
0x180028f0a  pop     rdi
0x180028f0b  pop     rsi
0x180028f0c  pop     rbp
0x180028f0d  pop     rbx
0x180028f0e  retn
```
