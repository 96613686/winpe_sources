# ElementEnumerator::CreateElementEnumerator(ProvisioningPackage *,_PROVISIONINGELEMENTTYPE)

- ea: `0x18000d0c4`
- end: `0x18000d349`
- name: `?CreateElementEnumerator@ElementEnumerator@@QEAAJPEAVProvisioningPackage@@W4_PROVISIONINGELEMENTTYPE@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006f10`

## callees

- `0x1800020a8`
- `0x1800020ec`
- `0x180005424`
- `0x180006014`
- `0x18000d0c4`
- `0x18000fc8c`

## string_xrefs

- `0x18000d330`: `    Failed to assemble element search path`
- `0x18000d0f6`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d142`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d1fa`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d244`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d2cb`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d31d`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d257`: `    Failed to copy element type string`
- `0x18000d2de`: `    Failed to allocate _spElementSearchPath.get()`

## pseudocode

```c
__int64 __fastcall ElementEnumerator::CreateElementEnumerator(__int64 a1, __int64 a2, int a3)
{
  unsigned int v4; // edi
  int v6; // eax
  const unsigned __int16 *v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // kr00_8
  void *v12; // rax
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  unsigned __int16 *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  size_t v18; // rdi
  unsigned __int64 v19; // rax
  void *v20; // rax
  const struct std::nothrow_t *v21; // rdx
  void *v22; // rcx
  WCHAR *v23; // rcx
  HRESULT v24; // eax
  ULONG v25; // [rsp+20h] [rbp-38h]
  int v26; // [rsp+20h] [rbp-38h]
  int v27; // [rsp+20h] [rbp-38h]
  int v28; // [rsp+20h] [rbp-38h]
  int v29; // [rsp+20h] [rbp-38h]
  int v30; // [rsp+20h] [rbp-38h]
  __int64 v31; // [rsp+20h] [rbp-38h]
  int v32; // [rsp+28h] [rbp-30h]
  int v33; // [rsp+28h] [rbp-30h]
  int v34; // [rsp+28h] [rbp-30h]
  int v35; // [rsp+28h] [rbp-30h]
  int v36; // [rsp+28h] [rbp-30h]
  HRESULT v37; // [rsp+28h] [rbp-30h]

  if ( !a3 )
  {
    v4 = -2147024809;
    v32 = -2147024809;
    v26 = 44;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v26,
      v32);
    ProvPackageLog(3, L"    Invalid element type");
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v33 = -2147024809;
    v27 = 48;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v27,
      v33);
    ProvPackageLog(3, L"    pkg: Argument cannot be NULL");
    return v4;
  }
  *(_QWORD *)(a1 + 8) = a2;
  *(_BYTE *)(a1 + 64) = 0;
  v6 = 1;
  while ( LODWORD(qword_18001A280[2 * v6]) != a3 )
  {
    if ( (unsigned int)++v6 >= 0xC )
    {
      v7 = L"Invalid";
      goto LABEL_11;
    }
  }
  v7 = (const unsigned __int16 *)qword_18001A280[2 * v6 + 1];
LABEL_11:
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  v9 = v8 + 1;
  v11 = v8 + 1;
  v10 = 2 * (v8 + 1);
  if ( !is_mul_ok(v11, 2u) )
    v10 = -1;
  v12 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v14 = *(void **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v12;
  if ( v14 )
    operator delete(v14, v13);
  v15 = *(unsigned __int16 **)(a1 + 40);
  if ( !v15 )
  {
    v4 = -2147024882;
    v34 = -2147024882;
    v28 = 58;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v28,
      v34);
    ProvPackageLog(3, L"    Failed to allocate _spElementType.get()");
    return v4;
  }
  v16 = StringCchCopyW(v15, v9, v7);
  v4 = v16;
  if ( v16 < 0 )
  {
    v35 = v16;
    v29 = 61;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v29,
      v35);
    ProvPackageLog(3, L"    Failed to copy element type string");
    return v4;
  }
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 40) + 2 * v17) );
  v18 = v17 + 3;
  v19 = 2 * (v17 + 3);
  if ( !is_mul_ok(v17 + 3, 2u) )
    v19 = -1;
  v20 = operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
  v22 = *(void **)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v20;
  if ( v22 )
    operator delete(v22, v21);
  v23 = *(WCHAR **)(a1 + 56);
  if ( !v23 )
  {
    v4 = -2147024882;
    v36 = -2147024882;
    v30 = 66;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v30,
      v36);
    ProvPackageLog(3, L"    Failed to allocate _spElementSearchPath.get()");
    return v4;
  }
  v24 = PathCchCombineEx(v23, v18, *(PCWSTR *)(a1 + 40), L"*", v25);
  v4 = v24;
  if ( v24 < 0 )
  {
    v37 = v24;
    LODWORD(v31) = 70;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v31,
      v37);
    ProvPackageLog(3, L"    Failed to assemble element search path");
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d0c4  push    rbx
0x18000d0c6  push    rbp
0x18000d0c7  push    rsi
0x18000d0c8  push    rdi
0x18000d0c9  push    r14
0x18000d0cb  sub     rsp, 30h
0x18000d0cf  xor     ebp, ebp
0x18000d0d1  mov     rbx, rcx
0x18000d0d4  test    r8d, r8d
0x18000d0d7  jnz     short loc_18000D11E
0x18000d0d9  mov     edi, 80070057h
0x18000d0de  lea     ebx, [rbp+3]
0x18000d0e1  mov     [rsp+58h+var_30], edi
0x18000d0e5  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d0ec  mov     ecx, ebx
0x18000d0ee  mov     dword ptr [rsp+58h+var_38], 2Ch ; ','
0x18000d0f6  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d0fd  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d104  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d109  lea     rdx, aInvalidElement; "    Invalid element type"
0x18000d110  mov     ecx, ebx
0x18000d112  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d117  mov     eax, edi
0x18000d119  jmp     loc_18000D33E
0x18000d11e  test    rdx, rdx
0x18000d121  jnz     short loc_18000D15E
0x18000d123  mov     edi, 80070057h
0x18000d128  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d12f  mov     ebx, 3
0x18000d134  mov     [rsp+58h+var_30], edi
0x18000d138  mov     ecx, ebx
0x18000d13a  mov     dword ptr [rsp+58h+var_38], 30h ; '0'
0x18000d142  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d149  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d150  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d155  lea     rdx, aPkgArgumentCan; "    pkg: Argument cannot be NULL"
0x18000d15c  jmp     short loc_18000D110
0x18000d15e  mov     [rcx+8], rdx
0x18000d162  lea     rdi, qword_18001A280
0x18000d169  mov     [rcx+40h], bpl
0x18000d16d  mov     eax, 1
0x18000d172  movsxd  rcx, eax
0x18000d175  add     rcx, rcx
0x18000d178  cmp     [rdi+rcx*8], r8d
0x18000d17c  jz      short loc_18000D18E
0x18000d17e  inc     eax
0x18000d180  cmp     eax, 0Ch
0x18000d183  jb      short loc_18000D172
0x18000d185  mov     rdi, cs:off_18001A288; "Invalid"
0x18000d18c  jmp     short loc_18000D193
0x18000d18e  mov     rdi, [rdi+rcx*8+8]
0x18000d193  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000d197  mov     rax, r14
0x18000d19a  inc     rax
0x18000d19d  cmp     [rdi+rax*2], bp
0x18000d1a1  jnz     short loc_18000D19A
0x18000d1a3  lea     rsi, [rax+1]
0x18000d1a7  mov     eax, 2
0x18000d1ac  mul     rsi
0x18000d1af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d1b6  cmovb   rax, r14
0x18000d1ba  mov     rcx, rax; unsigned __int64
0x18000d1bd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d1c2  mov     rcx, [rbx+28h]; void *
0x18000d1c6  mov     [rbx+28h], rax
0x18000d1ca  test    rcx, rcx
0x18000d1cd  jz      short loc_18000D1D4
0x18000d1cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d1d4  mov     rcx, [rbx+28h]; unsigned __int16 *
0x18000d1d8  test    rcx, rcx
0x18000d1db  jnz     short loc_18000D219
0x18000d1dd  lea     ebx, [rcx+3]
0x18000d1e0  mov     edi, 8007000Eh
0x18000d1e5  mov     [rsp+58h+var_30], edi
0x18000d1e9  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d1f0  mov     ecx, ebx
0x18000d1f2  mov     dword ptr [rsp+58h+var_38], 3Ah ; ':'
0x18000d1fa  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d201  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d208  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d20d  lea     rdx, aFailedToAlloca_41; "    Failed to allocate _spElementType.g"...
0x18000d214  jmp     loc_18000D110
0x18000d219  mov     r8, rdi; unsigned __int16 *
0x18000d21c  mov     rdx, rsi; unsigned __int64
0x18000d21f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d224  mov     edi, eax
0x18000d226  test    eax, eax
0x18000d228  jns     short loc_18000D263
0x18000d22a  mov     [rsp+58h+var_30], eax
0x18000d22e  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d235  mov     ebx, 3
0x18000d23a  mov     dword ptr [rsp+58h+var_38], 3Dh ; '='
0x18000d242  mov     ecx, ebx
0x18000d244  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d24b  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d252  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d257  lea     rdx, aFailedToCopyEl; "    Failed to copy element type string"
0x18000d25e  jmp     loc_18000D110
0x18000d263  mov     r8, [rbx+28h]
0x18000d267  mov     rcx, r14
0x18000d26a  inc     rcx
0x18000d26d  cmp     [r8+rcx*2], bp
0x18000d272  jnz     short loc_18000D26A
0x18000d274  lea     rdi, [rcx+3]
0x18000d278  mov     eax, 2
0x18000d27d  mul     rdi
0x18000d280  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d287  cmovb   rax, r14
0x18000d28b  mov     rcx, rax; unsigned __int64
0x18000d28e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d293  mov     rcx, [rbx+38h]; void *
0x18000d297  mov     [rbx+38h], rax
0x18000d29b  test    rcx, rcx
0x18000d29e  jz      short loc_18000D2A5
0x18000d2a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d2a5  mov     rcx, [rbx+38h]; pszPathOut
0x18000d2a9  test    rcx, rcx
0x18000d2ac  jnz     short loc_18000D2EA
0x18000d2ae  lea     ebx, [rcx+3]
0x18000d2b1  mov     edi, 8007000Eh
0x18000d2b6  mov     [rsp+58h+var_30], edi
0x18000d2ba  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d2c1  mov     ecx, ebx
0x18000d2c3  mov     dword ptr [rsp+58h+var_38], 42h ; 'B'
0x18000d2cb  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d2d2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d2d9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d2de  lea     rdx, aFailedToAlloca_36; "    Failed to allocate _spElementSearch"...
0x18000d2e5  jmp     loc_18000D110
0x18000d2ea  mov     r8, [rbx+28h]; pszPathIn
0x18000d2ee  lea     r9, pszMore; "*"
0x18000d2f5  mov     rdx, rdi; cchPathOut
0x18000d2f8  call    PathCchCombineEx
0x18000d2fd  mov     edi, eax
0x18000d2ff  test    eax, eax
0x18000d301  jns     short loc_18000D33C
0x18000d303  mov     [rsp+58h+var_30], eax
0x18000d307  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d30e  mov     ebx, 3
0x18000d313  mov     dword ptr [rsp+58h+var_38], 46h ; 'F'
0x18000d31b  mov     ecx, ebx
0x18000d31d  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d324  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d32b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d330  lea     rdx, aFailedToAssemb_5; "    Failed to assemble element search p"...
0x18000d337  jmp     loc_18000D110
0x18000d33c  xor     eax, eax
0x18000d33e  add     rsp, 30h
0x18000d342  pop     r14
0x18000d344  pop     rdi
0x18000d345  pop     rsi
0x18000d346  pop     rbp
0x18000d347  pop     rbx
0x18000d348  retn
```
