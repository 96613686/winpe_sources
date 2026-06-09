# setColorConvThreadClass(void *,unsigned __int64,ushort *,ulong)

- ea: `0x1800149ec`
- end: `0x180014a0f`
- name: `?setColorConvThreadClass@@YAJPEAX_KPEAGK@Z`
- size: `35`
- prototype: `__int64 __fastcall(void *, unsigned __int64, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c8bc`
- `0x18000dfb0`

## callees

- `0x18000e440`
- `0x1800149ec`

## pseudocode

```c
__int64 __fastcall setColorConvThreadClass(void *a1, __int64 a2, unsigned __int16 *a3, int a4)
{
  if ( !a1 )
    return 1;
  *((_DWORD *)a1 + 3807) = a4;
  return StringCchCopyW((unsigned __int16 *)a1 + 7358, 0x100u, a3);
}

```

## disassembly

```asm
0x1800149ec  test    rcx, rcx
0x1800149ef  jz      short loc_180014A09
0x1800149f1  mov     [rcx+3B7Ch], r9d
0x1800149f8  mov     edx, 100h; unsigned __int64
0x1800149fd  add     rcx, 397Ch; unsigned __int16 *
0x180014a04  jmp     ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014a09  mov     eax, 1
0x180014a0e  retn
```
