# CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources(void)

- ea: `0x1800384a0`
- end: `0x1800387d3`
- name: `?CreateResources@CxCodeVideoProcGeometryImplD3D11SphereGeometry@@UEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(CxCodeVideoProcGeometryImplD3D11SphereGeometry *__hidden this)`
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
- `0x1800384a0`
- `0x180054140`
- `0x1800a00f0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003854c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003863f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800386e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003854c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003863f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800386e0`

## string_xrefs

- `0x1800384c6`: `CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources`
- `0x1800385a3`: `CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources`
- `0x180038696`: `CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources`
- `0x180038737`: `CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources(
        CxCodeVideoProcGeometryImplD3D11SphereGeometry *this)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, int *, _QWORD, char *); // rbx
  int Resources; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, int *, _QWORD, char *); // rbx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-30h] BYREF
  int v19; // [rsp+38h] [rbp-28h] BYREF
  int v20; // [rsp+3Ch] [rbp-24h]
  int v21; // [rsp+40h] [rbp-20h]
  int v22; // [rsp+44h] [rbp-1Ch]
  __int64 v23; // [rsp+48h] [rbp-18h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v18,
    "CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources",
    258);
  if ( *((_QWORD *)this + 5) )
    goto LABEL_42;
  v2 = *((_QWORD *)this + 1);
  v23 = 0;
  v20 = 2;
  v19 = 57144;
  v21 = 1;
  v22 = 0x10000;
  v3 = *(__int64 (__fastcall **)(__int64, int *, _QWORD, char *))(*(_QWORD *)v2 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 40);
  Resources = v3(v2, &v19, 0, (char *)this + 40);
  if ( Resources >= 0 )
  {
LABEL_42:
    if ( *((_QWORD *)this + 7) )
      goto LABEL_25;
    v9 = *((_QWORD *)this + 1);
    v23 = 0;
    v20 = 2;
    v19 = 28080;
    v21 = 2;
    v22 = 0x10000;
    v10 = *(__int64 (__fastcall **)(__int64, int *, _QWORD, char *))(*(_QWORD *)v9 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 56);
    Resources = v10(v9, &v19, 0, (char *)this + 56);
    if ( Resources >= 0 )
    {
LABEL_25:
      Resources = CxCodeVideoProcGeometryImplD3D11::CreateResources(this);
      if ( Resources < 0 )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Resources )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources",
              285,
              Resources);
        }
        if ( g_wppLevels )
        {
          v8 = 26;
          goto LABEL_36;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != Resources )
          CallStackContext::TraceFailure(
            v13,
            "CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources",
            282,
            Resources);
      }
      if ( g_wppLevels )
      {
        v8 = 25;
        goto LABEL_36;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != Resources )
        CallStackContext::TraceFailure(
          v7,
          "CxCodeVideoProcGeometryImplD3D11SphereGeometry::CreateResources",
          270,
          Resources);
    }
    if ( g_wppLevels )
    {
      v8 = 24;
LABEL_36:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        WPP_9ed8b548847234ef96bd260641d768de_Traceguids,
        this,
        Resources);
    }
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      27,
      WPP_9ed8b548847234ef96bd260641d768de_Traceguids,
      this,
      Resources);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  return (unsigned int)Resources;
}

```

## disassembly

```asm
0x1800384a0  mov     [rsp-18h+arg_8], rbx
0x1800384a5  mov     [rsp-18h+arg_10], rsi
0x1800384aa  push    rbp
0x1800384ab  push    rdi
0x1800384ac  push    r14
0x1800384ae  mov     rbp, rsp
0x1800384b1  sub     rsp, 60h
0x1800384b5  mov     rax, cs:__security_cookie
0x1800384bc  xor     rax, rsp
0x1800384bf  mov     [rbp+var_10], rax
0x1800384c3  mov     rsi, rcx
0x1800384c6  lea     rdx, aCxcodevideopro_58; "CxCodeVideoProcGeometryImplD3D11SphereG"...
0x1800384cd  lea     rcx, [rbp+var_30]; this
0x1800384d1  mov     r8d, 102h; int
0x1800384d7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800384dc  lea     r14, [rsi+28h]
0x1800384e0  cmp     qword ptr [r14], 0
0x1800384e4  jnz     loc_1800385CF
0x1800384ea  mov     rdi, [rsi+8]
0x1800384ee  mov     rcx, r14
0x1800384f1  mov     [rbp+var_18], 0
0x1800384f9  mov     [rbp+var_24], 2
0x180038500  mov     [rbp+var_28], 0DF38h
0x180038507  mov     [rbp+var_20], 1
0x18003850e  mov     [rbp+var_1C], 10000h
0x180038515  mov     rax, [rdi]
0x180038518  mov     rbx, [rax+18h]
0x18003851c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038521  mov     r9, r14
0x180038524  lea     rdx, [rbp+var_28]
0x180038528  xor     r8d, r8d
0x18003852b  mov     rcx, rdi
0x18003852e  mov     rax, rbx
0x180038531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038536  mov     ebx, eax
0x180038538  test    eax, eax
0x18003853a  jns     loc_1800385CF
0x180038540  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038547  test    rcx, rcx
0x18003854a  jnz     short loc_18003858D
0x18003854c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038552  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038559  mov     rcx, rax
0x18003855c  test    rax, rax
0x18003855f  jz      short loc_18003857F
0x180038561  mov     rax, [rax]
0x180038564  mov     edx, 7F0h
0x180038569  mov     rax, [rax+8]
0x18003856d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038572  test    eax, eax
0x180038574  jz      short loc_18003857F
0x180038576  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003857d  jmp     short loc_18003858D
0x18003857f  lea     rcx, qword_180153440; this
0x180038586  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003858d  cmp     byte ptr [rcx+8], 0
0x180038591  jz      short loc_1800385B8
0x180038593  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038598  cmp     [rax+7CCh], ebx
0x18003859e  jz      short loc_1800385B8
0x1800385a0  mov     r9d, ebx; int
0x1800385a3  lea     rdx, aCxcodevideopro_58; "CxCodeVideoProcGeometryImplD3D11SphereG"...
0x1800385aa  mov     r8d, 10Eh; int
0x1800385b0  mov     rcx, rax; this
0x1800385b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800385b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800385bf  jb      loc_180038778
0x1800385c5  mov     edx, 18h
0x1800385ca  jmp     loc_18003875A
0x1800385cf  lea     r14, [rsi+38h]
0x1800385d3  cmp     qword ptr [r14], 0
0x1800385d7  jnz     loc_1800386C2
0x1800385dd  mov     rdi, [rsi+8]
0x1800385e1  mov     rcx, r14
0x1800385e4  mov     [rbp+var_18], 0
0x1800385ec  mov     [rbp+var_24], 2
0x1800385f3  mov     [rbp+var_28], 6DB0h
0x1800385fa  mov     [rbp+var_20], 2
0x180038601  mov     [rbp+var_1C], 10000h
0x180038608  mov     rax, [rdi]
0x18003860b  mov     rbx, [rax+18h]
0x18003860f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038614  mov     r9, r14
0x180038617  lea     rdx, [rbp+var_28]
0x18003861b  xor     r8d, r8d
0x18003861e  mov     rcx, rdi
0x180038621  mov     rax, rbx
0x180038624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038629  mov     ebx, eax
0x18003862b  test    eax, eax
0x18003862d  jns     loc_1800386C2
0x180038633  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003863a  test    rcx, rcx
0x18003863d  jnz     short loc_180038680
0x18003863f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038645  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003864c  mov     rcx, rax
0x18003864f  test    rax, rax
0x180038652  jz      short loc_180038672
0x180038654  mov     rax, [rax]
0x180038657  mov     edx, 7F0h
0x18003865c  mov     rax, [rax+8]
0x180038660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038665  test    eax, eax
0x180038667  jz      short loc_180038672
0x180038669  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038670  jmp     short loc_180038680
0x180038672  lea     rcx, qword_180153440; this
0x180038679  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038680  cmp     byte ptr [rcx+8], 0
0x180038684  jz      short loc_1800386AB
0x180038686  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003868b  cmp     [rax+7CCh], ebx
0x180038691  jz      short loc_1800386AB
0x180038693  mov     r9d, ebx; int
0x180038696  lea     rdx, aCxcodevideopro_58; "CxCodeVideoProcGeometryImplD3D11SphereG"...
0x18003869d  mov     r8d, 11Ah; int
0x1800386a3  mov     rcx, rax; this
0x1800386a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800386ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800386b2  jb      loc_180038778
0x1800386b8  mov     edx, 19h
0x1800386bd  jmp     loc_18003875A
0x1800386c2  mov     rcx, rsi; this
0x1800386c5  call    ?CreateResources@CxCodeVideoProcGeometryImplD3D11@@UEAAJXZ; CxCodeVideoProcGeometryImplD3D11::CreateResources(void)
0x1800386ca  mov     ebx, eax
0x1800386cc  test    eax, eax
0x1800386ce  jns     loc_180038778
0x1800386d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800386db  test    rcx, rcx
0x1800386de  jnz     short loc_180038721
0x1800386e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800386e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800386ed  mov     rcx, rax
0x1800386f0  test    rax, rax
0x1800386f3  jz      short loc_180038713
0x1800386f5  mov     rax, [rax]
0x1800386f8  mov     edx, 7F0h
0x1800386fd  mov     rax, [rax+8]
0x180038701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038706  test    eax, eax
0x180038708  jz      short loc_180038713
0x18003870a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038711  jmp     short loc_180038721
0x180038713  lea     rcx, qword_180153440; this
0x18003871a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038721  cmp     byte ptr [rcx+8], 0
0x180038725  jz      short loc_18003874C
0x180038727  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003872c  cmp     [rax+7CCh], ebx
0x180038732  jz      short loc_18003874C
0x180038734  mov     r9d, ebx; int
0x180038737  lea     rdx, aCxcodevideopro_58; "CxCodeVideoProcGeometryImplD3D11SphereG"...
0x18003873e  mov     r8d, 11Dh; int
0x180038744  mov     rcx, rax; this
0x180038747  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003874c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038753  jb      short loc_180038778
0x180038755  mov     edx, 1Ah
0x18003875a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038761  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x180038768  mov     r9, rsi
0x18003876b  mov     [rsp+60h+var_40], ebx
0x18003876f  mov     rcx, [rcx+10h]
0x180038773  call    WPP_SF_qD
0x180038778  cmp     cs:byte_180153DE0, 20h ; ' '
0x18003877f  jb      short loc_1800387A7
0x180038781  mov     rcx, cs:WPP_GLOBAL_Control
0x180038788  lea     r8, WPP_9ed8b548847234ef96bd260641d768de_Traceguids
0x18003878f  mov     edx, 1Bh
0x180038794  mov     [rsp+60h+var_40], ebx
0x180038798  mov     r9, rsi
0x18003879b  mov     rcx, [rcx+150h]
0x1800387a2  call    WPP_SF_qD
0x1800387a7  lea     rcx, [rbp+var_30]; this
0x1800387ab  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800387b0  mov     eax, ebx
0x1800387b2  mov     rcx, [rbp+var_10]
0x1800387b6  xor     rcx, rsp; StackCookie
0x1800387b9  call    __security_check_cookie
0x1800387be  lea     r11, [rsp+60h+var_s0]
0x1800387c3  mov     rbx, [r11+28h]
0x1800387c7  mov     rsi, [r11+30h]
0x1800387cb  mov     rsp, r11
0x1800387ce  pop     r14
0x1800387d0  pop     rdi
0x1800387d1  pop     rbp
0x1800387d2  retn
```
