# DrSession::RemovePacketReceiver(ISessionPacketReceiver *)

- ea: `0x14001d504`
- end: `0x14001d558`
- name: `?RemovePacketReceiver@DrSession@@QEAAXPEAVISessionPacketReceiver@@@Z`
- size: `84`
- prototype: `void __fastcall(DrSession *__hidden this, struct ISessionPacketReceiver *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001bcb0`

## callees

- `0x140001c50`
- `0x140001e60`
- `0x140001ef0`
- `0x140002260`
- `0x140002564`
- `0x14001d504`

## pseudocode

```c
void __fastcall DrSession::RemovePacketReceiver(DrSession *this, struct ISessionPacketReceiver *a2)
{
  DoubleList *v2; // rbx
  struct ListEntry *i; // rax
  DoubleList *v5; // rcx

  v2 = (DrSession *)((char *)this + 48);
  DoubleList::LockExclusive((DrSession *)((char *)this + 48));
  for ( i = DoubleList::First(v2); i; i = DoubleList::Next(v2, i) )
  {
    if ( *((struct ISessionPacketReceiver **)i + 2) == a2 )
    {
      DoubleList::RemoveEntry(v5, (struct ListEntry ***)i);
      break;
    }
  }
  DoubleList::Unlock(v2);
}

```

## disassembly

```asm
0x14001d504  mov     [rsp+arg_0], rbx
0x14001d509  push    rdi
0x14001d50a  sub     rsp, 20h
0x14001d50e  lea     rbx, [rcx+30h]
0x14001d512  mov     rdi, rdx
0x14001d515  mov     rcx, rbx; this
0x14001d518  call    ?LockExclusive@DoubleList@@QEAAXXZ; DoubleList::LockExclusive(void)
0x14001d51d  mov     rcx, rbx; this
0x14001d520  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x14001d525  jmp     short loc_14001D538
0x14001d527  mov     rdx, rax; struct ListEntry *
0x14001d52a  cmp     [rax+10h], rdi
0x14001d52e  jz      short loc_14001D53F
0x14001d530  mov     rcx, rbx; this
0x14001d533  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x14001d538  test    rax, rax
0x14001d53b  jnz     short loc_14001D527
0x14001d53d  jmp     short loc_14001D544
0x14001d53f  call    ?RemoveEntry@DoubleList@@QEAAXPEAVListEntry@@@Z; DoubleList::RemoveEntry(ListEntry *)
0x14001d544  mov     rcx, rbx; this
0x14001d547  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x14001d54c  mov     rbx, [rsp+28h+arg_0]
0x14001d551  add     rsp, 20h
0x14001d555  pop     rdi
0x14001d556  retn
```
