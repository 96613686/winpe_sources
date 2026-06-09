# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(ushort)

- ea: `0x1800055c0`
- end: `0x18000569e`
- name: `?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@G@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fb40`

## callees

- `0x1800055c0`
- `0x1800056a4`
- `0x180005cb4`
- `0x180005cec`
- `0x18002d064`

## import_xrefs

- `msvcrt!memmove_s` at `0x180005674`
- `msvcrt!memmove_s` at `0x180005674`

## pseudocode

```c
void *const *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(
        void *const *a1)
{
  _WORD *v2; // rcx
  __int16 v3; // ax
  _WORD *v4; // rdx
  _WORD *v5; // rax
  _WORD *v6; // rax
  _WORD *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rdi
  unsigned int v10; // ebx
  errno_t v11; // eax

  v2 = *a1;
  v3 = *v2;
  if ( *v2 )
  {
    v4 = 0;
    do
    {
      if ( v3 == 92 )
      {
        v5 = v2;
        if ( v4 )
          v5 = v4;
        v4 = v5;
      }
      else
      {
        v4 = 0;
      }
      v3 = *++v2;
    }
    while ( *v2 );
    if ( v4 )
      ATL::CSimpleStringT<unsigned short,0>::Truncate(a1, ((char *)v4 - (char *)*a1) >> 1);
  }
  v6 = *a1;
  v7 = *a1;
  if ( **(_WORD **)a1 == 92 )
  {
    do
      ++v7;
    while ( *v7 == 92 );
    if ( v7 != v6 )
    {
      v8 = *((unsigned int *)v6 - 4);
      v9 = v7 - v6;
      if ( (int)((*((_DWORD *)v6 - 3) - v8) | (1 - *((_DWORD *)v6 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v8);
      v10 = *((_DWORD *)*a1 - 4) - v9;
      v11 = memmove_s(*a1, 2LL * (int)(v10 + 1), (char *)*a1 + 2 * (int)v9, 2LL * (int)(v10 + 1));
      ATL::AtlCrtErrorCheck(v11);
      ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v10);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800055c0  mov     [rsp+arg_0], rbx
0x1800055c5  mov     [rsp+arg_8], rsi
0x1800055ca  push    rdi
0x1800055cb  sub     rsp, 20h
0x1800055cf  mov     rsi, rcx
0x1800055d2  xor     r8d, r8d
0x1800055d5  mov     rcx, [rcx]
0x1800055d8  mov     ebx, 5Ch ; '\'
0x1800055dd  movzx   eax, word ptr [rcx]
0x1800055e0  test    ax, ax
0x1800055e3  jz      short loc_18000561E
0x1800055e5  mov     edx, r8d
0x1800055e8  cmp     ax, bx
0x1800055eb  jnz     short loc_1800055FC
0x1800055ed  test    rdx, rdx
0x1800055f0  mov     rax, rcx
0x1800055f3  cmovnz  rax, rdx
0x1800055f7  mov     rdx, rax
0x1800055fa  jmp     short loc_1800055FF
0x1800055fc  mov     rdx, r8
0x1800055ff  add     rcx, 2
0x180005603  movzx   eax, word ptr [rcx]
0x180005606  test    ax, ax
0x180005609  jnz     short loc_1800055E8
0x18000560b  test    rdx, rdx
0x18000560e  jz      short loc_18000561E
0x180005610  sub     rdx, [rsi]
0x180005613  mov     rcx, rsi
0x180005616  sar     rdx, 1
0x180005619  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18000561e  mov     rax, [rsi]
0x180005621  mov     rdi, rax
0x180005624  cmp     bx, [rax]
0x180005627  jnz     short loc_18000568B
0x180005629  add     rdi, 2
0x18000562d  cmp     bx, [rdi]
0x180005630  jz      short loc_180005629
0x180005632  cmp     rdi, rax
0x180005635  jz      short loc_18000568B
0x180005637  mov     edx, [rax-10h]
0x18000563a  sub     rdi, rax
0x18000563d  mov     ecx, 1
0x180005642  sar     rdi, 1
0x180005645  sub     ecx, [rax-8]
0x180005648  mov     eax, [rax-0Ch]
0x18000564b  sub     eax, edx
0x18000564d  or      ecx, eax
0x18000564f  jge     short loc_180005659
0x180005651  mov     rcx, rsi
0x180005654  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180005659  mov     rcx, [rsi]; Destination
0x18000565c  mov     ebx, [rcx-10h]
0x18000565f  sub     ebx, edi
0x180005661  lea     eax, [rbx+1]
0x180005664  movsxd  rdx, eax
0x180005667  movsxd  rax, edi
0x18000566a  add     rdx, rdx; DestinationSize
0x18000566d  mov     r9, rdx; SourceSize
0x180005670  lea     r8, [rcx+rax*2]; Source
0x180005674  call    cs:__imp_memmove_s
0x18000567a  mov     ecx, eax; int
0x18000567c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005681  mov     edx, ebx
0x180005683  mov     rcx, rsi
0x180005686  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18000568b  mov     rbx, [rsp+28h+arg_0]
0x180005690  mov     rax, rsi
0x180005693  mov     rsi, [rsp+28h+arg_8]
0x180005698  add     rsp, 20h
0x18000569c  pop     rdi
0x18000569d  retn
```
