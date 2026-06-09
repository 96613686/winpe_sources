# ErrSecGetAccess(x,x,x,x,x,x,x,x)

- ea: `0x1003a6c0`
- end: `0x1003a7e8`
- name: `_ErrSecGetAccess@32`
- size: `296`
- prototype: ``
- caller_count: `24`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x100133c0`
- `0x100137b0`
- `0x10014310`
- `0x10015460`
- `0x1001a430`
- `0x1001bc80`
- `0x10023f60`
- `0x1002c730`
- `0x10030370`
- `0x10032f00`
- `0x10033d50`
- `0x100366d0`
- `0x10036890`
- `0x10037570`
- `0x10038a30`
- `0x10039790`
- `0x1003a7f0`
- `0x1008b960`
- `0x1008c570`
- `0x1009e76a`
- `0x100a80f3`
- `0x100f35d8`
- `0x100f44be`
- `0x100f4cb6`

## callees

- `0x1003a6c0`
- `0x1003c820`
- `0x1003cb10`
- `0x1003d0e0`
- `0x1003d9f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003a7d4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003a7d4`

## pseudocode

```c
int __stdcall ErrSecGetAccess(int a1, int a2, int a3, int a4, size_t Size, int a6, _DWORD *a7, _DWORD *a8)
{
  _WORD *v8; // ecx
  int result; // eax
  _DWORD *v10; // edi
  size_t v11; // edx
  _DWORD *v12; // edi
  int v13; // esi
  void *Block; // [esp+10h] [ebp-8h] BYREF
  int v15; // [esp+14h] [ebp-4h]

  v8 = (_WORD *)a4;
  if ( !a4 )
  {
    if ( !*(&Src + 5 * mpdbidiiscb[a2]) )
      return -1001;
    v10 = *(&Src + 5 * mpdbidiiscb[a2]);
    return ErrSecCollectAccess(a1, a2, a3, v10, a6, a7, a8);
  }
  v11 = Size;
  v15 = 20 * mpdbidiiscb[a2];
  v10 = *(void **)((char *)&Src + v15);
  Block = v10;
  if ( v10 )
  {
    if ( SecFSameSid((char *)v10 + v10[3], v10[4] - v10[3]) )
      return ErrSecCollectAccess(a1, a2, a3, v10, a6, a7, a8);
    v8 = (_WORD *)a4;
    v11 = Size;
  }
  if ( v11 == 2 && *v8 == 770 )
  {
    *a7 = 0;
    return 0;
  }
  else
  {
    result = ErrSecBuildUserToken(a1, *(int *)((char *)&rgiscb + v15 + 12), (int)v8, v11, &Block);
    if ( result >= 0 )
    {
      v12 = Block;
      SecDeleteSidFromToken(2);
      v13 = ErrSecCollectAccess(a1, a2, a3, v12, a6, a7, a8);
      if ( v12 )
        _free(v12);
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1003a6c0  mov     edi, edi
0x1003a6c2  push    ebp
0x1003a6c3  mov     ebp, esp
0x1003a6c5  and     esp, 0FFFFFFF8h
0x1003a6c8  mov     ecx, [ebp+arg_C]
0x1003a6cb  sub     esp, 0Ch
0x1003a6ce  push    ebx
0x1003a6cf  mov     ebx, [ebp+arg_18]
0x1003a6d2  push    esi
0x1003a6d3  mov     esi, [ebp+arg_4]
0x1003a6d6  push    edi
0x1003a6d7  mov     eax, _mpdbidiiscb[esi*4]
0x1003a6de  lea     eax, [eax+eax*4]
0x1003a6e1  test    ecx, ecx
0x1003a6e3  jnz     short loc_1003A70F
0x1003a6e5  cmp     Src[eax*4], ecx
0x1003a6ec  jnz     short loc_1003A6FC
0x1003a6ee  mov     eax, 0FFFFFC17h
0x1003a6f3  pop     edi
0x1003a6f4  pop     esi
0x1003a6f5  pop     ebx
0x1003a6f6  mov     esp, ebp
0x1003a6f8  pop     ebp
0x1003a6f9  retn    20h ; ' '
0x1003a6fc  mov     eax, _mpdbidiiscb[esi*4]
0x1003a703  lea     eax, [eax+eax*4]
0x1003a706  mov     edi, Src[eax*4]
0x1003a70d  jmp     short loc_1003A740
0x1003a70f  mov     edx, [ebp+Size]
0x1003a712  shl     eax, 2
0x1003a715  mov     [esp+18h+var_4], eax
0x1003a719  mov     edi, Src[eax]
0x1003a71f  mov     [esp+18h+Block], edi
0x1003a723  test    edi, edi
0x1003a725  jz      short loc_1003A766
0x1003a727  mov     ecx, [edi+0Ch]
0x1003a72a  mov     eax, [edi+10h]
0x1003a72d  sub     eax, ecx
0x1003a72f  push    eax
0x1003a730  lea     eax, [edi+ecx]
0x1003a733  mov     ecx, [ebp+arg_C]
0x1003a736  push    eax
0x1003a737  call    _SecFSameSid@16; SecFSameSid(x,x,x,x)
0x1003a73c  test    eax, eax
0x1003a73e  jz      short loc_1003A760
0x1003a740  push    [ebp+arg_1C]
0x1003a743  mov     ecx, [ebp+arg_0]
0x1003a746  mov     edx, esi
0x1003a748  push    ebx
0x1003a749  push    [ebp+arg_14]
0x1003a74c  push    edi
0x1003a74d  push    [ebp+arg_8]
0x1003a750  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1003a755  mov     esi, eax
0x1003a757  pop     edi
0x1003a758  pop     esi
0x1003a759  pop     ebx
0x1003a75a  mov     esp, ebp
0x1003a75c  pop     ebp
0x1003a75d  retn    20h ; ' '
0x1003a760  mov     ecx, [ebp+arg_C]
0x1003a763  mov     edx, [ebp+Size]
0x1003a766  cmp     edx, 2
0x1003a769  jnz     short loc_1003A789
0x1003a76b  mov     eax, offset dword_1000A30C
0x1003a770  mov     ax, [eax]
0x1003a773  cmp     ax, [ecx]
0x1003a776  jnz     short loc_1003A789
0x1003a778  mov     dword ptr [ebx], 0
0x1003a77e  xor     eax, eax
0x1003a780  pop     edi
0x1003a781  pop     esi
0x1003a782  pop     ebx
0x1003a783  mov     esp, ebp
0x1003a785  pop     ebp
0x1003a786  retn    20h ; ' '
0x1003a789  lea     eax, [esp+18h+Block]
0x1003a78d  push    eax; int
0x1003a78e  push    edx; Size
0x1003a78f  mov     edx, [esp+20h+var_4]
0x1003a793  push    ecx; int
0x1003a794  mov     ecx, [ebp+arg_0]
0x1003a797  mov     edx, dword ptr (_rgiscb+0Ch)[edx]
0x1003a79d  call    _ErrSecBuildUserToken@20; ErrSecBuildUserToken(x,x,x,x,x)
0x1003a7a2  test    eax, eax
0x1003a7a4  js      short loc_1003A7DF
0x1003a7a6  mov     edi, [esp+18h+Block]
0x1003a7aa  mov     edx, offset dword_1000A30C
0x1003a7af  push    2
0x1003a7b1  mov     ecx, edi
0x1003a7b3  call    _SecDeleteSidFromToken@12; SecDeleteSidFromToken(x,x,x)
0x1003a7b8  push    [ebp+arg_1C]
0x1003a7bb  mov     ecx, [ebp+arg_0]
0x1003a7be  mov     edx, esi
0x1003a7c0  push    ebx
0x1003a7c1  push    [ebp+arg_14]
0x1003a7c4  push    edi
0x1003a7c5  push    [ebp+arg_8]
0x1003a7c8  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1003a7cd  mov     esi, eax
0x1003a7cf  test    edi, edi
0x1003a7d1  jz      short loc_1003A7DD
0x1003a7d3  push    edi; Block
0x1003a7d4  call    ds:__imp__free
0x1003a7da  add     esp, 4
0x1003a7dd  mov     eax, esi
0x1003a7df  pop     edi
0x1003a7e0  pop     esi
0x1003a7e1  pop     ebx
0x1003a7e2  mov     esp, ebp
0x1003a7e4  pop     ebp
0x1003a7e5  retn    20h ; ' '
```
