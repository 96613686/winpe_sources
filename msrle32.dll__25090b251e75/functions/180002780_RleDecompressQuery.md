# RleDecompressQuery

- ea: `0x180002780`
- end: `0x1800027ec`
- name: `RleDecompressQuery`
- size: `108`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`
- `0x1800025c4`
- `0x180002680`

## callees

- `0x180002780`
- `0x1800027f4`

## pseudocode

```c
__int64 __fastcall RleDecompressQuery(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v5; // ax

  if ( a2
    && (unsigned int)ValidateBitmapInfoHeader(a2)
    && ((v5 = *(_WORD *)(a2 + 14), v5 == 8) || *(_DWORD *)(a2 + 16) != 1)
    && *(_DWORD *)(a2 + 16) <= 1u
    && (!a3
     || !*(_DWORD *)(a3 + 16)
     && *(_WORD *)(a3 + 14) == v5
     && *(_DWORD *)(a3 + 4) == *(_DWORD *)(a2 + 4)
     && *(_DWORD *)(a3 + 8) == *(_DWORD *)(a2 + 8)) )
  {
    return 0;
  }
  else
  {
    return 4294967294LL;
  }
}

```

## disassembly

```asm
0x180002780  mov     [rsp+arg_0], rbx
0x180002785  push    rdi
0x180002786  sub     rsp, 20h
0x18000278a  mov     rdi, r8
0x18000278d  mov     rbx, rdx
0x180002790  test    rdx, rdx
0x180002793  jz      short loc_1800027DC
0x180002795  mov     rcx, rdx
0x180002798  call    ValidateBitmapInfoHeader
0x18000279d  test    eax, eax
0x18000279f  jz      short loc_1800027DC
0x1800027a1  movzx   eax, word ptr [rbx+0Eh]
0x1800027a5  cmp     ax, 8
0x1800027a9  jz      short loc_1800027B1
0x1800027ab  cmp     dword ptr [rbx+10h], 1
0x1800027af  jz      short loc_1800027DC
0x1800027b1  cmp     dword ptr [rbx+10h], 1
0x1800027b5  ja      short loc_1800027DC
0x1800027b7  test    rdi, rdi
0x1800027ba  jnz     short loc_1800027C0
0x1800027bc  xor     eax, eax
0x1800027be  jmp     short loc_1800027E1
0x1800027c0  cmp     dword ptr [rdi+10h], 0
0x1800027c4  jnz     short loc_1800027DC
0x1800027c6  cmp     [rdi+0Eh], ax
0x1800027ca  jnz     short loc_1800027DC
0x1800027cc  mov     eax, [rbx+4]
0x1800027cf  cmp     [rdi+4], eax
0x1800027d2  jnz     short loc_1800027DC
0x1800027d4  mov     eax, [rbx+8]
0x1800027d7  cmp     [rdi+8], eax
0x1800027da  jz      short loc_1800027BC
0x1800027dc  mov     eax, 0FFFFFFFEh
0x1800027e1  mov     rbx, [rsp+28h+arg_0]
0x1800027e6  add     rsp, 20h
0x1800027ea  pop     rdi
0x1800027eb  retn
```
