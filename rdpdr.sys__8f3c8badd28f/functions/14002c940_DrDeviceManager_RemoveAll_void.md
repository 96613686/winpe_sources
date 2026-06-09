# DrDeviceManager::RemoveAll(void)

- ea: `0x14002c940`
- end: `0x14002c9e6`
- name: `?RemoveAll@DrDeviceManager@@QEAAXXZ`
- size: `166`
- prototype: `void __fastcall(DrDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14001c6e0`

## callees

- `0x140001660`
- `0x140001c50`
- `0x140001e60`
- `0x140001ef0`
- `0x140002260`
- `0x140002564`
- `0x140006560`
- `0x14002c940`

## pseudocode

```c
void __fastcall DrDeviceManager::RemoveAll(DrDeviceManager *this)
{
  DoubleList *v1; // rdi
  struct ListEntry *v2; // rbx
  RefCount *v3; // rsi
  DoubleList *v4; // rcx
  struct ListEntry *v5; // rax

  v1 = (DrDeviceManager *)((char *)this + 32);
  DoubleList::LockExclusive((DrDeviceManager *)((char *)this + 32));
  v2 = DoubleList::First(v1);
  if ( v2 )
  {
    do
    {
      v3 = (RefCount *)*((_QWORD *)v2 + 2);
      if ( (*(unsigned int (__fastcall **)(RefCount *))(*(_QWORD *)v3 + 72LL))(v3) )
      {
        (*(void (__fastcall **)(RefCount *))(*(_QWORD *)v3 + 80LL))(v3);
        v5 = DoubleList::Next(v1, v2);
      }
      else
      {
        DoubleList::RemoveEntry(v4, (struct ListEntry ***)v2);
        (*(void (__fastcall **)(RefCount *))(*(_QWORD *)v3 + 64LL))(v3);
        RefCount::Release(v3);
        v5 = DoubleList::First(v1);
      }
      v2 = v5;
    }
    while ( v5 );
  }
  DoubleList::Unlock(v1);
}

```

## disassembly

```asm
0x14002c940  mov     [rsp+arg_0], rbx
0x14002c945  mov     [rsp+arg_8], rsi
0x14002c94a  push    rdi
0x14002c94b  sub     rsp, 20h
0x14002c94f  lea     rdi, [rcx+20h]
0x14002c953  mov     rcx, rdi; this
0x14002c956  call    ?LockExclusive@DoubleList@@QEAAXXZ; DoubleList::LockExclusive(void)
0x14002c95b  mov     rcx, rdi; this
0x14002c95e  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14002c963  mov     rbx, rax
0x14002c966  test    rax, rax
0x14002c969  jz      short loc_14002C9CD
0x14002c96b  mov     rsi, [rbx+10h]
0x14002c96f  mov     rcx, [rsi]
0x14002c972  mov     rax, [rcx+48h]
0x14002c976  mov     rcx, rsi
0x14002c979  call    _guard_dispatch_icall
0x14002c97e  test    eax, eax
0x14002c980  jnz     short loc_14002C9AB
0x14002c982  mov     rdx, rbx; struct ListEntry *
0x14002c985  call    ?RemoveEntry@DoubleList@@QEAAXPEAVListEntry@@@Z; DoubleList::RemoveEntry(ListEntry *)
0x14002c98a  mov     rax, [rsi]
0x14002c98d  mov     rcx, rsi
0x14002c990  mov     rax, [rax+40h]
0x14002c994  call    _guard_dispatch_icall
0x14002c999  mov     rcx, rsi; this
0x14002c99c  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002c9a1  mov     rcx, rdi; this
0x14002c9a4  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14002c9a9  jmp     short loc_14002C9C5
0x14002c9ab  mov     rax, [rsi]
0x14002c9ae  mov     rcx, rsi
0x14002c9b1  mov     rax, [rax+50h]
0x14002c9b5  call    _guard_dispatch_icall
0x14002c9ba  mov     rdx, rbx; struct ListEntry *
0x14002c9bd  mov     rcx, rdi; this
0x14002c9c0  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x14002c9c5  mov     rbx, rax
0x14002c9c8  test    rax, rax
0x14002c9cb  jnz     short loc_14002C96B
0x14002c9cd  mov     rcx, rdi; this
0x14002c9d0  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x14002c9d5  mov     rbx, [rsp+28h+arg_0]
0x14002c9da  mov     rsi, [rsp+28h+arg_8]
0x14002c9df  add     rsp, 20h
0x14002c9e3  pop     rdi
0x14002c9e4  retn
```
