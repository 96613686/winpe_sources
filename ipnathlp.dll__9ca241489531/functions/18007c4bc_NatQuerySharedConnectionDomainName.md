# NatQuerySharedConnectionDomainName

- ea: `0x18007c4bc`
- end: `0x18007c642`
- name: `NatQuerySharedConnectionDomainName`
- size: `390`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180003584`
- `0x180004a44`
- `0x18006c318`

## callees

- `0x18000c110`
- `0x18000f250`
- `0x18004af64`
- `0x18007b39c`
- `0x18007bdf8`
- `0x18007c4bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c55f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c5c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c55f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c5c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c570`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c5d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c570`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c5d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c504`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c504`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c5fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c5fc`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18007c53a`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18007c53a`
- `DNSAPI!DnsFree` at `0x18007c5a0`
- `DNSAPI!DnsFree` at `0x18007c5a0`
- `DNSAPI!DnsFreeConfigStructure` at `0x18007c5ad`
- `DNSAPI!DnsFreeConfigStructure` at `0x18007c5ad`

## pseudocode

```c
char *NatQuerySharedConnectionDomainName()
{
  char *v0; // rcx
  char *ConfigAlloc; // rdi
  char *v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // esi
  HANDLE v5; // rax
  char *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // edi
  HANDLE ProcessHeap; // rax
  char *v10; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  EnterCriticalSection(&NatInterfaceLock);
  v0 = NatSharedConnectionDomainName;
  if ( NatSharedConnectionDomainName
    || (NatUpdateSharedConnectionDomainName(0xFFFFFFFF), (v0 = NatSharedConnectionDomainName) != 0) )
  {
    v7 = -1;
    do
      ++v7;
    while ( v0[v7] );
    v8 = v7 + 1;
    ProcessHeap = GetProcessHeap();
    v10 = (char *)HeapAlloc(ProcessHeap, 8u, v8);
    v2 = v10;
    if ( v10 )
      StringCchCopyA(v10, v8, NatSharedConnectionDomainName);
  }
  else
  {
    ConfigAlloc = (char *)DnsQueryConfigAllocEx(1, 0, 0);
    if ( ConfigAlloc )
    {
      v3 = -1;
      do
        ++v3;
      while ( ConfigAlloc[v3] );
      v4 = v3 + 1;
      v5 = GetProcessHeap();
      v6 = (char *)HeapAlloc(v5, 8u, v4);
      v2 = v6;
      if ( v6 )
        StringCchCopyA(v6, v4, ConfigAlloc);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_5977_1413>::GetImpl'::`2'::impl) )
        DnsFree(ConfigAlloc, DnsFreeFlat);
      else
        DnsFreeConfigStructure(ConfigAlloc, 1);
    }
    else
    {
      v2 = 0;
    }
  }
  LeaveCriticalSection(&NatInterfaceLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18007c4bc  push    rbx
0x18007c4be  push    rsi
0x18007c4bf  push    rdi
0x18007c4c0  push    r15
0x18007c4c2  sub     rsp, 28h
0x18007c4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c4cd  lea     r15, WPP_GLOBAL_Control
0x18007c4d4  cmp     rcx, r15
0x18007c4d7  jz      short loc_18007C4FD
0x18007c4d9  test    dword ptr [rcx+1Ch], 200h
0x18007c4e0  jz      short loc_18007C4FD
0x18007c4e2  cmp     byte ptr [rcx+19h], 6
0x18007c4e6  jb      short loc_18007C4FD
0x18007c4e8  mov     rcx, [rcx+10h]
0x18007c4ec  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007c4f3  mov     edx, 0C0h
0x18007c4f8  call    WPP_SF_
0x18007c4fd  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c504  call    cs:__imp_EnterCriticalSection
0x18007c50a  mov     rcx, cs:?NatSharedConnectionDomainName@@3PEADEA; char * NatSharedConnectionDomainName
0x18007c511  test    rcx, rcx
0x18007c514  jnz     loc_18007C5B5
0x18007c51a  or      ecx, 0FFFFFFFFh; InterfaceIndex
0x18007c51d  call    ?NatUpdateSharedConnectionDomainName@@YAXK@Z; NatUpdateSharedConnectionDomainName(ulong)
0x18007c522  mov     rcx, cs:?NatSharedConnectionDomainName@@3PEADEA; char * NatSharedConnectionDomainName
0x18007c529  test    rcx, rcx
0x18007c52c  jnz     loc_18007C5B5
0x18007c532  xor     edx, edx
0x18007c534  xor     r8d, r8d
0x18007c537  lea     ecx, [rdx+1]
0x18007c53a  call    cs:__imp_DnsQueryConfigAllocEx
0x18007c540  mov     rdi, rax
0x18007c543  test    rax, rax
0x18007c546  jnz     short loc_18007C54F
0x18007c548  xor     ebx, ebx
0x18007c54a  jmp     loc_18007C5F5
0x18007c54f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007c553  inc     rax
0x18007c556  cmp     byte ptr [rdi+rax], 0
0x18007c55a  jnz     short loc_18007C553
0x18007c55c  lea     esi, [rax+1]
0x18007c55f  call    cs:__imp_GetProcessHeap
0x18007c565  mov     r8d, esi; dwBytes
0x18007c568  mov     edx, 8; dwFlags
0x18007c56d  mov     rcx, rax; hHeap
0x18007c570  call    cs:__imp_HeapAlloc
0x18007c576  mov     rbx, rax
0x18007c579  test    rax, rax
0x18007c57c  jz      short loc_18007C58B
0x18007c57e  mov     r8, rdi; char *
0x18007c581  mov     edx, esi; unsigned __int64
0x18007c583  mov     rcx, rax; char *
0x18007c586  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18007c58b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_5977_1413@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_5977_1413@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413> `wil::Feature<__WilFeatureTraits_Feature_5977_1413>::GetImpl(void)'::`2'::impl
0x18007c592  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_5977_1413@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413>::__private_IsEnabled(void)
0x18007c597  mov     rcx, rdi; pData
0x18007c59a  test    al, al
0x18007c59c  jz      short loc_18007C5A8
0x18007c59e  xor     edx, edx; FreeType
0x18007c5a0  call    cs:__imp_DnsFree
0x18007c5a6  jmp     short loc_18007C5F5
0x18007c5a8  mov     edx, 1
0x18007c5ad  call    cs:__imp_DnsFreeConfigStructure
0x18007c5b3  jmp     short loc_18007C5F5
0x18007c5b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007c5b9  inc     rax
0x18007c5bc  cmp     byte ptr [rcx+rax], 0
0x18007c5c0  jnz     short loc_18007C5B9
0x18007c5c2  lea     edi, [rax+1]
0x18007c5c5  call    cs:__imp_GetProcessHeap
0x18007c5cb  mov     r8d, edi; dwBytes
0x18007c5ce  mov     edx, 8; dwFlags
0x18007c5d3  mov     rcx, rax; hHeap
0x18007c5d6  call    cs:__imp_HeapAlloc
0x18007c5dc  mov     rbx, rax
0x18007c5df  test    rax, rax
0x18007c5e2  jz      short loc_18007C5F5
0x18007c5e4  mov     r8, cs:?NatSharedConnectionDomainName@@3PEADEA; char *
0x18007c5eb  mov     edx, edi; unsigned __int64
0x18007c5ed  mov     rcx, rax; char *
0x18007c5f0  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18007c5f5  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007c5fc  call    cs:__imp_LeaveCriticalSection
0x18007c602  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c609  cmp     rcx, r15
0x18007c60c  jz      short loc_18007C635
0x18007c60e  test    dword ptr [rcx+1Ch], 200h
0x18007c615  jz      short loc_18007C635
0x18007c617  cmp     byte ptr [rcx+19h], 6
0x18007c61b  jb      short loc_18007C635
0x18007c61d  mov     rcx, [rcx+10h]
0x18007c621  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007c628  mov     edx, 0C1h
0x18007c62d  mov     r9, rbx
0x18007c630  call    WPP_SF_s
0x18007c635  mov     rax, rbx
0x18007c638  add     rsp, 28h
0x18007c63c  pop     r15
0x18007c63e  pop     rdi
0x18007c63f  pop     rsi
0x18007c640  pop     rbx
0x18007c641  retn
```
