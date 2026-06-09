# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x180039710`
- end: `0x1800397c7`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180039a00`

## callees

- `0x1800018a4`
- `0x180039710`
- `0x1800397d0`
- `0x180039dc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039729`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003974d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003974d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039787`

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
0x180039710  mov     [rsp+arg_0], rbx
0x180039715  mov     [rsp+arg_8], rsi
0x18003971a  push    rdi
0x18003971b  sub     rsp, 20h
0x18003971f  lea     rsi, [rcx+10h]
0x180039723  mov     rbx, rcx
0x180039726  mov     rcx, rsi; lpCriticalSection
0x180039729  call    cs:__imp_EnterCriticalSection
0x18003972f  mov     rdi, [rbx+38h]
0x180039733  test    rdi, rdi
0x180039736  jnz     short loc_18003976E
0x180039738  inc     dword ptr [rbx+44h]
0x18003973b  mov     ecx, 7F8h; Size
0x180039740  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039745  mov     rbx, rax
0x180039748  test    rax, rax
0x18003974b  jz      short loc_18003976A
0x18003974d  call    cs:__imp_GetCurrentThreadId
0x180039753  lea     r8d, [rdi+7Ch]; unsigned int
0x180039757  mov     rcx, rbx; this
0x18003975a  mov     edx, eax; unsigned int
0x18003975c  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180039761  mov     [rbx+7F0h], rdi
0x180039768  jmp     short loc_1800397AB
0x18003976a  xor     ebx, ebx
0x18003976c  jmp     short loc_1800397AB
0x18003976e  mov     rax, [rdi+7F0h]
0x180039775  mov     [rbx+38h], rax
0x180039779  mov     qword ptr [rdi+7F0h], 0
0x180039784  dec     dword ptr [rbx+40h]
0x180039787  call    cs:__imp_GetCurrentThreadId
0x18003978d  mov     r8d, 7Ch ; '|'; unsigned int
0x180039793  mov     rcx, rdi; this
0x180039796  mov     edx, eax; unsigned int
0x180039798  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18003979d  mov     qword ptr [rdi+7F0h], 0
0x1800397a8  mov     rbx, rdi
0x1800397ab  mov     rcx, rsi; lpCriticalSection
0x1800397ae  call    cs:__imp_LeaveCriticalSection
0x1800397b4  mov     rsi, [rsp+28h+arg_8]
0x1800397b9  mov     rax, rbx
0x1800397bc  mov     rbx, [rsp+28h+arg_0]
0x1800397c1  add     rsp, 20h
0x1800397c5  pop     rdi
0x1800397c6  retn
```
