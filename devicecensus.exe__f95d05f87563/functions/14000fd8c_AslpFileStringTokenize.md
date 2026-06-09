# AslpFileStringTokenize

- ea: `0x14000fd8c`
- end: `0x14000fe4d`
- name: `AslpFileStringTokenize`
- size: `193`
- prototype: `_WORD *__fastcall(_WORD *, __int64, _WORD **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fee8`

## callees

- `0x14000fd8c`

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
    if ( Source[0] )
    {
      v6 = Source[0];
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
      if ( Source[0] )
      {
        v10 = Source[0];
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
0x14000fd8c  mov     [rsp+arg_0], rbx
0x14000fd91  xor     ebx, ebx
0x14000fd93  mov     r10, r8
0x14000fd96  mov     rdx, rcx
0x14000fd99  test    r8, r8
0x14000fd9c  jz      loc_14000FE45
0x14000fda2  test    rcx, rcx
0x14000fda5  jnz     short loc_14000FDB3
0x14000fda7  mov     rdx, [r8]
0x14000fdaa  test    rdx, rdx
0x14000fdad  jz      loc_14000FE45
0x14000fdb3  mov     eax, dword ptr cs:Source; "\\"
0x14000fdb9  jmp     short loc_14000FDE8
0x14000fdbb  lea     rcx, Source; "\\"
0x14000fdc2  test    ax, ax
0x14000fdc5  jz      short loc_14000FDDF
0x14000fdc7  movzx   r8d, ax
0x14000fdcb  cmp     r8w, [rdx]
0x14000fdcf  jz      short loc_14000FDDF
0x14000fdd1  add     rcx, 2
0x14000fdd5  movzx   r8d, word ptr [rcx]
0x14000fdd9  test    r8w, r8w
0x14000fddd  jnz     short loc_14000FDCB
0x14000fddf  cmp     [rcx], bx
0x14000fde2  jz      short loc_14000FDED
0x14000fde4  add     rdx, 2
0x14000fde8  cmp     [rdx], bx
0x14000fdeb  jnz     short loc_14000FDBB
0x14000fded  mov     r9, rdx
0x14000fdf0  mov     r11, rdx
0x14000fdf3  cmp     [rdx], bx
0x14000fdf6  jz      short loc_14000FE36
0x14000fdf8  lea     rcx, Source; "\\"
0x14000fdff  test    ax, ax
0x14000fe02  jz      short loc_14000FE1C
0x14000fe04  movzx   r8d, ax
0x14000fe08  cmp     r8w, [rdx]
0x14000fe0c  jz      short loc_14000FE1C
0x14000fe0e  add     rcx, 2
0x14000fe12  movzx   r8d, word ptr [rcx]
0x14000fe16  test    r8w, r8w
0x14000fe1a  jnz     short loc_14000FE08
0x14000fe1c  lea     r8, [rdx+2]
0x14000fe20  cmp     [rcx], bx
0x14000fe23  jnz     short loc_14000FE30
0x14000fe25  mov     rdx, r8
0x14000fe28  cmp     [r8], bx
0x14000fe2c  jnz     short loc_14000FDF8
0x14000fe2e  jmp     short loc_14000FE36
0x14000fe30  mov     [rdx], bx
0x14000fe33  mov     rdx, r8
0x14000fe36  cmp     rdx, r11
0x14000fe39  mov     [r10], rdx
0x14000fe3c  cmovz   r9, rbx
0x14000fe40  mov     rax, r9
0x14000fe43  jmp     short loc_14000FE47
0x14000fe45  xor     eax, eax
0x14000fe47  mov     rbx, [rsp+arg_0]
0x14000fe4c  retn
```
