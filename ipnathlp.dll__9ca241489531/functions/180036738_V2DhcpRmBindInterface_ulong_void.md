# V2DhcpRmBindInterface(ulong,void *)

- ea: `0x180036738`
- end: `0x180036862`
- name: `?V2DhcpRmBindInterface@@YAKKPEAX@Z`
- size: `298`
- prototype: `unsigned int __fastcall(unsigned int, struct IP_ADAPTER_BINDING_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021ab0`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x180036738`
- `0x180036868`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800367ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800367ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036811`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036811`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x1800367bb`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x1800367bb`
- `DNSAPI!DnsFree` at `0x1800367e7`
- `DNSAPI!DnsFree` at `0x1800367fd`
- `DNSAPI!DnsFree` at `0x1800367e7`
- `DNSAPI!DnsFree` at `0x1800367fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x1800367d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x1800367d8`

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
0x180036738  mov     [rsp+arg_0], rbx
0x18003673d  mov     [rsp+arg_8], rsi
0x180036742  push    rdi
0x180036743  sub     rsp, 20h
0x180036747  mov     rbx, rdx
0x18003674a  mov     edi, ecx
0x18003674c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036753  lea     rsi, WPP_GLOBAL_Control
0x18003675a  cmp     rcx, rsi
0x18003675d  jz      short loc_180036780
0x18003675f  test    byte ptr [rcx+1Ch], 2
0x180036763  jz      short loc_180036780
0x180036765  cmp     byte ptr [rcx+19h], 6
0x180036769  jb      short loc_180036780
0x18003676b  mov     rcx, [rcx+10h]
0x18003676f  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180036776  mov     edx, 39h ; '9'
0x18003677b  call    WPP_SF_
0x180036780  lea     rcx, ?V2DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x180036787  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18003678c  test    al, al
0x18003678e  jnz     short loc_18003679A
0x180036790  mov     eax, 3EBh
0x180036795  jmp     loc_180036852
0x18003679a  mov     rdx, rbx; struct IP_ADAPTER_BINDING_INFO *
0x18003679d  mov     ecx, edi; unsigned int
0x18003679f  call    ?V2DhcpBindInterface@@YAKKPEAUIP_ADAPTER_BINDING_INFO@@@Z; V2DhcpBindInterface(ulong,IP_ADAPTER_BINDING_INFO *)
0x1800367a4  lea     rcx, ?V2DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800367ab  mov     edi, eax
0x1800367ad  call    cs:__imp_EnterCriticalSection
0x1800367b3  xor     edx, edx
0x1800367b5  xor     r8d, r8d
0x1800367b8  lea     ecx, [rdx+1]
0x1800367bb  call    cs:__imp_DnsQueryConfigAllocEx
0x1800367c1  mov     rbx, rax
0x1800367c4  test    rax, rax
0x1800367c7  jz      short loc_18003680A
0x1800367c9  mov     rdx, cs:?g_v2DhcpDomainName@@3PEADEA; lpString2
0x1800367d0  test    rdx, rdx
0x1800367d3  jz      short loc_180036803
0x1800367d5  mov     rcx, rax; lpString1
0x1800367d8  call    cs:__imp_lstrcmpiA
0x1800367de  test    eax, eax
0x1800367e0  jnz     short loc_1800367EF
0x1800367e2  xor     edx, edx; FreeType
0x1800367e4  mov     rcx, rbx; pData
0x1800367e7  call    cs:__imp_DnsFree
0x1800367ed  jmp     short loc_18003680A
0x1800367ef  mov     rcx, cs:?g_v2DhcpDomainName@@3PEADEA; pData
0x1800367f6  test    rcx, rcx
0x1800367f9  jz      short loc_180036803
0x1800367fb  xor     edx, edx; FreeType
0x1800367fd  call    cs:__imp_DnsFree
0x180036803  mov     cs:?g_v2DhcpDomainName@@3PEADEA, rbx; char * g_v2DhcpDomainName
0x18003680a  lea     rcx, ?V2DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036811  call    cs:__imp_LeaveCriticalSection
0x180036817  mov     rcx, cs:WPP_GLOBAL_Control
0x18003681e  cmp     rcx, rsi
0x180036821  jz      short loc_180036844
0x180036823  test    byte ptr [rcx+1Ch], 2
0x180036827  jz      short loc_180036844
0x180036829  cmp     byte ptr [rcx+19h], 6
0x18003682d  jb      short loc_180036844
0x18003682f  mov     rcx, [rcx+10h]
0x180036833  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x18003683a  mov     edx, 3Ah ; ':'
0x18003683f  call    WPP_SF_
0x180036844  lea     rcx, ?V2DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18003684b  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180036850  mov     eax, edi
0x180036852  mov     rbx, [rsp+28h+arg_0]
0x180036857  mov     rsi, [rsp+28h+arg_8]
0x18003685c  add     rsp, 20h
0x180036860  pop     rdi
0x180036861  retn
```
