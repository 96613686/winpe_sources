# CDirMonitorEntry::IORelease(void)

- ea: `0x1800173fc`
- end: `0x180017469`
- name: `?IORelease@CDirMonitorEntry@@AEAAHXZ`
- size: `109`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800172b4`
- `0x180033508`

## callees

- `0x1800173fc`
- `0x180035010`

## import_xrefs

- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180017437`
- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180017437`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x18001741f`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x18001741f`

## pseudocode

```c
__int64 __fastcall CDirMonitorEntry::IORelease(CDirMonitorEntry *this)
{
  CLKRHashTable *v1; // rdi
  unsigned int v3; // esi

  v1 = (CLKRHashTable *)*((_QWORD *)this + 12);
  v3 = 1;
  if ( v1 )
    CLKRHashTable::WriteLock(v1);
  _InterlockedDecrement((volatile signed __int32 *)this + 9);
  if ( !*((_DWORD *)this + 9) && !*((_DWORD *)this + 8) )
  {
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
0x1800173fc  mov     [rsp+arg_0], rbx
0x180017401  mov     [rsp+arg_8], rsi
0x180017406  push    rdi
0x180017407  sub     rsp, 20h
0x18001740b  mov     rdi, [rcx+60h]
0x18001740f  mov     rbx, rcx
0x180017412  mov     esi, 1
0x180017417  test    rdi, rdi
0x18001741a  jz      short loc_180017425
0x18001741c  mov     rcx, rdi
0x18001741f  call    cs:__imp_?WriteLock@CLKRHashTable@@QEAAXXZ; CLKRHashTable::WriteLock(void)
0x180017425  lock dec dword ptr [rbx+24h]
0x180017429  cmp     dword ptr [rbx+24h], 0
0x18001742d  jz      short loc_18001744F
0x18001742f  test    rdi, rdi
0x180017432  jz      short loc_18001743D
0x180017434  mov     rcx, rdi
0x180017437  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x18001743d  mov     rbx, [rsp+28h+arg_0]
0x180017442  mov     eax, esi
0x180017444  mov     rsi, [rsp+28h+arg_8]
0x180017449  add     rsp, 20h
0x18001744d  pop     rdi
0x18001744e  retn
0x18001744f  cmp     dword ptr [rbx+20h], 0
0x180017453  jnz     short loc_18001742F
0x180017455  mov     rax, [rbx]
0x180017458  mov     edx, esi
0x18001745a  mov     rcx, rbx
0x18001745d  mov     rax, [rax]
0x180017460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017465  xor     esi, esi
0x180017467  jmp     short loc_18001742F
```
