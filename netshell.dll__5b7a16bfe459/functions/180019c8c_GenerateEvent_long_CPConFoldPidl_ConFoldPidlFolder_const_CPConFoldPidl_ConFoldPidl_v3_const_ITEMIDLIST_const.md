# GenerateEvent(long,CPConFoldPidl<ConFoldPidlFolder> const &,CPConFoldPidl<ConFoldPidl_v3> const &,_ITEMIDLIST const *)

- ea: `0x180019c8c`
- end: `0x180019d1c`
- name: `?GenerateEvent@@YAXJAEBV?$CPConFoldPidl@VConFoldPidlFolder@@@@AEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEFBU_ITEMIDLIST@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(LONG wEventId)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003770`
- `0x180004f10`
- `0x180019b50`
- `0x180019bb0`
- `0x18001d38c`
- `0x180042fb4`
- `0x18004abf0`
- `0x18004ae40`
- `0x18004b060`
- `0x18004b674`

## callees

- `0x180019c8c`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180019cd5`
- `SHELL32!SHChangeNotify` at `0x180019cf0`
- `SHELL32!SHChangeNotify` at `0x180019d03`
- `SHELL32!SHChangeNotify` at `0x180019cd5`
- `SHELL32!SHChangeNotify` at `0x180019cf0`
- `SHELL32!SHChangeNotify` at `0x180019d03`
- `SHELL32!__imp_ILCombine` at `0x180019ca4`
- `SHELL32!__imp_ILCombine` at `0x180019cbd`
- `SHELL32!__imp_ILCombine` at `0x180019ca4`
- `SHELL32!__imp_ILCombine` at `0x180019cbd`
- `SHELL32!__imp_SHFree` at `0x180019cde`
- `SHELL32!__imp_SHFree` at `0x180019d0c`
- `SHELL32!__imp_SHFree` at `0x180019cde`
- `SHELL32!__imp_SHFree` at `0x180019d0c`

## pseudocode

```c
void __fastcall GenerateEvent(LONG wEventId, LPCITEMIDLIST *a2, LPCITEMIDLIST *a3, const ITEMIDLIST *a4)
{
  LPITEMIDLIST v7; // rax
  LPITEMIDLIST v8; // rbx
  LPITEMIDLIST v9; // rax
  LPITEMIDLIST v10; // rdi

  v7 = ILCombine(*a2, *a3);
  v8 = v7;
  if ( v7 )
  {
    if ( a4 )
    {
      v9 = ILCombine(*a2, a4);
      v10 = v9;
      if ( v9 )
      {
        SHChangeNotify(wEventId, 0, v8, v9);
        SHFree(v10);
      }
    }
    else
    {
      SHChangeNotify(wEventId, 0, v7, 0);
    }
    SHChangeNotify(0, 0x3000u, 0, 0);
    SHFree(v8);
  }
}

```

## disassembly

```asm
0x180019c8c  push    rbx
0x180019c8e  push    rsi
0x180019c8f  push    rdi
0x180019c90  push    r14
0x180019c92  sub     rsp, 28h
0x180019c96  mov     r14, rdx
0x180019c99  mov     esi, ecx
0x180019c9b  mov     rdx, [r8]; pidl2
0x180019c9e  mov     rdi, r9
0x180019ca1  mov     rcx, [r14]; pidl1
0x180019ca4  call    cs:__imp_ILCombine
0x180019caa  mov     rbx, rax
0x180019cad  test    rax, rax
0x180019cb0  jz      short loc_180019D12
0x180019cb2  test    rdi, rdi
0x180019cb5  jz      short loc_180019CE6
0x180019cb7  mov     rcx, [r14]; pidl1
0x180019cba  mov     rdx, rdi; pidl2
0x180019cbd  call    cs:__imp_ILCombine
0x180019cc3  mov     rdi, rax
0x180019cc6  test    rax, rax
0x180019cc9  jz      short loc_180019CF6
0x180019ccb  mov     r9, rax; dwItem2
0x180019cce  mov     r8, rbx; dwItem1
0x180019cd1  xor     edx, edx; uFlags
0x180019cd3  mov     ecx, esi; wEventId
0x180019cd5  call    cs:__imp_SHChangeNotify
0x180019cdb  mov     rcx, rdi; pv
0x180019cde  call    cs:__imp_SHFree
0x180019ce4  jmp     short loc_180019CF6
0x180019ce6  xor     r9d, r9d; dwItem2
0x180019ce9  mov     r8, rbx; dwItem1
0x180019cec  xor     edx, edx; uFlags
0x180019cee  mov     ecx, esi; wEventId
0x180019cf0  call    cs:__imp_SHChangeNotify
0x180019cf6  xor     r9d, r9d; dwItem2
0x180019cf9  xor     r8d, r8d; dwItem1
0x180019cfc  mov     edx, 3000h; uFlags
0x180019d01  xor     ecx, ecx; wEventId
0x180019d03  call    cs:__imp_SHChangeNotify
0x180019d09  mov     rcx, rbx; pv
0x180019d0c  call    cs:__imp_SHFree
0x180019d12  add     rsp, 28h
0x180019d16  pop     r14
0x180019d18  pop     rdi
0x180019d19  pop     rsi
0x180019d1a  pop     rbx
0x180019d1b  retn
```
