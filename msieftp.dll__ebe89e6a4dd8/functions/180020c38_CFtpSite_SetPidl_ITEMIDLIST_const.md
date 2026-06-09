# CFtpSite::_SetPidl(_ITEMIDLIST const *)

- ea: `0x180020c38`
- end: `0x180020c95`
- name: `?_SetPidl@CFtpSite@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `93`
- prototype: `int(CFtpSite *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fc24`
- `0x1800201c4`
- `0x180020a4c`

## callees

- `0x18001bd14`
- `0x180020c38`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180020c63`
- `SHELL32!__imp_ILCombine` at `0x180020c63`
- `SHELL32!__imp_ILFree` at `0x180020c75`
- `SHELL32!__imp_ILFree` at `0x180020c84`
- `SHELL32!__imp_ILFree` at `0x180020c75`
- `SHELL32!__imp_ILFree` at `0x180020c84`

## pseudocode

```c
__int64 __fastcall CFtpSite::_SetPidl(LPCITEMIDLIST *this, const struct _ITEMIDLIST *a2)
{
  unsigned int v4; // ebx
  const ITEMIDLIST *v5; // rax
  ITEMIDLIST *v6; // rdi
  LPITEMIDLIST v7; // rbp

  v4 = -2147467259;
  v5 = FtpCloneServerID(this[9]);
  v6 = (ITEMIDLIST *)v5;
  if ( v5 )
  {
    v7 = ILCombine(v5, a2);
    if ( v7 )
    {
      ILFree((LPITEMIDLIST)this[9]);
      v4 = 0;
      this[9] = v7;
    }
    ILFree(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180020c38  push    rbx
0x180020c3a  push    rbp
0x180020c3b  push    rsi
0x180020c3c  push    rdi
0x180020c3d  sub     rsp, 28h
0x180020c41  mov     rsi, rcx
0x180020c44  mov     rbp, rdx
0x180020c47  mov     rcx, [rcx+48h]; pidl
0x180020c4b  mov     ebx, 80004005h
0x180020c50  call    ?FtpCloneServerID@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z; FtpCloneServerID(_ITEMIDLIST const *)
0x180020c55  mov     rdi, rax
0x180020c58  test    rax, rax
0x180020c5b  jz      short loc_180020C8A
0x180020c5d  mov     rdx, rbp; pidl2
0x180020c60  mov     rcx, rax; pidl1
0x180020c63  call    cs:__imp_ILCombine
0x180020c69  mov     rbp, rax
0x180020c6c  test    rax, rax
0x180020c6f  jz      short loc_180020C81
0x180020c71  mov     rcx, [rsi+48h]; pidl
0x180020c75  call    cs:__imp_ILFree
0x180020c7b  xor     ebx, ebx
0x180020c7d  mov     [rsi+48h], rbp
0x180020c81  mov     rcx, rdi; pidl
0x180020c84  call    cs:__imp_ILFree
0x180020c8a  mov     eax, ebx
0x180020c8c  add     rsp, 28h
0x180020c90  pop     rdi
0x180020c91  pop     rsi
0x180020c92  pop     rbp
0x180020c93  pop     rbx
0x180020c94  retn
```
