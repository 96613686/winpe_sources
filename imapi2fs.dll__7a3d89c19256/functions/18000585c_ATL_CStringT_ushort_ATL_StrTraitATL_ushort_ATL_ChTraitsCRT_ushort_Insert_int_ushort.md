# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort)

- ea: `0x18000585c`
- end: `0x1800058f0`
- name: `?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHG@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f650`

## callees

- `0x18000585c`
- `0x180005cb4`
- `0x180005cec`
- `0x18002d064`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800058c2`
- `msvcrt!memmove_s` at `0x1800058c2`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
        _QWORD *a1,
        int a2)
{
  int v2; // r8d
  int v4; // eax
  int v5; // ebx
  unsigned int v6; // edi
  rsize_t v7; // r9
  _WORD *v8; // rbx
  errno_t v9; // eax

  v2 = 0;
  if ( a2 >= 0 )
    v2 = a2;
  v4 = *(_DWORD *)(*a1 - 16LL);
  v5 = v4;
  if ( v2 <= v4 )
    v5 = v2;
  v6 = v4 + 1;
  if ( ((*(_DWORD *)(*a1 - 12LL) - (v4 + 1)) | (1 - *(_DWORD *)(*a1 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v6);
  v7 = 2LL * (int)(v6 - v5);
  v8 = (_WORD *)(*a1 + 2LL * v5);
  v9 = memmove_s(v8 + 1, v7, v8, v7);
  ATL::AtlCrtErrorCheck(v9);
  *v8 = 95;
  ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v6);
  return v6;
}

```

## disassembly

```asm
0x18000585c  mov     [rsp+arg_0], rbx
0x180005861  mov     [rsp+arg_8], rsi
0x180005866  push    rdi
0x180005867  sub     rsp, 20h
0x18000586b  xor     r8d, r8d
0x18000586e  mov     rsi, rcx
0x180005871  test    edx, edx
0x180005873  cmovns  r8d, edx
0x180005877  mov     rdx, [rcx]
0x18000587a  mov     ecx, 1
0x18000587f  mov     eax, [rdx-10h]
0x180005882  cmp     r8d, eax
0x180005885  mov     ebx, eax
0x180005887  cmovle  ebx, r8d
0x18000588b  sub     ecx, [rdx-8]
0x18000588e  lea     edi, [rax+1]
0x180005891  mov     eax, [rdx-0Ch]
0x180005894  sub     eax, edi
0x180005896  or      ecx, eax
0x180005898  jge     short loc_1800058A4
0x18000589a  mov     edx, edi
0x18000589c  mov     rcx, rsi
0x18000589f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800058a4  mov     rcx, [rsi]
0x1800058a7  mov     eax, edi
0x1800058a9  sub     eax, ebx
0x1800058ab  movsxd  r8, ebx
0x1800058ae  movsxd  rdx, eax
0x1800058b1  add     rdx, rdx; DestinationSize
0x1800058b4  mov     r9, rdx; SourceSize
0x1800058b7  lea     rbx, [rcx+r8*2]
0x1800058bb  lea     rcx, [rbx+2]; Destination
0x1800058bf  mov     r8, rbx; Source
0x1800058c2  call    cs:__imp_memmove_s
0x1800058c8  mov     ecx, eax; int
0x1800058ca  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800058cf  mov     edx, edi
0x1800058d1  mov     word ptr [rbx], 5Fh ; '_'
0x1800058d6  mov     rcx, rsi
0x1800058d9  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800058de  mov     rbx, [rsp+28h+arg_0]
0x1800058e3  mov     eax, edi
0x1800058e5  mov     rsi, [rsp+28h+arg_8]
0x1800058ea  add     rsp, 20h
0x1800058ee  pop     rdi
0x1800058ef  retn
```
