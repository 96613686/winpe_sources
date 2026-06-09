# GetCommonToken

- ea: `0x10030e30`
- end: `0x10030f89`
- name: `GetCommonToken`
- size: `345`
- prototype: `int __fastcall(__int16, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10030f8f`

## callees

- `0x10030d60`
- `0x10030e30`

## pseudocode

```c
int __fastcall GetCommonToken(__int16 a1, unsigned __int16 *a2)
{
  int v3; // edx
  unsigned __int16 Char; // ax
  __int16 v6; // ax
  _WORD *v7; // edi
  __int16 v8; // ax
  int v9; // eax
  unsigned __int16 v10; // ax
  unsigned __int16 v11; // ax
  unsigned __int16 v12; // ax
  int v13; // [esp-4h] [ebp-10h]

  v3 = 0;
  switch ( a1 )
  {
    case '\\':
      Char = GetChar(0);
      if ( Char )
      {
        v13 = 2;
LABEL_12:
        *a2 = Char;
        v3 = v13;
        a2[1] = 0;
        return v3;
      }
      return -102;
    case '*':
      Char = GetChar(0);
      if ( Char )
      {
        v13 = 4;
        goto LABEL_12;
      }
      return -103;
    case '_':
      Char = GetChar(0);
      if ( Char )
      {
        v13 = 6;
        goto LABEL_12;
      }
      return -102;
    case '"':
      while ( 1 )
      {
        v6 = GetChar(0);
        if ( !v6 )
          break;
        if ( v6 == 34 )
          return 1;
      }
      return -102;
    case '[':
      v7 = a2;
      *a2 = 0;
      while ( 1 )
      {
        v8 = GetChar(1);
        if ( !v8 )
          return -102;
        if ( v8 == 93 )
          break;
        *v7++ = v8;
      }
      v3 = 5;
      *v7 = 0;
      v9 = *a2;
      switch ( (_WORD)v9 )
      {
        case 'h':
          v10 = a2[1];
          if ( v10 && (v10 != 104 || a2[2]) )
            return v3;
          return 27;
        case 'm':
          v11 = a2[1];
          if ( v11 && (v11 != 109 || a2[2]) )
            return v3;
          return 28;
        case 's':
          v12 = a2[1];
          if ( v12 && (v12 != 115 || a2[2]) )
            return v3;
          return 29;
        default:
          if ( v9 != 60 && v9 != 62 && v9 != 61 )
            return v3;
          return 7;
      }
  }
  return v3;
}

```

## disassembly

```asm
0x10030e30  mov     edi, edi
0x10030e32  push    ebx
0x10030e33  push    esi
0x10030e34  xor     ebx, ebx
0x10030e36  mov     esi, edx
0x10030e38  mov     edx, ebx
0x10030e3a  push    edi
0x10030e3b  cmp     cx, 5Ch ; '\'
0x10030e3f  jnz     short loc_10030E58
0x10030e41  xor     ecx, ecx
0x10030e43  call    GetChar
0x10030e48  movzx   eax, ax
0x10030e4b  test    ax, ax
0x10030e4e  jz      loc_10030EE9
0x10030e54  push    2
0x10030e56  jmp     short loc_10030E8D
0x10030e58  cmp     cx, 2Ah ; '*'
0x10030e5c  jnz     short loc_10030E76
0x10030e5e  xor     ecx, ecx
0x10030e60  call    GetChar
0x10030e65  movzx   eax, ax
0x10030e68  test    ax, ax
0x10030e6b  jnz     short loc_10030E72
0x10030e6d  push    0FFFFFF99h
0x10030e6f  pop     eax
0x10030e70  jmp     short loc_10030E99
0x10030e72  push    4
0x10030e74  jmp     short loc_10030E8D
0x10030e76  cmp     cx, 5Fh ; '_'
0x10030e7a  jnz     short loc_10030E9D
0x10030e7c  xor     ecx, ecx
0x10030e7e  call    GetChar
0x10030e83  movzx   eax, ax
0x10030e86  test    ax, ax
0x10030e89  jz      short loc_10030EE9
0x10030e8b  push    6
0x10030e8d  mov     [esi], ax
0x10030e90  xor     eax, eax
0x10030e92  pop     edx
0x10030e93  mov     [esi+2], ax
0x10030e97  mov     eax, edx
0x10030e99  pop     edi
0x10030e9a  pop     esi
0x10030e9b  pop     ebx
0x10030e9c  retn
0x10030e9d  push    22h ; '"'
0x10030e9f  pop     edi
0x10030ea0  cmp     cx, di
0x10030ea3  jnz     short loc_10030EBE
0x10030ea5  xor     ecx, ecx
0x10030ea7  call    GetChar
0x10030eac  movzx   eax, ax
0x10030eaf  test    ax, ax
0x10030eb2  jz      short loc_10030EE9
0x10030eb4  cmp     ax, di
0x10030eb7  jnz     short loc_10030EA5
0x10030eb9  xor     edx, edx
0x10030ebb  inc     edx
0x10030ebc  jmp     short loc_10030E97
0x10030ebe  cmp     cx, 5Bh ; '['
0x10030ec2  jnz     short loc_10030E97
0x10030ec4  xor     eax, eax
0x10030ec6  mov     edi, esi
0x10030ec8  mov     [esi], ax
0x10030ecb  jmp     short loc_10030ED9
0x10030ecd  cmp     ax, 5Dh ; ']'
0x10030ed1  jz      short loc_10030EED
0x10030ed3  mov     [edi], ax
0x10030ed6  add     edi, 2
0x10030ed9  xor     ecx, ecx
0x10030edb  inc     ecx
0x10030edc  call    GetChar
0x10030ee1  movzx   eax, ax
0x10030ee4  test    ax, ax
0x10030ee7  jnz     short loc_10030ECD
0x10030ee9  push    0FFFFFF9Ah
0x10030eeb  jmp     short loc_10030E6F
0x10030eed  push    5
0x10030eef  xor     eax, eax
0x10030ef1  pop     edx
0x10030ef2  mov     [edi], ax
0x10030ef5  movzx   eax, word ptr [esi]
0x10030ef8  push    68h ; 'h'
0x10030efa  pop     edi
0x10030efb  cmp     ax, di
0x10030efe  jnz     short loc_10030F1A
0x10030f00  movzx   eax, word ptr [esi+2]
0x10030f04  mov     ecx, eax
0x10030f06  test    ax, ax
0x10030f09  jz      short loc_10030F16
0x10030f0b  cmp     cx, di
0x10030f0e  jnz     short loc_10030E97
0x10030f10  cmp     [esi+4], bx
0x10030f14  jnz     short loc_10030E97
0x10030f16  push    1Bh
0x10030f18  jmp     short loc_10030F6C
0x10030f1a  push    6Dh ; 'm'
0x10030f1c  pop     edi
0x10030f1d  cmp     ax, di
0x10030f20  jnz     short loc_10030F44
0x10030f22  movzx   eax, word ptr [esi+2]
0x10030f26  mov     ecx, eax
0x10030f28  test    ax, ax
0x10030f2b  jz      short loc_10030F40
0x10030f2d  cmp     cx, di
0x10030f30  jnz     loc_10030E97
0x10030f36  cmp     [esi+4], bx
0x10030f3a  jnz     loc_10030E97
0x10030f40  push    1Ch
0x10030f42  jmp     short loc_10030F6C
0x10030f44  push    73h ; 's'
0x10030f46  pop     edi
0x10030f47  cmp     ax, di
0x10030f4a  jnz     short loc_10030F72
0x10030f4c  movzx   eax, word ptr [esi+2]
0x10030f50  mov     ecx, eax
0x10030f52  test    ax, ax
0x10030f55  jz      short loc_10030F6A
0x10030f57  cmp     cx, di
0x10030f5a  jnz     loc_10030E97
0x10030f60  cmp     [esi+4], bx
0x10030f64  jnz     loc_10030E97
0x10030f6a  push    1Dh
0x10030f6c  pop     edx
0x10030f6d  jmp     loc_10030E97
0x10030f72  cmp     eax, 3Ch ; '<'
0x10030f75  jz      short loc_10030F85
0x10030f77  cmp     eax, 3Eh ; '>'
0x10030f7a  jz      short loc_10030F85
0x10030f7c  cmp     eax, 3Dh ; '='
0x10030f7f  jnz     loc_10030E97
0x10030f85  push    7
0x10030f87  jmp     short loc_10030F6C
```
