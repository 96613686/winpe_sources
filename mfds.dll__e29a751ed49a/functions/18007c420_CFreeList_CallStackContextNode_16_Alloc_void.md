# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x18007c420`
- end: `0x18007c4f0`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007c570`

## callees

- `0x180016674`
- `0x1800496bc`
- `0x180073d0c`
- `0x18007c420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c4d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c4d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c439`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c4a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c4a3`

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
0x18007c420  mov     [rsp+arg_0], rbx
0x18007c425  mov     [rsp+arg_8], rsi
0x18007c42a  push    rdi
0x18007c42b  sub     rsp, 20h
0x18007c42f  lea     rsi, [rcx+10h]
0x18007c433  mov     rbx, rcx
0x18007c436  mov     rcx, rsi; lpCriticalSection
0x18007c439  call    cs:__imp_EnterCriticalSection
0x18007c440  nop     dword ptr [rax+rax+00h]
0x18007c445  mov     rdi, [rbx+38h]
0x18007c449  test    rdi, rdi
0x18007c44c  jnz     short loc_18007C48A
0x18007c44e  inc     dword ptr [rbx+44h]
0x18007c451  mov     ecx, 7F8h; Size
0x18007c456  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007c45b  mov     rbx, rax
0x18007c45e  test    rax, rax
0x18007c461  jz      short loc_18007C486
0x18007c463  call    cs:__imp_GetCurrentThreadId
0x18007c46a  nop     dword ptr [rax+rax+00h]
0x18007c46f  lea     r8d, [rdi+7Ch]; unsigned int
0x18007c473  mov     rcx, rbx; this
0x18007c476  mov     edx, eax; unsigned int
0x18007c478  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x18007c47d  mov     [rbx+7F0h], rdi
0x18007c484  jmp     short loc_18007C4CD
0x18007c486  xor     ebx, ebx
0x18007c488  jmp     short loc_18007C4CD
0x18007c48a  mov     rax, [rdi+7F0h]
0x18007c491  mov     [rbx+38h], rax
0x18007c495  mov     qword ptr [rdi+7F0h], 0
0x18007c4a0  dec     dword ptr [rbx+40h]
0x18007c4a3  call    cs:__imp_GetCurrentThreadId
0x18007c4aa  nop     dword ptr [rax+rax+00h]
0x18007c4af  mov     r8d, 7Ch ; '|'; unsigned int
0x18007c4b5  mov     rcx, rdi; this
0x18007c4b8  mov     edx, eax; unsigned int
0x18007c4ba  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18007c4bf  mov     qword ptr [rdi+7F0h], 0
0x18007c4ca  mov     rbx, rdi
0x18007c4cd  mov     rcx, rsi; lpCriticalSection
0x18007c4d0  call    cs:__imp_LeaveCriticalSection
0x18007c4d7  nop     dword ptr [rax+rax+00h]
0x18007c4dc  mov     rsi, [rsp+28h+arg_8]
0x18007c4e1  mov     rax, rbx
0x18007c4e4  mov     rbx, [rsp+28h+arg_0]
0x18007c4e9  add     rsp, 20h
0x18007c4ed  pop     rdi
0x18007c4ee  retn
```
