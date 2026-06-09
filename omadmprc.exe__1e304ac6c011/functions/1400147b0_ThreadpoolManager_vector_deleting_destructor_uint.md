# ThreadpoolManager::`vector deleting destructor'(uint)

- ea: `0x1400147b0`
- end: `0x1400147e7`
- name: `??_EThreadpoolManager@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(ThreadpoolManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400146c8`
- `0x1400147b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400147cc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400147cc`

## pseudocode

```c
ThreadpoolManager *__fastcall ThreadpoolManager::`vector deleting destructor'(ThreadpoolManager *this, char a2)
{
  ThreadpoolManager::~ThreadpoolManager(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400147b0  mov     [rsp+arg_0], rbx
0x1400147b5  push    rdi
0x1400147b6  sub     rsp, 20h
0x1400147ba  mov     ebx, edx
0x1400147bc  mov     rdi, rcx
0x1400147bf  call    ??1ThreadpoolManager@@UEAA@XZ; ThreadpoolManager::~ThreadpoolManager(void)
0x1400147c4  test    bl, 1
0x1400147c7  jz      short loc_1400147D8
0x1400147c9  mov     rcx, rdi
0x1400147cc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400147d3  nop     dword ptr [rax+rax+00h]
0x1400147d8  mov     rbx, [rsp+28h+arg_0]
0x1400147dd  mov     rax, rdi
0x1400147e0  add     rsp, 20h
0x1400147e4  pop     rdi
0x1400147e5  retn
```
