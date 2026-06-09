# fix_tree_cost_estimates

- ea: `0x18000e4a0`
- end: `0x18000e516`
- name: `fix_tree_cost_estimates`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001870`
- `0x180010130`
- `0x1800111c0`
- `0x180014568`

## callees

- `0x18000e4a0`
- `0x18000e51c`

## pseudocode

```c
__int64 __fastcall fix_tree_cost_estimates(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  __int64 i; // rax

  LODWORD(v1) = 0;
  v2 = 0;
  do
  {
    if ( !*(_BYTE *)(v2 + a1 + 9608) )
      *(_BYTE *)(v2 + a1 + 9608) = 11;
    v1 = (unsigned int)(v1 + 1);
    ++v2;
  }
  while ( (unsigned int)v1 < 0x100 );
  while ( (unsigned int)v1 < 8 * *(_DWORD *)(a1 + 2208) + 256 )
  {
    if ( !*(_BYTE *)(v1 + a1 + 9608) )
      *(_BYTE *)(v1 + a1 + 9608) = 12;
    v1 = (unsigned int)(v1 + 1);
  }
  for ( i = 0; i != 249; ++i )
  {
    if ( !*(_BYTE *)(a1 + i + 10309) )
      *(_BYTE *)(a1 + i + 10309) = 8;
  }
  return prevent_far_matches(a1);
}

```

## disassembly

```asm
0x18000e4a0  xor     r8d, r8d
0x18000e4a3  mov     edx, r8d
0x18000e4a6  mov     eax, r8d
0x18000e4a9  cmp     [rax+rcx+2588h], r8b
0x18000e4b1  jz      short loc_18000E4E7
0x18000e4b3  inc     edx
0x18000e4b5  inc     rax
0x18000e4b8  cmp     edx, 100h
0x18000e4be  jb      short loc_18000E4A9
0x18000e4c0  mov     eax, [rcx+8A0h]
0x18000e4c6  lea     eax, ds:100h[rax*8]
0x18000e4cd  cmp     edx, eax
0x18000e4cf  jnb     short loc_18000E4F1
0x18000e4d1  cmp     [rdx+rcx+2588h], r8b
0x18000e4d9  jnz     short loc_18000E4E3
0x18000e4db  mov     byte ptr [rdx+rcx+2588h], 0Ch
0x18000e4e3  inc     edx
0x18000e4e5  jmp     short loc_18000E4C0
0x18000e4e7  mov     byte ptr [rax+rcx+2588h], 0Bh
0x18000e4ef  jmp     short loc_18000E4B3
0x18000e4f1  mov     rax, r8
0x18000e4f4  cmp     [rcx+rax+2845h], r8b
0x18000e4fc  jnz     short loc_18000E506
0x18000e4fe  mov     byte ptr [rcx+rax+2845h], 8
0x18000e506  inc     rax
0x18000e509  cmp     rax, 0F9h
0x18000e50f  jnz     short loc_18000E4F4
0x18000e511  jmp     prevent_far_matches
```
