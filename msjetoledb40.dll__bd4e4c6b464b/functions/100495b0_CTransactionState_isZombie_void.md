# CTransactionState::isZombie(void)

- ea: `0x100495b0`
- end: `0x100495c9`
- name: `?isZombie@CTransactionState@@QAEHXZ`
- size: `25`
- prototype: `int __thiscall(CTransactionState *__hidden this)`
- caller_count: `44`
- callee_count: `1`
- tags: ``

## callers

- `0x1000c0d0`
- `0x1000ce70`
- `0x1000d150`
- `0x100132e0`
- `0x10013890`
- `0x100147f0`
- `0x1001caa0`
- `0x1001cbe0`
- `0x1001cd20`
- `0x1001ce30`
- `0x1001cf40`
- `0x1001d060`
- `0x1001d180`
- `0x1001d4b0`
- `0x1001d650`
- `0x10027f00`
- `0x1002d790`
- `0x1002db00`
- `0x1002dca0`
- `0x1002dde0`
- `0x1002df50`
- `0x1002e200`
- `0x1002e3e0`
- `0x1002ef90`
- `0x1002f660`
- `0x1002f820`
- `0x10030340`
- `0x100304b0`
- `0x10030b40`
- `0x10031240`
- `0x10031490`
- `0x10031650`
- `0x10031af0`
- `0x10031e10`
- `0x10032020`
- `0x10032280`
- `0x10032510`
- `0x10032ba0`
- `0x10032e50`
- `0x10032ff0`
- `0x10033170`
- `0x100334f0`
- `0x100336f0`
- `0x10033f30`

## callees

- `0x100495b0`

## pseudocode

```c
int __thiscall CTransactionState::isZombie(CTransactionState *this)
{
  int v1; // eax

  if ( *((_DWORD *)this + 4) == 1 )
  {
    do
    {
      v1 = *((_DWORD *)this + 2);
      if ( !v1 )
        break;
      this = (CTransactionState *)*((_DWORD *)this + 2);
    }
    while ( *(_DWORD *)(v1 + 16) == 1 );
  }
  return *((_DWORD *)this + 3);
}

```

## disassembly

```asm
0x100495b0  cmp     dword ptr [ecx+10h], 1
0x100495b4  jnz     short loc_100495C5
0x100495b6  mov     eax, [ecx+8]
0x100495b9  test    eax, eax
0x100495bb  jz      short loc_100495C5
0x100495bd  mov     ecx, eax
0x100495bf  cmp     dword ptr [ecx+10h], 1
0x100495c3  jz      short loc_100495B6
0x100495c5  mov     eax, [ecx+0Ch]
0x100495c8  retn
```
