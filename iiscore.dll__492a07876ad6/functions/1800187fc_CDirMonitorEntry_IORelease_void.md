# CDirMonitorEntry::IORelease(void)

- ea: `0x1800187fc`
- end: `0x180018876`
- name: `?IORelease@CDirMonitorEntry@@AEAAHXZ`
- size: `122`
- prototype: `__int64 __fastcall(CDirMonitorEntry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001869c`
- `0x180036748`

## callees

- `0x1800187fc`
- `0x180038010`

## import_xrefs

- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x18001883d`
- `iisutil!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x18001883d`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x18001881f`
- `iisutil!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x18001881f`

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
0x1800187fc  mov     [rsp+arg_0], rbx
0x180018801  mov     [rsp+arg_8], rsi
0x180018806  push    rdi
0x180018807  sub     rsp, 20h
0x18001880b  mov     rdi, [rcx+60h]
0x18001880f  mov     rbx, rcx
0x180018812  mov     esi, 1
0x180018817  test    rdi, rdi
0x18001881a  jz      short loc_18001882B
0x18001881c  mov     rcx, rdi
0x18001881f  call    cs:__imp_?WriteLock@CLKRHashTable@@QEAAXXZ; CLKRHashTable::WriteLock(void)
0x180018826  nop     dword ptr [rax+rax+00h]
0x18001882b  lock dec dword ptr [rbx+24h]
0x18001882f  cmp     dword ptr [rbx+24h], 0
0x180018833  jz      short loc_18001885C
0x180018835  test    rdi, rdi
0x180018838  jz      short loc_180018849
0x18001883a  mov     rcx, rdi
0x18001883d  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x180018844  nop     dword ptr [rax+rax+00h]
0x180018849  mov     rbx, [rsp+28h+arg_0]
0x18001884e  mov     eax, esi
0x180018850  mov     rsi, [rsp+28h+arg_8]
0x180018855  add     rsp, 20h
0x180018859  pop     rdi
0x18001885a  retn
0x18001885c  cmp     dword ptr [rbx+20h], 0
0x180018860  jnz     short loc_180018835
0x180018862  mov     rax, [rbx]
0x180018865  mov     edx, esi
0x180018867  mov     rcx, rbx
0x18001886a  mov     rax, [rax]
0x18001886d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018872  xor     esi, esi
0x180018874  jmp     short loc_180018835
```
