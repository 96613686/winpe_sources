# SplitCommandLine(ushort *,ushort * *)

- ea: `0x140003d30`
- end: `0x140003e25`
- name: `?SplitCommandLine@@YAIPEAGPEAPEAG@Z`
- size: `245`
- prototype: `unsigned int __fastcall(wchar_t *Destination, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400032a8`

## callees

- `0x140003d30`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x140003e09`
- `msvcrt!wcscpy_s` at `0x140003e09`

## pseudocode

```c
__int64 __fastcall SplitCommandLine(wchar_t *Destination, unsigned __int16 **a2)
{
  __int64 v2; // rbp
  wchar_t *v4; // rbx
  wchar_t v6; // ax
  bool v7; // di
  unsigned __int16 *v8; // r14
  __int64 v9; // rdx

  v2 = 0;
  v4 = Destination;
  if ( !*Destination )
    return 0;
LABEL_3:
  while ( 1 )
  {
    v6 = *v4;
    if ( *v4 != 32 && v6 != 9 )
      break;
    ++v4;
  }
  if ( v6 )
  {
    v7 = 0;
    v8 = v4;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v6 )
        {
LABEL_17:
          if ( a2 )
            a2[v2] = v8;
          v2 = (unsigned int)(v2 + 1);
          if ( !*v4 )
            return (unsigned int)v2;
          goto LABEL_3;
        }
        if ( v6 != 32 && v6 != 9 )
          break;
        if ( !v7 )
        {
          if ( a2 )
            *v4 = 0;
          ++v4;
          goto LABEL_17;
        }
LABEL_12:
        v6 = v4[1];
        ++v4;
      }
      if ( v6 != 34 )
        goto LABEL_12;
      v7 = !v7;
      if ( !a2 )
        goto LABEL_12;
      v9 = -1;
      do
        ++v9;
      while ( v4[v9] );
      wcscpy_s(v4, v9 + 1, v4 + 1);
      v6 = *v4;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140003d30  mov     [rsp+arg_10], rbx
0x140003d35  mov     [rsp+arg_18], rbp
0x140003d3a  push    rsi
0x140003d3b  sub     rsp, 20h
0x140003d3f  xor     ebp, ebp
0x140003d41  mov     rsi, rdx
0x140003d44  mov     rbx, rcx
0x140003d47  cmp     [rcx], bp
0x140003d4a  jnz     short loc_140003D5E
0x140003d4c  mov     eax, ebp
0x140003d4e  mov     rbx, [rsp+28h+arg_10]
0x140003d53  mov     rbp, [rsp+28h+arg_18]
0x140003d58  add     rsp, 20h
0x140003d5c  pop     rsi
0x140003d5d  retn
0x140003d5e  mov     [rsp+28h+arg_0], rdi
0x140003d63  mov     [rsp+28h+arg_8], r14
0x140003d68  nop     dword ptr [rax+rax+00000000h]
0x140003d70  movzx   eax, word ptr [rbx]
0x140003d73  cmp     ax, 20h ; ' '
0x140003d77  jnz     short loc_140003D7F
0x140003d79  add     rbx, 2
0x140003d7d  jmp     short loc_140003D70
0x140003d7f  cmp     ax, 9
0x140003d83  jz      short loc_140003D79
0x140003d85  test    ax, ax
0x140003d88  jz      short loc_140003DD1
0x140003d8a  xor     dil, dil
0x140003d8d  mov     r14, rbx
0x140003d90  test    ax, ax
0x140003d93  jz      short loc_140003DC4
0x140003d95  cmp     ax, 20h ; ' '
0x140003d99  jz      short loc_140003DB1
0x140003d9b  cmp     ax, 9
0x140003d9f  jz      short loc_140003DB1
0x140003da1  cmp     ax, 22h ; '"'
0x140003da5  jz      short loc_140003DE2
0x140003da7  movzx   eax, word ptr [rbx+2]
0x140003dab  add     rbx, 2
0x140003daf  jmp     short loc_140003D90
0x140003db1  test    dil, dil
0x140003db4  jnz     short loc_140003DA7
0x140003db6  test    rsi, rsi
0x140003db9  jz      short loc_140003DC0
0x140003dbb  xor     eax, eax
0x140003dbd  mov     [rbx], ax
0x140003dc0  add     rbx, 2
0x140003dc4  test    rsi, rsi
0x140003dc7  jnz     short loc_140003E1F
0x140003dc9  inc     ebp
0x140003dcb  cmp     word ptr [rbx], 0
0x140003dcf  jnz     short loc_140003D70
0x140003dd1  mov     r14, [rsp+28h+arg_8]
0x140003dd6  mov     eax, ebp
0x140003dd8  mov     rdi, [rsp+28h+arg_0]
0x140003ddd  jmp     loc_140003D4E
0x140003de2  test    dil, dil
0x140003de5  setz    dil
0x140003de9  test    rsi, rsi
0x140003dec  jz      short loc_140003DA7
0x140003dee  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140003df5  inc     rdx
0x140003df8  cmp     word ptr [rbx+rdx*2], 0
0x140003dfd  jnz     short loc_140003DF5
0x140003dff  lea     r8, [rbx+2]; Source
0x140003e03  inc     rdx; SizeInWords
0x140003e06  mov     rcx, rbx; Destination
0x140003e09  call    cs:__imp_wcscpy_s
0x140003e0f  sub     rbx, 2
0x140003e13  add     rbx, 2
0x140003e17  movzx   eax, word ptr [rbx]
0x140003e1a  jmp     loc_140003D90
0x140003e1f  mov     [rsi+rbp*8], r14
0x140003e23  jmp     short loc_140003DC9
```
