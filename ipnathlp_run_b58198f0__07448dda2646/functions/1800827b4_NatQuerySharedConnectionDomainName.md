# NatQuerySharedConnectionDomainName

- ea: `0x1800827b4`
- end: `0x180082971`
- name: `NatQuerySharedConnectionDomainName`
- size: `445`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180003650`
- `0x180004bd8`
- `0x18007197c`

## callees

- `0x18000ca20`
- `0x18000fde0`
- `0x18004eb64`
- `0x18008157c`
- `0x1800820c4`
- `0x1800827b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800828e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082863`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800828e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008287a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800828f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008287a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800828f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800827fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800827fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082924`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180082838`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180082838`
- `DNSAPI!DnsFree` at `0x1800828b0`
- `DNSAPI!DnsFree` at `0x1800828b0`
- `DNSAPI!DnsFreeConfigStructure` at `0x1800828c3`
- `DNSAPI!DnsFreeConfigStructure` at `0x1800828c3`

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
0x1800827b4  push    rbx
0x1800827b6  push    rsi
0x1800827b7  push    rdi
0x1800827b8  push    r15
0x1800827ba  sub     rsp, 28h
0x1800827be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800827c5  lea     r15, WPP_GLOBAL_Control
0x1800827cc  cmp     rcx, r15
0x1800827cf  jz      short loc_1800827F5
0x1800827d1  test    dword ptr [rcx+1Ch], 200h
0x1800827d8  jz      short loc_1800827F5
0x1800827da  cmp     byte ptr [rcx+19h], 6
0x1800827de  jb      short loc_1800827F5
0x1800827e0  mov     rcx, [rcx+10h]
0x1800827e4  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800827eb  mov     edx, 0C0h
0x1800827f0  call    WPP_SF_
0x1800827f5  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800827fc  call    cs:__imp_EnterCriticalSection
0x180082803  nop     dword ptr [rax+rax+00h]
0x180082808  mov     rcx, cs:?NatSharedConnectionDomainName@@3PEADEA; char * NatSharedConnectionDomainName
0x18008280f  test    rcx, rcx
0x180082812  jnz     loc_1800828D1
0x180082818  or      ecx, 0FFFFFFFFh; InterfaceIndex
0x18008281b  call    ?NatUpdateSharedConnectionDomainName@@YAXK@Z; NatUpdateSharedConnectionDomainName(ulong)
0x180082820  mov     rcx, cs:?NatSharedConnectionDomainName@@3PEADEA; char * NatSharedConnectionDomainName
0x180082827  test    rcx, rcx
0x18008282a  jnz     loc_1800828D1
0x180082830  xor     edx, edx
0x180082832  xor     r8d, r8d
0x180082835  lea     ecx, [rdx+1]
0x180082838  call    cs:__imp_DnsQueryConfigAllocEx
0x18008283f  nop     dword ptr [rax+rax+00h]
0x180082844  mov     rdi, rax
0x180082847  test    rax, rax
0x18008284a  jnz     short loc_180082853
0x18008284c  xor     ebx, ebx
0x18008284e  jmp     loc_18008291D
0x180082853  or      rax, 0FFFFFFFFFFFFFFFFh
0x180082857  inc     rax
0x18008285a  cmp     byte ptr [rdi+rax], 0
0x18008285e  jnz     short loc_180082857
0x180082860  lea     esi, [rax+1]
0x180082863  call    cs:__imp_GetProcessHeap
0x18008286a  nop     dword ptr [rax+rax+00h]
0x18008286f  mov     r8d, esi; dwBytes
0x180082872  mov     edx, 8; dwFlags
0x180082877  mov     rcx, rax; hHeap
0x18008287a  call    cs:__imp_HeapAlloc
0x180082881  nop     dword ptr [rax+rax+00h]
0x180082886  mov     rbx, rax
0x180082889  test    rax, rax
0x18008288c  jz      short loc_18008289B
0x18008288e  mov     r8, rdi; char *
0x180082891  mov     edx, esi; unsigned __int64
0x180082893  mov     rcx, rax; char *
0x180082896  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18008289b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_5977_1413@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_5977_1413@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413> `wil::Feature<__WilFeatureTraits_Feature_5977_1413>::GetImpl(void)'::`2'::impl
0x1800828a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_5977_1413@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_5977_1413>::__private_IsEnabled(void)
0x1800828a7  mov     rcx, rdi; pData
0x1800828aa  test    al, al
0x1800828ac  jz      short loc_1800828BE
0x1800828ae  xor     edx, edx; FreeType
0x1800828b0  call    cs:__imp_DnsFree
0x1800828b7  nop     dword ptr [rax+rax+00h]
0x1800828bc  jmp     short loc_18008291D
0x1800828be  mov     edx, 1
0x1800828c3  call    cs:__imp_DnsFreeConfigStructure
0x1800828ca  nop     dword ptr [rax+rax+00h]
0x1800828cf  jmp     short loc_18008291D
0x1800828d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800828d5  inc     rax
0x1800828d8  cmp     byte ptr [rcx+rax], 0
0x1800828dc  jnz     short loc_1800828D5
0x1800828de  lea     edi, [rax+1]
0x1800828e1  call    cs:__imp_GetProcessHeap
0x1800828e8  nop     dword ptr [rax+rax+00h]
0x1800828ed  mov     r8d, edi; dwBytes
0x1800828f0  mov     edx, 8; dwFlags
0x1800828f5  mov     rcx, rax; hHeap
0x1800828f8  call    cs:__imp_HeapAlloc
0x1800828ff  nop     dword ptr [rax+rax+00h]
0x180082904  mov     rbx, rax
0x180082907  test    rax, rax
0x18008290a  jz      short loc_18008291D
0x18008290c  mov     r8, cs:?NatSharedConnectionDomainName@@3PEADEA; char *
0x180082913  mov     edx, edi; unsigned __int64
0x180082915  mov     rcx, rax; char *
0x180082918  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18008291d  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180082924  call    cs:__imp_LeaveCriticalSection
0x18008292b  nop     dword ptr [rax+rax+00h]
0x180082930  mov     rcx, cs:WPP_GLOBAL_Control
0x180082937  cmp     rcx, r15
0x18008293a  jz      short loc_180082963
0x18008293c  test    dword ptr [rcx+1Ch], 200h
0x180082943  jz      short loc_180082963
0x180082945  cmp     byte ptr [rcx+19h], 6
0x180082949  jb      short loc_180082963
0x18008294b  mov     rcx, [rcx+10h]
0x18008294f  lea     r8, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180082956  mov     edx, 0C1h
0x18008295b  mov     r9, rbx
0x18008295e  call    WPP_SF_s
0x180082963  mov     rax, rbx
0x180082966  add     rsp, 28h
0x18008296a  pop     r15
0x18008296c  pop     rdi
0x18008296d  pop     rsi
0x18008296e  pop     rbx
0x18008296f  retn
```
