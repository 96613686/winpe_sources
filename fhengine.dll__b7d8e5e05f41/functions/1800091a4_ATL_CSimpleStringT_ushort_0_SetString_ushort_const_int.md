# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x1800091a4`
- end: `0x18000923a`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `5`
- tags: ``

## callers

- `0x18000815c`
- `0x1800081d0`
- `0x180009a80`
- `0x180009d70`
- `0x18000a21c`
- `0x18000ac60`
- `0x18000c004`
- `0x18000e078`
- `0x18000f728`
- `0x18000fde8`
- `0x18001284c`
- `0x180013e14`
- `0x1800196f8`
- `0x18001a7d0`
- `0x18001baf8`
- `0x1800236d0`
- `0x1800244e0`
- `0x180024b10`
- `0x180028280`
- `0x180028508`
- `0x18002a678`
- `0x1800304a4`
- `0x180030790`
- `0x180030aac`
- `0x180030b88`

## callees

- `0x1800042e8`
- `0x18000801c`
- `0x180008cac`
- `0x180008fd0`
- `0x1800091a4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180009214`
- `msvcrt!memmove_s` at `0x180009214`
- `msvcrt!memcpy_s` at `0x18000921f`
- `msvcrt!memcpy_s` at `0x18000921f`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r14
  char *v8; // rcx
  rsize_t v9; // rdx
  rsize_t v10; // r9

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      ATL::AtlThrowImpl(-2147024809);
    v6 = ((__int64)a2 - *a1) >> 1;
    v7 = *(unsigned int *)(*a1 - 16);
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v8 = (char *)*a1;
    v9 = 2 * v3;
    v10 = 2 * v3;
    if ( v6 > v7 )
      memcpy_s(v8, v9, a2, v10);
    else
      memmove_s(v8, v9, &v8[2 * v6], v10);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  }
}

```

## disassembly

```asm
0x1800091a4  push    rbx
0x1800091a6  push    rbp
0x1800091a7  push    rsi
0x1800091a8  push    rdi
0x1800091a9  push    r14
0x1800091ab  sub     rsp, 20h
0x1800091af  movsxd  rdi, r8d
0x1800091b2  mov     rbp, rdx
0x1800091b5  mov     rbx, rcx
0x1800091b8  test    r8d, r8d
0x1800091bb  jnz     short loc_1800091C4
0x1800091bd  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800091c2  jmp     short loc_18000922F
0x1800091c4  test    rbp, rbp
0x1800091c7  jnz     short loc_1800091D4
0x1800091c9  mov     ecx, 80070057h; int
0x1800091ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800091d4  mov     rax, [rcx]
0x1800091d7  mov     rsi, rbp
0x1800091da  sub     rsi, rax
0x1800091dd  mov     ecx, 1
0x1800091e2  sar     rsi, 1
0x1800091e5  sub     ecx, [rax-8]
0x1800091e8  mov     r14d, [rax-10h]
0x1800091ec  mov     eax, [rax-0Ch]
0x1800091ef  sub     eax, edi
0x1800091f1  or      ecx, eax
0x1800091f3  jge     short loc_1800091FF
0x1800091f5  mov     edx, edi
0x1800091f7  mov     rcx, rbx
0x1800091fa  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800091ff  mov     rcx, [rbx]; Destination
0x180009202  mov     rdx, rdi
0x180009205  add     rdx, rdx; DestinationSize
0x180009208  mov     r9, rdx; SourceSize
0x18000920b  cmp     rsi, r14
0x18000920e  ja      short loc_18000921C
0x180009210  lea     r8, [rcx+rsi*2]; Source
0x180009214  call    cs:__imp_memmove_s
0x18000921a  jmp     short loc_180009225
0x18000921c  mov     r8, rbp; Source
0x18000921f  call    cs:__imp_memcpy_s
0x180009225  mov     edx, edi
0x180009227  mov     rcx, rbx
0x18000922a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18000922f  add     rsp, 20h
0x180009233  pop     r14
0x180009235  pop     rdi
0x180009236  pop     rsi
0x180009237  pop     rbp
0x180009238  pop     rbx
0x180009239  retn
```
