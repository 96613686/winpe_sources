# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x18000a370`
- end: `0x18000a478`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008e30`

## callees

- `0x18000a370`
- `0x18000a638`
- `0x18000a690`
- `0x18011fff0`
- `0x180120ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a434`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  CallStackContext *v3; // rsi
  CallStackContext *v4; // rdi
  CallStackInfo *v5; // rsi
  __int64 v6; // rbp
  DWORD v7; // r14d
  DWORD CurrentThreadId; // eax
  DWORD v10; // edi

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v3 = *(CallStackContext **)(a1 + 56);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 56) = v3[1].m_rgInfo[0].m_pszFunction;
    v3[1].m_rgInfo[0].m_pszFunction = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    v3->m_dwMaxDepth = 124;
    v10 = CurrentThreadId;
    memset_0(v3, 0, 0x7C0u);
    CallStackContext::ClearState(v3);
    v3->m_dwThreadID = v10;
    v4 = v3;
    v3[1].m_rgInfo[0].m_pszFunction = 0;
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v4 = (CallStackContext *)operator new(0x7F8u);
    if ( v4 )
    {
      v5 = (CallStackInfo *)v4;
      v6 = 124;
      v7 = GetCurrentThreadId();
      do
      {
        CallStackInfo::CallStackInfo(v5++);
        --v6;
      }
      while ( v6 );
      v4->m_dwMaxDepth = 124;
      memset_0(v4, 0, 0x7C0u);
      CallStackContext::ClearState(v4);
      v4->m_dwThreadID = v7;
      v4[1].m_rgInfo[0].m_pszFunction = 0;
    }
    else
    {
      v4 = 0;
    }
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x18000a370  push    rbx
0x18000a372  push    rbp
0x18000a373  push    rsi
0x18000a374  push    rdi
0x18000a375  push    r14
0x18000a377  sub     rsp, 20h
0x18000a37b  lea     rbx, [rcx+10h]
0x18000a37f  mov     rdi, rcx
0x18000a382  mov     rcx, rbx; lpCriticalSection
0x18000a385  call    cs:__imp_EnterCriticalSection
0x18000a38b  mov     rsi, [rdi+38h]
0x18000a38f  test    rsi, rsi
0x18000a392  jnz     loc_18000A41B
0x18000a398  inc     dword ptr [rdi+44h]
0x18000a39b  mov     ecx, 7F8h; Size
0x18000a3a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a3a5  mov     rdi, rax
0x18000a3a8  test    rax, rax
0x18000a3ab  jz      loc_18000A474
0x18000a3b1  call    cs:__imp_GetCurrentThreadId
0x18000a3b7  mov     rsi, rdi
0x18000a3ba  mov     ebp, 7Ch ; '|'
0x18000a3bf  mov     r14d, eax
0x18000a3c2  mov     rcx, rsi; this
0x18000a3c5  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x18000a3ca  add     rsi, 10h
0x18000a3ce  sub     rbp, 1
0x18000a3d2  jnz     short loc_18000A3C2
0x18000a3d4  xor     edx, edx; Val
0x18000a3d6  mov     dword ptr [rdi+7C8h], 7Ch ; '|'
0x18000a3e0  mov     r8d, 7C0h; Size
0x18000a3e6  mov     rcx, rdi; void *
0x18000a3e9  call    memset_0
0x18000a3ee  mov     rcx, rdi; this
0x18000a3f1  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18000a3f6  mov     [rdi+7C0h], r14d
0x18000a3fd  mov     [rdi+7F0h], rbp
0x18000a404  mov     rcx, rbx; lpCriticalSection
0x18000a407  call    cs:__imp_LeaveCriticalSection
0x18000a40d  mov     rax, rdi
0x18000a410  add     rsp, 20h
0x18000a414  pop     r14
0x18000a416  pop     rdi
0x18000a417  pop     rsi
0x18000a418  pop     rbp
0x18000a419  pop     rbx
0x18000a41a  retn
0x18000a41b  mov     rax, [rsi+7F0h]
0x18000a422  mov     [rdi+38h], rax
0x18000a426  mov     qword ptr [rsi+7F0h], 0
0x18000a431  dec     dword ptr [rdi+40h]
0x18000a434  call    cs:__imp_GetCurrentThreadId
0x18000a43a  xor     edx, edx; Val
0x18000a43c  mov     dword ptr [rsi+7C8h], 7Ch ; '|'
0x18000a446  mov     r8d, 7C0h; Size
0x18000a44c  mov     rcx, rsi; void *
0x18000a44f  mov     edi, eax
0x18000a451  call    memset_0
0x18000a456  mov     rcx, rsi; this
0x18000a459  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18000a45e  mov     [rsi+7C0h], edi
0x18000a464  mov     rdi, rsi
0x18000a467  mov     qword ptr [rsi+7F0h], 0
0x18000a472  jmp     short loc_18000A404
0x18000a474  xor     edi, edi
0x18000a476  jmp     short loc_18000A404
```
