# Rdp::Utils::Graphics::CRenderDevice::CRenderDevice(IDXGIAdapter3 *)

- ea: `0x1800205d4`
- end: `0x180020975`
- name: `??0CRenderDevice@Graphics@Utils@Rdp@@QEAA@PEAUIDXGIAdapter3@@@Z`
- size: `929`
- prototype: `_QWORD(Rdp::Utils::Graphics::CRenderDevice *__hidden this, struct IDXGIAdapter3 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022330`

## callees

- `0x18000208c`
- `0x180002d44`
- `0x1800036f0`
- `0x180004154`
- `0x180007b28`
- `0x18000cf28`
- `0x18000d858`
- `0x18000d98c`
- `0x1800205d4`
- `0x18002a010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x180020720`
- `d3d11!D3D11CreateDevice` at `0x180020720`

## string_xrefs

- `0x18002072d`: `D3D11CreateDevice failed`
- `0x18002080e`: `Render device created`
- `0x180020637`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RenderAdapter.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Rdp::Utils::Graphics::CRenderDevice *__fastcall Rdp::Utils::Graphics::CRenderDevice::CRenderDevice(
        Rdp::Utils::Graphics::CRenderDevice *this,
        IDXGIAdapter *a2,
        int a3,
        int a4)
{
  ID3D11DeviceContext *v6; // rcx
  ID3D11Device *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // r8d
  int v11; // r9d
  ID3D11Device *v12; // rax
  __int64 v13; // rcx
  ID3D11DeviceContext *v14; // rax
  __int64 v15; // rcx
  const char *FeatureLevelsa; // [rsp+28h] [rbp-F8h]
  const char *FeatureLevelsb; // [rsp+28h] [rbp-F8h]
  UINT FeatureLevels[2]; // [rsp+28h] [rbp-F8h]
  int v20; // [rsp+A0h] [rbp-80h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+A8h] [rbp-78h] BYREF
  ID3D11Device *ppDevice; // [rsp+B0h] [rbp-70h] BYREF
  int v23; // [rsp+B8h] [rbp-68h] BYREF
  int v24; // [rsp+BCh] [rbp-64h] BYREF
  int v25; // [rsp+C0h] [rbp-60h] BYREF
  int v26; // [rsp+C4h] [rbp-5Ch] BYREF
  int v27; // [rsp+C8h] [rbp-58h] BYREF
  int v28; // [rsp+CCh] [rbp-54h] BYREF
  const char *v29; // [rsp+D0h] [rbp-50h] BYREF
  const char *v30; // [rsp+D8h] [rbp-48h] BYREF
  const char *v31; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-38h] BYREF
  _BYTE *v33; // [rsp+F0h] [rbp-30h] BYREF
  const char *v34; // [rsp+F8h] [rbp-28h] BYREF
  const char *v35; // [rsp+100h] [rbp-20h] BYREF
  _QWORD v36[3]; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v37[256]; // [rsp+120h] [rbp+0h] BYREF
  int v38; // [rsp+220h] [rbp+100h]
  int v39; // [rsp+224h] [rbp+104h]
  int v40; // [rsp+228h] [rbp+108h]
  int v41; // [rsp+22Ch] [rbp+10Ch]
  int v42; // [rsp+230h] [rbp+110h]
  int v43; // [rsp+238h] [rbp+118h]
  int v44; // [rsp+240h] [rbp+120h]
  __int64 v45; // [rsp+248h] [rbp+128h]
  int v46; // [rsp+250h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+178h]

  v36[1] = this;
  *(_QWORD *)this = &Rdp::Utils::Graphics::CRenderDevice::`vftable';
  *((_BYTE *)this + 8) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  ppDevice = 0;
  ppImmediateContext = 0;
  if ( (unsigned int)dword_18003C058 > 4 )
  {
    v31 = "Creating render device";
    v30 = "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice";
    v20 = 104;
    v29 = "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&dword_180035F44,
      a3,
      a4,
      (__int64)&v29,
      (__int64)&v20,
      (__int64)&v30,
      (__int64)&v31);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"Creating render device",
    "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice",
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    0x69u);
  v6 = ppImmediateContext;
  ppImmediateContext = 0;
  if ( v6 )
    ((void (__fastcall *)(ID3D11DeviceContext *))v6->lpVtbl->Release)(v6);
  v7 = ppDevice;
  ppDevice = 0;
  if ( v7 )
    ((void (__fastcall *)(ID3D11Device *))v7->lpVtbl->Release)(v7);
  v8 = D3D11CreateDevice(a2, D3D_DRIVER_TYPE_UNKNOWN, 0, 0x20u, 0, 0, 7u, &ppDevice, 0, &ppImmediateContext);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x77,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v8,
    (int)"D3D11CreateDevice failed",
    FeatureLevelsa);
  memset_0(v37, 0, 0x140u);
  v9 = ((__int64 (__fastcall *)(IDXGIAdapter *, _BYTE *))a2->lpVtbl[1].AddRef)(a2, v37);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v9,
    (int)"Failed to get DXGI adapter description",
    FeatureLevelsb);
  *((_BYTE *)this + 8) = (v46 & 2) != 0;
  if ( (unsigned int)dword_18003C058 > 4 )
  {
    v20 = *((unsigned __int8 *)this + 8);
    v32 = v45;
    v23 = v46;
    v24 = v44;
    v25 = v43;
    v26 = v42;
    v27 = v41;
    v28 = v40;
    LODWORD(v29) = v39;
    LODWORD(v30) = v38;
    v33 = v37;
    v34 = "Render device created";
    v35 = "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice";
    LODWORD(v31) = 142;
    v36[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_180035F7B,
      v10,
      v11,
      (__int64)v36,
      (__int64)&v31,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v32,
      (__int64)&v20);
  }
  FeatureLevels[0] = *((unsigned __int8 *)this + 8);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"RenderDevice: IsWarp: %d",
    "Rdp::Utils::Graphics::CRenderDevice::CRenderDevice",
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    0x8Fu,
    *(_QWORD *)FeatureLevels);
  v12 = ppDevice;
  ppDevice = 0;
  v13 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v12;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = ppImmediateContext;
  ppImmediateContext = 0;
  v15 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v14;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&ppImmediateContext);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&ppDevice);
  return this;
}

```

## disassembly

```asm
0x1800205d4  mov     [rsp-8+arg_10], rbx
0x1800205d9  push    rbp
0x1800205da  push    rsi
0x1800205db  push    rdi
0x1800205dc  push    r14
0x1800205de  push    r15
0x1800205e0  lea     rbp, [rsp-150h]
0x1800205e8  sub     rsp, 270h
0x1800205ef  mov     rax, cs:__security_cookie
0x1800205f6  xor     rax, rsp
0x1800205f9  mov     [rbp+170h+var_30], rax
0x180020600  mov     rdi, rdx
0x180020603  mov     rbx, rcx
0x180020606  mov     [rbp+170h+var_180], rcx
0x18002060a  lea     rax, ??_7CRenderDevice@Graphics@Utils@Rdp@@6B@; const Rdp::Utils::Graphics::CRenderDevice::`vftable'
0x180020611  mov     [rcx], rax
0x180020614  xor     esi, esi
0x180020616  mov     [rcx+8], sil
0x18002061a  mov     [rcx+10h], rsi
0x18002061e  mov     [rcx+18h], rsi
0x180020622  mov     [rbp+170h+var_1E0], rsi
0x180020626  mov     [rbp+170h+var_1E8], rsi
0x18002062a  mov     eax, cs:dword_18003C058
0x180020630  lea     r15, aRdpUtilsGraphi_0; "Rdp::Utils::Graphics::CRenderDevice::CR"...
0x180020637  lea     r14, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002063e  cmp     eax, 4
0x180020641  jbe     short loc_180020694
0x180020643  lea     rax, aCreatingRender; "Creating render device"
0x18002064a  mov     [rbp+170h+var_1B0], rax
0x18002064e  mov     [rbp+170h+var_1B8], r15
0x180020652  mov     [rbp+170h+var_1F0], 68h ; 'h'
0x180020659  mov     [rbp+170h+var_1C0], r14
0x18002065d  lea     rax, [rbp+170h+var_1B0]
0x180020661  mov     [rsp+290h+ppDevice], rax
0x180020666  lea     rax, [rbp+170h+var_1B8]
0x18002066a  mov     qword ptr [rsp+290h+SDKVersion], rax
0x18002066f  lea     rax, [rbp+170h+var_1F0]
0x180020673  mov     qword ptr [rsp+290h+FeatureLevels], rax
0x180020678  lea     rax, [rbp+170h+var_1C0]
0x18002067c  mov     [rsp+290h+pFeatureLevels], rax
0x180020681  lea     rdx, dword_180035F44
0x180020688  lea     rcx, dword_18003C058
0x18002068f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180020694  mov     dword ptr [rsp+290h+pFeatureLevels], 69h ; 'i'; unsigned int
0x18002069c  mov     r9, r14; char *
0x18002069f  mov     r8, r15; char *
0x1800206a2  lea     rdx, aCreatingRender_0; "Creating render device"
0x1800206a9  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800206b0  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x1800206b5  nop
0x1800206b6  mov     rcx, [rbp+170h+var_1E8]
0x1800206ba  mov     [rbp+170h+var_1E8], rsi
0x1800206be  test    rcx, rcx
0x1800206c1  jz      short loc_1800206D0
0x1800206c3  mov     rax, [rcx]
0x1800206c6  mov     rax, [rax+10h]
0x1800206ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206cf  nop
0x1800206d0  mov     rcx, [rbp+170h+var_1E0]
0x1800206d4  mov     [rbp+170h+var_1E0], rsi
0x1800206d8  test    rcx, rcx
0x1800206db  jz      short loc_1800206EA
0x1800206dd  mov     rax, [rcx]
0x1800206e0  mov     rax, [rax+10h]
0x1800206e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206e9  nop
0x1800206ea  lea     rax, [rbp+170h+var_1E8]
0x1800206ee  mov     [rsp+290h+ppImmediateContext], rax; ppImmediateContext
0x1800206f3  mov     [rsp+290h+pFeatureLevel], rsi; pFeatureLevel
0x1800206f8  lea     rax, [rbp+170h+var_1E0]
0x1800206fc  mov     [rsp+290h+ppDevice], rax; ppDevice
0x180020701  mov     [rsp+290h+SDKVersion], 7; SDKVersion
0x180020709  mov     [rsp+290h+FeatureLevels], esi; char *
0x18002070d  mov     [rsp+290h+pFeatureLevels], rsi; pFeatureLevels
0x180020712  mov     r9d, 20h ; ' '; Flags
0x180020718  xor     r8d, r8d; Software
0x18002071b  xor     edx, edx; DriverType
0x18002071d  mov     rcx, rdi; pAdapter
0x180020720  call    cs:__imp_D3D11CreateDevice
0x180020726  mov     rcx, [rbp+178h]; this
0x18002072d  lea     rdx, aD3d11createdev; "D3D11CreateDevice failed"
0x180020734  mov     [rsp+290h+pFeatureLevels], rdx; int
0x180020739  mov     r9d, eax; char *
0x18002073c  mov     r8, r14; unsigned int
0x18002073f  mov     edx, 77h ; 'w'; void *
0x180020744  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020749  xor     edx, edx; Val
0x18002074b  mov     r8d, 140h; Size
0x180020751  lea     rcx, [rbp+170h+var_170]; void *
0x180020755  call    memset_0
0x18002075a  mov     rax, [rdi]
0x18002075d  lea     rdx, [rbp+170h+var_170]
0x180020761  mov     rcx, rdi
0x180020764  mov     rax, [rax+58h]
0x180020768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002076d  mov     rcx, [rbp+178h]; this
0x180020774  lea     rdx, aFailedToGetDxg; "Failed to get DXGI adapter description"
0x18002077b  mov     [rsp+290h+pFeatureLevels], rdx; int
0x180020780  mov     r9d, eax; char *
0x180020783  mov     r8, r14; unsigned int
0x180020786  mov     edx, 7Eh ; '~'; void *
0x18002078b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020790  mov     eax, [rbp+170h+var_40]
0x180020796  shr     eax, 1
0x180020798  and     al, 1
0x18002079a  mov     [rbx+8], al
0x18002079d  mov     eax, cs:dword_18003C058
0x1800207a3  cmp     eax, 4
0x1800207a6  jbe     loc_1800208CB
0x1800207ac  movzx   eax, byte ptr [rbx+8]
0x1800207b0  mov     [rbp+170h+var_1F0], eax
0x1800207b3  mov     rax, [rbp+170h+var_48]
0x1800207ba  mov     [rbp+170h+var_1A8], rax
0x1800207be  mov     eax, [rbp+170h+var_40]
0x1800207c4  mov     [rbp+170h+var_1D8], eax
0x1800207c7  mov     eax, [rbp+170h+var_50]
0x1800207cd  mov     [rbp+170h+var_1D4], eax
0x1800207d0  mov     eax, [rbp+170h+var_58]
0x1800207d6  mov     [rbp+170h+var_1D0], eax
0x1800207d9  mov     eax, [rbp+170h+var_60]
0x1800207df  mov     [rbp+170h+var_1CC], eax
0x1800207e2  mov     eax, [rbp+170h+var_64]
0x1800207e8  mov     [rbp+170h+var_1C8], eax
0x1800207eb  mov     eax, [rbp+170h+var_68]
0x1800207f1  mov     [rbp+170h+var_1C4], eax
0x1800207f4  mov     eax, [rbp+170h+var_6C]
0x1800207fa  mov     dword ptr [rbp+170h+var_1C0], eax
0x1800207fd  mov     eax, [rbp+170h+var_70]
0x180020803  mov     dword ptr [rbp+170h+var_1B8], eax
0x180020806  lea     rax, [rbp+170h+var_170]
0x18002080a  mov     [rbp+170h+var_1A0], rax
0x18002080e  lea     rax, aRenderDeviceCr; "Render device created"
0x180020815  mov     [rbp+170h+var_198], rax
0x180020819  mov     [rbp+170h+var_190], r15
0x18002081d  mov     dword ptr [rbp+170h+var_1B0], 8Eh
0x180020824  mov     [rbp+170h+var_188], r14
0x180020828  lea     rax, [rbp+170h+var_1F0]
0x18002082c  mov     [rsp+290h+var_200], rax
0x180020834  lea     rax, [rbp+170h+var_1A8]
0x180020838  mov     [rsp+290h+var_208], rax
0x180020840  lea     rax, [rbp+170h+var_1D8]
0x180020844  mov     [rsp+290h+var_210], rax
0x18002084c  lea     rax, [rbp+170h+var_1D4]
0x180020850  mov     [rsp+290h+var_218], rax
0x180020855  lea     rax, [rbp+170h+var_1D0]
0x180020859  mov     [rsp+290h+var_220], rax
0x18002085e  lea     rax, [rbp+170h+var_1CC]
0x180020862  mov     [rsp+290h+var_228], rax
0x180020867  lea     rax, [rbp+170h+var_1C8]
0x18002086b  mov     [rsp+290h+var_230], rax
0x180020870  lea     rax, [rbp+170h+var_1C4]
0x180020874  mov     [rsp+290h+var_238], rax
0x180020879  lea     rax, [rbp+170h+var_1C0]
0x18002087d  mov     [rsp+290h+var_240], rax
0x180020882  lea     rax, [rbp+170h+var_1B8]
0x180020886  mov     [rsp+290h+ppImmediateContext], rax
0x18002088b  lea     rax, [rbp+170h+var_1A0]
0x18002088f  mov     [rsp+290h+pFeatureLevel], rax
0x180020894  lea     rax, [rbp+170h+var_198]
0x180020898  mov     [rsp+290h+ppDevice], rax
0x18002089d  lea     rax, [rbp+170h+var_190]
0x1800208a1  mov     qword ptr [rsp+290h+SDKVersion], rax
0x1800208a6  lea     rax, [rbp+170h+var_1B0]
0x1800208aa  mov     qword ptr [rsp+290h+FeatureLevels], rax
0x1800208af  lea     rax, [rbp+170h+var_188]
0x1800208b3  mov     [rsp+290h+pFeatureLevels], rax
0x1800208b8  lea     rdx, byte_180035F7B
0x1800208bf  lea     rcx, dword_18003C058
0x1800208c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@44444444AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800208cb  movzx   eax, byte ptr [rbx+8]
0x1800208cf  mov     [rsp+290h+FeatureLevels], eax
0x1800208d3  mov     dword ptr [rsp+290h+pFeatureLevels], 8Fh; unsigned int
0x1800208db  mov     r9, r14; char *
0x1800208de  mov     r8, r15; char *
0x1800208e1  lea     rdx, aRenderdeviceIs; "RenderDevice: IsWarp: %d"
0x1800208e8  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800208ef  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800208f4  mov     rax, [rbp+170h+var_1E0]
0x1800208f8  mov     [rbp+170h+var_1E0], rsi
0x1800208fc  mov     rcx, [rbx+10h]
0x180020900  mov     [rbx+10h], rax
0x180020904  test    rcx, rcx
0x180020907  jz      short loc_180020916
0x180020909  mov     rax, [rcx]
0x18002090c  mov     rax, [rax+10h]
0x180020910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020915  nop
0x180020916  mov     rax, [rbp+170h+var_1E8]
0x18002091a  mov     [rbp+170h+var_1E8], rsi
0x18002091e  mov     rcx, [rbx+18h]
0x180020922  mov     [rbx+18h], rax
0x180020926  test    rcx, rcx
0x180020929  jz      short loc_180020938
0x18002092b  mov     rax, [rcx]
0x18002092e  mov     rax, [rax+10h]
0x180020932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020937  nop
0x180020938  lea     rcx, [rbp+170h+var_1E8]
0x18002093c  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180020941  nop
0x180020942  lea     rcx, [rbp+170h+var_1E0]
0x180020946  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18002094b  nop
0x18002094c  mov     rax, rbx
0x18002094f  mov     rcx, [rbp+170h+var_30]
0x180020956  xor     rcx, rsp; StackCookie
0x180020959  call    __security_check_cookie
0x18002095e  mov     rbx, [rsp+290h+arg_10]
0x180020966  add     rsp, 270h
0x18002096d  pop     r15
0x18002096f  pop     r14
0x180020971  pop     rdi
0x180020972  pop     rsi
0x180020973  pop     rbp
0x180020974  retn
```
