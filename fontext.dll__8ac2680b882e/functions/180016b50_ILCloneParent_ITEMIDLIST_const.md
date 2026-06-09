# ILCloneParent(_ITEMIDLIST const *)

- ea: `0x180016b50`
- end: `0x180016b76`
- name: `?ILCloneParent@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z`
- size: `38`
- prototype: `struct _ITEMIDLIST *__fastcall(const struct _ITEMIDLIST *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016510`
- `0x180016bd0`

## callees

- `0x180016b50`

## import_xrefs

- `SHELL32!__imp_ILRemoveLastID` at `0x180016b67`
- `SHELL32!__imp_ILRemoveLastID` at `0x180016b67`
- `SHELL32!__imp_ILClone` at `0x180016b56`
- `SHELL32!__imp_ILClone` at `0x180016b56`

## pseudocode

```c
struct _ITEMIDLIST *__fastcall ILCloneParent(const struct _ITEMIDLIST *a1)
{
  ITEMIDLIST *v1; // rax
  ITEMIDLIST *v2; // rbx

  v1 = ILClone(a1);
  v2 = v1;
  if ( v1 )
    ILRemoveLastID(v1);
  return v2;
}

```

## disassembly

```asm
0x180016b50  push    rbx
0x180016b52  sub     rsp, 20h
0x180016b56  call    cs:__imp_ILClone
0x180016b5c  mov     rbx, rax
0x180016b5f  test    rax, rax
0x180016b62  jz      short loc_180016B6D
0x180016b64  mov     rcx, rax; pidl
0x180016b67  call    cs:__imp_ILRemoveLastID
0x180016b6d  mov     rax, rbx
0x180016b70  add     rsp, 20h
0x180016b74  pop     rbx
0x180016b75  retn
```
