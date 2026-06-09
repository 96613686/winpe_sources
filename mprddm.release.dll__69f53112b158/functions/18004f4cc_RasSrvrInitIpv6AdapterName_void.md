# RasSrvrInitIpv6AdapterName(void)

- ea: `0x18004f4cc`
- end: `0x18004f8bc`
- name: `?RasSrvrInitIpv6AdapterName@@YAKXZ`
- size: `1008`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180052b74`

## callees

- `0x18004f4cc`
- `0x18005015c`
- `0x18005789c`
- `0x18005aaf8`
- `0x18005af78`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18004f73c`
- `KERNEL32!DeviceIoControl` at `0x18004f73c`
- `KERNEL32!GetLastError` at `0x18004f74c`
- `KERNEL32!GetLastError` at `0x18004f74c`
- `ADVAPI32!RegCloseKey` at `0x18004f616`
- `ADVAPI32!RegCloseKey` at `0x18004f842`
- `ADVAPI32!RegCloseKey` at `0x18004f616`
- `ADVAPI32!RegCloseKey` at `0x18004f842`
- `ADVAPI32!RegSetValueExA` at `0x18004f649`
- `ADVAPI32!RegSetValueExA` at `0x18004f649`
- `ADVAPI32!RegCreateKeyExA` at `0x18004f5a5`
- `ADVAPI32!RegCreateKeyExA` at `0x18004f5a5`
- `ADVAPI32!RegQueryValueExA` at `0x18004f5e3`
- `ADVAPI32!RegQueryValueExA` at `0x18004f5e3`

## string_xrefs

- `0x18004f58d`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x18004f861`: `RasSrvrInitIpv6AdapterName completed %d`

## pseudocode

```c
__int64 RasSrvrInitIpv6AdapterName(void)
{
  unsigned int InterfaceId; // ebx
  __int64 ServerAdapterLuidIndex; // rax
  _WORD *v2; // rcx
  __int64 v3; // rdx
  __int16 v4; // ax
  _WORD *v5; // rax
  HANDLE v6; // rcx
  DWORD LastError; // eax
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v15[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE OutBuffer[4]; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+84h] [rbp-7Ch]
  unsigned int v18; // [rsp+88h] [rbp-78h]
  _BYTE v19[516]; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v20; // [rsp+290h] [rbp+190h]
  _BYTE v21[512]; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v22; // [rsp+4A8h] [rbp+3A8h]
  int v23; // [rsp+4B0h] [rbp+3B0h]
  int v24; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v25[2044]; // [rsp+4C4h] [rbp+3C4h] BYREF

  memset_0(OutBuffer, 0, 0x438u);
  cbData = 8;
  BytesReturned = 0;
  hKey = 0;
  Type = 0;
  dwDisposition = 0;
  *(_QWORD *)Data = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasSrvrInitIpv6AdapterName entering");
  InterfaceId = RegCreateKeyExA(
                  HKEY_LOCAL_MACHINE,
                  "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6",
                  0,
                  (LPSTR)Class,
                  0,
                  3u,
                  0,
                  &hKey,
                  &dwDisposition);
  if ( !InterfaceId )
  {
    if ( RegQueryValueExA(hKey, "ServerInterfaceId", 0, &Type, Data, &cbData) || Type != 3 || cbData != 8 )
    {
      InterfaceId = RasSrvrIpv6GenerateInterfaceId(Data);
      if ( InterfaceId )
      {
        RegCloseKey(hKey);
        goto LABEL_22;
      }
      RegSetValueExA(hKey, "ServerInterfaceId", 0, 3u, Data, 8u);
    }
    v15[0] = *(_QWORD *)Data;
    RasRoutingDomainSetConfigParam(&GUID_NULL, 9, 8, v15);
    v17 = 1;
    v23 = 1;
    ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(&GUID_NULL);
    v2 = v21;
    v3 = 256;
    v20 = (ServerAdapterLuidIndex & 0xFFFFFF | 0x17000000) << 24;
    v22 = *(_QWORD *)Data;
    do
    {
      if ( v3 == -2147483390 )
        break;
      v4 = *(_WORD *)((char *)v2 + (char *)L"RAS (Dial In) Interface" - v21);
      if ( !v4 )
        break;
      *v2++ = v4;
      --v3;
    }
    while ( v3 );
    v5 = v2 - 1;
    if ( v3 )
      v5 = v2;
    v6 = HelperWanArpv6Handle;
    *v5 = 0;
    if ( DeviceIoControl(v6, 0x90018004, OutBuffer, 0x438u, OutBuffer, 0x438u, &BytesReturned, 0) )
    {
      LODWORD(v15[0]) = v18;
      RasRoutingDomainSetConfigParam(&GUID_NULL, 8, 4, v15);
      RasRoutingDomainSetConfigParam(&GUID_NULL, 6, 516, v19);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"IPV6 Add user Interface: g_ServerIfIndex %d", v18);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v24);
      }
      WriteDialinInterfaceIndexIntoRegistry(0, v18);
    }
    else
    {
      LastError = GetLastError();
      InterfaceId = LastError;
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"rasSrvrInitIpv6AdapterName: Error %d getting server name", LastError);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v24);
      }
    }
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"RasSrvrInitIpv6AdapterName completed %d", InterfaceId);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v24);
  }
  return InterfaceId;
}

```

## disassembly

```asm
0x18004f4cc  mov     [rsp-8+arg_0], rbx
0x18004f4d1  mov     [rsp-8+arg_8], rdi
0x18004f4d6  push    rbp
0x18004f4d7  lea     rbp, [rsp-0BD0h]
0x18004f4df  sub     rsp, 0CD0h
0x18004f4e6  mov     rax, cs:__security_cookie
0x18004f4ed  xor     rax, rsp
0x18004f4f0  mov     [rbp+0BD0h+var_10], rax
0x18004f4f7  xor     edx, edx; Val
0x18004f4f9  lea     rcx, [rbp+0BD0h+OutBuffer]; void *
0x18004f4fd  mov     r8d, 438h; Size
0x18004f503  call    memset_0
0x18004f508  xor     edi, edi
0x18004f50a  mov     [rsp+0CD0h+cbData], 8
0x18004f512  xor     edx, edx; Val
0x18004f514  mov     [rsp+0CD0h+BytesReturned], edi
0x18004f518  mov     r8d, 7FCh; Size
0x18004f51e  mov     [rsp+0CD0h+hKey], rdi
0x18004f523  lea     rcx, [rbp+0BD0h+var_80C]; void *
0x18004f52a  mov     [rsp+0CD0h+Type], edi
0x18004f52e  mov     [rsp+0CD0h+dwDisposition], edi
0x18004f532  mov     qword ptr [rsp+0CD0h+Data], rdi
0x18004f537  mov     [rbp+0BD0h+var_810], edi
0x18004f53d  call    memset_0
0x18004f542  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18004f549  test    rdx, rdx
0x18004f54c  jz      short loc_18004F568
0x18004f54e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f555  lea     r8, aRassrvrinitipv_1; "RasSrvrInitIpv6AdapterName entering"
0x18004f55c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f568  lea     rax, [rsp+0CD0h+dwDisposition]
0x18004f56d  xor     r8d, r8d; Reserved
0x18004f570  mov     [rsp+0CD0h+lpdwDisposition], rax; lpdwDisposition
0x18004f575  lea     r9, Class; lpClass
0x18004f57c  lea     rax, [rsp+0CD0h+hKey]
0x18004f581  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f588  mov     [rsp+0CD0h+phkResult], rax; phkResult
0x18004f58d  lea     rdx, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x18004f594  mov     [rsp+0CD0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004f599  mov     [rsp+0CD0h+samDesired], 3; samDesired
0x18004f5a1  mov     [rsp+0CD0h+dwOptions], edi; dwOptions
0x18004f5a5  call    cs:__imp_RegCreateKeyExA
0x18004f5ac  nop     dword ptr [rax+rax+00h]
0x18004f5b1  mov     ebx, eax
0x18004f5b3  test    eax, eax
0x18004f5b5  jnz     loc_18004F838
0x18004f5bb  mov     rcx, [rsp+0CD0h+hKey]; hKey
0x18004f5c0  lea     rax, [rsp+0CD0h+cbData]
0x18004f5c5  mov     qword ptr [rsp+0CD0h+samDesired], rax; lpcbData
0x18004f5ca  lea     r9, [rsp+0CD0h+Type]; lpType
0x18004f5cf  lea     rax, [rsp+0CD0h+Data]
0x18004f5d4  xor     r8d, r8d; lpReserved
0x18004f5d7  lea     rdx, aServerinterfac; "ServerInterfaceId"
0x18004f5de  mov     qword ptr [rsp+0CD0h+dwOptions], rax; lpData
0x18004f5e3  call    cs:__imp_RegQueryValueExA
0x18004f5ea  nop     dword ptr [rax+rax+00h]
0x18004f5ef  test    eax, eax
0x18004f5f1  jnz     short loc_18004F601
0x18004f5f3  cmp     [rsp+0CD0h+Type], 3
0x18004f5f8  jnz     short loc_18004F601
0x18004f5fa  cmp     [rsp+0CD0h+cbData], 8
0x18004f5ff  jz      short loc_18004F655
0x18004f601  lea     rcx, [rsp+0CD0h+Data]; pbBuffer
0x18004f606  call    RasSrvrIpv6GenerateInterfaceId
0x18004f60b  mov     rcx, [rsp+0CD0h+hKey]; hKey
0x18004f610  mov     ebx, eax
0x18004f612  test    eax, eax
0x18004f614  jz      short loc_18004F627
0x18004f616  call    cs:__imp_RegCloseKey
0x18004f61d  nop     dword ptr [rax+rax+00h]
0x18004f622  jmp     loc_18004F838
0x18004f627  lea     rax, [rsp+0CD0h+Data]
0x18004f62c  mov     [rsp+0CD0h+samDesired], 8; cbData
0x18004f634  mov     r9d, 3; dwType
0x18004f63a  mov     qword ptr [rsp+0CD0h+dwOptions], rax; lpData
0x18004f63f  xor     r8d, r8d; Reserved
0x18004f642  lea     rdx, aServerinterfac; "ServerInterfaceId"
0x18004f649  call    cs:__imp_RegSetValueExA
0x18004f650  nop     dword ptr [rax+rax+00h]
0x18004f655  mov     rax, qword ptr [rsp+0CD0h+Data]
0x18004f65a  lea     r9, [rsp+0CD0h+var_C60]
0x18004f65f  mov     edx, 9
0x18004f664  mov     [rsp+0CD0h+var_C60], rax
0x18004f669  lea     rcx, GUID_NULL
0x18004f670  lea     r8d, [rdx-1]
0x18004f674  call    RasRoutingDomainSetConfigParam
0x18004f679  lea     rcx, GUID_NULL
0x18004f680  mov     [rbp+0BD0h+var_C4C], 1
0x18004f687  mov     [rbp+0BD0h+var_820], 1
0x18004f691  call    RasRdGetServerAdapterLuidIndex
0x18004f696  and     eax, 0FFFFFFh
0x18004f69b  lea     r8, aRasDialInInter; "RAS (Dial In) Interface"
0x18004f6a2  or      rax, 17000000h
0x18004f6a8  lea     rcx, [rbp+0BD0h+var_A28]
0x18004f6af  shl     rax, 18h
0x18004f6b3  mov     edx, 100h
0x18004f6b8  mov     [rbp+0BD0h+var_A40], rax
0x18004f6bf  mov     rax, qword ptr [rsp+0CD0h+Data]
0x18004f6c4  mov     [rbp+0BD0h+var_828], rax
0x18004f6cb  lea     rax, [rbp+0BD0h+var_A28]
0x18004f6d2  sub     r8, rax
0x18004f6d5  lea     rax, [rdx+7FFFFEFEh]
0x18004f6dc  test    rax, rax
0x18004f6df  jz      short loc_18004F6F8
0x18004f6e1  movzx   eax, word ptr [r8+rcx]
0x18004f6e6  test    ax, ax
0x18004f6e9  jz      short loc_18004F6F8
0x18004f6eb  mov     [rcx], ax
0x18004f6ee  add     rcx, 2
0x18004f6f2  sub     rdx, 1
0x18004f6f6  jnz     short loc_18004F6D5
0x18004f6f8  test    rdx, rdx
0x18004f6fb  mov     [rsp+0CD0h+phkResult], rdi; lpOverlapped
0x18004f700  lea     rax, [rcx-2]
0x18004f704  mov     r9d, 438h; nInBufferSize
0x18004f70a  cmovnz  rax, rcx
0x18004f70e  lea     r8, [rbp+0BD0h+OutBuffer]; lpInBuffer
0x18004f712  mov     rcx, cs:?HelperWanArpv6Handle@@3PEAXEA; hDevice
0x18004f719  mov     edx, 90018004h; dwIoControlCode
0x18004f71e  mov     [rax], di
0x18004f721  lea     rax, [rsp+0CD0h+BytesReturned]
0x18004f726  mov     [rsp+0CD0h+lpSecurityAttributes], rax; lpBytesReturned
0x18004f72b  lea     rax, [rbp+0BD0h+OutBuffer]
0x18004f72f  mov     [rsp+0CD0h+samDesired], 438h; nOutBufferSize
0x18004f737  mov     qword ptr [rsp+0CD0h+dwOptions], rax; lpOutBuffer
0x18004f73c  call    cs:__imp_DeviceIoControl
0x18004f743  nop     dword ptr [rax+rax+00h]
0x18004f748  test    eax, eax
0x18004f74a  jnz     short loc_18004F7AA
0x18004f74c  call    cs:__imp_GetLastError
0x18004f753  nop     dword ptr [rax+rax+00h]
0x18004f758  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x18004f75f  mov     ebx, eax
0x18004f761  jz      loc_18004F838
0x18004f767  mov     r8d, eax
0x18004f76a  mov     word ptr [rbp+0BD0h+var_810], di
0x18004f771  lea     rdx, aRassrvrinitipv; "rasSrvrInitIpv6AdapterName: Error %d ge"...
0x18004f778  lea     rcx, [rbp+0BD0h+var_810]
0x18004f77f  call    FormatRRASErrorString
0x18004f784  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004f78b  lea     r8, [rbp+0BD0h+var_810]
0x18004f792  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f799  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7a5  jmp     loc_18004F838
0x18004f7aa  mov     eax, [rbp+0BD0h+var_C48]
0x18004f7ad  lea     r9, [rsp+0CD0h+var_C60]
0x18004f7b2  mov     edx, 8
0x18004f7b7  mov     dword ptr [rsp+0CD0h+var_C60], eax
0x18004f7bb  lea     rcx, GUID_NULL
0x18004f7c2  lea     r8d, [rdx-4]
0x18004f7c6  call    RasRoutingDomainSetConfigParam
0x18004f7cb  lea     r9, [rbp+0BD0h+var_C44]
0x18004f7cf  mov     edx, 6
0x18004f7d4  mov     r8d, 204h
0x18004f7da  lea     rcx, GUID_NULL
0x18004f7e1  call    RasRoutingDomainSetConfigParam
0x18004f7e6  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x18004f7ed  jz      short loc_18004F82E
0x18004f7ef  mov     r8d, [rbp+0BD0h+var_C48]
0x18004f7f3  lea     rdx, aIpv6AddUserInt; "IPV6 Add user Interface: g_ServerIfInde"...
0x18004f7fa  lea     rcx, [rbp+0BD0h+var_810]
0x18004f801  mov     word ptr [rbp+0BD0h+var_810], di
0x18004f808  call    FormatRRASErrorString
0x18004f80d  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004f814  lea     r8, [rbp+0BD0h+var_810]
0x18004f81b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f822  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f82e  mov     edx, [rbp+0BD0h+var_C48]; unsigned int
0x18004f831  xor     ecx, ecx; int
0x18004f833  call    ?WriteDialinInterfaceIndexIntoRegistry@@YAXHK@Z; WriteDialinInterfaceIndexIntoRegistry(int,ulong)
0x18004f838  mov     rcx, [rsp+0CD0h+hKey]; hKey
0x18004f83d  test    rcx, rcx
0x18004f840  jz      short loc_18004F84E
0x18004f842  call    cs:__imp_RegCloseKey
0x18004f849  nop     dword ptr [rax+rax+00h]
0x18004f84e  cmp     qword ptr cs:xmmword_1800D0740, rdi
0x18004f855  jz      short loc_18004F895
0x18004f857  mov     r8d, ebx
0x18004f85a  mov     word ptr [rbp+0BD0h+var_810], di
0x18004f861  lea     rdx, aRassrvrinitipv_0; "RasSrvrInitIpv6AdapterName completed %d"
0x18004f868  lea     rcx, [rbp+0BD0h+var_810]
0x18004f86f  call    FormatRRASErrorString
0x18004f874  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004f87b  lea     r8, [rbp+0BD0h+var_810]
0x18004f882  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f889  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f895  mov     eax, ebx
0x18004f897  mov     rcx, [rbp+0BD0h+var_10]
0x18004f89e  xor     rcx, rsp; StackCookie
0x18004f8a1  call    __security_check_cookie
0x18004f8a6  lea     r11, [rsp+0CD0h+var_s0]
0x18004f8ae  mov     rbx, [r11+10h]
0x18004f8b2  mov     rdi, [r11+18h]
0x18004f8b6  mov     rsp, r11
0x18004f8b9  pop     rbp
0x18004f8ba  retn
```
