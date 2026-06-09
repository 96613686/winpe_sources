# IpTlsAddInterface

- ea: `0x18005fabc`
- end: `0x18005fea6`
- name: `IpTlsAddInterface`
- size: `1002`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003cf4`

## callees

- `0x18000d7c0`
- `0x180013580`
- `0x18001e6d0`
- `0x18001f404`
- `0x18001f6d8`
- `0x180040d90`
- `0x180045014`
- `0x18004901c`
- `0x18005fabc`
- `0x18005ffd0`
- `0x1800604b4`
- `0x1800606b8`
- `0x1800678bc`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x18005fcec`
- `IPHLPAPI!FreeMibTable` at `0x18005fcec`
- `IPHLPAPI!GetIfTable2` at `0x18005fc00`
- `IPHLPAPI!GetIfTable2` at `0x18005fc00`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18005fcae`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18005fcae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fe1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fe7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fe1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18005fe7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fd4a`

## string_xrefs

- `0x18005fad0`: `IpTlsAddInterface ConfigOrigin: %d`
- `0x18005fd05`: `%s: Failed to find the installed interface GUID in the interface table`

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
0x18005fabc  push    rbx
0x18005fabe  push    rbp
0x18005fabf  push    rsi
0x18005fac0  push    rdi
0x18005fac1  push    r14
0x18005fac3  push    r15
0x18005fac5  sub     rsp, 28h
0x18005fac9  mov     r8d, [rcx+400h]
0x18005fad0  lea     rdx, aIptlsaddinterf; "IpTlsAddInterface ConfigOrigin: %d"
0x18005fad7  mov     rbx, rcx
0x18005fada  mov     [rsp+58h+Table], 0
0x18005fae3  mov     r14d, 10000000h
0x18005fae9  mov     ecx, r14d
0x18005faec  call    EventWrite0
0x18005faf1  cmp     dword ptr [rbx+3F4h], 0
0x18005faf8  mov     edi, 32h ; '2'
0x18005fafd  jz      short loc_18005FB21
0x18005faff  cmp     cs:g_IpTlsConfigureServerInterfaces, 0
0x18005fb06  jnz     short loc_18005FB21
0x18005fb08  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fb0f  jz      loc_18005FC78
0x18005fb15  mov     r9d, edi
0x18005fb18  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED
0x18005fb1f  jmp     short loc_18005FB51
0x18005fb21  cmp     cs:g_IpTlsDisabledInDisabledComponents, 0
0x18005fb28  jz      short loc_18005FB66
0x18005fb2a  mov     dword ptr [rbx+4A8h], 0Dh
0x18005fb34  mov     [rbx+4ACh], edi
0x18005fb3a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 8
0x18005fb41  jz      loc_18005FC78
0x18005fb47  xor     r9d, r9d
0x18005fb4a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_ADMIN_DISABLED
0x18005fb51  lea     r8, [rbx+38h]
0x18005fb55  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fb5c  call    McTemplateU0zq_EventWriteTransfer
0x18005fb61  jmp     loc_18005FC78
0x18005fb66  mov     eax, 1
0x18005fb6b  lock xadd cs:g_IpTlsInterfacesStarted, eax
0x18005fb73  inc     eax
0x18005fb75  mov     esi, 0Fh
0x18005fb7a  cmp     eax, 1
0x18005fb7d  jnz     short loc_18005FBC9
0x18005fb7f  lea     rdx, IPHTTPS_INTERFACE_GUID
0x18005fb86  mov     ecx, esi
0x18005fb88  call    StartTunnelInterface
0x18005fb8d  mov     edi, eax
0x18005fb8f  test    eax, eax
0x18005fb91  jz      short loc_18005FBC9
0x18005fb93  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fb9a  jz      short loc_18005FBB6
0x18005fb9c  lea     r8, [rbx+38h]
0x18005fba0  mov     r9d, eax
0x18005fba3  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED
0x18005fbaa  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fbb1  call    McTemplateU0zq_EventWriteTransfer
0x18005fbb6  and     byte ptr [rbx+408h], 0FEh
0x18005fbbd  lock dec cs:g_IpTlsInterfacesStarted
0x18005fbc4  jmp     loc_18005FC78
0x18005fbc9  movups  xmm0, xmmword ptr cs:IPHTTPS_INTERFACE_GUID.Data1
0x18005fbd0  mov     edx, [rbx+400h]
0x18005fbd6  lea     r15, [rbx+410h]
0x18005fbdd  or      byte ptr [rbx+408h], 1
0x18005fbe4  movzx   r8d, si
0x18005fbe8  mov     rcx, rbx
0x18005fbeb  movdqu  xmmword ptr [r15], xmm0
0x18005fbf0  call    IpTlsStoreInterfacePersistentValues
0x18005fbf5  mov     edi, eax
0x18005fbf7  test    eax, eax
0x18005fbf9  jnz     short loc_18005FC4E
0x18005fbfb  lea     rcx, [rsp+58h+Table]; Table
0x18005fc00  call    cs:__imp_GetIfTable2
0x18005fc07  nop     dword ptr [rax+rax+00h]
0x18005fc0c  mov     edi, eax
0x18005fc0e  test    eax, eax
0x18005fc10  jz      short loc_18005FC88
0x18005fc12  mov     r9d, eax
0x18005fc15  lea     r8, [rbx+38h]
0x18005fc19  lea     rdx, aSGetiftable2Fa; "%s:GetIfTable2 failed:Status = %d"
0x18005fc20  mov     ecx, r14d
0x18005fc23  call    EventWrite0
0x18005fc28  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fc2f  jz      short loc_18005FC4E
0x18005fc31  mov     r9d, 54Fh
0x18005fc37  lea     r8, [rbx+38h]
0x18005fc3b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_INSTALLATION_FAILED
0x18005fc42  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fc49  call    McTemplateU0zq_EventWriteTransfer
0x18005fc4e  or      eax, 0FFFFFFFFh
0x18005fc51  lock xadd cs:g_IpTlsInterfacesStarted, eax
0x18005fc59  cmp     eax, 1
0x18005fc5c  jnz     short loc_18005FC66
0x18005fc5e  mov     rcx, r15; struct _GUID *
0x18005fc61  call    StopTunnelInterface
0x18005fc66  mov     al, [rbx+408h]
0x18005fc6c  test    al, 1
0x18005fc6e  jz      short loc_18005FC78
0x18005fc70  and     al, 0FEh
0x18005fc72  mov     [rbx+408h], al
0x18005fc78  mov     eax, edi
0x18005fc7a  add     rsp, 28h
0x18005fc7e  pop     r15
0x18005fc80  pop     r14
0x18005fc82  pop     rdi
0x18005fc83  pop     rsi
0x18005fc84  pop     rbp
0x18005fc85  pop     rbx
0x18005fc86  retn
0x18005fc88  mov     rcx, [rsp+58h+Table]; Memory
0x18005fc8d  xor     edi, edi
0x18005fc8f  mov     ebp, [rcx]
0x18005fc91  cmp     edi, ebp
0x18005fc93  jnb     short loc_18005FCE5
0x18005fc95  mov     eax, edi
0x18005fc97  add     rcx, 14h
0x18005fc9b  imul    r14, rax, 548h
0x18005fca2  mov     r8d, 10h; Length
0x18005fca8  mov     rdx, r15; Source2
0x18005fcab  add     rcx, r14; Source1
0x18005fcae  call    cs:__imp_RtlCompareMemory
0x18005fcb5  nop     dword ptr [rax+rax+00h]
0x18005fcba  mov     rcx, [rsp+58h+Table]
0x18005fcbf  cmp     rax, 10h
0x18005fcc3  jz      short loc_18005FCC9
0x18005fcc5  inc     edi
0x18005fcc7  jmp     short loc_18005FC91
0x18005fcc9  mov     eax, [r14+rcx+10h]
0x18005fcce  lea     rsi, [rbx+420h]
0x18005fcd5  mov     [rbx+428h], eax
0x18005fcdb  mov     rax, [r14+rcx+8]
0x18005fce0  mov     [rsi], rax
0x18005fce3  jmp     short loc_18005FCEC
0x18005fce5  lea     rsi, [rbx+420h]
0x18005fcec  call    cs:__imp_FreeMibTable
0x18005fcf3  nop     dword ptr [rax+rax+00h]
0x18005fcf8  cmp     edi, ebp
0x18005fcfa  jnz     short loc_18005FD2B
0x18005fcfc  lea     r8, [rbx+38h]
0x18005fd00  mov     ecx, 10000000h
0x18005fd05  lea     rdx, aSFailedToFindT; "%s: Failed to find the installed interf"...
0x18005fd0c  call    EventWrite0
0x18005fd11  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fd18  mov     edi, 643h
0x18005fd1d  jz      loc_18005FC4E
0x18005fd23  mov     r9d, edi
0x18005fd26  jmp     loc_18005FC37
0x18005fd2b  lea     rdx, [rbx+20h]
0x18005fd2f  mov     r8d, 18h
0x18005fd35  mov     rcx, rsi
0x18005fd38  call    UpdateLinkAddress
0x18005fd3d  test    eax, eax
0x18005fd3f  jnz     short loc_18005FD7A
0x18005fd41  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fd48  jz      short loc_18005FD70
0x18005fd4a  call    cs:__imp_GetLastError
0x18005fd51  nop     dword ptr [rax+rax+00h]
0x18005fd56  mov     r9d, eax
0x18005fd59  lea     r8, [rbx+38h]
0x18005fd5d  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_LINKADDRUPDATE
0x18005fd64  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005fd6b  call    McTemplateU0zq_EventWriteTransfer
0x18005fd70  mov     edi, 643h
0x18005fd75  jmp     loc_18005FC4E
0x18005fd7a  and     byte ptr [rbx+408h], 0FBh
0x18005fd81  mov     rcx, rbx
0x18005fd84  cmp     dword ptr [rbx+3F4h], 0
0x18005fd8b  jz      short loc_18005FDB9
0x18005fd8d  call    IpTlsCreateFirewallException
0x18005fd92  mov     edi, eax
0x18005fd94  test    eax, eax
0x18005fd96  jz      short loc_18005FDA4
0x18005fd98  mov     dword ptr [rbx+4A8h], 2
0x18005fda2  jmp     short loc_18005FDD6
0x18005fda4  mov     rcx, [rbx+3E8h]
0x18005fdab  mov     rdx, rbx
0x18005fdae  call    StartServer
0x18005fdb3  mov     edi, eax
0x18005fdb5  test    eax, eax
0x18005fdb7  jmp     short loc_18005FDFC
0x18005fdb9  call    IpTlsGetClientCertificate
0x18005fdbe  mov     rcx, rbx
0x18005fdc1  call    IpTlsCreateFirewallException
0x18005fdc6  mov     edi, eax
0x18005fdc8  test    eax, eax
0x18005fdca  jz      short loc_18005FDE1
0x18005fdcc  mov     dword ptr [rbx+4A8h], 3
0x18005fdd6  mov     [rbx+4ACh], eax
0x18005fddc  jmp     loc_18005FC4E
0x18005fde1  mov     rcx, [rbx+3E8h]
0x18005fde8  mov     r8, rbx
0x18005fdeb  call    IpTlsStartClient
0x18005fdf0  xor     edi, edi
0x18005fdf2  cmp     eax, 3E5h
0x18005fdf7  cmovnz  edi, eax
0x18005fdfa  test    edi, edi
0x18005fdfc  jnz     loc_18005FC4E
0x18005fe02  mov     rcx, cs:g_IpTlsInterfaceListLock
0x18005fe09  call    IpTlsAcquireLock
0x18005fe0e  cmp     dword ptr [rbx+3F4h], 0
0x18005fe15  jz      short loc_18005FE4A
0x18005fe17  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18005fe1e  call    cs:__imp_ReleaseMutex
0x18005fe25  nop     dword ptr [rax+rax+00h]
0x18005fe2a  xor     edx, edx
0x18005fe2c  mov     rcx, rbx
0x18005fe2f  call    IpTlsInterfaceIndicateConnect
0x18005fe34  mov     edi, eax
0x18005fe36  test    eax, eax
0x18005fe38  jnz     loc_18005FC4E
0x18005fe3e  mov     rcx, cs:g_IpTlsInterfaceListLock
0x18005fe45  call    IpTlsAcquireLock
0x18005fe4a  mov     rax, cs:g_IpTlsInterfaceListHead
0x18005fe51  lea     rcx, g_IpTlsInterfaceListHead
0x18005fe58  cmp     [rax+8], rcx
0x18005fe5c  jz      short loc_18005FE65
0x18005fe5e  mov     ecx, 3
0x18005fe63  int     29h; Win8: RtlFailFast(ecx)
0x18005fe65  mov     [rbx], rax
0x18005fe68  mov     [rbx+8], rcx
0x18005fe6c  mov     [rax+8], rbx
0x18005fe70  mov     rcx, cs:g_IpTlsInterfaceListLock; hMutex
0x18005fe77  mov     cs:g_IpTlsInterfaceListHead, rbx
0x18005fe7e  call    cs:__imp_ReleaseMutex
0x18005fe85  nop     dword ptr [rax+rax+00h]
0x18005fe8a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 10h
0x18005fe91  jz      loc_18005FC78
0x18005fe97  mov     r9d, edi
0x18005fe9a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_LINKADDRUPDATE
0x18005fea1  jmp     loc_18005FB51
```
