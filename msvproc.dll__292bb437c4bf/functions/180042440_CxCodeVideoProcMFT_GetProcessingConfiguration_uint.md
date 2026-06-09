# CxCodeVideoProcMFT::GetProcessingConfiguration(uint *)

- ea: `0x180042440`
- end: `0x1800425e9`
- name: `?GetProcessingConfiguration@CxCodeVideoProcMFT@@UEAAJPEAI@Z`
- size: `425`
- prototype: `int(CxCodeVideoProcMFT *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180042440`
- `0x1800504d8`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042457`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800425d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800425d8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042492`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042533`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042492`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042533`

## string_xrefs

- `0x180042463`: `CxCodeVideoProcMFT::GetProcessingConfiguration`
- `0x1800424e9`: `CxCodeVideoProcMFT::GetProcessingConfiguration`
- `0x18004258a`: `CxCodeVideoProcMFT::GetProcessingConfiguration`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::GetProcessingConfiguration(CxCodeVideoProcMFT *this, unsigned int *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  char *v4; // rsi
  CxCodeVideoProcMFTDataHandler *v5; // rcx
  __int64 *v6; // rcx
  int ProcessingConfiguration; // ebx
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
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v15,
    "CxCodeVideoProcMFT::GetProcessingConfiguration",
    771);
  v5 = (CxCodeVideoProcMFTDataHandler *)*((_QWORD *)v4 + 4);
  if ( v5 )
  {
    ProcessingConfiguration = CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration(v5, a2);
    if ( ProcessingConfiguration < 0 )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != ProcessingConfiguration )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcMFT::GetProcessingConfiguration",
            772,
            ProcessingConfiguration);
      }
      if ( g_wppLevels )
      {
        v10 = 47;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    ProcessingConfiguration = -1072875845;
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
        CallStackContext::TraceFailure(v9, "CxCodeVideoProcMFT::GetProcessingConfiguration", 771, -1072875845);
    }
    if ( g_wppLevels )
    {
      v10 = 46;
LABEL_23:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        v4,
        ProcessingConfiguration);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  LeaveCriticalSection(v2);
  return (unsigned int)ProcessingConfiguration;
}

```

## disassembly

```asm
0x180042440  push    rbx
0x180042442  push    rbp
0x180042443  push    rsi
0x180042444  push    rdi
0x180042445  sub     rsp, 38h
0x180042449  lea     rbp, [rcx-30h]
0x18004244d  mov     rdi, rdx
0x180042450  lea     rsi, [rcx-58h]
0x180042454  mov     rcx, rbp; lpCriticalSection
0x180042457  call    cs:__imp_EnterCriticalSection
0x18004245d  mov     r8d, 303h; int
0x180042463  lea     rdx, aCxcodevideopro_27; "CxCodeVideoProcMFT::GetProcessingConfig"...
0x18004246a  lea     rcx, [rsp+58h+arg_0]; this
0x18004246f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180042474  mov     rcx, [rsi+20h]; this
0x180042478  test    rcx, rcx
0x18004247b  jnz     loc_180042515
0x180042481  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042488  mov     ebx, 0C00D36BBh
0x18004248d  test    rcx, rcx
0x180042490  jnz     short loc_1800424D3
0x180042492  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042498  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004249f  mov     rcx, rax
0x1800424a2  test    rax, rax
0x1800424a5  jz      short loc_1800424C5
0x1800424a7  mov     rax, [rax]
0x1800424aa  mov     edx, 7F0h
0x1800424af  mov     rax, [rax+8]
0x1800424b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424b8  test    eax, eax
0x1800424ba  jz      short loc_1800424C5
0x1800424bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800424c3  jmp     short loc_1800424D3
0x1800424c5  lea     rcx, qword_180153440; this
0x1800424cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800424d3  cmp     byte ptr [rcx+8], 0
0x1800424d7  jz      short loc_1800424FE
0x1800424d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800424de  cmp     [rax+7CCh], ebx
0x1800424e4  jz      short loc_1800424FE
0x1800424e6  mov     r9d, ebx; int
0x1800424e9  lea     rdx, aCxcodevideopro_27; "CxCodeVideoProcMFT::GetProcessingConfig"...
0x1800424f0  mov     r8d, 303h; int
0x1800424f6  mov     rcx, rax; this
0x1800424f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800424fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042505  jb      loc_1800425CB
0x18004250b  mov     edx, 2Eh ; '.'
0x180042510  jmp     loc_1800425AD
0x180042515  mov     rdx, rdi; unsigned int *
0x180042518  call    ?GetProcessingConfiguration@CxCodeVideoProcMFTDataHandler@@QEAAJPEAI@Z; CxCodeVideoProcMFTDataHandler::GetProcessingConfiguration(uint *)
0x18004251d  mov     ebx, eax
0x18004251f  test    eax, eax
0x180042521  jns     loc_1800425CB
0x180042527  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004252e  test    rcx, rcx
0x180042531  jnz     short loc_180042574
0x180042533  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042539  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042540  mov     rcx, rax
0x180042543  test    rax, rax
0x180042546  jz      short loc_180042566
0x180042548  mov     rax, [rax]
0x18004254b  mov     edx, 7F0h
0x180042550  mov     rax, [rax+8]
0x180042554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042559  test    eax, eax
0x18004255b  jz      short loc_180042566
0x18004255d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042564  jmp     short loc_180042574
0x180042566  lea     rcx, qword_180153440; this
0x18004256d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042574  cmp     byte ptr [rcx+8], 0
0x180042578  jz      short loc_18004259F
0x18004257a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004257f  cmp     [rax+7CCh], ebx
0x180042585  jz      short loc_18004259F
0x180042587  mov     r9d, ebx; int
0x18004258a  lea     rdx, aCxcodevideopro_27; "CxCodeVideoProcMFT::GetProcessingConfig"...
0x180042591  mov     r8d, 304h; int
0x180042597  mov     rcx, rax; this
0x18004259a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004259f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800425a6  jb      short loc_1800425CB
0x1800425a8  mov     edx, 2Fh ; '/'
0x1800425ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425b4  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x1800425bb  mov     r9, rsi
0x1800425be  mov     [rsp+58h+var_38], ebx
0x1800425c2  mov     rcx, [rcx+10h]
0x1800425c6  call    WPP_SF_qD
0x1800425cb  lea     rcx, [rsp+58h+arg_0]; this
0x1800425d0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800425d5  mov     rcx, rbp; lpCriticalSection
0x1800425d8  call    cs:__imp_LeaveCriticalSection
0x1800425de  mov     eax, ebx
0x1800425e0  add     rsp, 38h
0x1800425e4  pop     rdi
0x1800425e5  pop     rsi
0x1800425e6  pop     rbp
0x1800425e7  pop     rbx
0x1800425e8  retn
```
