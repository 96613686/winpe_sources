# CDirMonitorEntry::Release(void)

- ea: `0x180017110`
- end: `0x180017185`
- name: `?Release@CDirMonitorEntry@@UEAAHXZ`
- size: `117`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180017110`
- `0x180033158`
- `0x180035010`

## import_xrefs

- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x18001714d`
- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x18001714d`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x180017133`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x180017133`

## pseudocode

```c
__int64 __fastcall CDirMonitorEntry::Release(CDirMonitorEntry *this)
{
  CLKRHashTable *v1; // rbx
  unsigned int v3; // esi

  v1 = (CLKRHashTable *)*((_QWORD *)this + 12);
  v3 = 1;
  if ( v1 )
    CLKRHashTable::WriteLock(*((CLKRHashTable **)this + 12));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 8, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned int)CDirMonitorEntry::Cleanup(this) )
      (**(void (__fastcall ***)(CDirMonitorEntry *, __int64))this)(this, 1);
    v3 = 0;
  }
  if ( v1 )
    CLKRHashTable::WriteUnlock(v1);
  return v3;
}

```

## disassembly

```asm
0x180017110  mov     [rsp+arg_8], rbx
0x180017115  mov     [rsp+arg_10], rsi
0x18001711a  push    rdi
0x18001711b  sub     rsp, 20h
0x18001711f  mov     rbx, [rcx+60h]
0x180017123  mov     rdi, rcx
0x180017126  mov     esi, 1
0x18001712b  test    rbx, rbx
0x18001712e  jz      short loc_180017139
0x180017130  mov     rcx, rbx
0x180017133  call    cs:__imp_?WriteLock@CLKRHashTable@@QEAAXXZ; CLKRHashTable::WriteLock(void)
0x180017139  or      eax, 0FFFFFFFFh
0x18001713c  lock xadd [rdi+20h], eax
0x180017141  cmp     eax, esi
0x180017143  jz      short loc_180017165
0x180017145  test    rbx, rbx
0x180017148  jz      short loc_180017153
0x18001714a  mov     rcx, rbx
0x18001714d  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x180017153  mov     rbx, [rsp+28h+arg_8]
0x180017158  mov     eax, esi
0x18001715a  mov     rsi, [rsp+28h+arg_10]
0x18001715f  add     rsp, 20h
0x180017163  pop     rdi
0x180017164  retn
0x180017165  mov     rcx, rdi; this
0x180017168  call    ?Cleanup@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::Cleanup(void)
0x18001716d  test    eax, eax
0x18001716f  jz      short loc_180017181
0x180017171  mov     rax, [rdi]
0x180017174  mov     edx, esi
0x180017176  mov     rcx, rdi
0x180017179  mov     rax, [rax]
0x18001717c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017181  xor     esi, esi
0x180017183  jmp     short loc_180017145
```
