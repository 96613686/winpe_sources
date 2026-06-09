# CFtpFolder::_ForPopulateAndEnum(CFtpDir *,_ITEMIDLIST const *,ushort const *,char const *,_ITEMIDLIST * *)

- ea: `0x18001812c`
- end: `0x18001823b`
- name: `?_ForPopulateAndEnum@CFtpFolder@@IEAAJPEAVCFtpDir@@PEFBU_ITEMIDLIST@@PEBGPEBDPEAPEFAU3@@Z`
- size: `271`
- prototype: `__int64 __usercall@<rax>(CFtpFolder *__hidden this@<rcx>, struct CFtpDir *@<rdx>, LPCITEMIDLIST pidl1@<r8>, const unsigned __int16 *@<r9>, LPCSTR pszPath, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800182c4`

## callees

- `0x1800112d4`
- `0x1800152e0`
- `0x18001812c`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x1800181fe`
- `SHELL32!__imp_ILCombine` at `0x1800181fe`
- `SHELL32!__imp_ILFree` at `0x18001820a`
- `SHELL32!__imp_ILFree` at `0x18001820a`
- `SHLWAPI!PathFindExtensionA` at `0x18001818c`
- `SHLWAPI!PathFindExtensionA` at `0x18001818c`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_ForPopulateAndEnum(
        CFtpFolder *this,
        struct CFtpDir *a2,
        LPCITEMIDLIST pidl1,
        struct IEnumIDList *a4,
        LPCSTR pszPath,
        struct _ITEMIDLIST **a6)
{
  struct _ITEMIDLIST **v6; // r14
  int v10; // ebx
  _WORD *v11; // rax
  const ITEMIDLIST *PidlFromWireName; // rax
  ITEMIDLIST *v13; // rdi
  struct IEnumIDList *v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = a4;
  v6 = a6;
  v10 = -2147467259;
  *a6 = 0;
  if ( a2 )
  {
    v11 = (_WORD *)*((_QWORD *)a2 + 5);
    if ( v11 )
    {
      if ( *v11 && (!pszPath || !*PathFindExtensionA(pszPath)) )
      {
        v15 = 0;
        v10 = CFtpEidl_Create(a2, this, 0, 0xE0u, &v15);
        if ( v10 >= 0 )
        {
          v10 = ((__int64 (__fastcall *)(struct IEnumIDList *))v15->lpVtbl->Reset)(v15);
          PidlFromWireName = CFtpDir::GetPidlFromWireName(a2, pszPath);
          v13 = (ITEMIDLIST *)PidlFromWireName;
          if ( PidlFromWireName )
          {
            *v6 = ILCombine(pidl1, PidlFromWireName);
            ILFree(v13);
          }
          else
          {
            v10 = -2147467259;
          }
          ((void (__fastcall *)(struct IEnumIDList *))v15->lpVtbl->Release)(v15);
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001812c  mov     [rsp+arg_18], r9
0x180018131  push    rbx
0x180018132  push    rbp
0x180018133  push    rdi
0x180018134  push    r12
0x180018136  push    r14
0x180018138  push    r15
0x18001813a  sub     rsp, 38h
0x18001813e  mov     r14, [rsp+68h+arg_28]
0x180018146  xor     r12d, r12d
0x180018149  mov     rbp, r8
0x18001814c  mov     rdi, rdx
0x18001814f  mov     r15, rcx
0x180018152  mov     ebx, 80004005h
0x180018157  mov     [r14], r12
0x18001815a  test    rdx, rdx
0x18001815d  jz      loc_18001822B
0x180018163  mov     rax, [rdx+28h]
0x180018167  test    rax, rax
0x18001816a  jz      loc_18001822B
0x180018170  cmp     [rax], r12w
0x180018174  jz      loc_18001822B
0x18001817a  cmp     [rsp+68h+pszPath], r12
0x180018182  jz      short loc_18001819B
0x180018184  mov     rcx, [rsp+68h+pszPath]; pszPath
0x18001818c  call    cs:__imp_PathFindExtensionA
0x180018192  cmp     [rax], r12b
0x180018195  jnz     loc_18001822B
0x18001819b  lea     rax, [rsp+68h+arg_18]
0x1800181a3  mov     [rsp+68h+arg_18], r12
0x1800181ab  mov     r9d, 0E0h; unsigned int
0x1800181b1  mov     [rsp+68h+var_48], rax; struct IEnumIDList **
0x1800181b6  xor     r8d, r8d; HWND
0x1800181b9  mov     rdx, r15; struct CFtpFolder *
0x1800181bc  mov     rcx, rdi; struct CFtpDir *
0x1800181bf  call    ?CFtpEidl_Create@@YAJPEAVCFtpDir@@PEAVCFtpFolder@@PEAUHWND__@@KPEAPEAUIEnumIDList@@@Z; CFtpEidl_Create(CFtpDir *,CFtpFolder *,HWND__ *,ulong,IEnumIDList * *)
0x1800181c4  mov     ebx, eax
0x1800181c6  test    eax, eax
0x1800181c8  js      short loc_18001822B
0x1800181ca  mov     rcx, [rsp+68h+arg_18]
0x1800181d2  mov     rax, [rcx]
0x1800181d5  mov     rax, [rax+28h]
0x1800181d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181de  mov     rdx, [rsp+68h+pszPath]; char *
0x1800181e6  mov     rcx, rdi; this
0x1800181e9  mov     ebx, eax
0x1800181eb  call    ?GetPidlFromWireName@CFtpDir@@QEAAPEFBU_ITEMIDLIST@@PEBD@Z; CFtpDir::GetPidlFromWireName(char const *)
0x1800181f0  mov     rdi, rax
0x1800181f3  test    rax, rax
0x1800181f6  jz      short loc_180018212
0x1800181f8  mov     rdx, rax; pidl2
0x1800181fb  mov     rcx, rbp; pidl1
0x1800181fe  call    cs:__imp_ILCombine
0x180018204  mov     rcx, rdi; pidl
0x180018207  mov     [r14], rax
0x18001820a  call    cs:__imp_ILFree
0x180018210  jmp     short loc_180018217
0x180018212  mov     ebx, 80004005h
0x180018217  mov     rcx, [rsp+68h+arg_18]
0x18001821f  mov     rax, [rcx]
0x180018222  mov     rax, [rax+10h]
0x180018226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001822b  mov     eax, ebx
0x18001822d  add     rsp, 38h
0x180018231  pop     r15
0x180018233  pop     r14
0x180018235  pop     r12
0x180018237  pop     rdi
0x180018238  pop     rbp
0x180018239  pop     rbx
0x18001823a  retn
```
