# MFMkvPropertyHandler::InternalInitialize(ulong)

- ea: `0x18004fde0`
- end: `0x180050024`
- name: `?InternalInitialize@MFMkvPropertyHandler@@MEAAJK@Z`
- size: `580`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x18004fde0`
- `0x180050060`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fdff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ffa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fdff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ffa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ffd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005000a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ffd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005000a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004ff7e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004ff7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004febb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004febb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ffef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ffef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fe39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fee3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fe39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004fee3`

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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v17 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18004fde0  push    rbx
0x18004fde2  push    rbp
0x18004fde3  push    rsi
0x18004fde4  push    rdi
0x18004fde5  push    r14
0x18004fde7  sub     rsp, 20h
0x18004fdeb  mov     esi, edx
0x18004fded  mov     rdi, rcx
0x18004fdf0  lea     rbp, [rcx+760h]
0x18004fdf7  mov     [rsp+48h+arg_0], rbp
0x18004fdfc  mov     rcx, rbp; lpCriticalSection
0x18004fdff  call    cs:__imp_EnterCriticalSection
0x18004fe06  nop     dword ptr [rax+rax+00h]
0x18004fe0b  nop
0x18004fe0c  mov     r8d, 26h ; '&'; int
0x18004fe12  lea     r14, aMfmkvpropertyh_2; "MFMkvPropertyHandler::InternalInitializ"...
0x18004fe19  mov     rdx, r14; char *
0x18004fe1c  lea     rcx, [rsp+48h+arg_8]; this
0x18004fe21  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004fe26  nop
0x18004fe27  test    sil, 3
0x18004fe2b  jz      short loc_18004FEAB
0x18004fe2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe34  test    rcx, rcx
0x18004fe37  jnz     short loc_18004FE80
0x18004fe39  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004fe40  nop     dword ptr [rax+rax+00h]
0x18004fe45  mov     rcx, rax
0x18004fe48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe4f  test    rax, rax
0x18004fe52  jz      short loc_18004FE72
0x18004fe54  mov     rax, [rax]
0x18004fe57  mov     edx, 7F0h
0x18004fe5c  mov     rax, [rax+8]
0x18004fe60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fe65  test    eax, eax
0x18004fe67  jz      short loc_18004FE72
0x18004fe69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe70  jmp     short loc_18004FE80
0x18004fe72  lea     rcx, qword_1800DBF70; this
0x18004fe79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fe80  mov     ebx, 80030005h
0x18004fe85  cmp     byte ptr [rcx+8], 0
0x18004fe89  jz      loc_18004FFFC
0x18004fe8f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004fe94  cmp     [rax+7CCh], ebx
0x18004fe9a  jz      loc_18004FFFC
0x18004fea0  mov     r8d, 2Bh ; '+'
0x18004fea6  jmp     loc_18004FF50
0x18004feab  mov     [rdi+7C8h], esi
0x18004feb1  xor     r9d, r9d; lpName
0x18004feb4  xor     r8d, r8d; bInitialState
0x18004feb7  xor     edx, edx; bManualReset
0x18004feb9  xor     ecx, ecx; lpEventAttributes
0x18004febb  call    cs:__imp_CreateEventW
0x18004fec2  nop     dword ptr [rax+rax+00h]
0x18004fec7  mov     [rdi+7D0h], rax
0x18004fece  test    rax, rax
0x18004fed1  jnz     loc_18004FF63
0x18004fed7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fede  test    rcx, rcx
0x18004fee1  jnz     short loc_18004FF2A
0x18004fee3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004feea  nop     dword ptr [rax+rax+00h]
0x18004feef  mov     rcx, rax
0x18004fef2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004fef9  test    rax, rax
0x18004fefc  jz      short loc_18004FF1C
0x18004fefe  mov     rax, [rax]
0x18004ff01  mov     edx, 7F0h
0x18004ff06  mov     rax, [rax+8]
0x18004ff0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff0f  test    eax, eax
0x18004ff11  jz      short loc_18004FF1C
0x18004ff13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff1a  jmp     short loc_18004FF2A
0x18004ff1c  lea     rcx, qword_1800DBF70; this
0x18004ff23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ff2a  mov     ebx, 80004005h
0x18004ff2f  cmp     byte ptr [rcx+8], 0
0x18004ff33  jz      loc_18004FFFC
0x18004ff39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ff3e  cmp     [rax+7CCh], ebx
0x18004ff44  jz      loc_18004FFFC
0x18004ff4a  mov     r8d, 34h ; '4'; int
0x18004ff50  mov     r9d, ebx; int
0x18004ff53  mov     rdx, r14; char *
0x18004ff56  mov     rcx, rax; this
0x18004ff59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ff5e  jmp     loc_18004FFFC
0x18004ff63  lea     rcx, [rdi-20h]; this
0x18004ff67  call    ?LoadSourceAsync@MFMkvPropertyHandler@@AEAAJXZ; MFMkvPropertyHandler::LoadSourceAsync(void)
0x18004ff6c  mov     ebx, eax
0x18004ff6e  test    eax, eax
0x18004ff70  js      short loc_18004FF94
0x18004ff72  mov     edx, 1388h; dwMilliseconds
0x18004ff77  mov     rcx, [rdi+7D0h]; hHandle
0x18004ff7e  call    cs:__imp_WaitForSingleObject
0x18004ff85  nop     dword ptr [rax+rax+00h]
0x18004ff8a  mov     ecx, 0C00D36EDh
0x18004ff8f  test    eax, eax
0x18004ff91  cmovnz  ebx, ecx
0x18004ff94  lea     rsi, [rdi+788h]
0x18004ff9b  mov     [rsp+48h+arg_10], rsi
0x18004ffa0  mov     rcx, rsi; lpCriticalSection
0x18004ffa3  call    cs:__imp_EnterCriticalSection
0x18004ffaa  nop     dword ptr [rax+rax+00h]
0x18004ffaf  nop
0x18004ffb0  lea     r14, [rdi+7B8h]
0x18004ffb7  mov     rcx, [r14]
0x18004ffba  test    rcx, rcx
0x18004ffbd  jz      short loc_18004FFD4
0x18004ffbf  mov     rax, [rcx]
0x18004ffc2  mov     rax, [rax+60h]
0x18004ffc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffcb  mov     rcx, r14
0x18004ffce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ffd3  nop
0x18004ffd4  mov     rcx, rsi; lpCriticalSection
0x18004ffd7  call    cs:__imp_LeaveCriticalSection
0x18004ffde  nop     dword ptr [rax+rax+00h]
0x18004ffe3  mov     rcx, [rdi+7D0h]; hObject
0x18004ffea  test    rcx, rcx
0x18004ffed  jz      short loc_18004FFFC
0x18004ffef  call    cs:__imp_CloseHandle
0x18004fff6  nop     dword ptr [rax+rax+00h]
0x18004fffb  nop
0x18004fffc  lea     rcx, [rsp+48h+arg_8]; this
0x180050001  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050006  nop
0x180050007  mov     rcx, rbp; lpCriticalSection
0x18005000a  call    cs:__imp_LeaveCriticalSection
0x180050011  nop     dword ptr [rax+rax+00h]
0x180050016  mov     eax, ebx
0x180050018  add     rsp, 20h
0x18005001c  pop     r14
0x18005001e  pop     rdi
0x18005001f  pop     rsi
0x180050020  pop     rbp
0x180050021  pop     rbx
0x180050022  retn
```
