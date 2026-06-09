# CFontFolderBase::_CreateDataObject(HWND__ *,uint,_ITEMIDLIST const * *,IDataObject * *)

- ea: `0x18001a0c8`
- end: `0x18001a196`
- name: `?_CreateDataObject@CFontFolderBase@@AEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@PEAPEAUIDataObject@@@Z`
- size: `206`
- prototype: `int(CFontFolderBase *__hidden this, HWND, unsigned int, const struct _ITEMIDLIST **, struct IDataObject **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016950`

## callees

- `0x180011788`
- `0x18001a0c8`
- `0x180032010`

## import_xrefs

- `SHELL32!SHGetSpecialFolderLocation` at `0x18001a106`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18001a106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a181`

## pseudocode

```c
__int64 __fastcall CFontFolderBase::_CreateDataObject(
        __int64 (__fastcall ***this)(CFontFolderBase *, GUID *, struct IDataObject ***),
        HWND a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4,
        struct IDataObject **a5)
{
  struct IDataObject **v5; // r14
  HRESULT Instance; // ebx
  __int64 (__fastcall **v11)(CFontFolderBase *, GUID *, struct IDataObject ***); // rax
  struct IDataObject *v13; // [rsp+30h] [rbp-58h]
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-48h] BYREF

  v5 = a5;
  ppidl = 0;
  *a5 = 0;
  Instance = SHGetSpecialFolderLocation(a2, 20, &ppidl);
  if ( Instance >= 0 )
  {
    v11 = *this;
    a5 = 0;
    Instance = (*v11)((CFontFolderBase *)this, &GUID_000214e6_0000_0000_c000_000000000046, &a5);
    if ( Instance >= 0 )
    {
      Instance = CFontFolderData::CreateInstance(v5, ppidl, a3, a4, a2, (struct IShellFolder *)a5, v13);
      ((void (__fastcall *)(struct IDataObject **))(*a5)[2].lpVtbl)(a5);
    }
    CoTaskMemFree(ppidl);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001a0c8  push    rbx
0x18001a0ca  push    rbp
0x18001a0cb  push    rsi
0x18001a0cc  push    rdi
0x18001a0cd  push    r14
0x18001a0cf  push    r15
0x18001a0d1  sub     rsp, 58h
0x18001a0d5  mov     r14, [rsp+88h+arg_20]
0x18001a0dd  mov     rsi, rdx
0x18001a0e0  mov     r15d, r8d
0x18001a0e3  mov     [rsp+88h+ppidl], 0
0x18001a0ec  mov     rdi, rcx
0x18001a0ef  lea     r8, [rsp+88h+ppidl]; ppidl
0x18001a0f4  mov     edx, 14h; csidl
0x18001a0f9  mov     rcx, rsi; hwnd
0x18001a0fc  mov     qword ptr [r14], 0
0x18001a103  mov     rbp, r9
0x18001a106  call    cs:__imp_SHGetSpecialFolderLocation
0x18001a10c  mov     ebx, eax
0x18001a10e  test    eax, eax
0x18001a110  js      short loc_18001A187
0x18001a112  mov     rax, [rdi]
0x18001a115  lea     r8, [rsp+88h+arg_20]
0x18001a11d  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18001a124  mov     [rsp+88h+arg_20], 0
0x18001a130  mov     rcx, rdi
0x18001a133  mov     rax, [rax]
0x18001a136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a13b  mov     ebx, eax
0x18001a13d  test    eax, eax
0x18001a13f  js      short loc_18001A17C
0x18001a141  mov     rax, [rsp+88h+arg_20]
0x18001a149  mov     r9, rbp; struct _ITEMIDLIST **
0x18001a14c  mov     rdx, [rsp+88h+ppidl]; struct _ITEMIDLIST *
0x18001a151  mov     r8d, r15d; unsigned int
0x18001a154  mov     [rsp+88h+var_60], rax; struct IShellFolder *
0x18001a159  mov     rcx, r14; struct IDataObject **
0x18001a15c  mov     [rsp+88h+var_68], rsi; HWND
0x18001a161  call    ?CreateInstance@CFontFolderData@@SAJPEAPEAUIDataObject@@PEFBU_ITEMIDLIST@@IPEAPEFBU3@PEAUHWND__@@PEAUIShellFolder@@PEAU2@@Z; CFontFolderData::CreateInstance(IDataObject * *,_ITEMIDLIST const *,uint,_ITEMIDLIST const * *,HWND__ *,IShellFolder *,IDataObject *)
0x18001a166  mov     rcx, [rsp+88h+arg_20]
0x18001a16e  mov     ebx, eax
0x18001a170  mov     rax, [rcx]
0x18001a173  mov     rax, [rax+10h]
0x18001a177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a17c  mov     rcx, [rsp+88h+ppidl]; pv
0x18001a181  call    cs:__imp_CoTaskMemFree
0x18001a187  mov     eax, ebx
0x18001a189  add     rsp, 58h
0x18001a18d  pop     r15
0x18001a18f  pop     r14
0x18001a191  pop     rdi
0x18001a192  pop     rsi
0x18001a193  pop     rbp
0x18001a194  pop     rbx
0x18001a195  retn
```
