# IpTlsAddInterface

- ea: `0x18005fa9c`
- end: `0x18005fe86`
- name: `IpTlsAddInterface`
- size: `1002`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003ce4`

## callees

- `0x18000d7b0`
- `0x180013570`
- `0x18001e6c0`
- `0x18001f3f4`
- `0x18001f6c8`
- `0x180040dd0`
- `0x180045054`
- `0x18004905c`
- `0x18005fa9c`
- `0x18005ffb0`
- `0x180060494`
- `0x180060698`
- `0x18006789c`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x18005fccc`
- `IPHLPAPI!FreeMibTable` at `0x18005fccc`
- `IPHLPAPI!GetIfTable2` at `0x18005fbe0`
- `IPHLPAPI!GetIfTable2` at `0x18005fbe0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18005fc8e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18005fc8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fdfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fe5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fdfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fe5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd2a`

## string_xrefs

- `0x18005fab0`: `IpTlsAddInterface ConfigOrigin: %d`
- `0x18005fce5`: `%s: Failed to find the installed interface GUID in the interface table`

## pseudocode

```c
__int64 __fastcall IpTlsAddInterface(__int64 a1)
{
  __int64 v1; // r8
  unsigned int v3; // edi
  __int64 v4; // r9
  __int64 *v5; // rdx
  unsigned int started; // eax
  int v7; // edx
  unsigned int IfTable2; // eax
  __int64 v9; // r9
  char v10; // al
  PMIB_IF_TABLE2 v12; // rcx
  ULONG v13; // edi
  ULONG NumEntries; // ebp
  unsigned __int64 v15; // r14
  SIZE_T v16; // rax
  __int64 v17; // rsi
  DWORD LastError; // eax
  unsigned int FirewallException; // eax
  bool v20; // zf
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rax
  PMIB_IF_TABLE2 Table; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(unsigned int *)(a1 + 1024);
  Table = 0;
  EventWrite0(0x10000000, L"IpTlsAddInterface ConfigOrigin: %d", v1);
  v3 = 50;
  if ( *(_DWORD *)(a1 + 1012) && !g_IpTlsConfigureServerInterfaces )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
    {
      v4 = 50;
      v5 = EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED;
LABEL_8:
      McTemplateU0zq_EventWriteTransfer(MS_IPHLPSVC_ETW_PROVIDER_ID_Context, v5, a1 + 56, v4);
      return v3;
    }
    return v3;
  }
  if ( !g_IpTlsDisabledInDisabledComponents )
  {
    if ( _InterlockedIncrement(&g_IpTlsInterfacesStarted) == 1 )
    {
      started = StartTunnelInterface(15, &IPHTTPS_INTERFACE_GUID);
      v3 = started;
      if ( started )
      {
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
            EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED,
            a1 + 56,
            started);
        *(_BYTE *)(a1 + 1032) &= ~1u;
        _InterlockedDecrement(&g_IpTlsInterfacesStarted);
        return v3;
      }
    }
    v7 = *(_DWORD *)(a1 + 1024);
    *(_BYTE *)(a1 + 1032) |= 1u;
    *(struct _GUID *)(a1 + 1040) = IPHTTPS_INTERFACE_GUID;
    v3 = IpTlsStoreInterfacePersistentValues((const BYTE *)a1, v7, 15);
    if ( v3 )
      goto LABEL_19;
    IfTable2 = GetIfTable2(&Table);
    v3 = IfTable2;
    if ( IfTable2 )
    {
      EventWrite0(0x10000000, L"%s:GetIfTable2 failed:Status = %d", a1 + 56, IfTable2);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      {
        v9 = 1359;
LABEL_18:
        McTemplateU0zq_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED,
          a1 + 56,
          v9);
      }
LABEL_19:
      if ( _InterlockedExchangeAdd(&g_IpTlsInterfacesStarted, 0xFFFFFFFF) == 1 )
        StopTunnelInterface((struct _GUID *)(a1 + 1040));
      v10 = *(_BYTE *)(a1 + 1032);
      if ( (v10 & 1) != 0 )
        *(_BYTE *)(a1 + 1032) = v10 & 0xFE;
      return v3;
    }
    v12 = Table;
    v13 = 0;
    NumEntries = Table->NumEntries;
    while ( v13 < NumEntries )
    {
      v15 = v13;
      v16 = RtlCompareMemory(&v12->Table[v15].InterfaceGuid, (const void *)(a1 + 1040), 0x10u);
      v12 = Table;
      if ( v16 == 16 )
      {
        v17 = a1 + 1056;
        *(_DWORD *)(a1 + 1064) = Table->Table[v15].InterfaceIndex;
        *(_QWORD *)(a1 + 1056) = v12->Table[v15].InterfaceLuid.Value;
        goto LABEL_30;
      }
      ++v13;
    }
    v17 = a1 + 1056;
LABEL_30:
    FreeMibTable(v12);
    if ( v13 == NumEntries )
    {
      EventWrite0(0x10000000, L"%s: Failed to find the installed interface GUID in the interface table", a1 + 56);
      v3 = 1603;
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) == 0 )
        goto LABEL_19;
      v9 = 1603;
      goto LABEL_18;
    }
    if ( !(unsigned int)UpdateLinkAddress(v17, a1 + 32, 24) )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      {
        LastError = GetLastError();
        McTemplateU0zq_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_LINKADDRUPDATE,
          a1 + 56,
          LastError);
      }
      v3 = 1603;
      goto LABEL_19;
    }
    *(_BYTE *)(a1 + 1032) &= ~4u;
    if ( *(_DWORD *)(a1 + 1012) )
    {
      FirewallException = IpTlsCreateFirewallException(a1);
      v3 = FirewallException;
      if ( FirewallException )
      {
        *(_DWORD *)(a1 + 1192) = 2;
LABEL_43:
        *(_DWORD *)(a1 + 1196) = FirewallException;
        goto LABEL_19;
      }
      v3 = StartServer(*(_QWORD *)(a1 + 1000), a1);
      v20 = v3 == 0;
    }
    else
    {
      IpTlsGetClientCertificate(a1);
      FirewallException = IpTlsCreateFirewallException(a1);
      v3 = FirewallException;
      if ( FirewallException )
      {
        *(_DWORD *)(a1 + 1192) = 3;
        goto LABEL_43;
      }
      v22 = IpTlsStartClient(*(_QWORD *)(a1 + 1000), v21, a1);
      v3 = 0;
      if ( v22 != 997 )
        v3 = v22;
      v20 = v3 == 0;
    }
    if ( v20 )
    {
      IpTlsAcquireLock(g_IpTlsInterfaceListLock);
      if ( *(_DWORD *)(a1 + 1012) )
      {
        ReleaseMutex(g_IpTlsInterfaceListLock);
        v3 = IpTlsInterfaceIndicateConnect(a1, 0);
        if ( v3 )
          goto LABEL_19;
        IpTlsAcquireLock(g_IpTlsInterfaceListLock);
      }
      v23 = g_IpTlsInterfaceListHead;
      if ( *(__int64 **)(g_IpTlsInterfaceListHead + 8) != &g_IpTlsInterfaceListHead )
        __fastfail(3u);
      *(_QWORD *)a1 = g_IpTlsInterfaceListHead;
      *(_QWORD *)(a1 + 8) = &g_IpTlsInterfaceListHead;
      *(_QWORD *)(v23 + 8) = a1;
      g_IpTlsInterfaceListHead = a1;
      ReleaseMutex(g_IpTlsInterfaceListLock);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x1000) != 0 )
      {
        v4 = v3;
        v5 = EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_LINKADDRUPDATE;
        goto LABEL_8;
      }
      return v3;
    }
    goto LABEL_19;
  }
  *(_DWORD *)(a1 + 1192) = 13;
  *(_DWORD *)(a1 + 1196) = 50;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800) != 0 )
  {
    v4 = 0;
    v5 = EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_ADMIN_DISABLED;
    goto LABEL_8;
  }
  return v3;
}

```

## disassembly

```asm
0x18005fa9c  push    rbx
0x18005fa9e  push    rbp
0x18005fa9f  push    rsi
0x18005faa0  push    rdi
0x18005faa1  push    r14
0x18005faa3  push    r15
0x18005faa5  sub     rsp, 28h
0x18005faa9  mov     r8d, [rcx+400h]
0x18005fab0  lea     rdx, aIptlsaddinterf; "IpTlsAddInterface ConfigOrigin: %d"
0x18005fab7  mov     rbx, rcx
0x18005faba  mov     [rsp+58h+Table], 0
0x18005fac3  mov     r14d, 10000000h
0x18005fac9  mov     ecx, r14d
0x18005facc  call    EventWrite0
0x18005fad1  cmp     dword ptr [rbx+3F4h], 0
0x18005fad8  mov     edi, 32h ; '2'
0x18005fadd  jz      short loc_18005FB01
0x18005fadf  cmp     cs:g_IpTlsConfigureServerInterfaces, 0
0x18005fae6  jnz     short loc_18005FB01
0x18005fae8  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005faef  jz      loc_18005FC58
0x18005faf5  mov     r9d, edi
0x18005faf8  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED
0x18005faff  jmp     short loc_18005FB31
0x18005fb01  cmp     cs:g_IpTlsDisabledInDisabledComponents, 0
0x18005fb08  jz      short loc_18005FB46
0x18005fb0a  mov     dword ptr [rbx+4A8h], 0Dh
0x18005fb14  mov     [rbx+4ACh], edi
0x18005fb1a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18005fb21  jz      loc_18005FC58
0x18005fb27  xor     r9d, r9d
0x18005fb2a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_ADMIN_DISABLED
0x18005fb31  lea     r8, [rbx+38h]
0x18005fb35  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fb3c  call    McTemplateU0zq_EventWriteTransfer
0x18005fb41  jmp     loc_18005FC58
0x18005fb46  mov     eax, 1
0x18005fb4b  lock xadd cs:g_IpTlsInterfacesStarted, eax
0x18005fb53  inc     eax
0x18005fb55  mov     esi, 0Fh
0x18005fb5a  cmp     eax, 1
0x18005fb5d  jnz     short loc_18005FBA9
0x18005fb5f  lea     rdx, IPHTTPS_INTERFACE_GUID
0x18005fb66  mov     ecx, esi
0x18005fb68  call    StartTunnelInterface
0x18005fb6d  mov     edi, eax
0x18005fb6f  test    eax, eax
0x18005fb71  jz      short loc_18005FBA9
0x18005fb73  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fb7a  jz      short loc_18005FB96
0x18005fb7c  lea     r8, [rbx+38h]
0x18005fb80  mov     r9d, eax
0x18005fb83  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED
0x18005fb8a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fb91  call    McTemplateU0zq_EventWriteTransfer
0x18005fb96  and     byte ptr [rbx+408h], 0FEh
0x18005fb9d  lock dec cs:g_IpTlsInterfacesStarted
0x18005fba4  jmp     loc_18005FC58
0x18005fba9  movups  xmm0, xmmword ptr cs:IPHTTPS_INTERFACE_GUID.Data1
0x18005fbb0  mov     edx, [rbx+400h]
0x18005fbb6  lea     r15, [rbx+410h]
0x18005fbbd  or      byte ptr [rbx+408h], 1
0x18005fbc4  movzx   r8d, si
0x18005fbc8  mov     rcx, rbx
0x18005fbcb  movdqu  xmmword ptr [r15], xmm0
0x18005fbd0  call    IpTlsStoreInterfacePersistentValues
0x18005fbd5  mov     edi, eax
0x18005fbd7  test    eax, eax
0x18005fbd9  jnz     short loc_18005FC2E
0x18005fbdb  lea     rcx, [rsp+58h+Table]; Table
0x18005fbe0  call    cs:__imp_GetIfTable2
0x18005fbe7  nop     dword ptr [rax+rax+00h]
0x18005fbec  mov     edi, eax
0x18005fbee  test    eax, eax
0x18005fbf0  jz      short loc_18005FC68
0x18005fbf2  mov     r9d, eax
0x18005fbf5  lea     r8, [rbx+38h]
0x18005fbf9  lea     rdx, aSGetiftable2Fa; "%s:GetIfTable2 failed:Status = %d"
0x18005fc00  mov     ecx, r14d
0x18005fc03  call    EventWrite0
0x18005fc08  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fc0f  jz      short loc_18005FC2E
0x18005fc11  mov     r9d, 54Fh
0x18005fc17  lea     r8, [rbx+38h]
0x18005fc1b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED
0x18005fc22  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fc29  call    McTemplateU0zq_EventWriteTransfer
0x18005fc2e  or      eax, 0FFFFFFFFh
0x18005fc31  lock xadd cs:g_IpTlsInterfacesStarted, eax
0x18005fc39  cmp     eax, 1
0x18005fc3c  jnz     short loc_18005FC46
0x18005fc3e  mov     rcx, r15; struct _GUID *
0x18005fc41  call    StopTunnelInterface
0x18005fc46  mov     al, [rbx+408h]
0x18005fc4c  test    al, 1
0x18005fc4e  jz      short loc_18005FC58
0x18005fc50  and     al, 0FEh
0x18005fc52  mov     [rbx+408h], al
0x18005fc58  mov     eax, edi
0x18005fc5a  add     rsp, 28h
0x18005fc5e  pop     r15
0x18005fc60  pop     r14
0x18005fc62  pop     rdi
0x18005fc63  pop     rsi
0x18005fc64  pop     rbp
0x18005fc65  pop     rbx
0x18005fc66  retn
0x18005fc68  mov     rcx, [rsp+58h+Table]; Memory
0x18005fc6d  xor     edi, edi
0x18005fc6f  mov     ebp, [rcx]
0x18005fc71  cmp     edi, ebp
0x18005fc73  jnb     short loc_18005FCC5
0x18005fc75  mov     eax, edi
0x18005fc77  add     rcx, 14h
0x18005fc7b  imul    r14, rax, 548h
0x18005fc82  mov     r8d, 10h; Length
0x18005fc88  mov     rdx, r15; Source2
0x18005fc8b  add     rcx, r14; Source1
0x18005fc8e  call    cs:__imp_RtlCompareMemory
0x18005fc95  nop     dword ptr [rax+rax+00h]
0x18005fc9a  mov     rcx, [rsp+58h+Table]
0x18005fc9f  cmp     rax, 10h
0x18005fca3  jz      short loc_18005FCA9
0x18005fca5  inc     edi
0x18005fca7  jmp     short loc_18005FC71
0x18005fca9  mov     eax, [r14+rcx+10h]
0x18005fcae  lea     rsi, [rbx+420h]
0x18005fcb5  mov     [rbx+428h], eax
0x18005fcbb  mov     rax, [r14+rcx+8]
0x18005fcc0  mov     [rsi], rax
0x18005fcc3  jmp     short loc_18005FCCC
0x18005fcc5  lea     rsi, [rbx+420h]
0x18005fccc  call    cs:__imp_FreeMibTable
0x18005fcd3  nop     dword ptr [rax+rax+00h]
0x18005fcd8  cmp     edi, ebp
0x18005fcda  jnz     short loc_18005FD0B
0x18005fcdc  lea     r8, [rbx+38h]
0x18005fce0  mov     ecx, 10000000h
0x18005fce5  lea     rdx, aSFailedToFindT; "%s: Failed to find the installed interf"...
0x18005fcec  call    EventWrite0
0x18005fcf1  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fcf8  mov     edi, 643h
0x18005fcfd  jz      loc_18005FC2E
0x18005fd03  mov     r9d, edi
0x18005fd06  jmp     loc_18005FC17
0x18005fd0b  lea     rdx, [rbx+20h]
0x18005fd0f  mov     r8d, 18h
0x18005fd15  mov     rcx, rsi
0x18005fd18  call    UpdateLinkAddress
0x18005fd1d  test    eax, eax
0x18005fd1f  jnz     short loc_18005FD5A
0x18005fd21  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fd28  jz      short loc_18005FD50
0x18005fd2a  call    cs:__imp_GetLastError
0x18005fd31  nop     dword ptr [rax+rax+00h]
0x18005fd36  mov     r9d, eax
0x18005fd39  lea     r8, [rbx+38h]
0x18005fd3d  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_LINKADDRUPDATE
0x18005fd44  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fd4b  call    McTemplateU0zq_EventWriteTransfer
0x18005fd50  mov     edi, 643h
0x18005fd55  jmp     loc_18005FC2E
0x18005fd5a  and     byte ptr [rbx+408h], 0FBh
0x18005fd61  mov     rcx, rbx
0x18005fd64  cmp     dword ptr [rbx+3F4h], 0
0x18005fd6b  jz      short loc_18005FD99
0x18005fd6d  call    IpTlsCreateFirewallException
0x18005fd72  mov     edi, eax
0x18005fd74  test    eax, eax
0x18005fd76  jz      short loc_18005FD84
0x18005fd78  mov     dword ptr [rbx+4A8h], 2
0x18005fd82  jmp     short loc_18005FDB6
0x18005fd84  mov     rcx, [rbx+3E8h]
0x18005fd8b  mov     rdx, rbx
0x18005fd8e  call    StartServer
0x18005fd93  mov     edi, eax
0x18005fd95  test    eax, eax
0x18005fd97  jmp     short loc_18005FDDC
0x18005fd99  call    IpTlsGetClientCertificate
0x18005fd9e  mov     rcx, rbx
0x18005fda1  call    IpTlsCreateFirewallException
0x18005fda6  mov     edi, eax
0x18005fda8  test    eax, eax
0x18005fdaa  jz      short loc_18005FDC1
0x18005fdac  mov     dword ptr [rbx+4A8h], 3
0x18005fdb6  mov     [rbx+4ACh], eax
0x18005fdbc  jmp     loc_18005FC2E
0x18005fdc1  mov     rcx, [rbx+3E8h]
0x18005fdc8  mov     r8, rbx
0x18005fdcb  call    IpTlsStartClient
0x18005fdd0  xor     edi, edi
0x18005fdd2  cmp     eax, 3E5h
0x18005fdd7  cmovnz  edi, eax
0x18005fdda  test    edi, edi
0x18005fddc  jnz     loc_18005FC2E
0x18005fde2  mov     rcx, cs:g_IpTlsInterfaceListLock
0x18005fde9  call    IpTlsAcquireLock
0x18005fdee  cmp     dword ptr [rbx+3F4h], 0
0x18005fdf5  jz      short loc_18005FE2A
0x18005fdf7  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18005fdfe  call    cs:__imp_ReleaseMutex
0x18005fe05  nop     dword ptr [rax+rax+00h]
0x18005fe0a  xor     edx, edx
0x18005fe0c  mov     rcx, rbx
0x18005fe0f  call    IpTlsInterfaceIndicateConnect
0x18005fe14  mov     edi, eax
0x18005fe16  test    eax, eax
0x18005fe18  jnz     loc_18005FC2E
0x18005fe1e  mov     rcx, cs:g_IpTlsInterfaceListLock
0x18005fe25  call    IpTlsAcquireLock
0x18005fe2a  mov     rax, cs:g_IpTlsInterfaceListHead
0x18005fe31  lea     rcx, g_IpTlsInterfaceListHead
0x18005fe38  cmp     [rax+8], rcx
0x18005fe3c  jz      short loc_18005FE45
0x18005fe3e  mov     ecx, 3
0x18005fe43  int     29h; Win8: RtlFailFast(ecx)
0x18005fe45  mov     [rbx], rax
0x18005fe48  mov     [rbx+8], rcx
0x18005fe4c  mov     [rax+8], rbx
0x18005fe50  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18005fe57  mov     cs:g_IpTlsInterfaceListHead, rbx
0x18005fe5e  call    cs:__imp_ReleaseMutex
0x18005fe65  nop     dword ptr [rax+rax+00h]
0x18005fe6a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fe71  jz      loc_18005FC58
0x18005fe77  mov     r9d, edi
0x18005fe7a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_LINKADDRUPDATE
0x18005fe81  jmp     loc_18005FB31
```
