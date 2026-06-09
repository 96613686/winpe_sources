# AslpFileStringTokenize

- ea: `0x180013218`
- end: `0x1800132d9`
- name: `AslpFileStringTokenize`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013374`

## callees

- `0x180013218`

## pseudocode

```c
_WORD *__fastcall AslpFileStringTokenize(_WORD *a1, __int64 a2, _WORD **a3)
{
  _WORD *v4; // rdx
  const WCHAR *v5; // rcx
  WCHAR v6; // r8
  _WORD *v7; // r9
  _WORD *v8; // r11
  const WCHAR *v9; // rcx
  WCHAR v10; // r8
  _WORD *v11; // r8

  v4 = a1;
  if ( !a3 )
    return 0;
  if ( !a1 )
  {
    v4 = *a3;
    if ( !*a3 )
      return 0;
  }
  while ( *v4 )
  {
    v5 = L"\\";
    if ( asc_18001D1B4[0] )
    {
      v6 = asc_18001D1B4[0];
      do
      {
        if ( v6 == *v4 )
          break;
        v6 = *++v5;
      }
      while ( *v5 );
    }
    if ( !*v5 )
      break;
    ++v4;
  }
  v7 = v4;
  v8 = v4;
  if ( *v4 )
  {
    while ( 1 )
    {
      v9 = L"\\";
      if ( asc_18001D1B4[0] )
      {
        v10 = asc_18001D1B4[0];
        do
        {
          if ( v10 == *v4 )
            break;
          v10 = *++v9;
        }
        while ( *v9 );
      }
      v11 = v4 + 1;
      if ( *v9 )
        break;
      ++v4;
      if ( !*v11 )
        goto LABEL_21;
    }
    *v4++ = 0;
  }
LABEL_21:
  *a3 = v4;
  if ( v4 == v8 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x180013218  mov     [rsp+arg_0], rbx
0x18001321d  xor     ebx, ebx
0x18001321f  mov     r10, r8
0x180013222  mov     rdx, rcx
0x180013225  test    r8, r8
0x180013228  jz      loc_1800132D1
0x18001322e  test    rcx, rcx
0x180013231  jnz     short loc_18001323F
0x180013233  mov     rdx, [r8]
0x180013236  test    rdx, rdx
0x180013239  jz      loc_1800132D1
0x18001323f  mov     eax, dword ptr cs:asc_18001D1B4; "\\"
0x180013245  jmp     short loc_180013274
0x180013247  lea     rcx, asc_18001D1B4; "\\"
0x18001324e  test    ax, ax
0x180013251  jz      short loc_18001326B
0x180013253  movzx   r8d, ax
0x180013257  cmp     r8w, [rdx]
0x18001325b  jz      short loc_18001326B
0x18001325d  add     rcx, 2
0x180013261  movzx   r8d, word ptr [rcx]
0x180013265  test    r8w, r8w
0x180013269  jnz     short loc_180013257
0x18001326b  cmp     [rcx], bx
0x18001326e  jz      short loc_180013279
0x180013270  add     rdx, 2
0x180013274  cmp     [rdx], bx
0x180013277  jnz     short loc_180013247
0x180013279  mov     r9, rdx
0x18001327c  mov     r11, rdx
0x18001327f  cmp     [rdx], bx
0x180013282  jz      short loc_1800132C2
0x180013284  lea     rcx, asc_18001D1B4; "\\"
0x18001328b  test    ax, ax
0x18001328e  jz      short loc_1800132A8
0x180013290  movzx   r8d, ax
0x180013294  cmp     r8w, [rdx]
0x180013298  jz      short loc_1800132A8
0x18001329a  add     rcx, 2
0x18001329e  movzx   r8d, word ptr [rcx]
0x1800132a2  test    r8w, r8w
0x1800132a6  jnz     short loc_180013294
0x1800132a8  lea     r8, [rdx+2]
0x1800132ac  cmp     [rcx], bx
0x1800132af  jnz     short loc_1800132BC
0x1800132b1  mov     rdx, r8
0x1800132b4  cmp     [r8], bx
0x1800132b8  jnz     short loc_180013284
0x1800132ba  jmp     short loc_1800132C2
0x1800132bc  mov     [rdx], bx
0x1800132bf  mov     rdx, r8
0x1800132c2  cmp     rdx, r11
0x1800132c5  mov     [r10], rdx
0x1800132c8  cmovz   r9, rbx
0x1800132cc  mov     rax, r9
0x1800132cf  jmp     short loc_1800132D3
0x1800132d1  xor     eax, eax
0x1800132d3  mov     rbx, [rsp+arg_0]
0x1800132d8  retn
```
