# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimLeft(ushort const *)

- ea: `0x1800058f8`
- end: `0x18000599f`
- name: `?TrimLeft@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b9d4`

## callees

- `0x1800058f8`
- `0x180005cb4`
- `0x180005cec`
- `0x18002d064`

## import_xrefs

- `msvcrt!wcschr` at `0x180005919`
- `msvcrt!wcschr` at `0x180005919`
- `msvcrt!memmove_s` at `0x180005975`
- `msvcrt!memmove_s` at `0x180005975`

## pseudocode

```c
void *const *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimLeft(
        void *const *a1)
{
  wchar_t *i; // rdi
  _BYTE *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rdi
  unsigned int v6; // ebx
  errno_t v7; // eax

  for ( i = (wchar_t *)*a1; *i && wcschr(L":", *i); ++i )
    ;
  v3 = *a1;
  if ( i != *(wchar_t **)a1 )
  {
    v4 = *((unsigned int *)v3 - 4);
    v5 = ((char *)i - v3) >> 1;
    if ( (int)((*((_DWORD *)v3 - 3) - v4) | (1 - *((_DWORD *)v3 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v4);
    v6 = *((_DWORD *)*a1 - 4) - v5;
    v7 = memmove_s(*a1, 2LL * (int)(v6 + 1), (char *)*a1 + 2 * (int)v5, 2LL * (int)(v6 + 1));
    ATL::AtlCrtErrorCheck(v7);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v6);
  }
  return a1;
}

```

## disassembly

```asm
0x1800058f8  mov     [rsp+arg_0], rbx
0x1800058fd  mov     [rsp+arg_8], rsi
0x180005902  push    rdi
0x180005903  sub     rsp, 20h
0x180005907  mov     rdi, [rcx]
0x18000590a  mov     rsi, rcx
0x18000590d  jmp     short loc_180005928
0x18000590f  movzx   edx, ax; Ch
0x180005912  lea     rcx, Str; ":"
0x180005919  call    cs:__imp_wcschr
0x18000591f  test    rax, rax
0x180005922  jz      short loc_180005930
0x180005924  add     rdi, 2
0x180005928  movzx   eax, word ptr [rdi]
0x18000592b  test    ax, ax
0x18000592e  jnz     short loc_18000590F
0x180005930  mov     rax, [rsi]
0x180005933  cmp     rdi, rax
0x180005936  jz      short loc_18000598C
0x180005938  mov     edx, [rax-10h]
0x18000593b  sub     rdi, rax
0x18000593e  mov     ecx, 1
0x180005943  sar     rdi, 1
0x180005946  sub     ecx, [rax-8]
0x180005949  mov     eax, [rax-0Ch]
0x18000594c  sub     eax, edx
0x18000594e  or      ecx, eax
0x180005950  jge     short loc_18000595A
0x180005952  mov     rcx, rsi
0x180005955  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000595a  mov     rcx, [rsi]; Destination
0x18000595d  mov     ebx, [rcx-10h]
0x180005960  sub     ebx, edi
0x180005962  lea     eax, [rbx+1]
0x180005965  movsxd  rdx, eax
0x180005968  movsxd  rax, edi
0x18000596b  add     rdx, rdx; DestinationSize
0x18000596e  mov     r9, rdx; SourceSize
0x180005971  lea     r8, [rcx+rax*2]; Source
0x180005975  call    cs:__imp_memmove_s
0x18000597b  mov     ecx, eax; int
0x18000597d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005982  mov     edx, ebx
0x180005984  mov     rcx, rsi
0x180005987  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18000598c  mov     rbx, [rsp+28h+arg_0]
0x180005991  mov     rax, rsi
0x180005994  mov     rsi, [rsp+28h+arg_8]
0x180005999  add     rsp, 20h
0x18000599d  pop     rdi
0x18000599e  retn
```
