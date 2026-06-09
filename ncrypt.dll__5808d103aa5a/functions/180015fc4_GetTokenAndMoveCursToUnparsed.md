# _GetTokenAndMoveCursToUnparsed

- ea: `0x180015fc4`
- end: `0x18001609d`
- name: `_GetTokenAndMoveCursToUnparsed`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009ecc`

## callees

- `0x18000e120`
- `0x180015fc4`
- `0x18001f18d`

## string_xrefs

- `0x18001607b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall GetTokenAndMoveCursToUnparsed(_WORD **a1, _DWORD *a2)
{
  _WORD *v2; // r8
  unsigned int v4; // edi
  const wchar_t *v6; // r9
  int v7; // edx
  int v8; // edx

  v2 = *a1;
  v4 = 0;
  while ( *v2 == 32 )
    ++v2;
  if ( *v2 )
  {
    v6 = v2;
    while ( *v2 != 32 && *v2 )
      ++v2;
    *v2 = 0;
    v7 = *v6;
    *a1 = v2 + 1;
    v8 = v7 - 79;
    if ( !v8 )
    {
      v8 = v6[1] - 82;
      if ( v6[1] == 82 )
        v8 = v6[2];
    }
    if ( v8 )
    {
      if ( !wcscmp_0(v6, L"AND") )
      {
        *a2 = 1;
      }
      else
      {
        *a2 = 0;
        v4 = -2146893819;
        DebugTraceError(
          2148073477LL,
          "hr",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
          725);
      }
    }
    else
    {
      *a2 = 2;
    }
  }
  else
  {
    *a2 = 3;
  }
  return v4;
}

```

## disassembly

```asm
0x180015fc4  mov     [rsp+arg_0], rbx
0x180015fc9  mov     [rsp+arg_8], rsi
0x180015fce  push    rdi
0x180015fcf  sub     rsp, 20h
0x180015fd3  mov     r8, [rcx]
0x180015fd6  xor     esi, esi
0x180015fd8  mov     rbx, rdx
0x180015fdb  mov     edi, esi
0x180015fdd  mov     dx, 20h ; ' '
0x180015fe1  movzx   eax, word ptr [r8]
0x180015fe5  cmp     ax, dx
0x180015fe8  jz      short loc_180016007
0x180015fea  test    ax, ax
0x180015fed  jnz     short loc_18001600D
0x180015fef  mov     dword ptr [rbx], 3
0x180015ff5  mov     rbx, [rsp+28h+arg_0]
0x180015ffa  mov     eax, edi
0x180015ffc  mov     rsi, [rsp+28h+arg_8]
0x180016001  add     rsp, 20h
0x180016005  pop     rdi
0x180016006  retn
0x180016007  add     r8, 2
0x18001600b  jmp     short loc_180015FE1
0x18001600d  mov     r9, r8
0x180016010  jmp     short loc_18001601B
0x180016012  test    ax, ax
0x180016015  jz      short loc_180016024
0x180016017  add     r8, 2
0x18001601b  movzx   eax, word ptr [r8]
0x18001601f  cmp     ax, dx
0x180016022  jnz     short loc_180016012
0x180016024  mov     [r8], si
0x180016028  lea     rax, [r8+2]
0x18001602c  movzx   edx, word ptr [r9]
0x180016030  mov     [rcx], rax
0x180016033  sub     edx, 4Fh ; 'O'
0x180016036  jnz     short loc_18001604C
0x180016038  movzx   edx, word ptr [r9+2]
0x18001603d  sub     edx, 52h ; 'R'
0x180016040  jnz     short loc_18001604C
0x180016042  movzx   edx, word ptr [r9+4]
0x180016047  movzx   ecx, si
0x18001604a  sub     edx, ecx
0x18001604c  test    edx, edx
0x18001604e  jnz     short loc_180016058
0x180016050  mov     dword ptr [rbx], 2
0x180016056  jmp     short loc_180015FF5
0x180016058  lea     rdx, aAnd; "AND"
0x18001605f  mov     rcx, r9; String1
0x180016062  call    wcscmp_0
0x180016067  test    eax, eax
0x180016069  jnz     short loc_180016073
0x18001606b  mov     dword ptr [rbx], 1
0x180016071  jmp     short loc_180015FF5
0x180016073  mov     r9d, 2D5h
0x180016079  mov     [rbx], esi
0x18001607b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016082  mov     ecx, 80090005h
0x180016087  lea     rdx, aHr; "hr"
0x18001608e  mov     edi, 80090005h
0x180016093  call    DebugTraceError
0x180016098  jmp     loc_180015FF5
```
