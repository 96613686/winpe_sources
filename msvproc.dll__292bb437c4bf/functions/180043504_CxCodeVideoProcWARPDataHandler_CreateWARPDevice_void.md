# CxCodeVideoProcWARPDataHandler::CreateWARPDevice(void)

- ea: `0x180043504`
- end: `0x1800436f0`
- name: `?CreateWARPDevice@CxCodeVideoProcWARPDataHandler@@QEAAJXZ`
- size: `492`
- prototype: `__int64 __fastcall(CxCodeVideoProcWARPDataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005ef34`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800116a0`
- `0x18003639c`
- `0x180043504`
- `0x1800d1010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x180043578`
- `d3d11!D3D11CreateDevice` at `0x180043578`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043594`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004363c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043594`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004363c`

## string_xrefs

- `0x180043516`: `CxCodeVideoProcWARPDataHandler::CreateWARPDevice`
- `0x1800435eb`: `CxCodeVideoProcWARPDataHandler::CreateWARPDevice`
- `0x180043693`: `CxCodeVideoProcWARPDataHandler::CreateWARPDevice`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcWARPDataHandler::CreateWARPDevice(ID3D11Device **this)
{
  HRESULT Device; // ebx
  __int64 *v3; // rcx
  CallStackTracing *v4; // rax
  struct CallStackContext *v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+60h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
    "CxCodeVideoProcWARPDataHandler::CreateWARPDevice",
    228);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 146);
  Device = D3D11CreateDevice(0, D3D_DRIVER_TYPE_WARP, 0, 0, 0, 0, 7u, this + 146, 0, 0);
  if ( Device >= 0 )
  {
    Device = CxCodeVideoProcD3D11DataHandler::OnNewDevice(
               (CxCodeVideoProcD3D11DataHandler *)(this + 154),
               (struct IUnknown *)this[146]);
    if ( Device < 0 )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Device )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcWARPDataHandler::CreateWARPDevice",
            229,
            Device);
      }
      if ( g_wppLevels )
      {
        v6 = 37;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v4 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v4;
      if ( v4 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v4 + 8LL))(v4, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v5 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v5 + 499) != Device )
        CallStackContext::TraceFailure(v5, "CxCodeVideoProcWARPDataHandler::CreateWARPDevice", 228, Device);
    }
    if ( g_wppLevels )
    {
      v6 = 36;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids, this, Device);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x180043504  mov     [rsp+arg_8], rbx
0x180043509  mov     [rsp+arg_10], rsi
0x18004350e  push    rdi
0x18004350f  sub     rsp, 50h
0x180043513  mov     rdi, rcx
0x180043516  lea     rdx, aCxcodevideopro_82; "CxCodeVideoProcWARPDataHandler::CreateW"...
0x18004351d  lea     rcx, [rsp+58h+arg_0]; this
0x180043522  mov     r8d, 0E4h; int
0x180043528  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004352d  lea     rsi, [rdi+490h]
0x180043534  mov     rcx, rsi
0x180043537  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004353c  mov     [rsp+58h+ppImmediateContext], 0; ppImmediateContext
0x180043545  xor     r9d, r9d; Flags
0x180043548  mov     [rsp+58h+pFeatureLevel], 0; pFeatureLevel
0x180043551  xor     r8d, r8d; Software
0x180043554  mov     [rsp+58h+ppDevice], rsi; ppDevice
0x180043559  xor     ecx, ecx; pAdapter
0x18004355b  mov     [rsp+58h+SDKVersion], 7; SDKVersion
0x180043563  lea     edx, [r9+5]; DriverType
0x180043567  mov     [rsp+58h+FeatureLevels], 0; FeatureLevels
0x18004356f  mov     [rsp+58h+pFeatureLevels], 0; pFeatureLevels
0x180043578  call    cs:__imp_D3D11CreateDevice
0x18004357e  mov     ebx, eax
0x180043580  test    eax, eax
0x180043582  jns     loc_180043617
0x180043588  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004358f  test    rcx, rcx
0x180043592  jnz     short loc_1800435D5
0x180043594  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004359a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800435a1  mov     rcx, rax
0x1800435a4  test    rax, rax
0x1800435a7  jz      short loc_1800435C7
0x1800435a9  mov     rax, [rax]
0x1800435ac  mov     edx, 7F0h
0x1800435b1  mov     rax, [rax+8]
0x1800435b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435ba  test    eax, eax
0x1800435bc  jz      short loc_1800435C7
0x1800435be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800435c5  jmp     short loc_1800435D5
0x1800435c7  lea     rcx, qword_180153440; this
0x1800435ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800435d5  cmp     byte ptr [rcx+8], 0
0x1800435d9  jz      short loc_180043600
0x1800435db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800435e0  cmp     [rax+7CCh], ebx
0x1800435e6  jz      short loc_180043600
0x1800435e8  mov     r9d, ebx; int
0x1800435eb  lea     rdx, aCxcodevideopro_82; "CxCodeVideoProcWARPDataHandler::CreateW"...
0x1800435f2  mov     r8d, 0E4h; int
0x1800435f8  mov     rcx, rax; this
0x1800435fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043600  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043607  jb      loc_1800436D4
0x18004360d  mov     edx, 24h ; '$'
0x180043612  jmp     loc_1800436B6
0x180043617  mov     rdx, [rsi]; struct IUnknown *
0x18004361a  lea     rcx, [rdi+4D0h]; this
0x180043621  call    ?OnNewDevice@CxCodeVideoProcD3D11DataHandler@@UEAAJPEAUIUnknown@@@Z; CxCodeVideoProcD3D11DataHandler::OnNewDevice(IUnknown *)
0x180043626  mov     ebx, eax
0x180043628  test    eax, eax
0x18004362a  jns     loc_1800436D4
0x180043630  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043637  test    rcx, rcx
0x18004363a  jnz     short loc_18004367D
0x18004363c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043642  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043649  mov     rcx, rax
0x18004364c  test    rax, rax
0x18004364f  jz      short loc_18004366F
0x180043651  mov     rax, [rax]
0x180043654  mov     edx, 7F0h
0x180043659  mov     rax, [rax+8]
0x18004365d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043662  test    eax, eax
0x180043664  jz      short loc_18004366F
0x180043666  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004366d  jmp     short loc_18004367D
0x18004366f  lea     rcx, qword_180153440; this
0x180043676  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004367d  cmp     byte ptr [rcx+8], 0
0x180043681  jz      short loc_1800436A8
0x180043683  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043688  cmp     [rax+7CCh], ebx
0x18004368e  jz      short loc_1800436A8
0x180043690  mov     r9d, ebx; int
0x180043693  lea     rdx, aCxcodevideopro_82; "CxCodeVideoProcWARPDataHandler::CreateW"...
0x18004369a  mov     r8d, 0E5h; int
0x1800436a0  mov     rcx, rax; this
0x1800436a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800436a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800436af  jb      short loc_1800436D4
0x1800436b1  mov     edx, 25h ; '%'
0x1800436b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800436bd  lea     r8, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids
0x1800436c4  mov     r9, rdi
0x1800436c7  mov     dword ptr [rsp+58h+pFeatureLevels], ebx
0x1800436cb  mov     rcx, [rcx+10h]
0x1800436cf  call    WPP_SF_qD
0x1800436d4  lea     rcx, [rsp+58h+arg_0]; this
0x1800436d9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800436de  mov     rsi, [rsp+58h+arg_10]
0x1800436e3  mov     eax, ebx
0x1800436e5  mov     rbx, [rsp+58h+arg_8]
0x1800436ea  add     rsp, 50h
0x1800436ee  pop     rdi
0x1800436ef  retn
```
