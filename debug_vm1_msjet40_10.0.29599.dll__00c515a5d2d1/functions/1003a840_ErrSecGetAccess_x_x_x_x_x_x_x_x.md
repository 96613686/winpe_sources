# ErrSecGetAccess(x,x,x,x,x,x,x,x)

- ea: `0x1003a840`
- end: `0x1003a968`
- name: `_ErrSecGetAccess@32`
- size: `296`
- prototype: ``
- caller_count: `24`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x10013500`
- `0x100138f0`
- `0x10014450`
- `0x100155a0`
- `0x1001a570`
- `0x1001bdd0`
- `0x100240c0`
- `0x1002c8f0`
- `0x10030510`
- `0x100330a0`
- `0x10033ef0`
- `0x10036860`
- `0x10036a20`
- `0x100376f0`
- `0x10038bb0`
- `0x10039910`
- `0x1003a970`
- `0x1008baf0`
- `0x1008c700`
- `0x1009e8fa`
- `0x100a8283`
- `0x100f3768`
- `0x100f464e`
- `0x100f4e46`

## callees

- `0x1003a840`
- `0x1003c9a0`
- `0x1003cc90`
- `0x1003d260`
- `0x1003db70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003a954`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1003a954`

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
0x1003a840  mov     edi, edi
0x1003a842  push    ebp
0x1003a843  mov     ebp, esp
0x1003a845  and     esp, 0FFFFFFF8h
0x1003a848  mov     ecx, [ebp+arg_C]
0x1003a84b  sub     esp, 0Ch
0x1003a84e  push    ebx
0x1003a84f  mov     ebx, [ebp+arg_18]
0x1003a852  push    esi
0x1003a853  mov     esi, [ebp+arg_4]
0x1003a856  push    edi
0x1003a857  mov     eax, _mpdbidiiscb[esi*4]
0x1003a85e  lea     eax, [eax+eax*4]
0x1003a861  test    ecx, ecx
0x1003a863  jnz     short loc_1003A88F
0x1003a865  cmp     Src[eax*4], ecx
0x1003a86c  jnz     short loc_1003A87C
0x1003a86e  mov     eax, 0FFFFFC17h
0x1003a873  pop     edi
0x1003a874  pop     esi
0x1003a875  pop     ebx
0x1003a876  mov     esp, ebp
0x1003a878  pop     ebp
0x1003a879  retn    20h ; ' '
0x1003a87c  mov     eax, _mpdbidiiscb[esi*4]
0x1003a883  lea     eax, [eax+eax*4]
0x1003a886  mov     edi, Src[eax*4]
0x1003a88d  jmp     short loc_1003A8C0
0x1003a88f  mov     edx, [ebp+Size]
0x1003a892  shl     eax, 2
0x1003a895  mov     [esp+18h+var_4], eax
0x1003a899  mov     edi, Src[eax]
0x1003a89f  mov     [esp+18h+Block], edi
0x1003a8a3  test    edi, edi
0x1003a8a5  jz      short loc_1003A8E6
0x1003a8a7  mov     ecx, [edi+0Ch]
0x1003a8aa  mov     eax, [edi+10h]
0x1003a8ad  sub     eax, ecx
0x1003a8af  push    eax
0x1003a8b0  lea     eax, [edi+ecx]
0x1003a8b3  mov     ecx, [ebp+arg_C]
0x1003a8b6  push    eax
0x1003a8b7  call    _SecFSameSid@16; SecFSameSid(x,x,x,x)
0x1003a8bc  test    eax, eax
0x1003a8be  jz      short loc_1003A8E0
0x1003a8c0  push    [ebp+arg_1C]
0x1003a8c3  mov     ecx, [ebp+arg_0]
0x1003a8c6  mov     edx, esi
0x1003a8c8  push    ebx
0x1003a8c9  push    [ebp+arg_14]
0x1003a8cc  push    edi
0x1003a8cd  push    [ebp+arg_8]
0x1003a8d0  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1003a8d5  mov     esi, eax
0x1003a8d7  pop     edi
0x1003a8d8  pop     esi
0x1003a8d9  pop     ebx
0x1003a8da  mov     esp, ebp
0x1003a8dc  pop     ebp
0x1003a8dd  retn    20h ; ' '
0x1003a8e0  mov     ecx, [ebp+arg_C]
0x1003a8e3  mov     edx, [ebp+Size]
0x1003a8e6  cmp     edx, 2
0x1003a8e9  jnz     short loc_1003A909
0x1003a8eb  mov     eax, offset dword_1000A374
0x1003a8f0  mov     ax, [eax]
0x1003a8f3  cmp     ax, [ecx]
0x1003a8f6  jnz     short loc_1003A909
0x1003a8f8  mov     dword ptr [ebx], 0
0x1003a8fe  xor     eax, eax
0x1003a900  pop     edi
0x1003a901  pop     esi
0x1003a902  pop     ebx
0x1003a903  mov     esp, ebp
0x1003a905  pop     ebp
0x1003a906  retn    20h ; ' '
0x1003a909  lea     eax, [esp+18h+Block]
0x1003a90d  push    eax; int
0x1003a90e  push    edx; Size
0x1003a90f  mov     edx, [esp+20h+var_4]
0x1003a913  push    ecx; int
0x1003a914  mov     ecx, [ebp+arg_0]
0x1003a917  mov     edx, dword ptr (_rgiscb+0Ch)[edx]
0x1003a91d  call    _ErrSecBuildUserToken@20; ErrSecBuildUserToken(x,x,x,x,x)
0x1003a922  test    eax, eax
0x1003a924  js      short loc_1003A95F
0x1003a926  mov     edi, [esp+18h+Block]
0x1003a92a  mov     edx, offset dword_1000A374
0x1003a92f  push    2
0x1003a931  mov     ecx, edi
0x1003a933  call    _SecDeleteSidFromToken@12; SecDeleteSidFromToken(x,x,x)
0x1003a938  push    [ebp+arg_1C]
0x1003a93b  mov     ecx, [ebp+arg_0]
0x1003a93e  mov     edx, esi
0x1003a940  push    ebx
0x1003a941  push    [ebp+arg_14]
0x1003a944  push    edi
0x1003a945  push    [ebp+arg_8]
0x1003a948  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x1003a94d  mov     esi, eax
0x1003a94f  test    edi, edi
0x1003a951  jz      short loc_1003A95D
0x1003a953  push    edi; Block
0x1003a954  call    ds:__imp__free
0x1003a95a  add     esp, 4
0x1003a95d  mov     eax, esi
0x1003a95f  pop     edi
0x1003a960  pop     esi
0x1003a961  pop     ebx
0x1003a962  mov     esp, ebp
0x1003a964  pop     ebp
0x1003a965  retn    20h ; ' '
```
