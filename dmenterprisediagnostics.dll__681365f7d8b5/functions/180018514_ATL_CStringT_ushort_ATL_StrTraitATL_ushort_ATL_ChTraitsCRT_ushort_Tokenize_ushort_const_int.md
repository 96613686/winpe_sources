# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x180018514`
- end: `0x1800185d4`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `192`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011618`
- `0x1800195c0`

## callees

- `0x180008044`
- `0x1800092fc`
- `0x18000acd0`
- `0x1800166bc`
- `0x180018514`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x18001855c`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x18001855c`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18001857e`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18001857e`

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
    || (v10 = wcsspn((const wchar_t *)(v7 + 2LL * *a4), L";"),
        v11 = (const wchar_t *)(v8 + 2LL * v10),
        (unsigned __int64)v11 >= v9) )
  {
    *a4 = -1;
    Manager = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetManager(a1);
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a2, Manager);
  }
  else
  {
    v12 = wcscspn(v11, L";");
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
0x180018514  push    rbx
0x180018516  push    rbp
0x180018517  push    rsi
0x180018518  push    rdi
0x180018519  push    r14
0x18001851b  push    r15
0x18001851d  sub     rsp, 38h
0x180018521  mov     rdi, r9
0x180018524  mov     rbx, rdx
0x180018527  mov     r14, rcx
0x18001852a  cmp     dword ptr [r9], 0
0x18001852e  jge     short loc_18001853B
0x180018530  mov     ecx, 80070057h; int
0x180018535  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001853b  mov     rcx, [rcx]
0x18001853e  movsxd  rax, dword ptr [r9]
0x180018541  lea     rsi, [rcx+rax*2]
0x180018545  movsxd  rax, dword ptr [rcx-10h]
0x180018549  lea     rbp, [rcx+rax*2]
0x18001854d  cmp     rsi, rbp
0x180018550  jnb     short loc_1800185A8
0x180018552  lea     rdx, Control; ";"
0x180018559  mov     rcx, rsi; String
0x18001855c  call    cs:__imp_wcsspn
0x180018563  nop     dword ptr [rax+rax+00h]
0x180018568  mov     r15, rax
0x18001856b  movsxd  rcx, eax
0x18001856e  lea     rcx, [rsi+rcx*2]; String
0x180018572  cmp     rcx, rbp
0x180018575  jnb     short loc_1800185A8
0x180018577  lea     rdx, Control; ";"
0x18001857e  call    cs:__imp_wcscspn
0x180018585  nop     dword ptr [rax+rax+00h]
0x18001858a  mov     r8d, [rdi]
0x18001858d  add     r8d, r15d
0x180018590  lea     ecx, [rax+1]
0x180018593  add     ecx, r8d
0x180018596  mov     [rdi], ecx
0x180018598  mov     r9d, eax
0x18001859b  mov     rdx, rbx
0x18001859e  mov     rcx, r14
0x1800185a1  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1800185a6  jmp     short loc_1800185C3
0x1800185a8  mov     dword ptr [rdi], 0FFFFFFFFh
0x1800185ae  mov     rcx, r14
0x1800185b1  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x1800185b6  nop
0x1800185b7  mov     rdx, rax
0x1800185ba  mov     rcx, rbx
0x1800185bd  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x1800185c2  nop
0x1800185c3  mov     rax, rbx
0x1800185c6  add     rsp, 38h
0x1800185ca  pop     r15
0x1800185cc  pop     r14
0x1800185ce  pop     rdi
0x1800185cf  pop     rsi
0x1800185d0  pop     rbp
0x1800185d1  pop     rbx
0x1800185d2  retn
```
