# EnumDeviceRegHWMFTs(_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)

- ea: `0x1800afd58`
- end: `0x1800b0278`
- name: `?EnumDeviceRegHWMFTs@@YAJAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAPEAUIMFActivate@@PEAI@Z`
- size: `1312`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFActivate ***, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180092ba0`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004a6c8`
- `0x1800916e8`
- `0x1800a8634`
- `0x1800afd58`
- `0x18011fff0`
- `0x180120030`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800b021e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800b021e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b00a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b00a1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800b01b8`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800b01b8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800afe01`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800affa7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800afe01`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800affa7`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1800b0197`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x1800b0197`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800b00ed`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800b0148`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800b00ed`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800b0148`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x1800afdf4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x1800afdf4`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800b0163`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800b0163`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x1800afe76`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x1800afe76`

## pseudocode

```c
__int64 __fastcall EnumDeviceRegHWMFTs(
        struct _GUID *a1,
        DEVNODE a2,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a3,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a4,
        struct IMFActivate ***a5,
        unsigned int *a6)
{
  CONFIGRET Device_Interface_ListW; // eax
  PZZWSTR v7; // r12
  int i; // edi
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int v10; // eax
  signed int v11; // ebx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  CallStackTracing *v15; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  signed int v17; // eax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  unsigned int j; // edi
  struct IMFActivate *v21; // rcx
  unsigned __int64 v22; // rsi
  DEVNODE v23; // ebx
  unsigned __int16 *v24; // rdi
  size_t v25; // rax
  CallStackScopeTrace v27; // [rsp+40h] [rbp-49h] BYREF
  ULONG pulLen; // [rsp+44h] [rbp-45h] BYREF
  DEVNODE pdnDevInst; // [rsp+48h] [rbp-41h] BYREF
  PZZWSTR Buffer; // [rsp+50h] [rbp-39h] BYREF
  ULONG PropertyBufferSize; // [rsp+58h] [rbp-31h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-29h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+68h] [rbp-21h] BYREF
  signed int v34; // [rsp+6Ch] [rbp-1Dh]
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v35; // [rsp+70h] [rbp-19h]
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v36; // [rsp+78h] [rbp-11h]
  struct _GUID *v37; // [rsp+80h] [rbp-9h]
  GUID InterfaceClassGuid; // [rsp+88h] [rbp-1h] BYREF

  v36 = a3;
  pdnDevInst = a2;
  v37 = a1;
  v35 = a4;
  CallStackScopeTrace::CallStackScopeTrace(&v27, "EnumDeviceRegHWMFTs", 2112);
  Device_Interface_ListW = 26;
  v7 = 0;
  Buffer = 0;
  pulLen = 0;
  for ( i = 0; Device_Interface_ListW == 26 && i < 10; ++i )
  {
    InterfaceClassGuid = GUID_DISPLAY_DEVICE_ARRIVAL;
    Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, &InterfaceClassGuid, 0, 0);
    v10 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0x507u);
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( v11 < 0 )
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v15 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v15->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
        if ( ThreadRelativeContext->m_result != v11 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "EnumDeviceRegHWMFTs", 2123, v11);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 44;
        goto LABEL_42;
      }
      goto LABEL_43;
    }
    phkResult = (HKEY)operator new(saturated_mul(pulLen, 2u));
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&Buffer, &phkResult);
    if ( phkResult )
      operator delete(phkResult);
    v7 = Buffer;
    if ( !Buffer )
    {
      v12 = CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v12->m_fEnabled )
      {
        v13 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( v13->m_result != -2147024882 )
          CallStackContext::TraceFailure(v13, "EnumDeviceRegHWMFTs", 2127, -2147024882);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 45;
        goto LABEL_42;
      }
      goto LABEL_43;
    }
    Device_Interface_ListW = CM_Get_Device_Interface_ListW(&InterfaceClassGuid, 0, Buffer, pulLen, 0);
    if ( !Device_Interface_ListW )
      break;
  }
  v17 = CM_MapCrToWin32Err(Device_Interface_ListW, 0x507u);
  v34 = v17;
  v11 = v17;
  if ( v17 > 0 )
  {
    v11 = (unsigned __int16)v17 | 0x80070000;
    v34 = v11;
  }
  if ( v11 < 0 )
  {
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v18 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v18->m_fEnabled )
    {
      v19 = CallStackTracing::GetThreadRelativeContext(v18);
      if ( v19->m_result != v11 )
        CallStackContext::TraceFailure(v19, "EnumDeviceRegHWMFTs", 2136, v11);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v14 = 46;
LABEL_42:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids, 0, v11);
    }
LABEL_43:
    if ( *a5 )
    {
      for ( j = 0; j < *a6; ++j )
      {
        v21 = (*a5)[j];
        if ( v21 )
        {
          ((void (__fastcall *)(struct IMFActivate *))v21->lpVtbl->Release)(v21);
          (*a5)[j] = 0;
        }
      }
      CoTaskMemFree(*a5);
      *a5 = 0;
    }
    *a6 = 0;
    goto LABEL_67;
  }
  v22 = 0;
  if ( pulLen )
  {
    v23 = pdnDevInst;
    do
    {
      PropertyType = 0;
      PropertyBufferSize = 0;
      if ( CM_Get_Device_Interface_PropertyW(
             &v7[v22],
             &DEVPKEY_Device_InstanceId,
             &PropertyType,
             0,
             &PropertyBufferSize,
             0) == 26 )
      {
        v24 = (unsigned __int16 *)operator new(saturated_mul(PropertyBufferSize, 2u));
        if ( v24 )
        {
          if ( !CM_Get_Device_Interface_PropertyW(
                  &v7[v22],
                  &DEVPKEY_Device_InstanceId,
                  &PropertyType,
                  (PBYTE)v24,
                  &PropertyBufferSize,
                  0) )
          {
            pdnDevInst = 0;
            if ( !CM_Locate_DevNodeW(&pdnDevInst, v24, 0) )
            {
              Buffer = 0;
              if ( !CM_Open_DevNode_Key(pdnDevInst, 0x20019u, 0, 1u, (PHKEY)&Buffer, 1u) )
              {
                phkResult = 0;
                if ( !RegOpenKeyW((HKEY)Buffer, L"MediaFoundation\\Transforms", &phkResult) )
                  EnumSoftwareMFTsBase(phkResult, v24, v37, v23, v36, v35, a5, a6);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&Buffer);
            }
          }
          operator delete(v24);
        }
      }
      if ( &v7[v22] )
        v25 = wcsnlen(&v7[v22], pulLen - v22);
      else
        v25 = 0;
      v22 += v25 + 1;
    }
    while ( v22 < pulLen );
    v11 = v34;
  }
LABEL_67:
  if ( v7 )
    operator delete(v7);
  CallStackScopeTrace::~CallStackScopeTrace(&v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800afd58  mov     [rsp-8+arg_8], rbx
0x1800afd5d  push    rbp
0x1800afd5e  push    rsi
0x1800afd5f  push    rdi
0x1800afd60  push    r12
0x1800afd62  push    r13
0x1800afd64  push    r14
0x1800afd66  push    r15
0x1800afd68  lea     rbp, [rsp-17h]
0x1800afd6d  sub     rsp, 0A0h
0x1800afd74  mov     rax, cs:__security_cookie
0x1800afd7b  xor     rax, rsp
0x1800afd7e  mov     [rbp+47h+var_38], rax
0x1800afd82  mov     r15, [rbp+47h+arg_20]
0x1800afd86  lea     rsi, aEnumdeviceregh; "EnumDeviceRegHWMFTs"
0x1800afd8d  mov     r13, [rbp+47h+arg_28]
0x1800afd91  mov     [rbp+47h+var_58], r8
0x1800afd95  mov     r8d, 840h; int
0x1800afd9b  mov     [rbp+47h+pdnDevInst], edx
0x1800afd9e  mov     rdx, rsi; char *
0x1800afda1  mov     [rbp+47h+var_50], rcx
0x1800afda5  lea     rcx, [rbp+47h+var_90]; this
0x1800afda9  mov     [rbp+47h+var_60], r9
0x1800afdad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800afdb2  xor     r14d, r14d
0x1800afdb5  mov     eax, 1Ah
0x1800afdba  mov     r12d, r14d
0x1800afdbd  mov     [rbp+47h+Buffer], r14
0x1800afdc1  mov     [rbp+47h+pulLen], r14d
0x1800afdc5  mov     edi, r14d
0x1800afdc8  cmp     eax, 1Ah
0x1800afdcb  jnz     loc_1800AFFA0
0x1800afdd1  cmp     edi, 0Ah
0x1800afdd4  jge     loc_1800AFFA0
0x1800afdda  movups  xmm0, xmmword ptr cs:GUID_DISPLAY_DEVICE_ARRIVAL.Data1
0x1800afde1  xor     r9d, r9d; ulFlags
0x1800afde4  lea     rdx, [rbp+47h+InterfaceClassGuid]; InterfaceClassGuid
0x1800afde8  xor     r8d, r8d; pDeviceID
0x1800afdeb  lea     rcx, [rbp+47h+pulLen]; pulLen
0x1800afdef  movdqu  xmmword ptr [rbp+47h+InterfaceClassGuid.Data1], xmm0
0x1800afdf4  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x1800afdfa  mov     ecx, eax; CmReturnCode
0x1800afdfc  mov     edx, 507h; DefaultErr
0x1800afe01  call    cs:__imp_CM_MapCrToWin32Err
0x1800afe07  mov     ebx, eax
0x1800afe09  test    eax, eax
0x1800afe0b  jle     short loc_1800AFE16
0x1800afe0d  movzx   ebx, ax
0x1800afe10  or      ebx, 80070000h
0x1800afe16  test    ebx, ebx
0x1800afe18  js      loc_1800AFF18
0x1800afe1e  mov     ecx, [rbp+47h+pulLen]
0x1800afe21  mov     eax, 2
0x1800afe26  mul     rcx
0x1800afe29  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800afe30  cmovb   rax, rcx
0x1800afe34  mov     rcx, rax; Size
0x1800afe37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800afe3c  lea     rdx, [rbp+47h+phkResult]
0x1800afe40  mov     [rbp+47h+phkResult], rax
0x1800afe44  lea     rcx, [rbp+47h+Buffer]
0x1800afe48  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800afe4d  mov     rcx, [rbp+47h+phkResult]; void *
0x1800afe51  test    rcx, rcx
0x1800afe54  jz      short loc_1800AFE5B
0x1800afe56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800afe5b  mov     r12, [rbp+47h+Buffer]
0x1800afe5f  test    r12, r12
0x1800afe62  jz      short loc_1800AFE8B
0x1800afe64  mov     r9d, [rbp+47h+pulLen]; BufferLen
0x1800afe68  lea     rcx, [rbp+47h+InterfaceClassGuid]; InterfaceClassGuid
0x1800afe6c  mov     r8, r12; Buffer
0x1800afe6f  mov     [rsp+0D0h+ulFlags], r14d; ulFlags
0x1800afe74  xor     edx, edx; pDeviceID
0x1800afe76  call    cs:__imp_CM_Get_Device_Interface_ListW
0x1800afe7c  test    eax, eax
0x1800afe7e  jz      loc_1800AFFA0
0x1800afe84  inc     edi
0x1800afe86  jmp     loc_1800AFDC8
0x1800afe8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800afe92  mov     ebx, 8007000Eh
0x1800afe97  test    rcx, rcx
0x1800afe9a  jnz     short loc_1800AFEDA
0x1800afe9c  mov     rax, cs:stru_1801FC290.__vftable
0x1800afea3  lea     rcx, stru_1801FC290
0x1800afeaa  mov     edx, 7F0h
0x1800afeaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800afeb6  mov     rax, [rax+8]
0x1800afeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afebf  test    eax, eax
0x1800afec1  jnz     short loc_1800AFED3
0x1800afec3  lea     rcx, stru_1801F8A30
0x1800afeca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800afed1  jmp     short loc_1800AFEDA
0x1800afed3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800afeda  cmp     [rcx+8], r14b
0x1800afede  jz      short loc_1800AFF01
0x1800afee0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800afee5  cmp     [rax+7CCh], ebx
0x1800afeeb  jz      short loc_1800AFF01
0x1800afeed  mov     r9d, ebx; int
0x1800afef0  mov     r8d, 84Fh; int
0x1800afef6  mov     rdx, rsi; char *
0x1800afef9  mov     rcx, rax; this
0x1800afefc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aff01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aff08  jb      loc_1800B0067
0x1800aff0e  mov     edx, 2Dh ; '-'
0x1800aff13  jmp     loc_1800B0049
0x1800aff18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aff1f  test    rcx, rcx
0x1800aff22  jnz     short loc_1800AFF62
0x1800aff24  mov     rax, cs:stru_1801FC290.__vftable
0x1800aff2b  lea     rcx, stru_1801FC290
0x1800aff32  mov     edx, 7F0h
0x1800aff37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aff3e  mov     rax, [rax+8]
0x1800aff42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff47  test    eax, eax
0x1800aff49  jnz     short loc_1800AFF5B
0x1800aff4b  lea     rcx, stru_1801F8A30
0x1800aff52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aff59  jmp     short loc_1800AFF62
0x1800aff5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aff62  cmp     [rcx+8], r14b
0x1800aff66  jz      short loc_1800AFF89
0x1800aff68  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aff6d  cmp     [rax+7CCh], ebx
0x1800aff73  jz      short loc_1800AFF89
0x1800aff75  mov     r9d, ebx; int
0x1800aff78  mov     r8d, 84Bh; int
0x1800aff7e  mov     rdx, rsi; char *
0x1800aff81  mov     rcx, rax; this
0x1800aff84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aff89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aff90  jb      loc_1800B0067
0x1800aff96  mov     edx, 2Ch ; ','
0x1800aff9b  jmp     loc_1800B0049
0x1800affa0  mov     edx, 507h; DefaultErr
0x1800affa5  mov     ecx, eax; CmReturnCode
0x1800affa7  call    cs:__imp_CM_MapCrToWin32Err
0x1800affad  mov     [rbp+47h+var_64], eax
0x1800affb0  mov     ebx, eax
0x1800affb2  test    eax, eax
0x1800affb4  jle     short loc_1800AFFC2
0x1800affb6  movzx   ebx, ax
0x1800affb9  or      ebx, 80070000h
0x1800affbf  mov     [rbp+47h+var_64], ebx
0x1800affc2  test    ebx, ebx
0x1800affc4  jns     loc_1800B00B3
0x1800affca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800affd1  test    rcx, rcx
0x1800affd4  jnz     short loc_1800B0014
0x1800affd6  mov     rax, cs:stru_1801FC290.__vftable
0x1800affdd  lea     rcx, stru_1801FC290
0x1800affe4  mov     edx, 7F0h
0x1800affe9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800afff0  mov     rax, [rax+8]
0x1800afff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afff9  test    eax, eax
0x1800afffb  jnz     short loc_1800B000D
0x1800afffd  lea     rcx, stru_1801F8A30
0x1800b0004  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b000b  jmp     short loc_1800B0014
0x1800b000d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b0014  cmp     [rcx+8], r14b
0x1800b0018  jz      short loc_1800B003B
0x1800b001a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b001f  cmp     [rax+7CCh], ebx
0x1800b0025  jz      short loc_1800B003B
0x1800b0027  mov     r9d, ebx; int
0x1800b002a  mov     r8d, 858h; int
0x1800b0030  mov     rdx, rsi; char *
0x1800b0033  mov     rcx, rax; this
0x1800b0036  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b003b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b0042  jb      short loc_1800B0067
0x1800b0044  mov     edx, 2Eh ; '.'
0x1800b0049  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0050  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x1800b0057  xor     r9d, r9d
0x1800b005a  mov     [rsp+0D0h+ulFlags], ebx
0x1800b005e  mov     rcx, [rcx+10h]
0x1800b0062  call    WPP_SF_qD
0x1800b0067  cmp     [r15], r14
0x1800b006a  jz      short loc_1800B00AA
0x1800b006c  mov     edi, r14d
0x1800b006f  cmp     [r13+0], r14d
0x1800b0073  jbe     short loc_1800B009E
0x1800b0075  mov     rax, [r15]
0x1800b0078  mov     esi, edi
0x1800b007a  mov     rcx, [rax+rsi*8]
0x1800b007e  test    rcx, rcx
0x1800b0081  jz      short loc_1800B0096
0x1800b0083  mov     rax, [rcx]
0x1800b0086  mov     rax, [rax+10h]
0x1800b008a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b008f  mov     rax, [r15]
0x1800b0092  mov     [rax+rsi*8], r14
0x1800b0096  inc     edi
0x1800b0098  cmp     edi, [r13+0]
0x1800b009c  jb      short loc_1800B0075
0x1800b009e  mov     rcx, [r15]; pv
0x1800b00a1  call    cs:__imp_CoTaskMemFree
0x1800b00a7  mov     [r15], r14
0x1800b00aa  mov     [r13+0], r14d
0x1800b00ae  jmp     loc_1800B0239
0x1800b00b3  mov     rsi, r14
0x1800b00b6  cmp     [rbp+47h+pulLen], r14d
0x1800b00ba  jbe     loc_1800B0239
0x1800b00c0  mov     ebx, [rbp+47h+pdnDevInst]
0x1800b00c3  xor     eax, eax
0x1800b00c5  lea     r14, [r12+rsi*2]
0x1800b00c9  mov     [rsp+0D0h+var_A8], eax; ulFlags
0x1800b00cd  lea     r8, [rbp+47h+PropertyType]; PropertyType
0x1800b00d1  mov     [rbp+47h+PropertyType], eax
0x1800b00d4  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800b00db  mov     [rbp+47h+PropertyBufferSize], eax
0x1800b00de  xor     r9d, r9d; PropertyBuffer
0x1800b00e1  lea     rax, [rbp+47h+PropertyBufferSize]
0x1800b00e5  mov     rcx, r14; pszDeviceInterface
0x1800b00e8  mov     qword ptr [rsp+0D0h+ulFlags], rax; PropertyBufferSize
0x1800b00ed  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800b00f3  cmp     eax, 1Ah
0x1800b00f6  jnz     loc_1800B020B
0x1800b00fc  mov     ecx, [rbp+47h+PropertyBufferSize]
0x1800b00ff  mov     eax, 2
0x1800b0104  mul     rcx
0x1800b0107  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b010e  cmovb   rax, rcx
0x1800b0112  mov     rcx, rax; Size
0x1800b0115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b011a  mov     rdi, rax
0x1800b011d  test    rax, rax
0x1800b0120  jz      loc_1800B020B
0x1800b0126  lea     rax, [rbp+47h+PropertyBufferSize]
0x1800b012a  mov     [rsp+0D0h+var_A8], 0; ulFlags
0x1800b0132  mov     r9, rdi; PropertyBuffer
0x1800b0135  mov     qword ptr [rsp+0D0h+ulFlags], rax; PropertyBufferSize
0x1800b013a  lea     r8, [rbp+47h+PropertyType]; PropertyType
0x1800b013e  mov     rcx, r14; pszDeviceInterface
0x1800b0141  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800b0148  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800b014e  test    eax, eax
0x1800b0150  jnz     loc_1800B0203
0x1800b0156  xor     r8d, r8d; ulFlags
0x1800b0159  mov     [rbp+47h+pdnDevInst], eax
0x1800b015c  mov     rdx, rdi; pDeviceID
0x1800b015f  lea     rcx, [rbp+47h+pdnDevInst]; pdnDevInst
0x1800b0163  call    cs:__imp_CM_Locate_DevNodeW
0x1800b0169  test    eax, eax
0x1800b016b  jnz     loc_1800B0203
0x1800b0171  lea     ecx, [rax+1]
0x1800b0174  mov     [rbp+47h+Buffer], 0
0x1800b017c  mov     [rsp+0D0h+var_A8], ecx; ulFlags
0x1800b0180  lea     rax, [rbp+47h+Buffer]
0x1800b0184  mov     r9d, ecx; Disposition
0x1800b0187  mov     qword ptr [rsp+0D0h+ulFlags], rax; phkDevice
0x1800b018c  mov     ecx, [rbp+47h+pdnDevInst]; dnDevNode
0x1800b018f  xor     r8d, r8d; ulHardwareProfile
0x1800b0192  mov     edx, 20019h; samDesired
0x1800b0197  call    cs:__imp_CM_Open_DevNode_Key
0x1800b019d  test    eax, eax
0x1800b019f  jnz     short loc_1800B01FA
0x1800b01a1  mov     rcx, [rbp+47h+Buffer]; hKey
0x1800b01a5  lea     r8, [rbp+47h+phkResult]; phkResult
0x1800b01a9  lea     rdx, SubKey; "MediaFoundation\\Transforms"
0x1800b01b0  mov     [rbp+47h+phkResult], 0
0x1800b01b8  call    cs:__imp_RegOpenKeyW
0x1800b01be  test    eax, eax
0x1800b01c0  jnz     short loc_1800B01F1
0x1800b01c2  mov     rax, [rbp+47h+var_60]
0x1800b01c6  mov     r9d, ebx; unsigned int
0x1800b01c9  mov     r8, [rbp+47h+var_50]; struct _GUID *
0x1800b01cd  mov     rdx, rdi; unsigned __int16 *
0x1800b01d0  mov     rcx, [rbp+47h+phkResult]; hKey
0x1800b01d4  mov     [rsp+0D0h+var_98], r13; unsigned int *
0x1800b01d9  mov     [rsp+0D0h+var_A0], r15; struct IMFActivate ***
0x1800b01de  mov     qword ptr [rsp+0D0h+var_A8], rax; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800b01e3  mov     rax, [rbp+47h+var_58]
0x1800b01e7  mov     qword ptr [rsp+0D0h+ulFlags], rax; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800b01ec  call    ?EnumSoftwareMFTsBase@@YAJPEAUHKEY__@@PEAGAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@3PEAPEAPEAUIMFActivate@@PEAI@Z; EnumSoftwareMFTsBase(HKEY__ *,ushort *,_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x1800b01f1  lea     rcx, [rbp+47h+phkResult]
0x1800b01f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b01fa  lea     rcx, [rbp+47h+Buffer]
0x1800b01fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b0203  mov     rcx, rdi; void *
0x1800b0206  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b020b  test    r14, r14
0x1800b020e  jnz     short loc_1800B0215
0x1800b0210  mov     rax, r14
0x1800b0213  jmp     short loc_1800B0224
0x1800b0215  mov     edx, [rbp+47h+pulLen]
0x1800b0218  mov     rcx, r14; Source
0x1800b021b  sub     rdx, rsi; MaxCount
0x1800b021e  call    cs:__imp_wcsnlen
0x1800b0224  inc     rax
0x1800b0227  add     rsi, rax
0x1800b022a  mov     eax, [rbp+47h+pulLen]
0x1800b022d  cmp     rsi, rax
  ... truncated ...
```
