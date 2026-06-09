# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x1800c9aec`
- end: `0x1800c9ba3`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800c9c20`

## callees

- `0x180023244`
- `0x180036218`
- `0x180053bfc`
- `0x1800c9aec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c9b05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c9b05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c9b8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c9b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c9b63`

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
0x1800c9aec  mov     [rsp+arg_0], rbx
0x1800c9af1  mov     [rsp+arg_8], rsi
0x1800c9af6  push    rdi
0x1800c9af7  sub     rsp, 20h
0x1800c9afb  lea     rsi, [rcx+10h]
0x1800c9aff  mov     rbx, rcx
0x1800c9b02  mov     rcx, rsi; lpCriticalSection
0x1800c9b05  call    cs:__imp_EnterCriticalSection
0x1800c9b0b  mov     rdi, [rbx+38h]
0x1800c9b0f  test    rdi, rdi
0x1800c9b12  jnz     short loc_1800C9B4A
0x1800c9b14  inc     dword ptr [rbx+44h]
0x1800c9b17  mov     ecx, 7F8h; Size
0x1800c9b1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c9b21  mov     rbx, rax
0x1800c9b24  test    rax, rax
0x1800c9b27  jz      short loc_1800C9B46
0x1800c9b29  call    cs:__imp_GetCurrentThreadId
0x1800c9b2f  lea     r8d, [rdi+7Ch]; unsigned int
0x1800c9b33  mov     rcx, rbx; this
0x1800c9b36  mov     edx, eax; unsigned int
0x1800c9b38  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x1800c9b3d  mov     [rbx+7F0h], rdi
0x1800c9b44  jmp     short loc_1800C9B87
0x1800c9b46  xor     ebx, ebx
0x1800c9b48  jmp     short loc_1800C9B87
0x1800c9b4a  mov     rax, [rdi+7F0h]
0x1800c9b51  mov     [rbx+38h], rax
0x1800c9b55  mov     qword ptr [rdi+7F0h], 0
0x1800c9b60  dec     dword ptr [rbx+40h]
0x1800c9b63  call    cs:__imp_GetCurrentThreadId
0x1800c9b69  mov     r8d, 7Ch ; '|'; unsigned int
0x1800c9b6f  mov     rcx, rdi; this
0x1800c9b72  mov     edx, eax; unsigned int
0x1800c9b74  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x1800c9b79  mov     qword ptr [rdi+7F0h], 0
0x1800c9b84  mov     rbx, rdi
0x1800c9b87  mov     rcx, rsi; lpCriticalSection
0x1800c9b8a  call    cs:__imp_LeaveCriticalSection
0x1800c9b90  mov     rsi, [rsp+28h+arg_8]
0x1800c9b95  mov     rax, rbx
0x1800c9b98  mov     rbx, [rsp+28h+arg_0]
0x1800c9b9d  add     rsp, 20h
0x1800c9ba1  pop     rdi
0x1800c9ba2  retn
```
