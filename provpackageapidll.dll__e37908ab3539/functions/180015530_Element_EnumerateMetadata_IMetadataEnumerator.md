# Element::EnumerateMetadata(IMetadataEnumerator * *)

- ea: `0x180015530`
- end: `0x1800157bc`
- name: `?EnumerateMetadata@Element@@EEAAJPEAPEAUIMetadataEnumerator@@@Z`
- size: `652`
- prototype: `__int64 __fastcall(Element *__hidden this, struct IMetadataEnumerator **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x180002084`
- `0x1800020a8`
- `0x180002110`
- `0x180006014`
- `0x18000e060`
- `0x18000e4b0`
- `0x180012444`
- `0x180015530`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015792`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180015792`

## string_xrefs

- `0x180015595`: `    Failed to get metadata temporary file`
- `0x18001576b`: `    Failed to create metadata enumerator`
- `0x18001570b`: `MetadataEnumerator::CreateMetadataEnumerator`

## pseudocode

```c
__int64 __fastcall Element::EnumerateMetadata(Element *this, struct IMetadataEnumerator **a2)
{
  int TemporaryFile; // eax
  unsigned int v5; // ebx
  const struct std::nothrow_t *v6; // rdx
  WCHAR *v7; // rcx
  WCHAR *v9; // rdi
  int File; // eax
  struct IMetadataEnumerator *v11; // rax
  struct IMetadataEnumerator *v12; // rbx
  _QWORD *v13; // rax
  unsigned int ElementMetadataKeys; // r14d
  const struct std::nothrow_t *v15; // rdx
  const struct std::nothrow_t *v16; // rdx
  __int64 v17; // [rsp+20h] [rbp-28h]
  __int64 v18; // [rsp+28h] [rbp-20h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp+18h] BYREF
  struct IMetadataEnumerator *v20; // [rsp+68h] [rbp+20h]

  lpFileName = 0;
  TemporaryFile = GetTemporaryFile((__int64)L"tem", &lpFileName);
  v5 = TemporaryFile;
  if ( TemporaryFile < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::EnumerateMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      288,
      TemporaryFile);
    ProvPackageLog(3, L"    Failed to get metadata temporary file");
    v7 = (WCHAR *)lpFileName;
    if ( !lpFileName )
      return v5;
LABEL_3:
    operator delete(v7, v6);
    return v5;
  }
  v9 = (WCHAR *)lpFileName;
  File = ExtractFile(*(void **)(*((_QWORD *)this + 1) + 16LL), *((const unsigned __int16 **)this + 5), lpFileName, 1);
  v5 = File;
  if ( File < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::EnumerateMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      292,
      File);
    ProvPackageLog(3, L"    Failed to retrieve metadata file");
LABEL_7:
    if ( !v9 )
      return v5;
    v7 = v9;
    goto LABEL_3;
  }
  *a2 = 0;
  v11 = (struct IMetadataEnumerator *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  v20 = v11;
  if ( v11 )
  {
    *(_OWORD *)v11 = 0;
    *(_QWORD *)v11 = &MetadataEnumerator::`vftable';
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    v13 = operator new(0x18u);
    *v13 = v13;
    v13[1] = v13;
    *((_QWORD *)v12 + 1) = v13;
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    v5 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::EnumerateMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      299,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate ptr");
    goto LABEL_7;
  }
  ElementMetadataKeys = GetElementMetadataKeys((char *)v12 + 8, *((_QWORD *)this + 4), v9);
  if ( (int)(ElementMetadataKeys + 0x80000000) < 0 || ElementMetadataKeys == -2147023728 )
  {
    *a2 = v12;
    DeleteFileW(v9);
    if ( v9 )
      operator delete(v9, v16);
    return 0;
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "MetadataEnumerator::CreateMetadataEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataenumerator.cpp",
      24,
      ElementMetadataKeys);
    ProvPackageLog(3, L"    Failed to get element metadata keys");
    (*(void (__fastcall **)(struct IMetadataEnumerator *))(*(_QWORD *)v12 + 8LL))(v12);
    LODWORD(v18) = ElementMetadataKeys;
    LODWORD(v17) = 306;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::EnumerateMetadata",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      v17,
      v18);
    ProvPackageLog(3, L"    Failed to create metadata enumerator");
    if ( v9 )
      operator delete(v9, v15);
    return ElementMetadataKeys;
  }
}

```

## disassembly

```asm
0x180015530  mov     rax, rsp
0x180015533  mov     [rax+8], rbx
0x180015537  mov     [rax+10h], rsi
0x18001553b  push    rdi
0x18001553c  push    r14
0x18001553e  push    r15
0x180015540  sub     rsp, 30h
0x180015544  mov     r15, rdx
0x180015547  mov     rsi, rcx
0x18001554a  mov     qword ptr [rax+18h], 0
0x180015552  lea     rdx, [rax+18h]
0x180015556  lea     rcx, aTem; "tem"
0x18001555d  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x180015562  mov     ebx, eax
0x180015564  test    eax, eax
0x180015566  jns     short loc_1800155BA
0x180015568  mov     dword ptr [rsp+48h+var_20], eax
0x18001556c  mov     dword ptr [rsp+48h+var_28], 120h
0x180015574  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001557b  lea     r8, aElementEnumera; "Element::EnumerateMetadata"
0x180015582  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015589  mov     esi, 3
0x18001558e  mov     ecx, esi
0x180015590  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015595  lea     rdx, aFailedToGetMet_2; "    Failed to get metadata temporary fi"...
0x18001559c  mov     ecx, esi
0x18001559e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800155a3  nop
0x1800155a4  mov     rcx, [rsp+48h+lpFileName]; void *
0x1800155a9  test    rcx, rcx
0x1800155ac  jz      short loc_1800155B3
0x1800155ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800155b3  mov     eax, ebx
0x1800155b5  jmp     loc_1800157A8
0x1800155ba  mov     rcx, [rsi+8]
0x1800155be  mov     r9d, 1; int
0x1800155c4  mov     rdi, [rsp+48h+lpFileName]
0x1800155c9  mov     r8, rdi; unsigned __int16 *
0x1800155cc  mov     rdx, [rsi+28h]; unsigned __int16 *
0x1800155d0  mov     rcx, [rcx+10h]; void *
0x1800155d4  call    ?ExtractFile@@YAJPEAXPEBG1H@Z; ExtractFile(void *,ushort const *,ushort const *,int)
0x1800155d9  mov     ebx, eax
0x1800155db  test    eax, eax
0x1800155dd  jns     short loc_180015625
0x1800155df  mov     dword ptr [rsp+48h+var_20], eax
0x1800155e3  mov     dword ptr [rsp+48h+var_28], 124h
0x1800155eb  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800155f2  lea     r8, aElementEnumera; "Element::EnumerateMetadata"
0x1800155f9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015600  mov     esi, 3
0x180015605  mov     ecx, esi
0x180015607  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001560c  lea     rdx, aFailedToRetrie; "    Failed to retrieve metadata file"
0x180015613  mov     ecx, esi
0x180015615  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001561a  nop
0x18001561b  test    rdi, rdi
0x18001561e  jz      short loc_1800155B3
0x180015620  mov     rcx, rdi
0x180015623  jmp     short loc_1800155AE
0x180015625  mov     qword ptr [r15], 0
0x18001562c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015633  mov     ecx, 18h; unsigned __int64
0x180015638  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001563d  mov     rbx, rax
0x180015640  mov     [rsp+48h+arg_18], rax
0x180015645  test    rax, rax
0x180015648  jz      short loc_180015681
0x18001564a  xorps   xmm0, xmm0
0x18001564d  movups  xmmword ptr [rax], xmm0
0x180015650  lea     rax, ??_7MetadataEnumerator@@6B@; const MetadataEnumerator::`vftable'
0x180015657  mov     [rbx], rax
0x18001565a  mov     qword ptr [rbx+8], 0
0x180015662  mov     qword ptr [rbx+10h], 0
0x18001566a  mov     ecx, 18h; Size
0x18001566f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015674  mov     [rax], rax
0x180015677  mov     [rax+8], rax
0x18001567b  mov     [rbx+8], rax
0x18001567f  jmp     short loc_180015683
0x180015681  xor     ebx, ebx
0x180015683  test    rbx, rbx
0x180015686  jnz     short loc_1800156C6
0x180015688  mov     ebx, 8007000Eh
0x18001568d  mov     dword ptr [rsp+48h+var_20], ebx
0x180015691  mov     dword ptr [rsp+48h+var_28], 12Bh
0x180015699  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800156a0  lea     r8, aElementEnumera; "Element::EnumerateMetadata"
0x1800156a7  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800156ae  mov     esi, 3
0x1800156b3  mov     ecx, esi
0x1800156b5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800156ba  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x1800156c1  jmp     loc_180015613
0x1800156c6  lea     rcx, [rbx+8]
0x1800156ca  mov     r8, rdi
0x1800156cd  mov     rdx, [rsi+20h]
0x1800156d1  call    ?GetElementMetadataKeys@@YAJPEAV?$list@PEBGV?$allocator@PEBG@std@@@std@@PEBG1@Z; GetElementMetadataKeys(std::list<ushort const *> *,ushort const *,ushort const *)
0x1800156d6  mov     r14d, eax
0x1800156d9  mov     eax, 80000000h
0x1800156de  lea     ecx, [r14+rax]
0x1800156e2  test    eax, ecx
0x1800156e4  jnz     loc_18001578C
0x1800156ea  cmp     r14d, 80070490h
0x1800156f1  jz      loc_18001578C
0x1800156f7  mov     dword ptr [rsp+48h+var_20], r14d
0x1800156fc  mov     dword ptr [rsp+48h+var_28], 18h
0x180015704  lea     r9, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001570b  lea     r8, aMetadataenumer_0; "MetadataEnumerator::CreateMetadataEnume"...
0x180015712  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015719  mov     esi, 3
0x18001571e  mov     ecx, esi
0x180015720  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015725  lea     rdx, aFailedToGetEle_2; "    Failed to get element metadata keys"
0x18001572c  mov     ecx, esi
0x18001572e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015733  mov     rax, [rbx]
0x180015736  mov     rcx, rbx
0x180015739  mov     rax, [rax+8]
0x18001573d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015742  mov     dword ptr [rsp+48h+var_20], r14d
0x180015747  mov     dword ptr [rsp+48h+var_28], 132h
0x18001574f  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015756  lea     r8, aElementEnumera; "Element::EnumerateMetadata"
0x18001575d  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015764  mov     ecx, esi
0x180015766  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001576b  lea     rdx, aFailedToCreate_9; "    Failed to create metadata enumerato"...
0x180015772  mov     ecx, esi
0x180015774  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015779  nop
0x18001577a  test    rdi, rdi
0x18001577d  jz      short loc_180015787
0x18001577f  mov     rcx, rdi; void *
0x180015782  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015787  mov     eax, r14d
0x18001578a  jmp     short loc_1800157A8
0x18001578c  mov     [r15], rbx
0x18001578f  mov     rcx, rdi; lpFileName
0x180015792  call    cs:__imp_DeleteFileW
0x180015798  nop
0x180015799  test    rdi, rdi
0x18001579c  jz      short loc_1800157A6
0x18001579e  mov     rcx, rdi; void *
0x1800157a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800157a6  xor     eax, eax
0x1800157a8  mov     rbx, [rsp+48h+arg_0]
0x1800157ad  mov     rsi, [rsp+48h+arg_8]
0x1800157b2  add     rsp, 30h
0x1800157b6  pop     r15
0x1800157b8  pop     r14
0x1800157ba  pop     rdi
0x1800157bb  retn
```
