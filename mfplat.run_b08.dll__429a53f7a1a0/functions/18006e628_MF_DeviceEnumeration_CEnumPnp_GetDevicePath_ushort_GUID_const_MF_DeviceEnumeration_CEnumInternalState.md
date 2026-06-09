# MF::DeviceEnumeration::CEnumPnp::GetDevicePath(ushort * *,_GUID const * *,MF::DeviceEnumeration::CEnumInternalState *)

- ea: `0x18006e628`
- end: `0x18006efc7`
- name: `?GetDevicePath@CEnumPnp@DeviceEnumeration@MF@@QEAAJPEAPEAGPEAPEBU_GUID@@PEAUCEnumInternalState@23@@Z`
- size: `2463`
- prototype: `__int64 __fastcall(MF::DeviceEnumeration::CEnumPnp *__hidden this, unsigned __int16 **, const struct _GUID **, struct MF::DeviceEnumeration::CEnumInternalState *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x18006df58`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18006e628`
- `0x18006fbbc`
- `0x1800b095c`
- `0x180120030`
- `0x18012003c`
- `0x1801200d0`
- `0x180120e84`
- `0x180128588`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e924`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e918`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e918`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18006e842`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18006ef2b`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18006ef7e`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18006e842`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18006ef2b`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x18006ef7e`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006ea49`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006eab3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006eca8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006ea49`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006eab3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006eca8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18006e76f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18006e76f`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006e8d8`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006e8d8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18006e7e7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18006e7e7`

## string_xrefs

- `0x18006e652`: `MF::DeviceEnumeration::CEnumPnp::GetDevicePath`
- `0x18006e6c9`: `MF::DeviceEnumeration::CEnumPnp::GetDevicePath`
- `0x18006e857`: `MF::DeviceEnumeration::CEnumPnp::GetDevicePath`
- `0x18006e88d`: `MF::DeviceEnumeration::CEnumPnp::GetDevicePath`
- `0x18006e90d`: `InterfaceLink`

## pseudocode

```c
__int64 __fastcall MF::DeviceEnumeration::CEnumPnp::GetDevicePath(
        MF::DeviceEnumeration::CEnumPnp *this,
        unsigned __int16 **a2,
        GUID **a3,
        struct MF::DeviceEnumeration::CEnumInternalState *a4)
{
  GUID *v4; // rax
  GUID v7; // xmm0
  unsigned int v8; // r13d
  WCHAR *v9; // r15
  unsigned int v10; // eax
  const WCHAR *i; // rsi
  unsigned int v12; // r12d
  __int64 v13; // rax
  const WCHAR *v14; // rsi
  CallStackTracing *v15; // rcx
  signed int v16; // edi
  struct CallStackContext *v17; // rax
  CONFIGRET Device_Interface_List_SizeW; // ebx
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  CONFIGRET Device_Interface_ListW; // ebx
  unsigned int j; // ebx
  GUID *v24; // rax
  GUID v25; // xmm0
  LSTATUS v26; // ebx
  const WCHAR *v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // r14
  unsigned __int16 *v30; // rax
  unsigned __int16 **v31; // r12
  unsigned int k; // esi
  __int64 v33; // rbx
  unsigned __int16 v34; // ax
  CallStackTracing *v35; // rcx
  signed int v36; // eax
  CallStackTracing *v37; // rcx
  __int64 v38; // rdx
  signed int v39; // eax
  CallStackTracing *v40; // rcx
  MF::DeviceEnumeration::CEnumPnp *v41; // r9
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  signed int v45; // eax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  WCHAR *v50; // rax
  CONFIGRET Device_Interface_AliasW; // eax
  int ulFlags; // [rsp+20h] [rbp-59h]
  CallStackScopeTrace v53; // [rsp+30h] [rbp-49h] BYREF
  ULONG pulLen; // [rsp+34h] [rbp-45h] BYREF
  ULONG pulLength; // [rsp+38h] [rbp-41h] BYREF
  DWORD Type[2]; // [rsp+40h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-31h] BYREF
  HKEY phkDeviceInterface; // [rsp+50h] [rbp-29h] BYREF
  MF::DeviceEnumeration::CEnumPnp *v59; // [rsp+58h] [rbp-21h]
  unsigned __int16 **v60; // [rsp+60h] [rbp-19h]
  GUID AliasInterfaceGuid; // [rsp+68h] [rbp-11h] BYREF
  GUID InterfaceClassGuid; // [rsp+78h] [rbp-1h] BYREF

  v4 = *a3;
  *(_QWORD *)Type = a3;
  v60 = a2;
  v7 = *v4;
  v59 = this;
  pulLength = 0;
  InterfaceClassGuid = v7;
  if ( *((_QWORD *)a4 + 1) )
    goto LABEL_2;
  pulLen = 0;
  Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, &InterfaceClassGuid, 0, 0);
  if ( Device_Interface_List_SizeW )
  {
    CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 500);
    if ( byte_1801FD28B )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 24, &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids);
    v39 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
    v16 = v39;
    if ( v39 > 0 )
      v16 = (unsigned __int16)v39 | 0x80070000;
    if ( v16 < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v40->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v40);
        if ( ThreadRelativeContext->m_result != v16 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "MF::DeviceEnumeration::CEnumPnp::GetDevicePath",
            502,
            v16);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_46;
      v38 = 25;
LABEL_66:
      ulFlags = v16;
LABEL_67:
      v41 = this;
LABEL_107:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v38,
        &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids,
        v41,
        ulFlags);
      goto LABEL_46;
    }
  }
  else
  {
    v20 = 2LL * (pulLen + 2);
    if ( !is_mul_ok(pulLen + 2, 2u) )
      v20 = -1;
    *((_QWORD *)a4 + 1) = operator new[](v20);
    CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 477);
    v21 = *((_QWORD *)a4 + 1);
    if ( !v21 )
    {
      v35 = CallStackTracing::s_wpInstance;
      v16 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v35 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v35->m_fEnabled )
      {
        v42 = CallStackTracing::GetThreadRelativeContext(v35);
        if ( v42->m_result != -2147024882 )
          CallStackContext::TraceFailure(v42, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 477, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_46;
      v38 = 21;
      ulFlags = -2147024882;
      goto LABEL_67;
    }
    *(_WORD *)(v21 + 2LL * pulLen) = 0;
    *(_WORD *)(*((_QWORD *)a4 + 1) + 2LL * (pulLen + 1)) = 0;
    Device_Interface_ListW = CM_Get_Device_Interface_ListW(&InterfaceClassGuid, 0, *((PZZWSTR *)a4 + 1), pulLen, 0);
    if ( Device_Interface_ListW )
    {
      if ( byte_1801FD28B )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 22, &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids);
      v36 = CM_MapCrToWin32Err(Device_Interface_ListW, 0xDu);
      v16 = v36;
      if ( v36 > 0 )
        v16 = (unsigned __int16)v36 | 0x80070000;
      if ( v16 < 0 )
      {
        v37 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v37 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v37->m_fEnabled )
        {
          v43 = CallStackTracing::GetThreadRelativeContext(v37);
          if ( v43->m_result != v16 )
            CallStackContext::TraceFailure(v43, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 495, v16);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_46;
        v38 = 23;
        goto LABEL_66;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v53);
  a3 = *(GUID ***)Type;
LABEL_2:
  v8 = *(_DWORD *)a4;
  v9 = 0;
  v10 = 0;
  for ( i = (const WCHAR *)*((_QWORD *)a4 + 1); ; i = v14 + 1 )
  {
    if ( !*i )
      goto LABEL_8;
    v12 = v10 + 1;
    if ( v10 >= v8 )
    {
      *(_DWORD *)a4 = v12;
      for ( j = 1; ; ++j )
      {
        v24 = a3[j];
        if ( !v24 )
          break;
        v25 = *v24;
        LOWORD(pulLen) = 0;
        pulLength = 1;
        AliasInterfaceGuid = v25;
        if ( CM_Get_Device_Interface_AliasW(i, &AliasInterfaceGuid, (LPWSTR)&pulLen, &pulLength, 0) != 26 )
        {
          CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 543);
          if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              26,
              &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids,
              (unsigned int)(*(_DWORD *)a4 - 1),
              **(_DWORD **)(*(_QWORD *)Type + 8LL * j));
          CallStackScopeTrace::~CallStackScopeTrace(&v53);
          a3 = *(GUID ***)Type;
          break;
        }
        a3 = *(GUID ***)Type;
      }
      if ( !a3[j] )
        break;
    }
    v13 = -1;
    do
      ++v13;
    while ( i[v13] );
    v14 = &i[v13];
    v10 = v12;
  }
  CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 557);
  if ( (unsigned __int8)byte_1801FD28B >= 0x20u )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      27,
      &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids,
      (unsigned int)(*(_DWORD *)a4 - 1),
      j);
  CallStackScopeTrace::~CallStackScopeTrace(&v53);
  phkDeviceInterface = 0;
  if ( CM_Open_Device_Interface_KeyW(i, 0x20019u, 1u, &phkDeviceInterface, 0) )
    goto LABEL_34;
  cbData = 16;
  Type[0] = 0;
  AliasInterfaceGuid = 0;
  v26 = RegQueryValueExW(phkDeviceInterface, L"InterfaceLink", 0, Type, (LPBYTE)&AliasInterfaceGuid, &cbData);
  RegCloseKey(phkDeviceInterface);
  if ( v26 )
    goto LABEL_34;
  pulLength = 1;
  LOWORD(pulLen) = 0;
  if ( CM_Get_Device_Interface_AliasW(i, &AliasInterfaceGuid, (LPWSTR)&pulLen, &pulLength, 0) != 26 )
    goto LABEL_34;
  v50 = (WCHAR *)operator new[](saturated_mul(++pulLength, 2u));
  v9 = v50;
  if ( v50 )
  {
    Device_Interface_AliasW = CM_Get_Device_Interface_AliasW(i, &AliasInterfaceGuid, v50, &pulLength, 0);
    if ( !Device_Interface_AliasW )
    {
      i = v9;
      goto LABEL_35;
    }
    v45 = CM_MapCrToWin32Err(Device_Interface_AliasW, 0xDu);
    v16 = v45;
    if ( v45 > 0 )
      v16 = (unsigned __int16)v45 | 0x80070000;
    CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 640);
    if ( v16 < 0 )
    {
      v46 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v46 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v46->m_fEnabled )
      {
        v47 = CallStackTracing::GetThreadRelativeContext(v46);
        if ( v47->m_result != v16 )
          CallStackContext::TraceFailure(v47, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 640, v16);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids, v59, v16);
      CallStackScopeTrace::~CallStackScopeTrace(&v53);
LABEL_97:
      operator delete(v9);
      return (unsigned int)v16;
    }
    CallStackScopeTrace::~CallStackScopeTrace(&v53);
LABEL_34:
    if ( !i )
    {
LABEL_8:
      CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 663);
      v15 = CallStackTracing::s_wpInstance;
      v16 = -2147024637;
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
        v17 = CallStackTracing::GetThreadRelativeContext(v15);
        if ( v17->m_result != -2147024637 )
          CallStackContext::TraceFailure(v17, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 663, -2147024637);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids,
          v59,
          -2147024637);
      CallStackScopeTrace::~CallStackScopeTrace(&v53);
LABEL_15:
      if ( !v9 )
        return (unsigned int)v16;
      goto LABEL_97;
    }
LABEL_35:
    v27 = i;
    v28 = 2147483646;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v28;
    }
    while ( v28 );
    v16 = v28 == 0 ? 0x80070057 : 0;
    v29 = (2147483646 - v28) & -(__int64)(v28 != 0);
    if ( v28 )
    {
      v30 = (unsigned __int16 *)operator new[](saturated_mul(v29 + 1, 2u));
      v31 = v60;
      *v60 = v30;
      if ( v30 )
      {
        StringCchCopyW(v30, v29 + 1, i);
        v16 = 0;
        for ( k = 0; k < v29; (*v31)[v33] = v34 )
        {
          v33 = k;
          v34 = o_towlower_0((*v31)[k++]);
        }
      }
      else
      {
        v16 = -2147024882;
      }
    }
    goto LABEL_15;
  }
  CallStackScopeTrace::CallStackScopeTrace(&v53, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 646);
  v48 = CallStackTracing::s_wpInstance;
  v16 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v48 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v48 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v48->m_fEnabled )
  {
    v49 = CallStackTracing::GetThreadRelativeContext(v48);
    if ( v49->m_result != -2147024882 )
      CallStackContext::TraceFailure(v49, "MF::DeviceEnumeration::CEnumPnp::GetDevicePath", 646, -2147024882);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v41 = v59;
    v38 = 29;
    ulFlags = -2147024882;
    goto LABEL_107;
  }
LABEL_46:
  CallStackScopeTrace::~CallStackScopeTrace(&v53);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18006e628  push    rbp
0x18006e62a  push    rbx
0x18006e62b  push    rsi
0x18006e62c  push    rdi
0x18006e62d  push    r12
0x18006e62f  push    r13
0x18006e631  push    r14
0x18006e633  push    r15
0x18006e635  lea     rbp, [rsp-1Fh]
0x18006e63a  sub     rsp, 98h
0x18006e641  mov     rax, cs:__security_cookie
0x18006e648  xor     rax, rsp
0x18006e64b  mov     [rbp+57h+var_48], rax
0x18006e64f  mov     rax, [r8]
0x18006e652  lea     r15, aMfDeviceenumer_2; "MF::DeviceEnumeration::CEnumPnp::GetDev"...
0x18006e659  xor     esi, esi
0x18006e65b  mov     qword ptr [rbp+57h+Type], r8
0x18006e65f  lea     r13, WPP_f07109cb91a038d7dc23b63a8bb53f63_Traceguids
0x18006e666  mov     r14, r9
0x18006e669  mov     r12, rcx
0x18006e66c  mov     [rbp+57h+var_70], rdx
0x18006e670  movups  xmm0, xmmword ptr [rax]
0x18006e673  lea     edi, [rsi+0Dh]
0x18006e676  mov     [rbp+57h+var_78], rcx
0x18006e67a  mov     [rbp+57h+pulLength], esi
0x18006e67d  movdqu  xmmword ptr [rbp+57h+InterfaceClassGuid.Data1], xmm0
0x18006e682  cmp     [r9+8], rsi
0x18006e686  jz      loc_18006E75E
0x18006e68c  mov     r13d, [r14]
0x18006e68f  mov     r15, rsi
0x18006e692  mov     eax, esi
0x18006e694  xor     ecx, ecx
0x18006e696  mov     rsi, [r14+8]
0x18006e69a  cmp     [rsi], cx
0x18006e69d  jz      short loc_18006E6C6
0x18006e69f  lea     r12d, [rax+1]
0x18006e6a3  cmp     eax, r13d
0x18006e6a6  jnb     loc_18006E809
0x18006e6ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e6b0  inc     rax
0x18006e6b3  cmp     [rsi+rax*2], cx
0x18006e6b7  jnz     short loc_18006E6B0
0x18006e6b9  lea     rsi, [rsi+rax*2]
0x18006e6bd  mov     eax, r12d
0x18006e6c0  add     rsi, 2
0x18006e6c4  jmp     short loc_18006E69A
0x18006e6c6  xor     r13d, r13d
0x18006e6c9  lea     r12, aMfDeviceenumer_2; "MF::DeviceEnumeration::CEnumPnp::GetDev"...
0x18006e6d0  mov     ebx, 297h
0x18006e6d5  lea     rcx, [rbp+57h+var_A0]; this
0x18006e6d9  mov     r8d, ebx; int
0x18006e6dc  mov     rdx, r12; char *
0x18006e6df  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e6e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006e6eb  mov     edi, 80070103h
0x18006e6f0  test    rcx, rcx
0x18006e6f3  jz      loc_18006EB0B
0x18006e6f9  cmp     [rcx+8], r13b
0x18006e6fd  jz      short loc_18006E71D
0x18006e6ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e704  cmp     [rax+7CCh], edi
0x18006e70a  jz      short loc_18006E71D
0x18006e70c  mov     r9d, edi; int
0x18006e70f  mov     r8d, ebx; int
0x18006e712  mov     rdx, r12; char *
0x18006e715  mov     rcx, rax; this
0x18006e718  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e71d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e724  jnb     loc_18006EF9E
0x18006e72a  lea     rcx, [rbp+57h+var_A0]; this
0x18006e72e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006e733  test    r15, r15
0x18006e736  jnz     loc_18006ED60
0x18006e73c  mov     eax, edi
0x18006e73e  mov     rcx, [rbp+57h+var_48]
0x18006e742  xor     rcx, rsp; StackCookie
0x18006e745  call    __security_check_cookie
0x18006e74a  add     rsp, 98h
0x18006e751  pop     r15
0x18006e753  pop     r14
0x18006e755  pop     r13
0x18006e757  pop     r12
0x18006e759  pop     rdi
0x18006e75a  pop     rsi
0x18006e75b  pop     rbx
0x18006e75c  pop     rbp
0x18006e75d  retn
0x18006e75e  xor     r9d, r9d; ulFlags
0x18006e761  mov     [rbp+57h+pulLen], esi
0x18006e764  xor     r8d, r8d; pDeviceID
0x18006e767  lea     rdx, [rbp+57h+InterfaceClassGuid]; InterfaceClassGuid
0x18006e76b  lea     rcx, [rbp+57h+pulLen]; pulLen
0x18006e76f  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x18006e775  mov     ebx, eax
0x18006e777  test    eax, eax
0x18006e779  jnz     loc_18006EA90
0x18006e77f  mov     ecx, [rbp+57h+pulLen]
0x18006e782  lea     eax, [rbx+2]
0x18006e785  add     ecx, 2
0x18006e788  mul     rcx
0x18006e78b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006e792  cmovb   rax, rcx
0x18006e796  mov     rcx, rax; unsigned __int64
0x18006e799  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006e79e  mov     r8d, 1DDh; int
0x18006e7a4  mov     [r14+8], rax
0x18006e7a8  mov     rdx, r15; char *
0x18006e7ab  lea     rcx, [rbp+57h+var_A0]; this
0x18006e7af  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e7b4  mov     rdx, [r14+8]
0x18006e7b8  test    rdx, rdx
0x18006e7bb  jz      loc_18006E9EF
0x18006e7c1  mov     ecx, [rbp+57h+pulLen]
0x18006e7c4  mov     [rsp+0D0h+ulFlags], esi; ulFlags
0x18006e7c8  mov     [rdx+rcx*2], si
0x18006e7cc  xor     edx, edx; pDeviceID
0x18006e7ce  mov     eax, [rbp+57h+pulLen]
0x18006e7d1  mov     rcx, [r14+8]
0x18006e7d5  inc     eax
0x18006e7d7  mov     [rcx+rax*2], si
0x18006e7db  lea     rcx, [rbp+57h+InterfaceClassGuid]; InterfaceClassGuid
0x18006e7df  mov     r9d, [rbp+57h+pulLen]; BufferLen
0x18006e7e3  mov     r8, [r14+8]; Buffer
0x18006e7e7  call    cs:__imp_CM_Get_Device_Interface_ListW
0x18006e7ed  mov     ebx, eax
0x18006e7ef  test    eax, eax
0x18006e7f1  jnz     loc_18006EA38
0x18006e7f7  lea     rcx, [rbp+57h+var_A0]; this
0x18006e7fb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006e800  mov     r8, qword ptr [rbp+57h+Type]
0x18006e804  jmp     loc_18006E68C
0x18006e809  mov     [r14], r12d
0x18006e80c  mov     ebx, 1
0x18006e811  mov     edi, ebx
0x18006e813  mov     rax, [r8+rdi*8]
0x18006e817  test    rax, rax
0x18006e81a  jz      short loc_18006E883
0x18006e81c  movups  xmm0, xmmword ptr [rax]
0x18006e81f  mov     word ptr [rbp+57h+pulLen], cx
0x18006e823  lea     r9, [rbp+57h+pulLength]; pulLength
0x18006e827  mov     [rsp+0D0h+ulFlags], ecx; ulFlags
0x18006e82b  lea     r8, [rbp+57h+pulLen]; pszAliasDeviceInterface
0x18006e82f  lea     rdx, [rbp+57h+AliasInterfaceGuid]; AliasInterfaceGuid
0x18006e833  mov     [rbp+57h+pulLength], 1
0x18006e83a  mov     rcx, rsi; pszDeviceInterface
0x18006e83d  movdqu  xmmword ptr [rbp+57h+AliasInterfaceGuid.Data1], xmm0
0x18006e842  call    cs:__imp_CM_Get_Device_Interface_AliasW
0x18006e848  cmp     eax, 1Ah
0x18006e84b  jz      loc_18006EA2B
0x18006e851  mov     r8d, 21Fh; int
0x18006e857  lea     rdx, aMfDeviceenumer_2; "MF::DeviceEnumeration::CEnumPnp::GetDev"...
0x18006e85e  lea     rcx, [rbp+57h+var_A0]; this
0x18006e862  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e867  cmp     cs:byte_1801FD28B, 20h ; ' '
0x18006e86e  jnb     loc_18006EEA5
0x18006e874  lea     rcx, [rbp+57h+var_A0]; this
0x18006e878  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006e87d  mov     r8, qword ptr [rbp+57h+Type]
0x18006e881  xor     ecx, ecx
0x18006e883  cmp     [r8+rdi*8], rcx
0x18006e887  jnz     loc_18006E6AC
0x18006e88d  lea     r12, aMfDeviceenumer_2; "MF::DeviceEnumeration::CEnumPnp::GetDev"...
0x18006e894  mov     r8d, 22Dh; int
0x18006e89a  mov     rdx, r12; char *
0x18006e89d  lea     rcx, [rbp+57h+var_A0]; this
0x18006e8a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e8a6  cmp     cs:byte_1801FD28B, 20h ; ' '
0x18006e8ad  jnb     loc_18006EEDD
0x18006e8b3  lea     rcx, [rbp+57h+var_A0]; this
0x18006e8b7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006e8bc  xor     r13d, r13d
0x18006e8bf  lea     r9, [rbp+57h+phkDeviceInterface]; phkDeviceInterface
0x18006e8c3  mov     edx, 20019h; samDesired
0x18006e8c8  mov     [rbp+57h+phkDeviceInterface], r13
0x18006e8cc  mov     rcx, rsi; pszDeviceInterface
0x18006e8cf  mov     [rsp+0D0h+ulFlags], r13d; ulFlags
0x18006e8d4  lea     r8d, [r13+1]; Disposition
0x18006e8d8  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18006e8de  test    eax, eax
0x18006e8e0  jnz     short loc_18006E932
0x18006e8e2  mov     rcx, [rbp+57h+phkDeviceInterface]; hKey
0x18006e8e6  lea     rax, [rbp+57h+cbData]
0x18006e8ea  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18006e8ef  lea     r9, [rbp+57h+Type]; lpType
0x18006e8f3  lea     rax, [rbp+57h+AliasInterfaceGuid]
0x18006e8f7  mov     [rbp+57h+cbData], 10h
0x18006e8fe  xorps   xmm0, xmm0
0x18006e901  mov     qword ptr [rsp+0D0h+ulFlags], rax; lpData
0x18006e906  xor     r8d, r8d; lpReserved
0x18006e909  mov     [rbp+57h+Type], r13d
0x18006e90d  lea     rdx, aInterfacelink; "InterfaceLink"
0x18006e914  movups  xmmword ptr [rbp+57h+AliasInterfaceGuid.Data1], xmm0
0x18006e918  call    cs:__imp_RegQueryValueExW
0x18006e91e  mov     rcx, [rbp+57h+phkDeviceInterface]; hKey
0x18006e922  mov     ebx, eax
0x18006e924  call    cs:__imp_RegCloseKey
0x18006e92a  test    ebx, ebx
0x18006e92c  jz      loc_18006EF0B
0x18006e932  test    rsi, rsi
0x18006e935  jz      loc_18006E6D0
0x18006e93b  mov     edx, 7FFFFFFEh
0x18006e940  mov     rax, rsi
0x18006e943  mov     ecx, edx
0x18006e945  cmp     [rax], r13w
0x18006e949  jz      short loc_18006E955
0x18006e94b  add     rax, 2
0x18006e94f  sub     rcx, 1
0x18006e953  jnz     short loc_18006E945
0x18006e955  mov     rax, rcx
0x18006e958  neg     rax
0x18006e95b  mov     rax, rcx
0x18006e95e  sbb     edi, edi
0x18006e960  sub     rdx, rcx
0x18006e963  not     edi
0x18006e965  and     edi, 80070057h
0x18006e96b  neg     rax
0x18006e96e  sbb     r14, r14
0x18006e971  and     r14, rdx
0x18006e974  test    rcx, rcx
0x18006e977  jz      loc_18006E733
0x18006e97d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006e984  lea     rbx, [r14+1]
0x18006e988  mov     eax, 2
0x18006e98d  mul     rbx
0x18006e990  cmovb   rax, rcx
0x18006e994  mov     rcx, rax; unsigned __int64
0x18006e997  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006e99c  mov     r12, [rbp+57h+var_70]
0x18006e9a0  mov     [r12], rax
0x18006e9a4  test    rax, rax
0x18006e9a7  jz      loc_18006EF94
0x18006e9ad  mov     r8, rsi; unsigned __int16 *
0x18006e9b0  mov     rdx, rbx; unsigned __int64
0x18006e9b3  mov     rcx, rax; unsigned __int16 *
0x18006e9b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006e9bb  mov     edi, r13d
0x18006e9be  mov     esi, r13d
0x18006e9c1  test    r14, r14
0x18006e9c4  jz      loc_18006E733
0x18006e9ca  mov     rcx, [r12]
0x18006e9ce  mov     ebx, esi
0x18006e9d0  movzx   ecx, word ptr [rcx+rbx*2]
0x18006e9d4  call    _o_towlower_0
0x18006e9d9  mov     rcx, [r12]
0x18006e9dd  inc     esi
0x18006e9df  mov     [rcx+rbx*2], ax
0x18006e9e3  mov     eax, esi
0x18006e9e5  cmp     rax, r14
0x18006e9e8  jb      short loc_18006E9CA
0x18006e9ea  jmp     loc_18006E733
0x18006e9ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006e9f6  mov     ebx, 8007000Eh
0x18006e9fb  mov     edi, ebx
0x18006e9fd  test    rcx, rcx
0x18006ea00  jz      loc_18006EB51
0x18006ea06  cmp     [rcx+8], sil
0x18006ea0a  jnz     loc_18006EC23
0x18006ea10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ea17  jnb     loc_18006EE57
0x18006ea1d  lea     rcx, [rbp+57h+var_A0]; this
0x18006ea21  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006ea26  jmp     loc_18006E73C
0x18006ea2b  mov     r8, qword ptr [rbp+57h+Type]
0x18006ea2f  inc     ebx
0x18006ea31  xor     ecx, ecx
0x18006ea33  jmp     loc_18006E811
0x18006ea38  cmp     cs:byte_1801FD28B, 1
0x18006ea3f  jnb     loc_18006EE65
0x18006ea45  mov     edx, edi; DefaultErr
0x18006ea47  mov     ecx, ebx; CmReturnCode
0x18006ea49  call    cs:__imp_CM_MapCrToWin32Err
0x18006ea4f  mov     edi, eax
0x18006ea51  test    eax, eax
0x18006ea53  jle     short loc_18006EA5E
0x18006ea55  movzx   edi, ax
0x18006ea58  or      edi, 80070000h
0x18006ea5e  test    edi, edi
0x18006ea60  jns     loc_18006E7F7
0x18006ea66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006ea6d  test    rcx, rcx
0x18006ea70  jz      loc_18006EB97
0x18006ea76  cmp     [rcx+8], sil
0x18006ea7a  jnz     loc_18006EC4D
0x18006ea80  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ea87  jb      short loc_18006EA1D
0x18006ea89  mov     edx, 17h
0x18006ea8e  jmp     short loc_18006EAFC
0x18006ea90  mov     r8d, 1F4h; int
0x18006ea96  lea     rcx, [rbp+57h+var_A0]; this
0x18006ea9a  mov     rdx, r15; char *
0x18006ea9d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006eaa2  cmp     cs:byte_1801FD28B, 1
0x18006eaa9  jnb     loc_18006EE85
0x18006eaaf  mov     edx, edi; DefaultErr
0x18006eab1  mov     ecx, ebx; CmReturnCode
0x18006eab3  call    cs:__imp_CM_MapCrToWin32Err
0x18006eab9  mov     edi, eax
0x18006eabb  test    eax, eax
0x18006eabd  jle     short loc_18006EAC8
0x18006eabf  movzx   edi, ax
  ... truncated ...
```
