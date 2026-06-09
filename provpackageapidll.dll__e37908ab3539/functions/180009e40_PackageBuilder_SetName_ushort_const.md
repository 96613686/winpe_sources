# PackageBuilder::SetName(ushort const *)

- ea: `0x180009e40`
- end: `0x180009f2f`
- name: `?SetName@PackageBuilder@@EEAAJPEBG@Z`
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
- `0x180009e40`

## string_xrefs

- `0x180009f1b`: `    Failed to copy name string`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetName(PackageBuilder *this, const unsigned __int16 *a2)
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
  v10 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v8;
  if ( v10 )
    operator delete(v10, v9);
  v11 = (unsigned __int16 *)*((_QWORD *)this + 2);
  if ( !v11 )
  {
    v12 = -2147024882;
    v17 = -2147024882;
    v15 = 49;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetName",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to allocate _spName.get()");
    return v12;
  }
  v14 = StringCchCopyW(v11, v5, a2);
  v12 = v14;
  if ( v14 < 0 )
  {
    v18 = v14;
    v16 = 52;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetName",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v16,
      v18);
    ProvPackageLog(3u, L"    Failed to copy name string");
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x180009e40  push    rbx
0x180009e42  push    rbp
0x180009e43  push    rsi
0x180009e44  push    rdi
0x180009e45  sub     rsp, 38h
0x180009e49  mov     rdi, rcx
0x180009e4c  mov     rbx, rdx
0x180009e4f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009e53  mov     rax, rcx
0x180009e56  xor     ebp, ebp
0x180009e58  inc     rax
0x180009e5b  cmp     [rdx+rax*2], bp
0x180009e5f  jnz     short loc_180009E58
0x180009e61  lea     rsi, [rax+1]
0x180009e65  mov     eax, 2
0x180009e6a  mul     rsi
0x180009e6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e74  cmovb   rax, rcx
0x180009e78  mov     rcx, rax; unsigned __int64
0x180009e7b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009e80  mov     rcx, [rdi+10h]; void *
0x180009e84  mov     [rdi+10h], rax
0x180009e88  test    rcx, rcx
0x180009e8b  jz      short loc_180009E92
0x180009e8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009e92  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180009e96  test    rcx, rcx
0x180009e99  jnz     short loc_180009EDD
0x180009e9b  lea     ebx, [rcx+3]
0x180009e9e  mov     edi, 8007000Eh
0x180009ea3  mov     [rsp+58h+var_30], edi
0x180009ea7  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009eae  mov     ecx, ebx
0x180009eb0  mov     [rsp+58h+var_38], 31h ; '1'
0x180009eb8  lea     r8, aPackagebuilder_7; "PackageBuilder::SetName"
0x180009ebf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009ec6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009ecb  lea     rdx, aFailedToAlloca_25; "    Failed to allocate _spName.get()"
0x180009ed2  mov     ecx, ebx
0x180009ed4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009ed9  mov     eax, edi
0x180009edb  jmp     short loc_180009F26
0x180009edd  mov     r8, rbx; unsigned __int16 *
0x180009ee0  mov     rdx, rsi; unsigned __int64
0x180009ee3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009ee8  mov     edi, eax
0x180009eea  test    eax, eax
0x180009eec  jns     short loc_180009F24
0x180009eee  mov     [rsp+58h+var_30], eax
0x180009ef2  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009ef9  mov     ebx, 3
0x180009efe  mov     [rsp+58h+var_38], 34h ; '4'
0x180009f06  mov     ecx, ebx
0x180009f08  lea     r8, aPackagebuilder_7; "PackageBuilder::SetName"
0x180009f0f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009f16  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009f1b  lea     rdx, aFailedToCopyNa; "    Failed to copy name string"
0x180009f22  jmp     short loc_180009ED2
0x180009f24  xor     eax, eax
0x180009f26  add     rsp, 38h
0x180009f2a  pop     rdi
0x180009f2b  pop     rsi
0x180009f2c  pop     rbp
0x180009f2d  pop     rbx
0x180009f2e  retn
```
