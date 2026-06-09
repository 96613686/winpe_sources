# SHCreateItemWithParentHelper(_ITEMIDLIST_ABSOLUTE const *,IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180008730`
- end: `0x1800087a8`
- name: `?SHCreateItemWithParentHelper@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `120`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *, struct IShellFolder *, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001dac4`
- `0x180020180`
- `0x180028884`

## callees

- `0x180008730`
- `0x180008c80`
- `0x180008d2c`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000876f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000876f`

## string_xrefs

- `0x180008768`: `SHCreateItemWithParent`

## pseudocode

```c
__int64 __fastcall SHCreateItemWithParentHelper(
        const struct _ITEMIDLIST_ABSOLUTE *a1,
        struct IShellFolder *a2,
        const struct _ITEMID_CHILD *a3,
        const struct _GUID *a4,
        void **a5)
{
  FARPROC ProcAddress; // rax

  if ( AutoLibrary::valid((AutoLibrary *)&g_shell32Helper)
    && (AutoLibrary::load((AutoLibrary *)&g_shell32Helper),
        (ProcAddress = GetProcAddress(qword_180053418, "SHCreateItemWithParent")) != 0) )
  {
    return ((__int64 (__fastcall *)(const struct _ITEMIDLIST_ABSOLUTE *, struct IShellFolder *, const struct _ITEMID_CHILD *, const struct _GUID *, void **))ProcAddress)(
             a1,
             a2,
             a3,
             a4,
             a5);
  }
  else
  {
    return 2147942527LL;
  }
}

```

## disassembly

```asm
0x180008730  push    rbx
0x180008732  push    rbp
0x180008733  push    rsi
0x180008734  push    rdi
0x180008735  sub     rsp, 38h
0x180008739  mov     rbp, rcx
0x18000873c  mov     rbx, r9
0x18000873f  lea     rcx, ?g_shell32Helper@@3UAutoLibrary@@A; this
0x180008746  mov     rdi, r8
0x180008749  mov     rsi, rdx
0x18000874c  call    ?valid@AutoLibrary@@QEAA_NXZ; AutoLibrary::valid(void)
0x180008751  test    al, al
0x180008753  jz      short loc_18000879A
0x180008755  lea     rcx, ?g_shell32Helper@@3UAutoLibrary@@A; this
0x18000875c  call    ?load@AutoLibrary@@AEAAXXZ; AutoLibrary::load(void)
0x180008761  mov     rcx, cs:qword_180053418; hModule
0x180008768  lea     rdx, aShcreateitemwi; "SHCreateItemWithParent"
0x18000876f  call    cs:__imp_GetProcAddress
0x180008775  test    rax, rax
0x180008778  jz      short loc_18000879A
0x18000877a  mov     rcx, [rsp+58h+arg_20]
0x180008782  mov     r9, rbx
0x180008785  mov     [rsp+58h+var_38], rcx
0x18000878a  mov     r8, rdi
0x18000878d  mov     rcx, rbp
0x180008790  mov     rdx, rsi
0x180008793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008798  jmp     short loc_18000879F
0x18000879a  mov     eax, 8007007Fh
0x18000879f  add     rsp, 38h
0x1800087a3  pop     rdi
0x1800087a4  pop     rsi
0x1800087a5  pop     rbp
0x1800087a6  pop     rbx
0x1800087a7  retn
```
