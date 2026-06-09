# FtpPidl_InsertVirtualRoot(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)

- ea: `0x18001cd5c`
- end: `0x18001cdb1`
- name: `?FtpPidl_InsertVirtualRoot@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z`
- size: `85`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl1, const struct _ITEMIDLIST *, struct _ITEMIDLIST **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001876c`
- `0x180020efc`

## callees

- `0x18001bda4`
- `0x18001cd5c`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001cd8c`
- `SHELL32!__imp_ILCombine` at `0x18001cd8c`

## pseudocode

```c
__int64 __fastcall FtpPidl_InsertVirtualRoot(
        LPCITEMIDLIST pidl1,
        const struct _ITEMIDLIST *a2,
        struct _ITEMIDLIST **a3)
{
  const ITEMIDLIST *v5; // rbx
  struct _ITEMIDLIST *v6; // rax

  v5 = a2;
  if ( (unsigned int)FtpID_IsServerItemID(a2) )
    v5 = (const ITEMIDLIST *)((char *)v5 + v5->mkid.cb);
  v6 = ILCombine(pidl1, v5);
  *a3 = v6;
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001cd5c  mov     [rsp+arg_0], rbx
0x18001cd61  mov     [rsp+arg_8], rsi
0x18001cd66  push    rdi
0x18001cd67  sub     rsp, 20h
0x18001cd6b  mov     rsi, rcx
0x18001cd6e  mov     rdi, r8
0x18001cd71  mov     rcx, rdx; struct _ITEMIDLIST *
0x18001cd74  mov     rbx, rdx
0x18001cd77  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001cd7c  test    eax, eax
0x18001cd7e  jz      short loc_18001CD86
0x18001cd80  movzx   eax, word ptr [rbx]
0x18001cd83  add     rbx, rax
0x18001cd86  mov     rdx, rbx; pidl2
0x18001cd89  mov     rcx, rsi; pidl1
0x18001cd8c  call    cs:__imp_ILCombine
0x18001cd92  mov     rbx, [rsp+28h+arg_0]
0x18001cd97  mov     rsi, [rsp+28h+arg_8]
0x18001cd9c  mov     [rdi], rax
0x18001cd9f  neg     rax
0x18001cda2  sbb     eax, eax
0x18001cda4  not     eax
0x18001cda6  and     eax, 8007000Eh
0x18001cdab  add     rsp, 20h
0x18001cdaf  pop     rdi
0x18001cdb0  retn
```
