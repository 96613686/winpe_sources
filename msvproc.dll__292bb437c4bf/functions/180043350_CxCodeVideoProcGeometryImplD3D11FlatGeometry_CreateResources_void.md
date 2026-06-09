# CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources(void)

- ea: `0x180043350`
- end: `0x1800434fb`
- name: `?CreateResources@CxCodeVideoProcGeometryImplD3D11FlatGeometry@@UEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CxCodeVideoProcGeometryImplD3D11FlatGeometry *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180043350`
- `0x180049bf4`
- `0x1800a00f0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800433ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004344c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800433ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004344c`

## string_xrefs

- `0x18004335d`: `CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources`
- `0x180043402`: `CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources`
- `0x1800434a3`: `CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources(struct ID3D11Buffer **this)
{
  int Resources; // ebx
  __int64 *v3; // rcx
  CallStackTracing *v4; // rax
  struct CallStackContext *v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v11; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v11,
    "CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources",
    113);
  if ( this[4]
    || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 4),
        Resources = CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource(
                      (CxCodeVideoProcGeometryImplD3D11FlatGeometry *)this,
                      this + 4),
        Resources >= 0) )
  {
    Resources = CxCodeVideoProcGeometryImplD3D11::CreateResources((CxCodeVideoProcGeometryImplD3D11 *)this);
    if ( Resources < 0 )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Resources )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources",
            118,
            Resources);
      }
      if ( g_wppLevels )
      {
        v6 = 13;
        goto LABEL_24;
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
      if ( *((_DWORD *)v5 + 499) != Resources )
        CallStackContext::TraceFailure(
          v5,
          "CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResources",
          116,
          Resources);
    }
    if ( g_wppLevels )
    {
      v6 = 12;
LABEL_24:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_9ed8b548847234ef96bd260641d768de_Traceguids,
        this,
        Resources);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return (unsigned int)Resources;
}

```

## disassembly

```asm
0x180043350  mov     [rsp+arg_8], rbx
0x180043355  push    rdi
0x180043356  sub     rsp, 30h
0x18004335a  mov     rdi, rcx
0x18004335d  lea     rdx, aCxcodevideopro_159; "CxCodeVideoProcGeometryImplD3D11FlatGeo"...
0x180043364  lea     rcx, [rsp+38h+arg_0]; this
0x180043369  mov     r8d, 71h ; 'q'; int
0x18004336f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180043374  lea     rbx, [rdi+20h]
0x180043378  cmp     qword ptr [rbx], 0
0x18004337c  jnz     loc_18004342E
0x180043382  mov     rcx, rbx
0x180043385  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004338a  mov     rdx, rbx; struct ID3D11Buffer **
0x18004338d  mov     rcx, rdi; this
0x180043390  call    ?CreateResource@CxCodeVideoProcGeometryImplD3D11FlatGeometry@@IEAAJPEAPEAUID3D11Buffer@@@Z; CxCodeVideoProcGeometryImplD3D11FlatGeometry::CreateResource(ID3D11Buffer * *)
0x180043395  mov     ebx, eax
0x180043397  test    eax, eax
0x180043399  jns     loc_18004342E
0x18004339f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800433a6  test    rcx, rcx
0x1800433a9  jnz     short loc_1800433EC
0x1800433ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800433b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800433b8  mov     rcx, rax
0x1800433bb  test    rax, rax
0x1800433be  jz      short loc_1800433DE
0x1800433c0  mov     rax, [rax]
0x1800433c3  mov     edx, 7F0h
0x1800433c8  mov     rax, [rax+8]
0x1800433cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433d1  test    eax, eax
0x1800433d3  jz      short loc_1800433DE
0x1800433d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800433dc  jmp     short loc_1800433EC
0x1800433de  lea     rcx, qword_180153440; this
0x1800433e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800433ec  cmp     byte ptr [rcx+8], 0
0x1800433f0  jz      short loc_180043417
0x1800433f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800433f7  cmp     [rax+7CCh], ebx
0x1800433fd  jz      short loc_180043417
0x1800433ff  mov     r9d, ebx; int
0x180043402  lea     rdx, aCxcodevideopro_159; "CxCodeVideoProcGeometryImplD3D11FlatGeo"...
0x180043409  mov     r8d, 74h ; 't'; int
0x18004340f  mov     rcx, rax; this
0x180043412  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043417  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004341e  jb      loc_1800434E4
0x180043424  mov     edx, 0Ch
0x180043429  jmp     loc_1800434C6
0x18004342e  mov     rcx, rdi; this
0x180043431  call    ?CreateResources@CxCodeVideoProcGeometryImplD3D11@@UEAAJXZ; CxCodeVideoProcGeometryImplD3D11::CreateResources(void)
0x180043436  mov     ebx, eax
0x180043438  test    eax, eax
0x18004343a  jns     loc_1800434E4
0x180043440  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043447  test    rcx, rcx
0x18004344a  jnz     short loc_18004348D
0x18004344c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043452  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043459  mov     rcx, rax
0x18004345c  test    rax, rax
0x18004345f  jz      short loc_18004347F
0x180043461  mov     rax, [rax]
0x180043464  mov     edx, 7F0h
0x180043469  mov     rax, [rax+8]
0x18004346d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043472  test    eax, eax
0x180043474  jz      short loc_18004347F
0x180043476  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004347d  jmp     short loc_18004348D
0x18004347f  lea     rcx, qword_180153440; this
0x180043486  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004348d  cmp     byte ptr [rcx+8], 0
0x180043491  jz      short loc_1800434B8
0x180043493  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043498  cmp     [rax+7CCh], ebx
0x18004349e  jz      short loc_1800434B8
0x1800434a0  mov     r9d, ebx; int
0x1800434a3  lea     rdx, aCxcodevideopro_159; "CxCodeVideoProcGeometryImplD3D11FlatGeo"...
0x1800434aa  mov     r8d, 76h ; 'v'; int
0x1800434b0  mov     rcx, rax; this
0x1800434b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800434b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800434bf  jb      short loc_1800434E4
0x1800434c1  mov     edx, 0Dh
0x1800434c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800434cd  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x1800434d4  mov     r9, rdi
0x1800434d7  mov     [rsp+38h+var_18], ebx
0x1800434db  mov     rcx, [rcx+10h]
0x1800434df  call    WPP_SF_qD
0x1800434e4  lea     rcx, [rsp+38h+arg_0]; this
0x1800434e9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800434ee  mov     eax, ebx
0x1800434f0  mov     rbx, [rsp+38h+arg_8]
0x1800434f5  add     rsp, 30h
0x1800434f9  pop     rdi
0x1800434fa  retn
```
