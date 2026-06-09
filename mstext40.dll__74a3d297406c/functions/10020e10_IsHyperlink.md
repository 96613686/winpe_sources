# IsHyperlink

- ea: `0x10020e10`
- end: `0x10020f13`
- name: `IsHyperlink`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10022160`

## callees

- `0x10020e10`
- `0x1002ccad`

## pseudocode

```c
int __stdcall IsHyperlink(unsigned __int16 *a1)
{
  BOOL v1; // esi
  int v2; // ebp
  int v3; // edi
  int v4; // ecx

  v1 = 0;
  v2 = 0;
  while ( v2 != 8 && v2 != 7 )
  {
    v3 = *a1++;
    if ( (_WORD)v3 )
    {
      if ( toupper(v3) != 70 || v1 )
      {
        if ( toupper(v3) != 72 || v1 )
        {
          if ( toupper(v3) != 84 || v1 )
          {
            if ( toupper(v3) != 80 || v1 )
            {
              if ( toupper(v3) != 58 || v1 )
              {
                if ( v3 != 35 || v1 )
                {
                  v4 = 6;
                  if ( v3 == 34 || v3 == 39 )
                    v1 = !v1;
                }
                else
                {
                  v4 = 0;
                }
              }
              else
              {
                v4 = 5;
              }
            }
            else
            {
              v4 = 4;
            }
          }
          else
          {
            v4 = 3;
          }
        }
        else
        {
          v4 = 2;
        }
      }
      else
      {
        v4 = 1;
      }
    }
    else
    {
      v4 = 7;
    }
    v2 = dword_1003EAF8[8 * v2 + v4];
    if ( v2 == 6 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x10020e10  push    ebx
0x10020e11  push    ebp
0x10020e12  push    esi
0x10020e13  xor     esi, esi
0x10020e15  xor     ebp, ebp
0x10020e17  push    edi
0x10020e18  jmp     short loc_10020E20
0x10020e20  cmp     ebp, 8
0x10020e23  jz      loc_10020F0A
0x10020e29  cmp     ebp, 7
0x10020e2c  jz      loc_10020F0A
0x10020e32  mov     eax, [esp+10h+arg_0]
0x10020e36  movzx   edi, word ptr [eax]
0x10020e39  add     eax, 2
0x10020e3c  mov     [esp+10h+arg_0], eax
0x10020e40  test    di, di
0x10020e43  jnz     short loc_10020E4F
0x10020e45  mov     ecx, 7
0x10020e4a  jmp     loc_10020EED
0x10020e4f  mov     ebx, edi
0x10020e51  push    ebx; C
0x10020e52  call    _toupper
0x10020e57  add     esp, 4
0x10020e5a  cmp     eax, 46h ; 'F'
0x10020e5d  jnz     short loc_10020E6B
0x10020e5f  test    esi, esi
0x10020e61  jnz     short loc_10020E6B
0x10020e63  lea     ecx, [eax-45h]
0x10020e66  jmp     loc_10020EED
0x10020e6b  push    ebx; C
0x10020e6c  call    _toupper
0x10020e71  add     esp, 4
0x10020e74  cmp     eax, 48h ; 'H'
0x10020e77  jnz     short loc_10020E82
0x10020e79  test    esi, esi
0x10020e7b  jnz     short loc_10020E82
0x10020e7d  lea     ecx, [eax-46h]
0x10020e80  jmp     short loc_10020EED
0x10020e82  push    ebx; C
0x10020e83  call    _toupper
0x10020e88  add     esp, 4
0x10020e8b  cmp     eax, 54h ; 'T'
0x10020e8e  jnz     short loc_10020E99
0x10020e90  test    esi, esi
0x10020e92  jnz     short loc_10020E99
0x10020e94  lea     ecx, [eax-51h]
0x10020e97  jmp     short loc_10020EED
0x10020e99  push    ebx; C
0x10020e9a  call    _toupper
0x10020e9f  add     esp, 4
0x10020ea2  cmp     eax, 50h ; 'P'
0x10020ea5  jnz     short loc_10020EB0
0x10020ea7  test    esi, esi
0x10020ea9  jnz     short loc_10020EB0
0x10020eab  lea     ecx, [eax-4Ch]
0x10020eae  jmp     short loc_10020EED
0x10020eb0  push    ebx; C
0x10020eb1  call    _toupper
0x10020eb6  add     esp, 4
0x10020eb9  cmp     eax, 3Ah ; ':'
0x10020ebc  jnz     short loc_10020EC7
0x10020ebe  test    esi, esi
0x10020ec0  jnz     short loc_10020EC7
0x10020ec2  lea     ecx, [eax-35h]
0x10020ec5  jmp     short loc_10020EED
0x10020ec7  cmp     edi, 23h ; '#'
0x10020eca  jnz     short loc_10020ED4
0x10020ecc  test    esi, esi
0x10020ece  jnz     short loc_10020ED4
0x10020ed0  xor     ecx, ecx
0x10020ed2  jmp     short loc_10020EED
0x10020ed4  mov     ecx, 6
0x10020ed9  cmp     edi, 22h ; '"'
0x10020edc  jz      short loc_10020EE3
0x10020ede  cmp     edi, 27h ; '''
0x10020ee1  jnz     short loc_10020EED
0x10020ee3  xor     eax, eax
0x10020ee5  cmp     esi, 1
0x10020ee8  setnz   al
0x10020eeb  mov     esi, eax
0x10020eed  lea     eax, [ecx+ebp*8]
0x10020ef0  mov     ebp, dword_1003EAF8[eax*4]
0x10020ef7  cmp     ebp, 6
0x10020efa  jnz     loc_10020E20
0x10020f00  pop     edi
0x10020f01  pop     esi
0x10020f02  lea     eax, [ebp-5]
0x10020f05  pop     ebp
0x10020f06  pop     ebx
0x10020f07  retn    4
0x10020f0a  pop     edi
0x10020f0b  pop     esi
0x10020f0c  pop     ebp
0x10020f0d  xor     eax, eax
0x10020f0f  pop     ebx
0x10020f10  retn    4
```
