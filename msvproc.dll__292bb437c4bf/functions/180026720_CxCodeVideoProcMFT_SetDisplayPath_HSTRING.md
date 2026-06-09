# CxCodeVideoProcMFT::SetDisplayPath(HSTRING__ *)

- ea: `0x180026720`
- end: `0x1800268c9`
- name: `?SetDisplayPath@CxCodeVideoProcMFT@@UEAAJPEAUHSTRING__@@@Z`
- size: `425`
- prototype: `int(CxCodeVideoProcMFT *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180026720`
- `0x1800268d0`
- `0x18003639c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026737`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026737`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800268b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800268b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026772`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026772`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026813`

## string_xrefs

- `0x180026743`: `CxCodeVideoProcMFT::SetDisplayPath`
- `0x1800267c9`: `CxCodeVideoProcMFT::SetDisplayPath`
- `0x18002686a`: `CxCodeVideoProcMFT::SetDisplayPath`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::SetDisplayPath(CxCodeVideoProcMFT *this, HSTRING a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  char *v4; // rsi
  HSTRING *v5; // rcx
  __int64 *v6; // rcx
  int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v15; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v4 = (char *)this - 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v15, "CxCodeVideoProcMFT::SetDisplayPath", 822);
  v5 = (HSTRING *)*((_QWORD *)v4 + 4);
  if ( v5 )
  {
    v7 = CxCodeVideoProcMFTDataHandler::SetDisplayPath(v5, a2);
    if ( v7 < 0 )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcMFT::SetDisplayPath", 823, v7);
      }
      if ( g_wppLevels )
      {
        v10 = 55;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v9 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v9, "CxCodeVideoProcMFT::SetDisplayPath", 822, -1072875845);
    }
    if ( g_wppLevels )
    {
      v10 = 54;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, v4, v7);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  LeaveCriticalSection(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026720  push    rbx
0x180026722  push    rbp
0x180026723  push    rsi
0x180026724  push    rdi
0x180026725  sub     rsp, 38h
0x180026729  lea     rbp, [rcx-30h]
0x18002672d  mov     rdi, rdx
0x180026730  lea     rsi, [rcx-58h]
0x180026734  mov     rcx, rbp; lpCriticalSection
0x180026737  call    cs:__imp_EnterCriticalSection
0x18002673d  mov     r8d, 336h; int
0x180026743  lea     rdx, aCxcodevideopro_14; "CxCodeVideoProcMFT::SetDisplayPath"
0x18002674a  lea     rcx, [rsp+58h+arg_0]; this
0x18002674f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180026754  mov     rcx, [rsi+20h]; this
0x180026758  test    rcx, rcx
0x18002675b  jnz     loc_1800267F5
0x180026761  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026768  mov     ebx, 0C00D36BBh
0x18002676d  test    rcx, rcx
0x180026770  jnz     short loc_1800267B3
0x180026772  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026778  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002677f  mov     rcx, rax
0x180026782  test    rax, rax
0x180026785  jz      short loc_1800267A5
0x180026787  mov     rax, [rax]
0x18002678a  mov     edx, 7F0h
0x18002678f  mov     rax, [rax+8]
0x180026793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026798  test    eax, eax
0x18002679a  jz      short loc_1800267A5
0x18002679c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800267a3  jmp     short loc_1800267B3
0x1800267a5  lea     rcx, qword_180153440; this
0x1800267ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800267b3  cmp     byte ptr [rcx+8], 0
0x1800267b7  jz      short loc_1800267DE
0x1800267b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800267be  cmp     [rax+7CCh], ebx
0x1800267c4  jz      short loc_1800267DE
0x1800267c6  mov     r9d, ebx; int
0x1800267c9  lea     rdx, aCxcodevideopro_14; "CxCodeVideoProcMFT::SetDisplayPath"
0x1800267d0  mov     r8d, 336h; int
0x1800267d6  mov     rcx, rax; this
0x1800267d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800267de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800267e5  jb      loc_1800268AB
0x1800267eb  mov     edx, 36h ; '6'
0x1800267f0  jmp     loc_18002688D
0x1800267f5  mov     rdx, rdi; HSTRING
0x1800267f8  call    ?SetDisplayPath@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUHSTRING__@@@Z; CxCodeVideoProcMFTDataHandler::SetDisplayPath(HSTRING__ *)
0x1800267fd  mov     ebx, eax
0x1800267ff  test    eax, eax
0x180026801  jns     loc_1800268AB
0x180026807  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002680e  test    rcx, rcx
0x180026811  jnz     short loc_180026854
0x180026813  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026819  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026820  mov     rcx, rax
0x180026823  test    rax, rax
0x180026826  jz      short loc_180026846
0x180026828  mov     rax, [rax]
0x18002682b  mov     edx, 7F0h
0x180026830  mov     rax, [rax+8]
0x180026834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026839  test    eax, eax
0x18002683b  jz      short loc_180026846
0x18002683d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026844  jmp     short loc_180026854
0x180026846  lea     rcx, qword_180153440; this
0x18002684d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026854  cmp     byte ptr [rcx+8], 0
0x180026858  jz      short loc_18002687F
0x18002685a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002685f  cmp     [rax+7CCh], ebx
0x180026865  jz      short loc_18002687F
0x180026867  mov     r9d, ebx; int
0x18002686a  lea     rdx, aCxcodevideopro_14; "CxCodeVideoProcMFT::SetDisplayPath"
0x180026871  mov     r8d, 337h; int
0x180026877  mov     rcx, rax; this
0x18002687a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002687f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026886  jb      short loc_1800268AB
0x180026888  mov     edx, 37h ; '7'
0x18002688d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026894  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18002689b  mov     r9, rsi
0x18002689e  mov     [rsp+58h+var_38], ebx
0x1800268a2  mov     rcx, [rcx+10h]
0x1800268a6  call    WPP_SF_qD
0x1800268ab  lea     rcx, [rsp+58h+arg_0]; this
0x1800268b0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800268b5  mov     rcx, rbp; lpCriticalSection
0x1800268b8  call    cs:__imp_LeaveCriticalSection
0x1800268be  mov     eax, ebx
0x1800268c0  add     rsp, 38h
0x1800268c4  pop     rdi
0x1800268c5  pop     rsi
0x1800268c6  pop     rbp
0x1800268c7  pop     rbx
0x1800268c8  retn
```
