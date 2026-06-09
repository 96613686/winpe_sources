# GetNextRefToken

- ea: `0x10018f40`
- end: `0x10019153`
- name: `GetNextRefToken`
- size: `531`
- prototype: `int __fastcall(int, int, int *, _DWORD *, char *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100192b0`
- `0x100197c0`

## callees

- `0x10018f40`
- `0x10025757`
- `0x1003669c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x10019079`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x10019079`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10018f99`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10018fc7`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10019036`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001904e`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001906b`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10018f99`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10018fc7`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x10019036`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001904e`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x1001906b`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x10018f7b`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x10018fa9`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x10018f7b`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x10018fa9`

## pseudocode

```c
int __fastcall GetNextRefToken(int a1, int a2, int *a3, _DWORD *a4, char *a5, int a6)
{
  int v7; // eax
  wint_t v8; // bx
  int result; // eax
  wint_t *v10; // ebx
  int v11; // ebx
  int v12; // eax
  _WORD *v13; // ecx
  size_t v14; // ebx
  int v15; // eax
  __int16 v16; // dx
  int v17; // ecx
  int C; // [esp+Ch] [ebp-8h]
  int v19; // [esp+10h] [ebp-4h]

  v19 = a1;
  v7 = *a3;
  v8 = *(_WORD *)(a2 + 2 * *a3);
  if ( !v8 )
    return 4;
  while ( 1 )
  {
    if ( v8 == (_WORD)qword_1003A9A4 )
    {
      *a3 = v7 + 1;
      return 3;
    }
    if ( a1 == 1 )
    {
      if ( _toupper(v8) == WORD1(qword_1003A9A4) && _iswctype(*(_WORD *)(a2 + 2 * *a3 + 2), 4u) )
      {
        ++*a3;
        return 5;
      }
      if ( _toupper(v8) == WORD2(qword_1003A9A4) && _iswctype(*(_WORD *)(a2 + 2 * *a3 + 2), 4u) )
      {
        ++*a3;
        return 6;
      }
      a1 = v19;
    }
    if ( v8 != 36 )
      break;
    v7 = *a3 + 1;
    *a3 = v7;
    v8 = *(_WORD *)(a2 + 2 * v7);
    if ( !v8 )
      return 4;
  }
  if ( v8 == 58 )
  {
    ++*a3;
    return 2;
  }
  if ( _iswctype(v8, 4u) )
  {
    v10 = (wint_t *)(a2 + 2 * *a3);
    if ( _iswctype(*v10, 4u) )
    {
      do
        ++*a3;
      while ( _iswctype(*(_WORD *)(a2 + 2 * *a3), 4u) );
    }
    *a4 = __o__wtoi(v10);
    return 1;
  }
  else
  {
    if ( v8 == 39 )
    {
      v11 = 0;
      v12 = *a3 + 1;
      *a3 = v12;
      v13 = (_WORD *)(a2 + 2 * v12);
      if ( *v13 )
      {
        do
        {
          if ( *(_WORD *)(a2 + 2 * v12) == 39 )
          {
            *a3 = ++v12;
            if ( *(_WORD *)(a2 + 2 * v12) != 39 )
              break;
          }
          ++v12;
          ++v11;
          *a3 = v12;
        }
        while ( *(_WORD *)(a2 + 2 * v12) );
      }
    }
    else
    {
      if ( !DBIsCharAlpha(v8) )
        return 7;
      v15 = *a3;
      v11 = 0;
      v13 = (_WORD *)(a2 + 2 * *a3);
      C = (int)v13;
      if ( *v13 )
      {
        v16 = qword_1003A9A4;
        do
        {
          v17 = *(unsigned __int16 *)(a2 + 2 * v15);
          if ( (_WORD)v17 == v16 )
            break;
          if ( v17 == 58 )
            break;
          ++v15;
          ++v11;
          *a3 = v15;
        }
        while ( *(_WORD *)(a2 + 2 * v15) );
        v13 = (_WORD *)C;
      }
    }
    if ( v11 >= a6 - 1 )
      v11 = a6 - 1;
    v14 = 2 * v11;
    memcpy(a5, v13, v14);
    result = 0;
    *(_WORD *)&a5[v14] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x10018f40  mov     edi, edi
0x10018f42  push    ebp
0x10018f43  mov     ebp, esp
0x10018f45  sub     esp, 8
0x10018f48  push    ebx
0x10018f49  push    esi
0x10018f4a  mov     esi, [ebp+arg_0]
0x10018f4d  push    edi
0x10018f4e  mov     edi, edx
0x10018f50  mov     [ebp+var_4], ecx
0x10018f53  mov     eax, [esi]
0x10018f55  movzx   ebx, word ptr [edi+eax*2]
0x10018f59  test    bx, bx
0x10018f5c  jz      loc_10018FEF
0x10018f62  cmp     bx, word ptr qword_1003A9A4
0x10018f69  jz      loc_10019142
0x10018f6f  cmp     ecx, 1
0x10018f72  jnz     short loc_10018FD7
0x10018f74  movzx   eax, bx
0x10018f77  push    eax; C
0x10018f78  mov     [ebp+C], eax
0x10018f7b  call    ds:__imp__toupper
0x10018f81  movzx   ecx, word ptr qword_1003A9A4+2
0x10018f88  add     esp, 4
0x10018f8b  cmp     eax, ecx
0x10018f8d  jnz     short loc_10018FA6
0x10018f8f  mov     eax, [esi]
0x10018f91  push    4; Type
0x10018f93  movzx   eax, word ptr [edi+eax*2+2]
0x10018f98  push    eax; C
0x10018f99  call    ds:__imp__iswctype
0x10018f9f  add     esp, 8
0x10018fa2  test    eax, eax
0x10018fa4  jnz     short loc_10018FFD
0x10018fa6  push    [ebp+C]; C
0x10018fa9  call    ds:__imp__toupper
0x10018faf  movzx   ecx, word ptr qword_1003A9A4+4
0x10018fb6  add     esp, 4
0x10018fb9  cmp     eax, ecx
0x10018fbb  jnz     short loc_10018FD4
0x10018fbd  mov     eax, [esi]
0x10018fbf  push    4; Type
0x10018fc1  movzx   eax, word ptr [edi+eax*2+2]
0x10018fc6  push    eax; C
0x10018fc7  call    ds:__imp__iswctype
0x10018fcd  add     esp, 8
0x10018fd0  test    eax, eax
0x10018fd2  jnz     short loc_1001900D
0x10018fd4  mov     ecx, [ebp+var_4]
0x10018fd7  cmp     bx, 24h ; '$'
0x10018fdb  jnz     short loc_1001901D
0x10018fdd  mov     eax, [esi]
0x10018fdf  inc     eax
0x10018fe0  mov     [esi], eax
0x10018fe2  movzx   ebx, word ptr [edi+eax*2]
0x10018fe6  test    bx, bx
0x10018fe9  jnz     loc_10018F62
0x10018fef  pop     edi
0x10018ff0  pop     esi
0x10018ff1  mov     eax, 4
0x10018ff6  pop     ebx
0x10018ff7  mov     esp, ebp
0x10018ff9  pop     ebp
0x10018ffa  retn    10h
0x10018ffd  inc     dword ptr [esi]
0x10018fff  mov     eax, 5
0x10019004  pop     edi
0x10019005  pop     esi
0x10019006  pop     ebx
0x10019007  mov     esp, ebp
0x10019009  pop     ebp
0x1001900a  retn    10h
0x1001900d  inc     dword ptr [esi]
0x1001900f  mov     eax, 6
0x10019014  pop     edi
0x10019015  pop     esi
0x10019016  pop     ebx
0x10019017  mov     esp, ebp
0x10019019  pop     ebp
0x1001901a  retn    10h
0x1001901d  cmp     bx, 3Ah ; ':'
0x10019021  jnz     short loc_10019033
0x10019023  inc     dword ptr [esi]
0x10019025  mov     eax, 2
0x1001902a  pop     edi
0x1001902b  pop     esi
0x1001902c  pop     ebx
0x1001902d  mov     esp, ebp
0x1001902f  pop     ebp
0x10019030  retn    10h
0x10019033  push    4; Type
0x10019035  push    ebx; C
0x10019036  call    ds:__imp__iswctype
0x1001903c  add     esp, 8
0x1001903f  test    eax, eax
0x10019041  jz      short loc_10019095
0x10019043  mov     eax, [esi]
0x10019045  push    4; Type
0x10019047  lea     ebx, [edi+eax*2]
0x1001904a  movzx   eax, word ptr [ebx]
0x1001904d  push    eax; C
0x1001904e  call    ds:__imp__iswctype
0x10019054  add     esp, 8
0x10019057  test    eax, eax
0x10019059  jz      short loc_10019078
0x1001905b  nop     dword ptr [eax+eax+00h]
0x10019060  inc     dword ptr [esi]
0x10019062  mov     eax, [esi]
0x10019064  push    4; Type
0x10019066  movzx   eax, word ptr [edi+eax*2]
0x1001906a  push    eax; C
0x1001906b  call    ds:__imp__iswctype
0x10019071  add     esp, 8
0x10019074  test    eax, eax
0x10019076  jnz     short loc_10019060
0x10019078  push    ebx
0x10019079  call    ds:__imp___o__wtoi
0x1001907f  mov     ecx, [ebp+arg_4]
0x10019082  add     esp, 4
0x10019085  pop     edi
0x10019086  pop     esi
0x10019087  mov     [ecx], eax
0x10019089  mov     eax, 1
0x1001908e  pop     ebx
0x1001908f  mov     esp, ebp
0x10019091  pop     ebp
0x10019092  retn    10h
0x10019095  cmp     bx, 27h ; '''
0x10019099  jnz     short loc_100190F4
0x1001909b  mov     eax, [esi]
0x1001909d  xor     ebx, ebx
0x1001909f  inc     eax
0x100190a0  mov     [esi], eax
0x100190a2  cmp     [edi+eax*2], bx
0x100190a6  lea     ecx, [edi+eax*2]
0x100190a9  jz      short loc_100190CC
0x100190ab  nop     dword ptr [eax+eax+00h]
0x100190b0  cmp     word ptr [edi+eax*2], 27h ; '''
0x100190b5  jnz     short loc_100190C1
0x100190b7  inc     eax
0x100190b8  mov     [esi], eax
0x100190ba  cmp     word ptr [edi+eax*2], 27h ; '''
0x100190bf  jnz     short loc_100190CC
0x100190c1  inc     eax
0x100190c2  inc     ebx
0x100190c3  mov     [esi], eax
0x100190c5  cmp     word ptr [edi+eax*2], 0
0x100190ca  jnz     short loc_100190B0
0x100190cc  mov     eax, [ebp+arg_C]
0x100190cf  mov     esi, [ebp+arg_8]
0x100190d2  dec     eax
0x100190d3  cmp     ebx, eax
0x100190d5  cmovge  ebx, eax
0x100190d8  add     ebx, ebx
0x100190da  push    ebx; Size
0x100190db  push    ecx; Src
0x100190dc  push    esi; void *
0x100190dd  call    _memcpy
0x100190e2  add     esp, 0Ch
0x100190e5  xor     eax, eax
0x100190e7  mov     [ebx+esi], ax
0x100190eb  pop     edi
0x100190ec  pop     esi
0x100190ed  pop     ebx
0x100190ee  mov     esp, ebp
0x100190f0  pop     ebp
0x100190f1  retn    10h
0x100190f4  movzx   ecx, bx; C
0x100190f7  call    _DBIsCharAlpha@4; DBIsCharAlpha(x)
0x100190fc  test    eax, eax
0x100190fe  jz      short loc_10019134
0x10019100  mov     eax, [esi]
0x10019102  xor     ebx, ebx
0x10019104  lea     ecx, [edi+eax*2]
0x10019107  mov     [ebp+C], ecx
0x1001910a  cmp     [ecx], bx
0x1001910d  jz      short loc_100190CC
0x1001910f  mov     dx, word ptr qword_1003A9A4
0x10019116  movzx   ecx, word ptr [edi+eax*2]
0x1001911a  cmp     cx, dx
0x1001911d  jz      short loc_1001912F
0x1001911f  cmp     ecx, 3Ah ; ':'
0x10019122  jz      short loc_1001912F
0x10019124  inc     eax
0x10019125  inc     ebx
0x10019126  mov     [esi], eax
0x10019128  cmp     word ptr [edi+eax*2], 0
0x1001912d  jnz     short loc_10019116
0x1001912f  mov     ecx, [ebp+C]
0x10019132  jmp     short loc_100190CC
0x10019134  pop     edi
0x10019135  pop     esi
0x10019136  mov     eax, 7
0x1001913b  pop     ebx
0x1001913c  mov     esp, ebp
0x1001913e  pop     ebp
0x1001913f  retn    10h
0x10019142  inc     eax
0x10019143  pop     edi
0x10019144  mov     [esi], eax
0x10019146  mov     eax, 3
0x1001914b  pop     esi
0x1001914c  pop     ebx
0x1001914d  mov     esp, ebp
0x1001914f  pop     ebp
0x10019150  retn    10h
```
