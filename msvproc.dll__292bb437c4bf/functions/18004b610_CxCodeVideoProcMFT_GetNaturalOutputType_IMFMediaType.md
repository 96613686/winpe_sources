# CxCodeVideoProcMFT::GetNaturalOutputType(IMFMediaType * *)

- ea: `0x18004b610`
- end: `0x18004b85d`
- name: `?GetNaturalOutputType@CxCodeVideoProcMFT@@UEAAJPEAPEAUIMFMediaType@@@Z`
- size: `589`
- prototype: `int(CxCodeVideoProcMFT *__hidden this, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180005f64`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x18004b610`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b627`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b627`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b84c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b84c`
- `MFPlat!MFCreateMediaType` at `0x18004b6e6`
- `MFPlat!MFCreateMediaType` at `0x18004b6e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b660`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b702`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b7a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b660`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b702`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b7a7`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::GetNaturalOutputType(CxCodeVideoProcMFT *this, struct IMFMediaType **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  CxCodeVideoProcMFTDataHandler **v4; // rdi
  __int64 *v5; // rcx
  HRESULT NaturalOutputType; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v17; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v4 = (CxCodeVideoProcMFTDataHandler **)((char *)this - 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v17,
    "CxCodeVideoProcMFT::GetNaturalOutputType",
    1014);
  if ( v4[4] )
  {
    NaturalOutputType = MFCreateMediaType(a2);
    if ( NaturalOutputType >= 0 )
    {
      NaturalOutputType = CxCodeVideoProcMFTDataHandler::GetNaturalOutputType(v4[4], *a2);
      if ( NaturalOutputType < 0 )
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != NaturalOutputType )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CxCodeVideoProcMFT::GetNaturalOutputType",
              1016,
              NaturalOutputType);
        }
        if ( g_wppLevels )
        {
          v9 = 86;
          goto LABEL_34;
        }
      }
    }
    else
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
        if ( *((_DWORD *)v12 + 499) != NaturalOutputType )
          CallStackContext::TraceFailure(v12, "CxCodeVideoProcMFT::GetNaturalOutputType", 1015, NaturalOutputType);
      }
      if ( g_wppLevels )
      {
        v9 = 85;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    NaturalOutputType = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v8, "CxCodeVideoProcMFT::GetNaturalOutputType", 1014, -1072875845);
    }
    if ( g_wppLevels )
    {
      v9 = 84;
LABEL_34:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        v4,
        NaturalOutputType);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  LeaveCriticalSection(v2);
  return (unsigned int)NaturalOutputType;
}

```

## disassembly

```asm
0x18004b610  push    rbx
0x18004b612  push    rbp
0x18004b613  push    rsi
0x18004b614  push    rdi
0x18004b615  sub     rsp, 38h
0x18004b619  lea     rbp, [rcx-30h]
0x18004b61d  mov     rsi, rdx
0x18004b620  lea     rdi, [rcx-58h]
0x18004b624  mov     rcx, rbp; lpCriticalSection
0x18004b627  call    cs:__imp_EnterCriticalSection
0x18004b62d  mov     r8d, 3F6h; int
0x18004b633  lea     rdx, aCxcodevideopro_6; "CxCodeVideoProcMFT::GetNaturalOutputTyp"...
0x18004b63a  lea     rcx, [rsp+58h+arg_0]; this
0x18004b63f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004b644  cmp     qword ptr [rdi+20h], 0
0x18004b649  jnz     loc_18004B6E3
0x18004b64f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b656  mov     ebx, 0C00D36BBh
0x18004b65b  test    rcx, rcx
0x18004b65e  jnz     short loc_18004B6A1
0x18004b660  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b666  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b66d  mov     rcx, rax
0x18004b670  test    rax, rax
0x18004b673  jz      short loc_18004B693
0x18004b675  mov     rax, [rax]
0x18004b678  mov     edx, 7F0h
0x18004b67d  mov     rax, [rax+8]
0x18004b681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b686  test    eax, eax
0x18004b688  jz      short loc_18004B693
0x18004b68a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b691  jmp     short loc_18004B6A1
0x18004b693  lea     rcx, qword_180153440; this
0x18004b69a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b6a1  cmp     byte ptr [rcx+8], 0
0x18004b6a5  jz      short loc_18004B6CC
0x18004b6a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b6ac  cmp     [rax+7CCh], ebx
0x18004b6b2  jz      short loc_18004B6CC
0x18004b6b4  mov     r9d, ebx; int
0x18004b6b7  lea     rdx, aCxcodevideopro_6; "CxCodeVideoProcMFT::GetNaturalOutputTyp"...
0x18004b6be  mov     r8d, 3F6h; int
0x18004b6c4  mov     rcx, rax; this
0x18004b6c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b6cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b6d3  jb      loc_18004B83F
0x18004b6d9  mov     edx, 54h ; 'T'
0x18004b6de  jmp     loc_18004B821
0x18004b6e3  mov     rcx, rsi; ppMFType
0x18004b6e6  call    cs:__imp_MFCreateMediaType
0x18004b6ec  mov     ebx, eax
0x18004b6ee  test    eax, eax
0x18004b6f0  jns     loc_18004B785
0x18004b6f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b6fd  test    rcx, rcx
0x18004b700  jnz     short loc_18004B743
0x18004b702  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b708  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b70f  mov     rcx, rax
0x18004b712  test    rax, rax
0x18004b715  jz      short loc_18004B735
0x18004b717  mov     rax, [rax]
0x18004b71a  mov     edx, 7F0h
0x18004b71f  mov     rax, [rax+8]
0x18004b723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b728  test    eax, eax
0x18004b72a  jz      short loc_18004B735
0x18004b72c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b733  jmp     short loc_18004B743
0x18004b735  lea     rcx, qword_180153440; this
0x18004b73c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b743  cmp     byte ptr [rcx+8], 0
0x18004b747  jz      short loc_18004B76E
0x18004b749  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b74e  cmp     [rax+7CCh], ebx
0x18004b754  jz      short loc_18004B76E
0x18004b756  mov     r9d, ebx; int
0x18004b759  lea     rdx, aCxcodevideopro_6; "CxCodeVideoProcMFT::GetNaturalOutputTyp"...
0x18004b760  mov     r8d, 3F7h; int
0x18004b766  mov     rcx, rax; this
0x18004b769  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b76e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b775  jb      loc_18004B83F
0x18004b77b  mov     edx, 55h ; 'U'
0x18004b780  jmp     loc_18004B821
0x18004b785  mov     rdx, [rsi]; struct IMFMediaType *
0x18004b788  mov     rcx, [rdi+20h]; this
0x18004b78c  call    ?GetNaturalOutputType@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUIMFMediaType@@@Z; CxCodeVideoProcMFTDataHandler::GetNaturalOutputType(IMFMediaType *)
0x18004b791  mov     ebx, eax
0x18004b793  test    eax, eax
0x18004b795  jns     loc_18004B83F
0x18004b79b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b7a2  test    rcx, rcx
0x18004b7a5  jnz     short loc_18004B7E8
0x18004b7a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b7ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b7b4  mov     rcx, rax
0x18004b7b7  test    rax, rax
0x18004b7ba  jz      short loc_18004B7DA
0x18004b7bc  mov     rax, [rax]
0x18004b7bf  mov     edx, 7F0h
0x18004b7c4  mov     rax, [rax+8]
0x18004b7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7cd  test    eax, eax
0x18004b7cf  jz      short loc_18004B7DA
0x18004b7d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b7d8  jmp     short loc_18004B7E8
0x18004b7da  lea     rcx, qword_180153440; this
0x18004b7e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b7e8  cmp     byte ptr [rcx+8], 0
0x18004b7ec  jz      short loc_18004B813
0x18004b7ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b7f3  cmp     [rax+7CCh], ebx
0x18004b7f9  jz      short loc_18004B813
0x18004b7fb  mov     r9d, ebx; int
0x18004b7fe  lea     rdx, aCxcodevideopro_6; "CxCodeVideoProcMFT::GetNaturalOutputTyp"...
0x18004b805  mov     r8d, 3F8h; int
0x18004b80b  mov     rcx, rax; this
0x18004b80e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b813  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b81a  jb      short loc_18004B83F
0x18004b81c  mov     edx, 56h ; 'V'
0x18004b821  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b828  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18004b82f  mov     r9, rdi
0x18004b832  mov     [rsp+58h+var_38], ebx
0x18004b836  mov     rcx, [rcx+10h]
0x18004b83a  call    WPP_SF_qD
0x18004b83f  lea     rcx, [rsp+58h+arg_0]; this
0x18004b844  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004b849  mov     rcx, rbp; lpCriticalSection
0x18004b84c  call    cs:__imp_LeaveCriticalSection
0x18004b852  mov     eax, ebx
0x18004b854  add     rsp, 38h
0x18004b858  pop     rdi
0x18004b859  pop     rsi
0x18004b85a  pop     rbp
0x18004b85b  pop     rbx
0x18004b85c  retn
```
