# _InvokeCommandOnChildIDs(HWND__ *,IUnknown *,IShellFolder *,_ITEMID_CHILD const * const *,uint,uint,uint,char const *,ushort const *)

- ea: `0x18002c58c`
- end: `0x18002c632`
- name: `?_InvokeCommandOnChildIDs@@YAJPEAUHWND__@@PEAUIUnknown@@PEAUIShellFolder@@PEBQEFBU_ITEMID_CHILD@@IIIPEBDPEBG@Z`
- size: `166`
- prototype: `__int64 __usercall@<rax>(HWND pszPath@<rcx>, struct IUnknown *@<rdx>, struct IShellFolder *@<r8>, const struct _ITEMID_CHILD *const *@<r9>, unsigned int, unsigned int, unsigned int, const char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c638`

## callees

- `0x18002c58c`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_SHInvokeCommandOnContextMenuEx` at `0x18002c60c`
- `SHLWAPI!__imp_SHInvokeCommandOnContextMenuEx` at `0x18002c60c`

## pseudocode

```c
__int64 __fastcall _InvokeCommandOnChildIDs(
        const WCHAR *pszPath,
        struct IUnknown *a2,
        struct IShellFolder *a3,
        const struct _ITEMID_CHILD *const *a4,
        unsigned int a5)
{
  struct IShellFolderVtbl *lpVtbl; // rax
  int v7; // ebx
  struct IUnknown *v9; // [rsp+58h] [rbp+10h] BYREF

  v9 = a2;
  lpVtbl = a3->lpVtbl;
  v9 = 0;
  v7 = ((__int64 (__fastcall *)(struct IShellFolder *, const WCHAR *, _QWORD, const struct _ITEMID_CHILD *const *, GUID *, _QWORD, struct IUnknown **))lpVtbl->GetUIObjectOf)(
         a3,
         pszPath,
         a5,
         a4,
         &GUID_000214e4_0000_0000_c000_000000000046,
         0,
         &v9);
  if ( v7 >= 0 )
  {
    v7 = SHInvokeCommandOnContextMenuEx(pszPath, 0);
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002c58c  mov     r11, rsp
0x18002c58f  mov     [r11+8], rbx
0x18002c593  mov     [r11+10h], rdx
0x18002c597  push    rdi
0x18002c598  sub     rsp, 40h
0x18002c59c  mov     rax, [r8]
0x18002c59f  mov     rdi, rcx
0x18002c5a2  lea     rcx, [r11+10h]
0x18002c5a6  mov     qword ptr [r11+10h], 0
0x18002c5ae  mov     [r11-18h], rcx
0x18002c5b2  mov     r10, r8
0x18002c5b5  mov     r8d, [rsp+48h+arg_20]
0x18002c5ba  lea     rcx, _GUID_000214e4_0000_0000_c000_000000000046
0x18002c5c1  mov     rax, [rax+50h]
0x18002c5c5  mov     rdx, rdi
0x18002c5c8  mov     qword ptr [r11-20h], 0
0x18002c5d0  mov     [r11-28h], rcx
0x18002c5d4  mov     rcx, r10
0x18002c5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5dc  mov     ebx, eax
0x18002c5de  test    eax, eax
0x18002c5e0  js      short loc_18002C625
0x18002c5e2  mov     r8, [rsp+48h+arg_8]
0x18002c5e7  lea     rax, aProperties; "properties"
0x18002c5ee  mov     [rsp+48h+var_18], 0
0x18002c5f7  xor     r9d, r9d
0x18002c5fa  mov     [rsp+48h+var_20], rax
0x18002c5ff  xor     edx, edx; dwAttrb
0x18002c601  mov     rcx, rdi; pszPath
0x18002c604  mov     [rsp+48h+var_28], 0
0x18002c60c  call    cs:__imp_SHInvokeCommandOnContextMenuEx
0x18002c612  mov     rcx, [rsp+48h+arg_8]
0x18002c617  mov     ebx, eax
0x18002c619  mov     rax, [rcx]
0x18002c61c  mov     rax, [rax+10h]
0x18002c620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c625  mov     eax, ebx
0x18002c627  mov     rbx, [rsp+48h+arg_0]
0x18002c62c  add     rsp, 40h
0x18002c630  pop     rdi
0x18002c631  retn
```
