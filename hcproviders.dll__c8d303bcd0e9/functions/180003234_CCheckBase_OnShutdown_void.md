# CCheckBase::OnShutdown(void)

- ea: `0x180003234`
- end: `0x18000329d`
- name: `?OnShutdown@CCheckBase@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CCheckBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003090`
- `0x180003160`

## callees

- `0x180003234`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003254`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003254`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003291`

## pseudocode

```c
void __fastcall CCheckBase::OnShutdown(RTL_SRWLOCK *this)
{
  PVOID Ptr; // rcx

  (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 17))(this);
  AcquireSRWLockExclusive(this + 2);
  Ptr = this[27].Ptr;
  if ( Ptr )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
  this[27].Ptr = 0;
  ReleaseSRWLockExclusive(this + 2);
}

```

## disassembly

```asm
0x180003234  mov     [rsp+arg_0], rbx
0x180003239  push    rdi
0x18000323a  sub     rsp, 20h
0x18000323e  mov     rax, [rcx]
0x180003241  mov     rbx, rcx
0x180003244  mov     rax, [rax+88h]
0x18000324b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003250  lea     rcx, [rbx+10h]; SRWLock
0x180003254  call    cs:__imp_AcquireSRWLockExclusive
0x18000325b  nop     dword ptr [rax+rax+00h]
0x180003260  mov     rcx, [rbx+0D8h]
0x180003267  test    rcx, rcx
0x18000326a  jz      short loc_180003278
0x18000326c  mov     rax, [rcx]
0x18000326f  mov     rax, [rax+10h]
0x180003273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003278  lea     rcx, [rbx+10h]
0x18000327c  mov     qword ptr [rbx+0D8h], 0
0x180003287  mov     rbx, [rsp+28h+arg_0]
0x18000328c  add     rsp, 20h
0x180003290  pop     rdi
0x180003291  jmp     cs:__imp_ReleaseSRWLockExclusive
```
