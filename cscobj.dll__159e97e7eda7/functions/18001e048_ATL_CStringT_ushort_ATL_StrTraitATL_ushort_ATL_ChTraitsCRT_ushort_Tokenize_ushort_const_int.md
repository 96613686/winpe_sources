# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)

- ea: `0x18001e048`
- end: `0x18001e0f9`
- name: `?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001dc18`
- `0x18001ef70`

## callees

- `0x18001886c`
- `0x18001c8f8`
- `0x18001d994`
- `0x18001db14`
- `0x18001e048`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x18001e090`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x18001e090`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18001e0ac`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18001e0ac`

## pseudocode

```c
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
0x18001e048  push    rbx
0x18001e04a  push    rbp
0x18001e04b  push    rsi
0x18001e04c  push    rdi
0x18001e04d  push    r14
0x18001e04f  push    r15
0x18001e051  sub     rsp, 28h
0x18001e055  cmp     dword ptr [r9], 0
0x18001e059  mov     rbx, r9
0x18001e05c  mov     rdi, rdx
0x18001e05f  mov     r14, rcx
0x18001e062  jge     short loc_18001E06F
0x18001e064  mov     ecx, 80070057h; int
0x18001e069  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e06f  mov     rcx, [rcx]
0x18001e072  movsxd  rax, dword ptr [r9]
0x18001e075  lea     rsi, [rcx+rax*2]
0x18001e079  movsxd  rax, dword ptr [rcx-10h]
0x18001e07d  lea     rbp, [rcx+rax*2]
0x18001e081  cmp     rsi, rbp
0x18001e084  jnb     short loc_18001E0D0
0x18001e086  lea     rdx, Control; ";"
0x18001e08d  mov     rcx, rsi; String
0x18001e090  call    cs:__imp_wcsspn
0x18001e096  movsxd  rcx, eax
0x18001e099  mov     r15, rax
0x18001e09c  lea     rcx, [rsi+rcx*2]; String
0x18001e0a0  cmp     rcx, rbp
0x18001e0a3  jnb     short loc_18001E0D0
0x18001e0a5  lea     rdx, Control; ";"
0x18001e0ac  call    cs:__imp_wcscspn
0x18001e0b2  mov     r8d, [rbx]
0x18001e0b5  mov     rdx, rdi
0x18001e0b8  add     r8d, r15d
0x18001e0bb  mov     r9d, eax
0x18001e0be  lea     ecx, [rax+1]
0x18001e0c1  add     ecx, r8d
0x18001e0c4  mov     [rbx], ecx
0x18001e0c6  mov     rcx, r14
0x18001e0c9  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x18001e0ce  jmp     short loc_18001E0E9
0x18001e0d0  mov     rcx, r14
0x18001e0d3  mov     dword ptr [rbx], 0FFFFFFFFh
0x18001e0d9  call    ?GetManager@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAPEAUIAtlStringMgr@2@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetManager(void)
0x18001e0de  mov     rdx, rax
0x18001e0e1  mov     rcx, rdi
0x18001e0e4  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18001e0e9  mov     rax, rdi
0x18001e0ec  add     rsp, 28h
0x18001e0f0  pop     r15
0x18001e0f2  pop     r14
0x18001e0f4  pop     rdi
0x18001e0f5  pop     rsi
0x18001e0f6  pop     rbp
0x18001e0f7  pop     rbx
0x18001e0f8  retn
```
