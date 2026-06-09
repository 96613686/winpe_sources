# CxCodeVideoProcMFTDataHandler::Init(CxCodeVideoProcMFTTypeHandler *)

- ea: `0x180060600`
- end: `0x180060b34`
- name: `?Init@CxCodeVideoProcMFTDataHandler@@QEAAJPEAVCxCodeVideoProcMFTTypeHandler@@@Z`
- size: `1332`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this, struct CxCodeVideoProcMFTTypeHandler *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001649c`

## callees

- `0x180009724`
- `0x180009848`
- `0x180009940`
- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180016e1c`
- `0x180036268`
- `0x18003639c`
- `0x180054140`
- `0x180060600`
- `0x180065cb0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180060818`
- `MFPlat!MFCreateAttributes` at `0x180060a3a`
- `MFPlat!MFCreateAttributes` at `0x180060818`
- `MFPlat!MFCreateAttributes` at `0x180060a3a`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::Init(
        CxCodeVideoProcMFTDataHandler *this,
        struct CxCodeVideoProcMFTTypeHandler *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  _DWORD *v7; // r14
  int v8; // eax
  char v9; // al
  _QWORD *v10; // rdi
  HRESULT v11; // ebx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rdx
  _BYTE v27[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v28[16]; // [rsp+38h] [rbp-40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v27, "CxCodeVideoProcMFTDataHandler::Init", 2275);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 388) + 280LL))(
                      *((_QWORD *)this + 388),
                      v28);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v7 = (_DWORD *)((char *)this + 1504);
  XVPReadRegistryOverrides((CxCodeVideoProcMFTDataHandler *)((char *)this + 1504));
  v8 = AccessRegistryInt(L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP", L"disableSSE2", 0);
  *((_DWORD *)this + 766) = v8;
  *((_DWORD *)this + 765) = v8 == 0;
  *((_DWORD *)this + 371) = AccessRegistryInt(
                              L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
                              L"forceBGRX",
                              0);
  *((_DWORD *)this + 368) = XVPReadAutoProcessRegistry(0, (int *)this + 369);
  *((_DWORD *)this + 372) = AccessRegistryInt(
                              L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
                              L"forceDX11RotMirror",
                              0);
  *((_DWORD *)this + 374) = AccessRegistryInt(
                              L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
                              L"forceFastScaleArea",
                              2073600);
  *((_DWORD *)this + 791) = AccessRegistryInt(
                              L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
                              L"dx11SliceCount",
                              4);
  *((_DWORD *)this + 250) = XVPReadOutSideModeRegistry() != 0;
  *((_DWORD *)this + 383) = AccessRegistryInt(L"Software\\Microsoft\\OEM\\Device\\Video", L"VPBltTMLuminanceMinimum", 0);
  v9 = byte_180153DE0;
  if ( (unsigned __int8)byte_180153DE0 >= 8u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      142,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      *((_DWORD *)this + 250));
    v9 = byte_180153DE0;
  }
  if ( (unsigned __int8)v9 >= 0x20u )
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      143,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      *v7,
      *((_DWORD *)this + 766));
  v10 = (_QWORD *)((char *)this + 224);
  *((_QWORD *)this + 1) = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 224);
  v11 = MFCreateAttributes((IMFAttributes **)this + 28, 2u);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, bool))(*(_QWORD *)*v10 + 168LL))(
            *v10,
            MF_SA_D3D11_AWARE,
            *v7 != 1);
    if ( v11 >= 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2508>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2508>::GetImpl'::`2'::impl)
        && (v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, bool))(*(_QWORD *)*v10 + 168LL))(
                    *v10,
                    MF_SA_D3D12_AWARE,
                    *v7 != 1),
            v11 < 0) )
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v17 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext(v17);
          if ( *((_DWORD *)v18 + 499) != v11 )
            CallStackContext::TraceFailure(v18, "CxCodeVideoProcMFTDataHandler::Init", 2318, v11);
        }
        if ( g_wppLevels )
        {
          v14 = 146;
          goto LABEL_16;
        }
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v10 + 168LL))(
                *v10,
                MFT_SUPPORT_3DVIDEO,
                1);
        if ( v11 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 232);
          v11 = MFCreateAttributes((IMFAttributes **)this + 29, 1u);
          if ( v11 >= 0 )
          {
            *((_QWORD *)this + 448) = 0;
            if ( !*((_QWORD *)this + 397) )
            {
              *((_DWORD *)this + 796) = 1;
              *((_QWORD *)this + 397) = (char *)this + 3192;
              v23 = 0;
              *((_QWORD *)this + 399) = 0;
              do
              {
                v24 = v23 + 2 * v23 + 1;
                ++v23;
                v25 = *((_QWORD *)this + 397) + 8 * v24;
                *(_QWORD *)(v25 + 8) = *((_QWORD *)this + 396);
                *((_QWORD *)this + 396) = v25;
              }
              while ( v23 != 16 );
            }
            v11 = 0;
          }
          else
          {
            v21 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v21 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v22 = CallStackTracing::GetThreadRelativeContext(v21);
              if ( *((_DWORD *)v22 + 499) != v11 )
                CallStackContext::TraceFailure(v22, "CxCodeVideoProcMFTDataHandler::Init", 2323, v11);
            }
            if ( g_wppLevels )
            {
              v14 = 148;
              goto LABEL_16;
            }
          }
        }
        else
        {
          v19 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v19 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext(v19);
            if ( *((_DWORD *)v20 + 499) != v11 )
              CallStackContext::TraceFailure(v20, "CxCodeVideoProcMFTDataHandler::Init", 2321, v11);
          }
          if ( g_wppLevels )
          {
            v14 = 147;
            goto LABEL_16;
          }
        }
      }
    }
    else
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v15 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext(v15);
        if ( *((_DWORD *)v16 + 499) != v11 )
          CallStackContext::TraceFailure(v16, "CxCodeVideoProcMFTDataHandler::Init", 2315, v11);
      }
      if ( g_wppLevels )
      {
        v14 = 145;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v13 + 499) != v11 )
        CallStackContext::TraceFailure(v13, "CxCodeVideoProcMFTDataHandler::Init", 2314, v11);
    }
    if ( g_wppLevels )
    {
      v14 = 144;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, v11);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180060600  mov     [rsp+arg_8], rbx
0x180060605  mov     [rsp+arg_10], rbp
0x18006060a  push    rsi
0x18006060b  push    rdi
0x18006060c  push    r12
0x18006060e  push    r13
0x180060610  push    r14
0x180060612  sub     rsp, 50h
0x180060616  mov     rax, cs:__security_cookie
0x18006061d  xor     rax, rsp
0x180060620  mov     [rsp+78h+var_30], rax
0x180060625  mov     rbp, rdx
0x180060628  lea     r13, aCxcodevideopro_149; "CxCodeVideoProcMFTDataHandler::Init"
0x18006062f  mov     rsi, rcx
0x180060632  mov     rdx, r13; char *
0x180060635  mov     r8d, 8E3h; int
0x18006063b  lea     rcx, [rsp+78h+var_48]; this
0x180060640  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180060645  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006064c  cmp     byte ptr [rcx+8], 0
0x180060650  jz      short loc_1800606A8
0x180060652  cmp     qword ptr [rsi+0C20h], 0
0x18006065a  jz      short loc_1800606A8
0x18006065c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060661  mov     rcx, [rsi+0C20h]
0x180060668  mov     rdi, rax
0x18006066b  mov     rdx, [rcx]
0x18006066e  mov     rax, [rdx+128h]
0x180060675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006067a  mov     rcx, [rsi+0C20h]
0x180060681  mov     ebx, eax
0x180060683  mov     rdx, [rcx]
0x180060686  mov     rax, [rdx+118h]
0x18006068d  lea     rdx, [rsp+78h+var_40]
0x180060692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060697  movups  xmm0, xmmword ptr [rax]
0x18006069a  mov     [rdi+7E0h], ebx
0x1800606a0  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800606a8  lea     r14, [rsi+5E0h]
0x1800606af  mov     rcx, r14; enum XVPDebugMode *
0x1800606b2  call    ?XVPReadRegistryOverrides@@YAXAEAW4XVPDebugMode@@@Z; XVPReadRegistryOverrides(XVPDebugMode &)
0x1800606b7  lea     rbx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x1800606be  xor     r8d, r8d; int
0x1800606c1  mov     rcx, rbx; lpSubKey
0x1800606c4  lea     rdx, aDisablesse2; "disableSSE2"
0x1800606cb  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x1800606d0  xor     ecx, ecx
0x1800606d2  mov     [rsi+0BF8h], eax
0x1800606d8  test    eax, eax
0x1800606da  lea     rdx, aForcebgrx; "forceBGRX"
0x1800606e1  setz    cl
0x1800606e4  xor     r8d, r8d; int
0x1800606e7  mov     [rsi+0BF4h], ecx
0x1800606ed  mov     rcx, rbx; lpSubKey
0x1800606f0  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x1800606f5  lea     rdx, [rsi+5C4h]; int *
0x1800606fc  mov     [rsi+5CCh], eax
0x180060702  xor     ecx, ecx; int
0x180060704  call    ?XVPReadAutoProcessRegistry@@YAIHAEAH@Z; XVPReadAutoProcessRegistry(int,int &)
0x180060709  xor     r8d, r8d; int
0x18006070c  mov     [rsi+5C0h], eax
0x180060712  lea     rdx, aForcedx11rotmi; "forceDX11RotMirror"
0x180060719  mov     rcx, rbx; lpSubKey
0x18006071c  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x180060721  mov     r8d, 1FA400h; int
0x180060727  mov     [rsi+5D0h], eax
0x18006072d  lea     rdx, aForcefastscale; "forceFastScaleArea"
0x180060734  mov     rcx, rbx; lpSubKey
0x180060737  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x18006073c  mov     r8d, 4; int
0x180060742  mov     [rsi+5D8h], eax
0x180060748  lea     rdx, aDx11slicecount; "dx11SliceCount"
0x18006074f  mov     rcx, rbx; lpSubKey
0x180060752  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x180060757  mov     [rsi+0C5Ch], eax
0x18006075d  call    ?XVPReadOutSideModeRegistry@@YAIXZ; XVPReadOutSideModeRegistry(void)
0x180060762  xor     ecx, ecx
0x180060764  lea     rdx, aVpblttmluminan; "VPBltTMLuminanceMinimum"
0x18006076b  test    eax, eax
0x18006076d  setnz   cl
0x180060770  xor     r8d, r8d; int
0x180060773  mov     [rsi+3E8h], ecx
0x180060779  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\OEM\\Device\\Video"
0x180060780  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x180060785  mov     [rsi+5FCh], eax
0x18006078b  mov     al, cs:byte_180153DE0
0x180060791  lea     r12, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180060798  cmp     al, 8
0x18006079a  jb      short loc_1800607CA
0x18006079c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800607a3  mov     edx, 8Eh
0x1800607a8  mov     eax, [rsi+3E8h]
0x1800607ae  mov     r9, rsi
0x1800607b1  mov     r8, r12
0x1800607b4  mov     [rsp+78h+var_58], eax
0x1800607b8  mov     rcx, [rcx+150h]
0x1800607bf  call    WPP_SF_qD
0x1800607c4  mov     al, cs:byte_180153DE0
0x1800607ca  cmp     al, 20h ; ' '
0x1800607cc  jb      short loc_1800607FD
0x1800607ce  mov     eax, [rsi+0BF8h]
0x1800607d4  mov     edx, 8Fh
0x1800607d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800607e0  mov     r9, rsi
0x1800607e3  mov     [rsp+78h+var_50], eax
0x1800607e7  mov     r8, r12
0x1800607ea  mov     eax, [r14]
0x1800607ed  mov     [rsp+78h+var_58], eax
0x1800607f1  mov     rcx, [rcx+150h]
0x1800607f8  call    WPP_SF_qdd
0x1800607fd  lea     rdi, [rsi+0E0h]
0x180060804  mov     [rsi+8], rbp
0x180060808  mov     rcx, rdi
0x18006080b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060810  mov     edx, 2; cInitialSize
0x180060815  mov     rcx, rdi; ppMFAttributes
0x180060818  call    cs:__imp_MFCreateAttributes
0x18006081e  mov     ebx, eax
0x180060820  test    eax, eax
0x180060822  jns     short loc_180060894
0x180060824  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006082b  test    rcx, rcx
0x18006082e  jnz     short loc_18006083C
0x180060830  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180060835  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006083c  cmp     byte ptr [rcx+8], 0
0x180060840  jz      short loc_180060863
0x180060842  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060847  cmp     [rax+7CCh], ebx
0x18006084d  jz      short loc_180060863
0x18006084f  mov     r9d, ebx; int
0x180060852  mov     r8d, 90Ah; int
0x180060858  mov     rdx, r13; char *
0x18006085b  mov     rcx, rax; this
0x18006085e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060863  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006086a  jb      loc_180060B02
0x180060870  mov     edx, 90h
0x180060875  mov     rcx, cs:WPP_GLOBAL_Control
0x18006087c  mov     r9, rsi
0x18006087f  mov     r8, r12
0x180060882  mov     [rsp+78h+var_58], ebx
0x180060886  mov     rcx, [rcx+10h]
0x18006088a  call    WPP_SF_qD
0x18006088f  jmp     loc_180060B02
0x180060894  mov     rcx, [rdi]
0x180060897  lea     rdx, MF_SA_D3D11_AWARE
0x18006089e  xor     r8d, r8d
0x1800608a1  cmp     dword ptr [r14], 1
0x1800608a5  mov     rax, [rcx]
0x1800608a8  setnz   r8b
0x1800608ac  mov     rax, [rax+0A8h]
0x1800608b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800608b8  mov     ebx, eax
0x1800608ba  test    eax, eax
0x1800608bc  jns     short loc_180060914
0x1800608be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800608c5  test    rcx, rcx
0x1800608c8  jnz     short loc_1800608D6
0x1800608ca  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800608cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800608d6  cmp     byte ptr [rcx+8], 0
0x1800608da  jz      short loc_1800608FD
0x1800608dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800608e1  cmp     [rax+7CCh], ebx
0x1800608e7  jz      short loc_1800608FD
0x1800608e9  mov     r9d, ebx; int
0x1800608ec  mov     r8d, 90Bh; int
0x1800608f2  mov     rdx, r13; char *
0x1800608f5  mov     rcx, rax; this
0x1800608f8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800608fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060904  jb      loc_180060B02
0x18006090a  mov     edx, 91h
0x18006090f  jmp     loc_180060875
0x180060914  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2508@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2508@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2508> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2508>::GetImpl(void)'::`2'::impl
0x18006091b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2508@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2508>::__private_IsEnabled(void)
0x180060920  test    al, al
0x180060922  jz      loc_1800609A8
0x180060928  mov     rcx, [rdi]
0x18006092b  lea     rdx, MF_SA_D3D12_AWARE
0x180060932  xor     r8d, r8d
0x180060935  cmp     dword ptr [r14], 1
0x180060939  mov     rax, [rcx]
0x18006093c  setnz   r8b
0x180060940  mov     rax, [rax+0A8h]
0x180060947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006094c  mov     ebx, eax
0x18006094e  test    eax, eax
0x180060950  jns     short loc_1800609A8
0x180060952  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060959  test    rcx, rcx
0x18006095c  jnz     short loc_18006096A
0x18006095e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180060963  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006096a  cmp     byte ptr [rcx+8], 0
0x18006096e  jz      short loc_180060991
0x180060970  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060975  cmp     [rax+7CCh], ebx
0x18006097b  jz      short loc_180060991
0x18006097d  mov     r9d, ebx; int
0x180060980  mov     r8d, 90Eh; int
0x180060986  mov     rdx, r13; char *
0x180060989  mov     rcx, rax; this
0x18006098c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060991  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060998  jb      loc_180060B02
0x18006099e  mov     edx, 92h
0x1800609a3  jmp     loc_180060875
0x1800609a8  mov     rcx, [rdi]
0x1800609ab  lea     rdx, MFT_SUPPORT_3DVIDEO
0x1800609b2  mov     r8d, 1
0x1800609b8  mov     rax, [rcx]
0x1800609bb  mov     rax, [rax+0A8h]
0x1800609c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609c7  mov     ebx, eax
0x1800609c9  test    eax, eax
0x1800609cb  jns     short loc_180060A23
0x1800609cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800609d4  test    rcx, rcx
0x1800609d7  jnz     short loc_1800609E5
0x1800609d9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800609de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800609e5  cmp     byte ptr [rcx+8], 0
0x1800609e9  jz      short loc_180060A0C
0x1800609eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800609f0  cmp     [rax+7CCh], ebx
0x1800609f6  jz      short loc_180060A0C
0x1800609f8  mov     r9d, ebx; int
0x1800609fb  mov     r8d, 911h; int
0x180060a01  mov     rdx, r13; char *
0x180060a04  mov     rcx, rax; this
0x180060a07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060a0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060a13  jb      loc_180060B02
0x180060a19  mov     edx, 93h
0x180060a1e  jmp     loc_180060875
0x180060a23  lea     rbx, [rsi+0E8h]
0x180060a2a  mov     rcx, rbx
0x180060a2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060a32  mov     edx, 1; cInitialSize
0x180060a37  mov     rcx, rbx; ppMFAttributes
0x180060a3a  call    cs:__imp_MFCreateAttributes
0x180060a40  mov     ebx, eax
0x180060a42  test    eax, eax
0x180060a44  jns     short loc_180060A98
0x180060a46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060a4d  test    rcx, rcx
0x180060a50  jnz     short loc_180060A5E
0x180060a52  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180060a57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180060a5e  cmp     byte ptr [rcx+8], 0
0x180060a62  jz      short loc_180060A85
0x180060a64  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060a69  cmp     [rax+7CCh], ebx
0x180060a6f  jz      short loc_180060A85
0x180060a71  mov     r9d, ebx; int
0x180060a74  mov     r8d, 913h; int
0x180060a7a  mov     rdx, r13; char *
0x180060a7d  mov     rcx, rax; this
0x180060a80  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060a85  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060a8c  jb      short loc_180060B02
0x180060a8e  mov     edx, 94h
0x180060a93  jmp     loc_180060875
0x180060a98  mov     qword ptr [rsi+0E00h], 0
0x180060aa3  cmp     qword ptr [rsi+0C68h], 0
0x180060aab  jnz     short loc_180060B00
0x180060aad  lea     rax, [rsi+0C78h]
0x180060ab4  mov     dword ptr [rsi+0C70h], 1
0x180060abe  mov     [rsi+0C68h], rax
0x180060ac5  xor     r8d, r8d
0x180060ac8  mov     qword ptr [rax], 0
0x180060acf  mov     rax, [rsi+0C68h]
0x180060ad6  lea     rdx, ds:1[r8*2]
0x180060ade  add     rdx, r8
0x180060ae1  inc     r8
0x180060ae4  lea     rdx, [rax+rdx*8]
0x180060ae8  mov     rax, [rsi+0C60h]
0x180060aef  mov     [rdx+8], rax
0x180060af3  mov     [rsi+0C60h], rdx
0x180060afa  cmp     r8, 10h
0x180060afe  jnz     short loc_180060ACF
0x180060b00  xor     ebx, ebx
0x180060b02  lea     rcx, [rsp+78h+var_48]; this
0x180060b07  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180060b0c  mov     eax, ebx
0x180060b0e  mov     rcx, [rsp+78h+var_30]
0x180060b13  xor     rcx, rsp; StackCookie
0x180060b16  call    __security_check_cookie
0x180060b1b  lea     r11, [rsp+78h+var_28]
0x180060b20  mov     rbx, [r11+38h]
0x180060b24  mov     rbp, [r11+40h]
0x180060b28  mov     rsp, r11
0x180060b2b  pop     r14
0x180060b2d  pop     r13
0x180060b2f  pop     r12
0x180060b31  pop     rdi
0x180060b32  pop     rsi
0x180060b33  retn
  ... truncated ...
```
