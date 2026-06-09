# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x180070bbc`
- end: `0x180070c73`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180070ed0`

## callees

- `0x180001f90`
- `0x180070bbc`
- `0x180070c7c`
- `0x180071298`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180070bd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180070bd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070c5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070c5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070bf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070bf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070c33`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  CallStackContext *v3; // rdi
  CallStackContext *v4; // rbx
  DWORD v5; // eax
  DWORD CurrentThreadId; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v3 = *(CallStackContext **)(a1 + 56);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 56) = *((_QWORD *)v3 + 254);
    *((_QWORD *)v3 + 254) = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    CallStackContext::Init(v3, CurrentThreadId, 0x7Cu);
    *((_QWORD *)v3 + 254) = 0;
    v4 = v3;
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v4 = (CallStackContext *)operator new(0x7F8u);
    if ( v4 )
    {
      v5 = GetCurrentThreadId();
      CallStackContext::CallStackContext(v4, v5, 0x7Cu);
      *((_QWORD *)v4 + 254) = 0;
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
0x180070bbc  mov     [rsp+arg_0], rbx
0x180070bc1  mov     [rsp+arg_8], rsi
0x180070bc6  push    rdi
0x180070bc7  sub     rsp, 20h
0x180070bcb  lea     rsi, [rcx+10h]
0x180070bcf  mov     rbx, rcx
0x180070bd2  mov     rcx, rsi; lpCriticalSection
0x180070bd5  call    cs:__imp_EnterCriticalSection
0x180070bdb  mov     rdi, [rbx+38h]
0x180070bdf  test    rdi, rdi
0x180070be2  jnz     short loc_180070C1A
0x180070be4  inc     dword ptr [rbx+44h]
0x180070be7  mov     ecx, 7F8h; Size
0x180070bec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070bf1  mov     rbx, rax
0x180070bf4  test    rax, rax
0x180070bf7  jz      short loc_180070C16
0x180070bf9  call    cs:__imp_GetCurrentThreadId
0x180070bff  lea     r8d, [rdi+7Ch]; unsigned int
0x180070c03  mov     rcx, rbx; this
0x180070c06  mov     edx, eax; unsigned int
0x180070c08  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180070c0d  mov     [rbx+7F0h], rdi
0x180070c14  jmp     short loc_180070C57
0x180070c16  xor     ebx, ebx
0x180070c18  jmp     short loc_180070C57
0x180070c1a  mov     rax, [rdi+7F0h]
0x180070c21  mov     [rbx+38h], rax
0x180070c25  mov     qword ptr [rdi+7F0h], 0
0x180070c30  dec     dword ptr [rbx+40h]
0x180070c33  call    cs:__imp_GetCurrentThreadId
0x180070c39  mov     r8d, 7Ch ; '|'; unsigned int
0x180070c3f  mov     rcx, rdi; this
0x180070c42  mov     edx, eax; unsigned int
0x180070c44  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x180070c49  mov     qword ptr [rdi+7F0h], 0
0x180070c54  mov     rbx, rdi
0x180070c57  mov     rcx, rsi; lpCriticalSection
0x180070c5a  call    cs:__imp_LeaveCriticalSection
0x180070c60  mov     rsi, [rsp+28h+arg_8]
0x180070c65  mov     rax, rbx
0x180070c68  mov     rbx, [rsp+28h+arg_0]
0x180070c6d  add     rsp, 20h
0x180070c71  pop     rdi
0x180070c72  retn
```
