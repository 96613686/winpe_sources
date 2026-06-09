# WriteElementBlock(IXmlWriter *,ushort const *,int)

- ea: `0x18001345c`
- end: `0x180013680`
- name: `?WriteElementBlock@@YAJPEAUIXmlWriter@@PEBGH@Z`
- size: `548`
- prototype: `__int64 __fastcall(struct IXmlWriter *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800112a4`
- `0x180013688`

## callees

- `0x180006014`
- `0x18001345c`
- `0x180019010`

## string_xrefs

- `0x1800134bf`: `    Failed to write whitespace`
- `0x1800134a3`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800134fc`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013558`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013609`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800134ac`: `WriteElementBlock`
- `0x180013512`: `WriteElementBlock`
- `0x18001356e`: `WriteElementBlock`
- `0x18001361f`: `WriteElementBlock`
- `0x180013525`: `    Failed to write element start element`
- `0x180013581`: `    Failed to write index attribute`
- `0x180013632`: `    Failed to write full end element`

## pseudocode

```c
__int64 __fastcall WriteElementBlock(struct IXmlWriter *a1, const unsigned __int16 *a2, int a3)
{
  int v5; // eax
  unsigned int v6; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+20h] [rbp-18h]
  int v16; // [rsp+28h] [rbp-10h]
  int v17; // [rsp+28h] [rbp-10h]
  int v18; // [rsp+28h] [rbp-10h]
  int v19; // [rsp+28h] [rbp-10h]

  if ( !a3 )
  {
    v5 = ((__int64 (__fastcall *)(struct IXmlWriter *, const wchar_t *))a1->lpVtbl->WriteWhitespace)(a1, L"  ");
    v6 = v5;
    if ( v5 < 0 )
    {
      v16 = v5;
      LODWORD(v14) = 208;
LABEL_4:
      ProvPackageLog(
        3u,
        L"%hs (%hs:%d) - 0x%08x:",
        "WriteElementBlock",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        v14,
        v16);
      ProvPackageLog(3u, L"    Failed to write whitespace");
      return v6;
    }
  }
  v8 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const unsigned __int16 *, _QWORD))a1->lpVtbl->WriteStartElement)(
         a1,
         0,
         L"Element",
         0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v17 = v8;
    v15 = 212;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteElementBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to write element start element");
    return v6;
  }
  v9 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const unsigned __int16 *, _QWORD, const unsigned __int16 *))a1->lpVtbl->WriteAttributeString)(
         a1,
         0,
         L"Index",
         0,
         a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    v18 = v9;
    LODWORD(v14) = 216;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteElementBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v14,
      v18);
    ProvPackageLog(3u, L"    Failed to write index attribute");
    return v6;
  }
  v10 = ((__int64 (__fastcall *)(struct IXmlWriter *, const unsigned __int16 *))a1->lpVtbl->WriteWhitespace)(a1, L"\n");
  v6 = v10;
  if ( v10 < 0 )
  {
    v16 = v10;
    LODWORD(v14) = 219;
    goto LABEL_4;
  }
  v11 = ((__int64 (__fastcall *)(struct IXmlWriter *, const wchar_t *))a1->lpVtbl->WriteWhitespace)(a1, L"  ");
  v6 = v11;
  if ( v11 < 0 )
  {
    v16 = v11;
    LODWORD(v14) = 222;
    goto LABEL_4;
  }
  v12 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = v12;
    LODWORD(v14) = 225;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WriteElementBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v14,
      v19);
    ProvPackageLog(3u, L"    Failed to write full end element");
    return v6;
  }
  v13 = ((__int64 (__fastcall *)(struct IXmlWriter *, const unsigned __int16 *))a1->lpVtbl->WriteWhitespace)(a1, L"\n");
  v6 = v13;
  if ( v13 < 0 )
  {
    v16 = v13;
    LODWORD(v14) = 228;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18001345c  mov     [rsp+arg_0], rbx
0x180013461  mov     [rsp+arg_8], rsi
0x180013466  push    rdi
0x180013467  sub     rsp, 30h
0x18001346b  mov     rsi, rdx
0x18001346e  mov     rbx, rcx
0x180013471  test    r8d, r8d
0x180013474  jnz     short loc_1800134D4
0x180013476  mov     rax, [rcx]
0x180013479  lea     rdx, asc_18001F298; "  "
0x180013480  mov     rax, [rax+0F0h]
0x180013487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001348c  mov     edi, eax
0x18001348e  test    eax, eax
0x180013490  jns     short loc_1800134D4
0x180013492  mov     [rsp+38h+var_10], eax
0x180013496  mov     dword ptr [rsp+38h+var_18], 0D0h
0x18001349e  mov     ebx, 3
0x1800134a3  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800134aa  mov     ecx, ebx
0x1800134ac  lea     r8, aWriteelementbl; "WriteElementBlock"
0x1800134b3  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800134ba  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800134bf  lea     rdx, aFailedToWriteW; "    Failed to write whitespace"
0x1800134c6  mov     ecx, ebx
0x1800134c8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800134cd  mov     eax, edi
0x1800134cf  jmp     loc_180013670
0x1800134d4  mov     rax, [rbx]
0x1800134d7  lea     r8, aElement_0; "Element"
0x1800134de  xor     r9d, r9d
0x1800134e1  xor     edx, edx
0x1800134e3  mov     rcx, rbx
0x1800134e6  mov     rax, [rax+0D8h]
0x1800134ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134f2  mov     edi, eax
0x1800134f4  test    eax, eax
0x1800134f6  jns     short loc_18001352E
0x1800134f8  mov     [rsp+38h+var_10], eax
0x1800134fc  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013503  mov     ebx, 3
0x180013508  mov     dword ptr [rsp+38h+var_18], 0D4h
0x180013510  mov     ecx, ebx
0x180013512  lea     r8, aWriteelementbl; "WriteElementBlock"
0x180013519  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180013520  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013525  lea     rdx, aFailedToWriteE_4; "    Failed to write element start eleme"...
0x18001352c  jmp     short loc_1800134C6
0x18001352e  mov     rax, [rbx]
0x180013531  lea     r8, aIndex_0; "Index"
0x180013538  xor     r9d, r9d
0x18001353b  mov     [rsp+38h+var_18], rsi
0x180013540  xor     edx, edx
0x180013542  mov     rcx, rbx
0x180013545  mov     rax, [rax+38h]
0x180013549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001354e  mov     edi, eax
0x180013550  test    eax, eax
0x180013552  jns     short loc_18001358D
0x180013554  mov     [rsp+38h+var_10], eax
0x180013558  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001355f  mov     ebx, 3
0x180013564  mov     dword ptr [rsp+38h+var_18], 0D8h
0x18001356c  mov     ecx, ebx
0x18001356e  lea     r8, aWriteelementbl; "WriteElementBlock"
0x180013575  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001357c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013581  lea     rdx, aFailedToWriteI; "    Failed to write index attribute"
0x180013588  jmp     loc_1800134C6
0x18001358d  mov     rax, [rbx]
0x180013590  lea     rdx, asc_18001AD68; "\n"
0x180013597  mov     rcx, rbx
0x18001359a  mov     rax, [rax+0F0h]
0x1800135a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135a6  mov     edi, eax
0x1800135a8  test    eax, eax
0x1800135aa  jns     short loc_1800135BD
0x1800135ac  mov     [rsp+38h+var_10], eax
0x1800135b0  mov     dword ptr [rsp+38h+var_18], 0DBh
0x1800135b8  jmp     loc_18001349E
0x1800135bd  mov     rax, [rbx]
0x1800135c0  lea     rdx, asc_18001F298; "  "
0x1800135c7  mov     rcx, rbx
0x1800135ca  mov     rax, [rax+0F0h]
0x1800135d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135d6  mov     edi, eax
0x1800135d8  test    eax, eax
0x1800135da  jns     short loc_1800135ED
0x1800135dc  mov     [rsp+38h+var_10], eax
0x1800135e0  mov     dword ptr [rsp+38h+var_18], 0DEh
0x1800135e8  jmp     loc_18001349E
0x1800135ed  mov     rax, [rbx]
0x1800135f0  mov     rcx, rbx
0x1800135f3  mov     rax, [rax+88h]
0x1800135fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135ff  mov     edi, eax
0x180013601  test    eax, eax
0x180013603  jns     short loc_18001363E
0x180013605  mov     [rsp+38h+var_10], eax
0x180013609  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013610  mov     ebx, 3
0x180013615  mov     dword ptr [rsp+38h+var_18], 0E1h
0x18001361d  mov     ecx, ebx
0x18001361f  lea     r8, aWriteelementbl; "WriteElementBlock"
0x180013626  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001362d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013632  lea     rdx, aFailedToWriteF_0; "    Failed to write full end element"
0x180013639  jmp     loc_1800134C6
0x18001363e  mov     rax, [rbx]
0x180013641  lea     rdx, asc_18001AD68; "\n"
0x180013648  mov     rcx, rbx
0x18001364b  mov     rax, [rax+0F0h]
0x180013652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013657  mov     edi, eax
0x180013659  test    eax, eax
0x18001365b  jns     short loc_18001366E
0x18001365d  mov     [rsp+38h+var_10], eax
0x180013661  mov     dword ptr [rsp+38h+var_18], 0E4h
0x180013669  jmp     loc_18001349E
0x18001366e  xor     eax, eax
0x180013670  mov     rbx, [rsp+38h+arg_0]
0x180013675  mov     rsi, [rsp+38h+arg_8]
0x18001367a  add     rsp, 30h
0x18001367e  pop     rdi
0x18001367f  retn
```
