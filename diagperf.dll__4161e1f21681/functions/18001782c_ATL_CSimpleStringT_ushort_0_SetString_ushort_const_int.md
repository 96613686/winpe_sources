# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18001782c`
- end: `0x1800178d5`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x1800166e0`
- `0x1800168b4`
- `0x1800169b8`
- `0x180016a1c`
- `0x180016a44`
- `0x180016c1c`
- `0x1800177b4`
- `0x1800279d8`
- `0x180039858`
- `0x18003b3f0`
- `0x180040750`
- `0x180054e78`
- `0x180054f34`
- `0x18005507c`

## callees

- `0x18001782c`
- `0x1800178dc`
- `0x180018aa4`
- `0x180039bbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800178c2`
- `msvcrt!memmove_s` at `0x1800178c2`
- `msvcrt!memcpy_s` at `0x18001788c`
- `msvcrt!memcpy_s` at `0x18001788c`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // r15
  char *v8; // rcx
  rsize_t v9; // r9
  rsize_t v10; // rdx
  __int64 result; // rax

  v3 = (int)a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1);
  if ( !a2 )
    goto LABEL_12;
  v6 = (a2 - *a1) >> 1;
  v7 = *((unsigned int *)*a1 - 4);
  if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v8 = *a1;
  v9 = 2 * v3;
  v10 = 2 * v3;
  if ( v6 <= v7 )
    memmove_s(v8, v10, &v8[2 * v6], v9);
  else
    memcpy_s(v8, v10, a2, v9);
  if ( (int)v3 < 0 || (int)v3 > *((_DWORD *)*a1 - 3) )
LABEL_12:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v3;
  result = 0;
  *(_WORD *)&(*a1)[2 * v3] = 0;
  return result;
}

```

## disassembly

```asm
0x18001782c  push    rbx
0x18001782e  push    rbp
0x18001782f  push    rsi
0x180017830  push    rdi
0x180017831  push    r14
0x180017833  push    r15
0x180017835  sub     rsp, 28h
0x180017839  movsxd  rbx, r8d
0x18001783c  mov     r14, rdx
0x18001783f  mov     rdi, rcx
0x180017842  test    r8d, r8d
0x180017845  jz      short loc_1800178B7
0x180017847  test    rdx, rdx
0x18001784a  jz      short loc_1800178CA
0x18001784c  mov     rax, [rcx]
0x18001784f  mov     rbp, rdx
0x180017852  sub     rbp, rax
0x180017855  mov     ecx, 1
0x18001785a  sar     rbp, 1
0x18001785d  sub     ecx, [rax-8]
0x180017860  mov     r15d, [rax-10h]
0x180017864  mov     eax, [rax-0Ch]
0x180017867  sub     eax, ebx
0x180017869  or      ecx, eax
0x18001786b  jge     short loc_180017877
0x18001786d  mov     edx, ebx
0x18001786f  mov     rcx, rdi
0x180017872  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180017877  mov     rcx, [rdi]; Destination
0x18001787a  lea     rsi, [rbx+rbx]
0x18001787e  mov     r9, rsi; SourceSize
0x180017881  mov     rdx, rsi; DestinationSize
0x180017884  cmp     rbp, r15
0x180017887  jbe     short loc_1800178BE
0x180017889  mov     r8, r14; Source
0x18001788c  call    cs:__imp_memcpy_s
0x180017892  test    ebx, ebx
0x180017894  js      short loc_1800178CA
0x180017896  mov     rax, [rdi]
0x180017899  cmp     ebx, [rax-0Ch]
0x18001789c  jg      short loc_1800178CA
0x18001789e  mov     [rax-10h], ebx
0x1800178a1  xor     eax, eax
0x1800178a3  mov     rcx, [rdi]
0x1800178a6  mov     [rsi+rcx], ax
0x1800178aa  add     rsp, 28h
0x1800178ae  pop     r15
0x1800178b0  pop     r14
0x1800178b2  pop     rdi
0x1800178b3  pop     rsi
0x1800178b4  pop     rbp
0x1800178b5  pop     rbx
0x1800178b6  retn
0x1800178b7  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800178bc  jmp     short loc_1800178AA
0x1800178be  lea     r8, [rcx+rbp*2]; Source
0x1800178c2  call    cs:__imp_memmove_s
0x1800178c8  jmp     short loc_180017892
0x1800178ca  mov     ecx, 80070057h; int
0x1800178cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
