# PackageBuilder::SetDescription(ushort const *)

- ea: `0x180009d40`
- end: `0x180009e2f`
- name: `?SetDescription@PackageBuilder@@EEAAJPEBG@Z`
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
- `0x180009d40`

## string_xrefs

- `0x180009e1b`: `    Failed to copy description string`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetDescription(PackageBuilder *this, const unsigned __int16 *a2)
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
  v10 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v8;
  if ( v10 )
    operator delete(v10, v9);
  v11 = (unsigned __int16 *)*((_QWORD *)this + 3);
  if ( !v11 )
  {
    v12 = -2147024882;
    v17 = -2147024882;
    v15 = 65;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetDescription",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to allocate _spDescription.get()");
    return v12;
  }
  v14 = StringCchCopyW(v11, v5, a2);
  v12 = v14;
  if ( v14 < 0 )
  {
    v18 = v14;
    v16 = 69;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "PackageBuilder::SetDescription",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\packagebuilder.cpp",
      v16,
      v18);
    ProvPackageLog(3u, L"    Failed to copy description string");
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x180009d40  push    rbx
0x180009d42  push    rbp
0x180009d43  push    rsi
0x180009d44  push    rdi
0x180009d45  sub     rsp, 38h
0x180009d49  mov     rdi, rcx
0x180009d4c  mov     rbx, rdx
0x180009d4f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009d53  mov     rax, rcx
0x180009d56  xor     ebp, ebp
0x180009d58  inc     rax
0x180009d5b  cmp     [rdx+rax*2], bp
0x180009d5f  jnz     short loc_180009D58
0x180009d61  lea     rsi, [rax+1]
0x180009d65  mov     eax, 2
0x180009d6a  mul     rsi
0x180009d6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009d74  cmovb   rax, rcx
0x180009d78  mov     rcx, rax; unsigned __int64
0x180009d7b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009d80  mov     rcx, [rdi+18h]; void *
0x180009d84  mov     [rdi+18h], rax
0x180009d88  test    rcx, rcx
0x180009d8b  jz      short loc_180009D92
0x180009d8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009d92  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180009d96  test    rcx, rcx
0x180009d99  jnz     short loc_180009DDD
0x180009d9b  lea     ebx, [rcx+3]
0x180009d9e  mov     edi, 8007000Eh
0x180009da3  mov     [rsp+58h+var_30], edi
0x180009da7  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009dae  mov     ecx, ebx
0x180009db0  mov     [rsp+58h+var_38], 41h ; 'A'
0x180009db8  lea     r8, aPackagebuilder_4; "PackageBuilder::SetDescription"
0x180009dbf  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009dc6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009dcb  lea     rdx, aFailedToAlloca_8; "    Failed to allocate _spDescription.g"...
0x180009dd2  mov     ecx, ebx
0x180009dd4  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009dd9  mov     eax, edi
0x180009ddb  jmp     short loc_180009E26
0x180009ddd  mov     r8, rbx; unsigned __int16 *
0x180009de0  mov     rdx, rsi; unsigned __int64
0x180009de3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009de8  mov     edi, eax
0x180009dea  test    eax, eax
0x180009dec  jns     short loc_180009E24
0x180009dee  mov     [rsp+58h+var_30], eax
0x180009df2  lea     r9, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\provpackageapi"...
0x180009df9  mov     ebx, 3
0x180009dfe  mov     [rsp+58h+var_38], 45h ; 'E'
0x180009e06  mov     ecx, ebx
0x180009e08  lea     r8, aPackagebuilder_4; "PackageBuilder::SetDescription"
0x180009e0f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180009e16  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180009e1b  lea     rdx, aFailedToCopyDe; "    Failed to copy description string"
0x180009e22  jmp     short loc_180009DD2
0x180009e24  xor     eax, eax
0x180009e26  add     rsp, 38h
0x180009e2a  pop     rdi
0x180009e2b  pop     rsi
0x180009e2c  pop     rbp
0x180009e2d  pop     rbx
0x180009e2e  retn
```
