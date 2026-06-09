# DhcpRmBindInterface(ulong,void *)

- ea: `0x18004ba94`
- end: `0x18004bbcf`
- name: `?DhcpRmBindInterface@@YAKKPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(unsigned int, struct IP_ADAPTER_BINDING_INFO *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002252c`
- `0x180057f70`
- `0x18006fa64`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c750`
- `0x18000f250`
- `0x18002b350`
- `0x18004ba94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bb0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bb0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bb70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bb70`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18004bb1a`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18004bb1a`
- `DNSAPI!DnsFree` at `0x18004bb46`
- `DNSAPI!DnsFree` at `0x18004bb5c`
- `DNSAPI!DnsFree` at `0x18004bb46`
- `DNSAPI!DnsFree` at `0x18004bb5c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18004bb37`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18004bb37`

## pseudocode

```c
__int64 __fastcall DhcpRmBindInterface(unsigned int a1, struct IP_ADAPTER_BINDING_INFO *a2)
{
  unsigned int v5; // edi
  const CHAR *ConfigAlloc; // rax
  CHAR *v7; // rbx
  const unsigned __int16 *v8; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids, a1);
  }
  if ( !AcquireComponentReference(&DhcpComponentReference) )
    return 1003;
  v5 = DhcpBindInterface(a1, a2);
  EnterCriticalSection(&DhcpGlobalInfoLock);
  ConfigAlloc = (const CHAR *)DnsQueryConfigAllocEx(1, 0, 0);
  v7 = (CHAR *)ConfigAlloc;
  if ( ConfigAlloc )
  {
    if ( DhcpDomainName )
    {
      if ( !lstrcmpiA(ConfigAlloc, (LPCSTR)DhcpDomainName) )
      {
        DnsFree(v7, DnsFreeFlat);
        goto LABEL_14;
      }
      if ( DhcpDomainName )
        DnsFree(DhcpDomainName, DnsFreeFlat);
    }
    DhcpDomainName = v7;
  }
LABEL_14:
  LeaveCriticalSection(&DhcpGlobalInfoLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v8 = &word_1800969CA;
    if ( v7 )
      v8 = (const unsigned __int16 *)v7;
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids, v8);
  }
  ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&DhcpComponentReference);
  return v5;
}

```

## disassembly

```asm
0x18004ba94  mov     [rsp+arg_0], rbx
0x18004ba99  mov     [rsp+arg_8], rsi
0x18004ba9e  push    rdi
0x18004ba9f  sub     rsp, 20h
0x18004baa3  mov     rdi, rdx
0x18004baa6  mov     ebx, ecx
0x18004baa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004baaf  lea     rsi, WPP_GLOBAL_Control
0x18004bab6  cmp     rcx, rsi
0x18004bab9  jz      short loc_18004BADF
0x18004babb  test    byte ptr [rcx+1Ch], 2
0x18004babf  jz      short loc_18004BADF
0x18004bac1  cmp     byte ptr [rcx+19h], 6
0x18004bac5  jb      short loc_18004BADF
0x18004bac7  mov     rcx, [rcx+10h]
0x18004bacb  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18004bad2  mov     edx, 3Ah ; ':'
0x18004bad7  mov     r9d, ebx
0x18004bada  call    WPP_SF_d
0x18004badf  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18004bae6  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18004baeb  test    al, al
0x18004baed  jnz     short loc_18004BAF9
0x18004baef  mov     eax, 3EBh
0x18004baf4  jmp     loc_18004BBBF
0x18004baf9  mov     rdx, rdi; struct IP_ADAPTER_BINDING_INFO *
0x18004bafc  mov     ecx, ebx; unsigned int
0x18004bafe  call    ?DhcpBindInterface@@YAKKPEAUIP_ADAPTER_BINDING_INFO@@@Z; DhcpBindInterface(ulong,IP_ADAPTER_BINDING_INFO *)
0x18004bb03  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004bb0a  mov     edi, eax
0x18004bb0c  call    cs:__imp_EnterCriticalSection
0x18004bb12  xor     edx, edx
0x18004bb14  xor     r8d, r8d
0x18004bb17  lea     ecx, [rdx+1]
0x18004bb1a  call    cs:__imp_DnsQueryConfigAllocEx
0x18004bb20  mov     rbx, rax
0x18004bb23  test    rax, rax
0x18004bb26  jz      short loc_18004BB69
0x18004bb28  mov     rdx, cs:?DhcpDomainName@@3PEADEA; lpString2
0x18004bb2f  test    rdx, rdx
0x18004bb32  jz      short loc_18004BB62
0x18004bb34  mov     rcx, rax; lpString1
0x18004bb37  call    cs:__imp_lstrcmpiA
0x18004bb3d  test    eax, eax
0x18004bb3f  jnz     short loc_18004BB4E
0x18004bb41  xor     edx, edx; FreeType
0x18004bb43  mov     rcx, rbx; pData
0x18004bb46  call    cs:__imp_DnsFree
0x18004bb4c  jmp     short loc_18004BB69
0x18004bb4e  mov     rcx, cs:?DhcpDomainName@@3PEADEA; pData
0x18004bb55  test    rcx, rcx
0x18004bb58  jz      short loc_18004BB62
0x18004bb5a  xor     edx, edx; FreeType
0x18004bb5c  call    cs:__imp_DnsFree
0x18004bb62  mov     cs:?DhcpDomainName@@3PEADEA, rbx; char * DhcpDomainName
0x18004bb69  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004bb70  call    cs:__imp_LeaveCriticalSection
0x18004bb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb7d  cmp     rcx, rsi
0x18004bb80  jz      short loc_18004BBB1
0x18004bb82  test    byte ptr [rcx+1Ch], 2
0x18004bb86  jz      short loc_18004BBB1
0x18004bb88  cmp     byte ptr [rcx+19h], 6
0x18004bb8c  jb      short loc_18004BBB1
0x18004bb8e  mov     rcx, [rcx+10h]
0x18004bb92  lea     r9, word_1800969CA
0x18004bb99  test    rbx, rbx
0x18004bb9c  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18004bba3  mov     edx, 3Bh ; ';'
0x18004bba8  cmovnz  r9, rbx
0x18004bbac  call    WPP_SF_s
0x18004bbb1  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18004bbb8  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004bbbd  mov     eax, edi
0x18004bbbf  mov     rbx, [rsp+28h+arg_0]
0x18004bbc4  mov     rsi, [rsp+28h+arg_8]
0x18004bbc9  add     rsp, 20h
0x18004bbcd  pop     rdi
0x18004bbce  retn
```
