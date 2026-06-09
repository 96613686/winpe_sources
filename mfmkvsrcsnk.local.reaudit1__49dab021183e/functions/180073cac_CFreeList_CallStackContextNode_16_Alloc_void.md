# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x180073cac`
- end: `0x180073d7c`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180074000`

## callees

- `0x180001fb0`
- `0x180073cac`
- `0x180073d84`
- `0x180074438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073cc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073cc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073d5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073d5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073cef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073d2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073cef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073d2f`

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
0x180073cac  mov     [rsp+arg_0], rbx
0x180073cb1  mov     [rsp+arg_8], rsi
0x180073cb6  push    rdi
0x180073cb7  sub     rsp, 20h
0x180073cbb  lea     rsi, [rcx+10h]
0x180073cbf  mov     rbx, rcx
0x180073cc2  mov     rcx, rsi; lpCriticalSection
0x180073cc5  call    cs:__imp_EnterCriticalSection
0x180073ccc  nop     dword ptr [rax+rax+00h]
0x180073cd1  mov     rdi, [rbx+38h]
0x180073cd5  test    rdi, rdi
0x180073cd8  jnz     short loc_180073D16
0x180073cda  inc     dword ptr [rbx+44h]
0x180073cdd  mov     ecx, 7F8h; Size
0x180073ce2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073ce7  mov     rbx, rax
0x180073cea  test    rax, rax
0x180073ced  jz      short loc_180073D12
0x180073cef  call    cs:__imp_GetCurrentThreadId
0x180073cf6  nop     dword ptr [rax+rax+00h]
0x180073cfb  lea     r8d, [rdi+7Ch]; unsigned int
0x180073cff  mov     rcx, rbx; this
0x180073d02  mov     edx, eax; unsigned int
0x180073d04  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180073d09  mov     [rbx+7F0h], rdi
0x180073d10  jmp     short loc_180073D59
0x180073d12  xor     ebx, ebx
0x180073d14  jmp     short loc_180073D59
0x180073d16  mov     rax, [rdi+7F0h]
0x180073d1d  mov     [rbx+38h], rax
0x180073d21  mov     qword ptr [rdi+7F0h], 0
0x180073d2c  dec     dword ptr [rbx+40h]
0x180073d2f  call    cs:__imp_GetCurrentThreadId
0x180073d36  nop     dword ptr [rax+rax+00h]
0x180073d3b  mov     r8d, 7Ch ; '|'; unsigned int
0x180073d41  mov     rcx, rdi; this
0x180073d44  mov     edx, eax; unsigned int
0x180073d46  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x180073d4b  mov     qword ptr [rdi+7F0h], 0
0x180073d56  mov     rbx, rdi
0x180073d59  mov     rcx, rsi; lpCriticalSection
0x180073d5c  call    cs:__imp_LeaveCriticalSection
0x180073d63  nop     dword ptr [rax+rax+00h]
0x180073d68  mov     rsi, [rsp+28h+arg_8]
0x180073d6d  mov     rax, rbx
0x180073d70  mov     rbx, [rsp+28h+arg_0]
0x180073d75  add     rsp, 20h
0x180073d79  pop     rdi
0x180073d7a  retn
```
