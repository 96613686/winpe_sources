# CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(void)

- ea: `0x18006eb18`
- end: `0x18006ecc4`
- name: `?_Initialize@CMFSourceResolverOp@CMFVideoThumbnail@@AEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180069a0c`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18006eb18`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006eb45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006eb45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ebcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ebcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ebfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ebfc`

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
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  _BYTE v15[8]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v16[16]; // [rsp+38h] [rbp-20h] BYREF

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = EventW;
  if ( !EventW )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v15,
      "CMFVideoThumbnail::CMFSourceResolverOp::_Initialize",
      2144);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 11) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 296LL))(*((_QWORD *)this + 11));
      v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 11) + 280LL))(
                        *((_QWORD *)this + 11),
                        v16);
      *((_DWORD *)ThreadRelativeContext + 504) = v5;
      *((_OWORD *)ThreadRelativeContext + 125) = v6;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v2 )
          CallStackContext::TraceFailure(v13, "CMFVideoThumbnail::CMFSourceResolverOp::_Initialize", 2144, v2);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v2);
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v15);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18006eb18  mov     [rsp+arg_8], rbx
0x18006eb1d  mov     [rsp+arg_10], rsi
0x18006eb22  push    rdi
0x18006eb23  sub     rsp, 50h
0x18006eb27  mov     rax, cs:__security_cookie
0x18006eb2e  xor     rax, rsp
0x18006eb31  mov     [rsp+58h+var_10], rax
0x18006eb36  mov     rsi, rcx
0x18006eb39  xor     r9d, r9d; lpName
0x18006eb3c  xor     ecx, ecx; lpEventAttributes
0x18006eb3e  xor     r8d, r8d; bInitialState
0x18006eb41  xor     edx, edx; bManualReset
0x18006eb43  xor     ebx, ebx
0x18006eb45  call    cs:__imp_CreateEventW
0x18006eb4c  nop     dword ptr [rax+rax+00h]
0x18006eb51  mov     [rsi+20h], rax
0x18006eb55  test    rax, rax
0x18006eb58  jnz     loc_18006ECA4
0x18006eb5e  mov     r8d, 860h; int
0x18006eb64  lea     rdx, aCmfvideothumbn_3; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006eb6b  lea     rcx, [rsp+58h+var_28]; this
0x18006eb70  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006eb75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006eb7c  cmp     [rcx+8], bl
0x18006eb7f  jz      short loc_18006EBCD
0x18006eb81  cmp     [rsi+58h], rbx
0x18006eb85  jz      short loc_18006EBCD
0x18006eb87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006eb8c  mov     rcx, [rsi+58h]
0x18006eb90  mov     rdi, rax
0x18006eb93  mov     rax, [rcx]
0x18006eb96  mov     rax, [rax+128h]
0x18006eb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eba2  mov     rcx, [rsi+58h]
0x18006eba6  lea     rdx, [rsp+58h+var_20]
0x18006ebab  mov     ebx, eax
0x18006ebad  mov     rax, [rcx]
0x18006ebb0  mov     rax, [rax+118h]
0x18006ebb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebbc  movups  xmm0, xmmword ptr [rax]
0x18006ebbf  mov     [rdi+7E0h], ebx
0x18006ebc5  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006ebcd  call    cs:__imp_GetLastError
0x18006ebd4  nop     dword ptr [rax+rax+00h]
0x18006ebd9  mov     ebx, eax
0x18006ebdb  test    eax, eax
0x18006ebdd  jle     short loc_18006EBE8
0x18006ebdf  movzx   ebx, ax
0x18006ebe2  or      ebx, 80070000h
0x18006ebe8  test    ebx, ebx
0x18006ebea  jns     loc_18006EC9A
0x18006ebf0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ebf7  test    rcx, rcx
0x18006ebfa  jnz     short loc_18006EC43
0x18006ebfc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ec03  nop     dword ptr [rax+rax+00h]
0x18006ec08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ec0f  mov     rcx, rax
0x18006ec12  test    rax, rax
0x18006ec15  jz      short loc_18006EC35
0x18006ec17  mov     rax, [rax]
0x18006ec1a  mov     edx, 7F0h
0x18006ec1f  mov     rax, [rax+8]
0x18006ec23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec28  test    eax, eax
0x18006ec2a  jz      short loc_18006EC35
0x18006ec2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ec33  jmp     short loc_18006EC43
0x18006ec35  lea     rcx, qword_1800DBF70; this
0x18006ec3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ec43  cmp     byte ptr [rcx+8], 0
0x18006ec47  jz      short loc_18006EC6E
0x18006ec49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ec4e  cmp     [rax+7CCh], ebx
0x18006ec54  jz      short loc_18006EC6E
0x18006ec56  mov     r9d, ebx; int
0x18006ec59  lea     rdx, aCmfvideothumbn_3; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006ec60  mov     r8d, 860h; int
0x18006ec66  mov     rcx, rax; this
0x18006ec69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ec6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ec75  jb      short loc_18006EC9A
0x18006ec77  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ec7e  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006ec85  mov     edx, 0D2h
0x18006ec8a  mov     [rsp+58h+var_38], ebx
0x18006ec8e  mov     r9, rsi
0x18006ec91  mov     rcx, [rcx+10h]
0x18006ec95  call    WPP_SF_qD
0x18006ec9a  lea     rcx, [rsp+58h+var_28]; this
0x18006ec9f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006eca4  mov     eax, ebx
0x18006eca6  mov     rcx, [rsp+58h+var_10]
0x18006ecab  xor     rcx, rsp; StackCookie
0x18006ecae  call    __security_check_cookie
0x18006ecb3  mov     rbx, [rsp+58h+arg_8]
0x18006ecb8  mov     rsi, [rsp+58h+arg_10]
0x18006ecbd  add     rsp, 50h
0x18006ecc1  pop     rdi
0x18006ecc2  retn
```
