# VerifyAttribute(IXmlReader *,ushort const *,ushort const *)

- ea: `0x180013290`
- end: `0x1800133ed`
- name: `?VerifyAttribute@@YAJPEAUIXmlReader@@PEBG1@Z`
- size: `349`
- prototype: `int __fastcall(struct IXmlReader *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180010438`
- `0x180011e38`
- `0x180012444`

## callees

- `0x180006014`
- `0x180013290`
- `0x180018434`
- `0x180019010`

## string_xrefs

- `0x1800132ea`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180013377`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`

## pseudocode

```c
int __fastcall VerifyAttribute(struct IXmlReader *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetLocalName)(IXmlReader *, LPCWSTR *, UINT *); // rax
  int v8; // eax
  int v9; // edi
  int result; // eax
  __int64 v11; // rbx
  __int64 v12; // rcx
  struct IXmlReaderVtbl *v13; // rax
  int v14; // eax
  int v15; // [rsp+20h] [rbp-20h]
  int v16; // [rsp+20h] [rbp-20h]
  int v17; // [rsp+28h] [rbp-18h]
  int v18; // [rsp+28h] [rbp-18h]
  wchar_t *String1; // [rsp+30h] [rbp-10h] BYREF
  wchar_t *v20; // [rsp+38h] [rbp-8h] BYREF
  size_t MaxCount; // [rsp+70h] [rbp+30h] BYREF
  size_t v22; // [rsp+88h] [rbp+48h] BYREF

  lpVtbl = a1->lpVtbl;
  String1 = 0;
  GetLocalName = lpVtbl->GetLocalName;
  LODWORD(MaxCount) = 0;
  v8 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, size_t *))GetLocalName)(a1, &String1, &MaxCount);
  v9 = v8;
  if ( v8 < 0 )
  {
    v17 = v8;
    v15 = 245;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "VerifyAttribute",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v15,
      v17);
    ProvPackageLog(3u, L"    Failed to get local name");
    return v9;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  if ( (unsigned int)MaxCount != v12 || wcsncmp_0(String1, a2, (unsigned int)MaxCount) )
    return 1;
  v13 = a1->lpVtbl;
  v20 = 0;
  LODWORD(v22) = 0;
  v14 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, size_t *))v13->GetValue)(a1, &v20, &v22);
  v9 = v14;
  if ( v14 < 0 )
  {
    v18 = v14;
    v16 = 257;
    ProvPackageLog(
      3u,
      L"%hs (%hs:%d) - 0x%08x:",
      "VerifyAttribute",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      v16,
      v18);
    ProvPackageLog(3u, L"    Failed to get value");
    return v9;
  }
  do
    ++v11;
  while ( a3[v11] );
  if ( (unsigned int)v22 != v11 )
    return 1;
  result = wcsncmp_0(v20, a3, (unsigned int)v22);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180013290  mov     [rsp-28h+arg_8], rbx
0x180013295  mov     [rsp-28h+arg_10], rsi
0x18001329a  push    rbp
0x18001329b  push    rdi
0x18001329c  push    r12
0x18001329e  push    r14
0x1800132a0  push    r15
0x1800132a2  mov     rbp, rsp
0x1800132a5  sub     rsp, 40h
0x1800132a9  mov     rax, [rcx]
0x1800132ac  mov     r15, r8
0x1800132af  mov     rsi, rdx
0x1800132b2  lea     r8, [rbp+MaxCount]
0x1800132b6  xor     r12d, r12d
0x1800132b9  lea     rdx, [rbp+String1]
0x1800132bd  mov     r14, rcx
0x1800132c0  mov     [rbp+String1], r12
0x1800132c4  mov     rax, [rax+70h]
0x1800132c8  mov     dword ptr [rbp+MaxCount], r12d
0x1800132cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d1  mov     edi, eax
0x1800132d3  test    eax, eax
0x1800132d5  jns     short loc_180013319
0x1800132d7  mov     [rsp+40h+var_18], eax
0x1800132db  lea     ebx, [r12+3]
0x1800132e0  mov     ecx, ebx
0x1800132e2  mov     [rsp+40h+var_20], 0F5h
0x1800132ea  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800132f1  lea     r8, aVerifyattribut; "VerifyAttribute"
0x1800132f8  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800132ff  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013304  lea     rdx, aFailedToGetLoc; "    Failed to get local name"
0x18001330b  mov     ecx, ebx
0x18001330d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013312  mov     eax, edi
0x180013314  jmp     loc_1800133D4
0x180013319  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001331d  mov     rcx, rbx
0x180013320  inc     rcx
0x180013323  cmp     [rsi+rcx*2], r12w
0x180013328  jnz     short loc_180013320
0x18001332a  mov     r8d, dword ptr [rbp+MaxCount]; MaxCount
0x18001332e  cmp     r8, rcx
0x180013331  jnz     loc_1800133CF
0x180013337  mov     rcx, [rbp+String1]; String1
0x18001333b  mov     rdx, rsi; String2
0x18001333e  call    wcsncmp_0
0x180013343  test    eax, eax
0x180013345  jnz     loc_1800133CF
0x18001334b  mov     rax, [r14]
0x18001334e  lea     r8, [rbp+arg_18]
0x180013352  lea     rdx, [rbp+var_8]
0x180013356  mov     [rbp+var_8], r12
0x18001335a  mov     rcx, r14
0x18001335d  mov     dword ptr [rbp+arg_18], r12d
0x180013361  mov     rax, [rax+80h]
0x180013368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001336d  mov     edi, eax
0x18001336f  test    eax, eax
0x180013371  jns     short loc_1800133AC
0x180013373  mov     [rsp+40h+var_18], eax
0x180013377  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001337e  mov     ebx, 3
0x180013383  mov     [rsp+40h+var_20], 101h
0x18001338b  mov     ecx, ebx
0x18001338d  lea     r8, aVerifyattribut; "VerifyAttribute"
0x180013394  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001339b  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800133a0  lea     rdx, aFailedToGetVal_0; "    Failed to get value"
0x1800133a7  jmp     loc_18001330B
0x1800133ac  inc     rbx
0x1800133af  cmp     [r15+rbx*2], r12w
0x1800133b4  jnz     short loc_1800133AC
0x1800133b6  mov     r8d, dword ptr [rbp+arg_18]; MaxCount
0x1800133ba  cmp     r8, rbx
0x1800133bd  jnz     short loc_1800133CF
0x1800133bf  mov     rcx, [rbp+var_8]; String1
0x1800133c3  mov     rdx, r15; String2
0x1800133c6  call    wcsncmp_0
0x1800133cb  test    eax, eax
0x1800133cd  jz      short loc_1800133D4
0x1800133cf  mov     eax, 1
0x1800133d4  lea     r11, [rsp+40h+var_s0]
0x1800133d9  mov     rbx, [r11+38h]
0x1800133dd  mov     rsi, [r11+40h]
0x1800133e1  mov     rsp, r11
0x1800133e4  pop     r15
0x1800133e6  pop     r14
0x1800133e8  pop     r12
0x1800133ea  pop     rdi
0x1800133eb  pop     rbp
0x1800133ec  retn
```
