# DequeueInterruptReadIrp

- ea: `0x18000ebb0`
- end: `0x18000ec09`
- name: `DequeueInterruptReadIrp`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e880`
- `0x1800125c4`

## callees

- `0x18000ebb0`

## pseudocode

```c
_QWORD *__fastcall DequeueInterruptReadIrp(__int64 a1, __int64 a2)
{
  _QWORD **v3; // rax
  _QWORD *v4; // r8
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx

  v3 = (_QWORD **)(a2 + 24);
LABEL_2:
  v4 = 0;
  do
  {
    v5 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v5[1] != v3 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v3 = v6;
    v4 = v5 - 21;
    v6[1] = v3;
    if ( !_InterlockedExchange64(v5 - 8, 0) )
    {
      v5[1] = v5;
      *v5 = v5;
      goto LABEL_2;
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
  }
  while ( v5 == (_QWORD *)168 );
  return v4;
}

```

## disassembly

```asm
0x18000ebb0  mov     r9, rcx
0x18000ebb3  lea     rax, [rdx+18h]
0x18000ebb7  xor     r8d, r8d
0x18000ebba  mov     rdx, [rax]
0x18000ebbd  cmp     rdx, rax
0x18000ebc0  jz      short loc_18000EBF4
0x18000ebc2  cmp     [rdx+8], rax
0x18000ebc6  jnz     short loc_18000EBF9
0x18000ebc8  mov     rcx, [rdx]
0x18000ebcb  cmp     [rcx+8], rdx
0x18000ebcf  jnz     short loc_18000EBF9
0x18000ebd1  mov     [rax], rcx
0x18000ebd4  lea     r8, [rdx-0A8h]
0x18000ebdb  mov     [rcx+8], rax
0x18000ebdf  xor     ecx, ecx
0x18000ebe1  xchg    rcx, [r8+68h]
0x18000ebe5  test    rcx, rcx
0x18000ebe8  jz      short loc_18000EC00
0x18000ebea  lock dec dword ptr [r9+10h]
0x18000ebef  test    r8, r8
0x18000ebf2  jz      short loc_18000EBBA
0x18000ebf4  mov     rax, r8
0x18000ebf7  retn
0x18000ebf9  mov     ecx, 3
0x18000ebfe  int     29h; Win8: RtlFailFast(ecx)
0x18000ec00  mov     [rdx+8], rdx
0x18000ec04  mov     [rdx], rdx
0x18000ec07  jmp     short loc_18000EBB7
```
