# CReaderWriterLock3::_WriteLockSpin(void)

- ea: `0x180019a34`
- end: `0x180019a56`
- name: `?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ`
- size: `34`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800026c0`
- `0x1800029d0`
- `0x180002d60`
- `0x180004010`
- `0x180004180`

## callees

- `0x18001971c`
- `0x180019a34`

## pseudocode

```c
void __fastcall CReaderWriterLock3::_WriteLockSpin(CReaderWriterLock3 *this)
{
  signed __int32 v1; // r8d

  do
    v1 = *(_DWORD *)this;
  while ( v1 != _InterlockedCompareExchange((volatile signed __int32 *)this, v1 + 0x10000, v1) );
  CReaderWriterLock3::_LockSpin((volatile signed __int32 *)this, 1);
}

```

## disassembly

```asm
0x180019a34  xchg    ax, ax
0x180019a36  mov     r8d, [rcx]
0x180019a39  mov     eax, r8d
0x180019a3c  lea     edx, [r8+10000h]
0x180019a43  lock cmpxchg [rcx], edx
0x180019a47  cmp     r8d, eax
0x180019a4a  jnz     short loc_180019A36
0x180019a4c  mov     edx, 1
0x180019a51  jmp     ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
```
