# FastCoCreator::~FastCoCreator(void)

- ea: `0x18002c774`
- end: `0x18002c7a2`
- name: `??1FastCoCreator@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(FastCoCreator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002fe60`

## callees

- `0x18002c774`
- `0x180030010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002c79b`

## pseudocode

```c
void __fastcall FastCoCreator::~FastCoCreator(FastCoCreator *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18002c774  push    rbx
0x18002c776  sub     rsp, 20h
0x18002c77a  mov     rbx, rcx
0x18002c77d  mov     rcx, [rcx+40h]
0x18002c781  test    rcx, rcx
0x18002c784  jz      short loc_18002C792
0x18002c786  mov     rax, [rcx]
0x18002c789  mov     rax, [rax+10h]
0x18002c78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c792  lea     rcx, [rbx+10h]
0x18002c796  add     rsp, 20h
0x18002c79a  pop     rbx
0x18002c79b  jmp     cs:__imp_DeleteCriticalSection
```
