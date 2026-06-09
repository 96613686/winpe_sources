# CContextMenuExt::_PopulateSyncMenu(HMENU__ *)

- ea: `0x1800164e8`
- end: `0x18001666f`
- name: `?_PopulateSyncMenu@CContextMenuExt@@AEAAJPEAUHMENU__@@@Z`
- size: `391`
- prototype: `int(CContextMenuExt *__hidden this, HMENU)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014920`

## callees

- `0x1800164e8`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180016534`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180016534`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x18001658a`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x18001658a`
- `USER32!GetMenuItemCount` at `0x180016604`
- `USER32!GetMenuItemCount` at `0x180016604`
- `USER32!InsertMenuW` at `0x180016623`
- `USER32!InsertMenuW` at `0x180016623`

## pseudocode

```c
__int64 __fastcall CContextMenuExt::_PopulateSyncMenu(CContextMenuExt *this, HMENU a2)
{
  HRESULT v2; // ebx
  IUnknown **v3; // rsi
  IUnknown *v6; // rcx
  UINT MenuItemCount; // ebx
  BOOL inserted; // eax
  __int64 v9; // r8
  void *v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v3 = (IUnknown **)((char *)this + 56);
  if ( *((_QWORD *)this + 7) || !*((_QWORD *)this + 6) )
    goto LABEL_16;
  v11 = 0;
  v2 = SHCoCreateInstance(0, &CLSID_EnumExplorerCommandOnMenu, 0, &GUID_974fc285_a627_490d_a293_0f5e8ab987fe, &v11);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, *((_QWORD *)this + 6));
    if ( v2 >= 0 )
    {
      v2 = (**(__int64 (__fastcall ***)(void *, GUID *, IUnknown **))v11)(
             v11,
             &GUID_000214e4_0000_0000_c000_000000000046,
             v3);
      if ( v2 >= 0 )
      {
        IUnknown_SetSite(*v3, *((IUnknown **)this + 3));
        v6 = *v3;
        v12 = 0;
        v2 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v6->lpVtbl->QueryInterface)(
               v6,
               &GUID_000214e8_0000_0000_c000_000000000046,
               &v12);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 24LL))(
                 v12,
                 0,
                 *((_QWORD *)this + 5),
                 0);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v2 >= 0 )
    {
LABEL_16:
      if ( *v3 )
      {
        MenuItemCount = GetMenuItemCount(a2);
        inserted = InsertMenuW(a2, MenuItemCount, 0xC00u, 0, 0);
        v9 = MenuItemCount + 1;
        if ( !inserted )
          v9 = MenuItemCount;
        return ((unsigned int (__fastcall *)(IUnknown *, HMENU, __int64, _QWORD, _DWORD, _DWORD))(*v3)->lpVtbl[1].QueryInterface)(
                 *v3,
                 a2,
                 v9,
                 *((unsigned int *)this + 51),
                 *((_DWORD *)this + 52),
                 0);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800164e8  mov     r11, rsp
0x1800164eb  mov     [r11+10h], rbx
0x1800164ef  push    rbp
0x1800164f0  push    rsi
0x1800164f1  push    rdi
0x1800164f2  sub     rsp, 40h
0x1800164f6  xor     ebx, ebx
0x1800164f8  lea     rsi, [rcx+38h]
0x1800164fc  mov     rbp, rdx
0x1800164ff  mov     rdi, rcx
0x180016502  cmp     [rsi], rbx
0x180016505  jnz     loc_1800165FB
0x18001650b  cmp     [rcx+30h], rbx
0x18001650f  jz      loc_1800165FB
0x180016515  lea     rax, [r11+8]
0x180016519  mov     [r11+8], rbx
0x18001651d  lea     r9, _GUID_974fc285_a627_490d_a293_0f5e8ab987fe; riid
0x180016524  mov     [r11-38h], rax
0x180016528  xor     r8d, r8d; pUnkOuter
0x18001652b  lea     rdx, CLSID_EnumExplorerCommandOnMenu; pclsid
0x180016532  xor     ecx, ecx; pszCLSID
0x180016534  call    cs:__imp_SHCoCreateInstance
0x18001653a  mov     ebx, eax
0x18001653c  test    eax, eax
0x18001653e  js      loc_180016660
0x180016544  mov     rcx, [rsp+58h+arg_0]
0x180016549  mov     rdx, [rdi+30h]
0x18001654d  mov     rax, [rcx]
0x180016550  mov     rax, [rax+18h]
0x180016554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016559  mov     ebx, eax
0x18001655b  test    eax, eax
0x18001655d  js      loc_1800165E6
0x180016563  mov     rcx, [rsp+58h+arg_0]
0x180016568  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x18001656f  mov     r8, rsi
0x180016572  mov     rax, [rcx]
0x180016575  mov     rax, [rax]
0x180016578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001657d  mov     ebx, eax
0x18001657f  test    eax, eax
0x180016581  js      short loc_1800165E6
0x180016583  mov     rdx, [rdi+18h]; punkSite
0x180016587  mov     rcx, [rsi]; punk
0x18001658a  call    cs:__imp_IUnknown_SetSite
0x180016590  mov     rcx, [rsi]
0x180016593  lea     r8, [rsp+58h+arg_10]
0x180016598  mov     [rsp+58h+arg_10], 0
0x1800165a1  lea     rdx, _GUID_000214e8_0000_0000_c000_000000000046
0x1800165a8  mov     rax, [rcx]
0x1800165ab  mov     rax, [rax]
0x1800165ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165b3  mov     ebx, eax
0x1800165b5  test    eax, eax
0x1800165b7  js      short loc_1800165E6
0x1800165b9  mov     rcx, [rsp+58h+arg_10]
0x1800165be  xor     r9d, r9d
0x1800165c1  mov     r8, [rdi+28h]
0x1800165c5  xor     edx, edx
0x1800165c7  mov     rax, [rcx]
0x1800165ca  mov     rax, [rax+18h]
0x1800165ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165d3  mov     rcx, [rsp+58h+arg_10]
0x1800165d8  mov     ebx, eax
0x1800165da  mov     rax, [rcx]
0x1800165dd  mov     rax, [rax+10h]
0x1800165e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165e6  mov     rcx, [rsp+58h+arg_0]
0x1800165eb  mov     rax, [rcx]
0x1800165ee  mov     rax, [rax+10h]
0x1800165f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165f7  test    ebx, ebx
0x1800165f9  js      short loc_180016660
0x1800165fb  cmp     qword ptr [rsi], 0
0x1800165ff  jz      short loc_180016660
0x180016601  mov     rcx, rbp; hMenu
0x180016604  call    cs:__imp_GetMenuItemCount
0x18001660a  xor     r9d, r9d; uIDNewItem
0x18001660d  mov     [rsp+58h+lpNewItem], 0; lpNewItem
0x180016616  mov     edx, eax; uPosition
0x180016618  mov     r8d, 0C00h; uFlags
0x18001661e  mov     rcx, rbp; hMenu
0x180016621  mov     ebx, eax
0x180016623  call    cs:__imp_InsertMenuW
0x180016629  mov     edx, [rdi+0D0h]
0x18001662f  lea     r8d, [rbx+1]
0x180016633  mov     rcx, [rsi]
0x180016636  test    eax, eax
0x180016638  mov     r9d, [rdi+0CCh]
0x18001663f  mov     [rsp+58h+var_30], 0
0x180016647  cmovz   r8d, ebx
0x18001664b  mov     dword ptr [rsp+58h+lpNewItem], edx
0x18001664f  mov     rdx, rbp
0x180016652  mov     rax, [rcx]
0x180016655  mov     rax, [rax+18h]
0x180016659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001665e  mov     ebx, eax
0x180016660  mov     eax, ebx
0x180016662  mov     rbx, [rsp+58h+arg_8]
0x180016667  add     rsp, 40h
0x18001666b  pop     rdi
0x18001666c  pop     rsi
0x18001666d  pop     rbp
0x18001666e  retn
```
