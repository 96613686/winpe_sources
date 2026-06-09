# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)

- ea: `0x18004c838`
- end: `0x18004caf6`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeInfo *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800876f8`

## callees

- `0x180049bcc`
- `0x18004c838`
- `0x18004cafc`
- `0x1800576a0`
- `0x180087314`
- `0x18008735c`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004c9ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c9ff`
- `OLEAUT32!__imp_VariantCopy` at `0x18004c9a5`
- `OLEAUT32!__imp_VariantCopy` at `0x18004c9a5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004c91c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004c91c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004cab5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004cab5`

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
0x18004c838  mov     [rsp-40h+arg_10], r8
0x18004c83d  mov     [rsp-40h+arg_0], rcx
0x18004c842  push    rbp
0x18004c843  push    rbx
0x18004c844  push    rsi
0x18004c845  push    rdi
0x18004c846  push    r12
0x18004c848  push    r13
0x18004c84a  push    r14
0x18004c84c  push    r15
0x18004c84e  mov     rbp, rsp
0x18004c851  sub     rsp, 68h
0x18004c855  mov     rax, [rdx]
0x18004c858  mov     rdi, rdx
0x18004c85b  xor     esi, esi
0x18004c85d  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18004c865  lea     rdx, [rbp+arg_18]
0x18004c869  mov     [rbp+bstrString], 0
0x18004c871  mov     rcx, rdi
0x18004c874  mov     [rbp+arg_18], 0
0x18004c87c  mov     rax, [rax+18h]
0x18004c880  xor     r15d, r15d
0x18004c883  mov     [rbp+var_18], rsi
0x18004c887  mov     [rbp+arg_8], rsi
0x18004c88b  mov     [r8], rsi
0x18004c88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c893  mov     ebx, eax
0x18004c895  test    eax, eax
0x18004c897  js      loc_18004CA92
0x18004c89d  xor     r14d, r14d
0x18004c8a0  lea     r13d, [r15+1]
0x18004c8a4  xor     r12d, r12d
0x18004c8a7  mov     rax, [rbp+arg_18]
0x18004c8ab  movzx   ecx, word ptr [rax+32h]
0x18004c8af  cmp     r12d, ecx
0x18004c8b2  jnb     short loc_18004C8FC
0x18004c8b4  mov     rax, [rdi]
0x18004c8b7  lea     r8, [rbp+arg_8]
0x18004c8bb  mov     edx, r12d
0x18004c8be  mov     rcx, rdi
0x18004c8c1  mov     rax, [rax+30h]
0x18004c8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8ca  mov     ebx, eax
0x18004c8cc  test    eax, eax
0x18004c8ce  js      loc_18004CA92
0x18004c8d4  mov     rdx, [rbp+arg_8]
0x18004c8d8  cmp     dword ptr [rdx+3Ch], 2
0x18004c8dc  jnz     short loc_18004C8E1
0x18004c8de  add     r14d, r13d
0x18004c8e1  mov     rax, [rdi]
0x18004c8e4  mov     rcx, rdi
0x18004c8e7  mov     rax, [rax+0A8h]
0x18004c8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8f3  add     r12d, r13d
0x18004c8f6  mov     [rbp+arg_8], rsi
0x18004c8fa  jmp     short loc_18004C8A7
0x18004c8fc  test    r14d, r14d
0x18004c8ff  jnz     short loc_18004C909
0x18004c901  mov     ebx, r13d
0x18004c904  jmp     loc_18004CA92
0x18004c909  mov     ecx, 0Ch; vt
0x18004c90e  mov     [rbp+rgsabound.cElements], r14d
0x18004c912  lea     r8, [rbp+rgsabound]; rgsabound
0x18004c916  mov     [rbp+rgsabound.lLbound], esi
0x18004c919  mov     edx, r13d; cDims
0x18004c91c  call    cs:__imp_SafeArrayCreate
0x18004c922  mov     r15, rax
0x18004c925  test    rax, rax
0x18004c928  jz      loc_18004CA8D
0x18004c92e  mov     rax, [rax+10h]
0x18004c932  lea     rdx, [rbp+var_18]; struct CHashTable **
0x18004c936  mov     ecx, r14d; unsigned int
0x18004c939  mov     [rbp+var_10], rax
0x18004c93d  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18004c942  mov     rsi, [rbp+var_18]
0x18004c946  mov     ebx, eax
0x18004c948  test    eax, eax
0x18004c94a  js      loc_18004CA92
0x18004c950  xor     r12d, r12d
0x18004c953  xor     r13d, r13d
0x18004c956  mov     rax, [rbp+arg_18]
0x18004c95a  movzx   ecx, word ptr [rax+32h]
0x18004c95e  cmp     r13d, ecx
0x18004c961  jnb     loc_18004CA3B
0x18004c967  mov     rax, [rdi]
0x18004c96a  lea     r8, [rbp+arg_8]
0x18004c96e  mov     edx, r13d
0x18004c971  mov     rcx, rdi
0x18004c974  mov     rax, [rax+30h]
0x18004c978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c97d  mov     ebx, eax
0x18004c97f  test    eax, eax
0x18004c981  js      loc_18004CA92
0x18004c987  mov     rdx, [rbp+arg_8]
0x18004c98b  cmp     dword ptr [rdx+3Ch], 2
0x18004c98f  jnz     loc_18004CA19
0x18004c995  mov     rax, [rbp+var_10]
0x18004c999  lea     rcx, [r12+r12*2]
0x18004c99d  mov     rdx, [rdx+10h]; pvargSrc
0x18004c9a1  lea     rcx, [rax+rcx*8]; pvargDest
0x18004c9a5  call    cs:__imp_VariantCopy
0x18004c9ab  mov     ebx, eax
0x18004c9ad  test    eax, eax
0x18004c9af  js      loc_18004CA92
0x18004c9b5  mov     rax, [rdi]
0x18004c9b8  lea     r8, [rbp+bstrString]
0x18004c9bc  mov     rdx, [rbp+arg_8]
0x18004c9c0  xor     r9d, r9d
0x18004c9c3  mov     [rsp+68h+var_40], 0
0x18004c9cc  mov     rcx, rdi
0x18004c9cf  mov     [rsp+68h+var_48], 0
0x18004c9d8  mov     rax, [rax+60h]
0x18004c9dc  mov     edx, [rdx]
0x18004c9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9e3  mov     ebx, eax
0x18004c9e5  test    eax, eax
0x18004c9e7  js      loc_18004CA92
0x18004c9ed  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18004c9f1  mov     rcx, rsi; this
0x18004c9f4  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x18004c9f9  mov     rcx, [rbp+bstrString]; bstrString
0x18004c9fd  mov     ebx, eax
0x18004c9ff  call    cs:__imp_SysFreeString
0x18004ca05  test    ebx, ebx
0x18004ca07  js      loc_18004CA92
0x18004ca0d  inc     r12d
0x18004ca10  cmp     r12d, r14d
0x18004ca13  jz      short loc_18004CA3B
0x18004ca15  mov     rdx, [rbp+arg_8]
0x18004ca19  mov     rax, [rdi]
0x18004ca1c  mov     rcx, rdi
0x18004ca1f  mov     rax, [rax+0A8h]
0x18004ca26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca2b  inc     r13d
0x18004ca2e  mov     [rbp+arg_8], 0
0x18004ca36  jmp     loc_18004C956
0x18004ca3b  mov     ecx, 60h ; '`'; Size
0x18004ca40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ca45  test    rax, rax
0x18004ca48  jz      short loc_18004CA8D
0x18004ca4a  mov     rcx, rax; this
0x18004ca4d  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18004ca52  mov     rbx, rax
0x18004ca55  test    rax, rax
0x18004ca58  jz      short loc_18004CA8D
0x18004ca5a  mov     [rax+0Ch], r14d
0x18004ca5e  mov     r14, [rbp+arg_0]
0x18004ca62  mov     [rax+18h], r15
0x18004ca66  xor     r15d, r15d
0x18004ca69  mov     [rax+10h], rsi
0x18004ca6d  xor     esi, esi
0x18004ca6f  mov     rcx, [r14]
0x18004ca72  mov     rax, [rcx+8]
0x18004ca76  mov     rcx, r14
0x18004ca79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca7e  mov     rax, [rbp+arg_10]
0x18004ca82  mov     [rbx+20h], r14
0x18004ca86  mov     [rax], rbx
0x18004ca89  xor     ebx, ebx
0x18004ca8b  jmp     short loc_18004CA92
0x18004ca8d  mov     ebx, 8007000Eh
0x18004ca92  mov     rdx, [rbp+arg_18]
0x18004ca96  test    rdx, rdx
0x18004ca99  jz      short loc_18004CAAD
0x18004ca9b  mov     rax, [rdi]
0x18004ca9e  mov     rcx, rdi
0x18004caa1  mov     rax, [rax+98h]
0x18004caa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caad  test    r15, r15
0x18004cab0  jz      short loc_18004CABB
0x18004cab2  mov     rcx, r15; psa
0x18004cab5  call    cs:__imp_SafeArrayDestroy
0x18004cabb  test    rsi, rsi
0x18004cabe  jz      short loc_18004CAC8
0x18004cac0  mov     rcx, rsi; this
0x18004cac3  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x18004cac8  mov     rdx, [rbp+arg_8]
0x18004cacc  test    rdx, rdx
0x18004cacf  jz      short loc_18004CAE3
0x18004cad1  mov     rax, [rdi]
0x18004cad4  mov     rcx, rdi
0x18004cad7  mov     rax, [rax+0A8h]
0x18004cade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cae3  mov     eax, ebx
0x18004cae5  add     rsp, 68h
0x18004cae9  pop     r15
0x18004caeb  pop     r14
0x18004caed  pop     r13
0x18004caef  pop     r12
0x18004caf1  pop     rdi
0x18004caf2  pop     rsi
0x18004caf3  pop     rbx
0x18004caf4  pop     rbp
0x18004caf5  retn
```
