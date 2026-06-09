# ValidateMultiSzA

- ea: `0x180002ea0`
- end: `0x180002f5f`
- name: `ValidateMultiSzA`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a60`

## callees

- `0x180002ea0`

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
0x180002ea0  xor     r9d, r9d
0x180002ea3  mov     r10, r8
0x180002ea6  mov     [r8], r9d
0x180002ea9  test    rdx, rdx
0x180002eac  jnz     short loc_180002EB3
0x180002eae  test    rcx, rcx
0x180002eb1  jz      short loc_180002ECA
0x180002eb3  test    rcx, rcx
0x180002eb6  jz      short loc_180002ECF
0x180002eb8  test    rdx, rdx
0x180002ebb  jnz     short loc_180002ED4
0x180002ebd  mov     r9d, 57h ; 'W'
0x180002ec3  mov     dword ptr [r10], 0
0x180002eca  mov     eax, r9d
0x180002ecd  retn
0x180002ecf  test    rdx, rdx
0x180002ed2  jnz     short loc_180002EBD
0x180002ed4  cmp     rdx, 1
0x180002ed8  jnz     short loc_180002F2F
0x180002eda  cmp     [rcx], r9b
0x180002edd  jnz     short loc_180002EBD
0x180002edf  jmp     short loc_180002F2B
0x180002ee1  test    rcx, rcx
0x180002ee4  jz      short loc_180002F38
0x180002ee6  lea     rax, [rdx-1]
0x180002eea  cmp     rax, 7FFFFFFFh
0x180002ef0  ja      short loc_180002F38
0x180002ef2  mov     r11, rcx
0x180002ef5  mov     r8, rax
0x180002ef8  test    rax, rax
0x180002efb  jz      short loc_180002F0B
0x180002efd  cmp     [r11], r9b
0x180002f00  jz      short loc_180002F33
0x180002f02  inc     r11
0x180002f05  sub     rax, 1
0x180002f09  jnz     short loc_180002EFD
0x180002f0b  xor     r8d, r8d
0x180002f0e  test    rax, rax
0x180002f11  jz      short loc_180002F38
0x180002f13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002f17  inc     rcx
0x180002f1a  sub     rax, r8
0x180002f1d  add     rcx, r8
0x180002f20  add     rdx, rax
0x180002f23  test    r8, r8
0x180002f26  jz      short loc_180002F2B
0x180002f28  inc     dword ptr [r10]
0x180002f2b  cmp     rdx, 1
0x180002f2f  ja      short loc_180002EE1
0x180002f31  jmp     short loc_180002F3E
0x180002f33  sub     r8, rax
0x180002f36  jmp     short loc_180002F0E
0x180002f38  mov     r9d, 57h ; 'W'
0x180002f3e  cmp     rdx, 1
0x180002f42  jnz     loc_180002EBD
0x180002f48  cmp     byte ptr [rcx], 0
0x180002f4b  jnz     loc_180002EBD
0x180002f51  test    r9d, r9d
0x180002f54  jz      loc_180002ECA
0x180002f5a  jmp     loc_180002EC3
```
