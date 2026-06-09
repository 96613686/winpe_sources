# DetermineFileType(uchar const *,uint)

- ea: `0x180003ab0`
- end: `0x180003b99`
- name: `?DetermineFileType@@YA?AW4FileType@@PEBEI@Z`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fe4`
- `0x180004834`

## callees

- `0x180002d64`
- `0x180003ab0`

## pseudocode

```c
__int64 __fastcall DetermineFileType(__int64 a1, signed int a2)
{
  unsigned int v2; // ebx
  int v5; // edx
  __int64 v6; // r9
  char v7; // r10
  char v8; // r8
  char v9; // cl
  int v10; // eax
  bool v11; // sf
  int v12; // ecx
  int v14; // [rsp+38h] [rbp+10h] BYREF

  v2 = 1;
  if ( (unsigned int)a2 > 1 )
  {
    switch ( *(_WORD *)a1 )
    {
      case 0xBBEF:
        if ( (unsigned int)a2 > 2 )
        {
          v12 = 1;
          if ( *(_BYTE *)(a1 + 2) == 0xBF )
            return 4;
          return (unsigned int)v12;
        }
        break;
      case 0xFEFF:
        return 2;
      case 0xFFFE:
        return 3;
      default:
        v14 = 6109;
        if ( RtlIsTextUnicode(a1, a2, &v14) )
        {
          return 2;
        }
        else
        {
          v5 = 0;
          v6 = 0;
          v7 = 1;
          if ( a2 > 0 )
          {
            do
            {
              v8 = *(_BYTE *)(v6 + a1);
              v9 = 0;
              if ( v8 >= 0 )
                v9 = v7;
              v7 = v9;
              if ( v5 )
              {
                if ( (v8 & 0xC0) != 0x80 )
                  return v2;
                --v5;
              }
              else if ( (unsigned __int8)v8 >= 0x80u )
              {
                do
                {
                  v10 = v5++;
                  v11 = (v8 & 0x40) != 0;
                  v8 *= 2;
                }
                while ( v11 );
                v5 = v10;
                if ( !v10 )
                  return v2;
              }
              v6 = (unsigned int)(v6 + 1);
            }
            while ( (int)v6 < a2 );
            if ( !v5 && !v9 )
              return 4;
          }
        }
        break;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003ab0  mov     [rsp+arg_0], rbx
0x180003ab5  mov     [rsp+arg_10], rsi
0x180003aba  push    rdi
0x180003abb  sub     rsp, 20h
0x180003abf  mov     ebx, 1
0x180003ac4  mov     edi, edx
0x180003ac6  mov     rsi, rcx
0x180003ac9  cmp     edx, ebx
0x180003acb  jbe     loc_180003B87
0x180003ad1  mov     eax, 0BBEFh
0x180003ad6  cmp     [rcx], ax
0x180003ad9  jz      loc_180003B72
0x180003adf  mov     eax, 0FEFFh
0x180003ae4  cmp     [rcx], ax
0x180003ae7  jz      short loc_180003B09
0x180003ae9  mov     eax, 0FFFEh
0x180003aee  cmp     [rcx], ax
0x180003af1  jz      short loc_180003B6B
0x180003af3  lea     r8, [rsp+28h+arg_8]
0x180003af8  mov     [rsp+28h+arg_8], 17DDh
0x180003b00  call    RtlIsTextUnicode
0x180003b05  test    al, al
0x180003b07  jz      short loc_180003B10
0x180003b09  mov     ebx, 2
0x180003b0e  jmp     short loc_180003B87
0x180003b10  xor     edx, edx
0x180003b12  xor     r9d, r9d
0x180003b15  mov     r10b, bl
0x180003b18  test    edi, edi
0x180003b1a  jle     short loc_180003B87
0x180003b1c  mov     r8b, [r9+rsi]
0x180003b20  xor     ecx, ecx
0x180003b22  test    r8b, r8b
0x180003b25  movzx   eax, r10b
0x180003b29  cmovns  ecx, eax
0x180003b2c  mov     r10b, cl
0x180003b2f  test    edx, edx
0x180003b31  jnz     short loc_180003B4A
0x180003b33  cmp     r8b, 80h
0x180003b37  jb      short loc_180003B56
0x180003b39  mov     eax, edx
0x180003b3b  add     edx, ebx
0x180003b3d  add     r8b, r8b
0x180003b40  js      short loc_180003B39
0x180003b42  mov     edx, eax
0x180003b44  test    eax, eax
0x180003b46  jz      short loc_180003B87
0x180003b48  jmp     short loc_180003B56
0x180003b4a  and     r8b, 0C0h
0x180003b4e  cmp     r8b, 80h
0x180003b52  jnz     short loc_180003B87
0x180003b54  dec     edx
0x180003b56  add     r9d, ebx
0x180003b59  cmp     r9d, edi
0x180003b5c  jl      short loc_180003B1C
0x180003b5e  test    edx, edx
0x180003b60  jnz     short loc_180003B87
0x180003b62  test    cl, cl
0x180003b64  jnz     short loc_180003B87
0x180003b66  lea     ebx, [rdx+4]
0x180003b69  jmp     short loc_180003B87
0x180003b6b  mov     ebx, 3
0x180003b70  jmp     short loc_180003B87
0x180003b72  cmp     edi, 2
0x180003b75  jbe     short loc_180003B87
0x180003b77  cmp     byte ptr [rsi+2], 0BFh
0x180003b7b  mov     ecx, ebx
0x180003b7d  mov     ebx, 4
0x180003b82  cmovz   ecx, ebx
0x180003b85  mov     ebx, ecx
0x180003b87  mov     rsi, [rsp+28h+arg_10]
0x180003b8c  mov     eax, ebx
0x180003b8e  mov     rbx, [rsp+28h+arg_0]
0x180003b93  add     rsp, 20h
0x180003b97  pop     rdi
0x180003b98  retn
```
