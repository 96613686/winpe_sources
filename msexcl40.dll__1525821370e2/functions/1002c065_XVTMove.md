# XVTMove

- ea: `0x1002c065`
- end: `0x1002c133`
- name: `XVTMove`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1002c140`

## callees

- `0x1002c065`

## pseudocode

```c
int __fastcall XVTMove(int a1, _DWORD **a2, int a3, int a4)
{
  int v4; // edi
  _DWORD *v5; // esi
  int v6; // esi
  _DWORD *v7; // eax
  _DWORD *v8; // eax

  if ( !a3 )
  {
    v8 = (_DWORD *)*a2[1];
    if ( !v8 )
      goto LABEL_34;
    goto LABEL_25;
  }
  if ( a3 != 1 )
  {
    if ( a3 == 2 )
    {
      v8 = *a2;
    }
    else
    {
      if ( a3 != 3 )
      {
        if ( a3 != 4 )
        {
          if ( a3 == 5 )
          {
            v4 = 0;
            if ( -a4 >= 0 && a4 != 0 )
            {
              while ( 1 )
              {
                v5 = *a2;
                if ( a2[1] == *a2 )
                  goto LABEL_28;
                while ( v5 )
                {
                  if ( (_DWORD *)*v5 == a2[1] )
                  {
                    a2[1] = v5;
                    *(_BYTE *)(a1 + 36) = 2;
                    break;
                  }
                  v5 = (_DWORD *)*v5;
                }
                if ( ++v4 >= -a4 )
                  return 0;
              }
            }
          }
          return 0;
        }
        v6 = 0;
        if ( a4 <= 0 )
          return 0;
        while ( 1 )
        {
          v7 = (_DWORD *)*a2[1];
          if ( !v7 )
            break;
          ++v6;
          a2[1] = v7;
          *(_BYTE *)(a1 + 36) = 2;
          if ( v6 >= a4 )
            return 0;
        }
LABEL_34:
        *(_BYTE *)(a1 + 36) = 1;
        return 0;
      }
      v8 = *a2;
      if ( !*a2 )
        return 0;
      while ( *v8 )
        v8 = (_DWORD *)*v8;
    }
LABEL_25:
    a2[1] = v8;
    *(_BYTE *)(a1 + 36) = 2;
    return 0;
  }
  v8 = *a2;
  if ( a2[1] == *a2 )
  {
LABEL_28:
    *(_BYTE *)(a1 + 36) = 0;
    return 0;
  }
  while ( v8 )
  {
    if ( (_DWORD *)*v8 == a2[1] )
      goto LABEL_25;
    v8 = (_DWORD *)*v8;
  }
  return 0;
}

```

## disassembly

```asm
0x1002c065  mov     edi, edi
0x1002c067  push    ebp
0x1002c068  mov     ebp, esp
0x1002c06a  mov     eax, [ebp+arg_0]
0x1002c06d  push    ebx
0x1002c06e  push    esi
0x1002c06f  push    edi
0x1002c070  sub     eax, 0
0x1002c073  jz      loc_1002C124
0x1002c079  sub     eax, 1
0x1002c07c  jz      loc_1002C108
0x1002c082  sub     eax, 1
0x1002c085  jz      short loc_1002C0F6
0x1002c087  sub     eax, 1
0x1002c08a  jz      short loc_1002C0E6
0x1002c08c  sub     eax, 1
0x1002c08f  jz      short loc_1002C0C7
0x1002c091  sub     eax, 1
0x1002c094  jnz     short loc_1002C0FF
0x1002c096  mov     eax, [ebp+arg_4]
0x1002c099  xor     edi, edi
0x1002c09b  neg     eax
0x1002c09d  test    eax, eax
0x1002c09f  jle     short loc_1002C0FF
0x1002c0a1  mov     esi, [edx]
0x1002c0a3  cmp     [edx+4], esi
0x1002c0a6  jz      short loc_1002C10F
0x1002c0a8  jmp     short loc_1002C0B3
0x1002c0aa  mov     ebx, [esi]
0x1002c0ac  cmp     ebx, [edx+4]
0x1002c0af  jz      short loc_1002C0B9
0x1002c0b1  mov     esi, ebx
0x1002c0b3  test    esi, esi
0x1002c0b5  jnz     short loc_1002C0AA
0x1002c0b7  jmp     short loc_1002C0C0
0x1002c0b9  mov     [edx+4], esi
0x1002c0bc  mov     byte ptr [ecx+24h], 2
0x1002c0c0  inc     edi
0x1002c0c1  cmp     edi, eax
0x1002c0c3  jl      short loc_1002C0A1
0x1002c0c5  jmp     short loc_1002C0FF
0x1002c0c7  xor     esi, esi
0x1002c0c9  cmp     [ebp+arg_4], esi
0x1002c0cc  jle     short loc_1002C0FF
0x1002c0ce  mov     eax, [edx+4]
0x1002c0d1  mov     eax, [eax]
0x1002c0d3  test    eax, eax
0x1002c0d5  jz      short loc_1002C12D
0x1002c0d7  inc     esi
0x1002c0d8  mov     [edx+4], eax
0x1002c0db  mov     byte ptr [ecx+24h], 2
0x1002c0df  cmp     esi, [ebp+arg_4]
0x1002c0e2  jl      short loc_1002C0CE
0x1002c0e4  jmp     short loc_1002C0FF
0x1002c0e6  mov     eax, [edx]
0x1002c0e8  test    eax, eax
0x1002c0ea  jz      short loc_1002C0FF
0x1002c0ec  mov     esi, [eax]
0x1002c0ee  test    esi, esi
0x1002c0f0  jz      short loc_1002C0F8
0x1002c0f2  mov     eax, esi
0x1002c0f4  jmp     short loc_1002C0EC
0x1002c0f6  mov     eax, [edx]
0x1002c0f8  mov     [edx+4], eax
0x1002c0fb  mov     byte ptr [ecx+24h], 2
0x1002c0ff  pop     edi
0x1002c100  pop     esi
0x1002c101  xor     eax, eax
0x1002c103  pop     ebx
0x1002c104  pop     ebp
0x1002c105  retn    8
0x1002c108  mov     eax, [edx]
0x1002c10a  cmp     [edx+4], eax
0x1002c10d  jnz     short loc_1002C11E
0x1002c10f  mov     byte ptr [ecx+24h], 0
0x1002c113  jmp     short loc_1002C0FF
0x1002c115  mov     esi, [eax]
0x1002c117  cmp     esi, [edx+4]
0x1002c11a  jz      short loc_1002C0F8
0x1002c11c  mov     eax, esi
0x1002c11e  test    eax, eax
0x1002c120  jnz     short loc_1002C115
0x1002c122  jmp     short loc_1002C0FF
0x1002c124  mov     eax, [edx+4]
0x1002c127  mov     eax, [eax]
0x1002c129  test    eax, eax
0x1002c12b  jnz     short loc_1002C0F8
0x1002c12d  mov     byte ptr [ecx+24h], 1
0x1002c131  jmp     short loc_1002C0FF
```
