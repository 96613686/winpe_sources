# Element::RetrievePayload(ushort const *,ushort const *,int)

- ea: `0x1800170d0`
- end: `0x180017255`
- name: `?RetrievePayload@Element@@EEAAJPEBG0H@Z`
- size: `389`
- prototype: `__int64 __fastcall(Element *this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180006014`
- `0x18000e060`
- `0x18000fc8c`
- `0x1800170d0`

## string_xrefs

- `0x180017176`: `    Failed to allocate spSourcePath.get()`
- `0x1800171cf`: `    Failed to assemble source path`

## pseudocode

```c
__int64 __fastcall Element::RetrievePayload(
        Element *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  unsigned __int16 *v14; // rsi
  unsigned int v15; // edi
  HRESULT v16; // eax
  const struct std::nothrow_t *v17; // rdx
  int File; // eax
  ULONG v20; // [rsp+20h] [rbp-38h]
  __int64 v21; // [rsp+20h] [rbp-38h]

  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = *((_QWORD *)this + 2);
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v9 + 2 * v10) );
  v11 = v10 + v8 + 6;
  v12 = 2 * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  if ( v13 )
  {
    v16 = PathCchCombineEx(v13, v11, *((PCWSTR *)this + 2), a2, v20);
    v15 = v16;
    if ( v16 >= 0 )
    {
      File = ExtractFile(*(void **)(*((_QWORD *)this + 1) + 16LL), v14, a3, a4);
      v15 = File;
      if ( File >= 0 )
      {
        v15 = 0;
      }
      else
      {
        LODWORD(v21) = 370;
        ProvPackageLog(
          3u,
          L"%hs (%hs:%d) - 0x%08x:",
          "Element::RetrievePayload",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
          v21,
          File);
        ProvPackageLog(3u, L"    Failed to retrieve payload");
      }
    }
    else
    {
      LODWORD(v21) = 366;
      ProvPackageLog(
        3u,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::RetrievePayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        v21,
        v16);
      ProvPackageLog(3u, L"    Failed to assemble source path");
    }
    operator delete(v14, v17);
  }
  else
  {
    v15 = -2147024882;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::RetrievePayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      363,
      -2147024882);
    ProvPackageLog(3u, L"    Failed to allocate spSourcePath.get()");
  }
  return v15;
}

```

## disassembly

```asm
0x1800170d0  mov     [rsp+arg_8], rbx
0x1800170d5  mov     [rsp+arg_10], rbp
0x1800170da  push    rsi
0x1800170db  push    rdi
0x1800170dc  push    r12
0x1800170de  push    r14
0x1800170e0  push    r15
0x1800170e2  sub     rsp, 30h
0x1800170e6  mov     r14d, r9d
0x1800170e9  mov     r15, r8
0x1800170ec  mov     rdi, rdx
0x1800170ef  mov     rbx, rcx
0x1800170f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800170f6  mov     rax, r8
0x1800170f9  xor     r12d, r12d
0x1800170fc  inc     rax
0x1800170ff  cmp     [rdx+rax*2], r12w
0x180017104  jnz     short loc_1800170FC
0x180017106  mov     rdx, [rcx+10h]
0x18001710a  mov     rcx, r8
0x18001710d  inc     rcx
0x180017110  cmp     [rdx+rcx*2], r12w
0x180017115  jnz     short loc_18001710D
0x180017117  lea     rbp, [rax+6]
0x18001711b  add     rbp, rcx
0x18001711e  mov     eax, 2
0x180017123  mul     rbp
0x180017126  cmovb   rax, r8
0x18001712a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017131  mov     rcx, rax; unsigned __int64
0x180017134  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017139  mov     rsi, rax
0x18001713c  mov     [rsp+58h+arg_0], rax
0x180017141  test    rax, rax
0x180017144  jnz     short loc_18001718A
0x180017146  mov     edi, 8007000Eh
0x18001714b  mov     [rsp+58h+var_30], edi
0x18001714f  mov     dword ptr [rsp+58h+var_38], 16Bh
0x180017157  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001715e  lea     r8, aElementRetriev; "Element::RetrievePayload"
0x180017165  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001716c  lea     ebx, [rax+3]
0x18001716f  mov     ecx, ebx
0x180017171  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017176  lea     rdx, aFailedToAlloca_3; "    Failed to allocate spSourcePath.get"...
0x18001717d  mov     ecx, ebx
0x18001717f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017184  nop
0x180017185  jmp     loc_18001723C
0x18001718a  mov     r9, rdi; pszMore
0x18001718d  mov     r8, [rbx+10h]; pszPathIn
0x180017191  mov     rdx, rbp; cchPathOut
0x180017194  mov     rcx, rsi; pszPathOut
0x180017197  call    PathCchCombineEx
0x18001719c  mov     edi, eax
0x18001719e  test    eax, eax
0x1800171a0  jns     short loc_1800171D8
0x1800171a2  mov     [rsp+58h+var_30], eax
0x1800171a6  mov     dword ptr [rsp+58h+var_38], 16Eh
0x1800171ae  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800171b5  lea     r8, aElementRetriev; "Element::RetrievePayload"
0x1800171bc  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800171c3  mov     ebx, 3
0x1800171c8  mov     ecx, ebx
0x1800171ca  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800171cf  lea     rdx, aFailedToAssemb_10; "    Failed to assemble source path"
0x1800171d6  jmp     short loc_180017228
0x1800171d8  mov     rcx, [rbx+8]
0x1800171dc  mov     r9d, r14d; int
0x1800171df  mov     r8, r15; unsigned __int16 *
0x1800171e2  mov     rdx, rsi; unsigned __int16 *
0x1800171e5  mov     rcx, [rcx+10h]; void *
0x1800171e9  call    ?ExtractFile@@YAJPEAXPEBG1H@Z; ExtractFile(void *,ushort const *,ushort const *,int)
0x1800171ee  mov     edi, eax
0x1800171f0  test    eax, eax
0x1800171f2  jns     short loc_180017231
0x1800171f4  mov     [rsp+58h+var_30], eax
0x1800171f8  mov     dword ptr [rsp+58h+var_38], 172h
0x180017200  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017207  lea     r8, aElementRetriev; "Element::RetrievePayload"
0x18001720e  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017215  mov     ebx, 3
0x18001721a  mov     ecx, ebx
0x18001721c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017221  lea     rdx, aFailedToRetrie_1; "    Failed to retrieve payload"
0x180017228  mov     ecx, ebx
0x18001722a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001722f  jmp     short loc_180017234
0x180017231  mov     edi, r12d
0x180017234  mov     rcx, rsi; void *
0x180017237  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001723c  mov     eax, edi
0x18001723e  mov     rbx, [rsp+58h+arg_8]
0x180017243  mov     rbp, [rsp+58h+arg_10]
0x180017248  add     rsp, 30h
0x18001724c  pop     r15
0x18001724e  pop     r14
0x180017250  pop     r12
0x180017252  pop     rdi
0x180017253  pop     rsi
0x180017254  retn
```
