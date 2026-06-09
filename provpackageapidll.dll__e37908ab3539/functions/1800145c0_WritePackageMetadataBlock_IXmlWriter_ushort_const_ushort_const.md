# WritePackageMetadataBlock(IXmlWriter *,ushort const *,ushort const *)

- ea: `0x1800145c0`
- end: `0x180014766`
- name: `?WritePackageMetadataBlock@@YAJPEAUIXmlWriter@@PEBG1@Z`
- size: `422`
- prototype: `__int64 __fastcall(struct IXmlWriter *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180013c18`

## callees

- `0x180006014`
- `0x1800145c0`
- `0x180019010`

## string_xrefs

- `0x18001461b`: `    Failed to write whitespace`
- `0x1800145ff`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180014654`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800146a5`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x1800146f6`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x18001471f`: `    Failed to write full end element`
- `0x180014608`: `WritePackageMetadataBlock`
- `0x18001466a`: `WritePackageMetadataBlock`
- `0x1800146bb`: `WritePackageMetadataBlock`
- `0x18001470c`: `WritePackageMetadataBlock`
- `0x18001467d`: `    Failed to write start element`
- `0x1800146ce`: `    Failed to write value string`

## pseudocode

```c
__int64 __fastcall WritePackageMetadataBlock(
        struct IXmlWriter *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+20h] [rbp-38h]
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+28h] [rbp-30h]
  int v18; // [rsp+28h] [rbp-30h]
  int v19; // [rsp+28h] [rbp-30h]
  int v20; // [rsp+28h] [rbp-30h]

  v6 = ((__int64 (__fastcall *)(struct IXmlWriter *, const wchar_t *))a1->lpVtbl->WriteWhitespace)(a1, L"  ");
  v7 = v6;
  if ( v6 < 0 )
  {
    v17 = v6;
    v13 = 309;
LABEL_3:
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadataBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v13,
      v17);
    ProvPackageLog(3u, L"    Failed to write whitespace");
    return v7;
  }
  v9 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, const unsigned __int16 *, _QWORD))a1->lpVtbl->WriteStartElement)(
         a1,
         0,
         a2,
         0);
  v7 = v9;
  if ( v9 < 0 )
  {
    v18 = v9;
    v14 = 312;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadataBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v14,
      v18);
    ProvPackageLog(3u, L"    Failed to write start element");
    return v7;
  }
  v10 = ((__int64 (__fastcall *)(struct IXmlWriter *, const unsigned __int16 *))a1->lpVtbl->WriteString)(a1, a3);
  v7 = v10;
  if ( v10 < 0 )
  {
    v19 = v10;
    v15 = 315;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadataBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v15,
      v19);
    ProvPackageLog(3u, L"    Failed to write value string");
    return v7;
  }
  v11 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
  v7 = v11;
  if ( v11 < 0 )
  {
    v20 = v11;
    v16 = 318;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "WritePackageMetadataBlock",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v16,
      v20);
    ProvPackageLog(3u, L"    Failed to write full end element");
    return v7;
  }
  v12 = ((__int64 (__fastcall *)(struct IXmlWriter *, const unsigned __int16 *))a1->lpVtbl->WriteWhitespace)(a1, L"\n");
  v7 = v12;
  if ( v12 < 0 )
  {
    v17 = v12;
    v13 = 321;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800145c0  push    rbx
0x1800145c2  push    rbp
0x1800145c3  push    rsi
0x1800145c4  push    rdi
0x1800145c5  sub     rsp, 38h
0x1800145c9  mov     rax, [rcx]
0x1800145cc  mov     rbp, rdx
0x1800145cf  lea     rdx, asc_18001F298; "  "
0x1800145d6  mov     rsi, r8
0x1800145d9  mov     rbx, rcx
0x1800145dc  mov     rax, [rax+0F0h]
0x1800145e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145e8  mov     edi, eax
0x1800145ea  test    eax, eax
0x1800145ec  jns     short loc_180014630
0x1800145ee  mov     [rsp+58h+var_30], eax
0x1800145f2  mov     [rsp+58h+var_38], 135h
0x1800145fa  mov     ebx, 3
0x1800145ff  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180014606  mov     ecx, ebx
0x180014608  lea     r8, aWritepackageme; "WritePackageMetadataBlock"
0x18001460f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014616  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001461b  lea     rdx, aFailedToWriteW; "    Failed to write whitespace"
0x180014622  mov     ecx, ebx
0x180014624  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180014629  mov     eax, edi
0x18001462b  jmp     loc_18001475D
0x180014630  mov     rax, [rbx]
0x180014633  xor     r9d, r9d
0x180014636  mov     r8, rbp
0x180014639  xor     edx, edx
0x18001463b  mov     rcx, rbx
0x18001463e  mov     rax, [rax+0D8h]
0x180014645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001464a  mov     edi, eax
0x18001464c  test    eax, eax
0x18001464e  jns     short loc_180014686
0x180014650  mov     [rsp+58h+var_30], eax
0x180014654  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001465b  mov     ebx, 3
0x180014660  mov     [rsp+58h+var_38], 138h
0x180014668  mov     ecx, ebx
0x18001466a  lea     r8, aWritepackageme; "WritePackageMetadataBlock"
0x180014671  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180014678  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001467d  lea     rdx, aFailedToWriteS_0; "    Failed to write start element"
0x180014684  jmp     short loc_180014622
0x180014686  mov     rax, [rbx]
0x180014689  mov     rdx, rsi
0x18001468c  mov     rcx, rbx
0x18001468f  mov     rax, [rax+0E0h]
0x180014696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001469b  mov     edi, eax
0x18001469d  test    eax, eax
0x18001469f  jns     short loc_1800146DA
0x1800146a1  mov     [rsp+58h+var_30], eax
0x1800146a5  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800146ac  mov     ebx, 3
0x1800146b1  mov     [rsp+58h+var_38], 13Bh
0x1800146b9  mov     ecx, ebx
0x1800146bb  lea     r8, aWritepackageme; "WritePackageMetadataBlock"
0x1800146c2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800146c9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800146ce  lea     rdx, aFailedToWriteV_1; "    Failed to write value string"
0x1800146d5  jmp     loc_180014622
0x1800146da  mov     rax, [rbx]
0x1800146dd  mov     rcx, rbx
0x1800146e0  mov     rax, [rax+88h]
0x1800146e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146ec  mov     edi, eax
0x1800146ee  test    eax, eax
0x1800146f0  jns     short loc_18001472B
0x1800146f2  mov     [rsp+58h+var_30], eax
0x1800146f6  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800146fd  mov     ebx, 3
0x180014702  mov     [rsp+58h+var_38], 13Eh
0x18001470a  mov     ecx, ebx
0x18001470c  lea     r8, aWritepackageme; "WritePackageMetadataBlock"
0x180014713  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001471a  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001471f  lea     rdx, aFailedToWriteF_0; "    Failed to write full end element"
0x180014726  jmp     loc_180014622
0x18001472b  mov     rax, [rbx]
0x18001472e  lea     rdx, asc_18001AD68; "\n"
0x180014735  mov     rcx, rbx
0x180014738  mov     rax, [rax+0F0h]
0x18001473f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014744  mov     edi, eax
0x180014746  test    eax, eax
0x180014748  jns     short loc_18001475B
0x18001474a  mov     [rsp+58h+var_30], eax
0x18001474e  mov     [rsp+58h+var_38], 141h
0x180014756  jmp     loc_1800145FA
0x18001475b  xor     eax, eax
0x18001475d  add     rsp, 38h
0x180014761  pop     rdi
0x180014762  pop     rsi
0x180014763  pop     rbp
0x180014764  pop     rbx
0x180014765  retn
```
