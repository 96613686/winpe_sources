# ValidateMultiSzA

- ea: `0x180002d10`
- end: `0x180002dce`
- name: `ValidateMultiSzA`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a50`

## callees

- `0x180002d10`

## pseudocode

```c
__int64 __fastcall ValidateMultiSzA(_BYTE *a1, unsigned __int64 a2, _DWORD *a3)
{
  unsigned int v3; // r9d
  bool v6; // cc
  unsigned __int64 v7; // rax
  _BYTE *v8; // r11
  unsigned __int64 v9; // r8

  v3 = 0;
  *a3 = 0;
  if ( a2 || a1 )
  {
    if ( a1 )
    {
      if ( !a2 )
        goto LABEL_5;
    }
    else if ( a2 )
    {
      goto LABEL_5;
    }
    v6 = a2 <= 1;
    if ( a2 != 1 )
      goto LABEL_22;
    if ( !*a1 )
    {
      while ( 1 )
      {
        v6 = a2 <= 1;
LABEL_22:
        if ( v6 )
          break;
        if ( !a1 )
          goto LABEL_25;
        v7 = a2 - 1;
        if ( a2 - 1 > 0x7FFFFFFF )
          goto LABEL_25;
        v8 = a1;
        if ( a2 == 1 )
        {
LABEL_17:
          v9 = 0;
        }
        else
        {
          while ( *v8 )
          {
            ++v8;
            if ( !--v7 )
              goto LABEL_17;
          }
          v9 = a2 - 1 - v7;
        }
        if ( !v7 )
        {
LABEL_25:
          v3 = 87;
          break;
        }
        a1 += v9 + 1;
        a2 += -1LL - v9;
        if ( v9 )
          ++*a3;
      }
      if ( a2 == 1 && !*a1 )
      {
        if ( !v3 )
          return v3;
        goto LABEL_6;
      }
    }
LABEL_5:
    v3 = 87;
LABEL_6:
    *a3 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180002d10  xor     r9d, r9d
0x180002d13  mov     r10, r8
0x180002d16  mov     [r8], r9d
0x180002d19  test    rdx, rdx
0x180002d1c  jnz     short loc_180002D23
0x180002d1e  test    rcx, rcx
0x180002d21  jz      short loc_180002D3A
0x180002d23  test    rcx, rcx
0x180002d26  jz      short loc_180002D3E
0x180002d28  test    rdx, rdx
0x180002d2b  jnz     short loc_180002D43
0x180002d2d  mov     r9d, 57h ; 'W'
0x180002d33  mov     dword ptr [r10], 0
0x180002d3a  mov     eax, r9d
0x180002d3d  retn
0x180002d3e  test    rdx, rdx
0x180002d41  jnz     short loc_180002D2D
0x180002d43  cmp     rdx, 1
0x180002d47  jnz     short loc_180002D9E
0x180002d49  cmp     [rcx], r9b
0x180002d4c  jnz     short loc_180002D2D
0x180002d4e  jmp     short loc_180002D9A
0x180002d50  test    rcx, rcx
0x180002d53  jz      short loc_180002DA7
0x180002d55  lea     rax, [rdx-1]
0x180002d59  cmp     rax, 7FFFFFFFh
0x180002d5f  ja      short loc_180002DA7
0x180002d61  mov     r11, rcx
0x180002d64  mov     r8, rax
0x180002d67  test    rax, rax
0x180002d6a  jz      short loc_180002D7A
0x180002d6c  cmp     [r11], r9b
0x180002d6f  jz      short loc_180002DA2
0x180002d71  inc     r11
0x180002d74  sub     rax, 1
0x180002d78  jnz     short loc_180002D6C
0x180002d7a  xor     r8d, r8d
0x180002d7d  test    rax, rax
0x180002d80  jz      short loc_180002DA7
0x180002d82  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002d86  inc     rcx
0x180002d89  sub     rax, r8
0x180002d8c  add     rcx, r8
0x180002d8f  add     rdx, rax
0x180002d92  test    r8, r8
0x180002d95  jz      short loc_180002D9A
0x180002d97  inc     dword ptr [r10]
0x180002d9a  cmp     rdx, 1
0x180002d9e  ja      short loc_180002D50
0x180002da0  jmp     short loc_180002DAD
0x180002da2  sub     r8, rax
0x180002da5  jmp     short loc_180002D7D
0x180002da7  mov     r9d, 57h ; 'W'
0x180002dad  cmp     rdx, 1
0x180002db1  jnz     loc_180002D2D
0x180002db7  cmp     byte ptr [rcx], 0
0x180002dba  jnz     loc_180002D2D
0x180002dc0  test    r9d, r9d
0x180002dc3  jz      loc_180002D3A
0x180002dc9  jmp     loc_180002D33
```
