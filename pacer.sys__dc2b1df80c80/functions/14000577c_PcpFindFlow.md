# PcpFindFlow

- ea: `0x14000577c`
- end: `0x1400057a3`
- name: `PcpFindFlow`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005438`
- `0x14000570c`
- `0x14000d284`
- `0x14000fd20`

## callees

- `0x14000577c`

## pseudocode

```c
__int64 __fastcall PcpFindFlow(_QWORD *a1, __int64 a2)
{
  _QWORD *v2; // r9
  unsigned int v3; // r8d
  _QWORD *i; // rdx

  v2 = (_QWORD *)(a2 + 16);
  v3 = -1073741275;
  for ( i = *(_QWORD **)(a2 + 16); i != v2; i = (_QWORD *)*i )
  {
    if ( i - 2 == a1 )
      return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14000577c  lea     r9, [rdx+10h]
0x140005780  mov     r8d, 0C0000225h
0x140005786  mov     rdx, [r9]
0x140005789  cmp     rdx, r9
0x14000578c  jz      short loc_14000579F
0x14000578e  lea     rax, [rdx-10h]
0x140005792  cmp     rax, rcx
0x140005795  jz      short loc_14000579C
0x140005797  mov     rdx, [rdx]
0x14000579a  jmp     short loc_140005789
0x14000579c  xor     r8d, r8d
0x14000579f  mov     eax, r8d
0x1400057a2  retn
```
