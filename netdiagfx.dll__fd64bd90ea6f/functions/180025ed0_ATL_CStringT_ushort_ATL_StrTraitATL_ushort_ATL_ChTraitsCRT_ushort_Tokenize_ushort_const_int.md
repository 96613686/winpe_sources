# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x180025ed0`
- end: `0x180025f83`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024d80`

## callees

- `0x1800056f4`
- `0x180005c18`
- `0x18000641c`
- `0x180025234`
- `0x180025ed0`

## import_xrefs

- `msvcrt!wcscspn` at `0x180025f34`
- `msvcrt!wcscspn` at `0x180025f34`
- `msvcrt!wcsspn` at `0x180025f18`
- `msvcrt!wcsspn` at `0x180025f18`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int *a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rbp
  int v10; // r15d
  const wchar_t *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 Manager; // rax

  if ( *a4 < 0 )
    ATL::AtlThrowImpl(-2147024809);
  v7 = *a1;
  v8 = v7 + 2LL * *a4;
  v9 = v7 + 2LL * *(int *)(v7 - 16);
  if ( v8 >= v9
    || (v10 = wcsspn((const wchar_t *)(v7 + 2LL * *a4), L"."),
        v11 = (const wchar_t *)(v8 + 2LL * v10),
        (unsigned __int64)v11 >= v9) )
  {
    *a4 = -1;
    Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(a1);
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, Manager);
  }
  else
  {
    v12 = wcscspn(v11, L".");
    v13 = (unsigned int)(v10 + *a4);
    *a4 = v13 + v12 + 1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      a1,
      a2,
      v13,
      v12);
  }
  return a2;
}

```

## disassembly

```asm
0x180025ed0  push    rbx
0x180025ed2  push    rbp
0x180025ed3  push    rsi
0x180025ed4  push    rdi
0x180025ed5  push    r14
0x180025ed7  push    r15
0x180025ed9  sub     rsp, 38h
0x180025edd  mov     rdi, r9
0x180025ee0  mov     rbx, rdx
0x180025ee3  mov     r14, rcx
0x180025ee6  cmp     dword ptr [r9], 0
0x180025eea  jge     short loc_180025EF7
0x180025eec  mov     ecx, 80070057h; int
0x180025ef1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180025ef7  mov     rcx, [rcx]
0x180025efa  movsxd  rax, dword ptr [r9]
0x180025efd  lea     rsi, [rcx+rax*2]
0x180025f01  movsxd  rax, dword ptr [rcx-10h]
0x180025f05  lea     rbp, [rcx+rax*2]
0x180025f09  cmp     rsi, rbp
0x180025f0c  jnb     short loc_180025F58
0x180025f0e  lea     rdx, Control; "."
0x180025f15  mov     rcx, rsi; String
0x180025f18  call    cs:__imp_wcsspn
0x180025f1e  mov     r15, rax
0x180025f21  movsxd  rcx, eax
0x180025f24  lea     rcx, [rsi+rcx*2]; String
0x180025f28  cmp     rcx, rbp
0x180025f2b  jnb     short loc_180025F58
0x180025f2d  lea     rdx, Control; "."
0x180025f34  call    cs:__imp_wcscspn
0x180025f3a  mov     r8d, [rdi]
0x180025f3d  add     r8d, r15d
0x180025f40  lea     ecx, [rax+1]
0x180025f43  add     ecx, r8d
0x180025f46  mov     [rdi], ecx
0x180025f48  mov     r9d, eax
0x180025f4b  mov     rdx, rbx
0x180025f4e  mov     rcx, r14
0x180025f51  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180025f56  jmp     short loc_180025F73
0x180025f58  mov     dword ptr [rdi], 0FFFFFFFFh
0x180025f5e  mov     rcx, r14
0x180025f61  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x180025f66  nop
0x180025f67  mov     rdx, rax
0x180025f6a  mov     rcx, rbx
0x180025f6d  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180025f72  nop
0x180025f73  mov     rax, rbx
0x180025f76  add     rsp, 38h
0x180025f7a  pop     r15
0x180025f7c  pop     r14
0x180025f7e  pop     rdi
0x180025f7f  pop     rsi
0x180025f80  pop     rbp
0x180025f81  pop     rbx
0x180025f82  retn
```
