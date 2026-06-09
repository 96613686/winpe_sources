# itrp_ComputeAndCheck_PF_Proj

- ea: `0x14001e8a0`
- end: `0x14001e905`
- name: `itrp_ComputeAndCheck_PF_Proj`
- size: `101`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d2f0`
- `0x14001e910`
- `0x14001eb40`
- `0x140020190`
- `0x140020220`

## callees

- `0x14001e8a0`

## pseudocode

```c
__int64 __fastcall itrp_ComputeAndCheck_PF_Proj(__int64 a1)
{
  int v1; // r8d
  __int64 result; // rax
  bool v3; // sf

  v1 = (*(__int16 *)(a1 + 26) * *(__int16 *)(a1 + 30) + 0x2000) >> 14;
  LOWORD(v1) = ((*(__int16 *)(a1 + 24) * *(__int16 *)(a1 + 28) + 0x2000) >> 14) + v1;
  result = (unsigned int)(v1 + 1023);
  if ( (unsigned __int16)(v1 + 1023) <= 0x7FEu )
  {
    v3 = (v1 & 0x8000u) != 0;
    LOWORD(v1) = -16384;
    if ( !v3 )
      LOWORD(v1) = 0x4000;
  }
  *(_WORD *)(a1 + 98) = v1;
  *(_DWORD *)(a1 + 160) = 0;
  return result;
}

```

## disassembly

```asm
0x14001e8a0  movsx   eax, word ptr [rcx+1Ah]
0x14001e8a4  mov     r9d, 2000h
0x14001e8aa  movsx   r8d, word ptr [rcx+1Eh]
0x14001e8af  movsx   edx, word ptr [rcx+1Ch]
0x14001e8b3  imul    r8d, eax
0x14001e8b7  movsx   eax, word ptr [rcx+18h]
0x14001e8bb  imul    edx, eax
0x14001e8be  mov     eax, 3FFh
0x14001e8c3  add     r8d, r9d
0x14001e8c6  sar     r8d, 0Eh
0x14001e8ca  add     edx, r9d
0x14001e8cd  xor     r9d, r9d
0x14001e8d0  sar     edx, 0Eh
0x14001e8d3  add     r8w, dx
0x14001e8d7  mov     edx, 7FEh
0x14001e8dc  add     eax, r8d
0x14001e8df  cmp     ax, dx
0x14001e8e2  jbe     short loc_14001E8F1
0x14001e8e4  mov     [rcx+62h], r8w
0x14001e8e9  mov     [rcx+0A0h], r9d
0x14001e8f0  retn
0x14001e8f1  test    r8w, r8w
0x14001e8f5  mov     r8d, 0FFFFC000h
0x14001e8fb  js      short loc_14001E8E4
0x14001e8fd  mov     r8d, 4000h
0x14001e903  jmp     short loc_14001E8E4
```
