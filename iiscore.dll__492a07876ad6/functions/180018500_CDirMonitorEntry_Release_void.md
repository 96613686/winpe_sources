# CDirMonitorEntry::Release(void)

- ea: `0x180018500`
- end: `0x180018582`
- name: `?Release@CDirMonitorEntry@@UEAAHXZ`
- size: `130`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180018500`
- `0x180036338`
- `0x180038010`

## import_xrefs

- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180018543`
- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180018543`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x180018523`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x180018523`

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
0x180018500  mov     [rsp+arg_8], rbx
0x180018505  mov     [rsp+arg_10], rsi
0x18001850a  push    rdi
0x18001850b  sub     rsp, 20h
0x18001850f  mov     rbx, [rcx+60h]
0x180018513  mov     rdi, rcx
0x180018516  mov     esi, 1
0x18001851b  test    rbx, rbx
0x18001851e  jz      short loc_18001852F
0x180018520  mov     rcx, rbx
0x180018523  call    cs:__imp_?WriteLock@CLKRHashTable@@QEAAXXZ; CLKRHashTable::WriteLock(void)
0x18001852a  nop     dword ptr [rax+rax+00h]
0x18001852f  or      eax, 0FFFFFFFFh
0x180018532  lock xadd [rdi+20h], eax
0x180018537  cmp     eax, esi
0x180018539  jz      short loc_180018562
0x18001853b  test    rbx, rbx
0x18001853e  jz      short loc_18001854F
0x180018540  mov     rcx, rbx
0x180018543  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x18001854a  nop     dword ptr [rax+rax+00h]
0x18001854f  mov     rbx, [rsp+28h+arg_8]
0x180018554  mov     eax, esi
0x180018556  mov     rsi, [rsp+28h+arg_10]
0x18001855b  add     rsp, 20h
0x18001855f  pop     rdi
0x180018560  retn
0x180018562  mov     rcx, rdi; this
0x180018565  call    ?Cleanup@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::Cleanup(void)
0x18001856a  test    eax, eax
0x18001856c  jz      short loc_18001857E
0x18001856e  mov     rax, [rdi]
0x180018571  mov     edx, esi
0x180018573  mov     rcx, rdi
0x180018576  mov     rax, [rax]
0x180018579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001857e  xor     esi, esi
0x180018580  jmp     short loc_18001853B
```
