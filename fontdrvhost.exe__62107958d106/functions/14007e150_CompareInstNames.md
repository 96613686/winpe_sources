# CompareInstNames

- ea: `0x14007e150`
- end: `0x14007e26f`
- name: `CompareInstNames`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14007e378`

## callees

- `0x14007e150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e193`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1a6`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1be`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1d0`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1e9`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1f6`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e227`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e232`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e193`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1a6`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1be`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1d0`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1e9`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e1f6`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e227`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x14007e232`

## pseudocode

```c
__int64 __fastcall CompareInstNames(unsigned __int16 *a1, __int16 *a2)
{
  __int16 *v2; // rsi
  unsigned __int16 *v3; // r14
  unsigned __int16 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int16 v7; // cx
  __int16 v8; // ax
  unsigned __int16 v9; // bx
  int v10; // edi
  unsigned int v11; // edx

  v2 = a2;
  v3 = a1;
  if ( !a1 || !a2 )
    return 0;
  while ( 1 )
  {
    v4 = *v3;
    if ( !*v3 || !*v2 )
      break;
    if ( !(unsigned int)_o_iswdigit(v4) )
    {
      while ( 1 )
      {
        v5 = *v3;
        if ( !(_WORD)v5 || (unsigned int)_o_iswdigit(v5) )
          break;
        ++v3;
      }
    }
    if ( !(unsigned int)_o_iswdigit((unsigned __int16)*v2) )
    {
      while ( 1 )
      {
        v6 = (unsigned __int16)*v2;
        if ( !(_WORD)v6 || (unsigned int)_o_iswdigit(v6) )
          break;
        ++v2;
      }
    }
    while ( (unsigned int)_o_iswdigit(*v3) && (unsigned int)_o_iswdigit((unsigned __int16)*v2) )
    {
      v7 = *v3;
      v8 = *v2++;
      ++v3;
      if ( v7 != v8 )
        return 0;
    }
    v9 = *v2;
    v10 = _o_iswdigit(*v3);
    if ( v10 != (unsigned int)_o_iswdigit(v9) )
      return 0;
  }
  v11 = 1;
  if ( (v4 == 0) != (*v2 == 0) )
    return 0;
  return v11;
}

```

## disassembly

```asm
0x14007e150  push    rbx
0x14007e152  push    rsi
0x14007e153  push    rdi
0x14007e154  push    r14
0x14007e156  push    r15
0x14007e158  sub     rsp, 30h
0x14007e15c  mov     rsi, rdx
0x14007e15f  mov     r14, rcx
0x14007e162  xor     r15d, r15d
0x14007e165  test    rcx, rcx
0x14007e168  jz      loc_14007E25E
0x14007e16e  test    rdx, rdx
0x14007e171  jz      loc_14007E25E
0x14007e177  movzx   r8d, word ptr [r14]
0x14007e17b  test    r8w, r8w
0x14007e17f  jz      loc_14007E241
0x14007e185  cmp     [rsi], r15w
0x14007e189  jz      loc_14007E241
0x14007e18f  movzx   ecx, r8w
0x14007e193  call    cs:__imp__o_iswdigit
0x14007e199  test    eax, eax
0x14007e19b  jnz     short loc_14007E1BB
0x14007e19d  movzx   ecx, word ptr [r14]
0x14007e1a1  test    cx, cx
0x14007e1a4  jz      short loc_14007E1BB
0x14007e1a6  call    cs:__imp__o_iswdigit
0x14007e1ac  test    eax, eax
0x14007e1ae  jnz     short loc_14007E1BB
0x14007e1b0  add     r14, 2
0x14007e1b4  mov     [rsp+58h+var_30], r14
0x14007e1b9  jmp     short loc_14007E19D
0x14007e1bb  movzx   ecx, word ptr [rsi]
0x14007e1be  call    cs:__imp__o_iswdigit
0x14007e1c4  test    eax, eax
0x14007e1c6  jnz     short loc_14007E1E5
0x14007e1c8  movzx   ecx, word ptr [rsi]
0x14007e1cb  test    cx, cx
0x14007e1ce  jz      short loc_14007E1E5
0x14007e1d0  call    cs:__imp__o_iswdigit
0x14007e1d6  test    eax, eax
0x14007e1d8  jnz     short loc_14007E1E5
0x14007e1da  add     rsi, 2
0x14007e1de  mov     [rsp+58h+var_38], rsi
0x14007e1e3  jmp     short loc_14007E1C8
0x14007e1e5  movzx   ecx, word ptr [r14]
0x14007e1e9  call    cs:__imp__o_iswdigit
0x14007e1ef  test    eax, eax
0x14007e1f1  jz      short loc_14007E220
0x14007e1f3  movzx   ecx, word ptr [rsi]
0x14007e1f6  call    cs:__imp__o_iswdigit
0x14007e1fc  test    eax, eax
0x14007e1fe  jz      short loc_14007E220
0x14007e200  movzx   ecx, word ptr [r14]
0x14007e204  movzx   eax, word ptr [rsi]
0x14007e207  add     rsi, 2
0x14007e20b  mov     [rsp+58h+var_38], rsi
0x14007e210  add     r14, 2
0x14007e214  mov     [rsp+58h+var_30], r14
0x14007e219  cmp     cx, ax
0x14007e21c  jnz     short loc_14007E25E
0x14007e21e  jmp     short loc_14007E1E5
0x14007e220  movzx   ebx, word ptr [rsi]
0x14007e223  movzx   ecx, word ptr [r14]
0x14007e227  call    cs:__imp__o_iswdigit
0x14007e22d  mov     edi, eax
0x14007e22f  movzx   ecx, bx
0x14007e232  call    cs:__imp__o_iswdigit
0x14007e238  cmp     edi, eax
0x14007e23a  jnz     short loc_14007E25E
0x14007e23c  jmp     loc_14007E177
0x14007e241  mov     edx, 1
0x14007e246  mov     ecx, r15d
0x14007e249  cmp     [rsi], r15w
0x14007e24d  setz    cl
0x14007e250  mov     eax, r15d
0x14007e253  test    r8w, r8w
0x14007e257  setz    al
0x14007e25a  cmp     eax, ecx
0x14007e25c  jz      short loc_14007E261
0x14007e25e  mov     edx, r15d
0x14007e261  mov     eax, edx
0x14007e263  add     rsp, 30h
0x14007e267  pop     r15
0x14007e269  pop     r14
0x14007e26b  pop     rdi
0x14007e26c  pop     rsi
0x14007e26d  pop     rbx
0x14007e26e  retn
0x140097687  push    rbp
0x140097689  sub     rsp, 20h
0x14009768d  mov     rbp, rdx
0x140097690  add     rsp, 20h
0x140097694  pop     rbp
0x140097695  retn
```
