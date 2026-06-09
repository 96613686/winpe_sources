# appendPathSeparator

- ea: `0x140008f3c`
- end: `0x140008f69`
- name: `appendPathSeparator`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400072bc`
- `0x140008f70`
- `0x14000907c`
- `0x140009454`

## callees

- `0x140008f3c`

## pseudocode

```c
__int64 __fastcall appendPathSeparator(char *a1)
{
  __int64 v1; // rdx

  if ( (unsigned __int8)*a1 <= 0x3Au )
  {
    v1 = 0x400800000000001LL;
    if ( _bittest64(&v1, *a1) )
      return 0;
  }
  if ( *a1 == 92 )
    return 0;
  *(_WORD *)(a1 + 1) = 92;
  return 1;
}

```

## disassembly

```asm
0x140008f3c  cmp     byte ptr [rcx], 3Ah ; ':'
0x140008f3f  ja      short loc_140008F55
0x140008f41  movsx   rax, byte ptr [rcx]
0x140008f45  mov     rdx, 400800000000001h
0x140008f4f  bt      rdx, rax
0x140008f53  jb      short loc_140008F66
0x140008f55  cmp     byte ptr [rcx], 5Ch ; '\'
0x140008f58  jz      short loc_140008F66
0x140008f5a  mov     word ptr [rcx+1], 5Ch ; '\'
0x140008f60  mov     eax, 1
0x140008f65  retn
0x140008f66  xor     eax, eax
0x140008f68  retn
```
