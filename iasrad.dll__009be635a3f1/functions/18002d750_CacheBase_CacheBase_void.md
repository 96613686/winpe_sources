# CacheBase::~CacheBase(void)

- ea: `0x18002d750`
- end: `0x18002d7cf`
- name: `??1CacheBase@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(CacheBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180020fdc`

## callees

- `0x18002d750`
- `0x18002d7d8`
- `0x18002e202`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002d760`
- `KERNEL32!EnterCriticalSection` at `0x18002d760`
- `KERNEL32!LeaveCriticalSection` at `0x18002d7b2`
- `KERNEL32!LeaveCriticalSection` at `0x18002d7b2`

## pseudocode

```c
void __fastcall CacheBase::~CacheBase(CacheBase *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rcx
  void *v4; // rcx
  size_t v5; // r8

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = (_QWORD *)*((_QWORD *)this + 8);
  while ( v2 != (_QWORD *)((char *)this + 48) )
  {
    v3 = v2;
    v2 = (_QWORD *)v2[2];
    (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
  }
  v4 = (void *)*((_QWORD *)this + 1);
  v5 = 8LL * *((unsigned int *)this + 4);
  *((_QWORD *)this + 9) = (char *)this + 48;
  *((_QWORD *)this + 8) = (char *)this + 48;
  memset_0(v4, 0, v5);
  *((_DWORD *)this + 5) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_DWORD *)this + 4) = 0;
  HashTableBase::~HashTableBase(this);
}

```

## disassembly

```asm
0x18002d750  push    rbx
0x18002d752  push    rbp
0x18002d753  push    rsi
0x18002d754  push    rdi
0x18002d755  sub     rsp, 28h
0x18002d759  mov     rdi, rcx
0x18002d75c  add     rcx, 18h; lpCriticalSection
0x18002d760  call    cs:__imp_EnterCriticalSection
0x18002d766  mov     rbx, [rdi+40h]
0x18002d76a  lea     rsi, [rdi+30h]
0x18002d76e  cmp     rbx, rsi
0x18002d771  jz      short loc_18002D788
0x18002d773  mov     rcx, rbx
0x18002d776  mov     rbx, [rbx+10h]
0x18002d77a  mov     rax, [rcx]
0x18002d77d  mov     rax, [rax+8]
0x18002d781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d786  jmp     short loc_18002D76E
0x18002d788  mov     r8d, [rdi+10h]
0x18002d78c  lea     rax, [rdi+30h]
0x18002d790  mov     rcx, [rdi+8]; void *
0x18002d794  xor     edx, edx; Val
0x18002d796  shl     r8, 3; Size
0x18002d79a  mov     [rdi+48h], rax
0x18002d79e  mov     [rdi+40h], rax
0x18002d7a2  call    memset_0
0x18002d7a7  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002d7ab  mov     dword ptr [rdi+14h], 0
0x18002d7b2  call    cs:__imp_LeaveCriticalSection
0x18002d7b8  mov     rcx, rdi; this
0x18002d7bb  mov     dword ptr [rdi+10h], 0
0x18002d7c2  add     rsp, 28h
0x18002d7c6  pop     rdi
0x18002d7c7  pop     rsi
0x18002d7c8  pop     rbp
0x18002d7c9  pop     rbx
0x18002d7ca  jmp     ??1HashTableBase@@QEAA@XZ; HashTableBase::~HashTableBase(void)
```
