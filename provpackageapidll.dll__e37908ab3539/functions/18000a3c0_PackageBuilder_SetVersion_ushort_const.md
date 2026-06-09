# PackageBuilder::SetVersion(ushort const *)

- ea: `0x18000a3c0`
- end: `0x18000a4af`
- name: `?SetVersion@PackageBuilder@@EEAAJPEBG@Z`
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
- `0x18000a3c0`

## string_xrefs

- `0x18000a49b`: `    Failed to copy version string`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetVersion(PackageBuilder *this, const unsigned __int16 *a2)
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
  v10 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v8;
  if ( v10 )
    operator delete(v10, v9);
  v11 = (unsigned __int16 *)*((_QWORD *)this + 6);
  if ( !v11 )
  {
    v12 = -2147024882;
    v17 = -2147024882;
    v15 = 114;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetVersion",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to allocate _spVersion.get()");
    return v12;
  }
  v14 = StringCchCopyW(v11, v5, a2);
  v12 = v14;
  if ( v14 < 0 )
  {
    v18 = v14;
    v16 = 117;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetVersion",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v16,
      v18);
    ProvPackageLog(3u, L"    Failed to copy version string");
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a3c0  push    rbx
0x18000a3c2  push    rbp
0x18000a3c3  push    rsi
0x18000a3c4  push    rdi
0x18000a3c5  sub     rsp, 38h
0x18000a3c9  mov     rdi, rcx
0x18000a3cc  mov     rbx, rdx
0x18000a3cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a3d3  mov     rax, rcx
0x18000a3d6  xor     ebp, ebp
0x18000a3d8  inc     rax
0x18000a3db  cmp     [rdx+rax*2], bp
0x18000a3df  jnz     short loc_18000A3D8
0x18000a3e1  lea     rsi, [rax+1]
0x18000a3e5  mov     eax, 2
0x18000a3ea  mul     rsi
0x18000a3ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a3f4  cmovb   rax, rcx
0x18000a3f8  mov     rcx, rax; unsigned __int64
0x18000a3fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a400  mov     rcx, [rdi+30h]; void *
0x18000a404  mov     [rdi+30h], rax
0x18000a408  test    rcx, rcx
0x18000a40b  jz      short loc_18000A412
0x18000a40d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a412  mov     rcx, [rdi+30h]; unsigned __int16 *
0x18000a416  test    rcx, rcx
0x18000a419  jnz     short loc_18000A45D
0x18000a41b  lea     ebx, [rcx+3]
0x18000a41e  mov     edi, 8007000Eh
0x18000a423  mov     [rsp+58h+var_30], edi
0x18000a427  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a42e  mov     ecx, ebx
0x18000a430  mov     [rsp+58h+var_38], 72h ; 'r'
0x18000a438  lea     r8, aPackagebuilder_5; "PackageBuilder::SetVersion"
0x18000a43f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a446  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a44b  lea     rdx, aFailedToAlloca_17; "    Failed to allocate _spVersion.get()"
0x18000a452  mov     ecx, ebx
0x18000a454  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a459  mov     eax, edi
0x18000a45b  jmp     short loc_18000A4A6
0x18000a45d  mov     r8, rbx; unsigned __int16 *
0x18000a460  mov     rdx, rsi; unsigned __int64
0x18000a463  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a468  mov     edi, eax
0x18000a46a  test    eax, eax
0x18000a46c  jns     short loc_18000A4A4
0x18000a46e  mov     [rsp+58h+var_30], eax
0x18000a472  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000a479  mov     ebx, 3
0x18000a47e  mov     [rsp+58h+var_38], 75h ; 'u'
0x18000a486  mov     ecx, ebx
0x18000a488  lea     r8, aPackagebuilder_5; "PackageBuilder::SetVersion"
0x18000a48f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000a496  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000a49b  lea     rdx, aFailedToCopyVe; "    Failed to copy version string"
0x18000a4a2  jmp     short loc_18000A452
0x18000a4a4  xor     eax, eax
0x18000a4a6  add     rsp, 38h
0x18000a4aa  pop     rdi
0x18000a4ab  pop     rsi
0x18000a4ac  pop     rbp
0x18000a4ad  pop     rbx
0x18000a4ae  retn
```
