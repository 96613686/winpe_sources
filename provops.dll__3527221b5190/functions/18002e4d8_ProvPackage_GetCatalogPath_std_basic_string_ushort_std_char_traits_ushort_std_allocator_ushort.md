# ProvPackage::GetCatalogPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18002e4d8`
- end: `0x18002e622`
- name: `?GetCatalogPath@ProvPackage@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `330`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180024f80`
- `0x18002e6e0`

## callees

- `0x18000cbe4`
- `0x18001b388`
- `0x180021be4`
- `0x18002e4d8`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002e5d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e5d8`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18002e527`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18002e527`

## pseudocode

```c
_QWORD *__fastcall ProvPackage::GetCatalogPath(_QWORD *a1, __int64 a2)
{
  size_t v4; // rdx
  const WCHAR *v5; // rcx
  HRESULT Extension; // eax
  __int64 v7; // rcx
  int v9; // [rsp+20h] [rbp-38h]
  PCWSTR ppszExt[3]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  ppszExt[2] = (PCWSTR)a2;
  ppszExt[0] = 0;
  v4 = *(_QWORD *)(a2 + 16) + 1LL;
  if ( *(_QWORD *)(a2 + 24) < 8u )
    v5 = (const WCHAR *)a2;
  else
    v5 = *(const WCHAR **)a2;
  Extension = PathCchFindExtension(v5, v4, ppszExt);
  if ( Extension < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)(unsigned int)Extension,
      v9);
  v7 = -1;
  do
    ++v7;
  while ( ppszExt[0][v7] );
  std::wstring::replace((void *)a2, 4);
  std::wstring::wstring(a1, (_QWORD *)a2);
  if ( *(_QWORD *)(a2 + 24) >= 8u )
    operator delete(*(void **)a2);
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  return a1;
}

```

## disassembly

```asm
0x18002e4d8  mov     r11, rsp
0x18002e4db  mov     [r11+18h], rbx
0x18002e4df  mov     [r11+20h], rsi
0x18002e4e3  push    rdi
0x18002e4e4  sub     rsp, 50h
0x18002e4e8  mov     rax, cs:__security_cookie
0x18002e4ef  xor     rax, rsp
0x18002e4f2  mov     [rsp+58h+var_10], rax
0x18002e4f7  mov     rbx, rdx
0x18002e4fa  mov     rdi, rcx
0x18002e4fd  mov     [rsp+58h+ppszExt], rcx
0x18002e502  mov     [r11-18h], rdx
0x18002e506  xor     esi, esi
0x18002e508  mov     [r11-28h], rsi
0x18002e50c  mov     rdx, [rdx+10h]
0x18002e510  inc     rdx; cchPath
0x18002e513  cmp     qword ptr [rbx+18h], 8
0x18002e518  jb      short loc_18002E51F
0x18002e51a  mov     rcx, [rbx]
0x18002e51d  jmp     short loc_18002E522
0x18002e51f  mov     rcx, rbx; pszPath
0x18002e522  lea     r8, [rsp+58h+ppszExt]; ppszExt
0x18002e527  call    cs:__imp_PathCchFindExtension
0x18002e52d  mov     rcx, [rsp+58h]; this
0x18002e532  test    eax, eax
0x18002e534  js      loc_18002E60D
0x18002e53a  mov     rax, [rsp+58h+ppszExt]
0x18002e53f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e543  inc     rcx
0x18002e546  cmp     [rax+rcx*2], si
0x18002e54a  jnz     short loc_18002E543
0x18002e54c  cmp     qword ptr [rbx+18h], 8
0x18002e551  jb      short loc_18002E558
0x18002e553  mov     rdx, [rbx]
0x18002e556  jmp     short loc_18002E55B
0x18002e558  mov     rdx, rbx
0x18002e55b  mov     rax, [rbx+10h]
0x18002e55f  lea     r9, [rax+rax]
0x18002e563  lea     r8, [r9+rdx]
0x18002e567  jb      short loc_18002E56E
0x18002e569  mov     rdx, [rbx]
0x18002e56c  jmp     short loc_18002E571
0x18002e56e  mov     rdx, rbx
0x18002e571  lea     rax, [rcx+rcx]
0x18002e575  sub     r9, rax
0x18002e578  add     rdx, r9
0x18002e57b  test    r8, r8
0x18002e57e  jnz     short loc_18002E585
0x18002e580  mov     r8, rsi
0x18002e583  jmp     short loc_18002E58B
0x18002e585  sub     r8, rdx
0x18002e588  sar     r8, 1
0x18002e58b  cmp     qword ptr [rbx+18h], 8
0x18002e590  jb      short loc_18002E597
0x18002e592  mov     rax, [rbx]
0x18002e595  jmp     short loc_18002E59A
0x18002e597  mov     rax, rbx
0x18002e59a  test    rdx, rdx
0x18002e59d  jnz     short loc_18002E5A4
0x18002e59f  mov     rdx, rsi
0x18002e5a2  jmp     short loc_18002E5AA
0x18002e5a4  sub     rdx, rax
0x18002e5a7  sar     rdx, 1
0x18002e5aa  mov     qword ptr [rsp+58h+var_38], 4; __int64
0x18002e5b3  lea     r9, aCat; ".cat"
0x18002e5ba  mov     rcx, rbx; Src
0x18002e5bd  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x18002e5c2  mov     rdx, rbx
0x18002e5c5  mov     rcx, rdi
0x18002e5c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002e5cd  nop
0x18002e5ce  cmp     qword ptr [rbx+18h], 8
0x18002e5d3  jb      short loc_18002E5DE
0x18002e5d5  mov     rcx, [rbx]
0x18002e5d8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002e5de  mov     qword ptr [rbx+18h], 7
0x18002e5e6  mov     [rbx+10h], rsi
0x18002e5ea  mov     [rbx], si
0x18002e5ed  mov     rax, rdi
0x18002e5f0  mov     rcx, [rsp+58h+var_10]
0x18002e5f5  xor     rcx, rsp; StackCookie
0x18002e5f8  call    __security_check_cookie
0x18002e5fd  mov     rbx, [rsp+58h+arg_10]
0x18002e602  mov     rsi, [rsp+58h+arg_18]
0x18002e607  add     rsp, 50h
0x18002e60b  pop     rdi
0x18002e60c  retn
0x18002e60d  mov     r9d, eax; char *
0x18002e610  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002e617  mov     edx, 147h; void *
0x18002e61c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
