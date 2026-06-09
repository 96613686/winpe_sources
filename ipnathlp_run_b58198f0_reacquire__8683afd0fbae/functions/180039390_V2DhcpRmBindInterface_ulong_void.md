# V2DhcpRmBindInterface(ulong,void *)

- ea: `0x180039390`
- end: `0x1800394df`
- name: `?V2DhcpRmBindInterface@@YAKKPEAX@Z`
- size: `335`
- prototype: `unsigned int __fastcall(unsigned int, struct IP_ADAPTER_BINDING_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dedc`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x180039390`
- `0x1800394e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039405`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039487`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180039419`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x180039419`
- `DNSAPI!DnsFree` at `0x180039451`
- `DNSAPI!DnsFree` at `0x18003946d`
- `DNSAPI!DnsFree` at `0x180039451`
- `DNSAPI!DnsFree` at `0x18003946d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18003943c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18003943c`

## pseudocode

```c
__int64 __fastcall V2DhcpRmBindInterface(unsigned int a1, struct IP_ADAPTER_BINDING_INFO *a2)
{
  unsigned int v5; // edi
  const CHAR *ConfigAlloc; // rax
  CHAR *v7; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
  }
  if ( !AcquireComponentReference(&V2DhcpComponentReference) )
    return 1003;
  v5 = V2DhcpBindInterface(a1, a2);
  EnterCriticalSection(&V2DhcpGlobalInfoLock);
  ConfigAlloc = (const CHAR *)DnsQueryConfigAllocEx(1, 0, 0);
  v7 = (CHAR *)ConfigAlloc;
  if ( ConfigAlloc )
  {
    if ( g_v2DhcpDomainName )
    {
      if ( !lstrcmpiA(ConfigAlloc, g_v2DhcpDomainName) )
      {
        DnsFree(v7, DnsFreeFlat);
        goto LABEL_14;
      }
      if ( g_v2DhcpDomainName )
        DnsFree((PVOID)g_v2DhcpDomainName, DnsFreeFlat);
    }
    g_v2DhcpDomainName = v7;
  }
LABEL_14:
  LeaveCriticalSection(&V2DhcpGlobalInfoLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
  }
  ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&V2DhcpComponentReference);
  return v5;
}

```

## disassembly

```asm
0x180039390  mov     [rsp+arg_0], rbx
0x180039395  mov     [rsp+arg_8], rsi
0x18003939a  push    rdi
0x18003939b  sub     rsp, 20h
0x18003939f  mov     rbx, rdx
0x1800393a2  mov     edi, ecx
0x1800393a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393ab  lea     rsi, WPP_GLOBAL_Control
0x1800393b2  cmp     rcx, rsi
0x1800393b5  jz      short loc_1800393D8
0x1800393b7  test    byte ptr [rcx+1Ch], 2
0x1800393bb  jz      short loc_1800393D8
0x1800393bd  cmp     byte ptr [rcx+19h], 6
0x1800393c1  jb      short loc_1800393D8
0x1800393c3  mov     rcx, [rcx+10h]
0x1800393c7  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x1800393ce  mov     edx, 39h ; '9'
0x1800393d3  call    WPP_SF_
0x1800393d8  lea     rcx, ?V2DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800393df  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800393e4  test    al, al
0x1800393e6  jnz     short loc_1800393F2
0x1800393e8  mov     eax, 3EBh
0x1800393ed  jmp     loc_1800394CE
0x1800393f2  mov     rdx, rbx; struct IP_ADAPTER_BINDING_INFO *
0x1800393f5  mov     ecx, edi; unsigned int
0x1800393f7  call    ?V2DhcpBindInterface@@YAKKPEAUIP_ADAPTER_BINDING_INFO@@@Z; V2DhcpBindInterface(ulong,IP_ADAPTER_BINDING_INFO *)
0x1800393fc  lea     rcx, ?V2DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180039403  mov     edi, eax
0x180039405  call    cs:__imp_EnterCriticalSection
0x18003940c  nop     dword ptr [rax+rax+00h]
0x180039411  xor     edx, edx
0x180039413  xor     r8d, r8d
0x180039416  lea     ecx, [rdx+1]
0x180039419  call    cs:__imp_DnsQueryConfigAllocEx
0x180039420  nop     dword ptr [rax+rax+00h]
0x180039425  mov     rbx, rax
0x180039428  test    rax, rax
0x18003942b  jz      short loc_180039480
0x18003942d  mov     rdx, cs:?g_v2DhcpDomainName@@3PEADEA; lpString2
0x180039434  test    rdx, rdx
0x180039437  jz      short loc_180039479
0x180039439  mov     rcx, rax; lpString1
0x18003943c  call    cs:__imp_lstrcmpiA
0x180039443  nop     dword ptr [rax+rax+00h]
0x180039448  test    eax, eax
0x18003944a  jnz     short loc_18003945F
0x18003944c  xor     edx, edx; FreeType
0x18003944e  mov     rcx, rbx; pData
0x180039451  call    cs:__imp_DnsFree
0x180039458  nop     dword ptr [rax+rax+00h]
0x18003945d  jmp     short loc_180039480
0x18003945f  mov     rcx, cs:?g_v2DhcpDomainName@@3PEADEA; pData
0x180039466  test    rcx, rcx
0x180039469  jz      short loc_180039479
0x18003946b  xor     edx, edx; FreeType
0x18003946d  call    cs:__imp_DnsFree
0x180039474  nop     dword ptr [rax+rax+00h]
0x180039479  mov     cs:?g_v2DhcpDomainName@@3PEADEA, rbx; char * g_v2DhcpDomainName
0x180039480  lea     rcx, ?V2DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180039487  call    cs:__imp_LeaveCriticalSection
0x18003948e  nop     dword ptr [rax+rax+00h]
0x180039493  mov     rcx, cs:WPP_GLOBAL_Control
0x18003949a  cmp     rcx, rsi
0x18003949d  jz      short loc_1800394C0
0x18003949f  test    byte ptr [rcx+1Ch], 2
0x1800394a3  jz      short loc_1800394C0
0x1800394a5  cmp     byte ptr [rcx+19h], 6
0x1800394a9  jb      short loc_1800394C0
0x1800394ab  mov     rcx, [rcx+10h]
0x1800394af  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x1800394b6  mov     edx, 3Ah ; ':'
0x1800394bb  call    WPP_SF_
0x1800394c0  lea     rcx, ?V2DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x1800394c7  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x1800394cc  mov     eax, edi
0x1800394ce  mov     rbx, [rsp+28h+arg_0]
0x1800394d3  mov     rsi, [rsp+28h+arg_8]
0x1800394d8  add     rsp, 20h
0x1800394dc  pop     rdi
0x1800394dd  retn
```
