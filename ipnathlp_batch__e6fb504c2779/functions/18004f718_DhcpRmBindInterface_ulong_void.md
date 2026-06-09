# DhcpRmBindInterface(ulong,void *)

- ea: `0x18004f718`
- end: `0x18004f878`
- name: `?DhcpRmBindInterface@@YAKKPEAX@Z`
- size: `352`
- prototype: `unsigned int __fastcall(unsigned int, struct IP_ADAPTER_BINDING_INFO *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002470c`
- `0x18005c4f0`
- `0x1800753a8`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000d090`
- `0x18000fde0`
- `0x18002fa58`
- `0x18004f718`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f812`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f812`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18004f7a4`
- `DNSAPI!DnsQueryConfigAllocEx` at `0x18004f7a4`
- `DNSAPI!DnsFree` at `0x18004f7dc`
- `DNSAPI!DnsFree` at `0x18004f7f8`
- `DNSAPI!DnsFree` at `0x18004f7dc`
- `DNSAPI!DnsFree` at `0x18004f7f8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18004f7c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18004f7c7`

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
    v8 = &word_18009D9CA;
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
0x18004f718  mov     [rsp+arg_0], rbx
0x18004f71d  mov     [rsp+arg_8], rsi
0x18004f722  push    rdi
0x18004f723  sub     rsp, 20h
0x18004f727  mov     rdi, rdx
0x18004f72a  mov     ebx, ecx
0x18004f72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f733  lea     rsi, WPP_GLOBAL_Control
0x18004f73a  cmp     rcx, rsi
0x18004f73d  jz      short loc_18004F763
0x18004f73f  test    byte ptr [rcx+1Ch], 2
0x18004f743  jz      short loc_18004F763
0x18004f745  cmp     byte ptr [rcx+19h], 6
0x18004f749  jb      short loc_18004F763
0x18004f74b  mov     rcx, [rcx+10h]
0x18004f74f  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18004f756  mov     edx, 3Ah ; ':'
0x18004f75b  mov     r9d, ebx
0x18004f75e  call    WPP_SF_d
0x18004f763  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18004f76a  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18004f76f  test    al, al
0x18004f771  jnz     short loc_18004F77D
0x18004f773  mov     eax, 3EBh
0x18004f778  jmp     loc_18004F867
0x18004f77d  mov     rdx, rdi; struct IP_ADAPTER_BINDING_INFO *
0x18004f780  mov     ecx, ebx; unsigned int
0x18004f782  call    ?DhcpBindInterface@@YAKKPEAUIP_ADAPTER_BINDING_INFO@@@Z; DhcpBindInterface(ulong,IP_ADAPTER_BINDING_INFO *)
0x18004f787  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004f78e  mov     edi, eax
0x18004f790  call    cs:__imp_EnterCriticalSection
0x18004f797  nop     dword ptr [rax+rax+00h]
0x18004f79c  xor     edx, edx
0x18004f79e  xor     r8d, r8d
0x18004f7a1  lea     ecx, [rdx+1]
0x18004f7a4  call    cs:__imp_DnsQueryConfigAllocEx
0x18004f7ab  nop     dword ptr [rax+rax+00h]
0x18004f7b0  mov     rbx, rax
0x18004f7b3  test    rax, rax
0x18004f7b6  jz      short loc_18004F80B
0x18004f7b8  mov     rdx, cs:?DhcpDomainName@@3PEADEA; lpString2
0x18004f7bf  test    rdx, rdx
0x18004f7c2  jz      short loc_18004F804
0x18004f7c4  mov     rcx, rax; lpString1
0x18004f7c7  call    cs:__imp_lstrcmpiA
0x18004f7ce  nop     dword ptr [rax+rax+00h]
0x18004f7d3  test    eax, eax
0x18004f7d5  jnz     short loc_18004F7EA
0x18004f7d7  xor     edx, edx; FreeType
0x18004f7d9  mov     rcx, rbx; pData
0x18004f7dc  call    cs:__imp_DnsFree
0x18004f7e3  nop     dword ptr [rax+rax+00h]
0x18004f7e8  jmp     short loc_18004F80B
0x18004f7ea  mov     rcx, cs:?DhcpDomainName@@3PEADEA; pData
0x18004f7f1  test    rcx, rcx
0x18004f7f4  jz      short loc_18004F804
0x18004f7f6  xor     edx, edx; FreeType
0x18004f7f8  call    cs:__imp_DnsFree
0x18004f7ff  nop     dword ptr [rax+rax+00h]
0x18004f804  mov     cs:?DhcpDomainName@@3PEADEA, rbx; char * DhcpDomainName
0x18004f80b  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004f812  call    cs:__imp_LeaveCriticalSection
0x18004f819  nop     dword ptr [rax+rax+00h]
0x18004f81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f825  cmp     rcx, rsi
0x18004f828  jz      short loc_18004F859
0x18004f82a  test    byte ptr [rcx+1Ch], 2
0x18004f82e  jz      short loc_18004F859
0x18004f830  cmp     byte ptr [rcx+19h], 6
0x18004f834  jb      short loc_18004F859
0x18004f836  mov     rcx, [rcx+10h]
0x18004f83a  lea     r9, word_18009D9CA
0x18004f841  test    rbx, rbx
0x18004f844  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18004f84b  mov     edx, 3Bh ; ';'
0x18004f850  cmovnz  r9, rbx
0x18004f854  call    WPP_SF_s
0x18004f859  lea     rcx, ?DhcpComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18004f860  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004f865  mov     eax, edi
0x18004f867  mov     rbx, [rsp+28h+arg_0]
0x18004f86c  mov     rsi, [rsp+28h+arg_8]
0x18004f871  add     rsp, 20h
0x18004f875  pop     rdi
0x18004f876  retn
```
