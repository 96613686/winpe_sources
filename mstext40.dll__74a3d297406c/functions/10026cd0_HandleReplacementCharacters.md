# HandleReplacementCharacters

- ea: `0x10026cd0`
- end: `0x10026e61`
- name: `HandleReplacementCharacters`
- size: `401`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100277a0`
- `0x100279a0`
- `0x10027de0`
- `0x10028100`

## callees

- `0x10026cd0`
- `0x1002d672`

## pseudocode

```c
_WORD *__stdcall HandleReplacementCharacters(_WORD *a1, int a2)
{
  _WORD *result; // eax
  unsigned __int16 *v3; // ecx
  _WORD *v4; // edx
  int v5; // ebp
  int v6; // eax
  _WORD *v7; // esi
  const wchar_t *v8; // ebx
  __int16 v9; // ax
  int v10; // eax
  size_t v11; // ecx
  int v12; // ebp
  int v13; // edi
  int v14; // eax
  wchar_t *v15; // eax
  wchar_t *v16; // edx
  int v18; // ecx
  int v19; // edi
  unsigned __int16 *v20; // ebx
  int v21; // edx
  unsigned int v22; // ecx
  _WORD *v23; // [esp+10h] [ebp-10h]
  int v24; // [esp+18h] [ebp-8h]

  result = a1;
  v3 = a1;
  v4 = a1;
  v23 = a1;
  if ( *a1 )
  {
    v5 = a2;
    while ( 1 )
    {
      if ( !v5 )
        return a1;
      v6 = *v3++;
      if ( v6 != 38 )
        goto LABEL_30;
      v7 = v3;
      v8 = v3;
      v9 = *v3;
      if ( *v3 )
      {
        while ( v9 != 59 )
        {
          v9 = v7[1];
          ++v7;
          if ( !v9 )
            goto LABEL_8;
        }
      }
      else
      {
LABEL_8:
        if ( *v7 != 59 )
        {
          *v4 = 38;
          goto LABEL_31;
        }
      }
      v10 = 333;
      v24 = 333;
      v11 = v7 - v3;
      v12 = 0;
      while ( 1 )
      {
        v13 = (v12 + v10) / 2;
        v14 = wcsncmp(v8, (&off_1003F230)[2 * v13], v11);
        if ( !v14 )
          break;
        v18 = v7 - v8;
        if ( v14 <= 0 )
          goto LABEL_14;
        v10 = v13 - 1;
        v24 = v13 - 1;
LABEL_15:
        if ( v12 > v10 )
        {
          LOWORD(v6) = 0;
          goto LABEL_22;
        }
        v11 = v7 - v8;
      }
      v15 = (&off_1003F230)[2 * v13];
      v16 = v15 + 1;
      while ( *v15++ )
        ;
      v18 = v7 - v8;
      if ( v18 < v15 - v16 )
      {
LABEL_14:
        v10 = v24;
        v12 = v13 + 1;
        goto LABEL_15;
      }
      LOWORD(v6) = word_1003F234[4 * v13];
      if ( (_WORD)v6 )
        goto LABEL_29;
LABEL_22:
      if ( *v8 == 35 )
      {
        v19 = v18 - 1;
        v20 = (unsigned __int16 *)(v8 + 1);
        v21 = 0;
        if ( v18 - 1 > 0 )
        {
          while ( 1 )
          {
            v22 = *v20;
            if ( v22 < 0x30 || v22 > 0x39 )
              break;
            ++v21;
            ++v20;
            LOWORD(v6) = v22 + 2 * (5 * v6 - 24);
            if ( v21 >= v19 )
            {
              if ( (_WORD)v6 )
                goto LABEL_29;
              break;
            }
          }
        }
      }
      LOWORD(v6) = 32;
LABEL_29:
      v4 = v23;
      v3 = v7 + 1;
      v5 = a2;
LABEL_30:
      *v4 = v6;
LABEL_31:
      ++v4;
      --v5;
      v23 = v4;
      a2 = v5;
      if ( !*v3 )
      {
        result = a1;
        break;
      }
    }
  }
  if ( a2 )
    *v4 = 0;
  return result;
}

```

## disassembly

```asm
0x10026cd0  sub     esp, 10h
0x10026cd3  mov     eax, [esp+10h+arg_0]
0x10026cd7  mov     ecx, eax
0x10026cd9  push    ebx
0x10026cda  push    ebp
0x10026cdb  push    esi
0x10026cdc  cmp     word ptr [eax], 0
0x10026ce0  mov     edx, eax
0x10026ce2  push    edi
0x10026ce3  mov     [esp+20h+var_10], edx
0x10026ce7  jz      loc_10026E38
0x10026ced  mov     ebp, [esp+20h+arg_4]
0x10026cf1  mov     edi, 26h ; '&'
0x10026cf6  test    ebp, ebp
0x10026cf8  jz      loc_10026E53
0x10026cfe  movzx   eax, word ptr [ecx]
0x10026d01  add     ecx, 2
0x10026d04  cmp     eax, 26h ; '&'
0x10026d07  jnz     loc_10026E1B
0x10026d0d  mov     esi, ecx
0x10026d0f  mov     ebx, esi
0x10026d11  movzx   eax, word ptr [esi]
0x10026d14  test    ax, ax
0x10026d17  jz      short loc_10026D32
0x10026d19  lea     esp, [esp+0]
0x10026d20  cmp     ax, 3Bh ; ';'
0x10026d24  jz      short loc_10026D3C
0x10026d26  movzx   eax, word ptr [esi+2]
0x10026d2a  add     esi, 2
0x10026d2d  test    ax, ax
0x10026d30  jnz     short loc_10026D20
0x10026d32  cmp     word ptr [esi], 3Bh ; ';'
0x10026d36  jnz     loc_10026E4E
0x10026d3c  mov     ecx, esi
0x10026d3e  mov     eax, 14Dh
0x10026d43  sub     ecx, ebx
0x10026d45  mov     [esp+20h+var_8], eax
0x10026d49  sar     ecx, 1
0x10026d4b  xor     ebp, ebp
0x10026d4d  mov     [esp+20h+var_C], ecx
0x10026d51  mov     [esp+20h+var_4], ebp
0x10026d55  add     eax, ebp
0x10026d57  cdq
0x10026d58  sub     eax, edx
0x10026d5a  mov     edi, eax
0x10026d5c  sar     edi, 1
0x10026d5e  push    ecx; MaxCount
0x10026d5f  push    off_1003F230[edi*8]; String2
0x10026d66  push    ebx; String1
0x10026d67  call    _wcsncmp
0x10026d6c  add     esp, 0Ch
0x10026d6f  test    eax, eax
0x10026d71  jnz     short loc_10026DA8
0x10026d73  mov     eax, off_1003F230[edi*8]; "zwsp"
0x10026d7a  lea     edx, [eax+2]
0x10026d7d  lea     ecx, [ecx+0]
0x10026d80  mov     cx, [eax]
0x10026d83  add     eax, 2
0x10026d86  test    cx, cx
0x10026d89  jnz     short loc_10026D80
0x10026d8b  mov     ecx, [esp+20h+var_C]
0x10026d8f  sub     eax, edx
0x10026d91  sar     eax, 1
0x10026d93  cmp     ecx, eax
0x10026d95  jge     short loc_10026DB7
0x10026d97  mov     eax, [esp+20h+var_8]
0x10026d9b  lea     ebp, [edi+1]
0x10026d9e  cmp     ebp, eax
0x10026da0  jg      short loc_10026DC6
0x10026da2  mov     ecx, [esp+20h+var_C]
0x10026da6  jmp     short loc_10026D55
0x10026da8  mov     ecx, [esp+20h+var_C]
0x10026dac  jle     short loc_10026D97
0x10026dae  lea     eax, [edi-1]
0x10026db1  mov     [esp+20h+var_8], eax
0x10026db5  jmp     short loc_10026D9E
0x10026db7  movzx   eax, word_1003F234[edi*8]
0x10026dbf  test    ax, ax
0x10026dc2  jnz     short loc_10026E0B
0x10026dc4  jmp     short loc_10026DCA
0x10026dc6  mov     eax, [esp+20h+var_4]
0x10026dca  cmp     word ptr [ebx], 23h ; '#'
0x10026dce  jnz     short loc_10026E06
0x10026dd0  lea     edi, [ecx-1]
0x10026dd3  add     ebx, 2
0x10026dd6  xor     edx, edx
0x10026dd8  test    edi, edi
0x10026dda  jle     short loc_10026E06
0x10026ddc  lea     esp, [esp+0]
0x10026de0  movzx   ecx, word ptr [ebx]
0x10026de3  cmp     ecx, 30h ; '0'
0x10026de6  jb      short loc_10026E06
0x10026de8  cmp     ecx, 39h ; '9'
0x10026deb  ja      short loc_10026E06
0x10026ded  lea     eax, [eax+eax*4]
0x10026df0  inc     edx
0x10026df1  lea     eax, [eax-18h]
0x10026df4  add     ebx, 2
0x10026df7  lea     eax, [ecx+eax*2]
0x10026dfa  movzx   eax, ax
0x10026dfd  cmp     edx, edi
0x10026dff  jl      short loc_10026DE0
0x10026e01  test    ax, ax
0x10026e04  jnz     short loc_10026E0B
0x10026e06  mov     eax, 20h ; ' '
0x10026e0b  mov     edx, [esp+20h+var_10]
0x10026e0f  lea     ecx, [esi+2]
0x10026e12  mov     ebp, [esp+20h+arg_4]
0x10026e16  mov     edi, 26h ; '&'
0x10026e1b  mov     [edx], ax
0x10026e1e  add     edx, 2
0x10026e21  dec     ebp
0x10026e22  cmp     word ptr [ecx], 0
0x10026e26  mov     [esp+20h+var_10], edx
0x10026e2a  mov     [esp+20h+arg_4], ebp
0x10026e2e  jnz     loc_10026CF6
0x10026e34  mov     eax, [esp+20h+arg_0]
0x10026e38  cmp     [esp+20h+arg_4], 0
0x10026e3d  jbe     short loc_10026E44
0x10026e3f  xor     ecx, ecx
0x10026e41  mov     [edx], cx
0x10026e44  pop     edi
0x10026e45  pop     esi
0x10026e46  pop     ebp
0x10026e47  pop     ebx
0x10026e48  add     esp, 10h
0x10026e4b  retn    8
0x10026e4e  mov     [edx], di
0x10026e51  jmp     short loc_10026E1E
0x10026e53  mov     eax, [esp+20h+arg_0]
0x10026e57  pop     edi
0x10026e58  pop     esi
0x10026e59  pop     ebp
0x10026e5a  pop     ebx
0x10026e5b  add     esp, 10h
0x10026e5e  retn    8
```
