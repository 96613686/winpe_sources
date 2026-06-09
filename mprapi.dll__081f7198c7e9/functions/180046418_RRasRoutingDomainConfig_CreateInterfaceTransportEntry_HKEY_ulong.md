# RRasRoutingDomainConfig::CreateInterfaceTransportEntry(HKEY__ *,ulong)

- ea: `0x180046418`
- end: `0x18004663b`
- name: `?CreateInterfaceTransportEntry@RRasRoutingDomainConfig@@AEAAKPEAUHKEY__@@K@Z`
- size: `547`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, HKEY, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046014`

## callees

- `0x180046418`
- `0x18004fe38`
- `0x18004ff20`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046603`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046611`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046611`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800465f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800465f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046597`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046597`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046508`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046508`

## string_xrefs

- `0x1800465b6`: `RRasRoutingDomainConfig::CreateInterfaceTransportEntry`
- `0x1800464b0`: `%s: failed to create interfaceInfo: %d`
- `0x180046522`: `%s: RegCreateKeyEx failed : %d`
- `0x18004653e`: `ProtocolId`
- `0x18004656c`: `%s: RegSetValueEx failed for protocolId : %d`
- `0x1800465ad`: `%s: RegSetValueEx failed for InterfaceInfo : %d`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::CreateInterfaceTransportEntry(
        RRasRoutingDomainConfig *this,
        HKEY a2,
        int a3)
{
  unsigned int IpInterfaceInfo; // eax
  BYTE *v6; // rdi
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  const WCHAR *v9; // rdx
  HANDLE ProcessHeap; // rax
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *lpData; // [rsp+68h] [rbp-98h] BYREF
  int v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  lpData = 0;
  *(_DWORD *)Data = a3;
  cbData = 0;
  v16 = 0;
  hKey = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( a3 == 33 )
    IpInterfaceInfo = DimMakeIpInterfaceInfo(&cbData, &lpData);
  else
    IpInterfaceInfo = DimMakeIpv6InterfaceInfo(&cbData, &lpData);
  v6 = lpData;
  v7 = IpInterfaceInfo;
  if ( IpInterfaceInfo )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_19;
    v8 = L"%s: failed to create interfaceInfo: %d";
    goto LABEL_18;
  }
  v9 = L"Ipv4";
  if ( *(_DWORD *)Data != 33 )
    v9 = L"Ipv6";
  v7 = RegCreateKeyExW(a2, v9, 0, 0, 0, 0x3001Fu, 0, &hKey, 0);
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_19;
    v8 = L"%s: RegCreateKeyEx failed : %d";
    goto LABEL_18;
  }
  v7 = RegSetValueExW(hKey, L"ProtocolId", 0, 4u, Data, 4u);
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_19;
    v8 = L"%s: RegSetValueEx failed for protocolId : %d";
    goto LABEL_18;
  }
  v7 = RegSetValueExW(hKey, L"InterfaceInfo", 0, 3u, v6, cbData);
  if ( v7 && (_QWORD)xmmword_180078C50 )
  {
    v8 = L"%s: RegSetValueEx failed for InterfaceInfo : %d";
LABEL_18:
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, v8, L"RRasRoutingDomainConfig::CreateInterfaceTransportEntry", v7);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v16);
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180046418  mov     [rsp-8+arg_0], rbx
0x18004641d  push    rbp
0x18004641e  push    rsi
0x18004641f  push    rdi
0x180046420  lea     rbp, [rsp-780h]
0x180046428  sub     rsp, 880h
0x18004642f  mov     rax, cs:__security_cookie
0x180046436  xor     rax, rsp
0x180046439  mov     [rbp+790h+var_20], rax
0x180046440  mov     ebx, r8d
0x180046443  mov     [rsp+890h+lpData], 0
0x18004644c  mov     rsi, rdx
0x18004644f  mov     dword ptr [rsp+890h+Data], ebx
0x180046453  xor     eax, eax
0x180046455  mov     [rsp+890h+cbData], 0
0x18004645d  xor     edx, edx; Val
0x18004645f  mov     [rsp+890h+var_820], eax
0x180046463  mov     r8d, 7FCh; Size
0x180046469  mov     [rsp+890h+hKey], 0
0x180046472  lea     rcx, [rsp+890h+var_81C]; void *
0x180046477  call    memset_0
0x18004647c  lea     rdx, [rsp+890h+lpData]; unsigned __int8 **
0x180046481  lea     rcx, [rsp+890h+cbData]; unsigned int *
0x180046486  cmp     ebx, 21h ; '!'
0x180046489  jnz     short loc_180046492
0x18004648b  call    ?DimMakeIpInterfaceInfo@@YAKPEAKPEAPEAE@Z; DimMakeIpInterfaceInfo(ulong *,uchar * *)
0x180046490  jmp     short loc_180046497
0x180046492  call    ?DimMakeIpv6InterfaceInfo@@YAKPEAKPEAPEAE@Z; DimMakeIpv6InterfaceInfo(ulong *,uchar * *)
0x180046497  mov     rdi, [rsp+890h+lpData]
0x18004649c  mov     ebx, eax
0x18004649e  test    eax, eax
0x1800464a0  jz      short loc_1800464BC
0x1800464a2  cmp     qword ptr cs:xmmword_180078C50, 0
0x1800464aa  jz      loc_1800465EE
0x1800464b0  lea     rdx, aSFailedToCreat; "%s: failed to create interfaceInfo: %d"
0x1800464b7  jmp     loc_1800465B4
0x1800464bc  cmp     dword ptr [rsp+890h+Data], 21h ; '!'
0x1800464c1  lea     rax, aIpv6; "Ipv6"
0x1800464c8  mov     [rsp+890h+lpdwDisposition], 0; lpdwDisposition
0x1800464d1  lea     rdx, aIpv4; "Ipv4"
0x1800464d8  cmovnz  rdx, rax; lpSubKey
0x1800464dc  mov     rcx, rsi; hKey
0x1800464df  lea     rax, [rsp+890h+hKey]
0x1800464e4  xor     r9d, r9d; lpClass
0x1800464e7  mov     [rsp+890h+phkResult], rax; phkResult
0x1800464ec  xor     r8d, r8d; Reserved
0x1800464ef  mov     [rsp+890h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800464f8  mov     [rsp+890h+samDesired], 3001Fh; samDesired
0x180046500  mov     [rsp+890h+dwOptions], 0; dwOptions
0x180046508  call    cs:__imp_RegCreateKeyExW
0x18004650e  mov     ebx, eax
0x180046510  test    eax, eax
0x180046512  jz      short loc_18004652E
0x180046514  cmp     qword ptr cs:xmmword_180078C50, 0
0x18004651c  jz      loc_1800465EE
0x180046522  lea     rdx, aSRegcreatekeye; "%s: RegCreateKeyEx failed : %d"
0x180046529  jmp     loc_1800465B4
0x18004652e  mov     rcx, [rsp+890h+hKey]; hKey
0x180046533  lea     rax, [rsp+890h+Data]
0x180046538  mov     r9d, 4; dwType
0x18004653e  lea     rdx, aProtocolid; "ProtocolId"
0x180046545  mov     [rsp+890h+samDesired], r9d; cbData
0x18004654a  xor     r8d, r8d; Reserved
0x18004654d  mov     qword ptr [rsp+890h+dwOptions], rax; lpData
0x180046552  call    cs:__imp_RegSetValueExW
0x180046558  mov     ebx, eax
0x18004655a  test    eax, eax
0x18004655c  jz      short loc_180046575
0x18004655e  cmp     qword ptr cs:xmmword_180078C50, 0
0x180046566  jz      loc_1800465EE
0x18004656c  lea     rdx, aSRegsetvalueex; "%s: RegSetValueEx failed for protocolId"...
0x180046573  jmp     short loc_1800465B4
0x180046575  mov     eax, [rsp+890h+cbData]
0x180046579  lea     rdx, aInterfaceinfo; "InterfaceInfo"
0x180046580  mov     rcx, [rsp+890h+hKey]; hKey
0x180046585  mov     r9d, 3; dwType
0x18004658b  mov     [rsp+890h+samDesired], eax; cbData
0x18004658f  xor     r8d, r8d; Reserved
0x180046592  mov     qword ptr [rsp+890h+dwOptions], rdi; lpData
0x180046597  call    cs:__imp_RegSetValueExW
0x18004659d  mov     ebx, eax
0x18004659f  test    eax, eax
0x1800465a1  jz      short loc_1800465EE
0x1800465a3  cmp     qword ptr cs:xmmword_180078C50, 0
0x1800465ab  jz      short loc_1800465EE
0x1800465ad  lea     rdx, aSRegsetvalueex_1; "%s: RegSetValueEx failed for InterfaceI"...
0x1800465b4  xor     eax, eax
0x1800465b6  lea     r8, aRrasroutingdom_50; "RRasRoutingDomainConfig::CreateInterfac"...
0x1800465bd  mov     r9d, ebx
0x1800465c0  mov     word ptr [rsp+890h+var_820], ax
0x1800465c5  lea     rcx, [rsp+890h+var_820]
0x1800465ca  call    FormatRRASErrorString
0x1800465cf  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800465d6  lea     r8, [rsp+890h+var_820]
0x1800465db  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800465e2  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800465e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465ee  mov     rcx, [rsp+890h+hKey]; hKey
0x1800465f3  test    rcx, rcx
0x1800465f6  jz      short loc_1800465FE
0x1800465f8  call    cs:__imp_RegCloseKey
0x1800465fe  test    rdi, rdi
0x180046601  jz      short loc_180046617
0x180046603  call    cs:__imp_GetProcessHeap
0x180046609  mov     r8, rdi; lpMem
0x18004660c  xor     edx, edx; dwFlags
0x18004660e  mov     rcx, rax; hHeap
0x180046611  call    cs:__imp_HeapFree
0x180046617  mov     eax, ebx
0x180046619  mov     rcx, [rbp+790h+var_20]
0x180046620  xor     rcx, rsp; StackCookie
0x180046623  call    __security_check_cookie
0x180046628  mov     rbx, [rsp+890h+arg_0]
0x180046630  add     rsp, 880h
0x180046637  pop     rdi
0x180046638  pop     rsi
0x180046639  pop     rbp
0x18004663a  retn
```
