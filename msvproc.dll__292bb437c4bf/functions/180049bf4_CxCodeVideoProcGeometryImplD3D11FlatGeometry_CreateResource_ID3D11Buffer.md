# CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource(ID3D11Buffer * *)

- ea: `0x180049bf4`
- end: `0x180049d88`
- name: `?CreateResource@CxCodeVideoProcGeometryImplD3D11FlatGeometry@@IEAAJPEAPEAUID3D11Buffer@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(CxCodeVideoProcGeometryImplD3D11FlatGeometry *__hidden this, struct ID3D11Buffer **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180043350`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180049bf4`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049c98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049c98`

## string_xrefs

- `0x180049c1a`: `CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource`
- `0x180049cef`: `CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource(
        CxCodeVideoProcGeometryImplD3D11FlatGeometry *this,
        struct ID3D11Buffer **a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v10[8]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v11[2]; // [rsp+38h] [rbp-38h] BYREF
  _DWORD v12[4]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v10,
    "CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource",
    126);
  v4 = *((_QWORD *)this + 1);
  v11[0] = &CxCodeVideoProcD3DFlatGeometry::m_svDefaultFlatGeometry;
  v13 = 0;
  v12[1] = 2;
  v12[2] = 1;
  v12[3] = 0x10000;
  v12[0] = 96;
  v11[1] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD *, struct ID3D11Buffer **))(*(_QWORD *)v4 + 24LL))(
         v4,
         v12,
         v11,
         a2);
  if ( v5 < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource",
          140,
          v5);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9ed8b548847234ef96bd260641d768de_Traceguids, this, v5);
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 42), 16, WPP_9ed8b548847234ef96bd260641d768de_Traceguids, this, v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180049bf4  mov     [rsp-8+arg_10], rbx
0x180049bf9  mov     [rsp-8+arg_18], rdi
0x180049bfe  push    rbp
0x180049bff  mov     rbp, rsp
0x180049c02  sub     rsp, 70h
0x180049c06  mov     rax, cs:__security_cookie
0x180049c0d  xor     rax, rsp
0x180049c10  mov     [rbp+var_10], rax
0x180049c14  mov     rbx, rdx
0x180049c17  mov     rdi, rcx
0x180049c1a  lea     rdx, aCxcodevideopro_179; "CxCodeVideoProcGeometryImplD3D11FlatGeo"...
0x180049c21  mov     r8d, 7Eh ; '~'; int
0x180049c27  lea     rcx, [rbp+var_40]; this
0x180049c2b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180049c30  mov     rcx, [rdi+8]
0x180049c34  lea     rax, ?m_svDefaultFlatGeometry@CxCodeVideoProcD3DFlatGeometry@@2QBUScreenVertex@@B; ScreenVertex const near * const CxCodeVideoProcD3DFlatGeometry::m_svDefaultFlatGeometry
0x180049c3b  mov     [rbp+var_38], rax
0x180049c3f  lea     r8, [rbp+var_38]
0x180049c43  mov     [rbp+var_18], 0
0x180049c4b  lea     rdx, [rbp+var_28]
0x180049c4f  mov     [rbp+var_24], 2
0x180049c56  mov     r9, rbx
0x180049c59  mov     [rbp+var_20], 1
0x180049c60  mov     [rbp+var_1C], 10000h
0x180049c67  mov     [rbp+var_28], 60h ; '`'
0x180049c6e  mov     [rbp+var_30], 0
0x180049c76  mov     rax, [rcx]
0x180049c79  mov     rax, [rax+18h]
0x180049c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c82  mov     ebx, eax
0x180049c84  test    eax, eax
0x180049c86  jns     loc_180049D30
0x180049c8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049c93  test    rcx, rcx
0x180049c96  jnz     short loc_180049CD9
0x180049c98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049c9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049ca5  mov     rcx, rax
0x180049ca8  test    rax, rax
0x180049cab  jz      short loc_180049CCB
0x180049cad  mov     rax, [rax]
0x180049cb0  mov     edx, 7F0h
0x180049cb5  mov     rax, [rax+8]
0x180049cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cbe  test    eax, eax
0x180049cc0  jz      short loc_180049CCB
0x180049cc2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049cc9  jmp     short loc_180049CD9
0x180049ccb  lea     rcx, qword_180153440; this
0x180049cd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049cd9  cmp     byte ptr [rcx+8], 0
0x180049cdd  jz      short loc_180049D04
0x180049cdf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049ce4  cmp     [rax+7CCh], ebx
0x180049cea  jz      short loc_180049D04
0x180049cec  mov     r9d, ebx; int
0x180049cef  lea     rdx, aCxcodevideopro_179; "CxCodeVideoProcGeometryImplD3D11FlatGeo"...
0x180049cf6  mov     r8d, 8Ch; int
0x180049cfc  mov     rcx, rax; this
0x180049cff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049d04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049d0b  jb      short loc_180049D30
0x180049d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d14  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x180049d1b  mov     edx, 0Fh
0x180049d20  mov     [rsp+70h+var_50], ebx
0x180049d24  mov     r9, rdi
0x180049d27  mov     rcx, [rcx+10h]
0x180049d2b  call    WPP_SF_qD
0x180049d30  cmp     cs:byte_180153DE0, 20h ; ' '
0x180049d37  jb      short loc_180049D5F
0x180049d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d40  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x180049d47  mov     edx, 10h
0x180049d4c  mov     [rsp+70h+var_50], ebx
0x180049d50  mov     r9, rdi
0x180049d53  mov     rcx, [rcx+150h]
0x180049d5a  call    WPP_SF_qD
0x180049d5f  lea     rcx, [rbp+var_40]; this
0x180049d63  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180049d68  mov     eax, ebx
0x180049d6a  mov     rcx, [rbp+var_10]
0x180049d6e  xor     rcx, rsp; StackCookie
0x180049d71  call    __security_check_cookie
0x180049d76  lea     r11, [rsp+70h+var_s0]
0x180049d7b  mov     rbx, [r11+20h]
0x180049d7f  mov     rdi, [r11+28h]
0x180049d83  mov     rsp, r11
0x180049d86  pop     rbp
0x180049d87  retn
```
