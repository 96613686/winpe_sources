# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)

- ea: `0x18004d4cc`
- end: `0x18004d7a3`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z`
- size: `727`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeInfo *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18008952c`

## callees

- `0x18004a660`
- `0x18004d4cc`
- `0x18004d7ac`
- `0x1800585d0`
- `0x180089124`
- `0x18008916c`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004d69f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d69f`
- `OLEAUT32!__imp_VariantCopy` at `0x18004d63f`
- `OLEAUT32!__imp_VariantCopy` at `0x18004d63f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004d5b0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004d5b0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004d75b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004d75b`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Create(
        struct ICreateTypeLib *a1,
        struct ITypeInfo *a2,
        struct CTypeLibWrapper **a3)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  CHashTable *v5; // rsi
  HRESULT (__stdcall *GetTypeAttr)(ITypeInfo *, TYPEATTR **); // rax
  SAFEARRAY *v7; // r15
  HRESULT v8; // ebx
  ULONG v9; // r14d
  unsigned int i; // r12d
  SAFEARRAY *v11; // rax
  int v12; // eax
  __int64 v13; // r12
  unsigned int j; // r13d
  CTypeLibWrapper *v15; // rax
  CTypeLibWrapper *v16; // rax
  CTypeLibWrapper *v17; // rbx
  struct CTypeLibWrapper **v18; // rax
  unsigned int v19; // edx
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-20h] BYREF
  CHashTable *v23; // [rsp+50h] [rbp-18h] BYREF
  VARIANTARG *pvData; // [rsp+58h] [rbp-10h]
  const VARIANTARG **v26; // [rsp+B8h] [rbp+50h] BYREF
  struct CTypeLibWrapper **v27; // [rsp+C0h] [rbp+58h]
  __int64 v28; // [rsp+C8h] [rbp+60h] BYREF

  v27 = a3;
  lpVtbl = a2->lpVtbl;
  v5 = 0;
  rgsabound = 0;
  bstrString = 0;
  v28 = 0;
  GetTypeAttr = lpVtbl->GetTypeAttr;
  v7 = 0;
  v23 = 0;
  v26 = 0;
  *a3 = 0;
  v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))GetTypeAttr)(a2, &v28);
  if ( v8 >= 0 )
  {
    v9 = 0;
    for ( i = 0; i < *(unsigned __int16 *)(v28 + 50); ++i )
    {
      v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, const VARIANTARG ***))a2->lpVtbl->GetVarDesc)(
             a2,
             i,
             &v26);
      if ( v8 < 0 )
        goto LABEL_25;
      if ( *((_DWORD *)v26 + 15) == 2 )
        ++v9;
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseVarDesc)(a2);
      v26 = 0;
    }
    if ( !v9 )
    {
      v8 = 1;
      goto LABEL_25;
    }
    rgsabound.cElements = v9;
    rgsabound.lLbound = 0;
    v11 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v7 = v11;
    if ( !v11 )
      goto LABEL_24;
    pvData = (VARIANTARG *)v11->pvData;
    v12 = CHashTable::Create(v9, &v23);
    v5 = v23;
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_25;
    v13 = 0;
    for ( j = 0; j < *(unsigned __int16 *)(v28 + 50); ++j )
    {
      v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, const VARIANTARG ***))a2->lpVtbl->GetVarDesc)(
             a2,
             j,
             &v26);
      if ( v8 < 0 )
        goto LABEL_25;
      if ( *((_DWORD *)v26 + 15) == 2 )
      {
        v8 = VariantCopy(&pvData[v13], v26[2]);
        if ( v8 < 0 )
          goto LABEL_25;
        v8 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->GetDocumentation)(
               a2,
               *(unsigned int *)v26,
               &bstrString,
               0,
               0,
               0);
        if ( v8 < 0 )
          goto LABEL_25;
        v8 = CHashTable::Add(v5, bstrString);
        SysFreeString(bstrString);
        if ( v8 < 0 )
          goto LABEL_25;
        v13 = (unsigned int)(v13 + 1);
        if ( (_DWORD)v13 == v9 )
          break;
      }
      ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseVarDesc)(a2);
      v26 = 0;
    }
    v15 = (CTypeLibWrapper *)operator new(0x60u);
    if ( v15 && (v16 = CTypeLibWrapper::CTypeLibWrapper(v15), (v17 = v16) != 0) )
    {
      *((_DWORD *)v16 + 3) = v9;
      *((_QWORD *)v16 + 3) = v7;
      v7 = 0;
      *((_QWORD *)v16 + 2) = v5;
      v5 = 0;
      ((void (__fastcall *)(struct ICreateTypeLib *))a1->lpVtbl->AddRef)(a1);
      v18 = v27;
      *((_QWORD *)v17 + 4) = a1;
      *v18 = v17;
      v8 = 0;
    }
    else
    {
LABEL_24:
      v8 = -2147024882;
    }
  }
LABEL_25:
  v19 = v28;
  if ( v28 )
    ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseTypeAttr)(a2);
  if ( v7 )
    SafeArrayDestroy(v7);
  if ( v5 )
    CHashTable::`scalar deleting destructor'(v5, v19);
  if ( v26 )
    ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseVarDesc)(a2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004d4cc  mov     [rsp-40h+arg_10], r8
0x18004d4d1  mov     [rsp-40h+arg_0], rcx
0x18004d4d6  push    rbp
0x18004d4d7  push    rbx
0x18004d4d8  push    rsi
0x18004d4d9  push    rdi
0x18004d4da  push    r12
0x18004d4dc  push    r13
0x18004d4de  push    r14
0x18004d4e0  push    r15
0x18004d4e2  mov     rbp, rsp
0x18004d4e5  sub     rsp, 68h
0x18004d4e9  mov     rax, [rdx]
0x18004d4ec  mov     rdi, rdx
0x18004d4ef  xor     esi, esi
0x18004d4f1  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18004d4f9  lea     rdx, [rbp+arg_18]
0x18004d4fd  mov     [rbp+bstrString], 0
0x18004d505  mov     rcx, rdi
0x18004d508  mov     [rbp+arg_18], 0
0x18004d510  mov     rax, [rax+18h]
0x18004d514  xor     r15d, r15d
0x18004d517  mov     [rbp+var_18], rsi
0x18004d51b  mov     [rbp+arg_8], rsi
0x18004d51f  mov     [r8], rsi
0x18004d522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d527  mov     ebx, eax
0x18004d529  test    eax, eax
0x18004d52b  js      loc_18004D738
0x18004d531  xor     r14d, r14d
0x18004d534  lea     r13d, [r15+1]
0x18004d538  xor     r12d, r12d
0x18004d53b  mov     rax, [rbp+arg_18]
0x18004d53f  movzx   ecx, word ptr [rax+32h]
0x18004d543  cmp     r12d, ecx
0x18004d546  jnb     short loc_18004D590
0x18004d548  mov     rax, [rdi]
0x18004d54b  lea     r8, [rbp+arg_8]
0x18004d54f  mov     edx, r12d
0x18004d552  mov     rcx, rdi
0x18004d555  mov     rax, [rax+30h]
0x18004d559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d55e  mov     ebx, eax
0x18004d560  test    eax, eax
0x18004d562  js      loc_18004D738
0x18004d568  mov     rdx, [rbp+arg_8]
0x18004d56c  cmp     dword ptr [rdx+3Ch], 2
0x18004d570  jnz     short loc_18004D575
0x18004d572  add     r14d, r13d
0x18004d575  mov     rax, [rdi]
0x18004d578  mov     rcx, rdi
0x18004d57b  mov     rax, [rax+0A8h]
0x18004d582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d587  add     r12d, r13d
0x18004d58a  mov     [rbp+arg_8], rsi
0x18004d58e  jmp     short loc_18004D53B
0x18004d590  test    r14d, r14d
0x18004d593  jnz     short loc_18004D59D
0x18004d595  mov     ebx, r13d
0x18004d598  jmp     loc_18004D738
0x18004d59d  mov     ecx, 0Ch; vt
0x18004d5a2  mov     [rbp+rgsabound.cElements], r14d
0x18004d5a6  lea     r8, [rbp+rgsabound]; rgsabound
0x18004d5aa  mov     [rbp+rgsabound.lLbound], esi
0x18004d5ad  mov     edx, r13d; cDims
0x18004d5b0  call    cs:__imp_SafeArrayCreate
0x18004d5b7  nop     dword ptr [rax+rax+00h]
0x18004d5bc  mov     r15, rax
0x18004d5bf  test    rax, rax
0x18004d5c2  jz      loc_18004D733
0x18004d5c8  mov     rax, [rax+10h]
0x18004d5cc  lea     rdx, [rbp+var_18]; struct CHashTable **
0x18004d5d0  mov     ecx, r14d; unsigned int
0x18004d5d3  mov     [rbp+var_10], rax
0x18004d5d7  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18004d5dc  mov     rsi, [rbp+var_18]
0x18004d5e0  mov     ebx, eax
0x18004d5e2  test    eax, eax
0x18004d5e4  js      loc_18004D738
0x18004d5ea  xor     r12d, r12d
0x18004d5ed  xor     r13d, r13d
0x18004d5f0  mov     rax, [rbp+arg_18]
0x18004d5f4  movzx   ecx, word ptr [rax+32h]
0x18004d5f8  cmp     r13d, ecx
0x18004d5fb  jnb     loc_18004D6E1
0x18004d601  mov     rax, [rdi]
0x18004d604  lea     r8, [rbp+arg_8]
0x18004d608  mov     edx, r13d
0x18004d60b  mov     rcx, rdi
0x18004d60e  mov     rax, [rax+30h]
0x18004d612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d617  mov     ebx, eax
0x18004d619  test    eax, eax
0x18004d61b  js      loc_18004D738
0x18004d621  mov     rdx, [rbp+arg_8]
0x18004d625  cmp     dword ptr [rdx+3Ch], 2
0x18004d629  jnz     loc_18004D6BF
0x18004d62f  mov     rax, [rbp+var_10]
0x18004d633  lea     rcx, [r12+r12*2]
0x18004d637  mov     rdx, [rdx+10h]; pvargSrc
0x18004d63b  lea     rcx, [rax+rcx*8]; pvargDest
0x18004d63f  call    cs:__imp_VariantCopy
0x18004d646  nop     dword ptr [rax+rax+00h]
0x18004d64b  mov     ebx, eax
0x18004d64d  test    eax, eax
0x18004d64f  js      loc_18004D738
0x18004d655  mov     rax, [rdi]
0x18004d658  lea     r8, [rbp+bstrString]
0x18004d65c  mov     rdx, [rbp+arg_8]
0x18004d660  xor     r9d, r9d
0x18004d663  mov     [rsp+68h+var_40], 0
0x18004d66c  mov     rcx, rdi
0x18004d66f  mov     [rsp+68h+var_48], 0
0x18004d678  mov     rax, [rax+60h]
0x18004d67c  mov     edx, [rdx]
0x18004d67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d683  mov     ebx, eax
0x18004d685  test    eax, eax
0x18004d687  js      loc_18004D738
0x18004d68d  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18004d691  mov     rcx, rsi; this
0x18004d694  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x18004d699  mov     rcx, [rbp+bstrString]; bstrString
0x18004d69d  mov     ebx, eax
0x18004d69f  call    cs:__imp_SysFreeString
0x18004d6a6  nop     dword ptr [rax+rax+00h]
0x18004d6ab  test    ebx, ebx
0x18004d6ad  js      loc_18004D738
0x18004d6b3  inc     r12d
0x18004d6b6  cmp     r12d, r14d
0x18004d6b9  jz      short loc_18004D6E1
0x18004d6bb  mov     rdx, [rbp+arg_8]
0x18004d6bf  mov     rax, [rdi]
0x18004d6c2  mov     rcx, rdi
0x18004d6c5  mov     rax, [rax+0A8h]
0x18004d6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6d1  inc     r13d
0x18004d6d4  mov     [rbp+arg_8], 0
0x18004d6dc  jmp     loc_18004D5F0
0x18004d6e1  mov     ecx, 60h ; '`'; Size
0x18004d6e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d6eb  test    rax, rax
0x18004d6ee  jz      short loc_18004D733
0x18004d6f0  mov     rcx, rax; this
0x18004d6f3  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18004d6f8  mov     rbx, rax
0x18004d6fb  test    rax, rax
0x18004d6fe  jz      short loc_18004D733
0x18004d700  mov     [rax+0Ch], r14d
0x18004d704  mov     r14, [rbp+arg_0]
0x18004d708  mov     [rax+18h], r15
0x18004d70c  xor     r15d, r15d
0x18004d70f  mov     [rax+10h], rsi
0x18004d713  xor     esi, esi
0x18004d715  mov     rcx, [r14]
0x18004d718  mov     rax, [rcx+8]
0x18004d71c  mov     rcx, r14
0x18004d71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d724  mov     rax, [rbp+arg_10]
0x18004d728  mov     [rbx+20h], r14
0x18004d72c  mov     [rax], rbx
0x18004d72f  xor     ebx, ebx
0x18004d731  jmp     short loc_18004D738
0x18004d733  mov     ebx, 8007000Eh
0x18004d738  mov     rdx, [rbp+arg_18]
0x18004d73c  test    rdx, rdx
0x18004d73f  jz      short loc_18004D753
0x18004d741  mov     rax, [rdi]
0x18004d744  mov     rcx, rdi
0x18004d747  mov     rax, [rax+98h]
0x18004d74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d753  test    r15, r15
0x18004d756  jz      short loc_18004D767
0x18004d758  mov     rcx, r15; psa
0x18004d75b  call    cs:__imp_SafeArrayDestroy
0x18004d762  nop     dword ptr [rax+rax+00h]
0x18004d767  test    rsi, rsi
0x18004d76a  jz      short loc_18004D774
0x18004d76c  mov     rcx, rsi; this
0x18004d76f  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x18004d774  mov     rdx, [rbp+arg_8]
0x18004d778  test    rdx, rdx
0x18004d77b  jz      short loc_18004D78F
0x18004d77d  mov     rax, [rdi]
0x18004d780  mov     rcx, rdi
0x18004d783  mov     rax, [rax+0A8h]
0x18004d78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d78f  mov     eax, ebx
0x18004d791  add     rsp, 68h
0x18004d795  pop     r15
0x18004d797  pop     r14
0x18004d799  pop     r13
0x18004d79b  pop     r12
0x18004d79d  pop     rdi
0x18004d79e  pop     rsi
0x18004d79f  pop     rbx
0x18004d7a0  pop     rbp
0x18004d7a1  retn
```
