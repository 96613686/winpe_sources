# CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(void)

- ea: `0x18006bd44`
- end: `0x18006bedd`
- name: `?_Initialize@CMFSourceResolverOp@CMFVideoThumbnail@@AEAAJXZ`
- size: `409`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180066d9c`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18006bd44`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bd71`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bd71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006be1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006be1c`

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
          v11 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18006bd44  mov     [rsp+arg_8], rbx
0x18006bd49  mov     [rsp+arg_10], rsi
0x18006bd4e  push    rdi
0x18006bd4f  sub     rsp, 50h
0x18006bd53  mov     rax, cs:__security_cookie
0x18006bd5a  xor     rax, rsp
0x18006bd5d  mov     [rsp+58h+var_10], rax
0x18006bd62  mov     rsi, rcx
0x18006bd65  xor     r9d, r9d; lpName
0x18006bd68  xor     ecx, ecx; lpEventAttributes
0x18006bd6a  xor     r8d, r8d; bInitialState
0x18006bd6d  xor     edx, edx; bManualReset
0x18006bd6f  xor     ebx, ebx
0x18006bd71  call    cs:__imp_CreateEventW
0x18006bd77  mov     [rsi+20h], rax
0x18006bd7b  test    rax, rax
0x18006bd7e  jnz     loc_18006BEBE
0x18006bd84  mov     r8d, 860h; int
0x18006bd8a  lea     rdx, aCmfvideothumbn_3; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006bd91  lea     rcx, [rsp+58h+var_28]; this
0x18006bd96  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006bd9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006bda2  cmp     [rcx+8], bl
0x18006bda5  jz      short loc_18006BDF3
0x18006bda7  cmp     [rsi+58h], rbx
0x18006bdab  jz      short loc_18006BDF3
0x18006bdad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006bdb2  mov     rcx, [rsi+58h]
0x18006bdb6  mov     rdi, rax
0x18006bdb9  mov     rax, [rcx]
0x18006bdbc  mov     rax, [rax+128h]
0x18006bdc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdc8  mov     rcx, [rsi+58h]
0x18006bdcc  lea     rdx, [rsp+58h+var_20]
0x18006bdd1  mov     ebx, eax
0x18006bdd3  mov     rax, [rcx]
0x18006bdd6  mov     rax, [rax+118h]
0x18006bddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bde2  movups  xmm0, xmmword ptr [rax]
0x18006bde5  mov     [rdi+7E0h], ebx
0x18006bdeb  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006bdf3  call    cs:__imp_GetLastError
0x18006bdf9  mov     ebx, eax
0x18006bdfb  test    eax, eax
0x18006bdfd  jle     short loc_18006BE08
0x18006bdff  movzx   ebx, ax
0x18006be02  or      ebx, 80070000h
0x18006be08  test    ebx, ebx
0x18006be0a  jns     loc_18006BEB4
0x18006be10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006be17  test    rcx, rcx
0x18006be1a  jnz     short loc_18006BE5D
0x18006be1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006be22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006be29  mov     rcx, rax
0x18006be2c  test    rax, rax
0x18006be2f  jz      short loc_18006BE4F
0x18006be31  mov     rax, [rax]
0x18006be34  mov     edx, 7F0h
0x18006be39  mov     rax, [rax+8]
0x18006be3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be42  test    eax, eax
0x18006be44  jz      short loc_18006BE4F
0x18006be46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006be4d  jmp     short loc_18006BE5D
0x18006be4f  lea     rcx, qword_1800D6F70; this
0x18006be56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006be5d  cmp     byte ptr [rcx+8], 0
0x18006be61  jz      short loc_18006BE88
0x18006be63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006be68  cmp     [rax+7CCh], ebx
0x18006be6e  jz      short loc_18006BE88
0x18006be70  mov     r9d, ebx; int
0x18006be73  lea     rdx, aCmfvideothumbn_3; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006be7a  mov     r8d, 860h; int
0x18006be80  mov     rcx, rax; this
0x18006be83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006be88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006be8f  jb      short loc_18006BEB4
0x18006be91  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be98  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006be9f  mov     edx, 0D2h
0x18006bea4  mov     [rsp+58h+var_38], ebx
0x18006bea8  mov     r9, rsi
0x18006beab  mov     rcx, [rcx+10h]
0x18006beaf  call    WPP_SF_qD
0x18006beb4  lea     rcx, [rsp+58h+var_28]; this
0x18006beb9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006bebe  mov     eax, ebx
0x18006bec0  mov     rcx, [rsp+58h+var_10]
0x18006bec5  xor     rcx, rsp; StackCookie
0x18006bec8  call    __security_check_cookie
0x18006becd  mov     rbx, [rsp+58h+arg_8]
0x18006bed2  mov     rsi, [rsp+58h+arg_10]
0x18006bed7  add     rsp, 50h
0x18006bedb  pop     rdi
0x18006bedc  retn
```
