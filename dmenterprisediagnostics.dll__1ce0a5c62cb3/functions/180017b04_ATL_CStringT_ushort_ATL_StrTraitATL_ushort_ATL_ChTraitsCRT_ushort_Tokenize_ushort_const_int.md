# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x180017b04`
- end: `0x180017bb7`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180010e80`
- `0x180018bac`

## callees

- `0x180007cc4`
- `0x180008e80`
- `0x18000a75c`
- `0x180015cdc`
- `0x180017b04`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x180017b4c`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x180017b4c`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180017b68`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180017b68`

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
0x180017b04  push    rbx
0x180017b06  push    rbp
0x180017b07  push    rsi
0x180017b08  push    rdi
0x180017b09  push    r14
0x180017b0b  push    r15
0x180017b0d  sub     rsp, 38h
0x180017b11  mov     rdi, r9
0x180017b14  mov     rbx, rdx
0x180017b17  mov     r14, rcx
0x180017b1a  cmp     dword ptr [r9], 0
0x180017b1e  jge     short loc_180017B2B
0x180017b20  mov     ecx, 80070057h; int
0x180017b25  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017b2b  mov     rcx, [rcx]
0x180017b2e  movsxd  rax, dword ptr [r9]
0x180017b31  lea     rsi, [rcx+rax*2]
0x180017b35  movsxd  rax, dword ptr [rcx-10h]
0x180017b39  lea     rbp, [rcx+rax*2]
0x180017b3d  cmp     rsi, rbp
0x180017b40  jnb     short loc_180017B8C
0x180017b42  lea     rdx, Control; ";"
0x180017b49  mov     rcx, rsi; String
0x180017b4c  call    cs:__imp_wcsspn
0x180017b52  mov     r15, rax
0x180017b55  movsxd  rcx, eax
0x180017b58  lea     rcx, [rsi+rcx*2]; String
0x180017b5c  cmp     rcx, rbp
0x180017b5f  jnb     short loc_180017B8C
0x180017b61  lea     rdx, Control; ";"
0x180017b68  call    cs:__imp_wcscspn
0x180017b6e  mov     r8d, [rdi]
0x180017b71  add     r8d, r15d
0x180017b74  lea     ecx, [rax+1]
0x180017b77  add     ecx, r8d
0x180017b7a  mov     [rdi], ecx
0x180017b7c  mov     r9d, eax
0x180017b7f  mov     rdx, rbx
0x180017b82  mov     rcx, r14
0x180017b85  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180017b8a  jmp     short loc_180017BA7
0x180017b8c  mov     dword ptr [rdi], 0FFFFFFFFh
0x180017b92  mov     rcx, r14
0x180017b95  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x180017b9a  nop
0x180017b9b  mov     rdx, rax
0x180017b9e  mov     rcx, rbx
0x180017ba1  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180017ba6  nop
0x180017ba7  mov     rax, rbx
0x180017baa  add     rsp, 38h
0x180017bae  pop     r15
0x180017bb0  pop     r14
0x180017bb2  pop     rdi
0x180017bb3  pop     rsi
0x180017bb4  pop     rbp
0x180017bb5  pop     rbx
0x180017bb6  retn
```
