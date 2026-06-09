# CPL_CategoryViewEnumObjects(IShellFolder2 * *,IEnumIDList * *)

- ea: `0x18001a6c4`
- end: `0x18001a797`
- name: `?CPL_CategoryViewEnumObjects@@YAJPEAPEAUIShellFolder2@@PEAPEAUIEnumIDList@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(LPVOID *ppv, struct IEnumIDList **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001aac8`

## callees

- `0x18001a6c4`
- `0x18001a984`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a725`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a725`
- `SHELL32!SHGetKnownFolderIDList` at `0x18001a700`
- `SHELL32!SHGetKnownFolderIDList` at `0x18001a700`
- `SHELL32!__imp_ILFree` at `0x18001a77f`
- `SHELL32!__imp_ILFree` at `0x18001a77f`

## pseudocode

```c
__int64 __fastcall CPL_CategoryViewEnumObjects(LPVOID *ppv, struct IEnumIDList **a2)
{
  HRESULT Instance; // ebx
  LPITEMIDLIST pidl; // [rsp+40h] [rbp+8h] BYREF

  *ppv = 0;
  *a2 = 0;
  pidl = 0;
  Instance = SHGetKnownFolderIDList(&FOLDERID_ControlPanelFolder, 0, 0, &pidl);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_ControlPanel, 0, 1u, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, ppv);
    if ( Instance >= 0 )
    {
      Instance = IUnknown_SetIDList((struct IUnknown *)*ppv, (const struct _ITEMIDLIST_ABSOLUTE *)pidl);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct IEnumIDList **))(*(_QWORD *)*ppv + 32LL))(
                     *ppv,
                     0,
                     8288,
                     a2);
      if ( Instance )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
        *ppv = 0;
      }
    }
    ILFree(pidl);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001a6c4  mov     rax, rsp
0x18001a6c7  mov     [rax+10h], rbx
0x18001a6cb  mov     [rax+18h], rsi
0x18001a6cf  push    rdi
0x18001a6d0  sub     rsp, 30h
0x18001a6d4  mov     qword ptr [rcx], 0
0x18001a6db  lea     r9, [rax+8]; ppidl
0x18001a6df  mov     qword ptr [rdx], 0
0x18001a6e6  mov     rsi, rdx
0x18001a6e9  mov     rdi, rcx
0x18001a6ec  mov     qword ptr [rax+8], 0
0x18001a6f4  xor     edx, edx; dwFlags
0x18001a6f6  lea     rcx, FOLDERID_ControlPanelFolder; rfid
0x18001a6fd  xor     r8d, r8d; hToken
0x18001a700  call    cs:__imp_SHGetKnownFolderIDList
0x18001a706  mov     ebx, eax
0x18001a708  test    eax, eax
0x18001a70a  js      short loc_18001A785
0x18001a70c  xor     edx, edx; pUnkOuter
0x18001a70e  mov     [rsp+38h+ppv], rdi; ppv
0x18001a713  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x18001a71a  lea     rcx, CLSID_ControlPanel; rclsid
0x18001a721  lea     r8d, [rdx+1]; dwClsContext
0x18001a725  call    cs:__imp_CoCreateInstance
0x18001a72b  mov     ebx, eax
0x18001a72d  test    eax, eax
0x18001a72f  js      short loc_18001A77A
0x18001a731  mov     rdx, [rsp+38h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x18001a736  mov     rcx, [rdi]; struct IUnknown *
0x18001a739  call    ?IUnknown_SetIDList@@YAJPEAUIUnknown@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z; IUnknown_SetIDList(IUnknown *,_ITEMIDLIST_ABSOLUTE const *)
0x18001a73e  mov     ebx, eax
0x18001a740  test    eax, eax
0x18001a742  js      short loc_18001A760
0x18001a744  mov     rcx, [rdi]
0x18001a747  mov     r9, rsi
0x18001a74a  xor     edx, edx
0x18001a74c  mov     r8d, 2060h
0x18001a752  mov     rax, [rcx]
0x18001a755  mov     rax, [rax+20h]
0x18001a759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a75e  mov     ebx, eax
0x18001a760  test    ebx, ebx
0x18001a762  jz      short loc_18001A77A
0x18001a764  mov     rcx, [rdi]
0x18001a767  mov     rax, [rcx]
0x18001a76a  mov     rax, [rax+10h]
0x18001a76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a773  mov     qword ptr [rdi], 0
0x18001a77a  mov     rcx, [rsp+38h+pidl]; pidl
0x18001a77f  call    cs:__imp_ILFree
0x18001a785  mov     rsi, [rsp+38h+arg_10]
0x18001a78a  mov     eax, ebx
0x18001a78c  mov     rbx, [rsp+38h+arg_8]
0x18001a791  add     rsp, 30h
0x18001a795  pop     rdi
0x18001a796  retn
```
