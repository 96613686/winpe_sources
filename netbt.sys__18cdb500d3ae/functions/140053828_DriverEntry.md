# DriverEntry

- ea: `0x140053828`
- end: `0x140053d06`
- name: `DriverEntry`
- size: `1246`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140053190`

## callees

- `0x140014298`
- `0x1400279e0`
- `0x14002bfc0`
- `0x14002cbc4`
- `0x140030a44`
- `0x140031440`
- `0x1400400a4`
- `0x140040294`
- `0x140044068`
- `0x140044100`
- `0x140044b18`
- `0x140044bc4`
- `0x140044c80`
- `0x140045254`
- `0x1400493c4`
- `0x14004fcf4`
- `0x14005059c`
- `0x140053008`
- `0x1400531f8`
- `0x1400533a4`
- `0x140053828`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140053aac`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053acc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053bd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053c19`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053aac`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053acc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053bd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053c19`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140053910`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140053910`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400538a2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400538a2`
- `ntoskrnl!ExAllocatePool2` at `0x1400538ea`
- `ntoskrnl!ExAllocatePool2` at `0x1400538ea`
- `TDI!TdiDeregisterProvider` at `0x140053ca6`
- `TDI!TdiDeregisterProvider` at `0x140053ca6`
- `TDI!TdiRegisterPnPHandlers` at `0x140053c89`
- `TDI!TdiRegisterPnPHandlers` at `0x140053c89`
- `TDI!TdiRegisterProvider` at `0x140053bf8`
- `TDI!TdiRegisterProvider` at `0x140053bf8`
- `TDI!TdiInitialize` at `0x140053891`
- `TDI!TdiInitialize` at `0x140053891`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x140053bc1`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x140053bc1`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // eax
  int v5; // edi
  __int64 v6; // rcx
  int inited; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  UNICODE_STRING v12; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING ProviderName; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING v15; // [rsp+60h] [rbp-9h] BYREF
  TDI_CLIENT_INTERFACE_INFO ClientInterfaceInfo; // [rsp+70h] [rbp+7h] BYREF
  __int64 v17; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v18; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v19; // [rsp+E0h] [rbp+77h] BYREF

  v19 = 0;
  v18 = 0;
  v17 = 0;
  DestinationString = 0;
  v12 = 0;
  v15 = 0;
  ProviderName = 0;
  memset(&ClientInterfaceInfo, 0, sizeof(ClientInterfaceInfo));
  FastWppInit();
  if ( (unsigned int)Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline() )
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  TdiInitialize();
  wil_InitializeFeatureStaging();
  NbtFspProcess = (PRKPROCESS)PsGetCurrentProcess();
  memset(&NbtConfig, 0, 0x328u);
  ::DriverObject = DriverObject;
  stru_1400394D0.MaximumLength = RegistryPath->MaximumLength;
  stru_1400394D0.Buffer = (wchar_t *)ExAllocatePool2(64, RegistryPath->MaximumLength, 925983310);
  if ( stru_1400394D0.Buffer )
  {
    RtlCopyUnicodeString(&stru_1400394D0, RegistryPath);
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&NbtDispatchCreate;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)NbtDispatchDevCtrl;
    DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)&NbtDispatchInternalCtrl;
    DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&NbtDispatchCleanup;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&NbtDispatchClose;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)&NbtDispatchPnP;
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)NbtUnload;
    v4 = NbtReadRegistry(&v19, &v18, &v17);
    v5 = v4;
    if ( v4 >= 0 )
    {
      NbtReadRegistryCleanup(&v19, &v18, &v17);
      inited = InitNotOs();
      v5 = inited;
      if ( inited >= 0 )
      {
        v9 = NbtInitMdlQ(&Mdl);
        v5 = v9;
        if ( v9 >= 0 )
        {
          if ( byte_1400395D6 )
          {
            pNbtSmbDevice = (PDEVICE_OBJECT)NbtCreateSmbDevice();
            if ( !pNbtSmbDevice && (xmmword_140038420 & 4) != 0 )
              WPP_SF_(1026, 13, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids);
          }
          RtlInitUnicodeString(&DestinationString, L"\\Device\\NetBt_Wins_Bind");
          DestinationString.MaximumLength = 48;
          RtlInitUnicodeString(&v12, L"\\Device\\NetBt_Wins_Export");
          v12.MaximumLength = 52;
          v10 = NbtAllocAndInitDevice(&DestinationString, &v12);
          v5 = v10;
          if ( v10 >= 0 )
          {
            pWinsDeviceContext[1].AlignmentRequirement = 0;
            pWinsDeviceContext[1].Dpc.SystemArgument1 = 0;
            pWinsDeviceContext[1].Dpc.SystemArgument2 = 0;
            pWinsDeviceContext->Flags &= ~0x80u;
            NbtAcdBind();
            v11 = NbtRegisterNsiNotificationHandlers();
            if ( v11 < 0 && (xmmword_140038420 & 4) != 0 )
              WPP_SF_d(1026, 15, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, (unsigned int)v11);
            NbtInitializeNsi9FTriageBlock();
            NetioRegisterTriageDumpDataCallback(
              qword_140038540,
              29,
              NetBtPopulateTriageDumpData,
              &NetBTGlobalTriageBlock,
              "NetBT");
            RtlInitUnicodeString(&ProviderName, L"\\Device\\NetBT");
            ProviderName.MaximumLength = 28;
            v5 = TdiRegisterProvider(&ProviderName, &TdiProviderHandle);
            if ( v5 >= 0 )
            {
              RtlInitUnicodeString(&v15, L"NetBt");
              *(_DWORD *)&ClientInterfaceInfo.Unused = 0;
              v15.MaximumLength = 12;
              ClientInterfaceInfo.TdiVersion = 2;
              *(&ClientInterfaceInfo.Unused + 2) = 0;
              ClientInterfaceInfo.UnBindHandler = 0;
              ClientInterfaceInfo.ClientName = &v15;
              ClientInterfaceInfo.AddAddressHandlerV2 = (TDI_ADD_ADDRESS_HANDLER_V2)TdiAddressArrival;
              ClientInterfaceInfo.DelAddressHandlerV2 = (TDI_DEL_ADDRESS_HANDLER_V2)TdiAddressDeletion;
              ClientInterfaceInfo.BindingHandler = (TDI_BINDING_HANDLER)&TdiBindHandler;
              ClientInterfaceInfo.PnPPowerHandler = (TDI_PNP_POWER_HANDLER)&TdiPnPPowerHandler;
              v5 = TdiRegisterPnPHandlers(&ClientInterfaceInfo, 0x38u, &TdiClientHandle);
              if ( v5 >= 0 )
                return v5;
              TdiDeregisterProvider(TdiProviderHandle);
            }
            TdiProviderHandle = 0;
            if ( (xmmword_140038420 & 4) != 0 )
              WPP_SF_d(1026, 16, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, (unsigned int)v5);
            v6 = 7;
          }
          else
          {
            if ( (xmmword_140038420 & 4) != 0 )
              WPP_SF_d(1026, 14, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, (unsigned int)v10);
            v6 = 5;
          }
        }
        else
        {
          if ( (xmmword_140038420 & 4) != 0 )
            WPP_SF_d(1026, 12, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, (unsigned int)v9);
          v6 = 4;
        }
      }
      else
      {
        NbtLogEventDetailed(3221229781LL, (unsigned int)inited, 272, 0, 0, 0);
        if ( (xmmword_140038420 & 4) != 0 )
          WPP_SF_d(1026, 11, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, (unsigned int)v5);
        v6 = 3;
      }
    }
    else
    {
      if ( (xmmword_140038420 & 4) != 0 )
        WPP_SF_d(1026, 10, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids, (unsigned int)v4);
      v6 = 1;
    }
    CleanupDriverEntry(v6);
    return v5;
  }
  wil_UninitializeFeatureStaging();
  if ( (unsigned int)Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline() )
    TraceLoggingUnregister_EtwUnregister();
  return -1073741670;
}

```

## disassembly

```asm
0x140053828  push    rbp
0x14005382a  push    rbx
0x14005382b  push    rdi
0x14005382c  lea     rbp, [rsp-47h]
0x140053831  sub     rsp, 0B0h
0x140053838  xorps   xmm0, xmm0
0x14005383b  mov     [rbp+57h+arg_10], 0
0x140053843  xorps   xmm1, xmm1
0x140053846  mov     [rbp+57h+arg_8], 0
0x14005384e  xor     eax, eax
0x140053850  mov     [rbp+57h+arg_0], 0
0x140053858  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005385c  mov     qword ptr [rbp+57h+ClientInterfaceInfo.28h+8], rax
0x140053860  mov     rdi, rdx
0x140053863  movups  xmmword ptr [rbp+57h+var_90.Length], xmm1
0x140053867  mov     rbx, rcx
0x14005386a  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14005386e  movups  xmmword ptr [rbp+57h+ProviderName.Length], xmm1
0x140053872  movups  xmmword ptr [rbp+57h+ClientInterfaceInfo], xmm0
0x140053876  movups  xmmword ptr [rbp+57h+ClientInterfaceInfo.PnPPowerHandler], xmm0
0x14005387a  movups  xmmword ptr [rbp+57h+ClientInterfaceInfo.18h+8], xmm0
0x14005387e  call    FastWppInit
0x140053883  call    Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline
0x140053888  test    eax, eax
0x14005388a  jz      short loc_140053891
0x14005388c  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140053891  call    cs:__imp_TdiInitialize
0x140053898  nop     dword ptr [rax+rax+00h]
0x14005389d  call    wil_InitializeFeatureStaging
0x1400538a2  call    cs:__imp_PsGetCurrentProcess
0x1400538a9  nop     dword ptr [rax+rax+00h]
0x1400538ae  xor     edx, edx; Val
0x1400538b0  lea     rcx, NbtConfig; void *
0x1400538b7  mov     r8d, 328h; Size
0x1400538bd  mov     cs:NbtFspProcess, rax
0x1400538c4  call    memset
0x1400538c9  mov     cs:DriverObject, rbx
0x1400538d0  mov     ecx, 40h ; '@'
0x1400538d5  movzx   eax, word ptr [rdi+2]
0x1400538d9  mov     r8d, 3731624Eh
0x1400538df  mov     cs:stru_1400394D0.MaximumLength, ax
0x1400538e6  movzx   edx, word ptr [rdi+2]
0x1400538ea  call    cs:__imp_ExAllocatePool2
0x1400538f1  nop     dword ptr [rax+rax+00h]
0x1400538f6  mov     cs:stru_1400394D0.Buffer, rax
0x1400538fd  test    rax, rax
0x140053900  jz      loc_140053CE2
0x140053906  mov     rdx, rdi; SourceString
0x140053909  lea     rcx, stru_1400394D0; DestinationString
0x140053910  call    cs:__imp_RtlCopyUnicodeString
0x140053917  nop     dword ptr [rax+rax+00h]
0x14005391c  lea     rax, NbtDispatchCreate
0x140053923  mov     [rbx+70h], rax
0x140053927  lea     r8, [rbp+57h+arg_0]
0x14005392b  lea     rax, NbtDispatchDevCtrl
0x140053932  mov     [rbx+0E0h], rax
0x140053939  lea     rdx, [rbp+57h+arg_8]
0x14005393d  lea     rax, NbtDispatchInternalCtrl
0x140053944  mov     [rbx+0E8h], rax
0x14005394b  lea     rcx, [rbp+57h+arg_10]
0x14005394f  lea     rax, NbtDispatchCleanup
0x140053956  mov     [rbx+100h], rax
0x14005395d  lea     rax, NbtDispatchClose
0x140053964  mov     [rbx+80h], rax
0x14005396b  lea     rax, NbtDispatchPnP
0x140053972  mov     [rbx+148h], rax
0x140053979  lea     rax, NbtUnload
0x140053980  mov     [rbx+68h], rax
0x140053984  call    NbtReadRegistry
0x140053989  mov     edi, eax
0x14005398b  test    eax, eax
0x14005398d  jns     short loc_1400539C2
0x14005398f  test    byte ptr cs:xmmword_140038420, 4
0x140053996  jz      short loc_1400539B1
0x140053998  mov     edx, 0Ah
0x14005399d  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x1400539a4  mov     ecx, 402h
0x1400539a9  mov     r9d, eax
0x1400539ac  call    WPP_SF_d
0x1400539b1  mov     ecx, 1
0x1400539b6  call    CleanupDriverEntry
0x1400539bb  mov     eax, edi
0x1400539bd  jmp     loc_140053CFA
0x1400539c2  lea     r8, [rbp+57h+arg_0]
0x1400539c6  lea     rdx, [rbp+57h+arg_8]
0x1400539ca  lea     rcx, [rbp+57h+arg_10]
0x1400539ce  call    NbtReadRegistryCleanup
0x1400539d3  call    InitNotOs
0x1400539d8  mov     edi, eax
0x1400539da  test    eax, eax
0x1400539dc  jns     short loc_140053A2A
0x1400539de  xor     ecx, ecx
0x1400539e0  xor     edx, edx
0x1400539e2  mov     [rsp+0C0h+var_98], cx
0x1400539e7  xor     r9d, r9d
0x1400539ea  mov     word ptr [rsp+0C0h+var_A0], dx
0x1400539ef  mov     r8d, 110h
0x1400539f5  mov     edx, eax
0x1400539f7  mov     ecx, 0C00010D5h
0x1400539fc  call    NbtLogEventDetailed
0x140053a01  test    byte ptr cs:xmmword_140038420, 4
0x140053a08  jz      short loc_140053A23
0x140053a0a  mov     edx, 0Bh
0x140053a0f  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140053a16  mov     ecx, 402h
0x140053a1b  mov     r9d, edi
0x140053a1e  call    WPP_SF_d
0x140053a23  mov     ecx, 3
0x140053a28  jmp     short loc_1400539B6
0x140053a2a  lea     rcx, Mdl
0x140053a31  call    NbtInitMdlQ
0x140053a36  mov     edi, eax
0x140053a38  test    eax, eax
0x140053a3a  jns     short loc_140053A68
0x140053a3c  test    byte ptr cs:xmmword_140038420, 4
0x140053a43  jz      short loc_140053A5E
0x140053a45  mov     edx, 0Ch
0x140053a4a  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140053a51  mov     ecx, 402h
0x140053a56  mov     r9d, eax
0x140053a59  call    WPP_SF_d
0x140053a5e  mov     ecx, 4
0x140053a63  jmp     loc_1400539B6
0x140053a68  cmp     cs:byte_1400395D6, 0
0x140053a6f  mov     ebx, 402h
0x140053a74  jz      short loc_140053AA1
0x140053a76  call    NbtCreateSmbDevice
0x140053a7b  mov     cs:pNbtSmbDevice, rax
0x140053a82  test    rax, rax
0x140053a85  jnz     short loc_140053AA1
0x140053a87  test    byte ptr cs:xmmword_140038420, 4
0x140053a8e  jz      short loc_140053AA1
0x140053a90  lea     edx, [rax+0Dh]
0x140053a93  mov     ecx, ebx
0x140053a95  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140053a9c  call    WPP_SF_
0x140053aa1  lea     rdx, aDeviceNetbtWin_0; "\\Device\\NetBt_Wins_Bind"
0x140053aa8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140053aac  call    cs:__imp_RtlInitUnicodeString
0x140053ab3  nop     dword ptr [rax+rax+00h]
0x140053ab8  mov     eax, 30h ; '0'
0x140053abd  lea     rdx, aDeviceNetbtWin; "\\Device\\NetBt_Wins_Export"
0x140053ac4  lea     rcx, [rbp+57h+var_90]; DestinationString
0x140053ac8  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x140053acc  call    cs:__imp_RtlInitUnicodeString
0x140053ad3  nop     dword ptr [rax+rax+00h]
0x140053ad8  mov     eax, 34h ; '4'
0x140053add  lea     r8, pWinsDeviceContext
0x140053ae4  lea     rdx, [rbp+57h+var_90]; PCUNICODE_STRING
0x140053ae8  mov     [rbp+57h+var_90.MaximumLength], ax
0x140053aec  lea     rcx, [rbp+57h+DestinationString]; SourceString
0x140053af0  lea     r9d, [rax-31h]
0x140053af4  call    NbtAllocAndInitDevice
0x140053af9  mov     edi, eax
0x140053afb  test    eax, eax
0x140053afd  jns     short loc_140053B28
0x140053aff  test    byte ptr cs:xmmword_140038420, 4
0x140053b06  jz      short loc_140053B1E
0x140053b08  mov     edx, 0Eh
0x140053b0d  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140053b14  mov     ecx, ebx
0x140053b16  mov     r9d, eax
0x140053b19  call    WPP_SF_d
0x140053b1e  mov     ecx, 5
0x140053b23  jmp     loc_1400539B6
0x140053b28  mov     rax, cs:pWinsDeviceContext
0x140053b2f  mov     dword ptr [rax+1E8h], 0
0x140053b39  mov     rax, cs:pWinsDeviceContext
0x140053b40  mov     qword ptr [rax+240h], 0
0x140053b4b  mov     rax, cs:pWinsDeviceContext
0x140053b52  mov     qword ptr [rax+248h], 0
0x140053b5d  mov     rax, cs:pWinsDeviceContext
0x140053b64  btr     dword ptr [rax+30h], 7
0x140053b69  call    NbtAcdBind
0x140053b6e  call    NbtRegisterNsiNotificationHandlers
0x140053b73  test    eax, eax
0x140053b75  jns     short loc_140053B96
0x140053b77  test    byte ptr cs:xmmword_140038420, 4
0x140053b7e  jz      short loc_140053B96
0x140053b80  mov     edx, 0Fh
0x140053b85  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140053b8c  mov     ecx, ebx
0x140053b8e  mov     r9d, eax
0x140053b91  call    WPP_SF_d
0x140053b96  call    NbtInitializeNsi9FTriageBlock
0x140053b9b  lea     rax, aNetbt; "NetBT"
0x140053ba2  mov     edx, 1Dh
0x140053ba7  lea     r9, NetBTGlobalTriageBlock
0x140053bae  mov     [rsp+0C0h+var_A0], rax
0x140053bb3  lea     r8, NetBtPopulateTriageDumpData
0x140053bba  lea     rcx, qword_140038540
0x140053bc1  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x140053bc8  nop     dword ptr [rax+rax+00h]
0x140053bcd  lea     rdx, aDeviceNetbt; "\\Device\\NetBT"
0x140053bd4  lea     rcx, [rbp+57h+ProviderName]; DestinationString
0x140053bd8  call    cs:__imp_RtlInitUnicodeString
0x140053bdf  nop     dword ptr [rax+rax+00h]
0x140053be4  mov     eax, 1Ch
0x140053be9  lea     rdx, TdiProviderHandle; ProviderHandle
0x140053bf0  lea     rcx, [rbp+57h+ProviderName]; ProviderName
0x140053bf4  mov     [rbp+57h+ProviderName.MaximumLength], ax
0x140053bf8  call    cs:__imp_TdiRegisterProvider
0x140053bff  nop     dword ptr [rax+rax+00h]
0x140053c04  mov     edi, eax
0x140053c06  test    eax, eax
0x140053c08  js      loc_140053CB2
0x140053c0e  lea     rdx, aNetbt_0; "NetBt"
0x140053c15  lea     rcx, [rbp+57h+var_60]; DestinationString
0x140053c19  call    cs:__imp_RtlInitUnicodeString
0x140053c20  nop     dword ptr [rax+rax+00h]
0x140053c25  mov     eax, 0Ch
0x140053c2a  mov     dword ptr [rbp+57h+ClientInterfaceInfo.Unused], 0
0x140053c31  mov     [rbp+57h+var_60.MaximumLength], ax
0x140053c35  lea     r8, TdiClientHandle; BindingHandle
0x140053c3c  xor     eax, eax
0x140053c3e  mov     word ptr [rbp+57h+ClientInterfaceInfo], 2
0x140053c44  mov     word ptr [rbp+57h+ClientInterfaceInfo+6], ax
0x140053c48  lea     rcx, [rbp+57h+ClientInterfaceInfo]; ClientInterfaceInfo
0x140053c4c  mov     qword ptr [rbp+57h+ClientInterfaceInfo.18h+8], rax
0x140053c50  mov     edx, 38h ; '8'; InterfaceInfoSize
0x140053c55  lea     rax, [rbp+57h+var_60]
0x140053c59  mov     [rbp+57h+ClientInterfaceInfo.ClientName], rax
0x140053c5d  lea     rax, TdiAddressArrival
0x140053c64  mov     qword ptr [rbp+57h+ClientInterfaceInfo.28h], rax
0x140053c68  lea     rax, TdiAddressDeletion
0x140053c6f  mov     qword ptr [rbp+57h+ClientInterfaceInfo.28h+8], rax
0x140053c73  lea     rax, TdiBindHandler
0x140053c7a  mov     qword ptr [rbp+57h+ClientInterfaceInfo.18h], rax
0x140053c7e  lea     rax, TdiPnPPowerHandler
0x140053c85  mov     [rbp+57h+ClientInterfaceInfo.PnPPowerHandler], rax
0x140053c89  call    cs:__imp_TdiRegisterPnPHandlers
0x140053c90  nop     dword ptr [rax+rax+00h]
0x140053c95  mov     edi, eax
0x140053c97  test    eax, eax
0x140053c99  jns     loc_1400539BB
0x140053c9f  mov     rcx, cs:TdiProviderHandle; ProviderHandle
0x140053ca6  call    cs:__imp_TdiDeregisterProvider
0x140053cad  nop     dword ptr [rax+rax+00h]
0x140053cb2  xor     eax, eax
0x140053cb4  mov     cs:TdiProviderHandle, rax
0x140053cbb  test    byte ptr cs:xmmword_140038420, 4
0x140053cc2  jz      short loc_140053CD8
0x140053cc4  lea     edx, [rax+10h]
0x140053cc7  mov     ecx, ebx
0x140053cc9  mov     r9d, edi
0x140053ccc  lea     r8, WPP_a41fab0ebd9430672f19da0e3e39181e_Traceguids
0x140053cd3  call    WPP_SF_d
0x140053cd8  mov     ecx, 7
0x140053cdd  jmp     loc_1400539B6
0x140053ce2  call    wil_UninitializeFeatureStaging
0x140053ce7  call    Feature_TCPIP_K2_9F_Netbt_Timeout__private_IsEnabledDeviceUsageNoInline
0x140053cec  test    eax, eax
0x140053cee  jz      short loc_140053CF5
0x140053cf0  call    TraceLoggingUnregister_EtwUnregister
0x140053cf5  mov     eax, 0C000009Ah
0x140053cfa  add     rsp, 0B0h
0x140053d01  pop     rdi
0x140053d02  pop     rbx
0x140053d03  pop     rbp
0x140053d04  retn
```
