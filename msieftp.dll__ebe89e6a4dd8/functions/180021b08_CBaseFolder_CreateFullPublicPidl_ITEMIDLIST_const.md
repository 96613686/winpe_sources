# CBaseFolder::CreateFullPublicPidl(_ITEMIDLIST const *)

- ea: `0x180021b08`
- end: `0x180021b6b`
- name: `?CreateFullPublicPidl@CBaseFolder@@QEAAPEFAU_ITEMIDLIST@@PEFBU2@@Z`
- size: `99`
- prototype: `struct _ITEMIDLIST *(CBaseFolder *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ef80`
- `0x1800207b8`
- `0x180024be8`

## callees

- `0x180021b08`

## import_xrefs

- `SHELL32!__imp_ILRemoveLastID` at `0x180021b37`
- `SHELL32!__imp_ILRemoveLastID` at `0x180021b37`
- `SHELL32!__imp_ILClone` at `0x180021b1b`
- `SHELL32!__imp_ILClone` at `0x180021b1b`
- `SHELL32!__imp_ILCombine` at `0x180021b4d`
- `SHELL32!__imp_ILCombine` at `0x180021b4d`
- `SHELL32!__imp_ILFree` at `0x180021b59`
- `SHELL32!__imp_ILFree` at `0x180021b59`

## pseudocode

```c
LPITEMIDLIST __fastcall CBaseFolder::CreateFullPublicPidl(LPCITEMIDLIST *this, const struct _ITEMIDLIST *a2)
{
  LPITEMIDLIST v4; // rdi
  ITEMIDLIST *v5; // rbx
  LPITEMIDLIST v6; // rbx

  v4 = ILClone(this[6]);
  v5 = (LPITEMIDLIST)((char *)v4 + *((int *)this + 16));
  if ( v5 )
  {
    while ( v5->mkid.cb )
      ILRemoveLastID(v5);
  }
  v6 = 0;
  if ( v4 )
  {
    v6 = ILCombine(v4, a2);
    ILFree(v4);
  }
  return v6;
}

```

## disassembly

```asm
0x180021b08  push    rbx
0x180021b0a  push    rbp
0x180021b0b  push    rsi
0x180021b0c  push    rdi
0x180021b0d  sub     rsp, 28h
0x180021b11  mov     rbx, rcx
0x180021b14  mov     rsi, rdx
0x180021b17  mov     rcx, [rcx+30h]; pidl
0x180021b1b  call    cs:__imp_ILClone
0x180021b21  movsxd  rbx, dword ptr [rbx+40h]
0x180021b25  xor     ebp, ebp
0x180021b27  mov     rdi, rax
0x180021b2a  add     rbx, rax
0x180021b2d  jz      short loc_180021B3F
0x180021b2f  cmp     [rbx], bp
0x180021b32  jz      short loc_180021B3F
0x180021b34  mov     rcx, rbx; pidl
0x180021b37  call    cs:__imp_ILRemoveLastID
0x180021b3d  jmp     short loc_180021B2F
0x180021b3f  mov     rbx, rbp
0x180021b42  test    rdi, rdi
0x180021b45  jz      short loc_180021B5F
0x180021b47  mov     rdx, rsi; pidl2
0x180021b4a  mov     rcx, rdi; pidl1
0x180021b4d  call    cs:__imp_ILCombine
0x180021b53  mov     rcx, rdi; pidl
0x180021b56  mov     rbx, rax
0x180021b59  call    cs:__imp_ILFree
0x180021b5f  mov     rax, rbx
0x180021b62  add     rsp, 28h
0x180021b66  pop     rdi
0x180021b67  pop     rsi
0x180021b68  pop     rbp
0x180021b69  pop     rbx
0x180021b6a  retn
```
