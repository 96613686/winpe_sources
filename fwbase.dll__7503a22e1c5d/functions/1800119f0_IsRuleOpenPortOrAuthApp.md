# IsRuleOpenPortOrAuthApp

- ea: `0x1800119f0`
- end: `0x180011b14`
- name: `IsRuleOpenPortOrAuthApp`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017be0`

## callees

- `0x1800119f0`

## pseudocode

```c
_BOOL8 __fastcall IsRuleOpenPortOrAuthApp(__int64 a1)
{
  unsigned int v3; // eax
  int v4; // r8d
  int v5; // ecx

  if ( *(_WORD *)(a1 + 48) != 6 && *(_WORD *)(a1 + 48) != 17 )
    return 0;
  if ( *(_DWORD *)(a1 + 64) > 1u
    || *(_DWORD *)(a1 + 64) == 1 && **(_WORD **)(a1 + 72) != *(_WORD *)(*(_QWORD *)(a1 + 72) + 2LL) )
  {
    return 0;
  }
  if ( *(_WORD *)(a1 + 56) )
    return 0;
  if ( *(_DWORD *)(a1 + 88) )
    return 0;
  if ( *(_WORD *)(a1 + 80) )
    return 0;
  if ( *(_DWORD *)(a1 + 104) )
    return 0;
  if ( *(_DWORD *)(a1 + 108) )
    return 0;
  if ( *(_DWORD *)(a1 + 112) )
    return 0;
  if ( *(_DWORD *)(a1 + 144) )
    return 0;
  if ( *(_DWORD *)(a1 + 128) )
    return 0;
  if ( *(_DWORD *)(a1 + 160) )
    return 0;
  if ( *(_DWORD *)(a1 + 248) )
    return 0;
  if ( *(_DWORD *)(a1 + 264) )
    return 0;
  v3 = *(_DWORD *)(a1 + 176);
  if ( v3 > 1 || v3 != *(_DWORD *)(a1 + 180) )
    return 0;
  v4 = *(unsigned __int16 *)(a1 + 292);
  v5 = 393;
  if ( (v4 & 0x80) == 0 )
    v5 = 385;
  return *(_DWORD *)(a1 + 44) == 1
      && !*(_QWORD *)(a1 + 280)
      && (unsigned int)(*(_DWORD *)(a1 + 288) - 2) <= 1
      && (~v5 & v4) == 0
      && !*(_QWORD *)(a1 + 296)
      && !*(_QWORD *)(a1 + 304)
      && !*(_DWORD *)(a1 + 320)
      && !*(_QWORD *)(a1 + 312);
}

```

## disassembly

```asm
0x1800119f0  cmp     word ptr [rcx+30h], 6
0x1800119f5  mov     rdx, rcx
0x1800119f8  jz      short loc_180011A04
0x1800119fa  cmp     word ptr [rcx+30h], 11h
0x1800119ff  jz      short loc_180011A04
0x180011a01  xor     eax, eax
0x180011a03  retn
0x180011a04  mov     r10d, 1
0x180011a0a  cmp     [rcx+40h], r10d
0x180011a0e  ja      short loc_180011A01
0x180011a10  jnz     short loc_180011A1F
0x180011a12  mov     rcx, [rcx+48h]
0x180011a16  movzx   eax, word ptr [rcx+2]
0x180011a1a  cmp     [rcx], ax
0x180011a1d  jnz     short loc_180011A01
0x180011a1f  xor     r9d, r9d
0x180011a22  cmp     [rdx+38h], r9w
0x180011a27  jnz     short loc_180011A01
0x180011a29  cmp     [rdx+58h], r9d
0x180011a2d  ja      short loc_180011A01
0x180011a2f  cmp     [rdx+50h], r9w
0x180011a34  jnz     short loc_180011A01
0x180011a36  cmp     [rdx+68h], r9d
0x180011a3a  jnz     short loc_180011A01
0x180011a3c  cmp     [rdx+6Ch], r9d
0x180011a40  jnz     short loc_180011A01
0x180011a42  cmp     [rdx+70h], r9d
0x180011a46  jnz     short loc_180011A01
0x180011a48  cmp     [rdx+90h], r9d
0x180011a4f  jnz     short loc_180011A01
0x180011a51  cmp     [rdx+80h], r9d
0x180011a58  jnz     short loc_180011A01
0x180011a5a  cmp     [rdx+0A0h], r9d
0x180011a61  jnz     short loc_180011A01
0x180011a63  cmp     [rdx+0F8h], r9d
0x180011a6a  jnz     short loc_180011A01
0x180011a6c  cmp     [rdx+108h], r9d
0x180011a73  jnz     short loc_180011A01
0x180011a75  mov     eax, [rdx+0B0h]
0x180011a7b  cmp     eax, r10d
0x180011a7e  ja      short loc_180011A01
0x180011a80  cmp     eax, [rdx+0B4h]
0x180011a86  jnz     loc_180011A01
0x180011a8c  movzx   r8d, word ptr [rdx+124h]
0x180011a94  mov     ecx, 189h
0x180011a99  mov     eax, 80h
0x180011a9e  test    ax, r8w
0x180011aa2  lea     eax, [rcx-8]
0x180011aa5  cmovbe  ecx, eax
0x180011aa8  cmp     [rdx+2Ch], r10d
0x180011aac  jnz     loc_180011A01
0x180011ab2  cmp     [rdx+118h], r9
0x180011ab9  jnz     loc_180011A01
0x180011abf  mov     eax, [rdx+120h]
0x180011ac5  sub     eax, 2
0x180011ac8  cmp     eax, r10d
0x180011acb  ja      loc_180011A01
0x180011ad1  not     ecx
0x180011ad3  test    r8d, ecx
0x180011ad6  jnz     loc_180011A01
0x180011adc  cmp     [rdx+128h], r9
0x180011ae3  jnz     loc_180011A01
0x180011ae9  cmp     [rdx+130h], r9
0x180011af0  jnz     loc_180011A01
0x180011af6  cmp     [rdx+140h], r9d
0x180011afd  jnz     loc_180011A01
0x180011b03  cmp     [rdx+138h], r9
0x180011b0a  jnz     loc_180011A01
0x180011b10  mov     eax, r10d
0x180011b13  retn
```
