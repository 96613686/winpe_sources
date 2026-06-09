# Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter(_LUID const &)

- ea: `0x1800202a4`
- end: `0x1800205cd`
- name: `??0CRenderAdapter@Graphics@Utils@Rdp@@QEAA@AEBU_LUID@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(Rdp::Utils::Graphics::CRenderAdapter *__hidden this, const struct _LUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022330`

## callees

- `0x180002d44`
- `0x180004154`
- `0x180007b28`
- `0x18000cf28`
- `0x18000d98c`
- `0x1800202a4`
- `0x18002a010`

## import_xrefs

- `dxgi!CreateDXGIFactory2` at `0x1800202fa`
- `dxgi!CreateDXGIFactory2` at `0x1800202fa`

## string_xrefs

- `0x180020304`: `Failed to create DXGI factory`
- `0x180020313`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RenderAdapter.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Rdp::Utils::Graphics::CRenderAdapter *__fastcall Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter(
        Rdp::Utils::Graphics::CRenderAdapter *this,
        const struct _LUID *a2)
{
  char *v4; // r14
  unsigned int v5; // eax
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rcx
  char *v15; // [rsp+28h] [rbp-F8h]
  char *v16; // [rsp+28h] [rbp-F8h]
  char *v17; // [rsp+28h] [rbp-F8h]
  char *v18; // [rsp+28h] [rbp-F8h]
  DWORD LowPart; // [rsp+30h] [rbp-F0h]
  __int64 v20; // [rsp+A0h] [rbp-80h] BYREF
  void *ppFactory; // [rsp+A8h] [rbp-78h] BYREF
  int v22; // [rsp+B0h] [rbp-70h] BYREF
  int v23; // [rsp+B4h] [rbp-6Ch] BYREF
  int v24; // [rsp+B8h] [rbp-68h] BYREF
  int v25; // [rsp+BCh] [rbp-64h] BYREF
  int v26; // [rsp+C0h] [rbp-60h] BYREF
  int v27; // [rsp+C4h] [rbp-5Ch] BYREF
  int v28; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-50h] BYREF
  char *v30; // [rsp+D8h] [rbp-48h] BYREF
  const char *v31; // [rsp+E0h] [rbp-40h] BYREF
  const char *v32; // [rsp+E8h] [rbp-38h] BYREF
  const char *v33; // [rsp+F0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+18h]
  int v35; // [rsp+148h] [rbp+28h] BYREF
  int v36; // [rsp+150h] [rbp+30h] BYREF
  int v37; // [rsp+158h] [rbp+38h] BYREF

  *(_BYTE *)this = 0;
  v4 = (char *)this + 8;
  memset_0((char *)this + 8, 0, 0x140u);
  *((_QWORD *)this + 41) = 0;
  ppFactory = 0;
  v5 = CreateDXGIFactory2(0, &GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, &ppFactory);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF8,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v5,
    (int)"Failed to create DXGI factory",
    v15);
  v20 = 0;
  v6 = *(_QWORD *)ppFactory;
  if ( *a2 )
  {
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(v6 + 208))(
           ppFactory,
           *a2,
           &GUID_645967a4_1392_4310_a798_8053ce3e93fd,
           &v20);
    LowPart = a2->LowPart;
    LODWORD(v16) = a2->HighPart;
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
      (const char *)v8,
      (int)"Failed to enumerate render adapter by LUID: {%#x,%#x}",
      v16,
      LowPart);
  }
  else
  {
    v20 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, GUID *, __int64 *))(v6 + 216))(
           ppFactory,
           &GUID_645967a4_1392_4310_a798_8053ce3e93fd,
           &v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
      (const char *)v7,
      (int)"Failed to enumerate WARP render adapter",
      v16);
  }
  v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v20 + 88LL))(v20, v4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x117,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v9,
    (int)"Failed to get DXGI adapter description",
    v17);
  *(_BYTE *)this = (*((_DWORD *)this + 78) & 2) != 0;
  if ( (unsigned int)dword_18003C058 > 4 )
  {
    v35 = *(unsigned __int8 *)this;
    v29 = *((_QWORD *)this + 38);
    v36 = *((_DWORD *)this + 78);
    v37 = *((_DWORD *)this + 74);
    v22 = *((_DWORD *)this + 72);
    v23 = *((_DWORD *)this + 70);
    v24 = *((_DWORD *)this + 69);
    v25 = *((_DWORD *)this + 68);
    v26 = *((_DWORD *)this + 67);
    v27 = *((_DWORD *)this + 66);
    v30 = v4;
    v31 = "Adapter description";
    v32 = "Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter";
    v28 = 295;
    v33 = "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&byte_18003626F,
      v10,
      v11,
      (__int64)&v33,
      (__int64)&v28,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v29,
      (__int64)&v35);
  }
  LODWORD(v18) = *(unsigned __int8 *)this;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"RenderAdapter: IsWarp: %d",
    "Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter",
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    0x128u,
    v18);
  v12 = v20;
  v20 = 0;
  v13 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = v12;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v20);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&ppFactory);
  return this;
}

```

## disassembly

```asm
0x1800202a4  mov     [rsp-8+arg_0], rcx
0x1800202a9  push    rbp
0x1800202aa  push    rbx
0x1800202ab  push    rsi
0x1800202ac  push    rdi
0x1800202ad  push    r12
0x1800202af  push    r14
0x1800202b1  lea     rbp, [rsp+18h]
0x1800202b6  sub     rsp, 108h
0x1800202bd  mov     rsi, rdx
0x1800202c0  mov     rbx, rcx
0x1800202c3  mov     byte ptr [rcx], 0
0x1800202c6  lea     r14, [rcx+8]
0x1800202ca  xor     edx, edx; Val
0x1800202cc  mov     r8d, 140h; Size
0x1800202d2  mov     rcx, r14; void *
0x1800202d5  call    memset_0
0x1800202da  mov     qword ptr [rbx+148h], 0
0x1800202e5  mov     [rbp+10h+ppFactory], 0
0x1800202ed  lea     r8, [rbp+10h+ppFactory]; ppFactory
0x1800202f1  lea     rdx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x1800202f8  xor     ecx, ecx; Flags
0x1800202fa  call    cs:__imp_CreateDXGIFactory2
0x180020300  mov     rcx, [rbp+18h]; this
0x180020304  lea     rdx, aFailedToCreate_0; "Failed to create DXGI factory"
0x18002030b  mov     qword ptr [rsp+130h+var_110], rdx; int
0x180020310  mov     r9d, eax; char *
0x180020313  lea     r12, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002031a  mov     r8, r12; unsigned int
0x18002031d  mov     edx, 0F8h; void *
0x180020322  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020327  mov     [rbp+10h+var_90], 0
0x18002032f  mov     rax, cs:qword_180033460
0x180020336  cmp     eax, [rsi]
0x180020338  jnz     short loc_18002038D
0x18002033a  mov     eax, dword ptr cs:qword_180033460+4
0x180020340  cmp     eax, [rsi+4]
0x180020343  jnz     short loc_18002038D
0x180020345  mov     rcx, [rbp+10h+ppFactory]
0x180020349  mov     rax, [rcx]
0x18002034c  mov     [rbp+10h+var_90], 0
0x180020354  lea     r8, [rbp+10h+var_90]
0x180020358  lea     rdx, _GUID_645967a4_1392_4310_a798_8053ce3e93fd
0x18002035f  mov     rax, [rax+0D8h]
0x180020366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002036b  mov     rcx, [rbp+18h]; this
0x18002036f  lea     rdx, aFailedToEnumer_0; "Failed to enumerate WARP render adapter"
0x180020376  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18002037b  mov     r9d, eax; char *
0x18002037e  mov     r8, r12; unsigned int
0x180020381  mov     edx, 104h; void *
0x180020386  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002038b  jmp     short loc_1800203E3
0x18002038d  mov     rcx, [rbp+10h+ppFactory]
0x180020391  mov     rax, [rcx]
0x180020394  mov     [rbp+10h+var_90], 0
0x18002039c  lea     r9, [rbp+10h+var_90]
0x1800203a0  lea     r8, _GUID_645967a4_1392_4310_a798_8053ce3e93fd
0x1800203a7  mov     rdx, [rsi]
0x1800203aa  mov     rax, [rax+0D0h]
0x1800203b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203b6  mov     rcx, [rbp+18h]; this
0x1800203ba  mov     edx, [rsi]
0x1800203bc  mov     dword ptr [rsp+130h+var_100], edx
0x1800203c0  mov     edx, [rsi+4]
0x1800203c3  mov     dword ptr [rsp+130h+var_108], edx; char *
0x1800203c7  lea     rdx, aFailedToEnumer; "Failed to enumerate render adapter by L"...
0x1800203ce  mov     qword ptr [rsp+130h+var_110], rdx; int
0x1800203d3  mov     r9d, eax; char *
0x1800203d6  mov     r8, r12; unsigned int
0x1800203d9  mov     edx, 110h; void *
0x1800203de  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800203e3  mov     rcx, [rbp+10h+var_90]
0x1800203e7  mov     rax, [rcx]
0x1800203ea  mov     rdx, r14
0x1800203ed  mov     rax, [rax+58h]
0x1800203f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203f6  mov     rcx, [rbp+18h]; this
0x1800203fa  lea     rdx, aFailedToGetDxg; "Failed to get DXGI adapter description"
0x180020401  mov     qword ptr [rsp+130h+var_110], rdx; int
0x180020406  mov     r9d, eax; char *
0x180020409  mov     r8, r12; unsigned int
0x18002040c  mov     edx, 117h; void *
0x180020411  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180020416  mov     eax, [rbx+138h]
0x18002041c  shr     eax, 1
0x18002041e  and     al, 1
0x180020420  mov     [rbx], al
0x180020422  mov     eax, cs:dword_18003C058
0x180020428  lea     rdi, aRdpUtilsGraphi; "Rdp::Utils::Graphics::CRenderAdapter::C"...
0x18002042f  cmp     eax, 4
0x180020432  jbe     loc_180020552
0x180020438  movzx   eax, byte ptr [rbx]
0x18002043b  mov     [rbp+10h+arg_8], eax
0x18002043e  mov     rax, [rbx+130h]
0x180020445  mov     [rbp+10h+var_60], rax
0x180020449  mov     eax, [rbx+138h]
0x18002044f  mov     [rbp+10h+arg_10], eax
0x180020452  mov     eax, [rbx+128h]
0x180020458  mov     [rbp+10h+arg_18], eax
0x18002045b  mov     eax, [rbx+120h]
0x180020461  mov     [rbp+10h+var_80], eax
0x180020464  mov     eax, [rbx+118h]
0x18002046a  mov     [rbp+10h+var_7C], eax
0x18002046d  mov     eax, [rbx+114h]
0x180020473  mov     [rbp+10h+var_78], eax
0x180020476  mov     eax, [rbx+110h]
0x18002047c  mov     [rbp+10h+var_74], eax
0x18002047f  mov     eax, [rbx+10Ch]
0x180020485  mov     [rbp+10h+var_70], eax
0x180020488  mov     eax, [rbx+108h]
0x18002048e  mov     [rbp+10h+var_6C], eax
0x180020491  mov     [rbp+10h+var_58], r14
0x180020495  lea     rax, aAdapterDescrip; "Adapter description"
0x18002049c  mov     [rbp+10h+var_50], rax
0x1800204a0  mov     [rbp+10h+var_48], rdi
0x1800204a4  mov     [rbp+10h+var_68], 127h
0x1800204ab  mov     [rbp+10h+var_40], r12
0x1800204af  lea     rax, [rbp+10h+arg_8]
0x1800204b3  mov     [rsp+130h+var_A0], rax
0x1800204bb  lea     rax, [rbp+10h+var_60]
0x1800204bf  mov     [rsp+130h+var_A8], rax
0x1800204c7  lea     rax, [rbp+10h+arg_10]
0x1800204cb  mov     [rsp+130h+var_B0], rax
0x1800204d3  lea     rax, [rbp+10h+arg_18]
0x1800204d7  mov     [rsp+130h+var_B8], rax
0x1800204dc  lea     rax, [rbp+10h+var_80]
0x1800204e0  mov     [rsp+130h+var_C0], rax
0x1800204e5  lea     rax, [rbp+10h+var_7C]
0x1800204e9  mov     [rsp+130h+var_C8], rax
0x1800204ee  lea     rax, [rbp+10h+var_78]
0x1800204f2  mov     [rsp+130h+var_D0], rax
0x1800204f7  lea     rax, [rbp+10h+var_74]
0x1800204fb  mov     [rsp+130h+var_D8], rax
0x180020500  lea     rax, [rbp+10h+var_70]
0x180020504  mov     [rsp+130h+var_E0], rax
0x180020509  lea     rax, [rbp+10h+var_6C]
0x18002050d  mov     [rsp+130h+var_E8], rax
0x180020512  lea     rax, [rbp+10h+var_58]
0x180020516  mov     [rsp+130h+var_F0], rax
0x18002051b  lea     rax, [rbp+10h+var_50]
0x18002051f  mov     [rsp+130h+var_F8], rax
0x180020524  lea     rax, [rbp+10h+var_48]
0x180020528  mov     [rsp+130h+var_100], rax
0x18002052d  lea     rax, [rbp+10h+var_68]
0x180020531  mov     [rsp+130h+var_108], rax
0x180020536  lea     rax, [rbp+10h+var_40]
0x18002053a  mov     qword ptr [rsp+130h+var_110], rax
0x18002053f  lea     rdx, byte_18003626F
0x180020546  lea     rcx, dword_18003C058
0x18002054d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@44444444AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180020552  movzx   eax, byte ptr [rbx]
0x180020555  mov     dword ptr [rsp+130h+var_108], eax
0x180020559  mov     [rsp+130h+var_110], 128h; unsigned int
0x180020561  mov     r9, r12; char *
0x180020564  mov     r8, rdi; char *
0x180020567  lea     rdx, aRenderadapterI; "RenderAdapter: IsWarp: %d"
0x18002056e  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180020575  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002057a  mov     rax, [rbp+10h+var_90]
0x18002057e  mov     [rbp+10h+var_90], 0
0x180020586  mov     rcx, [rbx+148h]
0x18002058d  mov     [rbx+148h], rax
0x180020594  test    rcx, rcx
0x180020597  jz      short loc_1800205A6
0x180020599  mov     rax, [rcx]
0x18002059c  mov     rax, [rax+10h]
0x1800205a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205a5  nop
0x1800205a6  lea     rcx, [rbp+10h+var_90]
0x1800205aa  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800205af  nop
0x1800205b0  lea     rcx, [rbp+10h+ppFactory]
0x1800205b4  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800205b9  nop
0x1800205ba  mov     rax, rbx
0x1800205bd  add     rsp, 108h
0x1800205c4  pop     r14
0x1800205c6  pop     r12
0x1800205c8  pop     rdi
0x1800205c9  pop     rsi
0x1800205ca  pop     rbx
0x1800205cb  pop     rbp
0x1800205cc  retn
```
