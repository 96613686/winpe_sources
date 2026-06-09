# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)

- ea: `0x180007720`
- end: `0x1800077f8`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z`
- size: `216`
- prototype: `void __fastcall(__int64 *, _WORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a360`
- `0x18000bc2c`

## callees

- `0x180007644`
- `0x180007720`
- `0x1800078d0`
- `0x18000b48c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800077aa`
- `msvcrt!memmove_s` at `0x1800077aa`
- `msvcrt!memcpy_s` at `0x1800077b5`
- `msvcrt!memcpy_s` at `0x1800077b5`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, _WORD *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rbp
  char *v7; // rcx
  rsize_t v8; // r9

  if ( !a2 )
    goto LABEL_14;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( (_DWORD)v4 )
  {
    v5 = *(unsigned int *)(*a1 - 16);
    v6 = ((__int64)a2 - *a1) >> 1;
    if ( (int)((*(_DWORD *)(*a1 - 12) - v4) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v4);
    v7 = (char *)*a1;
    v8 = 2LL * (int)v4;
    if ( v6 > v5 )
      memcpy_s(v7, v8, a2, v8);
    else
      memmove_s(v7, v8, &v7[2 * v6], v8);
    if ( (int)v4 < 0 || (int)v4 > *(_DWORD *)(*a1 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a1 - 16) = v4;
    *(_WORD *)(2LL * (int)v4 + *a1) = 0;
  }
  else
  {
LABEL_14:
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  }
}

```

## disassembly

```asm
0x180007720  push    rbx
0x180007722  push    rsi
0x180007723  push    rdi
0x180007724  sub     rsp, 20h
0x180007728  mov     rdi, rdx
0x18000772b  mov     rsi, rcx
0x18000772e  test    rdx, rdx
0x180007731  jz      loc_1800077F1
0x180007737  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000773e  xchg    ax, ax
0x180007740  inc     rbx
0x180007743  cmp     word ptr [rdx+rbx*2], 0
0x180007748  jnz     short loc_180007740
0x18000774a  test    ebx, ebx
0x18000774c  jz      loc_1800077F1
0x180007752  mov     rax, [rcx]
0x180007755  mov     ecx, 1
0x18000775a  mov     [rsp+38h+arg_0], rbp
0x18000775f  mov     rbp, rdi
0x180007762  sub     rbp, rax
0x180007765  mov     [rsp+38h+arg_8], r14
0x18000776a  mov     [rsp+38h+arg_10], r15
0x18000776f  sub     ecx, [rax-8]
0x180007772  mov     r15d, [rax-10h]
0x180007776  mov     eax, [rax-0Ch]
0x180007779  sub     eax, ebx
0x18000777b  sar     rbp, 1
0x18000777e  or      ecx, eax
0x180007780  jge     short loc_18000778C
0x180007782  mov     edx, ebx
0x180007784  mov     rcx, rsi
0x180007787  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000778c  mov     rcx, [rsi]; Destination
0x18000778f  cmp     rbp, r15
0x180007792  mov     r15, [rsp+38h+arg_10]
0x180007797  movsxd  rax, ebx
0x18000779a  lea     r14, [rax+rax]
0x18000779e  mov     r9, r14; SourceSize
0x1800077a1  mov     rdx, r14; DestinationSize
0x1800077a4  ja      short loc_1800077B2
0x1800077a6  lea     r8, [rcx+rbp*2]; Source
0x1800077aa  call    cs:__imp_memmove_s
0x1800077b0  jmp     short loc_1800077BB
0x1800077b2  mov     r8, rdi; Source
0x1800077b5  call    cs:__imp_memcpy_s
0x1800077bb  mov     rbp, [rsp+38h+arg_0]
0x1800077c0  test    ebx, ebx
0x1800077c2  js      short loc_1800077E6
0x1800077c4  mov     rax, [rsi]
0x1800077c7  cmp     ebx, [rax-0Ch]
0x1800077ca  jg      short loc_1800077E6
0x1800077cc  mov     [rax-10h], ebx
0x1800077cf  xor     ecx, ecx
0x1800077d1  mov     rax, [rsi]
0x1800077d4  mov     [r14+rax], cx
0x1800077d9  mov     r14, [rsp+38h+arg_8]
0x1800077de  add     rsp, 20h
0x1800077e2  pop     rdi
0x1800077e3  pop     rsi
0x1800077e4  pop     rbx
0x1800077e5  retn
0x1800077e6  mov     ecx, 80070057h; int
0x1800077eb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800077f1  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800077f6  jmp     short loc_1800077DE
```
