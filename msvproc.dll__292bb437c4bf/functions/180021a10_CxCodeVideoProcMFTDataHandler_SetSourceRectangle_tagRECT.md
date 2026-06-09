# CxCodeVideoProcMFTDataHandler::SetSourceRectangle(tagRECT *)

- ea: `0x180021a10`
- end: `0x180021ccb`
- name: `?SetSourceRectangle@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUtagRECT@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this, RECT *lprc)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180021860`

## callees

- `0x180007010`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180021a10`
- `0x180024400`
- `0x18003639c`
- `0x180036470`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRectEmpty` at `0x180021aae`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRectEmpty` at `0x180021aae`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180021aca`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180021aca`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180021a98`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180021a98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021b71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021c0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021b71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021c0e`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::SetSourceRectangle(CxCodeVideoProcMFTDataHandler *this, RECT *lprc)
{
  bool v2; // zf
  RECT *v3; // rdi
  RendererEffectWrapper *v6; // rbp
  struct IMFVideoProcessorControl *Control; // rax
  __int64 result; // rax
  int v9; // ebx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v11; // ebx
  __int128 v12; // xmm0
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-48h] BYREF
  RECT rc1; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-30h] BYREF

  v2 = *((_QWORD *)this + 217) == 0;
  v3 = (RECT *)((char *)this + 280);
  rc1 = *(RECT *)((char *)this + 280);
  if ( v2
    || (*((_BYTE *)this + 2368) & 4) == 0
    || (v6 = (CxCodeVideoProcMFTDataHandler *)((char *)this + 1584),
        !RendererEffectWrapper::GetControl((CxCodeVideoProcMFTDataHandler *)((char *)this + 1584)))
    || (Control = RendererEffectWrapper::GetControl(v6),
        result = (*(__int64 (__fastcall **)(struct IMFVideoProcessorControl *, RECT *))(*(_QWORD *)Control + 32LL))(
                   Control,
                   lprc),
        (_DWORD)result == -2147467263) )
  {
    if ( !lprc || IsRectEmpty(lprc) )
      SetRectEmpty(v3);
    else
      *v3 = *lprc;
    v9 = 0;
    if ( !*((_DWORD *)this + 34) || EqualRect(&rc1, v3) )
      return (unsigned int)v9;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v20,
      "CxCodeVideoProcMFTDataHandler::SetSourceRectangle",
      6862);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
      v12 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 388) + 280LL))(
                         *((_QWORD *)this + 388),
                         v22);
      *((_DWORD *)ThreadRelativeContext + 504) = v11;
      *((_OWORD *)ThreadRelativeContext + 125) = v12;
    }
    v9 = CxCodeVideoProcMFTDataHandler::OnEndStreaming(this);
    if ( v9 >= 0 )
    {
      v9 = CxCodeVideoProcMFTDataHandler::OnBeginStreaming(this);
      if ( v9 >= 0 )
        goto LABEL_37;
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v9 )
          CallStackContext::TraceFailure(v19, "CxCodeVideoProcMFTDataHandler::SetSourceRectangle", 6863, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_37;
      v16 = 323;
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v9 )
          CallStackContext::TraceFailure(v15, "CxCodeVideoProcMFTDataHandler::SetSourceRectangle", 6862, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_37;
      v16 = 322;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, v9);
LABEL_37:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x180021a10  mov     [rsp+arg_10], rbx
0x180021a15  push    rbp
0x180021a16  push    rsi
0x180021a17  push    rdi
0x180021a18  sub     rsp, 60h
0x180021a1c  mov     rax, cs:__security_cookie
0x180021a23  xor     rax, rsp
0x180021a26  mov     [rsp+78h+var_20], rax
0x180021a2b  cmp     qword ptr [rcx+6C8h], 0
0x180021a33  lea     rdi, [rcx+118h]
0x180021a3a  movups  xmm0, xmmword ptr [rdi]
0x180021a3d  mov     rbx, rdx
0x180021a40  mov     rsi, rcx
0x180021a43  movdqu  xmmword ptr [rsp+78h+rc1.left], xmm0
0x180021a49  jz      short loc_180021A90
0x180021a4b  test    byte ptr [rcx+940h], 4
0x180021a52  jz      short loc_180021A90
0x180021a54  lea     rbp, [rcx+630h]
0x180021a5b  mov     rcx, rbp; this
0x180021a5e  call    ?GetControl@RendererEffectWrapper@@QEAAPEAUIMFVideoProcessorControl@@XZ; RendererEffectWrapper::GetControl(void)
0x180021a63  test    rax, rax
0x180021a66  jz      short loc_180021A90
0x180021a68  mov     rcx, rbp; this
0x180021a6b  call    ?GetControl@RendererEffectWrapper@@QEAAPEAUIMFVideoProcessorControl@@XZ; RendererEffectWrapper::GetControl(void)
0x180021a70  mov     r8, rax
0x180021a73  mov     rdx, rbx
0x180021a76  mov     rcx, [rax]
0x180021a79  mov     rax, [rcx+20h]
0x180021a7d  mov     rcx, r8
0x180021a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a85  cmp     eax, 80004001h
0x180021a8a  jnz     loc_180021CAE
0x180021a90  test    rbx, rbx
0x180021a93  jz      short loc_180021AAB
0x180021a95  mov     rcx, rbx; lprc
0x180021a98  call    cs:__imp_IsRectEmpty
0x180021a9e  test    eax, eax
0x180021aa0  jnz     short loc_180021AAB
0x180021aa2  movups  xmm0, xmmword ptr [rbx]
0x180021aa5  movdqu  xmmword ptr [rdi], xmm0
0x180021aa9  jmp     short loc_180021AB4
0x180021aab  mov     rcx, rdi; lprc
0x180021aae  call    cs:__imp_SetRectEmpty
0x180021ab4  xor     ebx, ebx
0x180021ab6  cmp     [rsi+88h], ebx
0x180021abc  jz      loc_180021CAC
0x180021ac2  mov     rdx, rdi; lprc2
0x180021ac5  lea     rcx, [rsp+78h+rc1]; lprc1
0x180021aca  call    cs:__imp_EqualRect
0x180021ad0  test    eax, eax
0x180021ad2  jnz     loc_180021CAC
0x180021ad8  lea     rbp, aCxcodevideopro_130; "CxCodeVideoProcMFTDataHandler::SetSourc"...
0x180021adf  mov     r8d, 1ACEh; int
0x180021ae5  mov     rdx, rbp; char *
0x180021ae8  lea     rcx, [rsp+78h+var_48]; this
0x180021aed  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180021af2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180021af9  cmp     [rcx+8], bl
0x180021afc  jz      short loc_180021B53
0x180021afe  cmp     [rsi+0C20h], rbx
0x180021b05  jz      short loc_180021B53
0x180021b07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021b0c  mov     rcx, [rsi+0C20h]
0x180021b13  mov     rdi, rax
0x180021b16  mov     rdx, [rcx]
0x180021b19  mov     rax, [rdx+128h]
0x180021b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b25  mov     rcx, [rsi+0C20h]
0x180021b2c  mov     ebx, eax
0x180021b2e  mov     rdx, [rcx]
0x180021b31  mov     rax, [rdx+118h]
0x180021b38  lea     rdx, [rsp+78h+var_30]
0x180021b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b42  movups  xmm0, xmmword ptr [rax]
0x180021b45  mov     [rdi+7E0h], ebx
0x180021b4b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180021b53  mov     rcx, rsi; this
0x180021b56  call    ?OnEndStreaming@CxCodeVideoProcMFTDataHandler@@UEAAJXZ; CxCodeVideoProcMFTDataHandler::OnEndStreaming(void)
0x180021b5b  mov     ebx, eax
0x180021b5d  test    eax, eax
0x180021b5f  jns     loc_180021BF0
0x180021b65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021b6c  test    rcx, rcx
0x180021b6f  jnz     short loc_180021BB2
0x180021b71  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021b77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021b7e  mov     rcx, rax
0x180021b81  test    rax, rax
0x180021b84  jz      short loc_180021BA4
0x180021b86  mov     rax, [rax]
0x180021b89  mov     edx, 7F0h
0x180021b8e  mov     rax, [rax+8]
0x180021b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b97  test    eax, eax
0x180021b99  jz      short loc_180021BA4
0x180021b9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021ba2  jmp     short loc_180021BB2
0x180021ba4  lea     rcx, qword_180153440; this
0x180021bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021bb2  cmp     byte ptr [rcx+8], 0
0x180021bb6  jz      short loc_180021BD9
0x180021bb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021bbd  cmp     [rax+7CCh], ebx
0x180021bc3  jz      short loc_180021BD9
0x180021bc5  mov     r9d, ebx; int
0x180021bc8  mov     r8d, 1ACEh; int
0x180021bce  mov     rdx, rbp; char *
0x180021bd1  mov     rcx, rax; this
0x180021bd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021bd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021be0  jb      loc_180021CA2
0x180021be6  mov     edx, 142h
0x180021beb  jmp     loc_180021C84
0x180021bf0  mov     rcx, rsi; this
0x180021bf3  call    ?OnBeginStreaming@CxCodeVideoProcMFTDataHandler@@UEAAJXZ; CxCodeVideoProcMFTDataHandler::OnBeginStreaming(void)
0x180021bf8  mov     ebx, eax
0x180021bfa  test    eax, eax
0x180021bfc  jns     loc_180021CA2
0x180021c02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021c09  test    rcx, rcx
0x180021c0c  jnz     short loc_180021C4F
0x180021c0e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021c14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021c1b  mov     rcx, rax
0x180021c1e  test    rax, rax
0x180021c21  jz      short loc_180021C41
0x180021c23  mov     rax, [rax]
0x180021c26  mov     edx, 7F0h
0x180021c2b  mov     rax, [rax+8]
0x180021c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c34  test    eax, eax
0x180021c36  jz      short loc_180021C41
0x180021c38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021c3f  jmp     short loc_180021C4F
0x180021c41  lea     rcx, qword_180153440; this
0x180021c48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021c4f  cmp     byte ptr [rcx+8], 0
0x180021c53  jz      short loc_180021C76
0x180021c55  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021c5a  cmp     [rax+7CCh], ebx
0x180021c60  jz      short loc_180021C76
0x180021c62  mov     r9d, ebx; int
0x180021c65  mov     r8d, 1ACFh; int
0x180021c6b  mov     rdx, rbp; char *
0x180021c6e  mov     rcx, rax; this
0x180021c71  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021c76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021c7d  jb      short loc_180021CA2
0x180021c7f  mov     edx, 143h
0x180021c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c8b  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180021c92  mov     r9, rsi
0x180021c95  mov     [rsp+78h+var_58], ebx
0x180021c99  mov     rcx, [rcx+10h]
0x180021c9d  call    WPP_SF_qD
0x180021ca2  lea     rcx, [rsp+78h+var_48]; this
0x180021ca7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180021cac  mov     eax, ebx
0x180021cae  mov     rcx, [rsp+78h+var_20]
0x180021cb3  xor     rcx, rsp; StackCookie
0x180021cb6  call    __security_check_cookie
0x180021cbb  mov     rbx, [rsp+78h+arg_10]
0x180021cc3  add     rsp, 60h
0x180021cc7  pop     rdi
0x180021cc8  pop     rsi
0x180021cc9  pop     rbp
0x180021cca  retn
```
