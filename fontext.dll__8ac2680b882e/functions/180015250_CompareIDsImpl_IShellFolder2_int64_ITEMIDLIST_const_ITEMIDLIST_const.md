# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x180015250`
- end: `0x180015488`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST@@2@Z`
- size: `568`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015180`

## callees

- `0x180015250`
- `0x180018ac8`
- `0x180018da0`
- `0x18002c8ec`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `PROPSYS!VariantCompare` at `0x180015410`
- `PROPSYS!VariantCompare` at `0x180015410`
- `SHELL32!__imp_ILFree` at `0x180015457`
- `SHELL32!__imp_ILFree` at `0x180015460`
- `SHELL32!__imp_ILFree` at `0x180015457`
- `SHELL32!__imp_ILFree` at `0x180015460`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x180015378`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x1800153f4`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x180015378`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x1800153f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015402`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015402`
- `OLEAUT32!__imp_VariantInit` at `0x1800153af`
- `OLEAUT32!__imp_VariantInit` at `0x1800153e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800153af`
- `OLEAUT32!__imp_VariantInit` at `0x1800153e9`
- `OLEAUT32!__imp_VariantClear` at `0x180015444`
- `OLEAUT32!__imp_VariantClear` at `0x18001544e`
- `OLEAUT32!__imp_VariantClear` at `0x180015444`
- `OLEAUT32!__imp_VariantClear` at `0x18001544e`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(struct IShellFolder2 *a1, __int64 a2, struct _ITEMIDLIST *a3, struct _ITEMIDLIST *a4)
{
  int v7; // ebx
  __int64 cb; // rcx
  ITEMIDLIST *v9; // r14
  _WORD *v10; // rcx
  LPITEMIDLIST v11; // r12
  ITEMIDLIST *v12; // r15
  _WORD *v13; // rcx
  int v14; // eax
  struct IShellFolder2Vtbl *lpVtbl; // rax
  const WCHAR *v16; // rdx
  int v17; // ebx
  struct IShellFolder2Vtbl *v18; // rax
  const WCHAR *v19; // rdx
  int v20; // eax
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-49h] BYREF
  __int64 v23; // [rsp+38h] [rbp-41h]
  VARIANTARG var2; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v26; // [rsp+70h] [rbp-9h] BYREF
  int v27; // [rsp+80h] [rbp+7h]

  v23 = a2;
  v7 = -2147024809;
  if ( a3 && a4 && a3->mkid.cb && a4->mkid.cb )
  {
    if ( a3 == a4 )
    {
      return 0;
    }
    else
    {
      cb = a3->mkid.cb;
      v9 = 0;
      pidl = 0;
      v10 = (USHORT *)((char *)&a3->mkid.cb + cb);
      if ( v10 && *v10 )
      {
        v7 = SHILCloneFirst(a3, &pidl);
        if ( v7 < 0 )
          return (unsigned int)v7;
        v9 = pidl;
        v11 = pidl;
      }
      else
      {
        v11 = a3;
      }
      v12 = 0;
      pidl = 0;
      if ( a4->mkid.cb && (v13 = (USHORT *)((char *)&a4->mkid.cb + a4->mkid.cb)) != 0 && *v13 )
      {
        v14 = SHILCloneFirst(a4, &pidl);
        v12 = pidl;
        v7 = v14;
      }
      else
      {
        pidl = a4;
        v7 = 0;
      }
      if ( v7 >= 0 )
      {
        v27 = 0;
        lpVtbl = a1->lpVtbl;
        v26 = 0;
        v7 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
               a1,
               (unsigned __int16)v23,
               &v26);
        if ( v7 >= 0 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          v17 = 0;
          if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v16) )
            v17 = SHCoInitialize();
          if ( ((int (__fastcall *)(struct IShellFolder2 *, LPITEMIDLIST, __int128 *, VARIANTARG *))a1->lpVtbl->GetDetailsEx)(
                 a1,
                 v11,
                 &v26,
                 &pvarg) < 0 )
            VariantInit(&pvarg);
          v18 = a1->lpVtbl;
          memset(&var2, 0, sizeof(var2));
          if ( ((int (__fastcall *)(struct IShellFolder2 *, LPITEMIDLIST, __int128 *, VARIANTARG *))v18->GetDetailsEx)(
                 a1,
                 pidl,
                 &v26,
                 &var2) < 0 )
            VariantInit(&var2);
          if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v19) && !v17 )
            CoUninitialize();
          v20 = VariantCompare(&pvarg, &var2);
          if ( v20 )
          {
            if ( v20 >= 0 )
              v7 = v20 > 0;
            else
              v7 = 0xFFFF;
          }
          else
          {
            v7 = ILCompareRelIDs(a1, a3, a4, v23);
          }
          VariantClear(&var2);
          VariantClear(&pvarg);
        }
        ILFree(v12);
      }
      ILFree(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015250  push    rbp
0x180015252  push    rbx
0x180015253  push    rsi
0x180015254  push    rdi
0x180015255  push    r12
0x180015257  push    r13
0x180015259  push    r14
0x18001525b  push    r15
0x18001525d  lea     rbp, [rsp-1Fh]
0x180015262  sub     rsp, 98h
0x180015269  mov     rax, cs:__security_cookie
0x180015270  xor     rax, rsp
0x180015273  mov     [rbp+57h+var_48], rax
0x180015277  mov     [rbp+57h+var_98], rdx
0x18001527b  mov     rdi, r9
0x18001527e  xor     edx, edx
0x180015280  mov     rsi, r8
0x180015283  mov     r13, rcx
0x180015286  mov     ebx, 80070057h
0x18001528b  test    r8, r8
0x18001528e  jz      loc_180015466
0x180015294  test    r9, r9
0x180015297  jz      loc_180015466
0x18001529d  cmp     [r8], dx
0x1800152a1  jz      loc_180015466
0x1800152a7  cmp     [r9], dx
0x1800152ab  jz      loc_180015466
0x1800152b1  cmp     r8, r9
0x1800152b4  jnz     short loc_1800152BD
0x1800152b6  mov     ebx, edx
0x1800152b8  jmp     loc_180015466
0x1800152bd  movzx   ecx, word ptr [r8]
0x1800152c1  mov     r14, rdx
0x1800152c4  mov     [rbp+57h+pidl], rdx
0x1800152c8  add     rcx, rsi
0x1800152cb  jz      short loc_1800152F3
0x1800152cd  cmp     [rcx], dx
0x1800152d0  jz      short loc_1800152F3
0x1800152d2  lea     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST **
0x1800152d6  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800152d9  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@@Z; SHILCloneFirst(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x1800152de  xor     edx, edx
0x1800152e0  mov     ebx, eax
0x1800152e2  test    eax, eax
0x1800152e4  js      loc_180015466
0x1800152ea  mov     r14, [rbp+57h+pidl]
0x1800152ee  mov     r12, r14
0x1800152f1  jmp     short loc_1800152F6
0x1800152f3  mov     r12, rsi
0x1800152f6  mov     r15, rdx
0x1800152f9  mov     [rbp+57h+pidl], rdx
0x1800152fd  cmp     [rdi], dx
0x180015300  jz      short loc_180015327
0x180015302  movzx   ecx, word ptr [rdi]
0x180015305  add     rcx, rdi
0x180015308  jz      short loc_180015327
0x18001530a  cmp     [rcx], dx
0x18001530d  jz      short loc_180015327
0x18001530f  lea     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST **
0x180015313  mov     rcx, rdi; struct _ITEMIDLIST *
0x180015316  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@@Z; SHILCloneFirst(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x18001531b  mov     r15, [rbp+57h+pidl]
0x18001531f  mov     ebx, eax
0x180015321  mov     [rbp+57h+pidl], r15
0x180015325  jmp     short loc_18001532D
0x180015327  mov     [rbp+57h+pidl], rdi
0x18001532b  mov     ebx, edx
0x18001532d  test    ebx, ebx
0x18001532f  js      loc_18001545D
0x180015335  movzx   edx, word ptr [rbp+57h+var_98]
0x180015339  lea     r8, [rbp+57h+var_60]
0x18001533d  xor     eax, eax
0x18001533f  xorps   xmm0, xmm0
0x180015342  mov     [rbp+57h+var_50], eax
0x180015345  mov     rcx, r13
0x180015348  mov     rax, [r13+0]
0x18001534c  movups  [rbp+57h+var_60], xmm0
0x180015350  mov     rax, [rax+98h]
0x180015357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001535c  mov     ebx, eax
0x18001535e  test    eax, eax
0x180015360  js      loc_180015454
0x180015366  xor     eax, eax
0x180015368  xorps   xmm0, xmm0
0x18001536b  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001536f  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180015373  xor     ebx, ebx
0x180015375  lea     ecx, [rax+19h]; pszPath
0x180015378  call    cs:__imp_IsAppCompatModeEnabled
0x18001537e  test    eax, eax
0x180015380  jz      short loc_180015389
0x180015382  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180015387  mov     ebx, eax
0x180015389  mov     rcx, [r13+0]
0x18001538d  lea     r9, [rbp+57h+pvarg]
0x180015391  lea     r8, [rbp+57h+var_60]
0x180015395  mov     rdx, r12
0x180015398  mov     rax, [rcx+88h]
0x18001539f  mov     rcx, r13
0x1800153a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a7  test    eax, eax
0x1800153a9  jns     short loc_1800153B5
0x1800153ab  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800153af  call    cs:__imp_VariantInit
0x1800153b5  mov     rdx, [rbp+57h+pidl]
0x1800153b9  lea     r9, [rbp+57h+var2]
0x1800153bd  xor     eax, eax
0x1800153bf  lea     r8, [rbp+57h+var_60]
0x1800153c3  mov     qword ptr [rbp+57h+var2+10h], rax
0x1800153c7  xorps   xmm0, xmm0
0x1800153ca  mov     rax, [r13+0]
0x1800153ce  mov     rcx, r13
0x1800153d1  movups  xmmword ptr [rbp+57h+var2], xmm0
0x1800153d5  mov     rax, [rax+88h]
0x1800153dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e1  test    eax, eax
0x1800153e3  jns     short loc_1800153EF
0x1800153e5  lea     rcx, [rbp+57h+var2]; pvarg
0x1800153e9  call    cs:__imp_VariantInit
0x1800153ef  mov     ecx, 19h; pszPath
0x1800153f4  call    cs:__imp_IsAppCompatModeEnabled
0x1800153fa  test    eax, eax
0x1800153fc  jz      short loc_180015408
0x1800153fe  test    ebx, ebx
0x180015400  jnz     short loc_180015408
0x180015402  call    cs:__imp_CoUninitialize
0x180015408  lea     rdx, [rbp+57h+var2]; var2
0x18001540c  lea     rcx, [rbp+57h+pvarg]; var1
0x180015410  call    cs:__imp_VariantCompare
0x180015416  test    eax, eax
0x180015418  jz      short loc_18001542C
0x18001541a  jns     short loc_180015423
0x18001541c  mov     ebx, 0FFFFh
0x180015421  jmp     short loc_180015440
0x180015423  xor     ebx, ebx
0x180015425  test    eax, eax
0x180015427  setnle  bl
0x18001542a  jmp     short loc_180015440
0x18001542c  mov     r9, [rbp+57h+var_98]
0x180015430  mov     r8, rdi
0x180015433  mov     rdx, rsi
0x180015436  mov     rcx, r13
0x180015439  call    ILCompareRelIDs
0x18001543e  mov     ebx, eax
0x180015440  lea     rcx, [rbp+57h+var2]; pvarg
0x180015444  call    cs:__imp_VariantClear
0x18001544a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001544e  call    cs:__imp_VariantClear
0x180015454  mov     rcx, r15; pidl
0x180015457  call    cs:__imp_ILFree
0x18001545d  mov     rcx, r14; pidl
0x180015460  call    cs:__imp_ILFree
0x180015466  mov     eax, ebx
0x180015468  mov     rcx, [rbp+57h+var_48]
0x18001546c  xor     rcx, rsp; StackCookie
0x18001546f  call    __security_check_cookie
0x180015474  add     rsp, 98h
0x18001547b  pop     r15
0x18001547d  pop     r14
0x18001547f  pop     r13
0x180015481  pop     r12
0x180015483  pop     rdi
0x180015484  pop     rsi
0x180015485  pop     rbx
0x180015486  pop     rbp
0x180015487  retn
```
