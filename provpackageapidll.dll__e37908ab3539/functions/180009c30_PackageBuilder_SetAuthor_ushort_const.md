# PackageBuilder::SetAuthor(ushort const *)

- ea: `0x180009c30`
- end: `0x180009d1f`
- name: `?SetAuthor@PackageBuilder@@EEAAJPEBG@Z`
- size: `239`
- prototype: `__int64 __fastcall(PackageBuilder *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180005424`
- `0x180006014`
- `0x180009c30`

## string_xrefs

- `0x180009d0b`: `    Failed to copy author string`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetAuthor(PackageBuilder *this, const unsigned __int16 *a2)
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
  v10 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v8;
  if ( v10 )
    operator delete(v10, v9);
  v11 = (unsigned __int16 *)*((_QWORD *)this + 5);
  if ( !v11 )
  {
    v12 = -2147024882;
    v17 = -2147024882;
    v15 = 98;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetAuthor",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to allocate _spAuthor.get()");
    return v12;
  }
  v14 = StringCchCopyW(v11, v5, a2);
  v12 = v14;
  if ( v14 < 0 )
  {
    v18 = v14;
    v16 = 101;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetAuthor",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v16,
      v18);
    ProvPackageLog(3u, L"    Failed to copy author string");
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x180009c30  push    rbx
0x180009c32  push    rbp
0x180009c33  push    rsi
0x180009c34  push    rdi
0x180009c35  sub     rsp, 38h
0x180009c39  mov     rdi, rcx
0x180009c3c  mov     rbx, rdx
0x180009c3f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009c43  mov     rax, rcx
0x180009c46  xor     ebp, ebp
0x180009c48  inc     rax
0x180009c4b  cmp     [rdx+rax*2], bp
0x180009c4f  jnz     short loc_180009C48
0x180009c51  lea     rsi, [rax+1]
0x180009c55  mov     eax, 2
0x180009c5a  mul     rsi
0x180009c5d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009c64  cmovb   rax, rcx
0x180009c68  mov     rcx, rax; unsigned __int64
0x180009c6b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009c70  mov     rcx, [rdi+28h]; void *
0x180009c74  mov     [rdi+28h], rax
0x180009c78  test    rcx, rcx
0x180009c7b  jz      short loc_180009C82
0x180009c7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009c82  mov     rcx, [rdi+28h]; unsigned __int16 *
0x180009c86  test    rcx, rcx
0x180009c89  jnz     short loc_180009CCD
0x180009c8b  lea     ebx, [rcx+3]
0x180009c8e  mov     edi, 8007000Eh
0x180009c93  mov     [rsp+58h+var_30], edi
0x180009c97  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009c9e  mov     ecx, ebx
0x180009ca0  mov     [rsp+58h+var_38], 62h ; 'b'
0x180009ca8  lea     r8, aPackagebuilder_2; "PackageBuilder::SetAuthor"
0x180009caf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009cb6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009cbb  lea     rdx, aFailedToAlloca_29; "    Failed to allocate _spAuthor.get()"
0x180009cc2  mov     ecx, ebx
0x180009cc4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009cc9  mov     eax, edi
0x180009ccb  jmp     short loc_180009D16
0x180009ccd  mov     r8, rbx; unsigned __int16 *
0x180009cd0  mov     rdx, rsi; unsigned __int64
0x180009cd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009cd8  mov     edi, eax
0x180009cda  test    eax, eax
0x180009cdc  jns     short loc_180009D14
0x180009cde  mov     [rsp+58h+var_30], eax
0x180009ce2  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009ce9  mov     ebx, 3
0x180009cee  mov     [rsp+58h+var_38], 65h ; 'e'
0x180009cf6  mov     ecx, ebx
0x180009cf8  lea     r8, aPackagebuilder_2; "PackageBuilder::SetAuthor"
0x180009cff  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009d06  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009d0b  lea     rdx, aFailedToCopyAu; "    Failed to copy author string"
0x180009d12  jmp     short loc_180009CC2
0x180009d14  xor     eax, eax
0x180009d16  add     rsp, 38h
0x180009d1a  pop     rdi
0x180009d1b  pop     rsi
0x180009d1c  pop     rbp
0x180009d1d  pop     rbx
0x180009d1e  retn
```
