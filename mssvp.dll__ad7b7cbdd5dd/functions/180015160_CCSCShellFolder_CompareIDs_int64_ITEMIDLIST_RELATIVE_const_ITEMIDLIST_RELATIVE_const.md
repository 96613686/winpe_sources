# CCSCShellFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180015160`
- end: `0x18001536c`
- name: `?CompareIDs@CCSCShellFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `524`
- prototype: `__int64 __fastcall(CCSCShellFolder *this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003a10`
- `0x180015160`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180015186`
- `OLEAUT32!__imp_VariantInit` at `0x1800151ba`
- `OLEAUT32!__imp_VariantInit` at `0x180015292`
- `OLEAUT32!__imp_VariantInit` at `0x1800152c0`
- `OLEAUT32!__imp_VariantInit` at `0x180015186`
- `OLEAUT32!__imp_VariantInit` at `0x1800151ba`
- `OLEAUT32!__imp_VariantInit` at `0x180015292`
- `OLEAUT32!__imp_VariantInit` at `0x1800152c0`
- `OLEAUT32!__imp_VariantClear` at `0x18001531a`
- `OLEAUT32!__imp_VariantClear` at `0x180015324`
- `OLEAUT32!__imp_VariantClear` at `0x180015330`
- `OLEAUT32!__imp_VariantClear` at `0x18001533a`
- `OLEAUT32!__imp_VariantClear` at `0x180015346`
- `OLEAUT32!__imp_VariantClear` at `0x180015350`
- `OLEAUT32!__imp_VariantClear` at `0x18001531a`
- `OLEAUT32!__imp_VariantClear` at `0x180015324`
- `OLEAUT32!__imp_VariantClear` at `0x180015330`
- `OLEAUT32!__imp_VariantClear` at `0x18001533a`
- `OLEAUT32!__imp_VariantClear` at `0x180015346`
- `OLEAUT32!__imp_VariantClear` at `0x180015350`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015276`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001530c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015276`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001530c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCSCShellFolder::CompareIDs(
        CCSCShellFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  CPidlMgr *v7; // rsi
  int v8; // ebx
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 cchCount2; // rax
  __int64 v13; // rcx
  VARIANTARG v15; // [rsp+30h] [rbp-49h] BYREF
  VARIANTARG v16; // [rsp+48h] [rbp-31h] BYREF
  VARIANTARG lpString2; // [rsp+60h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-1h] BYREF

  VariantInit(&pvarg);
  v7 = (CCSCShellFolder *)((char *)this + 80);
  v8 = CPidlMgr::PropertyDetailFromPIDL(v7, a3, &PKEY_ParsingPath, 8u, &pvarg);
  VariantInit(&lpString2);
  if ( v8 >= 0 )
    v8 = CPidlMgr::PropertyDetailFromPIDL(v7, a4, &PKEY_ParsingPath, 8u, &lpString2);
  v9 = -1;
  if ( pvarg.vt == 8 && lpString2.vt == 8 )
  {
    if ( v8 >= 0 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(pvarg.llVal + 2 * v10) );
      v11 = 2 * v10;
      if ( v10 && *(_WORD *)(v11 + pvarg.llVal - 2) == 47 || *(_WORD *)(v11 + pvarg.llVal - 2) == 92 )
        LODWORD(v10) = v10 - 1;
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( *(_WORD *)(lpString2.llVal + 2 * cchCount2) );
      v13 = 2 * cchCount2;
      if ( cchCount2 && *(_WORD *)(v13 + lpString2.llVal - 2) == 47 || *(_WORD *)(v13 + lpString2.llVal - 2) == 92 )
        LODWORD(cchCount2) = cchCount2 - 1;
      if ( CompareStringW(0x7Fu, 1u, pvarg.bstrVal, v10, lpString2.bstrVal, cchCount2) == 2 )
      {
        v9 = 0;
        goto LABEL_28;
      }
    }
  }
  else
  {
    v8 = -2147418113;
  }
  VariantInit(&v16);
  if ( v8 >= 0 )
    v8 = CPidlMgr::PropertyDetailFromPIDL(v7, a3, &PKEY_ItemPathDisplay, 8u, &v16);
  VariantInit(&v15);
  if ( v8 >= 0
    && (v8 = CPidlMgr::PropertyDetailFromPIDL(v7, a4, &PKEY_ItemPathDisplay, 8u, &v15), v8 >= 0)
    && (v8 = 1, CompareStringW(0x7Fu, 1u, v16.bstrVal, -1, v15.bstrVal, -1) == 1) )
  {
    VariantClear(&v15);
    VariantClear(&v16);
  }
  else
  {
    VariantClear(&v15);
    VariantClear(&v16);
    v9 = v8;
  }
LABEL_28:
  VariantClear(&lpString2);
  VariantClear(&pvarg);
  return v9;
}

```

## disassembly

```asm
0x180015160  push    rbp
0x180015162  push    rbx
0x180015163  push    rsi
0x180015164  push    rdi
0x180015165  push    r12
0x180015167  push    r13
0x180015169  push    r14
0x18001516b  push    r15
0x18001516d  lea     rbp, [rsp-1Fh]
0x180015172  sub     rsp, 98h
0x180015179  mov     rsi, rcx
0x18001517c  mov     r14, r9
0x18001517f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015183  mov     r15, r8
0x180015186  call    cs:__imp_VariantInit
0x18001518c  lea     rax, [rbp+57h+pvarg]
0x180015190  add     rsi, 50h ; 'P'
0x180015194  mov     r13d, 8
0x18001519a  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x18001519f  mov     r9d, r13d; unsigned __int16
0x1800151a2  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x1800151a9  mov     rcx, rsi; this
0x1800151ac  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x1800151af  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x1800151b4  lea     rcx, [rbp+57h+var_70]; pvarg
0x1800151b8  mov     ebx, eax
0x1800151ba  call    cs:__imp_VariantInit
0x1800151c0  xor     r12d, r12d
0x1800151c3  test    ebx, ebx
0x1800151c5  js      short loc_1800151E7
0x1800151c7  lea     rax, [rbp+57h+var_70]
0x1800151cb  mov     r9d, r13d; unsigned __int16
0x1800151ce  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x1800151d5  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x1800151da  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x1800151dd  mov     rcx, rsi; this
0x1800151e0  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x1800151e5  mov     ebx, eax
0x1800151e7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800151eb  cmp     r13w, word ptr [rbp+57h+pvarg]
0x1800151f0  jnz     loc_180015289
0x1800151f6  cmp     r13w, word ptr [rbp+57h+var_70]
0x1800151fb  jnz     loc_180015289
0x180015201  test    ebx, ebx
0x180015203  js      loc_18001528E
0x180015209  mov     r8, qword ptr [rbp+57h+pvarg+8]; lpString1
0x18001520d  mov     r9, rdi
0x180015210  inc     r9
0x180015213  cmp     [r8+r9*2], r12w
0x180015218  jnz     short loc_180015210
0x18001521a  lea     rax, [r9+r9]
0x18001521e  test    r9, r9
0x180015221  jz      short loc_18001522C
0x180015223  cmp     word ptr [rax+r8-2], 2Fh ; '/'
0x18001522a  jz      short loc_180015235
0x18001522c  cmp     word ptr [rax+r8-2], 5Ch ; '\'
0x180015233  jnz     short loc_180015238
0x180015235  dec     r9; cchCount1
0x180015238  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x18001523c  mov     rax, rdi
0x18001523f  inc     rax
0x180015242  cmp     [rdx+rax*2], r12w
0x180015247  jnz     short loc_18001523F
0x180015249  lea     rcx, [rax+rax]
0x18001524d  test    rax, rax
0x180015250  jz      short loc_18001525A
0x180015252  cmp     word ptr [rcx+rdx-2], 2Fh ; '/'
0x180015258  jz      short loc_180015262
0x18001525a  cmp     word ptr [rcx+rdx-2], 5Ch ; '\'
0x180015260  jnz     short loc_180015265
0x180015262  dec     rax
0x180015265  mov     [rsp+0D0h+cchCount2], eax; cchCount2
0x180015269  mov     [rsp+0D0h+lpString2], rdx; lpString2
0x18001526e  mov     edx, 1; dwCmpFlags
0x180015273  lea     ecx, [rdx+7Eh]; Locale
0x180015276  call    cs:__imp_CompareStringW
0x18001527c  cmp     eax, 2
0x18001527f  jnz     short loc_18001528E
0x180015281  mov     edi, r12d
0x180015284  jmp     loc_180015342
0x180015289  mov     ebx, 8000FFFFh
0x18001528e  lea     rcx, [rbp+57h+var_88]; pvarg
0x180015292  call    cs:__imp_VariantInit
0x180015298  test    ebx, ebx
0x18001529a  js      short loc_1800152BC
0x18001529c  lea     rax, [rbp+57h+var_88]
0x1800152a0  mov     r9d, r13d; unsigned __int16
0x1800152a3  lea     r8, PKEY_ItemPathDisplay; struct _tagpropertykey *
0x1800152aa  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x1800152af  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x1800152b2  mov     rcx, rsi; this
0x1800152b5  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x1800152ba  mov     ebx, eax
0x1800152bc  lea     rcx, [rbp+57h+var_A0]; pvarg
0x1800152c0  call    cs:__imp_VariantInit
0x1800152c6  test    ebx, ebx
0x1800152c8  js      short loc_18001532C
0x1800152ca  lea     rax, [rbp+57h+var_A0]
0x1800152ce  mov     r9d, r13d; unsigned __int16
0x1800152d1  lea     r8, PKEY_ItemPathDisplay; struct _tagpropertykey *
0x1800152d8  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x1800152dd  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x1800152e0  mov     rcx, rsi; this
0x1800152e3  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x1800152e8  mov     ebx, eax
0x1800152ea  test    eax, eax
0x1800152ec  js      short loc_18001532C
0x1800152ee  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x1800152f2  mov     ebx, 1
0x1800152f7  mov     r8, qword ptr [rbp+57h+var_88+8]; lpString1
0x1800152fb  mov     r9d, edi; cchCount1
0x1800152fe  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x180015302  mov     edx, ebx; dwCmpFlags
0x180015304  mov     [rsp+0D0h+lpString2], rax; lpString2
0x180015309  lea     ecx, [rbx+7Eh]; Locale
0x18001530c  call    cs:__imp_CompareStringW
0x180015312  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180015316  cmp     eax, ebx
0x180015318  jnz     short loc_180015330
0x18001531a  call    cs:__imp_VariantClear
0x180015320  lea     rcx, [rbp+57h+var_88]; pvarg
0x180015324  call    cs:__imp_VariantClear
0x18001532a  jmp     short loc_180015342
0x18001532c  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180015330  call    cs:__imp_VariantClear
0x180015336  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001533a  call    cs:__imp_VariantClear
0x180015340  mov     edi, ebx
0x180015342  lea     rcx, [rbp+57h+var_70]; pvarg
0x180015346  call    cs:__imp_VariantClear
0x18001534c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015350  call    cs:__imp_VariantClear
0x180015356  mov     eax, edi
0x180015358  add     rsp, 98h
0x18001535f  pop     r15
0x180015361  pop     r14
0x180015363  pop     r13
0x180015365  pop     r12
0x180015367  pop     rdi
0x180015368  pop     rsi
0x180015369  pop     rbx
0x18001536a  pop     rbp
0x18001536b  retn
```
