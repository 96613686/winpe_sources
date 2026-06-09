# Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetTargetUserSid(ushort const *,ushort * *)

- ea: `0x14004efcc`
- end: `0x14004f281`
- name: `?GetTargetUserSid@SyncmlSessionStateManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGPEAPEAG@Z`
- size: `693`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004f290`

## callees

- `0x140003450`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x1400134a4`
- `0x1400303d8`
- `0x14004e8a0`
- `0x14004efcc`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x14004f1f7`
- `DMCmnUtils!CopyString` at `0x14004f1f7`

## string_xrefs

- `0x14004f009`: `GetTargetUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager::GetTargetUserSid(
        Microsoft::Windows::MDM::OmadmClient::SyncmlSessionStateManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  struct COmaDmLogger *Logger; // rax
  __int64 v6; // r8
  __int64 v7; // rdi
  int v8; // eax
  int v9; // ebx
  __int64 v10; // r10
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  char *v20; // [rsp+20h] [rbp-59h]
  int v21; // [rsp+30h] [rbp-49h] BYREF
  const unsigned __int16 *v22; // [rsp+38h] [rbp-41h] BYREF
  int v23; // [rsp+40h] [rbp-39h] BYREF
  int v24; // [rsp+44h] [rbp-35h] BYREF
  int v25; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-29h] BYREF
  int v27; // [rsp+68h] [rbp-11h]
  int *v28; // [rsp+70h] [rbp-9h]
  _QWORD v29[2]; // [rsp+78h] [rbp-1h] BYREF
  char v30; // [rsp+88h] [rbp+Fh]
  char v31; // [rsp+90h] [rbp+17h] BYREF
  int *v32; // [rsp+A0h] [rbp+27h]
  __int64 v33; // [rsp+A8h] [rbp+2Fh]

  v21 = 0;
  Logger = COmaDmLogger::GetLogger();
  Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Logger, 2, "GetTargetUserSid", 0);
  v26[0] = 0;
  v26[1] = "GetTargetUserSid";
  v26[2] = COmaDmLogger::GetLogger();
  v27 = 2;
  v28 = &v21;
  v22 = 0;
  v23 = 0;
  v24 = 63;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v25 = 91;
    v32 = &v25;
    v33 = 4;
    v20 = &v31;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v6, 2);
  }
  v29[0] = &v21;
  v29[1] = &v22;
  v30 = 1;
  v7 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
                                                                                                  + 208LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
  v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, int *))(*(_QWORD *)v7 + 24LL))(
         v7,
         a2,
         1,
         &v24);
  v9 = v8;
  v21 = v8;
  if ( v8 < 0 )
  {
    LODWORD(v26[0]) = 9027;
    HIDWORD(v26[0]) = v8;
    goto LABEL_23;
  }
  if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, int *))(*(_QWORD *)v7 + 272LL))(
         v7,
         a2,
         L"RunAsSystem",
         &v23) >= 0
    && v23 == 1 )
  {
    v9 = -2147023728;
    v21 = -2147023728;
    goto LABEL_23;
  }
  v10 = *(_QWORD *)v7;
  if ( ((1LL << v24) & 0x9402021) != 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, const unsigned __int16 **))(v10 + 32))(
            v7,
            a2,
            1,
            &v22);
    v9 = v11;
    v21 = v11;
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0qz_EventWriteTransfer(v13, DmGetEnrollmentSidResults, v11, v22, v20);
      v9 = v21;
    }
    if ( v22 )
    {
      if ( v9 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::MDM::OmadmClient::IAbstractFactory *))(*(_QWORD *)Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory + 96LL))(Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory);
        if ( (*(unsigned int (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v16 + 24LL))(v16, v22) )
        {
          v9 = CopyString(v22, 0xFFFFFFFF, a3);
          v21 = v9;
          goto LABEL_23;
        }
        LODWORD(v26[0]) = 9022;
        v9 = -2147467259;
      }
      else
      {
        LODWORD(v26[0]) = 9026;
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v13, v12, v14, v15, v20);
      LODWORD(v26[0]) = 9023;
      v9 = -2147418113;
    }
LABEL_22:
    HIDWORD(v26[0]) = v9;
    goto LABEL_23;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(v10 + 48))(v7, a3);
  v9 = v17;
  v21 = v17;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 1) != 0 )
  {
    McTemplateU0qz_EventWriteTransfer(v18, GetActiveUserSidResults, v17, *a3, v20);
    v9 = v21;
  }
  if ( v9 < 0 )
  {
    LODWORD(v26[0]) = 9024;
    goto LABEL_22;
  }
LABEL_23:
  wil::details::ScopeExitFn__lambda_b46ff98123eee328f5ca5a458ca75051___::_ScopeExitFn__lambda_b46ff98123eee328f5ca5a458ca75051___(v29);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v26);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004efcc  mov     [rsp-8+arg_0], rbx
0x14004efd1  mov     [rsp-8+arg_18], rsi
0x14004efd6  push    rbp
0x14004efd7  push    rdi
0x14004efd8  push    r14
0x14004efda  lea     rbp, [rsp-47h]
0x14004efdf  sub     rsp, 0C0h
0x14004efe6  mov     rax, cs:__security_cookie
0x14004efed  xor     rax, rsp
0x14004eff0  mov     [rbp+57h+var_20], rax
0x14004eff4  mov     rsi, r8
0x14004eff7  mov     r14, rdx
0x14004effa  mov     [rbp+57h+var_A0], 0
0x14004f001  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004f006  xor     r9d, r9d
0x14004f009  lea     rbx, aGettargetusers; "GetTargetUserSid"
0x14004f010  mov     r8, rbx
0x14004f013  lea     edi, [r9+2]
0x14004f017  mov     edx, edi
0x14004f019  mov     rcx, rax
0x14004f01c  call    ?LogFunctionEntryMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@PEBDPEBGZZ; Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Microsoft::Windows::TracingLevel,char const *,ushort const *,...)
0x14004f021  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004f026  mov     [rbp+57h+var_80], 0
0x14004f02e  mov     [rbp+57h+var_78], rbx
0x14004f032  mov     [rbp+57h+var_70], rax
0x14004f036  mov     [rbp+57h+var_68], edi
0x14004f039  lea     rax, [rbp+57h+var_A0]
0x14004f03d  mov     [rbp+57h+var_60], rax
0x14004f041  mov     [rbp+57h+var_98], 0
0x14004f049  mov     [rbp+57h+var_90], 0
0x14004f050  mov     [rbp+57h+var_8C], 3Fh ; '?'
0x14004f057  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14004f05e  jz      short loc_14004F096
0x14004f060  mov     [rbp+57h+var_88], 5Bh ; '['
0x14004f067  lea     rax, [rbp+57h+var_88]
0x14004f06b  mov     [rbp+57h+var_30], rax
0x14004f06f  mov     [rbp+57h+var_28], 4
0x14004f077  lea     rax, [rbp+57h+var_40]
0x14004f07b  mov     [rsp+0D0h+var_B0], rax
0x14004f080  mov     r9d, edi
0x14004f083  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14004f08a  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14004f091  call    McGenEventWrite_EventWriteTransfer
0x14004f096  lea     rax, [rbp+57h+var_A0]
0x14004f09a  mov     [rbp+57h+var_58], rax
0x14004f09e  lea     rax, [rbp+57h+var_98]
0x14004f0a2  mov     [rbp+57h+var_50], rax
0x14004f0a6  mov     [rbp+57h+var_48], 1
0x14004f0aa  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x14004f0b1  mov     rax, [rcx]
0x14004f0b4  mov     rax, [rax+0D0h]
0x14004f0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0c0  mov     rdi, rax
0x14004f0c3  mov     rcx, [rax]
0x14004f0c6  mov     rax, [rcx+18h]
0x14004f0ca  lea     r9, [rbp+57h+var_8C]
0x14004f0ce  mov     r8d, 1
0x14004f0d4  mov     rdx, r14
0x14004f0d7  mov     rcx, rdi
0x14004f0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f0df  mov     ebx, eax
0x14004f0e1  mov     [rbp+57h+var_A0], eax
0x14004f0e4  test    eax, eax
0x14004f0e6  jns     short loc_14004F0F7
0x14004f0e8  mov     dword ptr [rbp+57h+var_80], 2343h
0x14004f0ef  mov     dword ptr [rbp+57h+var_80+4], eax
0x14004f0f2  jmp     loc_14004F247
0x14004f0f7  mov     rax, [rdi]
0x14004f0fa  lea     r9, [rbp+57h+var_90]
0x14004f0fe  lea     r8, aRunassystem; "RunAsSystem"
0x14004f105  mov     rdx, r14
0x14004f108  mov     rcx, rdi
0x14004f10b  mov     rax, [rax+110h]
0x14004f112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f117  test    eax, eax
0x14004f119  js      short loc_14004F12E
0x14004f11b  cmp     [rbp+57h+var_90], 1
0x14004f11f  jnz     short loc_14004F12E
0x14004f121  mov     ebx, 80070490h
0x14004f126  mov     [rbp+57h+var_A0], ebx
0x14004f129  jmp     loc_14004F247
0x14004f12e  mov     r10, [rdi]
0x14004f131  mov     ecx, [rbp+57h+var_8C]
0x14004f134  mov     eax, 1
0x14004f139  shl     rax, cl
0x14004f13c  mov     rcx, rdi
0x14004f13f  test    rax, 9402021h
0x14004f145  jz      loc_14004F20A
0x14004f14b  lea     r9, [rbp+57h+var_98]
0x14004f14f  mov     r8d, 1
0x14004f155  mov     rdx, r14
0x14004f158  mov     rax, [r10+20h]
0x14004f15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f161  mov     ebx, eax
0x14004f163  mov     [rbp+57h+var_A0], eax
0x14004f166  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 1
0x14004f16d  jz      short loc_14004F185
0x14004f16f  mov     r9, [rbp+57h+var_98]
0x14004f173  mov     r8d, eax
0x14004f176  lea     rdx, DmGetEnrollmentSidResults
0x14004f17d  call    McTemplateU0qz_EventWriteTransfer
0x14004f182  mov     ebx, [rbp+57h+var_A0]
0x14004f185  cmp     [rbp+57h+var_98], 0
0x14004f18a  jnz     short loc_14004F1A2
0x14004f18c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x14004f191  mov     dword ptr [rbp+57h+var_80], 233Fh
0x14004f198  mov     ebx, 8000FFFFh
0x14004f19d  jmp     loc_14004F244
0x14004f1a2  test    ebx, ebx
0x14004f1a4  jns     short loc_14004F1B2
0x14004f1a6  mov     dword ptr [rbp+57h+var_80], 2342h
0x14004f1ad  jmp     loc_14004F244
0x14004f1b2  mov     rcx, cs:?g_pIAbstractFactory@OmadmClient@MDM@Windows@Microsoft@@3PEAVIAbstractFactory@1234@EA; Microsoft::Windows::MDM::OmadmClient::IAbstractFactory * Microsoft::Windows::MDM::OmadmClient::g_pIAbstractFactory
0x14004f1b9  mov     rax, [rcx]
0x14004f1bc  mov     rax, [rax+60h]
0x14004f1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1c5  mov     r8, rax
0x14004f1c8  mov     rcx, [rax]
0x14004f1cb  mov     rax, [rcx+18h]
0x14004f1cf  mov     rdx, [rbp+57h+var_98]
0x14004f1d3  mov     rcx, r8
0x14004f1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1db  test    eax, eax
0x14004f1dd  jnz     short loc_14004F1ED
0x14004f1df  mov     dword ptr [rbp+57h+var_80], 233Eh
0x14004f1e6  mov     ebx, 80004005h
0x14004f1eb  jmp     short loc_14004F244
0x14004f1ed  mov     r8, rsi
0x14004f1f0  or      edx, 0FFFFFFFFh
0x14004f1f3  mov     rcx, [rbp+57h+var_98]
0x14004f1f7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14004f1fe  nop     dword ptr [rax+rax+00h]
0x14004f203  mov     ebx, eax
0x14004f205  mov     [rbp+57h+var_A0], eax
0x14004f208  jmp     short loc_14004F247
0x14004f20a  mov     rdx, rsi
0x14004f20d  mov     rax, [r10+30h]
0x14004f211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f216  mov     ebx, eax
0x14004f218  mov     [rbp+57h+var_A0], eax
0x14004f21b  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 1
0x14004f222  jz      short loc_14004F239
0x14004f224  mov     r9, [rsi]
0x14004f227  mov     r8d, eax
0x14004f22a  lea     rdx, GetActiveUserSidResults
0x14004f231  call    McTemplateU0qz_EventWriteTransfer
0x14004f236  mov     ebx, [rbp+57h+var_A0]
0x14004f239  test    ebx, ebx
0x14004f23b  jns     short loc_14004F247
0x14004f23d  mov     dword ptr [rbp+57h+var_80], 2340h
0x14004f244  mov     dword ptr [rbp+57h+var_80+4], ebx
0x14004f247  lea     rcx, [rbp+57h+var_58]
0x14004f24b  call    wil__details__ScopeExitFn__lambda_b46ff98123eee328f5ca5a458ca75051______ScopeExitFn__lambda_b46ff98123eee328f5ca5a458ca75051___
0x14004f250  nop
0x14004f251  lea     rcx, [rbp+57h+var_80]; this
0x14004f255  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004f25a  mov     eax, ebx
0x14004f25c  mov     rcx, [rbp+57h+var_20]
0x14004f260  xor     rcx, rsp; StackCookie
0x14004f263  call    __security_check_cookie
0x14004f268  lea     r11, [rsp+0D0h+var_10]
0x14004f270  mov     rbx, [r11+20h]
0x14004f274  mov     rsi, [r11+38h]
0x14004f278  mov     rsp, r11
0x14004f27b  pop     r14
0x14004f27d  pop     rdi
0x14004f27e  pop     rbp
0x14004f27f  retn
```
