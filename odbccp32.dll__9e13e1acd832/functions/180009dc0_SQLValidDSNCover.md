# SQLValidDSNCover

- ea: `0x180009dc0`
- end: `0x180009e46`
- name: `SQLValidDSNCover`
- size: `134`
- prototype: `_BOOL8 __fastcall(_WORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800097d0`
- `0x180009e50`
- `0x180009e8c`

## callees

- `0x180009dc0`

## import_xrefs

- `msvcrt!wcschr` at `0x180009e18`
- `msvcrt!wcschr` at `0x180009e18`

## pseudocode

```c
_BOOL8 __fastcall SQLValidDSNCover(_WORD *a1)
{
  _WORD *v1; // rbx
  unsigned __int64 v2; // rcx
  __int64 v3; // rdx
  unsigned __int64 v4; // rax

  v1 = a1;
  if ( !a1 )
    return 0;
  while ( 1 )
  {
    v2 = (unsigned __int16)*v1;
    if ( (unsigned __int16)v2 > 0x20u )
      break;
    v3 = 0x100002600LL;
    if ( !_bittest64(&v3, v2) )
      break;
    ++v1;
  }
  if ( !(_WORD)v2 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( v1[v4] );
  if ( v4 > 0x20 )
    return 0;
  do
  {
    if ( wcschr(L"[]{}(),;?*=!@\\", v2) )
      break;
    LOWORD(v2) = *++v1;
  }
  while ( *v1 );
  return *v1 == 0;
}

```

## disassembly

```asm
0x180009dc0  mov     [rsp+arg_0], rbx
0x180009dc5  push    rdi
0x180009dc6  sub     rsp, 20h
0x180009dca  xor     edi, edi
0x180009dcc  mov     rbx, rcx
0x180009dcf  test    rcx, rcx
0x180009dd2  jz      short loc_180009E39
0x180009dd4  lea     r8d, [rdi+20h]
0x180009dd8  movzx   ecx, word ptr [rbx]
0x180009ddb  cmp     cx, r8w
0x180009ddf  ja      short loc_180009DF7
0x180009de1  mov     rdx, 100002600h
0x180009deb  bt      rdx, rcx
0x180009def  jnb     short loc_180009DF7
0x180009df1  add     rbx, 2
0x180009df5  jmp     short loc_180009DD8
0x180009df7  test    cx, cx
0x180009dfa  jz      short loc_180009E39
0x180009dfc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009e00  inc     rax
0x180009e03  cmp     [rbx+rax*2], di
0x180009e07  jnz     short loc_180009E00
0x180009e09  cmp     rax, r8
0x180009e0c  ja      short loc_180009E39
0x180009e0e  movzx   edx, cx; Ch
0x180009e11  lea     rcx, Str; "[]{}(),;?*=!@\\"
0x180009e18  call    cs:__imp_wcschr
0x180009e1e  test    rax, rax
0x180009e21  jnz     short loc_180009E2F
0x180009e23  add     rbx, 2
0x180009e27  movzx   ecx, word ptr [rbx]
0x180009e2a  test    cx, cx
0x180009e2d  jnz     short loc_180009E0E
0x180009e2f  cmp     [rbx], di
0x180009e32  mov     eax, edi
0x180009e34  setz    al
0x180009e37  jmp     short loc_180009E3B
0x180009e39  xor     eax, eax
0x180009e3b  mov     rbx, [rsp+28h+arg_0]
0x180009e40  add     rsp, 20h
0x180009e44  pop     rdi
0x180009e45  retn
```
