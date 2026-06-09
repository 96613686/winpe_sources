# CPlatformPools::CallStackTracingTakeSnapshot(IMFAsyncResult *)

- ea: `0x18000b2f0`
- end: `0x18000b7a0`
- name: `?CallStackTracingTakeSnapshot@CPlatformPools@@QEAAJPEAUIMFAsyncResult@@@Z`
- size: `1200`
- prototype: `__int64 __fastcall(CPlatformPools *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b2d0`

## callees

- `0x180008428`
- `0x18000a588`
- `0x18000b2f0`
- `0x18011fff0`
- `0x180120ecc`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b323`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b323`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b753`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b48b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b543`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b620`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b785`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b48b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b543`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b620`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b785`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b3ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b3ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b63b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b69d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b69d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b68f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b68f`

## pseudocode

```c
__int64 __fastcall CPlatformPools::CallStackTracingTakeSnapshot(CPlatformPools *this, struct IMFAsyncResult *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rbp
  __int64 i; // rbp
  CallStackContextNode *v7; // rbp
  char *v8; // r14
  DWORD LastError; // esi
  char *Value; // rdi
  unsigned int v11; // esi
  unsigned int v12; // ecx
  __int64 v13; // rdx
  _DWORD *v15; // r12
  DWORD CurrentThreadId; // eax
  DWORD v17; // esi
  _QWORD *v18; // r8
  __int64 v19; // rdx
  DWORD v20; // eax
  CallStackTracing *v21; // rcx
  SIZE_T v22; // rsi
  HANDLE ProcessHeap; // rax
  _QWORD *v24; // r9
  __int64 j; // r8
  __int64 v26; // rdx
  _QWORD *v27; // rdx
  unsigned int v28; // edx

  if ( *((_BYTE *)this + 488) && a2 )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 440);
    EnterCriticalSection((LPCRITICAL_SECTION)this + 11);
    if ( !*((_BYTE *)this + 2832) )
    {
LABEL_18:
      LeaveCriticalSection(v4);
      return 0;
    }
    v5 = *((_QWORD *)this + 364);
    if ( v5 )
    {
      for ( i = *(_QWORD *)(v5 + 8LL * ((unsigned int)a2 % (*((_DWORD *)this + 730) & 0x7FFFFFFFu)));
            i;
            i = *(_QWORD *)(i + 16) )
      {
        if ( *(struct IMFAsyncResult **)i == a2 )
        {
          v7 = *(CallStackContextNode **)(i + 8);
          if ( !v7 )
            goto LABEL_18;
          goto LABEL_9;
        }
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2856));
    v7 = (CallStackContextNode *)*((_QWORD *)this + 362);
    if ( v7 )
    {
      v15 = (_DWORD *)((char *)this + 2904);
      *((_QWORD *)this + 362) = v7->m_pNext;
      v7->m_pNext = 0;
      --*((_DWORD *)this + 726);
      CurrentThreadId = GetCurrentThreadId();
      v7->m_dwMaxDepth = 124;
      v17 = CurrentThreadId;
      memset_0(v7, 0, 0x7C0u);
      v7->m_dwDepth = 0;
      *(_QWORD *)&v7->m_instanceId = 0;
      v7->m_result = 0;
      v7->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
      v7->m_dwErrorsInContext = 0;
      GetCurrentThreadId();
      v7->m_dwThreadID = v17;
      v7->m_pNext = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2856));
    }
    else
    {
      ++*((_DWORD *)this + 727);
      v7 = (CallStackContextNode *)operator new(0x7F8u);
      if ( v7 )
      {
        v20 = GetCurrentThreadId();
        CallStackContext::CallStackContext(v7, v20, 0x7Cu);
        v7->m_pNext = 0;
      }
      else
      {
        v7 = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2856));
      if ( !v7 )
        goto LABEL_18;
      v15 = (_DWORD *)((char *)this + 2904);
    }
    if ( !*((_QWORD *)this + 367) )
    {
      v22 = 24LL * (unsigned int)(*((_DWORD *)this + 738) - 1) + 32;
      ProcessHeap = GetProcessHeap();
      v24 = HeapAlloc(ProcessHeap, 0, v22);
      if ( !v24 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2856));
        if ( *v15 >= *((_DWORD *)this + 712) )
        {
          --*((_DWORD *)this + 727);
          CallStackContextNode::`scalar deleting destructor'(v7, v28);
        }
        else
        {
          v7->m_pNext = (CallStackContextNode *)*((_QWORD *)this + 362);
          ++*v15;
          *((_QWORD *)this + 362) = v7;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2856));
        goto LABEL_18;
      }
      for ( j = 0; (unsigned int)j < *((_DWORD *)this + 738); *((_QWORD *)this + 367) = v27 )
      {
        v26 = (unsigned int)j + 1LL + 2 * j;
        j = (unsigned int)(j + 1);
        v24[v26 + 2] = 0;
        v27 = &v24[v26];
        v27[2] = *((_QWORD *)this + 367);
      }
      *v24 = *((_QWORD *)this + 368);
      *((_QWORD *)this + 368) = v24;
    }
    v18 = (_QWORD *)*((_QWORD *)this + 367);
    *((_QWORD *)this + 367) = v18[2];
    v18[1] = v7;
    *v18 = a2;
    v19 = 8LL * ((unsigned int)a2 % (*((_DWORD *)this + 730) & 0x7FFFFFFFu));
    v18[2] = *(_QWORD *)(v19 + *((_QWORD *)this + 364));
    *(_QWORD *)(v19 + *((_QWORD *)this + 364)) = v18;
    ++*((_DWORD *)this + 731);
LABEL_9:
    v8 = (char *)this + 688;
    if ( *((_BYTE *)this + 488) )
    {
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)this + 123));
      if ( !Value )
      {
        if ( GetLastError() )
          goto LABEL_35;
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        Value = (char *)v21->AllocateNewContext(v21);
        if ( !Value )
LABEL_35:
          Value = v8;
      }
      SetLastError(LastError);
    }
    else
    {
      Value = (char *)this + 688;
    }
    if ( !*((_DWORD *)Value + 498) || !v7->m_dwMaxDepth )
      goto LABEL_18;
    v11 = *((_DWORD *)Value + 497);
    v12 = *((_DWORD *)Value + 506);
    if ( v11 >= 0x7C )
    {
      v11 = 124;
    }
    else if ( v11 <= 0xA )
    {
      v13 = 0;
LABEL_17:
      v7->m_dwErrorsInContext = v12;
      memcpy_0(v7, &Value[16 * v13], 16 * v11);
      v7->m_dwDepth = v11;
      v7->m_sessionId = (_GUID)*((_OWORD *)Value + 125);
      v7->m_instanceId = *((_DWORD *)Value + 504);
      v7->m_dwMark = *((_DWORD *)Value + 505);
      v7->m_result = *((_DWORD *)Value + 499);
      v7->m_dwThreadID = *((_DWORD *)Value + 496);
      goto LABEL_18;
    }
    v13 = v11 - 10;
    v11 = 10;
    if ( v12 >= (unsigned int)dword_1801FB400 >> 1 )
      v12 = (unsigned int)dword_1801FB400 >> 1;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b2f0  push    rdi
0x18000b2f2  push    r14
0x18000b2f4  sub     rsp, 38h
0x18000b2f8  cmp     byte ptr [rcx+1E8h], 0
0x18000b2ff  mov     r14, rdx
0x18000b302  mov     rdi, rcx
0x18000b305  jz      loc_18000B496
0x18000b30b  test    rdx, rdx
0x18000b30e  jz      loc_18000B496
0x18000b314  mov     [rsp+48h+arg_8], rbx
0x18000b319  lea     rbx, [rcx+1B8h]
0x18000b320  mov     rcx, rbx; lpCriticalSection
0x18000b323  call    cs:__imp_EnterCriticalSection
0x18000b329  cmp     byte ptr [rdi+0B10h], 0
0x18000b330  jz      loc_18000B488
0x18000b336  mov     [rsp+48h+arg_10], rbp
0x18000b33b  mov     rbp, [rdi+0B60h]
0x18000b342  mov     [rsp+48h+var_20], r13
0x18000b347  xor     r13d, r13d
0x18000b34a  mov     [rsp+48h+arg_18], rsi
0x18000b34f  mov     [rsp+48h+var_18], r12
0x18000b354  mov     [rsp+48h+var_28], r15
0x18000b359  test    rbp, rbp
0x18000b35c  jz      loc_18000B4A0
0x18000b362  mov     ecx, [rdi+0B68h]
0x18000b368  xor     edx, edx
0x18000b36a  btr     ecx, 1Fh
0x18000b36e  mov     eax, r14d
0x18000b371  div     ecx
0x18000b373  mov     rbp, [rbp+rdx*8+0]
0x18000b378  test    rbp, rbp
0x18000b37b  jz      loc_18000B4A0
0x18000b381  cmp     [rbp+0], r14
0x18000b385  jnz     loc_18000B5DB
0x18000b38b  mov     rbp, [rbp+8]
0x18000b38f  test    rbp, rbp
0x18000b392  jz      loc_18000B46F
0x18000b398  cmp     byte ptr [rdi+1E8h], 0
0x18000b39f  lea     r14, [rdi+2B0h]
0x18000b3a6  jz      loc_18000B5B4
0x18000b3ac  call    cs:__imp_GetLastError
0x18000b3b2  mov     ecx, [rdi+1ECh]; dwTlsIndex
0x18000b3b8  mov     esi, eax
0x18000b3ba  call    cs:__imp_TlsGetValue
0x18000b3c0  mov     rdi, rax
0x18000b3c3  test    rax, rax
0x18000b3c6  jz      loc_18000B63B
0x18000b3cc  mov     ecx, esi; dwErrCode
0x18000b3ce  call    cs:__imp_SetLastError
0x18000b3d4  cmp     dword ptr [rdi+7C8h], 0
0x18000b3db  jz      loc_18000B46F
0x18000b3e1  cmp     dword ptr [rbp+7C8h], 0
0x18000b3e8  jz      loc_18000B46F
0x18000b3ee  mov     esi, [rdi+7C4h]
0x18000b3f4  mov     ecx, [rdi+7E8h]
0x18000b3fa  cmp     esi, 7Ch ; '|'
0x18000b3fd  jnb     loc_18000B5BC
0x18000b403  cmp     esi, 0Ah
0x18000b406  ja      loc_18000B5C1
0x18000b40c  mov     edx, r13d
0x18000b40f  mov     r8d, esi
0x18000b412  shl     rdx, 4
0x18000b416  mov     [rbp+7E8h], ecx
0x18000b41c  add     rdx, rdi; Src
0x18000b41f  shl     r8d, 4; Size
0x18000b423  mov     rcx, rbp; void *
0x18000b426  call    memcpy_0
0x18000b42b  mov     [rbp+7C4h], esi
0x18000b431  movups  xmm0, xmmword ptr [rdi+7D0h]
0x18000b438  movups  xmmword ptr [rbp+7D0h], xmm0
0x18000b43f  mov     eax, [rdi+7E0h]
0x18000b445  mov     [rbp+7E0h], eax
0x18000b44b  mov     eax, [rdi+7E4h]
0x18000b451  mov     [rbp+7E4h], eax
0x18000b457  mov     eax, [rdi+7CCh]
0x18000b45d  mov     [rbp+7CCh], eax
0x18000b463  mov     eax, [rdi+7C0h]
0x18000b469  mov     [rbp+7C0h], eax
0x18000b46f  mov     rsi, [rsp+48h+arg_18]
0x18000b474  mov     r12, [rsp+48h+var_18]
0x18000b479  mov     r15, [rsp+48h+var_28]
0x18000b47e  mov     rbp, [rsp+48h+arg_10]
0x18000b483  mov     r13, [rsp+48h+var_20]
0x18000b488  mov     rcx, rbx; lpCriticalSection
0x18000b48b  call    cs:__imp_LeaveCriticalSection
0x18000b491  mov     rbx, [rsp+48h+arg_8]
0x18000b496  xor     eax, eax
0x18000b498  add     rsp, 38h
0x18000b49c  pop     r14
0x18000b49e  pop     rdi
0x18000b49f  retn
0x18000b4a0  lea     rcx, [rdi+0B28h]; lpCriticalSection
0x18000b4a7  call    cs:__imp_EnterCriticalSection
0x18000b4ad  mov     rbp, [rdi+0B50h]
0x18000b4b4  test    rbp, rbp
0x18000b4b7  jz      loc_18000B5E4
0x18000b4bd  mov     rax, [rbp+7F0h]
0x18000b4c4  lea     r12, [rdi+0B58h]
0x18000b4cb  mov     [rdi+0B50h], rax
0x18000b4d2  mov     [rbp+7F0h], r13
0x18000b4d9  dec     dword ptr [r12]
0x18000b4dd  call    cs:__imp_GetCurrentThreadId
0x18000b4e3  xor     edx, edx; Val
0x18000b4e5  mov     dword ptr [rbp+7C8h], 7Ch ; '|'
0x18000b4ef  mov     r8d, 7C0h; Size
0x18000b4f5  mov     rcx, rbp; void *
0x18000b4f8  mov     esi, eax
0x18000b4fa  call    memset_0
0x18000b4ff  mov     [rbp+7C4h], r13d
0x18000b506  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000b50d  mov     [rbp+7E0h], r13
0x18000b514  mov     [rbp+7CCh], r13d
0x18000b51b  movups  xmmword ptr [rbp+7D0h], xmm0
0x18000b522  mov     [rbp+7E8h], r13d
0x18000b529  call    cs:__imp_GetCurrentThreadId
0x18000b52f  lea     rcx, [rdi+0B28h]; lpCriticalSection
0x18000b536  mov     [rbp+7C0h], esi
0x18000b53c  mov     [rbp+7F0h], r13
0x18000b543  call    cs:__imp_LeaveCriticalSection
0x18000b549  cmp     qword ptr [rdi+0B78h], 0
0x18000b551  mov     r13, rbp
0x18000b554  jz      loc_18000B67B
0x18000b55a  mov     r8, [rdi+0B78h]
0x18000b561  xor     edx, edx
0x18000b563  mov     rax, [r8+10h]
0x18000b567  mov     [rdi+0B78h], rax
0x18000b56e  mov     eax, r14d
0x18000b571  mov     [r8+8], r13
0x18000b575  mov     [r8], r14
0x18000b578  mov     ecx, [rdi+0B68h]
0x18000b57e  btr     ecx, 1Fh
0x18000b582  div     ecx
0x18000b584  mov     rax, [rdi+0B60h]
0x18000b58b  lea     rdx, ds:0[rdx*8]
0x18000b593  mov     rcx, [rdx+rax]
0x18000b597  mov     [r8+10h], rcx
0x18000b59b  mov     rax, [rdi+0B60h]
0x18000b5a2  mov     [rdx+rax], r8
0x18000b5a6  inc     dword ptr [rdi+0B6Ch]
0x18000b5ac  xor     r13d, r13d
0x18000b5af  jmp     loc_18000B398
0x18000b5b4  mov     rdi, r14
0x18000b5b7  jmp     loc_18000B3D4
0x18000b5bc  mov     esi, 7Ch ; '|'
0x18000b5c1  mov     eax, cs:dword_1801FB400
0x18000b5c7  lea     edx, [rsi-0Ah]
0x18000b5ca  shr     eax, 1
0x18000b5cc  mov     esi, 0Ah
0x18000b5d1  cmp     ecx, eax
0x18000b5d3  cmovnb  ecx, eax
0x18000b5d6  jmp     loc_18000B40F
0x18000b5db  mov     rbp, [rbp+10h]
0x18000b5df  jmp     loc_18000B378
0x18000b5e4  inc     dword ptr [rdi+0B5Ch]
0x18000b5ea  mov     ecx, 7F8h; Size
0x18000b5ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5f4  mov     rbp, rax
0x18000b5f7  test    rax, rax
0x18000b5fa  jz      short loc_18000B64D
0x18000b5fc  call    cs:__imp_GetCurrentThreadId
0x18000b602  mov     r8d, 7Ch ; '|'; unsigned int
0x18000b608  mov     rcx, rbp; this
0x18000b60b  mov     edx, eax; unsigned int
0x18000b60d  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x18000b612  mov     [rbp+7F0h], r13
0x18000b619  lea     rcx, [rdi+0B28h]; lpCriticalSection
0x18000b620  call    cs:__imp_LeaveCriticalSection
0x18000b626  test    rbp, rbp
0x18000b629  jz      loc_18000B46F
0x18000b62f  lea     r12, [rdi+0B58h]
0x18000b636  jmp     loc_18000B549
0x18000b63b  call    cs:__imp_GetLastError
0x18000b641  test    eax, eax
0x18000b643  jz      short loc_18000B652
0x18000b645  mov     rdi, r14
0x18000b648  jmp     loc_18000B3CC
0x18000b64d  mov     rbp, r13
0x18000b650  jmp     short loc_18000B619
0x18000b652  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b659  test    rcx, rcx
0x18000b65c  jz      loc_18000B706
0x18000b662  mov     rax, [rcx]
0x18000b665  mov     rax, [rax]
0x18000b668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b66d  mov     rdi, rax
0x18000b670  test    rax, rax
0x18000b673  jnz     loc_18000B3CC
0x18000b679  jmp     short loc_18000B645
0x18000b67b  mov     eax, [rdi+0B88h]
0x18000b681  dec     eax
0x18000b683  lea     rcx, [rax+rax*2]
0x18000b687  lea     rsi, ds:20h[rcx*8]
0x18000b68f  call    cs:__imp_GetProcessHeap
0x18000b695  mov     r8, rsi; dwBytes
0x18000b698  xor     edx, edx; dwFlags
0x18000b69a  mov     rcx, rax; hHeap
0x18000b69d  call    cs:__imp_HeapAlloc
0x18000b6a3  mov     r9, rax
0x18000b6a6  test    rax, rax
0x18000b6a9  jz      loc_18000B74C
0x18000b6af  xor     r8d, r8d
0x18000b6b2  cmp     [rdi+0B88h], r8d
0x18000b6b9  jbe     short loc_18000B6F0
0x18000b6bb  mov     edx, r8d
0x18000b6be  inc     rdx
0x18000b6c1  lea     rdx, [rdx+r8*2]
0x18000b6c5  inc     r8d
0x18000b6c8  mov     qword ptr [r9+rdx*8+10h], 0
0x18000b6d1  lea     rdx, [r9+rdx*8]
0x18000b6d5  mov     rax, [rdi+0B78h]
0x18000b6dc  mov     [rdx+10h], rax
0x18000b6e0  mov     [rdi+0B78h], rdx
0x18000b6e7  cmp     r8d, [rdi+0B88h]
0x18000b6ee  jb      short loc_18000B6BB
0x18000b6f0  mov     rax, [rdi+0B80h]
0x18000b6f7  mov     [r9], rax
0x18000b6fa  mov     [rdi+0B80h], r9
0x18000b701  jmp     loc_18000B55A
0x18000b706  mov     rax, cs:stru_1801FC290.__vftable
0x18000b70d  lea     rcx, stru_1801FC290
0x18000b714  mov     edx, 7F0h
0x18000b719  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b720  mov     rax, [rax+8]
0x18000b724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b729  test    eax, eax
0x18000b72b  jnz     short loc_18000B740
0x18000b72d  lea     rcx, stru_1801F8A30
0x18000b734  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b73b  jmp     loc_18000B662
0x18000b740  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000b747  jmp     loc_18000B662
0x18000b74c  lea     rcx, [rdi+0B28h]; lpCriticalSection
0x18000b753  call    cs:__imp_EnterCriticalSection
0x18000b759  mov     eax, [rdi+0B20h]
0x18000b75f  cmp     [r12], eax
0x18000b763  jge     short loc_18000B790
0x18000b765  mov     rax, [rdi+0B50h]
0x18000b76c  mov     [r13+7F0h], rax
0x18000b773  inc     dword ptr [r12]
0x18000b777  mov     [rdi+0B50h], r13
0x18000b77e  lea     rcx, [rdi+0B28h]; lpCriticalSection
0x18000b785  call    cs:__imp_LeaveCriticalSection
0x18000b78b  jmp     loc_18000B46F
0x18000b790  dec     dword ptr [rdi+0B5Ch]
0x18000b796  mov     rcx, r13; this
0x18000b799  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x18000b79e  jmp     short loc_18000B77E
```
