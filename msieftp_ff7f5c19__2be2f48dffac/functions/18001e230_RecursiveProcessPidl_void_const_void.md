# RecursiveProcessPidl(void const *,void *)

- ea: `0x18001e230`
- end: `0x18001e29a`
- name: `?RecursiveProcessPidl@@YAHPEBXPEAX@Z`
- size: `106`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001e230`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001e249`
- `SHELL32!__imp_ILCombine` at `0x18001e249`
- `SHELL32!__imp_ILFree` at `0x18001e27c`
- `SHELL32!__imp_ILFree` at `0x18001e27c`

## pseudocode

```c
_BOOL8 __fastcall RecursiveProcessPidl(const ITEMIDLIST *p, LPCITEMIDLIST *pData)
{
  LPITEMIDLIST v3; // rax
  ITEMIDLIST *v4; // rsi

  v3 = ILCombine(pData[4], p);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)pData + 10) = ((__int64 (__fastcall *)(LPCITEMIDLIST, LPCITEMIDLIST, LPITEMIDLIST, LPCITEMIDLIST, LPCITEMIDLIST))pData[3])(
                                pData[3],
                                *pData,
                                v3,
                                pData[1],
                                pData[2]);
    ILFree(v4);
  }
  return *((_DWORD *)pData + 10) >= 0;
}

```

## disassembly

```asm
0x18001e230  mov     [rsp+arg_0], rbx
0x18001e235  mov     [rsp+arg_8], rsi
0x18001e23a  push    rdi
0x18001e23b  sub     rsp, 30h
0x18001e23f  mov     rdi, rdx
0x18001e242  mov     rdx, rcx; pidl2
0x18001e245  mov     rcx, [rdi+20h]; pidl1
0x18001e249  call    cs:__imp_ILCombine
0x18001e24f  mov     rsi, rax
0x18001e252  test    rax, rax
0x18001e255  jz      short loc_18001E282
0x18001e257  mov     rcx, [rdi+10h]
0x18001e25b  mov     r8, rsi
0x18001e25e  mov     rax, [rdi+18h]
0x18001e262  mov     r9, [rdi+8]
0x18001e266  mov     rdx, [rdi]
0x18001e269  mov     [rsp+38h+var_18], rcx
0x18001e26e  mov     rcx, rax
0x18001e271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e276  mov     rcx, rsi; pidl
0x18001e279  mov     [rdi+28h], eax
0x18001e27c  call    cs:__imp_ILFree
0x18001e282  mov     eax, [rdi+28h]
0x18001e285  mov     rbx, [rsp+38h+arg_0]
0x18001e28a  not     eax
0x18001e28c  mov     rsi, [rsp+38h+arg_8]
0x18001e291  shr     eax, 1Fh
0x18001e294  add     rsp, 30h
0x18001e298  pop     rdi
0x18001e299  retn
```
