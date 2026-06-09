# PackageBuilder::SetPackagePath(ushort const *)

- ea: `0x18000a1e0`
- end: `0x18000a2d5`
- name: `?SetPackagePath@PackageBuilder@@EEAAJPEBG@Z`
- size: `245`
- prototype: `__int64 __fastcall(PackageBuilder *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, installer_update`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000a1e0`
- `0x18000f040`

## string_xrefs

- `0x18000a26b`: `    Failed to allocate _spPackagePath.get()`
- `0x18000a258`: `PackageBuilder::SetPackagePath`
- `0x18000a2ae`: `PackageBuilder::SetPackagePath`
- `0x18000a2c1`: `    Failed to assemble package path string`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetPackagePath(PackageBuilder *this, unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // kr00_8
  void *v8; // rax
  const struct std::nothrow_t *v9; // rdx
  void *v10; // rcx
  unsigned __int16 *v11; // rcx
  unsigned int v12; // edi
  int v14; // eax
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+28h] [rbp-30h]
  int v18; // [rsp+28h] [rbp-30h]

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = v4 + 1;
  v7 = v4 + 1;
  v6 = 2 * (v4 + 1);
  if ( !is_mul_ok(v7, 2u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v10 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v8;
  if ( v10 )
    operator delete(v10, v9);
  v11 = (unsigned __int16 *)*((_QWORD *)this + 1);
  if ( !v11 )
  {
    v12 = -2147024882;
    v17 = -2147024882;
    v15 = 32;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetPackagePath",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to allocate _spPackagePath.get()");
    return v12;
  }
  v14 = PathCchCanonicalizeEx(v11, v5, a2, PATHCCH_ALLOW_LONG_PATHS);
  v12 = v14;
  if ( v14 < 0 )
  {
    v18 = v14;
    v16 = 36;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetPackagePath",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v16,
      v18);
    ProvPackageLog(3u, L"    Failed to assemble package path string");
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a1e0  push    rbx
0x18000a1e2  push    rbp
0x18000a1e3  push    rsi
0x18000a1e4  push    rdi
0x18000a1e5  sub     rsp, 38h
0x18000a1e9  mov     rdi, rcx
0x18000a1ec  mov     rbx, rdx
0x18000a1ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a1f3  mov     rax, rcx
0x18000a1f6  xor     ebp, ebp
0x18000a1f8  inc     rax
0x18000a1fb  cmp     [rdx+rax*2], bp
0x18000a1ff  jnz     short loc_18000A1F8
0x18000a201  lea     rsi, [rax+1]
0x18000a205  mov     eax, 2
0x18000a20a  mul     rsi
0x18000a20d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a214  cmovb   rax, rcx
0x18000a218  mov     rcx, rax; unsigned __int64
0x18000a21b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a220  mov     rcx, [rdi+8]; void *
0x18000a224  mov     [rdi+8], rax
0x18000a228  test    rcx, rcx
0x18000a22b  jz      short loc_18000A232
0x18000a22d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a232  mov     rcx, [rdi+8]; unsigned __int16 *
0x18000a236  test    rcx, rcx
0x18000a239  jnz     short loc_18000A27D
0x18000a23b  lea     ebx, [rcx+3]
0x18000a23e  mov     edi, 8007000Eh
0x18000a243  mov     [rsp+58h+var_30], edi
0x18000a247  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a24e  mov     ecx, ebx
0x18000a250  mov     [rsp+58h+var_38], 20h ; ' '
0x18000a258  lea     r8, aPackagebuilder; "PackageBuilder::SetPackagePath"
0x18000a25f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a266  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a26b  lea     rdx, aFailedToAlloca_11; "    Failed to allocate _spPackagePath.g"...
0x18000a272  mov     ecx, ebx
0x18000a274  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a279  mov     eax, edi
0x18000a27b  jmp     short loc_18000A2CC
0x18000a27d  mov     r9d, 1; enum PATHCCH_OPTIONS
0x18000a283  mov     r8, rbx; unsigned __int16 *
0x18000a286  mov     rdx, rsi; unsigned __int64
0x18000a289  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18000a28e  mov     edi, eax
0x18000a290  test    eax, eax
0x18000a292  jns     short loc_18000A2CA
0x18000a294  mov     [rsp+58h+var_30], eax
0x18000a298  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a29f  mov     ebx, 3
0x18000a2a4  mov     [rsp+58h+var_38], 24h ; '$'
0x18000a2ac  mov     ecx, ebx
0x18000a2ae  lea     r8, aPackagebuilder; "PackageBuilder::SetPackagePath"
0x18000a2b5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a2bc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a2c1  lea     rdx, aFailedToAssemb_14; "    Failed to assemble package path str"...
0x18000a2c8  jmp     short loc_18000A272
0x18000a2ca  xor     eax, eax
0x18000a2cc  add     rsp, 38h
0x18000a2d0  pop     rdi
0x18000a2d1  pop     rsi
0x18000a2d2  pop     rbp
0x18000a2d3  pop     rbx
0x18000a2d4  retn
```
