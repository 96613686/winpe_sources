# ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)

- ea: `0x140008120`
- end: `0x1400081b4`
- name: `?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z`
- size: `148`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140007f80`
- `0x140017580`
- `0x140024c30`
- `0x14003817c`
- `0x14003f580`
- `0x140045cb4`
- `0x14004b5f0`
- `0x14004f894`
- `0x140064500`
- `0x140064a80`
- `0x140064b20`

## callees

- `0x140002dd0`
- `0x140008120`
- `0x140033ab0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000817c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000817c`
- `SHLWAPI!PathCombineW` at `0x140008164`
- `SHLWAPI!PathCombineW` at `0x140008164`

## pseudocode

```c
LPWSTR __fastcall ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
        LPWSTR *a1,
        const WCHAR *a2,
        const WCHAR *a3)
{
  int v6; // eax
  __int64 v7; // rcx
  LPWSTR result; // rax

  if ( ((*((_DWORD *)*a1 - 3) - 260) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, 260);
  PathCombineW(*a1, a2, a3);
  if ( *a1 )
  {
    v6 = wcsnlen(*a1, *((int *)*a1 - 3));
    if ( v6 < 0 )
      goto LABEL_8;
  }
  else
  {
    v6 = 0;
  }
  if ( v6 > *((_DWORD *)*a1 - 3) )
LABEL_8:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v6;
  v7 = (unsigned int)v6;
  result = *a1;
  (*a1)[v7] = 0;
  return result;
}

```

## disassembly

```asm
0x140008120  mov     [rsp+arg_0], rbx
0x140008125  mov     [rsp+arg_8], rsi
0x14000812a  push    rdi
0x14000812b  sub     rsp, 20h
0x14000812f  mov     rax, [rcx]
0x140008132  mov     rsi, rdx
0x140008135  mov     r10d, 1
0x14000813b  mov     edx, 104h
0x140008140  mov     rdi, r8
0x140008143  mov     rbx, rcx
0x140008146  mov     r9d, [rax-0Ch]
0x14000814a  sub     r10d, [rax-8]
0x14000814e  sub     r9d, edx
0x140008151  or      r10d, r9d
0x140008154  jge     short loc_14000815B
0x140008156  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000815b  mov     rcx, [rbx]; pszDest
0x14000815e  mov     r8, rdi; pszFile
0x140008161  mov     rdx, rsi; pszDir
0x140008164  call    cs:__imp_PathCombineW
0x14000816a  mov     rcx, [rbx]; Source
0x14000816d  xor     edi, edi
0x14000816f  test    rcx, rcx
0x140008172  jnz     short loc_140008178
0x140008174  mov     eax, edi
0x140008176  jmp     short loc_140008186
0x140008178  movsxd  rdx, dword ptr [rcx-0Ch]; MaxCount
0x14000817c  call    cs:__imp_wcsnlen
0x140008182  test    eax, eax
0x140008184  js      short loc_1400081AA
0x140008186  mov     rcx, [rbx]
0x140008189  cmp     eax, [rcx-0Ch]
0x14000818c  jg      short loc_1400081AA
0x14000818e  mov     rsi, [rsp+28h+arg_8]
0x140008193  mov     [rcx-10h], eax
0x140008196  mov     ecx, eax
0x140008198  mov     rax, [rbx]
0x14000819b  mov     rbx, [rsp+28h+arg_0]
0x1400081a0  mov     [rax+rcx*2], di
0x1400081a4  add     rsp, 20h
0x1400081a8  pop     rdi
0x1400081a9  retn
0x1400081aa  mov     ecx, 80070057h; int
0x1400081af  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
