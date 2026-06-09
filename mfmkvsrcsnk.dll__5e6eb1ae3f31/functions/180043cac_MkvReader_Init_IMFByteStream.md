# MkvReader::Init(IMFByteStream *)

- ea: `0x180043cac`
- end: `0x180043fdd`
- name: `?Init@MkvReader@@QEAAJPEAUIMFByteStream@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, struct IMFByteStream *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b7f8`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180043cac`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043d03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043e0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043ed2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043d03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043e0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043ed2`

## string_xrefs

- `0x180043cca`: `MkvReader::Init`
- `0x180043d67`: `MkvReader::Init`
- `0x180043e6e`: `MkvReader::Init`
- `0x180043f36`: `MkvReader::Init`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvReader::Init(MkvReader *this, struct IMFByteStream *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v24; // [rsp+60h] [rbp+20h] BYREF
  int v25; // [rsp+68h] [rbp+28h]
  int v26; // [rsp+70h] [rbp+30h] BYREF
  __int64 v27; // [rsp+78h] [rbp+38h] BYREF

  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v24, "MkvReader::Init", 32);
  if ( !a2 )
  {
    v25 = -2147467261;
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( v25 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v25 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::Init", 34, v25);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v25);
    v10 = v25;
    goto LABEL_47;
  }
  if ( *((struct IMFByteStream **)this + 2) != a2 )
  {
    ((void (__fastcall *)(struct IMFByteStream *))a2->lpVtbl->AddRef)(a2);
    v24 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  }
  v26 = 0;
  v25 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), &v26);
  if ( v25 < 0 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( v25 < 0 && *((_DWORD *)v16 + 499) != v25 )
        CallStackContext::TraceFailure(v16, "MkvReader::Init", 39, v25);
    }
    if ( !g_wppLevels )
      goto LABEL_29;
    v17 = 12;
LABEL_28:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v25);
LABEL_29:
    v10 = v25;
    goto LABEL_47;
  }
  if ( (v26 & 1) == 0 )
  {
    v25 = -1072875845;
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( v25 < 0 && *((_DWORD *)v20 + 499) != v25 )
        CallStackContext::TraceFailure(v20, "MkvReader::Init", 43, v25);
    }
    if ( !g_wppLevels )
      goto LABEL_29;
    v17 = 13;
    goto LABEL_28;
  }
  if ( (v26 & 4) == 0 )
    *((_BYTE *)this + 228) = 0;
  *((_DWORD *)this + 48) = 0x40000;
  *((_DWORD *)this + 39) = 0x40000;
  v27 = 0;
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2), &v27);
  v22 = -1;
  if ( v21 >= 0 )
    v22 = v27;
  *((_QWORD *)this + 25) = v22;
  *((_QWORD *)this + 26) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  v10 = 0;
LABEL_47:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return v10;
}

```

## disassembly

```asm
0x180043cac  push    rbp
0x180043cae  push    rbx
0x180043caf  push    rdi
0x180043cb0  mov     rbp, rsp
0x180043cb3  sub     rsp, 40h
0x180043cb7  mov     rdi, rdx
0x180043cba  mov     rbx, rcx
0x180043cbd  mov     [rbp+arg_8], 0
0x180043cc4  mov     r8d, 20h ; ' '; int
0x180043cca  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180043cd1  lea     rcx, [rbp+arg_0]; this
0x180043cd5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180043cda  nop
0x180043cdb  mov     [rbp+var_10], rbx
0x180043cdf  lea     rax, [rbp+arg_8]
0x180043ce3  mov     [rbp+var_8], rax
0x180043ce7  test    rdi, rdi
0x180043cea  jnz     loc_180043DAD
0x180043cf0  mov     [rbp+arg_8], 80004003h
0x180043cf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043cfe  test    rcx, rcx
0x180043d01  jnz     short loc_180043D44
0x180043d03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043d09  mov     rcx, rax
0x180043d0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043d13  test    rax, rax
0x180043d16  jz      short loc_180043D36
0x180043d18  mov     rax, [rax]
0x180043d1b  mov     edx, 7F0h
0x180043d20  mov     rax, [rax+8]
0x180043d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d29  test    eax, eax
0x180043d2b  jz      short loc_180043D36
0x180043d2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043d34  jmp     short loc_180043D44
0x180043d36  lea     rcx, qword_1800D6F70; this
0x180043d3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043d44  cmp     byte ptr [rcx+8], 0
0x180043d48  jz      short loc_180043D76
0x180043d4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043d4f  mov     r9d, [rbp+arg_8]; int
0x180043d53  test    r9d, r9d
0x180043d56  jns     short loc_180043D76
0x180043d58  cmp     [rax+7CCh], r9d
0x180043d5f  jz      short loc_180043D76
0x180043d61  mov     r8d, 22h ; '"'; int
0x180043d67  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180043d6e  mov     rcx, rax; this
0x180043d71  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043d76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043d7d  jb      short loc_180043DA5
0x180043d7f  mov     edx, 0Bh
0x180043d84  mov     eax, [rbp+arg_8]
0x180043d87  mov     [rsp+40h+var_20], eax
0x180043d8b  mov     r9, rbx
0x180043d8e  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180043d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d9c  mov     rcx, [rcx+10h]
0x180043da0  call    WPP_SF_qD
0x180043da5  mov     ebx, [rbp+arg_8]
0x180043da8  jmp     loc_180043FCA
0x180043dad  cmp     [rbx+10h], rdi
0x180043db1  jz      short loc_180043DD8
0x180043db3  mov     rax, [rdi]
0x180043db6  mov     rcx, rdi
0x180043db9  mov     rax, [rax+8]
0x180043dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dc2  nop
0x180043dc3  mov     rax, [rbx+10h]
0x180043dc7  mov     [rbp+arg_0], rax
0x180043dcb  mov     [rbx+10h], rdi
0x180043dcf  lea     rcx, [rbp+arg_0]
0x180043dd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043dd8  mov     [rbp+arg_10], 0
0x180043ddf  mov     rcx, [rbx+10h]
0x180043de3  mov     rax, [rcx]
0x180043de6  lea     rdx, [rbp+arg_10]
0x180043dea  mov     rax, [rax+18h]
0x180043dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043df3  mov     [rbp+arg_8], eax
0x180043df6  test    eax, eax
0x180043df8  jns     loc_180043EB5
0x180043dfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e05  test    rcx, rcx
0x180043e08  jnz     short loc_180043E4B
0x180043e0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043e10  mov     rcx, rax
0x180043e13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e1a  test    rax, rax
0x180043e1d  jz      short loc_180043E3D
0x180043e1f  mov     rax, [rax]
0x180043e22  mov     edx, 7F0h
0x180043e27  mov     rax, [rax+8]
0x180043e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e30  test    eax, eax
0x180043e32  jz      short loc_180043E3D
0x180043e34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e3b  jmp     short loc_180043E4B
0x180043e3d  lea     rcx, qword_1800D6F70; this
0x180043e44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043e4b  cmp     byte ptr [rcx+8], 0
0x180043e4f  jz      short loc_180043E7D
0x180043e51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043e56  mov     r9d, [rbp+arg_8]; int
0x180043e5a  test    r9d, r9d
0x180043e5d  jns     short loc_180043E7D
0x180043e5f  cmp     [rax+7CCh], r9d
0x180043e66  jz      short loc_180043E7D
0x180043e68  mov     r8d, 27h ; '''; int
0x180043e6e  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180043e75  mov     rcx, rax; this
0x180043e78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043e7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043e84  jb      short loc_180043EAD
0x180043e86  mov     edx, 0Ch
0x180043e8b  mov     eax, [rbp+arg_8]
0x180043e8e  mov     [rsp+40h+var_20], eax
0x180043e92  mov     r9, rbx
0x180043e95  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180043e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ea3  mov     rcx, [rcx+10h]
0x180043ea7  call    WPP_SF_qD
0x180043eac  nop
0x180043ead  mov     ebx, [rbp+arg_8]
0x180043eb0  jmp     loc_180043FCA
0x180043eb5  test    byte ptr [rbp+arg_10], 1
0x180043eb9  jnz     loc_180043F5C
0x180043ebf  mov     [rbp+arg_8], 0C00D36BBh
0x180043ec6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043ecd  test    rcx, rcx
0x180043ed0  jnz     short loc_180043F13
0x180043ed2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180043ed8  mov     rcx, rax
0x180043edb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043ee2  test    rax, rax
0x180043ee5  jz      short loc_180043F05
0x180043ee7  mov     rax, [rax]
0x180043eea  mov     edx, 7F0h
0x180043eef  mov     rax, [rax+8]
0x180043ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ef8  test    eax, eax
0x180043efa  jz      short loc_180043F05
0x180043efc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043f03  jmp     short loc_180043F13
0x180043f05  lea     rcx, qword_1800D6F70; this
0x180043f0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043f13  cmp     byte ptr [rcx+8], 0
0x180043f17  jz      short loc_180043F45
0x180043f19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043f1e  mov     r9d, [rbp+arg_8]; int
0x180043f22  test    r9d, r9d
0x180043f25  jns     short loc_180043F45
0x180043f27  cmp     [rax+7CCh], r9d
0x180043f2e  jz      short loc_180043F45
0x180043f30  mov     r8d, 2Bh ; '+'; int
0x180043f36  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180043f3d  mov     rcx, rax; this
0x180043f40  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043f45  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f4c  jb      loc_180043EAD
0x180043f52  mov     edx, 0Dh
0x180043f57  jmp     loc_180043E8B
0x180043f5c  test    byte ptr [rbp+arg_10], 4
0x180043f60  jnz     short loc_180043F69
0x180043f62  mov     byte ptr [rbx+0E4h], 0
0x180043f69  mov     eax, 40000h
0x180043f6e  mov     [rbx+0C0h], eax
0x180043f74  mov     [rbx+9Ch], eax
0x180043f7a  mov     [rbp+arg_18], 0
0x180043f82  mov     rcx, [rbx+10h]
0x180043f86  mov     rax, [rcx]
0x180043f89  lea     rdx, [rbp+arg_18]
0x180043f8d  mov     rax, [rax+20h]
0x180043f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f96  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180043f9a  test    eax, eax
0x180043f9c  cmovns  rcx, [rbp+arg_18]
0x180043fa1  mov     [rbx+0C8h], rcx
0x180043fa8  mov     qword ptr [rbx+0D0h], 0
0x180043fb3  xorps   xmm0, xmm0
0x180043fb6  xor     eax, eax
0x180043fb8  movups  xmmword ptr [rbx+18h], xmm0
0x180043fbc  movups  xmmword ptr [rbx+28h], xmm0
0x180043fc0  movups  xmmword ptr [rbx+38h], xmm0
0x180043fc4  mov     [rbx+48h], rax
0x180043fc8  xor     ebx, ebx
0x180043fca  lea     rcx, [rbp+arg_0]; this
0x180043fce  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180043fd3  mov     eax, ebx
0x180043fd5  add     rsp, 40h
0x180043fd9  pop     rdi
0x180043fda  pop     rbx
0x180043fdb  pop     rbp
0x180043fdc  retn
```
