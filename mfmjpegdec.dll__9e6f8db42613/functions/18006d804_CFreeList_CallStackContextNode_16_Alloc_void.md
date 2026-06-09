# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x18006d804`
- end: `0x18006d8b4`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006d940`

## callees

- `0x18002131c`
- `0x180021444`
- `0x180021584`
- `0x180023df0`
- `0x18006d804`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d81a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d81a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d83e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d878`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d83e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d878`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  CallStackContext *v2; // rdi
  CallStackContext *v3; // rbx
  DWORD v4; // eax
  DWORD CurrentThreadId; // eax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v2 = *(CallStackContext **)(a1 + 56);
  if ( v2 )
  {
    *(_QWORD *)(a1 + 56) = *((_QWORD *)v2 + 254);
    *((_QWORD *)v2 + 254) = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    CallStackContext::Init(v2, CurrentThreadId, 0x7Cu);
    *((_QWORD *)v2 + 254) = 0;
    v3 = v2;
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v3 = (CallStackContext *)operator new(0x7F8u);
    if ( v3 )
    {
      v4 = GetCurrentThreadId();
      CallStackContext::CallStackContext(v3, v4, 0x7Cu);
      *((_QWORD *)v3 + 254) = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  CMFCSAutoLock::~CMFCSAutoLock((CMFCSAutoLock *)&v7);
  return v3;
}

```

## disassembly

```asm
0x18006d804  mov     [rsp+arg_8], rbx
0x18006d809  push    rdi
0x18006d80a  sub     rsp, 20h
0x18006d80e  mov     rbx, rcx
0x18006d811  add     rcx, 10h; lpCriticalSection
0x18006d815  mov     [rsp+28h+arg_0], rcx
0x18006d81a  call    cs:__imp_EnterCriticalSection
0x18006d820  mov     rdi, [rbx+38h]
0x18006d824  test    rdi, rdi
0x18006d827  jnz     short loc_18006D85F
0x18006d829  inc     dword ptr [rbx+44h]
0x18006d82c  mov     ecx, 7F8h; Size
0x18006d831  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d836  mov     rbx, rax
0x18006d839  test    rax, rax
0x18006d83c  jz      short loc_18006D85B
0x18006d83e  call    cs:__imp_GetCurrentThreadId
0x18006d844  lea     r8d, [rdi+7Ch]; unsigned int
0x18006d848  mov     rcx, rbx; this
0x18006d84b  mov     edx, eax; unsigned int
0x18006d84d  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x18006d852  mov     [rbx+7F0h], rdi
0x18006d859  jmp     short loc_18006D89C
0x18006d85b  xor     ebx, ebx
0x18006d85d  jmp     short loc_18006D89C
0x18006d85f  mov     rax, [rdi+7F0h]
0x18006d866  mov     [rbx+38h], rax
0x18006d86a  mov     qword ptr [rdi+7F0h], 0
0x18006d875  dec     dword ptr [rbx+40h]
0x18006d878  call    cs:__imp_GetCurrentThreadId
0x18006d87e  mov     r8d, 7Ch ; '|'; unsigned int
0x18006d884  mov     rcx, rdi; this
0x18006d887  mov     edx, eax; unsigned int
0x18006d889  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18006d88e  mov     qword ptr [rdi+7F0h], 0
0x18006d899  mov     rbx, rdi
0x18006d89c  lea     rcx, [rsp+28h+arg_0]; this
0x18006d8a1  call    ??1CMFCSAutoLock@@QEAA@XZ; CMFCSAutoLock::~CMFCSAutoLock(void)
0x18006d8a6  mov     rax, rbx
0x18006d8a9  mov     rbx, [rsp+28h+arg_8]
0x18006d8ae  add     rsp, 20h
0x18006d8b2  pop     rdi
0x18006d8b3  retn
```
