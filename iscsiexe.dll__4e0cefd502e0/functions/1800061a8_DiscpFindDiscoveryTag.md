# DiscpFindDiscoveryTag

- ea: `0x1800061a8`
- end: `0x180006295`
- name: `DiscpFindDiscoveryTag`
- size: `237`
- prototype: `__int64 __fastcall(wchar_t *pszSrc, int, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800064f8`
- `0x1800067e8`
- `0x18000690c`

## callees

- `0x180003198`
- `0x18000325c`
- `0x1800061a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000625a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000625a`
- `ISCSIUM!DiscpAllocMemory` at `0x1800061e6`
- `ISCSIUM!DiscpAllocMemory` at `0x1800061e6`
- `ISCSIUM!DiscpFreeMemory` at `0x18000627c`
- `ISCSIUM!DiscpFreeMemory` at `0x18000627c`

## pseudocode

```c
__int64 __fastcall DiscpFindDiscoveryTag(wchar_t *pszSrc, int a2, _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rax
  unsigned int v7; // edi
  wchar_t *v8; // rbx
  unsigned int v9; // esi
  _DWORD *v10; // rdi

  v3 = a2;
  if ( a2 == 1 )
  {
    v8 = pszSrc;
  }
  else
  {
    if ( (unsigned int)(a2 - 3) > 2 )
    {
      v8 = 0;
      v9 = 87;
    }
    else
    {
      v6 = -1;
      do
        ++v6;
      while ( pszSrc[v6] );
      v7 = v6 + 14;
      v8 = (wchar_t *)DiscpAllocMemory((unsigned int)(2 * (v6 + 14)));
      if ( v8 )
      {
        StringCchCopyW(v8, v7, DiscpMechanismText[v3 - 3]);
        StringCchCatW(v8, v7, pszSrc);
        v9 = 0;
      }
      else
      {
        v9 = 8;
      }
    }
    if ( v9 )
      return v9;
  }
  v10 = DiscpDiscoveryTagList;
  v9 = 1168;
  while ( v10 != (_DWORD *)&DiscpDiscoveryTagList )
  {
    if ( ((_DWORD)v3 == 1 || v10[5] == (_DWORD)v3) && !(unsigned int)_o__wcsicmp(v10 + 6, v8) )
    {
      *a3 = v10;
      v9 = 0;
      break;
    }
    v10 = *(_DWORD **)v10;
  }
  if ( v8 != pszSrc )
    DiscpFreeMemory(v8);
  return v9;
}

```

## disassembly

```asm
0x1800061a8  push    rbx
0x1800061aa  push    rbp
0x1800061ab  push    rsi
0x1800061ac  push    rdi
0x1800061ad  push    r12
0x1800061af  push    r13
0x1800061b1  push    r14
0x1800061b3  push    r15
0x1800061b5  sub     rsp, 28h
0x1800061b9  movsxd  rbp, edx
0x1800061bc  xor     r12d, r12d
0x1800061bf  mov     r15, r8
0x1800061c2  mov     r14, rcx
0x1800061c5  cmp     ebp, 1
0x1800061c8  jz      short loc_180006231
0x1800061ca  lea     eax, [rbp-3]
0x1800061cd  cmp     eax, 2
0x1800061d0  ja      short loc_180006223
0x1800061d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800061d6  inc     rax
0x1800061d9  cmp     [rcx+rax*2], r12w
0x1800061de  jnz     short loc_1800061D6
0x1800061e0  lea     edi, [rax+0Eh]
0x1800061e3  lea     ecx, [rdi+rdi]
0x1800061e6  call    cs:__imp_DiscpAllocMemory
0x1800061ec  mov     rbx, rax
0x1800061ef  test    rax, rax
0x1800061f2  jz      short loc_18000621C
0x1800061f4  lea     rax, DiscpMechanismText
0x1800061fb  mov     edx, edi; cchDest
0x1800061fd  mov     r8, [rax+rbp*8-18h]; pszSrc
0x180006202  mov     rcx, rbx; pszDest
0x180006205  call    StringCchCopyW
0x18000620a  mov     r8, r14; pszSrc
0x18000620d  mov     edx, edi; cchDest
0x18000620f  mov     rcx, rbx; pszDest
0x180006212  call    StringCchCatW
0x180006217  mov     esi, r12d
0x18000621a  jmp     short loc_18000622B
0x18000621c  mov     esi, 8
0x180006221  jmp     short loc_18000622B
0x180006223  mov     rbx, r12
0x180006226  mov     esi, 57h ; 'W'
0x18000622b  test    esi, esi
0x18000622d  jz      short loc_180006234
0x18000622f  jmp     short loc_180006282
0x180006231  mov     rbx, r14
0x180006234  mov     rdi, cs:DiscpDiscoveryTagList
0x18000623b  lea     r13, DiscpDiscoveryTagList
0x180006242  mov     esi, 490h
0x180006247  jmp     short loc_180006267
0x180006249  cmp     ebp, 1
0x18000624c  jz      short loc_180006253
0x18000624e  cmp     [rdi+14h], ebp
0x180006251  jnz     short loc_180006264
0x180006253  lea     rcx, [rdi+18h]
0x180006257  mov     rdx, rbx
0x18000625a  call    cs:__imp__o__wcsicmp
0x180006260  test    eax, eax
0x180006262  jz      short loc_18000626E
0x180006264  mov     rdi, [rdi]
0x180006267  cmp     rdi, r13
0x18000626a  jnz     short loc_180006249
0x18000626c  jmp     short loc_180006274
0x18000626e  mov     [r15], rdi
0x180006271  mov     esi, r12d
0x180006274  cmp     rbx, r14
0x180006277  jz      short loc_180006282
0x180006279  mov     rcx, rbx
0x18000627c  call    cs:__imp_DiscpFreeMemory
0x180006282  mov     eax, esi
0x180006284  add     rsp, 28h
0x180006288  pop     r15
0x18000628a  pop     r14
0x18000628c  pop     r13
0x18000628e  pop     r12
0x180006290  pop     rdi
0x180006291  pop     rsi
0x180006292  pop     rbp
0x180006293  pop     rbx
0x180006294  retn
```
