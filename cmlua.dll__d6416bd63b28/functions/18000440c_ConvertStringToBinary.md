# ConvertStringToBinary

- ea: `0x18000440c`
- end: `0x1800044bf`
- name: `ConvertStringToBinary`
- size: `179`
- prototype: `_BYTE *__fastcall(__int64, _DWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002420`
- `0x1800039c0`
- `0x180003ab0`
- `0x180003ba0`
- `0x180003cd0`

## callees

- `0x18000440c`

## import_xrefs

- `cmutil!CmMalloc` at `0x180004439`
- `cmutil!CmMalloc` at `0x180004439`

## pseudocode

```c
_BYTE *__fastcall ConvertStringToBinary(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // rbx
  _BYTE *v6; // r10
  int i; // r11d
  __int64 v8; // rcx
  __int16 v9; // dx
  __int16 v10; // r8
  char v11; // cl
  char v12; // r9
  char v13; // r9
  __int64 v14; // rax

  if ( !a1 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a1 + 2 * v4) );
  v5 = v4 >> 1;
  v6 = CmMalloc((int)v5);
  if ( !v6 )
    return 0;
  if ( a2 )
    *a2 = v5;
  for ( i = 0; i < (int)v5; v6[v14] = v10 + v13 - v11 )
  {
    v8 = 2 * i;
    v9 = *(_WORD *)(a1 + 2 * v8);
    v10 = *(_WORD *)(a1 + 2 * v8 + 2);
    v11 = 48;
    v12 = v9;
    if ( (unsigned __int16)(v9 - 48) > 9u )
      v12 = v9 - 55;
    v13 = 16 * v12;
    v14 = (unsigned int)i;
    if ( (unsigned __int16)(v10 - 48) > 9u )
      v11 = 55;
    ++i;
  }
  return v6;
}

```

## disassembly

```asm
0x18000440c  push    rbx
0x18000440e  push    rbp
0x18000440f  push    rsi
0x180004410  push    rdi
0x180004411  sub     rsp, 28h
0x180004415  xor     ebp, ebp
0x180004417  mov     rsi, rdx
0x18000441a  mov     rdi, rcx
0x18000441d  test    rcx, rcx
0x180004420  jz      loc_1800044B4
0x180004426  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000442a  inc     rbx
0x18000442d  cmp     [rcx+rbx*2], bp
0x180004431  jnz     short loc_18000442A
0x180004433  shr     rbx, 1
0x180004436  movsxd  rcx, ebx
0x180004439  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x18000443f  mov     r10, rax
0x180004442  test    rax, rax
0x180004445  jz      short loc_1800044B4
0x180004447  test    rsi, rsi
0x18000444a  jz      short loc_18000444E
0x18000444c  mov     [rsi], ebx
0x18000444e  mov     r11d, ebp
0x180004451  test    ebx, ebx
0x180004453  jle     short loc_1800044AF
0x180004455  mov     esi, 30h ; '0'
0x18000445a  lea     ebp, [rsi+7]
0x18000445d  lea     eax, [r11+r11]
0x180004461  movsxd  rcx, eax
0x180004464  movzx   edx, word ptr [rdi+rcx*2]
0x180004468  movzx   r8d, word ptr [rdi+rcx*2+2]
0x18000446e  mov     ecx, esi
0x180004470  movzx   r9d, dl
0x180004474  sub     dx, si
0x180004477  mov     al, r9b
0x18000447a  sub     al, bpl
0x18000447d  movzx   eax, al
0x180004480  cmp     dx, 9
0x180004484  cmova   r9d, eax
0x180004488  movzx   eax, r8w
0x18000448c  shl     r9b, 4
0x180004490  sub     ax, si
0x180004493  cmp     ax, 9
0x180004497  mov     eax, r11d
0x18000449a  cmova   ecx, ebp
0x18000449d  inc     r11d
0x1800044a0  sub     r9b, cl
0x1800044a3  add     r9b, r8b
0x1800044a6  mov     [rax+r10], r9b
0x1800044aa  cmp     r11d, ebx
0x1800044ad  jl      short loc_18000445D
0x1800044af  mov     rax, r10
0x1800044b2  jmp     short loc_1800044B6
0x1800044b4  xor     eax, eax
0x1800044b6  add     rsp, 28h
0x1800044ba  pop     rdi
0x1800044bb  pop     rsi
0x1800044bc  pop     rbp
0x1800044bd  pop     rbx
0x1800044be  retn
```
