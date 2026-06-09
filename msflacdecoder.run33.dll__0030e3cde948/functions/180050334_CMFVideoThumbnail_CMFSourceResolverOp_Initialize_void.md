# CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(void)

- ea: `0x180050334`
- end: `0x1800504cd`
- name: `?_Initialize@CMFSourceResolverOp@CMFVideoThumbnail@@AEAAJXZ`
- size: `409`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004b3b4`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180050334`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050361`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800503e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800503e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005040c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005040c`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(CMFVideoThumbnail::CMFSourceResolverOp *this)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  signed int LastError; // eax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  _BYTE v13[8]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-20h] BYREF

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( !EventW )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v13,
      "CMFVideoThumbnail::CMFSourceResolverOp::_Initialize",
      2144);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 11) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 296LL))(*((_QWORD *)this + 11));
      v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 11) + 280LL))(
                        *((_QWORD *)this + 11),
                        v14);
      *((_DWORD *)ThreadRelativeContext + 504) = v5;
      *((_OWORD *)ThreadRelativeContext + 125) = v6;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v2 )
          CallStackContext::TraceFailure(v11, "CMFVideoThumbnail::CMFSourceResolverOp::_Initialize", 2144, v2);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v2);
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180050334  mov     [rsp+arg_8], rbx
0x180050339  mov     [rsp+arg_10], rsi
0x18005033e  push    rdi
0x18005033f  sub     rsp, 50h
0x180050343  mov     rax, cs:__security_cookie
0x18005034a  xor     rax, rsp
0x18005034d  mov     [rsp+58h+var_10], rax
0x180050352  mov     rsi, rcx
0x180050355  xor     r9d, r9d; lpName
0x180050358  xor     ecx, ecx; lpEventAttributes
0x18005035a  xor     r8d, r8d; bInitialState
0x18005035d  xor     edx, edx; bManualReset
0x18005035f  xor     ebx, ebx
0x180050361  call    cs:__imp_CreateEventW
0x180050367  mov     [rsi+20h], rax
0x18005036b  test    rax, rax
0x18005036e  jnz     loc_1800504AE
0x180050374  mov     r8d, 860h; int
0x18005037a  lea     rdx, aCmfvideothumbn_3; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180050381  lea     rcx, [rsp+58h+var_28]; this
0x180050386  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005038b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180050392  cmp     [rcx+8], bl
0x180050395  jz      short loc_1800503E3
0x180050397  cmp     [rsi+58h], rbx
0x18005039b  jz      short loc_1800503E3
0x18005039d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800503a2  mov     rcx, [rsi+58h]
0x1800503a6  mov     rdi, rax
0x1800503a9  mov     rax, [rcx]
0x1800503ac  mov     rax, [rax+128h]
0x1800503b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503b8  mov     rcx, [rsi+58h]
0x1800503bc  lea     rdx, [rsp+58h+var_20]
0x1800503c1  mov     ebx, eax
0x1800503c3  mov     rax, [rcx]
0x1800503c6  mov     rax, [rax+118h]
0x1800503cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503d2  movups  xmm0, xmmword ptr [rax]
0x1800503d5  mov     [rdi+7E0h], ebx
0x1800503db  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800503e3  call    cs:__imp_GetLastError
0x1800503e9  mov     ebx, eax
0x1800503eb  test    eax, eax
0x1800503ed  jle     short loc_1800503F8
0x1800503ef  movzx   ebx, ax
0x1800503f2  or      ebx, 80070000h
0x1800503f8  test    ebx, ebx
0x1800503fa  jns     loc_1800504A4
0x180050400  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050407  test    rcx, rcx
0x18005040a  jnz     short loc_18005044D
0x18005040c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180050412  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050419  mov     rcx, rax
0x18005041c  test    rax, rax
0x18005041f  jz      short loc_18005043F
0x180050421  mov     rax, [rax]
0x180050424  mov     edx, 7F0h
0x180050429  mov     rax, [rax+8]
0x18005042d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050432  test    eax, eax
0x180050434  jz      short loc_18005043F
0x180050436  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005043d  jmp     short loc_18005044D
0x18005043f  lea     rcx, qword_18006EB20; this
0x180050446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005044d  cmp     byte ptr [rcx+8], 0
0x180050451  jz      short loc_180050478
0x180050453  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050458  cmp     [rax+7CCh], ebx
0x18005045e  jz      short loc_180050478
0x180050460  mov     r9d, ebx; int
0x180050463  lea     rdx, aCmfvideothumbn_3; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18005046a  mov     r8d, 860h; int
0x180050470  mov     rcx, rax; this
0x180050473  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050478  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005047d  cmp     al, 1
0x18005047f  jb      short loc_1800504A4
0x180050481  mov     rcx, cs:WPP_GLOBAL_Control
0x180050488  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18005048f  mov     edx, 0D2h
0x180050494  mov     [rsp+58h+var_38], ebx
0x180050498  mov     r9, rsi
0x18005049b  mov     rcx, [rcx+10h]
0x18005049f  call    WPP_SF_qd
0x1800504a4  lea     rcx, [rsp+58h+var_28]; this
0x1800504a9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800504ae  mov     eax, ebx
0x1800504b0  mov     rcx, [rsp+58h+var_10]
0x1800504b5  xor     rcx, rsp; StackCookie
0x1800504b8  call    __security_check_cookie
0x1800504bd  mov     rbx, [rsp+58h+arg_8]
0x1800504c2  mov     rsi, [rsp+58h+arg_10]
0x1800504c7  add     rsp, 50h
0x1800504cb  pop     rdi
0x1800504cc  retn
```
