# CxCodeVideoProcMFT::SetD3D12CommandQueue(ID3D12CommandQueue *)

- ea: `0x180064e50`
- end: `0x18006519e`
- name: `?SetD3D12CommandQueue@CxCodeVideoProcMFT@@UEAAJPEAUID3D12CommandQueue@@@Z`
- size: `846`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFT *__hidden this, struct ID3D12CommandQueue *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ecf0`
- `0x18003639c`
- `0x180064e50`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064e6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064e6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065184`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065184`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064f84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006511e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064f84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006511e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180064f08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800650a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180064f08`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800650a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064eaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064f2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006503f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800650c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064eaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180064f2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006503f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800650c8`

## string_xrefs

- `0x180064e7b`: `CxCodeVideoProcMFT::SetD3D12CommandQueue`
- `0x180064f95`: `CxCodeVideoProcMFT::SetD3D12CommandQueue`
- `0x180065135`: `CxCodeVideoProcMFT::SetD3D12CommandQueue`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::SetD3D12CommandQueue(CxCodeVideoProcMFT *this, struct ID3D12CommandQueue *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  char *v4; // r13
  __int64 v5; // rbx
  __int64 *v6; // rbx
  int v7; // edi
  CallStackTracing *v8; // rax
  CallStackContext *v9; // rsi
  DWORD v10; // r14d
  CallStackContext *v11; // rax
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 *v17; // rbx
  CallStackTracing *v18; // rax
  CallStackContext *v19; // rsi
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rax
  char v26; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v4 = (char *)this - 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "CxCodeVideoProcMFT::SetD3D12CommandQueue", 834);
  v5 = *((_QWORD *)v4 + 4);
  if ( v5 )
  {
    v15 = *(_QWORD *)(v5 + 168);
    if ( v15 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, struct ID3D12CommandQueue *))(*(_QWORD *)v15 + 160LL))(v15, a2);
      if ( v7 >= 0 )
        goto LABEL_51;
    }
    else
    {
      if ( *(struct ID3D12CommandQueue **)(v5 + 3128) != a2 )
      {
        if ( a2 )
          ((void (__fastcall *)(struct ID3D12CommandQueue *))a2->lpVtbl->AddRef)(a2);
        v16 = *(_QWORD *)(v5 + 3128);
        *(_QWORD *)(v5 + 3128) = a2;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v7 = -2147024809;
    }
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
      v19 = (CallStackContext *)(v17 + 26);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v17 + 3));
      if ( Value )
      {
        v19 = Value;
      }
      else if ( !GetLastError() )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        v24 = (*(__int64 (__fastcall **)(__int64 *))*v22)(v22);
        if ( v24 )
          v19 = (CallStackContext *)v24;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v19 + 499) != v7 )
        CallStackContext::TraceFailure(v19, "CxCodeVideoProcMFT::SetD3D12CommandQueue", 835, v7);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, v4, v7);
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
      v9 = (CallStackContext *)(v6 + 26);
      v10 = GetLastError();
      v11 = (CallStackContext *)TlsGetValue(*((_DWORD *)v6 + 3));
      if ( v11 )
      {
        v9 = v11;
      }
      else if ( !GetLastError() )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        v14 = (*(__int64 (__fastcall **)(__int64 *))*v12)(v12);
        if ( v14 )
          v9 = (CallStackContext *)v14;
      }
      SetLastError(v10);
      if ( *((_DWORD *)v9 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v9, "CxCodeVideoProcMFT::SetD3D12CommandQueue", 834, -1072875845);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        v4,
        -1072875845);
  }
LABEL_51:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  LeaveCriticalSection(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064e50  mov     [rsp+arg_10], rbx
0x180064e55  push    rsi
0x180064e56  push    rdi
0x180064e57  push    r12
0x180064e59  push    r13
0x180064e5b  push    r14
0x180064e5d  sub     rsp, 30h
0x180064e61  lea     r12, [rcx-30h]
0x180064e65  mov     rdi, rdx
0x180064e68  lea     r13, [rcx-58h]
0x180064e6c  mov     rcx, r12; lpCriticalSection
0x180064e6f  call    cs:__imp_EnterCriticalSection
0x180064e75  mov     r8d, 342h; int
0x180064e7b  lea     rdx, aCxcodevideopro_145; "CxCodeVideoProcMFT::SetD3D12CommandQueu"...
0x180064e82  lea     rcx, [rsp+58h+arg_0]; this
0x180064e87  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180064e8c  mov     rbx, [r13+20h]
0x180064e90  test    rbx, rbx
0x180064e93  jnz     loc_180064FC5
0x180064e99  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064ea0  mov     edi, 0C00D36BBh
0x180064ea5  test    rbx, rbx
0x180064ea8  jnz     short loc_180064EEB
0x180064eaa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180064eb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180064eb7  mov     rcx, rax
0x180064eba  test    rax, rax
0x180064ebd  jz      short loc_180064EDD
0x180064ebf  mov     rax, [rax]
0x180064ec2  mov     edx, 7F0h
0x180064ec7  mov     rax, [rax+8]
0x180064ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ed0  test    eax, eax
0x180064ed2  jz      short loc_180064EDD
0x180064ed4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064edb  jmp     short loc_180064EEB
0x180064edd  lea     rbx, qword_180153440
0x180064ee4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180064eeb  cmp     byte ptr [rbx+8], 0
0x180064eef  jz      loc_180064FAA
0x180064ef5  lea     rsi, [rbx+0D0h]
0x180064efc  call    cs:__imp_GetLastError
0x180064f02  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180064f05  mov     r14d, eax
0x180064f08  call    cs:__imp_TlsGetValue
0x180064f0e  test    rax, rax
0x180064f11  jz      short loc_180064F18
0x180064f13  mov     rsi, rax
0x180064f16  jmp     short loc_180064F81
0x180064f18  call    cs:__imp_GetLastError
0x180064f1e  test    eax, eax
0x180064f20  jnz     short loc_180064F81
0x180064f22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f29  test    rcx, rcx
0x180064f2c  jnz     short loc_180064F6F
0x180064f2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180064f34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f3b  mov     rcx, rax
0x180064f3e  test    rax, rax
0x180064f41  jz      short loc_180064F61
0x180064f43  mov     rax, [rax]
0x180064f46  mov     edx, 7F0h
0x180064f4b  mov     rax, [rax+8]
0x180064f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f54  test    eax, eax
0x180064f56  jz      short loc_180064F61
0x180064f58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f5f  jmp     short loc_180064F6F
0x180064f61  lea     rcx, qword_180153440
0x180064f68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180064f6f  mov     rax, [rcx]
0x180064f72  mov     rax, [rax]
0x180064f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f7a  test    rax, rax
0x180064f7d  cmovnz  rsi, rax
0x180064f81  mov     ecx, r14d; dwErrCode
0x180064f84  call    cs:__imp_SetLastError
0x180064f8a  cmp     [rsi+7CCh], edi
0x180064f90  jz      short loc_180064FAA
0x180064f92  mov     r9d, edi; int
0x180064f95  lea     rdx, aCxcodevideopro_145; "CxCodeVideoProcMFT::SetD3D12CommandQueu"...
0x180064f9c  mov     r8d, 342h; int
0x180064fa2  mov     rcx, rsi; this
0x180064fa5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180064faa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180064fb1  jb      loc_180065177
0x180064fb7  mov     edx, 38h ; '8'
0x180064fbc  mov     [rsp+58h+var_38], edi
0x180064fc0  jmp     loc_18006515D
0x180064fc5  mov     rcx, [rbx+0A8h]
0x180064fcc  test    rcx, rcx
0x180064fcf  jz      short loc_180064FEF
0x180064fd1  mov     rax, [rcx]
0x180064fd4  mov     rdx, rdi
0x180064fd7  mov     rax, [rax+0A0h]
0x180064fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fe3  mov     edi, eax
0x180064fe5  test    eax, eax
0x180064fe7  jns     loc_180065177
0x180064fed  jmp     short loc_180065030
0x180064fef  cmp     [rbx+0C38h], rdi
0x180064ff6  jz      short loc_18006502B
0x180064ff8  test    rdi, rdi
0x180064ffb  jz      short loc_18006500C
0x180064ffd  mov     rax, [rdi]
0x180065000  mov     rcx, rdi
0x180065003  mov     rax, [rax+8]
0x180065007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006500c  mov     rcx, [rbx+0C38h]
0x180065013  mov     [rbx+0C38h], rdi
0x18006501a  test    rcx, rcx
0x18006501d  jz      short loc_18006502B
0x18006501f  mov     rax, [rcx]
0x180065022  mov     rax, [rax+10h]
0x180065026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006502b  mov     edi, 80070057h
0x180065030  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065037  mov     r14d, edi
0x18006503a  test    rbx, rbx
0x18006503d  jnz     short loc_180065080
0x18006503f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065045  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006504c  mov     rcx, rax
0x18006504f  test    rax, rax
0x180065052  jz      short loc_180065072
0x180065054  mov     rax, [rax]
0x180065057  mov     edx, 7F0h
0x18006505c  mov     rax, [rax+8]
0x180065060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065065  test    eax, eax
0x180065067  jz      short loc_180065072
0x180065069  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065070  jmp     short loc_180065080
0x180065072  lea     rbx, qword_180153440
0x180065079  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065080  cmp     byte ptr [rbx+8], 0
0x180065084  jz      loc_18006514A
0x18006508a  lea     rsi, [rbx+0D0h]
0x180065091  mov     [rsp+58h+arg_8], r15
0x180065096  call    cs:__imp_GetLastError
0x18006509c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18006509f  mov     r15d, eax
0x1800650a2  call    cs:__imp_TlsGetValue
0x1800650a8  test    rax, rax
0x1800650ab  jz      short loc_1800650B2
0x1800650ad  mov     rsi, rax
0x1800650b0  jmp     short loc_18006511B
0x1800650b2  call    cs:__imp_GetLastError
0x1800650b8  test    eax, eax
0x1800650ba  jnz     short loc_18006511B
0x1800650bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800650c3  test    rcx, rcx
0x1800650c6  jnz     short loc_180065109
0x1800650c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800650ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800650d5  mov     rcx, rax
0x1800650d8  test    rax, rax
0x1800650db  jz      short loc_1800650FB
0x1800650dd  mov     rax, [rax]
0x1800650e0  mov     edx, 7F0h
0x1800650e5  mov     rax, [rax+8]
0x1800650e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650ee  test    eax, eax
0x1800650f0  jz      short loc_1800650FB
0x1800650f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800650f9  jmp     short loc_180065109
0x1800650fb  lea     rcx, qword_180153440
0x180065102  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065109  mov     rax, [rcx]
0x18006510c  mov     rax, [rax]
0x18006510f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065114  test    rax, rax
0x180065117  cmovnz  rsi, rax
0x18006511b  mov     ecx, r15d; dwErrCode
0x18006511e  call    cs:__imp_SetLastError
0x180065124  mov     r15, [rsp+58h+arg_8]
0x180065129  cmp     [rsi+7CCh], r14d
0x180065130  jz      short loc_18006514A
0x180065132  mov     r9d, r14d; int
0x180065135  lea     rdx, aCxcodevideopro_145; "CxCodeVideoProcMFT::SetD3D12CommandQueu"...
0x18006513c  mov     r8d, 343h; int
0x180065142  mov     rcx, rsi; this
0x180065145  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006514a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065151  jb      short loc_180065177
0x180065153  mov     edx, 39h ; '9'
0x180065158  mov     [rsp+58h+var_38], r14d
0x18006515d  mov     rcx, cs:WPP_GLOBAL_Control
0x180065164  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18006516b  mov     r9, r13
0x18006516e  mov     rcx, [rcx+10h]
0x180065172  call    WPP_SF_qD
0x180065177  lea     rcx, [rsp+58h+arg_0]; this
0x18006517c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180065181  mov     rcx, r12; lpCriticalSection
0x180065184  call    cs:__imp_LeaveCriticalSection
0x18006518a  mov     rbx, [rsp+58h+arg_10]
0x18006518f  mov     eax, edi
0x180065191  add     rsp, 30h
0x180065195  pop     r14
0x180065197  pop     r13
0x180065199  pop     r12
0x18006519b  pop     rdi
0x18006519c  pop     rsi
0x18006519d  retn
```
