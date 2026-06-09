# RasSrvrInitIpv6AdapterName(void)

- ea: `0x18004ddd0`
- end: `0x18004e194`
- name: `?RasSrvrInitIpv6AdapterName@@YAKXZ`
- size: `964`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800511bc`

## callees

- `0x18004ddd0`
- `0x18004e9b8`
- `0x180055a8c`
- `0x180058b94`
- `0x180059030`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18004e027`
- `KERNEL32!DeviceIoControl` at `0x18004e027`
- `KERNEL32!GetLastError` at `0x18004e031`
- `KERNEL32!GetLastError` at `0x18004e031`
- `ADVAPI32!RegCloseKey` at `0x18004df0e`
- `ADVAPI32!RegCloseKey` at `0x18004e121`
- `ADVAPI32!RegCloseKey` at `0x18004df0e`
- `ADVAPI32!RegCloseKey` at `0x18004e121`
- `ADVAPI32!RegSetValueExA` at `0x18004df3b`
- `ADVAPI32!RegSetValueExA` at `0x18004df3b`
- `ADVAPI32!RegCreateKeyExA` at `0x18004dea9`
- `ADVAPI32!RegCreateKeyExA` at `0x18004dea9`
- `ADVAPI32!RegQueryValueExA` at `0x18004dee1`
- `ADVAPI32!RegQueryValueExA` at `0x18004dee1`

## string_xrefs

- `0x18004de91`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x18004e13a`: `RasSrvrInitIpv6AdapterName completed %d`

## pseudocode

```c
__int64 RasSrvrInitIpv6AdapterName(void)
{
  unsigned int InterfaceId; // ebx
  __int64 ServerAdapterLuidIndex; // rax
  const wchar_t *v2; // r8
  __int64 v3; // rcx
  __int64 v4; // rdx
  char *v5; // rax
  char *v6; // rcx
  DWORD LastError; // eax
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v15[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD OutBuffer[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v17; // [rsp+88h] [rbp-78h]
  _BYTE v18[516]; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v19; // [rsp+290h] [rbp+190h]
  char v20; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v21; // [rsp+4A8h] [rbp+3A8h]
  int v22; // [rsp+4B0h] [rbp+3B0h]
  int v23; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v24[2044]; // [rsp+4C4h] [rbp+3C4h] BYREF

  memset_0(OutBuffer, 0, 0x438u);
  cbData = 8;
  BytesReturned = 0;
  hKey = 0;
  Type = 0;
  dwDisposition = 0;
  *(_QWORD *)Data = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
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
    OutBuffer[0] = 0;
    OutBuffer[1] = 1;
    v22 = 1;
    ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(&GUID_NULL);
    v2 = L"RAS (Dial In) Interface";
    v3 = 2147483646;
    v4 = 256;
    v19 = (ServerAdapterLuidIndex & 0xFFFFFF | 0x17000000) << 24;
    v21 = *(_QWORD *)Data;
    v5 = &v20;
    do
    {
      if ( !v3 )
        break;
      if ( !*v2 )
        break;
      *(_WORD *)v5 = *v2++;
      v5 += 2;
      --v3;
      --v4;
    }
    while ( v4 );
    v6 = v5 - 2;
    if ( v4 )
      v6 = v5;
    *(_WORD *)v6 = 0;
    if ( DeviceIoControl(HelperWanArpv6Handle, 0x90018004, OutBuffer, 0x438u, OutBuffer, 0x438u, &BytesReturned, 0) )
    {
      LODWORD(v15[0]) = v17;
      RasRoutingDomainSetConfigParam(&GUID_NULL, 8, 4, v15);
      RasRoutingDomainSetConfigParam(&GUID_NULL, 6, 516, v18);
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v23, L"IPV6 Add user Interface: g_ServerIfIndex %d", v17);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v23);
      }
      WriteDialinInterfaceIndexIntoRegistry(0, v17);
    }
    else
    {
      LastError = GetLastError();
      InterfaceId = LastError;
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v23, L"rasSrvrInitIpv6AdapterName: Error %d getting server name", LastError);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v23);
      }
    }
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"RasSrvrInitIpv6AdapterName completed %d", InterfaceId);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v23);
  }
  return InterfaceId;
}

```

## disassembly

```asm
0x18004ddd0  mov     [rsp-8+arg_0], rbx
0x18004ddd5  mov     [rsp-8+arg_8], rdi
0x18004ddda  push    rbp
0x18004dddb  lea     rbp, [rsp-0BD0h]
0x18004dde3  sub     rsp, 0CD0h
0x18004ddea  mov     rax, cs:__security_cookie
0x18004ddf1  xor     rax, rsp
0x18004ddf4  mov     [rbp+0BD0h+var_10], rax
0x18004ddfb  xor     edx, edx; Val
0x18004ddfd  lea     rcx, [rbp+0BD0h+OutBuffer]; void *
0x18004de01  mov     r8d, 438h; Size
0x18004de07  call    memset_0
0x18004de0c  xor     edi, edi
0x18004de0e  mov     [rsp+0CD0h+cbData], 8
0x18004de16  xor     edx, edx; Val
0x18004de18  mov     [rsp+0CD0h+BytesReturned], edi
0x18004de1c  mov     r8d, 7FCh; Size
0x18004de22  mov     [rsp+0CD0h+hKey], rdi
0x18004de27  lea     rcx, [rbp+0BD0h+var_80C]; void *
0x18004de2e  mov     [rsp+0CD0h+Type], edi
0x18004de32  mov     [rsp+0CD0h+dwDisposition], edi
0x18004de36  mov     qword ptr [rsp+0CD0h+Data], rdi
0x18004de3b  mov     [rbp+0BD0h+var_810], edi
0x18004de41  call    memset_0
0x18004de46  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004de4d  test    rdx, rdx
0x18004de50  jz      short loc_18004DE6C
0x18004de52  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004de59  lea     r8, aRassrvrinitipv_1; "RasSrvrInitIpv6AdapterName entering"
0x18004de60  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004de67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de6c  lea     rax, [rsp+0CD0h+dwDisposition]
0x18004de71  xor     r8d, r8d; Reserved
0x18004de74  mov     [rsp+0CD0h+lpdwDisposition], rax; lpdwDisposition
0x18004de79  lea     r9, Class; lpClass
0x18004de80  lea     rax, [rsp+0CD0h+hKey]
0x18004de85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004de8c  mov     [rsp+0CD0h+phkResult], rax; phkResult
0x18004de91  lea     rdx, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x18004de98  mov     [rsp+0CD0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004de9d  mov     [rsp+0CD0h+samDesired], 3; samDesired
0x18004dea5  mov     [rsp+0CD0h+dwOptions], edi; dwOptions
0x18004dea9  call    cs:__imp_RegCreateKeyExA
0x18004deaf  mov     ebx, eax
0x18004deb1  test    eax, eax
0x18004deb3  jnz     loc_18004E117
0x18004deb9  mov     rcx, [rsp+0CD0h+hKey]; hKey
0x18004debe  lea     rax, [rsp+0CD0h+cbData]
0x18004dec3  mov     qword ptr [rsp+0CD0h+samDesired], rax; lpcbData
0x18004dec8  lea     r9, [rsp+0CD0h+Type]; lpType
0x18004decd  lea     rax, [rsp+0CD0h+Data]
0x18004ded2  xor     r8d, r8d; lpReserved
0x18004ded5  lea     rdx, aServerinterfac; "ServerInterfaceId"
0x18004dedc  mov     qword ptr [rsp+0CD0h+dwOptions], rax; lpData
0x18004dee1  call    cs:__imp_RegQueryValueExA
0x18004dee7  test    eax, eax
0x18004dee9  jnz     short loc_18004DEF9
0x18004deeb  cmp     [rsp+0CD0h+Type], 3
0x18004def0  jnz     short loc_18004DEF9
0x18004def2  cmp     [rsp+0CD0h+cbData], 8
0x18004def7  jz      short loc_18004DF41
0x18004def9  lea     rcx, [rsp+0CD0h+Data]; pbBuffer
0x18004defe  call    RasSrvrIpv6GenerateInterfaceId
0x18004df03  mov     rcx, [rsp+0CD0h+hKey]; hKey
0x18004df08  mov     ebx, eax
0x18004df0a  test    eax, eax
0x18004df0c  jz      short loc_18004DF19
0x18004df0e  call    cs:__imp_RegCloseKey
0x18004df14  jmp     loc_18004E117
0x18004df19  lea     rax, [rsp+0CD0h+Data]
0x18004df1e  mov     [rsp+0CD0h+samDesired], 8; cbData
0x18004df26  mov     r9d, 3; dwType
0x18004df2c  mov     qword ptr [rsp+0CD0h+dwOptions], rax; lpData
0x18004df31  xor     r8d, r8d; Reserved
0x18004df34  lea     rdx, aServerinterfac; "ServerInterfaceId"
0x18004df3b  call    cs:__imp_RegSetValueExA
0x18004df41  mov     rax, qword ptr [rsp+0CD0h+Data]
0x18004df46  lea     r9, [rsp+0CD0h+var_C60]
0x18004df4b  mov     edx, 9
0x18004df50  mov     [rsp+0CD0h+var_C60], rax
0x18004df55  lea     rcx, GUID_NULL
0x18004df5c  lea     r8d, [rdx-1]
0x18004df60  call    RasRoutingDomainSetConfigParam
0x18004df65  lea     rcx, GUID_NULL
0x18004df6c  mov     [rbp+0BD0h+OutBuffer], edi
0x18004df6f  mov     [rbp+0BD0h+var_C4C], 1
0x18004df76  mov     [rbp+0BD0h+var_820], 1
0x18004df80  call    RasRdGetServerAdapterLuidIndex
0x18004df85  and     eax, 0FFFFFFh
0x18004df8a  lea     r8, aRasDialInInter; "RAS (Dial In) Interface"
0x18004df91  or      rax, 17000000h
0x18004df97  mov     ecx, 7FFFFFFEh
0x18004df9c  shl     rax, 18h
0x18004dfa0  mov     edx, 100h
0x18004dfa5  mov     [rbp+0BD0h+var_A40], rax
0x18004dfac  mov     rax, qword ptr [rsp+0CD0h+Data]
0x18004dfb1  mov     [rbp+0BD0h+var_828], rax
0x18004dfb8  lea     rax, [rbp+0BD0h+var_A28]
0x18004dfbf  test    rcx, rcx
0x18004dfc2  jz      short loc_18004DFE3
0x18004dfc4  movzx   r9d, word ptr [r8]
0x18004dfc8  test    r9w, r9w
0x18004dfcc  jz      short loc_18004DFE3
0x18004dfce  mov     [rax], r9w
0x18004dfd2  add     r8, 2
0x18004dfd6  add     rax, 2
0x18004dfda  dec     rcx
0x18004dfdd  sub     rdx, 1
0x18004dfe1  jnz     short loc_18004DFBF
0x18004dfe3  lea     rcx, [rax-2]
0x18004dfe7  mov     [rsp+0CD0h+phkResult], rdi; lpOverlapped
0x18004dfec  test    rdx, rdx
0x18004dfef  lea     r8, [rbp+0BD0h+OutBuffer]; lpInBuffer
0x18004dff3  mov     r9d, 438h; nInBufferSize
0x18004dff9  mov     edx, 90018004h; dwIoControlCode
0x18004dffe  cmovnz  rcx, rax
0x18004e002  lea     rax, [rsp+0CD0h+BytesReturned]
0x18004e007  mov     [rsp+0CD0h+lpSecurityAttributes], rax; lpBytesReturned
0x18004e00c  lea     rax, [rbp+0BD0h+OutBuffer]
0x18004e010  mov     [rsp+0CD0h+samDesired], 438h; nOutBufferSize
0x18004e018  mov     qword ptr [rsp+0CD0h+dwOptions], rax; lpOutBuffer
0x18004e01d  mov     [rcx], di
0x18004e020  mov     rcx, cs:?HelperWanArpv6Handle@@3PEAXEA; hDevice
0x18004e027  call    cs:__imp_DeviceIoControl
0x18004e02d  test    eax, eax
0x18004e02f  jnz     short loc_18004E089
0x18004e031  call    cs:__imp_GetLastError
0x18004e037  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x18004e03e  mov     ebx, eax
0x18004e040  jz      loc_18004E117
0x18004e046  mov     r8d, eax
0x18004e049  mov     word ptr [rbp+0BD0h+var_810], di
0x18004e050  lea     rdx, aRassrvrinitipv; "rasSrvrInitIpv6AdapterName: Error %d ge"...
0x18004e057  lea     rcx, [rbp+0BD0h+var_810]
0x18004e05e  call    FormatRRASErrorString
0x18004e063  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e06a  lea     r8, [rbp+0BD0h+var_810]
0x18004e071  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e078  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e084  jmp     loc_18004E117
0x18004e089  mov     eax, [rbp+0BD0h+var_C48]
0x18004e08c  lea     r9, [rsp+0CD0h+var_C60]
0x18004e091  mov     edx, 8
0x18004e096  mov     dword ptr [rsp+0CD0h+var_C60], eax
0x18004e09a  lea     rcx, GUID_NULL
0x18004e0a1  lea     r8d, [rdx-4]
0x18004e0a5  call    RasRoutingDomainSetConfigParam
0x18004e0aa  lea     r9, [rbp+0BD0h+var_C44]
0x18004e0ae  mov     edx, 6
0x18004e0b3  mov     r8d, 204h
0x18004e0b9  lea     rcx, GUID_NULL
0x18004e0c0  call    RasRoutingDomainSetConfigParam
0x18004e0c5  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x18004e0cc  jz      short loc_18004E10D
0x18004e0ce  mov     r8d, [rbp+0BD0h+var_C48]
0x18004e0d2  lea     rdx, aIpv6AddUserInt; "IPV6 Add user Interface: g_ServerIfInde"...
0x18004e0d9  lea     rcx, [rbp+0BD0h+var_810]
0x18004e0e0  mov     word ptr [rbp+0BD0h+var_810], di
0x18004e0e7  call    FormatRRASErrorString
0x18004e0ec  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e0f3  lea     r8, [rbp+0BD0h+var_810]
0x18004e0fa  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e101  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e10d  mov     edx, [rbp+0BD0h+var_C48]; unsigned int
0x18004e110  xor     ecx, ecx; int
0x18004e112  call    ?WriteDialinInterfaceIndexIntoRegistry@@YAXHK@Z; WriteDialinInterfaceIndexIntoRegistry(int,ulong)
0x18004e117  mov     rcx, [rsp+0CD0h+hKey]; hKey
0x18004e11c  test    rcx, rcx
0x18004e11f  jz      short loc_18004E127
0x18004e121  call    cs:__imp_RegCloseKey
0x18004e127  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x18004e12e  jz      short loc_18004E16E
0x18004e130  mov     r8d, ebx
0x18004e133  mov     word ptr [rbp+0BD0h+var_810], di
0x18004e13a  lea     rdx, aRassrvrinitipv_0; "RasSrvrInitIpv6AdapterName completed %d"
0x18004e141  lea     rcx, [rbp+0BD0h+var_810]
0x18004e148  call    FormatRRASErrorString
0x18004e14d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e154  lea     r8, [rbp+0BD0h+var_810]
0x18004e15b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e162  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e16e  mov     eax, ebx
0x18004e170  mov     rcx, [rbp+0BD0h+var_10]
0x18004e177  xor     rcx, rsp; StackCookie
0x18004e17a  call    __security_check_cookie
0x18004e17f  lea     r11, [rsp+0CD0h+var_s0]
0x18004e187  mov     rbx, [r11+10h]
0x18004e18b  mov     rdi, [r11+18h]
0x18004e18f  mov     rsp, r11
0x18004e192  pop     rbp
0x18004e193  retn
```
