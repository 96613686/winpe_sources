# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x18001244c`
- end: `0x180012671`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST_RELATIVE@@2@Z`
- size: `549`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800123b8`

## callees

- `0x180008034`
- `0x18001244c`
- `0x180013054`
- `0x18001372c`
- `0x180048054`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180012640`
- `SHELL32!__imp_ILFree` at `0x180012649`
- `SHELL32!__imp_ILFree` at `0x180012640`
- `SHELL32!__imp_ILFree` at `0x180012649`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x180012561`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x1800125dd`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x180012561`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x1800125dd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800125eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800125eb`
- `PROPSYS!VariantCompare` at `0x1800125f9`
- `PROPSYS!VariantCompare` at `0x1800125f9`
- `OLEAUT32!__imp_VariantInit` at `0x180012598`
- `OLEAUT32!__imp_VariantInit` at `0x1800125d2`
- `OLEAUT32!__imp_VariantInit` at `0x180012598`
- `OLEAUT32!__imp_VariantInit` at `0x1800125d2`
- `OLEAUT32!__imp_VariantClear` at `0x18001262d`
- `OLEAUT32!__imp_VariantClear` at `0x180012637`
- `OLEAUT32!__imp_VariantClear` at `0x18001262d`
- `OLEAUT32!__imp_VariantClear` at `0x180012637`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(
        struct IShellFolder2 *a1,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  ITEMIDLIST *v4; // r15
  int v8; // ebx
  ITEMIDLIST *v9; // r14
  const struct _ITEMIDLIST_RELATIVE *v10; // rcx
  struct _ITEMID_CHILD *v11; // r12
  const struct _ITEMIDLIST_RELATIVE *v12; // rcx
  struct IShellFolder2Vtbl *lpVtbl; // rax
  const WCHAR *v14; // rdx
  int v15; // ebx
  struct IShellFolder2Vtbl *v16; // rax
  const WCHAR *v17; // rdx
  int v18; // eax
  struct _ITEMID_CHILD *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h]
  VARIANTARG var2; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v24; // [rsp+70h] [rbp-9h] BYREF
  int v25; // [rsp+80h] [rbp+7h]

  v4 = 0;
  v21 = a2;
  v8 = -2147024809;
  if ( a3 && a4 && *(_WORD *)a3 && *(_WORD *)a4 )
  {
    if ( a3 == a4 )
      return 0;
    v20 = 0;
    v9 = 0;
    if ( (unsigned int)ILIsChild(a3) )
    {
      v11 = a3;
    }
    else
    {
      v8 = SHILCloneFirst(v10, &v20);
      if ( v8 < 0 )
        return (unsigned int)v8;
      v9 = (ITEMIDLIST *)v20;
      v11 = v20;
    }
    v20 = 0;
    if ( (unsigned int)ILIsChild(a4) )
    {
      v20 = a4;
    }
    else
    {
      v8 = SHILCloneFirst(v12, &v20);
      if ( v8 < 0 )
      {
LABEL_32:
        ILFree(v9);
        return (unsigned int)v8;
      }
      v4 = (ITEMIDLIST *)v20;
    }
    v25 = 0;
    lpVtbl = a1->lpVtbl;
    v24 = 0;
    v8 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
           a1,
           (unsigned __int16)v21,
           &v24);
    if ( v8 >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v15 = 0;
      if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v14) )
        v15 = SHCoInitialize();
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))a1->lpVtbl->GetDetailsEx)(
             a1,
             v11,
             &v24,
             &pvarg) < 0 )
        VariantInit(&pvarg);
      v16 = a1->lpVtbl;
      memset(&var2, 0, sizeof(var2));
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))v16->GetDetailsEx)(
             a1,
             v20,
             &v24,
             &var2) < 0 )
        VariantInit(&var2);
      if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v17) && !v15 )
        CoUninitialize();
      v18 = VariantCompare(&pvarg, &var2);
      if ( v18 )
      {
        if ( v18 >= 0 )
          v8 = v18 > 0;
        else
          v8 = 0xFFFF;
      }
      else
      {
        v8 = ILCompareRelIDs(a1, a3, a4, v21);
      }
      VariantClear(&var2);
      VariantClear(&pvarg);
    }
    ILFree(v4);
    goto LABEL_32;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001244c  push    rbp
0x18001244e  push    rbx
0x18001244f  push    rsi
0x180012450  push    rdi
0x180012451  push    r12
0x180012453  push    r13
0x180012455  push    r14
0x180012457  push    r15
0x180012459  lea     rbp, [rsp-1Fh]
0x18001245e  sub     rsp, 98h
0x180012465  mov     rax, cs:__security_cookie
0x18001246c  xor     rax, rsp
0x18001246f  mov     [rbp+57h+var_48], rax
0x180012473  xor     r15d, r15d
0x180012476  mov     [rbp+57h+var_98], rdx
0x18001247a  mov     rdi, r9
0x18001247d  mov     rsi, r8
0x180012480  mov     r13, rcx
0x180012483  mov     ebx, 80070057h
0x180012488  test    r8, r8
0x18001248b  jz      loc_18001264F
0x180012491  test    r9, r9
0x180012494  jz      loc_18001264F
0x18001249a  cmp     [r8], r15w
0x18001249e  jz      loc_18001264F
0x1800124a4  cmp     [r9], r15w
0x1800124a8  jz      loc_18001264F
0x1800124ae  cmp     r8, r9
0x1800124b1  jnz     short loc_1800124BB
0x1800124b3  mov     ebx, r15d
0x1800124b6  jmp     loc_18001264F
0x1800124bb  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800124be  mov     [rbp+57h+var_A0], r15
0x1800124c2  mov     r14, r15
0x1800124c5  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x1800124ca  test    eax, eax
0x1800124cc  jz      short loc_1800124D3
0x1800124ce  mov     r12, rsi
0x1800124d1  jmp     short loc_1800124ED
0x1800124d3  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x1800124d7  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x1800124dc  mov     ebx, eax
0x1800124de  test    eax, eax
0x1800124e0  js      loc_18001264F
0x1800124e6  mov     r14, [rbp+57h+var_A0]
0x1800124ea  mov     r12, r14
0x1800124ed  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x1800124f0  mov     [rbp+57h+var_A0], r15
0x1800124f4  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x1800124f9  test    eax, eax
0x1800124fb  jz      short loc_180012503
0x1800124fd  mov     [rbp+57h+var_A0], rdi
0x180012501  jmp     short loc_18001251E
0x180012503  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x180012507  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18001250c  mov     ebx, eax
0x18001250e  test    eax, eax
0x180012510  js      loc_180012646
0x180012516  mov     r15, [rbp+57h+var_A0]
0x18001251a  mov     [rbp+57h+var_A0], r15
0x18001251e  movzx   edx, word ptr [rbp+57h+var_98]
0x180012522  lea     r8, [rbp+57h+var_60]
0x180012526  xor     eax, eax
0x180012528  xorps   xmm0, xmm0
0x18001252b  mov     [rbp+57h+var_50], eax
0x18001252e  mov     rcx, r13
0x180012531  mov     rax, [r13+0]
0x180012535  movups  [rbp+57h+var_60], xmm0
0x180012539  mov     rax, [rax+98h]
0x180012540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012545  mov     ebx, eax
0x180012547  test    eax, eax
0x180012549  js      loc_18001263D
0x18001254f  xor     eax, eax
0x180012551  xorps   xmm0, xmm0
0x180012554  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180012558  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001255c  xor     ebx, ebx
0x18001255e  lea     ecx, [rax+19h]; pszPath
0x180012561  call    cs:__imp_IsAppCompatModeEnabled
0x180012567  test    eax, eax
0x180012569  jz      short loc_180012572
0x18001256b  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180012570  mov     ebx, eax
0x180012572  mov     rcx, [r13+0]
0x180012576  lea     r9, [rbp+57h+pvarg]
0x18001257a  lea     r8, [rbp+57h+var_60]
0x18001257e  mov     rdx, r12
0x180012581  mov     rax, [rcx+88h]
0x180012588  mov     rcx, r13
0x18001258b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012590  test    eax, eax
0x180012592  jns     short loc_18001259E
0x180012594  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012598  call    cs:__imp_VariantInit
0x18001259e  mov     rdx, [rbp+57h+var_A0]
0x1800125a2  lea     r9, [rbp+57h+var2]
0x1800125a6  xor     eax, eax
0x1800125a8  lea     r8, [rbp+57h+var_60]
0x1800125ac  mov     qword ptr [rbp+57h+var2+10h], rax
0x1800125b0  xorps   xmm0, xmm0
0x1800125b3  mov     rax, [r13+0]
0x1800125b7  mov     rcx, r13
0x1800125ba  movups  xmmword ptr [rbp+57h+var2], xmm0
0x1800125be  mov     rax, [rax+88h]
0x1800125c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ca  test    eax, eax
0x1800125cc  jns     short loc_1800125D8
0x1800125ce  lea     rcx, [rbp+57h+var2]; pvarg
0x1800125d2  call    cs:__imp_VariantInit
0x1800125d8  mov     ecx, 19h; pszPath
0x1800125dd  call    cs:__imp_IsAppCompatModeEnabled
0x1800125e3  test    eax, eax
0x1800125e5  jz      short loc_1800125F1
0x1800125e7  test    ebx, ebx
0x1800125e9  jnz     short loc_1800125F1
0x1800125eb  call    cs:__imp_CoUninitialize
0x1800125f1  lea     rdx, [rbp+57h+var2]; var2
0x1800125f5  lea     rcx, [rbp+57h+pvarg]; var1
0x1800125f9  call    cs:__imp_VariantCompare
0x1800125ff  test    eax, eax
0x180012601  jz      short loc_180012615
0x180012603  jns     short loc_18001260C
0x180012605  mov     ebx, 0FFFFh
0x18001260a  jmp     short loc_180012629
0x18001260c  xor     ebx, ebx
0x18001260e  test    eax, eax
0x180012610  setnle  bl
0x180012613  jmp     short loc_180012629
0x180012615  mov     r9, [rbp+57h+var_98]
0x180012619  mov     r8, rdi
0x18001261c  mov     rdx, rsi
0x18001261f  mov     rcx, r13
0x180012622  call    ILCompareRelIDs
0x180012627  mov     ebx, eax
0x180012629  lea     rcx, [rbp+57h+var2]; pvarg
0x18001262d  call    cs:__imp_VariantClear
0x180012633  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012637  call    cs:__imp_VariantClear
0x18001263d  mov     rcx, r15; pidl
0x180012640  call    cs:__imp_ILFree
0x180012646  mov     rcx, r14; pidl
0x180012649  call    cs:__imp_ILFree
0x18001264f  mov     eax, ebx
0x180012651  mov     rcx, [rbp+57h+var_48]
0x180012655  xor     rcx, rsp; StackCookie
0x180012658  call    __security_check_cookie
0x18001265d  add     rsp, 98h
0x180012664  pop     r15
0x180012666  pop     r14
0x180012668  pop     r13
0x18001266a  pop     r12
0x18001266c  pop     rdi
0x18001266d  pop     rsi
0x18001266e  pop     rbx
0x18001266f  pop     rbp
0x180012670  retn
```
