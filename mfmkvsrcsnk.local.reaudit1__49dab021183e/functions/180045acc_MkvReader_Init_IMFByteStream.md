# MkvReader::Init(IMFByteStream *)

- ea: `0x180045acc`
- end: `0x180045e10`
- name: `?Init@MkvReader@@QEAAJPEAUIMFByteStream@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, struct IMFByteStream *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001c47c`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180045acc`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045b23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045c30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045cfe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045b23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045c30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045cfe`

## string_xrefs

- `0x180045aea`: `MkvReader::Init`
- `0x180045b8d`: `MkvReader::Init`
- `0x180045c9a`: `MkvReader::Init`
- `0x180045d68`: `MkvReader::Init`

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
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v14 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v18 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180045acc  push    rbp
0x180045ace  push    rbx
0x180045acf  push    rdi
0x180045ad0  mov     rbp, rsp
0x180045ad3  sub     rsp, 40h
0x180045ad7  mov     rdi, rdx
0x180045ada  mov     rbx, rcx
0x180045add  mov     [rbp+arg_8], 0
0x180045ae4  mov     r8d, 20h ; ' '; int
0x180045aea  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180045af1  lea     rcx, [rbp+arg_0]; this
0x180045af5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180045afa  nop
0x180045afb  mov     [rbp+var_10], rbx
0x180045aff  lea     rax, [rbp+arg_8]
0x180045b03  mov     [rbp+var_8], rax
0x180045b07  test    rdi, rdi
0x180045b0a  jnz     loc_180045BD3
0x180045b10  mov     [rbp+arg_8], 80004003h
0x180045b17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b1e  test    rcx, rcx
0x180045b21  jnz     short loc_180045B6A
0x180045b23  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045b2a  nop     dword ptr [rax+rax+00h]
0x180045b2f  mov     rcx, rax
0x180045b32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b39  test    rax, rax
0x180045b3c  jz      short loc_180045B5C
0x180045b3e  mov     rax, [rax]
0x180045b41  mov     edx, 7F0h
0x180045b46  mov     rax, [rax+8]
0x180045b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b4f  test    eax, eax
0x180045b51  jz      short loc_180045B5C
0x180045b53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b5a  jmp     short loc_180045B6A
0x180045b5c  lea     rcx, qword_1800DBF70; this
0x180045b63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b6a  cmp     byte ptr [rcx+8], 0
0x180045b6e  jz      short loc_180045B9C
0x180045b70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045b75  mov     r9d, [rbp+arg_8]; int
0x180045b79  test    r9d, r9d
0x180045b7c  jns     short loc_180045B9C
0x180045b7e  cmp     [rax+7CCh], r9d
0x180045b85  jz      short loc_180045B9C
0x180045b87  mov     r8d, 22h ; '"'; int
0x180045b8d  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180045b94  mov     rcx, rax; this
0x180045b97  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045b9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045ba3  jb      short loc_180045BCB
0x180045ba5  mov     edx, 0Bh
0x180045baa  mov     eax, [rbp+arg_8]
0x180045bad  mov     [rsp+40h+var_20], eax
0x180045bb1  mov     r9, rbx
0x180045bb4  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180045bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045bc2  mov     rcx, [rcx+10h]
0x180045bc6  call    WPP_SF_qD
0x180045bcb  mov     ebx, [rbp+arg_8]
0x180045bce  jmp     loc_180045DFC
0x180045bd3  cmp     [rbx+10h], rdi
0x180045bd7  jz      short loc_180045BFE
0x180045bd9  mov     rax, [rdi]
0x180045bdc  mov     rcx, rdi
0x180045bdf  mov     rax, [rax+8]
0x180045be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045be8  nop
0x180045be9  mov     rax, [rbx+10h]
0x180045bed  mov     [rbp+arg_0], rax
0x180045bf1  mov     [rbx+10h], rdi
0x180045bf5  lea     rcx, [rbp+arg_0]
0x180045bf9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045bfe  mov     [rbp+arg_10], 0
0x180045c05  mov     rcx, [rbx+10h]
0x180045c09  mov     rax, [rcx]
0x180045c0c  lea     rdx, [rbp+arg_10]
0x180045c10  mov     rax, [rax+18h]
0x180045c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c19  mov     [rbp+arg_8], eax
0x180045c1c  test    eax, eax
0x180045c1e  jns     loc_180045CE1
0x180045c24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045c2b  test    rcx, rcx
0x180045c2e  jnz     short loc_180045C77
0x180045c30  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045c37  nop     dword ptr [rax+rax+00h]
0x180045c3c  mov     rcx, rax
0x180045c3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045c46  test    rax, rax
0x180045c49  jz      short loc_180045C69
0x180045c4b  mov     rax, [rax]
0x180045c4e  mov     edx, 7F0h
0x180045c53  mov     rax, [rax+8]
0x180045c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c5c  test    eax, eax
0x180045c5e  jz      short loc_180045C69
0x180045c60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045c67  jmp     short loc_180045C77
0x180045c69  lea     rcx, qword_1800DBF70; this
0x180045c70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045c77  cmp     byte ptr [rcx+8], 0
0x180045c7b  jz      short loc_180045CA9
0x180045c7d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045c82  mov     r9d, [rbp+arg_8]; int
0x180045c86  test    r9d, r9d
0x180045c89  jns     short loc_180045CA9
0x180045c8b  cmp     [rax+7CCh], r9d
0x180045c92  jz      short loc_180045CA9
0x180045c94  mov     r8d, 27h ; '''; int
0x180045c9a  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180045ca1  mov     rcx, rax; this
0x180045ca4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045ca9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045cb0  jb      short loc_180045CD9
0x180045cb2  mov     edx, 0Ch
0x180045cb7  mov     eax, [rbp+arg_8]
0x180045cba  mov     [rsp+40h+var_20], eax
0x180045cbe  mov     r9, rbx
0x180045cc1  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180045cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ccf  mov     rcx, [rcx+10h]
0x180045cd3  call    WPP_SF_qD
0x180045cd8  nop
0x180045cd9  mov     ebx, [rbp+arg_8]
0x180045cdc  jmp     loc_180045DFC
0x180045ce1  test    byte ptr [rbp+arg_10], 1
0x180045ce5  jnz     loc_180045D8E
0x180045ceb  mov     [rbp+arg_8], 0C00D36BBh
0x180045cf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045cf9  test    rcx, rcx
0x180045cfc  jnz     short loc_180045D45
0x180045cfe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045d05  nop     dword ptr [rax+rax+00h]
0x180045d0a  mov     rcx, rax
0x180045d0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d14  test    rax, rax
0x180045d17  jz      short loc_180045D37
0x180045d19  mov     rax, [rax]
0x180045d1c  mov     edx, 7F0h
0x180045d21  mov     rax, [rax+8]
0x180045d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d2a  test    eax, eax
0x180045d2c  jz      short loc_180045D37
0x180045d2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d35  jmp     short loc_180045D45
0x180045d37  lea     rcx, qword_1800DBF70; this
0x180045d3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d45  cmp     byte ptr [rcx+8], 0
0x180045d49  jz      short loc_180045D77
0x180045d4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045d50  mov     r9d, [rbp+arg_8]; int
0x180045d54  test    r9d, r9d
0x180045d57  jns     short loc_180045D77
0x180045d59  cmp     [rax+7CCh], r9d
0x180045d60  jz      short loc_180045D77
0x180045d62  mov     r8d, 2Bh ; '+'; int
0x180045d68  lea     rdx, aMkvreaderInit; "MkvReader::Init"
0x180045d6f  mov     rcx, rax; this
0x180045d72  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045d77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045d7e  jb      loc_180045CD9
0x180045d84  mov     edx, 0Dh
0x180045d89  jmp     loc_180045CB7
0x180045d8e  test    byte ptr [rbp+arg_10], 4
0x180045d92  jnz     short loc_180045D9B
0x180045d94  mov     byte ptr [rbx+0E4h], 0
0x180045d9b  mov     eax, 40000h
0x180045da0  mov     [rbx+0C0h], eax
0x180045da6  mov     [rbx+9Ch], eax
0x180045dac  mov     [rbp+arg_18], 0
0x180045db4  mov     rcx, [rbx+10h]
0x180045db8  mov     rax, [rcx]
0x180045dbb  lea     rdx, [rbp+arg_18]
0x180045dbf  mov     rax, [rax+20h]
0x180045dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045dc8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180045dcc  test    eax, eax
0x180045dce  cmovns  rcx, [rbp+arg_18]
0x180045dd3  mov     [rbx+0C8h], rcx
0x180045dda  mov     qword ptr [rbx+0D0h], 0
0x180045de5  xorps   xmm0, xmm0
0x180045de8  xor     eax, eax
0x180045dea  movups  xmmword ptr [rbx+18h], xmm0
0x180045dee  movups  xmmword ptr [rbx+28h], xmm0
0x180045df2  movups  xmmword ptr [rbx+38h], xmm0
0x180045df6  mov     [rbx+48h], rax
0x180045dfa  xor     ebx, ebx
0x180045dfc  lea     rcx, [rbp+arg_0]; this
0x180045e00  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045e05  mov     eax, ebx
0x180045e07  add     rsp, 40h
0x180045e0b  pop     rdi
0x180045e0c  pop     rbx
0x180045e0d  pop     rbp
0x180045e0e  retn
```
