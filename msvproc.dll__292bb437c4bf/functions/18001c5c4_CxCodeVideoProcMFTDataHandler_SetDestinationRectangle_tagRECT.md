# CxCodeVideoProcMFTDataHandler::SetDestinationRectangle(tagRECT *)

- ea: `0x18001c5c4`
- end: `0x18001c8d2`
- name: `?SetDestinationRectangle@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUtagRECT@@@Z`
- size: `782`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTDataHandler *__hidden this, RECT *lprc)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18001c3f0`

## callees

- `0x180007010`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001c5c4`
- `0x180024400`
- `0x18003639c`
- `0x180036470`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRectEmpty` at `0x18001c603`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!SetRectEmpty` at `0x18001c603`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18001c646`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x18001c646`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18001c7f2`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x18001c7f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c707`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c783`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c707`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c783`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTDataHandler::SetDestinationRectangle(
        CxCodeVideoProcMFTDataHandler *this,
        RECT *lprc)
{
  RECT *v2; // rdi
  int v3; // ebx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v8; // ebx
  __int128 v9; // xmm0
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  struct IMFVideoProcessorControl *Control; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-48h] BYREF
  RECT rc1; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v20[16]; // [rsp+48h] [rbp-30h] BYREF

  v2 = (RECT *)((char *)this + 632);
  v3 = 0;
  rc1 = *(RECT *)((char *)this + 632);
  if ( !lprc || IsRectEmpty(lprc) )
    SetRectEmpty(v2);
  else
    *v2 = *lprc;
  if ( !*((_DWORD *)this + 34) || EqualRect(&rc1, v2) )
    goto LABEL_4;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v18,
    "CxCodeVideoProcMFTDataHandler::SetDestinationRectangle",
    6899);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 388) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 388) + 296LL))(*((_QWORD *)this + 388));
    v9 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 388) + 280LL))(
                      *((_QWORD *)this + 388),
                      v20);
    *((_DWORD *)ThreadRelativeContext + 504) = v8;
    *((_OWORD *)ThreadRelativeContext + 125) = v9;
  }
  v3 = CxCodeVideoProcMFTDataHandler::OnEndStreaming(this);
  if ( v3 < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v3 )
        CallStackContext::TraceFailure(v12, "CxCodeVideoProcMFTDataHandler::SetDestinationRectangle", 6899, v3);
    }
    if ( !g_wppLevels )
      goto LABEL_32;
    v16 = 324;
    goto LABEL_31;
  }
  v3 = CxCodeVideoProcMFTDataHandler::OnBeginStreaming(this);
  if ( v3 < 0 )
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
      if ( *((_DWORD *)v15 + 499) != v3 )
        CallStackContext::TraceFailure(v15, "CxCodeVideoProcMFTDataHandler::SetDestinationRectangle", 6900, v3);
    }
    if ( !g_wppLevels )
      goto LABEL_32;
    v16 = 325;
LABEL_31:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, v3);
LABEL_32:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
    return (unsigned int)v3;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
LABEL_4:
  if ( *((_QWORD *)this + 217)
    && *((_DWORD *)this + 588) == 1
    && RendererEffectWrapper::GetControl((CxCodeVideoProcMFTDataHandler *)((char *)this + 1584)) )
  {
    Control = RendererEffectWrapper::GetControl((CxCodeVideoProcMFTDataHandler *)((char *)this + 1584));
    (*(void (__fastcall **)(struct IMFVideoProcessorControl *, RECT *))(*(_QWORD *)Control + 40LL))(Control, lprc);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c5c4  mov     [rsp+arg_10], rbx
0x18001c5c9  push    rbp
0x18001c5ca  push    rsi
0x18001c5cb  push    rdi
0x18001c5cc  sub     rsp, 60h
0x18001c5d0  mov     rax, cs:__security_cookie
0x18001c5d7  xor     rax, rsp
0x18001c5da  mov     [rsp+78h+var_20], rax
0x18001c5df  lea     rdi, [rcx+278h]
0x18001c5e6  xor     ebx, ebx
0x18001c5e8  mov     rbp, rdx
0x18001c5eb  mov     rsi, rcx
0x18001c5ee  movups  xmm0, xmmword ptr [rdi]
0x18001c5f1  movdqu  xmmword ptr [rsp+78h+rc1.left], xmm0
0x18001c5f7  test    rdx, rdx
0x18001c5fa  jnz     loc_18001C7EF
0x18001c600  mov     rcx, rdi; lprc
0x18001c603  call    cs:__imp_SetRectEmpty
0x18001c609  cmp     [rsi+88h], ebx
0x18001c60f  jnz     short loc_18001C63E
0x18001c611  cmp     qword ptr [rsi+6C8h], 0
0x18001c619  jnz     loc_18001C88A
0x18001c61f  mov     eax, ebx
0x18001c621  mov     rcx, [rsp+78h+var_20]
0x18001c626  xor     rcx, rsp; StackCookie
0x18001c629  call    __security_check_cookie
0x18001c62e  mov     rbx, [rsp+78h+arg_10]
0x18001c636  add     rsp, 60h
0x18001c63a  pop     rdi
0x18001c63b  pop     rsi
0x18001c63c  pop     rbp
0x18001c63d  retn
0x18001c63e  mov     rdx, rdi; lprc2
0x18001c641  lea     rcx, [rsp+78h+rc1]; lprc1
0x18001c646  call    cs:__imp_EqualRect
0x18001c64c  test    eax, eax
0x18001c64e  jnz     short loc_18001C611
0x18001c650  mov     r8d, 1AF3h; int
0x18001c656  lea     rdx, aCxcodevideopro_53; "CxCodeVideoProcMFTDataHandler::SetDesti"...
0x18001c65d  lea     rcx, [rsp+78h+var_48]; this
0x18001c662  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001c667  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001c66e  cmp     [rcx+8], bl
0x18001c671  jz      short loc_18001C6C8
0x18001c673  cmp     [rsi+0C20h], rbx
0x18001c67a  jz      short loc_18001C6C8
0x18001c67c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c681  mov     rcx, [rsi+0C20h]
0x18001c688  mov     rdi, rax
0x18001c68b  mov     rdx, [rcx]
0x18001c68e  mov     rax, [rdx+128h]
0x18001c695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c69a  mov     rcx, [rsi+0C20h]
0x18001c6a1  mov     ebx, eax
0x18001c6a3  mov     rdx, [rcx]
0x18001c6a6  mov     rax, [rdx+118h]
0x18001c6ad  lea     rdx, [rsp+78h+var_30]
0x18001c6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6b7  movups  xmm0, xmmword ptr [rax]
0x18001c6ba  mov     [rdi+7E0h], ebx
0x18001c6c0  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001c6c8  mov     rcx, rsi; this
0x18001c6cb  call    ?OnEndStreaming@CxCodeVideoProcMFTDataHandler@@UEAAJXZ; CxCodeVideoProcMFTDataHandler::OnEndStreaming(void)
0x18001c6d0  mov     ebx, eax
0x18001c6d2  test    eax, eax
0x18001c6d4  js      short loc_18001C6F7
0x18001c6d6  mov     rcx, rsi; this
0x18001c6d9  call    ?OnBeginStreaming@CxCodeVideoProcMFTDataHandler@@UEAAJXZ; CxCodeVideoProcMFTDataHandler::OnBeginStreaming(void)
0x18001c6de  mov     ebx, eax
0x18001c6e0  test    eax, eax
0x18001c6e2  js      loc_18001C773
0x18001c6e8  lea     rcx, [rsp+78h+var_48]; this
0x18001c6ed  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001c6f2  jmp     loc_18001C611
0x18001c6f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c6fe  test    rcx, rcx
0x18001c701  jnz     loc_18001C81B
0x18001c707  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c70d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c714  mov     rcx, rax
0x18001c717  test    rax, rax
0x18001c71a  jz      loc_18001C80D
0x18001c720  mov     rax, [rax]
0x18001c723  mov     edx, 7F0h
0x18001c728  mov     rax, [rax+8]
0x18001c72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c731  test    eax, eax
0x18001c733  jz      loc_18001C80D
0x18001c739  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c740  jmp     loc_18001C81B
0x18001c745  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c74a  cmp     [rax+7CCh], ebx
0x18001c750  jz      loc_18001C825
0x18001c756  mov     r9d, ebx; int
0x18001c759  lea     rdx, aCxcodevideopro_53; "CxCodeVideoProcMFTDataHandler::SetDesti"...
0x18001c760  mov     r8d, 1AF3h; int
0x18001c766  mov     rcx, rax; this
0x18001c769  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c76e  jmp     loc_18001C825
0x18001c773  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c77a  test    rcx, rcx
0x18001c77d  jnz     loc_18001C875
0x18001c783  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c789  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c790  mov     rcx, rax
0x18001c793  test    rax, rax
0x18001c796  jz      loc_18001C867
0x18001c79c  mov     rax, [rax]
0x18001c79f  mov     edx, 7F0h
0x18001c7a4  mov     rax, [rax+8]
0x18001c7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7ad  test    eax, eax
0x18001c7af  jz      loc_18001C867
0x18001c7b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c7bc  jmp     loc_18001C875
0x18001c7c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c7c6  cmp     [rax+7CCh], ebx
0x18001c7cc  jz      loc_18001C87F
0x18001c7d2  mov     r9d, ebx; int
0x18001c7d5  lea     rdx, aCxcodevideopro_53; "CxCodeVideoProcMFTDataHandler::SetDesti"...
0x18001c7dc  mov     r8d, 1AF4h; int
0x18001c7e2  mov     rcx, rax; this
0x18001c7e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c7ea  jmp     loc_18001C87F
0x18001c7ef  mov     rcx, rbp; lprc
0x18001c7f2  call    cs:__imp_IsRectEmpty
0x18001c7f8  test    eax, eax
0x18001c7fa  jnz     loc_18001C600
0x18001c800  movups  xmm0, xmmword ptr [rbp+0]
0x18001c804  movdqu  xmmword ptr [rdi], xmm0
0x18001c808  jmp     loc_18001C609
0x18001c80d  lea     rcx, qword_180153440; this
0x18001c814  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c81b  cmp     byte ptr [rcx+8], 0
0x18001c81f  jnz     loc_18001C745
0x18001c825  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c82c  jb      short loc_18001C858
0x18001c82e  mov     edx, 144h
0x18001c833  jmp     short loc_18001C83A
0x18001c835  mov     edx, 145h
0x18001c83a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c841  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18001c848  mov     r9, rsi
0x18001c84b  mov     [rsp+78h+var_58], ebx
0x18001c84f  mov     rcx, [rcx+10h]
0x18001c853  call    WPP_SF_qD
0x18001c858  lea     rcx, [rsp+78h+var_48]; this
0x18001c85d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001c862  jmp     loc_18001C61F
0x18001c867  lea     rcx, qword_180153440; this
0x18001c86e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c875  cmp     byte ptr [rcx+8], 0
0x18001c879  jnz     loc_18001C7C1
0x18001c87f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c886  jb      short loc_18001C858
0x18001c888  jmp     short loc_18001C835
0x18001c88a  cmp     dword ptr [rsi+930h], 1
0x18001c891  jnz     loc_18001C61F
0x18001c897  lea     rcx, [rsi+630h]; this
0x18001c89e  call    ?GetControl@RendererEffectWrapper@@QEAAPEAUIMFVideoProcessorControl@@XZ; RendererEffectWrapper::GetControl(void)
0x18001c8a3  test    rax, rax
0x18001c8a6  jz      loc_18001C61F
0x18001c8ac  lea     rcx, [rsi+630h]; this
0x18001c8b3  call    ?GetControl@RendererEffectWrapper@@QEAAPEAUIMFVideoProcessorControl@@XZ; RendererEffectWrapper::GetControl(void)
0x18001c8b8  mov     r8, rax
0x18001c8bb  mov     rdx, rbp
0x18001c8be  mov     rcx, [rax]
0x18001c8c1  mov     rax, [rcx+28h]
0x18001c8c5  mov     rcx, r8
0x18001c8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8cd  jmp     loc_18001C61F
```
