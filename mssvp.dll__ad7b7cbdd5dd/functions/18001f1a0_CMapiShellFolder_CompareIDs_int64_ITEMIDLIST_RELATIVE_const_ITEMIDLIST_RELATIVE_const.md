# CMapiShellFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x18001f1a0`
- end: `0x18001f3b4`
- name: `?CompareIDs@CMapiShellFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `532`
- prototype: `__int64 __fastcall(CMapiShellFolder *this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003a10`
- `0x18001f1a0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001f1c6`
- `OLEAUT32!__imp_VariantInit` at `0x18001f1d1`
- `OLEAUT32!__imp_VariantInit` at `0x18001f2d4`
- `OLEAUT32!__imp_VariantInit` at `0x18001f303`
- `OLEAUT32!__imp_VariantInit` at `0x18001f1c6`
- `OLEAUT32!__imp_VariantInit` at `0x18001f1d1`
- `OLEAUT32!__imp_VariantInit` at `0x18001f2d4`
- `OLEAUT32!__imp_VariantInit` at `0x18001f303`
- `OLEAUT32!__imp_VariantClear` at `0x18001f35f`
- `OLEAUT32!__imp_VariantClear` at `0x18001f36a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f376`
- `OLEAUT32!__imp_VariantClear` at `0x18001f381`
- `OLEAUT32!__imp_VariantClear` at `0x18001f38d`
- `OLEAUT32!__imp_VariantClear` at `0x18001f398`
- `OLEAUT32!__imp_VariantClear` at `0x18001f35f`
- `OLEAUT32!__imp_VariantClear` at `0x18001f36a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f376`
- `OLEAUT32!__imp_VariantClear` at `0x18001f381`
- `OLEAUT32!__imp_VariantClear` at `0x18001f38d`
- `OLEAUT32!__imp_VariantClear` at `0x18001f398`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f2b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f350`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f2b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f350`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapiShellFolder::CompareIDs(
        CMapiShellFolder *this,
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
  VariantInit(&lpString2);
  v7 = (CMapiShellFolder *)((char *)this + 104);
  v8 = CPidlMgr::PropertyDetailFromPIDL(v7, a3, &PKEY_ParsingPath, 8u, &pvarg);
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
0x18001f1a0  push    rbp
0x18001f1a2  push    rbx
0x18001f1a3  push    rsi
0x18001f1a4  push    rdi
0x18001f1a5  push    r12
0x18001f1a7  push    r13
0x18001f1a9  push    r14
0x18001f1ab  push    r15
0x18001f1ad  lea     rbp, [rsp-1Fh]
0x18001f1b2  sub     rsp, 98h
0x18001f1b9  mov     r14, r9
0x18001f1bc  mov     r15, r8
0x18001f1bf  mov     rsi, rcx
0x18001f1c2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f1c6  call    cs:__imp_VariantInit
0x18001f1cc  nop
0x18001f1cd  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001f1d1  call    cs:__imp_VariantInit
0x18001f1d7  nop
0x18001f1d8  add     rsi, 68h ; 'h'
0x18001f1dc  mov     r13d, 8
0x18001f1e2  mov     r9d, r13d; unsigned __int16
0x18001f1e5  lea     rax, [rbp+57h+pvarg]
0x18001f1e9  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x18001f1ee  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x18001f1f5  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x18001f1f8  mov     rcx, rsi; this
0x18001f1fb  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001f200  mov     ebx, eax
0x18001f202  xor     r12d, r12d
0x18001f205  test    eax, eax
0x18001f207  js      short loc_18001F229
0x18001f209  mov     r9d, r13d; unsigned __int16
0x18001f20c  lea     rax, [rbp+57h+var_70]
0x18001f210  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x18001f215  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x18001f21c  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x18001f21f  mov     rcx, rsi; this
0x18001f222  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001f227  mov     ebx, eax
0x18001f229  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f22d  cmp     r13w, word ptr [rbp+57h+pvarg]
0x18001f232  jnz     loc_18001F2CB
0x18001f238  cmp     r13w, word ptr [rbp+57h+var_70]
0x18001f23d  jnz     loc_18001F2CB
0x18001f243  test    ebx, ebx
0x18001f245  js      loc_18001F2D0
0x18001f24b  mov     r8, qword ptr [rbp+57h+pvarg+8]; lpString1
0x18001f24f  mov     r9, rdi
0x18001f252  inc     r9
0x18001f255  cmp     [r8+r9*2], r12w
0x18001f25a  jnz     short loc_18001F252
0x18001f25c  lea     rax, [r9+r9]
0x18001f260  test    r9, r9
0x18001f263  jz      short loc_18001F26E
0x18001f265  cmp     word ptr [rax+r8-2], 2Fh ; '/'
0x18001f26c  jz      short loc_18001F277
0x18001f26e  cmp     word ptr [rax+r8-2], 5Ch ; '\'
0x18001f275  jnz     short loc_18001F27A
0x18001f277  dec     r9; cchCount1
0x18001f27a  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x18001f27e  mov     rax, rdi
0x18001f281  inc     rax
0x18001f284  cmp     [rdx+rax*2], r12w
0x18001f289  jnz     short loc_18001F281
0x18001f28b  lea     rcx, [rax+rax]
0x18001f28f  test    rax, rax
0x18001f292  jz      short loc_18001F29C
0x18001f294  cmp     word ptr [rcx+rdx-2], 2Fh ; '/'
0x18001f29a  jz      short loc_18001F2A4
0x18001f29c  cmp     word ptr [rcx+rdx-2], 5Ch ; '\'
0x18001f2a2  jnz     short loc_18001F2A7
0x18001f2a4  dec     rax
0x18001f2a7  mov     [rsp+0D0h+cchCount2], eax; cchCount2
0x18001f2ab  mov     [rsp+0D0h+lpString2], rdx; lpString2
0x18001f2b0  mov     edx, 1; dwCmpFlags
0x18001f2b5  lea     ecx, [rdx+7Eh]; Locale
0x18001f2b8  call    cs:__imp_CompareStringW
0x18001f2be  cmp     eax, 2
0x18001f2c1  jnz     short loc_18001F2D0
0x18001f2c3  mov     edi, r12d
0x18001f2c6  jmp     loc_18001F389
0x18001f2cb  mov     ebx, 8000FFFFh
0x18001f2d0  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001f2d4  call    cs:__imp_VariantInit
0x18001f2da  nop
0x18001f2db  test    ebx, ebx
0x18001f2dd  js      short loc_18001F2FF
0x18001f2df  mov     r9d, r13d; unsigned __int16
0x18001f2e2  lea     rax, [rbp+57h+var_88]
0x18001f2e6  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x18001f2eb  lea     r8, PKEY_ItemPathDisplay; struct _tagpropertykey *
0x18001f2f2  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x18001f2f5  mov     rcx, rsi; this
0x18001f2f8  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001f2fd  mov     ebx, eax
0x18001f2ff  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001f303  call    cs:__imp_VariantInit
0x18001f309  nop
0x18001f30a  test    ebx, ebx
0x18001f30c  js      short loc_18001F372
0x18001f30e  mov     r9d, r13d; unsigned __int16
0x18001f311  lea     rax, [rbp+57h+var_A0]
0x18001f315  mov     [rsp+0D0h+lpString2], rax; struct tagVARIANT *
0x18001f31a  lea     r8, PKEY_ItemPathDisplay; struct _tagpropertykey *
0x18001f321  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x18001f324  mov     rcx, rsi; this
0x18001f327  call    ?PropertyDetailFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; CPidlMgr::PropertyDetailFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001f32c  mov     ebx, eax
0x18001f32e  test    eax, eax
0x18001f330  js      short loc_18001F372
0x18001f332  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x18001f336  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x18001f33a  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18001f33f  mov     r9d, edi; cchCount1
0x18001f342  mov     r8, qword ptr [rbp+57h+var_88+8]; lpString1
0x18001f346  mov     ebx, 1
0x18001f34b  mov     edx, ebx; dwCmpFlags
0x18001f34d  lea     ecx, [rbx+7Eh]; Locale
0x18001f350  call    cs:__imp_CompareStringW
0x18001f356  nop
0x18001f357  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001f35b  cmp     eax, ebx
0x18001f35d  jnz     short loc_18001F376
0x18001f35f  call    cs:__imp_VariantClear
0x18001f365  nop
0x18001f366  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001f36a  call    cs:__imp_VariantClear
0x18001f370  jmp     short loc_18001F389
0x18001f372  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001f376  call    cs:__imp_VariantClear
0x18001f37c  nop
0x18001f37d  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001f381  call    cs:__imp_VariantClear
0x18001f387  mov     edi, ebx
0x18001f389  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001f38d  call    cs:__imp_VariantClear
0x18001f393  nop
0x18001f394  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f398  call    cs:__imp_VariantClear
0x18001f39e  mov     eax, edi
0x18001f3a0  add     rsp, 98h
0x18001f3a7  pop     r15
0x18001f3a9  pop     r14
0x18001f3ab  pop     r13
0x18001f3ad  pop     r12
0x18001f3af  pop     rdi
0x18001f3b0  pop     rsi
0x18001f3b1  pop     rbx
0x18001f3b2  pop     rbp
0x18001f3b3  retn
```
