# CCscItemFolder::_AddNameToPropertyStore(IOfflineFilesItem *,IPropertyStore *)

- ea: `0x180038610`
- end: `0x1800386c7`
- name: `?_AddNameToPropertyStore@CCscItemFolder@@AEAAJPEAUIOfflineFilesItem@@PEAUIPropertyStore@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(CCscItemFolder *__hidden this, struct IOfflineFilesItem *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039254`

## callees

- `0x180037c80`
- `0x180038610`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathIsUNCServerW` at `0x180038658`
- `SHLWAPI!PathIsUNCServerW` at `0x180038658`
- `SHLWAPI!PathFindFileNameW` at `0x18003866e`
- `SHLWAPI!PathFindFileNameW` at `0x18003866e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800386a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800386a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386b4`

## pseudocode

```c
__int64 __fastcall CCscItemFolder::_AddNameToPropertyStore(
        const WCHAR *this,
        struct IOfflineFilesItem *a2,
        struct IPropertyStore *a3)
{
  struct IOfflineFilesItemVtbl *lpVtbl; // rax
  int inited; // ebx
  const unsigned __int16 *FileNameW; // rax
  struct tagPROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF
  LPCWSTR pszPath; // [rsp+50h] [rbp+8h] BYREF

  pszPath = this;
  lpVtbl = a2->lpVtbl;
  pszPath = 0;
  inited = ((__int64 (__fastcall *)(struct IOfflineFilesItem *, LPCWSTR *))lpVtbl->GetPath)(a2, &pszPath);
  if ( inited >= 0 )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PathIsUNCServerW(pszPath) )
      FileNameW = pszPath;
    else
      FileNameW = PathFindFileNameW(pszPath);
    inited = InitPropVariantFromString(FileNameW, &pvar);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, struct tagPROPVARIANT *))a3->lpVtbl->SetValue)(
                 a3,
                 &PKEY_ItemNameDisplay,
                 &pvar);
      PropVariantClear((PROPVARIANT *)&pvar);
    }
    CoTaskMemFree((LPVOID)pszPath);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180038610  mov     r11, rsp
0x180038613  mov     [r11+10h], rbx
0x180038617  mov     [r11+8], rcx
0x18003861b  push    rdi
0x18003861c  sub     rsp, 40h
0x180038620  mov     rax, [rdx]
0x180038623  mov     rcx, rdx
0x180038626  lea     rdx, [r11+8]
0x18003862a  mov     qword ptr [r11+8], 0
0x180038632  mov     rdi, r8
0x180038635  mov     rax, [rax+20h]
0x180038639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003863e  mov     ebx, eax
0x180038640  test    eax, eax
0x180038642  js      short loc_1800386BA
0x180038644  mov     rcx, [rsp+48h+pszPath]; pszPath
0x180038649  xorps   xmm0, xmm0
0x18003864c  xor     eax, eax
0x18003864e  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180038653  mov     [rsp+48h+var_18], rax
0x180038658  call    cs:__imp_PathIsUNCServerW
0x18003865e  test    eax, eax
0x180038660  jz      short loc_180038669
0x180038662  mov     rax, [rsp+48h+pszPath]
0x180038667  jmp     short loc_180038674
0x180038669  mov     rcx, [rsp+48h+pszPath]; pszPath
0x18003866e  call    cs:__imp_PathFindFileNameW
0x180038674  lea     rdx, [rsp+48h+pvar]; struct tagPROPVARIANT *
0x180038679  mov     rcx, rax; Source
0x18003867c  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180038681  mov     ebx, eax
0x180038683  test    eax, eax
0x180038685  js      short loc_1800386AF
0x180038687  mov     rax, [rdi]
0x18003868a  lea     r8, [rsp+48h+pvar]
0x18003868f  lea     rdx, PKEY_ItemNameDisplay
0x180038696  mov     rcx, rdi
0x180038699  mov     rax, [rax+30h]
0x18003869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386a2  lea     rcx, [rsp+48h+pvar]; pvar
0x1800386a7  mov     ebx, eax
0x1800386a9  call    cs:__imp_PropVariantClear
0x1800386af  mov     rcx, [rsp+48h+pszPath]; pv
0x1800386b4  call    cs:__imp_CoTaskMemFree
0x1800386ba  mov     eax, ebx
0x1800386bc  mov     rbx, [rsp+48h+arg_8]
0x1800386c1  add     rsp, 40h
0x1800386c5  pop     rdi
0x1800386c6  retn
```
