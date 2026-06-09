# EnumFolder(long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,_ITEMIDLIST const *,WIREENC,int *,void *)

- ea: `0x18001ded8`
- end: `0x18001e01c`
- name: `?EnumFolder@@YAJP6AJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z01W4WIREENC@@20@Z`
- size: `324`
- prototype: `int __high(int (__high *)(void *, void *, const struct _ITEMIDLIST *, int *, void *), void *, const struct _ITEMIDLIST *, enum WIREENC, int *, void *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d920`
- `0x18000dba0`
- `0x18000e100`
- `0x18001a2a0`

## callees

- `0x18000cca4`
- `0x18001ddf4`
- `0x18001ded8`
- `0x18001e2d4`
- `0x1800269f4`
- `0x180026ff0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001df83`
- `SHELL32!__imp_ILCombine` at `0x18001df83`
- `SHELL32!__imp_ILFree` at `0x18001dfac`
- `SHELL32!__imp_ILFree` at `0x18001dfac`

## pseudocode

```c
__int64 __fastcall EnumFolder(
        __int64 (__fastcall *a1)(_QWORD, void *, ITEMIDLIST *, int *, __int64),
        void *a2,
        ITEMIDLIST *a3,
        unsigned int a4,
        int *a5,
        __int64 a6)
{
  int v9; // edi
  struct CFtpPidlList *v10; // rsi
  __int64 v11; // r13
  int v12; // r14d
  PVOID Ptr; // rax
  struct _DPA *v14; // rcx
  ITEMIDLIST *v15; // rbx
  int v17; // [rsp+30h] [rbp-20h] BYREF
  struct _ITEMIDLIST *v18; // [rsp+38h] [rbp-18h] BYREF
  struct CFtpPidlList *v19; // [rsp+40h] [rbp-10h] BYREF
  struct _ITEMIDLIST *v21; // [rsp+A0h] [rbp+50h] BYREF

  v21 = a3;
  v19 = 0;
  v17 = 1;
  v9 = CFtpPidlList_Create(0, (const struct _ITEMIDLIST **const)&v21, &v19);
  if ( v9 >= 0 )
  {
    v10 = v19;
    v18 = 0;
    v9 = _EnumFolderPrep(a2, a3, v19, a4, &v18);
    if ( v9 >= 0 )
    {
      v11 = a6;
      v9 = 0;
      v12 = 0;
      do
      {
        Ptr = (PVOID)*((_QWORD *)v10 + 2);
        v14 = (struct _DPA *)*((_QWORD *)Ptr + 2);
        if ( v12 >= *(_DWORD *)v14 )
          break;
        if ( Ptr )
          Ptr = DPA_GetPtr(v14, v12);
        v15 = ILCombine(a3, (LPCITEMIDLIST)Ptr);
        v9 = a1(a1, a2, v15, &v17, v11);
        ILFree(v15);
        ++v12;
      }
      while ( v9 >= 0 );
      if ( v17 && v9 >= 0 )
        v9 = FtpSetCurrentDirectoryPidlWrap(a2, v18, 1, 1);
      Pidl_Set(&v18, 0);
    }
    (*(void (__fastcall **)(struct CFtpPidlList *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( a5 )
    *a5 = v17;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ded8  mov     [rsp-38h+arg_8], rbx
0x18001dedd  mov     [rsp-38h+arg_10], r8
0x18001dee2  mov     [rsp-38h+arg_0], rcx
0x18001dee7  push    rbp
0x18001dee8  push    rsi
0x18001dee9  push    rdi
0x18001deea  push    r12
0x18001deec  push    r13
0x18001deee  push    r14
0x18001def0  push    r15
0x18001def2  mov     rbp, rsp
0x18001def5  sub     rsp, 50h
0x18001def9  mov     r12, r8
0x18001defc  mov     [rbp+var_10], 0
0x18001df04  mov     r15, rdx
0x18001df07  mov     [rbp+var_20], 1
0x18001df0e  lea     r8, [rbp+var_10]; struct CFtpPidlList **
0x18001df12  xor     ecx, ecx; int
0x18001df14  lea     rdx, [rbp+arg_10]; struct _ITEMIDLIST **
0x18001df18  mov     ebx, r9d
0x18001df1b  call    ?CFtpPidlList_Create@@YAJHQEAPEFBU_ITEMIDLIST@@PEAPEAVCFtpPidlList@@@Z; CFtpPidlList_Create(int,_ITEMIDLIST const * * const,CFtpPidlList * *)
0x18001df20  mov     edi, eax
0x18001df22  test    eax, eax
0x18001df24  js      loc_18001DFF4
0x18001df2a  mov     rsi, [rbp+var_10]
0x18001df2e  lea     rax, [rbp+var_18]
0x18001df32  mov     r8, rsi
0x18001df35  mov     [rbp+var_18], 0
0x18001df3d  mov     r9d, ebx
0x18001df40  mov     [rsp+50h+var_30], rax
0x18001df45  mov     rdx, r12
0x18001df48  mov     rcx, r15
0x18001df4b  call    ?_EnumFolderPrep@@YAJPEAXPEFBU_ITEMIDLIST@@PEAVCFtpPidlList@@W4WIREENC@@PEAPEFAU1@@Z; _EnumFolderPrep(void *,_ITEMIDLIST const *,CFtpPidlList *,WIREENC,_ITEMIDLIST * *)
0x18001df50  mov     edi, eax
0x18001df52  test    eax, eax
0x18001df54  js      loc_18001DFE5
0x18001df5a  mov     r13, [rbp+arg_28]
0x18001df5e  xor     edi, edi
0x18001df60  xor     r14d, r14d
0x18001df63  mov     rax, [rsi+10h]
0x18001df67  mov     rcx, [rax+10h]; hdpa
0x18001df6b  cmp     r14d, [rcx]
0x18001df6e  jge     short loc_18001DFB9
0x18001df70  test    rax, rax
0x18001df73  jz      short loc_18001DF7D
0x18001df75  movsxd  rdx, r14d; i
0x18001df78  call    DPA_GetPtr
0x18001df7d  mov     rdx, rax; pidl2
0x18001df80  mov     rcx, r12; pidl1
0x18001df83  call    cs:__imp_ILCombine
0x18001df89  lea     r9, [rbp+var_20]
0x18001df8d  mov     [rsp+50h+var_30], r13
0x18001df92  mov     rbx, rax
0x18001df95  mov     r8, rax
0x18001df98  mov     rax, [rbp+arg_0]
0x18001df9c  mov     rdx, r15
0x18001df9f  mov     rcx, rax
0x18001dfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa7  mov     rcx, rbx; pidl
0x18001dfaa  mov     edi, eax
0x18001dfac  call    cs:__imp_ILFree
0x18001dfb2  inc     r14d
0x18001dfb5  test    edi, edi
0x18001dfb7  jns     short loc_18001DF63
0x18001dfb9  cmp     [rbp+var_20], 0
0x18001dfbd  jz      short loc_18001DFDA
0x18001dfbf  test    edi, edi
0x18001dfc1  js      short loc_18001DFDA
0x18001dfc3  mov     rdx, [rbp+var_18]; struct _ITEMIDLIST *
0x18001dfc7  mov     r9d, 1; int
0x18001dfcd  mov     r8d, r9d; int
0x18001dfd0  mov     rcx, r15; void *
0x18001dfd3  call    ?FtpSetCurrentDirectoryPidlWrap@@YAJPEAXPEFBU_ITEMIDLIST@@HH@Z; FtpSetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST const *,int,int)
0x18001dfd8  mov     edi, eax
0x18001dfda  xor     edx, edx
0x18001dfdc  lea     rcx, [rbp+var_18]
0x18001dfe0  call    Pidl_Set
0x18001dfe5  mov     rax, [rsi]
0x18001dfe8  mov     rcx, rsi
0x18001dfeb  mov     rax, [rax+10h]
0x18001dfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dff4  mov     rcx, [rbp+arg_20]
0x18001dff8  test    rcx, rcx
0x18001dffb  jz      short loc_18001E002
0x18001dffd  mov     eax, [rbp+var_20]
0x18001e000  mov     [rcx], eax
0x18001e002  mov     rbx, [rsp+50h+arg_8]
0x18001e00a  mov     eax, edi
0x18001e00c  add     rsp, 50h
0x18001e010  pop     r15
0x18001e012  pop     r14
0x18001e014  pop     r13
0x18001e016  pop     r12
0x18001e018  pop     rdi
0x18001e019  pop     rsi
0x18001e01a  pop     rbp
0x18001e01b  retn
```
