# MFMkvPropertyHandler::InternalInitialize(ulong)

- ea: `0x18004dd50`
- end: `0x18004df5d`
- name: `?InternalInitialize@MFMkvPropertyHandler@@MEAAJK@Z`
- size: `525`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18004dd50`
- `0x18004dfa0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dd6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004def5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dd6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004def5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004df23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004df4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004df23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004df4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004ded6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004ded6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004de1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004de1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004df35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004df35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dda3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004de41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dda3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004de41`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MFMkvPropertyHandler::InternalInitialize(MFMkvPropertyHandler *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  int SourceAsync; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v12; // r8d
  HANDLE EventW; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rcx
  void *v20; // rcx
  char v22; // [rsp+58h] [rbp+10h] BYREF
  char *v23; // [rsp+60h] [rbp+18h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1888);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1888));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "MFMkvPropertyHandler::InternalInitialize", 38);
  if ( (a2 & 3) != 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    SourceAsync = -2147287035;
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147287035 )
      {
        v12 = 43;
LABEL_19:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MFMkvPropertyHandler::InternalInitialize",
          v12,
          SourceAsync);
      }
    }
  }
  else
  {
    *((_DWORD *)this + 498) = a2;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 250) = EventW;
    if ( EventW )
    {
      SourceAsync = MFMkvPropertyHandler::LoadSourceAsync((MFMkvPropertyHandler *)((char *)this - 32));
      if ( SourceAsync >= 0 && WaitForSingleObject(*((HANDLE *)this + 250), 0x1388u) )
        SourceAsync = -1072875795;
      v23 = (char *)this + 1928;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
      v19 = *((_QWORD *)this + 247);
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 96LL))(v19);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 1976);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
      v20 = (void *)*((_QWORD *)this + 250);
      if ( v20 )
        CloseHandle(v20);
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      SourceAsync = -2147467259;
      if ( *((_BYTE *)v17 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467259 )
        {
          v12 = 52;
          goto LABEL_19;
        }
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  LeaveCriticalSection(v4);
  return (unsigned int)SourceAsync;
}

```

## disassembly

```asm
0x18004dd50  push    rbx
0x18004dd52  push    rbp
0x18004dd53  push    rsi
0x18004dd54  push    rdi
0x18004dd55  push    r14
0x18004dd57  sub     rsp, 20h
0x18004dd5b  mov     esi, edx
0x18004dd5d  mov     rdi, rcx
0x18004dd60  lea     rbp, [rcx+760h]
0x18004dd67  mov     [rsp+48h+arg_0], rbp
0x18004dd6c  mov     rcx, rbp; lpCriticalSection
0x18004dd6f  call    cs:__imp_EnterCriticalSection
0x18004dd75  nop
0x18004dd76  mov     r8d, 26h ; '&'; int
0x18004dd7c  lea     r14, aMfmkvpropertyh_2; "MFMkvPropertyHandler::InternalInitializ"...
0x18004dd83  mov     rdx, r14; char *
0x18004dd86  lea     rcx, [rsp+48h+arg_8]; this
0x18004dd8b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004dd90  nop
0x18004dd91  test    sil, 3
0x18004dd95  jz      short loc_18004DE0F
0x18004dd97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dd9e  test    rcx, rcx
0x18004dda1  jnz     short loc_18004DDE4
0x18004dda3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004dda9  mov     rcx, rax
0x18004ddac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ddb3  test    rax, rax
0x18004ddb6  jz      short loc_18004DDD6
0x18004ddb8  mov     rax, [rax]
0x18004ddbb  mov     edx, 7F0h
0x18004ddc0  mov     rax, [rax+8]
0x18004ddc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddc9  test    eax, eax
0x18004ddcb  jz      short loc_18004DDD6
0x18004ddcd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ddd4  jmp     short loc_18004DDE4
0x18004ddd6  lea     rcx, qword_1800D6F70; this
0x18004dddd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dde4  mov     ebx, 80030005h
0x18004dde9  cmp     byte ptr [rcx+8], 0
0x18004dded  jz      loc_18004DF3C
0x18004ddf3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ddf8  cmp     [rax+7CCh], ebx
0x18004ddfe  jz      loc_18004DF3C
0x18004de04  mov     r8d, 2Bh ; '+'
0x18004de0a  jmp     loc_18004DEA8
0x18004de0f  mov     [rdi+7C8h], esi
0x18004de15  xor     r9d, r9d; lpName
0x18004de18  xor     r8d, r8d; bInitialState
0x18004de1b  xor     edx, edx; bManualReset
0x18004de1d  xor     ecx, ecx; lpEventAttributes
0x18004de1f  call    cs:__imp_CreateEventW
0x18004de25  mov     [rdi+7D0h], rax
0x18004de2c  test    rax, rax
0x18004de2f  jnz     loc_18004DEBB
0x18004de35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de3c  test    rcx, rcx
0x18004de3f  jnz     short loc_18004DE82
0x18004de41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004de47  mov     rcx, rax
0x18004de4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de51  test    rax, rax
0x18004de54  jz      short loc_18004DE74
0x18004de56  mov     rax, [rax]
0x18004de59  mov     edx, 7F0h
0x18004de5e  mov     rax, [rax+8]
0x18004de62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de67  test    eax, eax
0x18004de69  jz      short loc_18004DE74
0x18004de6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de72  jmp     short loc_18004DE82
0x18004de74  lea     rcx, qword_1800D6F70; this
0x18004de7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de82  mov     ebx, 80004005h
0x18004de87  cmp     byte ptr [rcx+8], 0
0x18004de8b  jz      loc_18004DF3C
0x18004de91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004de96  cmp     [rax+7CCh], ebx
0x18004de9c  jz      loc_18004DF3C
0x18004dea2  mov     r8d, 34h ; '4'; int
0x18004dea8  mov     r9d, ebx; int
0x18004deab  mov     rdx, r14; char *
0x18004deae  mov     rcx, rax; this
0x18004deb1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004deb6  jmp     loc_18004DF3C
0x18004debb  lea     rcx, [rdi-20h]; this
0x18004debf  call    ?LoadSourceAsync@MFMkvPropertyHandler@@AEAAJXZ; MFMkvPropertyHandler::LoadSourceAsync(void)
0x18004dec4  mov     ebx, eax
0x18004dec6  test    eax, eax
0x18004dec8  js      short loc_18004DEE6
0x18004deca  mov     edx, 1388h; dwMilliseconds
0x18004decf  mov     rcx, [rdi+7D0h]; hHandle
0x18004ded6  call    cs:__imp_WaitForSingleObject
0x18004dedc  mov     ecx, 0C00D36EDh
0x18004dee1  test    eax, eax
0x18004dee3  cmovnz  ebx, ecx
0x18004dee6  lea     rsi, [rdi+788h]
0x18004deed  mov     [rsp+48h+arg_10], rsi
0x18004def2  mov     rcx, rsi; lpCriticalSection
0x18004def5  call    cs:__imp_EnterCriticalSection
0x18004defb  nop
0x18004defc  lea     r14, [rdi+7B8h]
0x18004df03  mov     rcx, [r14]
0x18004df06  test    rcx, rcx
0x18004df09  jz      short loc_18004DF20
0x18004df0b  mov     rax, [rcx]
0x18004df0e  mov     rax, [rax+60h]
0x18004df12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df17  mov     rcx, r14
0x18004df1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004df1f  nop
0x18004df20  mov     rcx, rsi; lpCriticalSection
0x18004df23  call    cs:__imp_LeaveCriticalSection
0x18004df29  mov     rcx, [rdi+7D0h]; hObject
0x18004df30  test    rcx, rcx
0x18004df33  jz      short loc_18004DF3C
0x18004df35  call    cs:__imp_CloseHandle
0x18004df3b  nop
0x18004df3c  lea     rcx, [rsp+48h+arg_8]; this
0x18004df41  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004df46  nop
0x18004df47  mov     rcx, rbp; lpCriticalSection
0x18004df4a  call    cs:__imp_LeaveCriticalSection
0x18004df50  mov     eax, ebx
0x18004df52  add     rsp, 20h
0x18004df56  pop     r14
0x18004df58  pop     rdi
0x18004df59  pop     rsi
0x18004df5a  pop     rbp
0x18004df5b  pop     rbx
0x18004df5c  retn
```
