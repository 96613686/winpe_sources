# SiteCache_PidlLookup(_ITEMIDLIST const *,int,IMalloc *,CFtpSite * *)

- ea: `0x18001fdb0`
- end: `0x18001fea2`
- name: `?SiteCache_PidlLookup@@YAJPEFBU_ITEMIDLIST@@HPEAUIMalloc@@PEAPEAVCFtpSite@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, int, struct IMalloc *, struct CFtpSite **)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016b9c`
- `0x1800172a0`
- `0x1800182c4`
- `0x18001876c`
- `0x180018a5c`
- `0x180018dc0`
- `0x1800207b8`
- `0x180020c9c`
- `0x180024be8`

## callees

- `0x18001d32c`
- `0x18001fdb0`
- `0x18001fea8`
- `0x180021600`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18001fe29`
- `SHELL32!__imp_ILClone` at `0x18001fe29`
- `SHELL32!__imp_ILFree` at `0x18001fe83`
- `SHELL32!__imp_ILFree` at `0x18001fe83`

## pseudocode

```c
__int64 __fastcall SiteCache_PidlLookup(struct _ITEMIDLIST *a1, int a2, IUnknown *a3, struct CFtpSite **a4)
{
  int v8; // ebx
  unsigned __int16 *v9; // rbp
  struct _ITEMIDLIST *v10; // rdi
  int v11; // eax
  struct _ITEMIDLIST *v13; // [rsp+60h] [rbp+8h] BYREF

  v8 = -2147467259;
  if ( a1 )
  {
    if ( a1->mkid.cb )
    {
      v8 = SiteCache_PidlLookupPrivHelper(a1, a3, a4);
      if ( v8 >= 0 )
      {
        v9 = (unsigned __int16 *)*((_QWORD *)*a4 + 14);
        if ( v9 )
        {
          if ( a2 )
          {
            v13 = 0;
            if ( (FtpServerID_GetTypeID(a1) & 0x200) != 0 )
            {
              v11 = PidlReplaceUserPassword(a1, &v13, (struct IMalloc *)a3, 0, v9);
              v10 = v13;
              v8 = v11;
            }
            else
            {
              v10 = ILClone(a1);
              if ( !v10 )
                v8 = -2147024882;
            }
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 16LL))(*a4);
            *a4 = 0;
            if ( v8 >= 0 )
            {
              v8 = SiteCache_PidlLookupPrivHelper(v10, a3, a4);
              ILFree(v10);
            }
          }
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001fdb0  mov     [rsp+arg_8], rbx
0x18001fdb5  mov     [rsp+arg_10], rbp
0x18001fdba  push    rsi
0x18001fdbb  push    rdi
0x18001fdbc  push    r12
0x18001fdbe  push    r14
0x18001fdc0  push    r15
0x18001fdc2  sub     rsp, 30h
0x18001fdc6  xor     r12d, r12d
0x18001fdc9  mov     rsi, r9
0x18001fdcc  mov     r14, r8
0x18001fdcf  mov     r15d, edx
0x18001fdd2  mov     rdi, rcx
0x18001fdd5  mov     ebx, 80004005h
0x18001fdda  test    rcx, rcx
0x18001fddd  jz      loc_18001FE89
0x18001fde3  cmp     [rcx], r12w
0x18001fde7  jz      loc_18001FE89
0x18001fded  mov     r8, r9; struct CFtpSite **
0x18001fdf0  mov     rdx, r14; punk
0x18001fdf3  call    ?SiteCache_PidlLookupPrivHelper@@YAJPEFBU_ITEMIDLIST@@PEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookupPrivHelper(_ITEMIDLIST const *,IMalloc *,CFtpSite * *)
0x18001fdf8  mov     ebx, eax
0x18001fdfa  test    eax, eax
0x18001fdfc  js      loc_18001FE89
0x18001fe02  mov     rcx, [rsi]
0x18001fe05  mov     rbp, [rcx+70h]
0x18001fe09  test    rbp, rbp
0x18001fe0c  jz      short loc_18001FE89
0x18001fe0e  test    r15d, r15d
0x18001fe11  jz      short loc_18001FE89
0x18001fe13  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001fe16  mov     [rsp+58h+arg_0], r12
0x18001fe1b  call    ?FtpServerID_GetTypeID@@YAKPEFBU_ITEMIDLIST@@@Z; FtpServerID_GetTypeID(_ITEMIDLIST const *)
0x18001fe20  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001fe23  bt      eax, 9
0x18001fe27  jb      short loc_18001FE3E
0x18001fe29  call    cs:__imp_ILClone
0x18001fe2f  mov     rdi, rax
0x18001fe32  test    rax, rax
0x18001fe35  jnz     short loc_18001FE5A
0x18001fe37  mov     ebx, 8007000Eh
0x18001fe3c  jmp     short loc_18001FE5A
0x18001fe3e  xor     r9d, r9d; unsigned __int16 *
0x18001fe41  mov     [rsp+58h+var_38], rbp; unsigned __int16 *
0x18001fe46  mov     r8, r14; struct IMalloc *
0x18001fe49  lea     rdx, [rsp+58h+arg_0]; struct _ITEMIDLIST **
0x18001fe4e  call    ?PidlReplaceUserPassword@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@PEAUIMalloc@@PEBG3@Z; PidlReplaceUserPassword(_ITEMIDLIST const *,_ITEMIDLIST * *,IMalloc *,ushort const *,ushort const *)
0x18001fe53  mov     rdi, [rsp+58h+arg_0]
0x18001fe58  mov     ebx, eax
0x18001fe5a  mov     rcx, [rsi]
0x18001fe5d  mov     rax, [rcx]
0x18001fe60  mov     rax, [rax+10h]
0x18001fe64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe69  mov     [rsi], r12
0x18001fe6c  test    ebx, ebx
0x18001fe6e  js      short loc_18001FE89
0x18001fe70  mov     r8, rsi; struct CFtpSite **
0x18001fe73  mov     rdx, r14; punk
0x18001fe76  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001fe79  call    ?SiteCache_PidlLookupPrivHelper@@YAJPEFBU_ITEMIDLIST@@PEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookupPrivHelper(_ITEMIDLIST const *,IMalloc *,CFtpSite * *)
0x18001fe7e  mov     rcx, rdi; pidl
0x18001fe81  mov     ebx, eax
0x18001fe83  call    cs:__imp_ILFree
0x18001fe89  mov     rbp, [rsp+58h+arg_10]
0x18001fe8e  mov     eax, ebx
0x18001fe90  mov     rbx, [rsp+58h+arg_8]
0x18001fe95  add     rsp, 30h
0x18001fe99  pop     r15
0x18001fe9b  pop     r14
0x18001fe9d  pop     r12
0x18001fe9f  pop     rdi
0x18001fea0  pop     rsi
0x18001fea1  retn
```
