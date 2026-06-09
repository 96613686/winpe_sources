# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180007800`
- end: `0x1800078c5`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `197`
- prototype: `void __fastcall(__int64 *, const void *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180003390`
- `0x180008b30`
- `0x18000a360`
- `0x18000aa08`
- `0x18000dd60`

## callees

- `0x180007644`
- `0x180007800`
- `0x1800078d0`
- `0x18000b48c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000787e`
- `msvcrt!memmove_s` at `0x18000787e`
- `msvcrt!memcpy_s` at `0x180007889`
- `msvcrt!memcpy_s` at `0x180007889`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rbx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r15
  char *v8; // rcx
  rsize_t v9; // r9
  rsize_t v10; // rdx

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      goto LABEL_12;
    v6 = ((__int64)a2 - *a1) >> 1;
    v7 = *(unsigned int *)(*a1 - 16);
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v8 = (char *)*a1;
    v9 = 2 * v3;
    v10 = 2 * v3;
    if ( v6 > v7 )
      memcpy_s(v8, v10, a2, v9);
    else
      memmove_s(v8, v10, &v8[2 * v6], v9);
    if ( (int)v3 < 0 || (int)v3 > *(_DWORD *)(*a1 - 12) )
LABEL_12:
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a1 - 16) = v3;
    *(_WORD *)(2 * v3 + *a1) = 0;
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  }
}

```

## disassembly

```asm
0x180007800  push    rbx
0x180007802  push    rbp
0x180007803  push    rdi
0x180007804  sub     rsp, 20h
0x180007808  movsxd  rbx, r8d
0x18000780b  mov     rbp, rdx
0x18000780e  mov     rdi, rcx
0x180007811  test    r8d, r8d
0x180007814  jnz     short loc_180007820
0x180007816  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000781b  jmp     loc_1800078B2
0x180007820  mov     [rsp+38h+arg_8], r14
0x180007825  test    rbp, rbp
0x180007828  jz      loc_1800078BA
0x18000782e  mov     rax, [rcx]
0x180007831  mov     ecx, 1
0x180007836  mov     [rsp+38h+arg_0], rsi
0x18000783b  mov     rsi, rbp
0x18000783e  sub     rsi, rax
0x180007841  mov     [rsp+38h+arg_10], r15
0x180007846  sar     rsi, 1
0x180007849  sub     ecx, [rax-8]
0x18000784c  mov     r15d, [rax-10h]
0x180007850  mov     eax, [rax-0Ch]
0x180007853  sub     eax, ebx
0x180007855  or      ecx, eax
0x180007857  jge     short loc_180007863
0x180007859  mov     edx, ebx
0x18000785b  mov     rcx, rdi
0x18000785e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180007863  mov     rcx, [rdi]; Destination
0x180007866  lea     r14, [rbx+rbx]
0x18000786a  cmp     rsi, r15
0x18000786d  mov     r9, r14; SourceSize
0x180007870  mov     r15, [rsp+38h+arg_10]
0x180007875  mov     rdx, r14; DestinationSize
0x180007878  ja      short loc_180007886
0x18000787a  lea     r8, [rcx+rsi*2]; Source
0x18000787e  call    cs:__imp_memmove_s
0x180007884  jmp     short loc_18000788F
0x180007886  mov     r8, rbp; Source
0x180007889  call    cs:__imp_memcpy_s
0x18000788f  mov     rsi, [rsp+38h+arg_0]
0x180007894  test    ebx, ebx
0x180007896  js      short loc_1800078BA
0x180007898  mov     rax, [rdi]
0x18000789b  cmp     ebx, [rax-0Ch]
0x18000789e  jg      short loc_1800078BA
0x1800078a0  mov     [rax-10h], ebx
0x1800078a3  xor     ecx, ecx
0x1800078a5  mov     rax, [rdi]
0x1800078a8  mov     [r14+rax], cx
0x1800078ad  mov     r14, [rsp+38h+arg_8]
0x1800078b2  add     rsp, 20h
0x1800078b6  pop     rdi
0x1800078b7  pop     rbp
0x1800078b8  pop     rbx
0x1800078b9  retn
0x1800078ba  mov     ecx, 80070057h; int
0x1800078bf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
