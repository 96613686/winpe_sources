# CRdpPipeGfxPlugin::StartPipeMgrLite(void)

- ea: `0x18005cf5c`
- end: `0x18005d734`
- name: `?StartPipeMgrLite@CRdpPipeGfxPlugin@@QEAAJXZ`
- size: `2008`
- prototype: `__int64 __fastcall(CRdpPipeGfxPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180059d20`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180012200`
- `0x18005a2f8`
- `0x18005cb40`
- `0x18005cf5c`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005d24f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005d3bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005d24f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005d3bd`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005cfda`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005cfda`
- `OLEAUT32!__imp_VariantInit` at `0x18005cfad`
- `OLEAUT32!__imp_VariantInit` at `0x18005cfb7`
- `OLEAUT32!__imp_VariantInit` at `0x18005cfc1`
- `OLEAUT32!__imp_VariantInit` at `0x18005cfad`
- `OLEAUT32!__imp_VariantInit` at `0x18005cfb7`
- `OLEAUT32!__imp_VariantInit` at `0x18005cfc1`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6e4`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6ee`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6f8`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6e4`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6ee`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6f8`

## string_xrefs

- `0x18005d06b`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005d1a6`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005d314`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005d481`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005d5f3`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005d68c`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005d047`: `Failed to open property store`
- `0x18005d2b2`: `Failed to get property RDP_PROPERTY_PROTOCOL_NAME`
- `0x18005d2ed`: `RDP_PROPERTY_PROTOCOL_NAME is not set properly`
- `0x18005d382`: `Failed to initialize PKEY_ProtocolName property`
- `0x18005d3d6`: `Failed to set PKEY_ProtocolName property`
- `0x18005d591`: `Failed to retrieve PKEY_Caps_Support_Monitor_Config_Channel property`
- `0x18005d5cc`: `PKEY_Caps_Support_Monitor_Config_Channel is not set properly`

## pseudocode

```c
__int64 __fastcall CRdpPipeGfxPlugin::StartPipeMgrLite(CRdpPipeGfxPlugin *this)
{
  __int64 v2; // rbx
  int inited; // edi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rsi
  int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  char *v10; // rdx
  const char **v11; // rax
  const char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  const char **v17; // [rsp+30h] [rbp-69h]
  const char **v18; // [rsp+40h] [rbp-59h]
  const char **v19; // [rsp+48h] [rbp-51h]
  const char *v20; // [rsp+50h] [rbp-49h] BYREF
  const char *v21; // [rsp+58h] [rbp-41h] BYREF
  const char *v22; // [rsp+60h] [rbp-39h] BYREF
  const char *v23; // [rsp+68h] [rbp-31h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-11h] BYREF
  VARIANTARG v26; // [rsp+A0h] [rbp+7h] BYREF
  VARIANTARG v27; // [rsp+B8h] [rbp+1Fh] BYREF
  char *v28; // [rsp+100h] [rbp+67h] BYREF
  int v29; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+110h] [rbp+77h] BYREF
  __int64 v31; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = 0;
  v31 = 0;
  v30 = 0;
  inited = -2147467259;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v26, 0, sizeof(v26));
  memset(&v27, 0, sizeof(v27));
  memset(&pvar, 0, sizeof(pvar));
  VariantInit(&pvarg);
  VariantInit(&v26);
  VariantInit(&v27);
  v28 = (char *)this + 160;
  if ( *((_DWORD *)this + 42) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 20), v4, v5);
  if ( *((_QWORD *)this + 17) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v31, v4, v5);
    v31 = *((_QWORD *)this + 17);
    v2 = v31;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v31);
    v6 = v2;
  }
  else
  {
    v6 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v28);
  if ( v6 )
  {
    inited = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 24LL))(v6, &v30);
    if ( inited < 0 )
    {
      v9 = dword_1801B76C8;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_61;
      LODWORD(v28) = 1021;
      v20 = "Failed to open property store";
      v10 = &byte_18019A39F;
      v21 = "StartPipeMgrLite";
      v22 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v23 = "Error HResult failed";
      v19 = &v20;
      v18 = &v21;
      v17 = &v22;
      v11 = &v23;
      goto LABEL_60;
    }
    pvar.lVal = *((_DWORD *)this + 50);
    pvar.vt = 19;
    inited = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)v30 + 48LL))(
               v30,
               PKEY_Session_Id,
               &pvar);
    if ( inited < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_61;
      v12 = "Failed to set PKEY_Session_Id property";
      LODWORD(v28) = 1033;
      v10 = &byte_18019A34F;
      goto LABEL_59;
    }
    inited = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 13) + 24LL))(
               *((_QWORD *)this + 13),
               L"IddDeviceInstance",
               &pvarg);
    if ( inited < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_61;
      v12 = "Failed to get property CONN_PROPERTY_IDD_DEVICE_INSTANCE";
      LODWORD(v28) = 1039;
      v10 = &byte_18019A2FF;
      goto LABEL_59;
    }
    if ( pvarg.vt == 8 )
    {
      inited = InitPropVariantFromString(pvarg.bstrVal, &pvar);
      if ( inited < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_61;
        v12 = "Failed to initialize device instance property";
        LODWORD(v28) = 1047;
        v10 = &byte_18019A25F;
        goto LABEL_59;
      }
      inited = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)v30 + 48LL))(
                 v30,
                 PKEY_IddDeviceInstance,
                 &pvar);
      PropVariantClear((PROPVARIANT *)&pvar);
      if ( inited < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_61;
        v12 = "Failed to set PKEY_IddDeviceInstance property";
        LODWORD(v28) = 1055;
        v10 = &byte_18019A20F;
        goto LABEL_59;
      }
      inited = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 13) + 24LL))(
                 *((_QWORD *)this + 13),
                 L"RDP::TerminalName",
                 &v26);
      if ( inited < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_61;
        v12 = "Failed to get property RDP_PROPERTY_PROTOCOL_NAME";
        LODWORD(v28) = 1064;
        v10 = &byte_18019A1BF;
        goto LABEL_59;
      }
      if ( v26.vt == 8 )
      {
        inited = InitPropVariantFromString(v26.bstrVal, &pvar);
        if ( inited < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_61;
          v12 = "Failed to initialize PKEY_ProtocolName property";
          LODWORD(v28) = 1072;
          v10 = &byte_18019A11F;
          goto LABEL_59;
        }
        inited = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)v30 + 48LL))(
                   v30,
                   PKEY_ProtocolName,
                   &pvar);
        PropVariantClear((PROPVARIANT *)&pvar);
        if ( inited < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_61;
          v12 = "Failed to set PKEY_ProtocolName property";
          LODWORD(v28) = 1079;
          v10 = &byte_18019A0CF;
          goto LABEL_59;
        }
        inited = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 13) + 24LL))(
                   *((_QWORD *)this + 13),
                   L"ConnectionID",
                   &v27);
        if ( inited < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_61;
          v12 = "Failed to get property CONN_PROPERTY_CONNECTION_ID";
          LODWORD(v28) = 1088;
          v10 = &byte_18019A07F;
          goto LABEL_59;
        }
        if ( v27.vt == 19 )
        {
          pvar.lVal = v27.lVal;
          pvar.vt = 19;
          inited = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)v30 + 48LL))(
                     v30,
                     PKEY_ConnectionId,
                     &pvar);
          if ( inited < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              goto LABEL_61;
            v12 = "Failed to set PKEY_ConnectionId property";
            LODWORD(v28) = 1102;
            v10 = &byte_180199FDF;
            goto LABEL_59;
          }
          inited = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, 0);
          if ( inited < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              goto LABEL_61;
            v12 = "Failed to start light Rdp graphics pipeline";
            LODWORD(v28) = 1108;
            v10 = &byte_180199F8F;
            goto LABEL_59;
          }
          inited = (*(__int64 (__fastcall **)(__int64, __int64 *, struct tagPROPVARIANT *))(*(_QWORD *)v30 + 40LL))(
                     v30,
                     PKEY_Caps_Support_Monitor_Config_Channel,
                     &pvar);
          if ( inited < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              goto LABEL_61;
            v12 = "Failed to retrieve PKEY_Caps_Support_Monitor_Config_Channel property";
            LODWORD(v28) = 1117;
            v10 = &byte_180199F3F;
            goto LABEL_59;
          }
          if ( pvar.vt == 11 )
          {
            if ( !pvar.iVal )
            {
              inited = CRdpPipeGfxPlugin::SetInitialMonitorLayout(this);
              if ( inited < 0 && (unsigned int)dword_1801B76C8 > 2 )
              {
                v12 = "Failed to set initial monitor layout";
                LODWORD(v28) = 1127;
                v10 = &byte_180199E9F;
LABEL_59:
                v23 = v12;
                v22 = "StartPipeMgrLite";
                v21 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
                v20 = "Error HResult failed";
                v19 = &v23;
                v18 = &v22;
                v17 = &v21;
                v11 = &v20;
LABEL_60:
                v29 = inited;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v9,
                  (_DWORD)v10,
                  v7,
                  v8,
                  (__int64)v11,
                  (__int64)&v29,
                  (__int64)v17,
                  (__int64)&v28,
                  (__int64)v18,
                  (__int64)v19);
              }
            }
          }
          else
          {
            inited = -2147418113;
            if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              LODWORD(v28) = 1122;
              v23 = "PKEY_Caps_Support_Monitor_Config_Channel is not set properly";
              v29 = -2147418113;
              v22 = "StartPipeMgrLite";
              v21 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
              v20 = "Error condition failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                -2147418113,
                (unsigned int)&byte_180199EEF,
                v7,
                v8,
                (__int64)&v20,
                (__int64)&v29,
                (__int64)&v21,
                (__int64)&v28,
                (__int64)&v22,
                (__int64)&v23);
            }
          }
        }
        else
        {
          inited = -2147418113;
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v28) = 1093;
            v23 = "CONN_PROPERTY_CONNECTION_ID is not set properly";
            v29 = -2147418113;
            v22 = "StartPipeMgrLite";
            v21 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
            v20 = "Error condition failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              -2147418113,
              (unsigned int)&byte_18019A02F,
              v7,
              v8,
              (__int64)&v20,
              (__int64)&v29,
              (__int64)&v21,
              (__int64)&v28,
              (__int64)&v22,
              (__int64)&v23);
          }
        }
      }
      else
      {
        inited = -2147418113;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v28) = 1069;
          v23 = "RDP_PROPERTY_PROTOCOL_NAME is not set properly";
          v29 = -2147418113;
          v22 = "StartPipeMgrLite";
          v21 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
          v20 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147418113,
            (unsigned int)&byte_18019A16F,
            v7,
            v8,
            (__int64)&v20,
            (__int64)&v29,
            (__int64)&v21,
            (__int64)&v28,
            (__int64)&v22,
            (__int64)&v23);
        }
      }
    }
    else
    {
      inited = -2147418113;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v28) = 1044;
        v23 = "IDD device instance is not set properly";
        v29 = -2147418113;
        v22 = "StartPipeMgrLite";
        v21 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
        v20 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147418113,
          (unsigned int)&byte_18019A2AF,
          v7,
          v8,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v21,
          (__int64)&v28,
          (__int64)&v22,
          (__int64)&v23);
      }
    }
  }
LABEL_61:
  VariantClear(&pvarg);
  VariantClear(&v26);
  VariantClear(&v27);
  v15 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v31, v13, v14);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18005cf5c  push    rbp
0x18005cf5e  push    rbx
0x18005cf5f  push    rsi
0x18005cf60  push    rdi
0x18005cf61  push    r14
0x18005cf63  lea     rbp, [rsp-37h]
0x18005cf68  sub     rsp, 0D0h
0x18005cf6f  xor     eax, eax
0x18005cf71  xorps   xmm0, xmm0
0x18005cf74  xorps   xmm1, xmm1
0x18005cf77  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18005cf7b  mov     r14, rcx
0x18005cf7e  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18005cf82  xor     ebx, ebx
0x18005cf84  mov     qword ptr [rbp+57h+var_38+10h], rax
0x18005cf88  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18005cf8c  mov     [rbp+57h+arg_18], rbx
0x18005cf90  mov     [rbp+57h+arg_10], rbx
0x18005cf94  mov     edi, 80004005h
0x18005cf99  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18005cf9d  mov     [rbp+57h+var_70], rax
0x18005cfa1  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x18005cfa5  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18005cfa9  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x18005cfad  call    cs:__imp_VariantInit
0x18005cfb3  lea     rcx, [rbp+57h+var_50]; pvarg
0x18005cfb7  call    cs:__imp_VariantInit
0x18005cfbd  lea     rcx, [rbp+57h+var_38]; pvarg
0x18005cfc1  call    cs:__imp_VariantInit
0x18005cfc7  lea     rcx, [r14+0A0h]
0x18005cfce  mov     [rbp+57h+arg_0], rcx
0x18005cfd2  cmp     [rcx+8], ebx
0x18005cfd5  jz      short loc_18005CFE0
0x18005cfd7  mov     rcx, [rcx]
0x18005cfda  call    cs:__imp_PAL_System_CritSecEnter
0x18005cfe0  cmp     [r14+88h], rbx
0x18005cfe7  jnz     short loc_18005CFED
0x18005cfe9  xor     esi, esi
0x18005cfeb  jmp     short loc_18005D00D
0x18005cfed  lea     rcx, [rbp+57h+arg_18]
0x18005cff1  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005cff6  mov     rbx, [r14+88h]
0x18005cffd  lea     rcx, [rbp+57h+arg_18]
0x18005d001  mov     [rbp+57h+arg_18], rbx
0x18005d005  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18005d00a  mov     rsi, rbx
0x18005d00d  lea     rcx, [rbp+57h+arg_0]; this
0x18005d011  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18005d016  test    rsi, rsi
0x18005d019  jz      loc_18005D6E0
0x18005d01f  mov     rax, [rsi]
0x18005d022  lea     rdx, [rbp+57h+arg_10]
0x18005d026  mov     rcx, rsi
0x18005d029  mov     rax, [rax+18h]
0x18005d02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d032  mov     edi, eax
0x18005d034  test    eax, eax
0x18005d036  jns     short loc_18005D0B7
0x18005d038  mov     ecx, cs:dword_1801B76C8
0x18005d03e  cmp     ecx, 2
0x18005d041  jbe     loc_18005D6E0
0x18005d047  lea     rax, aFailedToOpenPr; "Failed to open property store"
0x18005d04e  mov     dword ptr [rbp+57h+arg_0], 3FDh
0x18005d055  mov     [rbp+57h+var_A0], rax
0x18005d059  lea     rdx, byte_18019A39F
0x18005d060  lea     rax, aStartpipemgrli; "StartPipeMgrLite"
0x18005d067  mov     [rbp+57h+var_98], rax
0x18005d06b  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005d072  mov     [rbp+57h+var_90], rax
0x18005d076  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18005d07d  mov     [rbp+57h+var_88], rax
0x18005d081  lea     rax, [rbp+57h+var_A0]
0x18005d085  mov     [rsp+0F0h+var_A8], rax
0x18005d08a  lea     rax, [rbp+57h+var_98]
0x18005d08e  mov     [rsp+0F0h+var_B0], rax
0x18005d093  lea     rax, [rbp+57h+arg_0]
0x18005d097  mov     [rsp+0F0h+var_B8], rax
0x18005d09c  lea     rax, [rbp+57h+var_90]
0x18005d0a0  mov     [rsp+0F0h+var_C0], rax
0x18005d0a5  lea     rax, [rbp+57h+arg_8]
0x18005d0a9  mov     [rsp+0F0h+var_C8], rax
0x18005d0ae  lea     rax, [rbp+57h+var_88]
0x18005d0b2  jmp     loc_18005D6D3
0x18005d0b7  mov     eax, [r14+0C8h]
0x18005d0be  lea     r8, [rbp+57h+pvar]
0x18005d0c2  mov     rcx, [rbp+57h+arg_10]
0x18005d0c6  lea     rdx, PKEY_Session_Id
0x18005d0cd  mov     dword ptr [rbp+57h+pvar+8], eax
0x18005d0d0  mov     esi, 13h
0x18005d0d5  mov     word ptr [rbp+57h+pvar], si
0x18005d0d9  mov     rax, [rcx]
0x18005d0dc  mov     rax, [rax+30h]
0x18005d0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0e5  mov     edi, eax
0x18005d0e7  test    eax, eax
0x18005d0e9  jns     short loc_18005D114
0x18005d0eb  mov     eax, cs:dword_1801B76C8
0x18005d0f1  cmp     eax, 2
0x18005d0f4  jbe     loc_18005D6E0
0x18005d0fa  lea     rax, aFailedToSetPke_2; "Failed to set PKEY_Session_Id property"
0x18005d101  mov     dword ptr [rbp+57h+arg_0], 409h
0x18005d108  lea     rdx, byte_18019A34F
0x18005d10f  jmp     loc_18005D67D
0x18005d114  mov     rcx, [r14+68h]
0x18005d118  lea     r8, [rbp+57h+pvarg]
0x18005d11c  lea     rdx, aIdddeviceinsta; "IddDeviceInstance"
0x18005d123  mov     rax, [rcx]
0x18005d126  mov     rax, [rax+18h]
0x18005d12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d12f  mov     edi, eax
0x18005d131  test    eax, eax
0x18005d133  jns     short loc_18005D15E
0x18005d135  mov     eax, cs:dword_1801B76C8
0x18005d13b  cmp     eax, 2
0x18005d13e  jbe     loc_18005D6E0
0x18005d144  lea     rax, aFailedToGetPro_0; "Failed to get property CONN_PROPERTY_ID"...
0x18005d14b  mov     dword ptr [rbp+57h+arg_0], 40Fh
0x18005d152  lea     rdx, byte_18019A2FF
0x18005d159  jmp     loc_18005D67D
0x18005d15e  cmp     word ptr [rbp+57h+pvarg], 8
0x18005d163  jz      loc_18005D1F2
0x18005d169  mov     eax, cs:dword_1801B76C8
0x18005d16f  mov     ecx, 8000FFFFh
0x18005d174  mov     edi, ecx
0x18005d176  cmp     eax, 2
0x18005d179  jbe     loc_18005D6E0
0x18005d17f  lea     rax, aIddDeviceInsta; "IDD device instance is not set properly"
0x18005d186  mov     dword ptr [rbp+57h+arg_0], 414h
0x18005d18d  mov     [rbp+57h+var_88], rax
0x18005d191  lea     rdx, byte_18019A2AF
0x18005d198  lea     rax, aStartpipemgrli; "StartPipeMgrLite"
0x18005d19f  mov     [rbp+57h+arg_8], ecx
0x18005d1a2  mov     [rbp+57h+var_90], rax
0x18005d1a6  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005d1ad  mov     [rbp+57h+var_98], rax
0x18005d1b1  lea     rax, aErrorCondition; "Error condition failed"
0x18005d1b8  mov     [rbp+57h+var_A0], rax
0x18005d1bc  lea     rax, [rbp+57h+var_88]
0x18005d1c0  mov     [rsp+0F0h+var_A8], rax
0x18005d1c5  lea     rax, [rbp+57h+var_90]
0x18005d1c9  mov     [rsp+0F0h+var_B0], rax
0x18005d1ce  lea     rax, [rbp+57h+arg_0]
0x18005d1d2  mov     [rsp+0F0h+var_B8], rax
0x18005d1d7  lea     rax, [rbp+57h+var_98]
0x18005d1db  mov     [rsp+0F0h+var_C0], rax
0x18005d1e0  lea     rax, [rbp+57h+arg_8]
0x18005d1e4  mov     [rsp+0F0h+var_C8], rax
0x18005d1e9  lea     rax, [rbp+57h+var_A0]
0x18005d1ed  jmp     loc_18005D6D6
0x18005d1f2  mov     rcx, qword ptr [rbp+57h+pvarg+8]; Source
0x18005d1f6  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18005d1fa  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18005d1ff  mov     edi, eax
0x18005d201  test    eax, eax
0x18005d203  jns     short loc_18005D22E
0x18005d205  mov     eax, cs:dword_1801B76C8
0x18005d20b  cmp     eax, 2
0x18005d20e  jbe     loc_18005D6E0
0x18005d214  lea     rax, aFailedToInitia_25; "Failed to initialize device instance pr"...
0x18005d21b  mov     dword ptr [rbp+57h+arg_0], 417h
0x18005d222  lea     rdx, byte_18019A25F
0x18005d229  jmp     loc_18005D67D
0x18005d22e  mov     rcx, [rbp+57h+arg_10]
0x18005d232  lea     r8, [rbp+57h+pvar]
0x18005d236  lea     rdx, PKEY_IddDeviceInstance
0x18005d23d  mov     rax, [rcx]
0x18005d240  mov     rax, [rax+30h]
0x18005d244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d249  lea     rcx, [rbp+57h+pvar]; pvar
0x18005d24d  mov     edi, eax
0x18005d24f  call    cs:__imp_PropVariantClear
0x18005d255  test    edi, edi
0x18005d257  jns     short loc_18005D282
0x18005d259  mov     eax, cs:dword_1801B76C8
0x18005d25f  cmp     eax, 2
0x18005d262  jbe     loc_18005D6E0
0x18005d268  lea     rax, aFailedToSetPke_3; "Failed to set PKEY_IddDeviceInstance pr"...
0x18005d26f  mov     dword ptr [rbp+57h+arg_0], 41Fh
0x18005d276  lea     rdx, byte_18019A20F
0x18005d27d  jmp     loc_18005D67D
0x18005d282  mov     rcx, [r14+68h]
0x18005d286  lea     r8, [rbp+57h+var_50]
0x18005d28a  lea     rdx, aRdpTerminalnam; "RDP::TerminalName"
0x18005d291  mov     rax, [rcx]
0x18005d294  mov     rax, [rax+18h]
0x18005d298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d29d  mov     edi, eax
0x18005d29f  test    eax, eax
0x18005d2a1  jns     short loc_18005D2CC
0x18005d2a3  mov     eax, cs:dword_1801B76C8
0x18005d2a9  cmp     eax, 2
0x18005d2ac  jbe     loc_18005D6E0
0x18005d2b2  lea     rax, aFailedToGetPro_9; "Failed to get property RDP_PROPERTY_PRO"...
0x18005d2b9  mov     dword ptr [rbp+57h+arg_0], 428h
0x18005d2c0  lea     rdx, byte_18019A1BF
0x18005d2c7  jmp     loc_18005D67D
0x18005d2cc  cmp     word ptr [rbp+57h+var_50], 8
0x18005d2d1  jz      loc_18005D360
0x18005d2d7  mov     eax, cs:dword_1801B76C8
0x18005d2dd  mov     ecx, 8000FFFFh
0x18005d2e2  mov     edi, ecx
0x18005d2e4  cmp     eax, 2
0x18005d2e7  jbe     loc_18005D6E0
0x18005d2ed  lea     rax, aRdpPropertyPro; "RDP_PROPERTY_PROTOCOL_NAME is not set p"...
0x18005d2f4  mov     dword ptr [rbp+57h+arg_0], 42Dh
0x18005d2fb  mov     [rbp+57h+var_88], rax
0x18005d2ff  lea     rdx, byte_18019A16F
0x18005d306  lea     rax, aStartpipemgrli; "StartPipeMgrLite"
0x18005d30d  mov     [rbp+57h+arg_8], ecx
0x18005d310  mov     [rbp+57h+var_90], rax
0x18005d314  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005d31b  mov     [rbp+57h+var_98], rax
0x18005d31f  lea     rax, aErrorCondition; "Error condition failed"
0x18005d326  mov     [rbp+57h+var_A0], rax
0x18005d32a  lea     rax, [rbp+57h+var_88]
0x18005d32e  mov     [rsp+0F0h+var_A8], rax
0x18005d333  lea     rax, [rbp+57h+var_90]
0x18005d337  mov     [rsp+0F0h+var_B0], rax
0x18005d33c  lea     rax, [rbp+57h+arg_0]
0x18005d340  mov     [rsp+0F0h+var_B8], rax
0x18005d345  lea     rax, [rbp+57h+var_98]
0x18005d349  mov     [rsp+0F0h+var_C0], rax
0x18005d34e  lea     rax, [rbp+57h+arg_8]
0x18005d352  mov     [rsp+0F0h+var_C8], rax
0x18005d357  lea     rax, [rbp+57h+var_A0]
0x18005d35b  jmp     loc_18005D6D6
0x18005d360  mov     rcx, qword ptr [rbp+57h+var_50+8]; Source
0x18005d364  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18005d368  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18005d36d  mov     edi, eax
0x18005d36f  test    eax, eax
0x18005d371  jns     short loc_18005D39C
0x18005d373  mov     eax, cs:dword_1801B76C8
0x18005d379  cmp     eax, 2
0x18005d37c  jbe     loc_18005D6E0
0x18005d382  lea     rax, aFailedToInitia_19; "Failed to initialize PKEY_ProtocolName "...
0x18005d389  mov     dword ptr [rbp+57h+arg_0], 430h
0x18005d390  lea     rdx, byte_18019A11F
0x18005d397  jmp     loc_18005D67D
0x18005d39c  mov     rcx, [rbp+57h+arg_10]
0x18005d3a0  lea     r8, [rbp+57h+pvar]
0x18005d3a4  lea     rdx, PKEY_ProtocolName
0x18005d3ab  mov     rax, [rcx]
0x18005d3ae  mov     rax, [rax+30h]
0x18005d3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3b7  lea     rcx, [rbp+57h+pvar]; pvar
0x18005d3bb  mov     edi, eax
0x18005d3bd  call    cs:__imp_PropVariantClear
0x18005d3c3  test    edi, edi
0x18005d3c5  jns     short loc_18005D3F0
0x18005d3c7  mov     eax, cs:dword_1801B76C8
0x18005d3cd  cmp     eax, 2
0x18005d3d0  jbe     loc_18005D6E0
0x18005d3d6  lea     rax, aFailedToSetPke_1; "Failed to set PKEY_ProtocolName propert"...
0x18005d3dd  mov     dword ptr [rbp+57h+arg_0], 437h
0x18005d3e4  lea     rdx, byte_18019A0CF
0x18005d3eb  jmp     loc_18005D67D
0x18005d3f0  mov     rcx, [r14+68h]
0x18005d3f4  lea     r8, [rbp+57h+var_38]
0x18005d3f8  lea     rdx, aConnectionid; "ConnectionID"
0x18005d3ff  mov     rax, [rcx]
0x18005d402  mov     rax, [rax+18h]
0x18005d406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d40b  mov     edi, eax
0x18005d40d  test    eax, eax
0x18005d40f  jns     short loc_18005D43A
0x18005d411  mov     eax, cs:dword_1801B76C8
0x18005d417  cmp     eax, 2
0x18005d41a  jbe     loc_18005D6E0
0x18005d420  lea     rax, aFailedToGetPro_8; "Failed to get property CONN_PROPERTY_CO"...
0x18005d427  mov     dword ptr [rbp+57h+arg_0], 440h
0x18005d42e  lea     rdx, byte_18019A07F
0x18005d435  jmp     loc_18005D67D
0x18005d43a  cmp     word ptr [rbp+57h+var_38], si
0x18005d43e  jz      loc_18005D4CD
0x18005d444  mov     eax, cs:dword_1801B76C8
0x18005d44a  mov     ecx, 8000FFFFh
0x18005d44f  mov     edi, ecx
0x18005d451  cmp     eax, 2
0x18005d454  jbe     loc_18005D6E0
0x18005d45a  lea     rax, aConnPropertyCo; "CONN_PROPERTY_CONNECTION_ID is not set "...
0x18005d461  mov     dword ptr [rbp+57h+arg_0], 445h
0x18005d468  mov     [rbp+57h+var_88], rax
0x18005d46c  lea     rdx, byte_18019A02F
0x18005d473  lea     rax, aStartpipemgrli; "StartPipeMgrLite"
0x18005d47a  mov     [rbp+57h+arg_8], ecx
0x18005d47d  mov     [rbp+57h+var_90], rax
0x18005d481  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005d488  mov     [rbp+57h+var_98], rax
0x18005d48c  lea     rax, aErrorCondition; "Error condition failed"
0x18005d493  mov     [rbp+57h+var_A0], rax
0x18005d497  lea     rax, [rbp+57h+var_88]
0x18005d49b  mov     [rsp+0F0h+var_A8], rax
0x18005d4a0  lea     rax, [rbp+57h+var_90]
0x18005d4a4  mov     [rsp+0F0h+var_B0], rax
0x18005d4a9  lea     rax, [rbp+57h+arg_0]
0x18005d4ad  mov     [rsp+0F0h+var_B8], rax
0x18005d4b2  lea     rax, [rbp+57h+var_98]
0x18005d4b6  mov     [rsp+0F0h+var_C0], rax
0x18005d4bb  lea     rax, [rbp+57h+arg_8]
  ... truncated ...
```
