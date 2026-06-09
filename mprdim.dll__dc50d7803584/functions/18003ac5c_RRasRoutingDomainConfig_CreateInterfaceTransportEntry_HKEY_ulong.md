# RRasRoutingDomainConfig::CreateInterfaceTransportEntry(HKEY__ *,ulong)

- ea: `0x18003ac5c`
- end: `0x18003ae7f`
- name: `?CreateInterfaceTransportEntry@RRasRoutingDomainConfig@@AEAAKPEAUHKEY__@@K@Z`
- size: `547`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, HKEY, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a874`

## callees

- `0x18003ac5c`
- `0x180044758`
- `0x180044840`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ae55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ae55`
- `KERNEL32!GetProcessHeap` at `0x18003ae47`
- `KERNEL32!GetProcessHeap` at `0x18003ae47`
- `ADVAPI32!RegSetValueExW` at `0x18003ad96`
- `ADVAPI32!RegSetValueExW` at `0x18003addb`
- `ADVAPI32!RegSetValueExW` at `0x18003ad96`
- `ADVAPI32!RegSetValueExW` at `0x18003addb`
- `ADVAPI32!RegCloseKey` at `0x18003ae3c`
- `ADVAPI32!RegCloseKey` at `0x18003ae3c`
- `ADVAPI32!RegCreateKeyExW` at `0x18003ad4c`
- `ADVAPI32!RegCreateKeyExW` at `0x18003ad4c`

## string_xrefs

- `0x18003ad82`: `ProtocolId`
- `0x18003adfa`: `RRasRoutingDomainConfig::CreateInterfaceTransportEntry`
- `0x18003acf4`: `%s: failed to create interfaceInfo: %d`
- `0x18003ad66`: `%s: RegCreateKeyEx failed : %d`
- `0x18003adb0`: `%s: RegSetValueEx failed for protocolId : %d`
- `0x18003adf1`: `%s: RegSetValueEx failed for InterfaceInfo : %d`

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
    if ( !(_QWORD)xmmword_180071090 )
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
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_19;
    v8 = L"%s: RegCreateKeyEx failed : %d";
    goto LABEL_18;
  }
  v7 = RegSetValueExW(hKey, L"ProtocolId", 0, 4u, Data, 4u);
  if ( v7 )
  {
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_19;
    v8 = L"%s: RegSetValueEx failed for protocolId : %d";
    goto LABEL_18;
  }
  v7 = RegSetValueExW(hKey, L"InterfaceInfo", 0, 3u, v6, cbData);
  if ( v7 && (_QWORD)xmmword_180071090 )
  {
    v8 = L"%s: RegSetValueEx failed for InterfaceInfo : %d";
LABEL_18:
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, v8, L"RRasRoutingDomainConfig::CreateInterfaceTransportEntry", v7);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
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
0x18003ac5c  mov     [rsp-8+arg_0], rbx
0x18003ac61  push    rbp
0x18003ac62  push    rsi
0x18003ac63  push    rdi
0x18003ac64  lea     rbp, [rsp-780h]
0x18003ac6c  sub     rsp, 880h
0x18003ac73  mov     rax, cs:__security_cookie
0x18003ac7a  xor     rax, rsp
0x18003ac7d  mov     [rbp+790h+var_20], rax
0x18003ac84  mov     ebx, r8d
0x18003ac87  mov     [rsp+890h+lpData], 0
0x18003ac90  mov     rsi, rdx
0x18003ac93  mov     dword ptr [rsp+890h+Data], ebx
0x18003ac97  xor     eax, eax
0x18003ac99  mov     [rsp+890h+cbData], 0
0x18003aca1  xor     edx, edx; Val
0x18003aca3  mov     [rsp+890h+var_820], eax
0x18003aca7  mov     r8d, 7FCh; Size
0x18003acad  mov     [rsp+890h+hKey], 0
0x18003acb6  lea     rcx, [rsp+890h+var_81C]; void *
0x18003acbb  call    memset_0
0x18003acc0  lea     rdx, [rsp+890h+lpData]; unsigned __int8 **
0x18003acc5  lea     rcx, [rsp+890h+cbData]; unsigned int *
0x18003acca  cmp     ebx, 21h ; '!'
0x18003accd  jnz     short loc_18003ACD6
0x18003accf  call    ?DimMakeIpInterfaceInfo@@YAKPEAKPEAPEAE@Z; DimMakeIpInterfaceInfo(ulong *,uchar * *)
0x18003acd4  jmp     short loc_18003ACDB
0x18003acd6  call    ?DimMakeIpv6InterfaceInfo@@YAKPEAKPEAPEAE@Z; DimMakeIpv6InterfaceInfo(ulong *,uchar * *)
0x18003acdb  mov     rdi, [rsp+890h+lpData]
0x18003ace0  mov     ebx, eax
0x18003ace2  test    eax, eax
0x18003ace4  jz      short loc_18003AD00
0x18003ace6  cmp     qword ptr cs:xmmword_180071090, 0
0x18003acee  jz      loc_18003AE32
0x18003acf4  lea     rdx, aSFailedToCreat; "%s: failed to create interfaceInfo: %d"
0x18003acfb  jmp     loc_18003ADF8
0x18003ad00  cmp     dword ptr [rsp+890h+Data], 21h ; '!'
0x18003ad05  lea     rax, aIpv6; "Ipv6"
0x18003ad0c  mov     [rsp+890h+lpdwDisposition], 0; lpdwDisposition
0x18003ad15  lea     rdx, aIpv4; "Ipv4"
0x18003ad1c  cmovnz  rdx, rax; lpSubKey
0x18003ad20  mov     rcx, rsi; hKey
0x18003ad23  lea     rax, [rsp+890h+hKey]
0x18003ad28  xor     r9d, r9d; lpClass
0x18003ad2b  mov     [rsp+890h+phkResult], rax; phkResult
0x18003ad30  xor     r8d, r8d; Reserved
0x18003ad33  mov     [rsp+890h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003ad3c  mov     [rsp+890h+samDesired], 3001Fh; samDesired
0x18003ad44  mov     [rsp+890h+dwOptions], 0; dwOptions
0x18003ad4c  call    cs:__imp_RegCreateKeyExW
0x18003ad52  mov     ebx, eax
0x18003ad54  test    eax, eax
0x18003ad56  jz      short loc_18003AD72
0x18003ad58  cmp     qword ptr cs:xmmword_180071090, 0
0x18003ad60  jz      loc_18003AE32
0x18003ad66  lea     rdx, aSRegcreatekeye; "%s: RegCreateKeyEx failed : %d"
0x18003ad6d  jmp     loc_18003ADF8
0x18003ad72  mov     rcx, [rsp+890h+hKey]; hKey
0x18003ad77  lea     rax, [rsp+890h+Data]
0x18003ad7c  mov     r9d, 4; dwType
0x18003ad82  lea     rdx, aProtocolid; "ProtocolId"
0x18003ad89  mov     [rsp+890h+samDesired], r9d; cbData
0x18003ad8e  xor     r8d, r8d; Reserved
0x18003ad91  mov     qword ptr [rsp+890h+dwOptions], rax; lpData
0x18003ad96  call    cs:__imp_RegSetValueExW
0x18003ad9c  mov     ebx, eax
0x18003ad9e  test    eax, eax
0x18003ada0  jz      short loc_18003ADB9
0x18003ada2  cmp     qword ptr cs:xmmword_180071090, 0
0x18003adaa  jz      loc_18003AE32
0x18003adb0  lea     rdx, aSRegsetvalueex; "%s: RegSetValueEx failed for protocolId"...
0x18003adb7  jmp     short loc_18003ADF8
0x18003adb9  mov     eax, [rsp+890h+cbData]
0x18003adbd  lea     rdx, aInterfaceinfo; "InterfaceInfo"
0x18003adc4  mov     rcx, [rsp+890h+hKey]; hKey
0x18003adc9  mov     r9d, 3; dwType
0x18003adcf  mov     [rsp+890h+samDesired], eax; cbData
0x18003add3  xor     r8d, r8d; Reserved
0x18003add6  mov     qword ptr [rsp+890h+dwOptions], rdi; lpData
0x18003addb  call    cs:__imp_RegSetValueExW
0x18003ade1  mov     ebx, eax
0x18003ade3  test    eax, eax
0x18003ade5  jz      short loc_18003AE32
0x18003ade7  cmp     qword ptr cs:xmmword_180071090, 0
0x18003adef  jz      short loc_18003AE32
0x18003adf1  lea     rdx, aSRegsetvalueex_1; "%s: RegSetValueEx failed for InterfaceI"...
0x18003adf8  xor     eax, eax
0x18003adfa  lea     r8, aRrasroutingdom_51; "RRasRoutingDomainConfig::CreateInterfac"...
0x18003ae01  mov     r9d, ebx
0x18003ae04  mov     word ptr [rsp+890h+var_820], ax
0x18003ae09  lea     rcx, [rsp+890h+var_820]
0x18003ae0e  call    FormatRRASErrorString
0x18003ae13  mov     rdx, qword ptr cs:xmmword_180071090
0x18003ae1a  lea     r8, [rsp+890h+var_820]
0x18003ae1f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003ae26  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ae2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae32  mov     rcx, [rsp+890h+hKey]; hKey
0x18003ae37  test    rcx, rcx
0x18003ae3a  jz      short loc_18003AE42
0x18003ae3c  call    cs:__imp_RegCloseKey
0x18003ae42  test    rdi, rdi
0x18003ae45  jz      short loc_18003AE5B
0x18003ae47  call    cs:__imp_GetProcessHeap
0x18003ae4d  mov     r8, rdi; lpMem
0x18003ae50  xor     edx, edx; dwFlags
0x18003ae52  mov     rcx, rax; hHeap
0x18003ae55  call    cs:__imp_HeapFree
0x18003ae5b  mov     eax, ebx
0x18003ae5d  mov     rcx, [rbp+790h+var_20]
0x18003ae64  xor     rcx, rsp; StackCookie
0x18003ae67  call    __security_check_cookie
0x18003ae6c  mov     rbx, [rsp+890h+arg_0]
0x18003ae74  add     rsp, 880h
0x18003ae7b  pop     rdi
0x18003ae7c  pop     rsi
0x18003ae7d  pop     rbp
0x18003ae7e  retn
```
