# CTypeLibWrapper::Create(ITypeLib * *,uint,CTypeLibWrapper * *)

- ea: `0x180089194`
- end: `0x180089525`
- name: `?Create@CTypeLibWrapper@@SAJPEAPEAUITypeLib@@IPEAPEAV1@@Z`
- size: `913`
- prototype: `static int(struct ITypeLib **, unsigned int, struct CTypeLibWrapper **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18007fa20`
- `0x180084a10`

## callees

- `0x18004a5ec`
- `0x18004a660`
- `0x18004d7ac`
- `0x1800585d0`
- `0x180089124`
- `0x18008916c`
- `0x180089194`
- `0x18008952c`
- `0x18009669e`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18008930f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008930f`
- `OLEAUT32!__imp_VariantCopy` at `0x18008940a`
- `OLEAUT32!__imp_VariantCopy` at `0x18008940a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180089225`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180089225`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800894e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800894e8`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180089340`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180089340`
- `OLEAUT32!__imp_CreateTypeLib` at `0x1800891fd`
- `OLEAUT32!__imp_CreateTypeLib` at `0x1800891fd`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Create(struct ITypeLib **a1, unsigned int a2, struct CTypeLibWrapper **a3)
{
  CHashTable *v3; // rsi
  __int64 v4; // r12
  CHashTable *v5; // rdi
  SAFEARRAY *v7; // r15
  unsigned int v8; // edx
  HRESULT v9; // ebx
  SAFEARRAY *v10; // rax
  int v11; // eax
  __int64 i; // r13
  char *v13; // rdx
  struct CTypeLibWrapper *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // r13d
  char *v17; // rsi
  unsigned int v18; // r9d
  unsigned int j; // eax
  char *v20; // r8
  struct CHashTable *v21; // rcx
  __int64 v22; // r13
  __int64 v23; // rdx
  CTypeLibWrapper *v24; // rax
  CTypeLibWrapper *v25; // rbx
  int v26; // eax
  unsigned int v27; // [rsp+40h] [rbp-29h]
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-21h] BYREF
  struct CHashTable *v29; // [rsp+50h] [rbp-19h] BYREF
  struct CTypeLibWrapper *v30; // [rsp+58h] [rbp-11h] BYREF
  ICreateTypeLib *ppctlib; // [rsp+60h] [rbp-9h] BYREF
  char *pvData; // [rsp+68h] [rbp-1h]
  BSTR bstrString; // [rsp+70h] [rbp+7h] BYREF
  __int64 v34; // [rsp+78h] [rbp+Fh]
  unsigned int v36; // [rsp+D8h] [rbp+6Fh]
  CHashTable *v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = 0;
  v4 = a2;
  v5 = 0;
  rgsabound = 0;
  v29 = 0;
  v38 = 0;
  v30 = 0;
  ppctlib = 0;
  bstrString = 0;
  *a3 = 0;
  if ( !a2 )
    return 1;
  v7 = 0;
  v9 = CreateTypeLib(SYS_WIN32, L"ConstDeb.tlb", &ppctlib);
  if ( v9 < 0 )
    goto LABEL_34;
  rgsabound.cElements = v4;
  rgsabound.lLbound = 0;
  v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v7 = v10;
  if ( !v10 )
    goto LABEL_5;
  pvData = (char *)v10->pvData;
  v11 = CHashTable::Create(v4, &v38);
  v5 = v38;
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_34;
  v36 = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
  {
    v38 = (CHashTable *)a1[(unsigned int)(v4 - i - 1)];
    v9 = CTypeLibWrapper::Create(ppctlib, (struct ITypeLib *)v38, &v30);
    if ( v9 < 0 )
      goto LABEL_34;
    v13 = pvData;
    v14 = v30;
    v15 = 3 * i;
    *(_WORD *)&pvData[8 * v15] = 9;
    *(_QWORD *)&v13[8 * v15 + 8] = v14;
    if ( v14 )
      v36 += *((_DWORD *)v14 + 3);
    v9 = (*(__int64 (__fastcall **)(CHashTable *, __int64, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v38 + 72LL))(
           v38,
           0xFFFFFFFFLL,
           &bstrString,
           0,
           0,
           0);
    if ( v9 < 0 )
      goto LABEL_34;
    v9 = CHashTable::Add(v5, bstrString);
    SysFreeString(bstrString);
    if ( v9 < 0 )
      goto LABEL_34;
  }
  v16 = v36;
  LODWORD(v30) = v4 + v36;
  rgsabound.cElements = v4 + v36;
  v9 = SafeArrayRedim(v7, &rgsabound);
  if ( v9 < 0 )
    goto LABEL_34;
  v17 = (char *)v7->pvData;
  pvData = v17;
  v9 = CHashTable::Create((unsigned int)v4 + v36, &v29);
  if ( v9 < 0 )
  {
    v3 = v29;
    goto LABEL_34;
  }
  memmove_0(&v17[24 * v36], v17, 24 * v4);
  memset_0(v17, 0, 24LL * v36);
  v3 = v29;
  v18 = 0;
  LODWORD(v38) = 0;
  for ( j = 0; ; j = v27 + 1 )
  {
    v27 = j;
    if ( j >= (unsigned int)v4 )
      break;
    v20 = pvData;
    v21 = *(struct CHashTable **)&pvData[24 * v16 + 8 + 24 * j];
    v29 = v21;
    if ( v21 )
    {
      v22 = 0;
      v23 = *(_QWORD *)(*((_QWORD *)v21 + 3) + 16LL);
      v34 = v23;
      while ( (unsigned int)v22 < *((_DWORD *)v21 + 3) )
      {
        v9 = VariantCopy((VARIANTARG *)&v20[24 * v18], (const VARIANTARG *)(v23 + 24 * v22));
        if ( v9 < 0 )
          goto LABEL_34;
        v22 = (unsigned int)(v22 + 1);
        v21 = v29;
        v18 = (_DWORD)v38 + 1;
        v20 = pvData;
        v23 = v34;
        LODWORD(v38) = (_DWORD)v38 + 1;
      }
      v9 = CHashTable::Add(v3, *((struct CHashTable **)v21 + 2));
      if ( v9 < 0 )
        goto LABEL_34;
      v16 = v36;
      v18 = (unsigned int)v38;
    }
  }
  v9 = CHashTable::Add(v3, v5);
  if ( v9 < 0 )
    goto LABEL_34;
  v24 = (CTypeLibWrapper *)operator new(0x60u);
  if ( !v24 || (v25 = CTypeLibWrapper::CTypeLibWrapper(v24)) == 0 )
  {
LABEL_5:
    v9 = -2147024882;
LABEL_34:
    if ( ppctlib )
      ((void (__fastcall *)(ICreateTypeLib *))ppctlib->lpVtbl->Release)(ppctlib);
    if ( v7 )
      SafeArrayDestroy(v7);
    if ( v5 )
      CHashTable::`scalar deleting destructor'(v5, v8);
    if ( v3 )
      CHashTable::`scalar deleting destructor'(v3, v8);
    return (unsigned int)v9;
  }
  if ( v5 )
    CHashTable::`scalar deleting destructor'(v5, v8);
  v26 = (int)v30;
  *((_QWORD *)v25 + 3) = v7;
  *((_DWORD *)v25 + 3) = v26;
  *((_QWORD *)v25 + 2) = v3;
  *((_QWORD *)v25 + 4) = ppctlib;
  *a3 = v25;
  return 0;
}

```

## disassembly

```asm
0x180089194  mov     [rsp-8+arg_10], r8
0x180089199  mov     [rsp-8+arg_0], rcx
0x18008919e  push    rbp
0x18008919f  push    rbx
0x1800891a0  push    rsi
0x1800891a1  push    rdi
0x1800891a2  push    r12
0x1800891a4  push    r13
0x1800891a6  push    r14
0x1800891a8  push    r15
0x1800891aa  lea     rbp, [rsp-1Fh]
0x1800891af  sub     rsp, 88h
0x1800891b6  xor     esi, esi
0x1800891b8  mov     r12d, edx
0x1800891bb  xor     edi, edi
0x1800891bd  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x1800891c5  mov     [rbp+57h+var_70], rsi
0x1800891c9  mov     [rbp+57h+arg_18], rdi
0x1800891cd  mov     [rbp+57h+var_68], rsi
0x1800891d1  mov     [rbp+57h+ppctlib], rsi
0x1800891d5  mov     [rbp+57h+bstrString], rsi
0x1800891d9  mov     [r8], rsi
0x1800891dc  test    edx, edx
0x1800891de  jnz     short loc_1800891E8
0x1800891e0  lea     eax, [rsi+1]
0x1800891e3  jmp     loc_180089510
0x1800891e8  xor     r15d, r15d
0x1800891eb  lea     r8, [rbp+57h+ppctlib]; ppctlib
0x1800891ef  lea     rdx, aConstdebTlb; "ConstDeb.tlb"
0x1800891f6  lea     r14d, [r15+1]
0x1800891fa  mov     ecx, r14d; syskind
0x1800891fd  call    cs:__imp_CreateTypeLib
0x180089204  nop     dword ptr [rax+rax+00h]
0x180089209  mov     ebx, eax
0x18008920b  test    eax, eax
0x18008920d  js      loc_1800894CB
0x180089213  lea     ecx, [r15+0Ch]; vt
0x180089217  mov     [rbp+57h+rgsabound.cElements], r12d
0x18008921b  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18008921f  mov     [rbp+57h+rgsabound.lLbound], esi
0x180089222  mov     edx, r14d; cDims
0x180089225  call    cs:__imp_SafeArrayCreate
0x18008922c  nop     dword ptr [rax+rax+00h]
0x180089231  mov     r15, rax
0x180089234  test    rax, rax
0x180089237  jnz     short loc_180089243
0x180089239  mov     ebx, 8007000Eh
0x18008923e  jmp     loc_1800894CB
0x180089243  mov     rax, [rax+10h]
0x180089247  lea     rdx, [rbp+57h+arg_18]; struct CHashTable **
0x18008924b  mov     ecx, r12d; unsigned int
0x18008924e  mov     [rbp+57h+var_58], rax
0x180089252  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x180089257  mov     rdi, [rbp+57h+arg_18]
0x18008925b  mov     ebx, eax
0x18008925d  test    eax, eax
0x18008925f  js      loc_1800894CB
0x180089265  mov     [rbp+57h+arg_8], esi
0x180089268  xor     r13d, r13d
0x18008926b  cmp     r13d, r12d
0x18008926e  jnb     loc_18008932B
0x180089274  mov     rcx, [rbp+57h+arg_0]
0x180089278  lea     r8, [rbp+57h+var_68]; struct CTypeLibWrapper **
0x18008927c  mov     eax, r12d
0x18008927f  sub     eax, r13d
0x180089282  sub     eax, r14d
0x180089285  mov     rax, [rcx+rax*8]
0x180089289  mov     rcx, [rbp+57h+ppctlib]; struct ICreateTypeLib *
0x18008928d  mov     rdx, rax; struct ITypeLib *
0x180089290  mov     [rbp+57h+arg_18], rax
0x180089294  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)
0x180089299  mov     ebx, eax
0x18008929b  test    eax, eax
0x18008929d  js      loc_1800894CB
0x1800892a3  mov     rdx, [rbp+57h+var_58]
0x1800892a7  lea     rcx, ds:0[r13*2]
0x1800892af  mov     rax, [rbp+57h+var_68]
0x1800892b3  add     rcx, r13
0x1800892b6  mov     word ptr [rdx+rcx*8], 9
0x1800892bc  mov     [rdx+rcx*8+8], rax
0x1800892c1  test    rax, rax
0x1800892c4  jz      short loc_1800892CF
0x1800892c6  mov     ecx, [rbp+57h+arg_8]
0x1800892c9  add     ecx, [rax+0Ch]
0x1800892cc  mov     [rbp+57h+arg_8], ecx
0x1800892cf  mov     rcx, [rbp+57h+arg_18]
0x1800892d3  lea     r8, [rbp+57h+bstrString]
0x1800892d7  mov     [rsp+0C0h+var_98], rsi
0x1800892dc  xor     r9d, r9d
0x1800892df  or      edx, 0FFFFFFFFh
0x1800892e2  mov     [rsp+0C0h+var_A0], rsi
0x1800892e7  mov     rax, [rcx]
0x1800892ea  mov     rax, [rax+48h]
0x1800892ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892f3  mov     ebx, eax
0x1800892f5  test    eax, eax
0x1800892f7  js      loc_1800894CB
0x1800892fd  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180089301  mov     rcx, rdi; this
0x180089304  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x180089309  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18008930d  mov     ebx, eax
0x18008930f  call    cs:__imp_SysFreeString
0x180089316  nop     dword ptr [rax+rax+00h]
0x18008931b  test    ebx, ebx
0x18008931d  js      loc_1800894CB
0x180089323  add     r13d, r14d
0x180089326  jmp     loc_18008926B
0x18008932b  mov     r13d, [rbp+57h+arg_8]
0x18008932f  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180089333  mov     rcx, r15; psa
0x180089336  lea     eax, [r12+r13]
0x18008933a  mov     dword ptr [rbp+57h+var_68], eax
0x18008933d  mov     [rbp+57h+rgsabound.cElements], eax
0x180089340  call    cs:__imp_SafeArrayRedim
0x180089347  nop     dword ptr [rax+rax+00h]
0x18008934c  mov     ebx, eax
0x18008934e  test    eax, eax
0x180089350  js      loc_1800894CB
0x180089356  mov     rsi, [r15+10h]
0x18008935a  lea     rdx, [rbp+57h+var_70]; struct CHashTable **
0x18008935e  lea     ecx, [r12+r13]; unsigned int
0x180089362  mov     [rbp+57h+var_58], rsi
0x180089366  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18008936b  mov     ebx, eax
0x18008936d  test    eax, eax
0x18008936f  js      loc_1800894C7
0x180089375  lea     rcx, ds:0[r13*2]
0x18008937d  mov     rdx, rsi; Src
0x180089380  add     rcx, r13
0x180089383  lea     r8, [r12+r12*2]
0x180089387  shl     r8, 3; Size
0x18008938b  lea     rbx, ds:0[rcx*8]
0x180089393  lea     rcx, [rbx+rsi]; void *
0x180089397  call    memmove_0
0x18008939c  mov     r8, rbx; Size
0x18008939f  xor     edx, edx; Val
0x1800893a1  mov     rcx, rsi; void *
0x1800893a4  call    memset_0
0x1800893a9  mov     rsi, [rbp+57h+var_70]
0x1800893ad  xor     r9d, r9d
0x1800893b0  mov     dword ptr [rbp+57h+arg_18], r9d
0x1800893b4  xor     eax, eax
0x1800893b6  mov     [rbp+57h+var_80], eax
0x1800893b9  cmp     eax, r12d
0x1800893bc  jnb     loc_180089461
0x1800893c2  mov     r8, [rbp+57h+var_58]
0x1800893c6  add     eax, r13d
0x1800893c9  lea     rax, [rax+rax*2]
0x1800893cd  mov     rcx, [r8+rax*8+8]
0x1800893d2  mov     [rbp+57h+var_70], rcx
0x1800893d6  test    rcx, rcx
0x1800893d9  jz      short loc_180089456
0x1800893db  mov     rax, [rcx+18h]
0x1800893df  xor     r13d, r13d
0x1800893e2  mov     rdx, [rax+10h]
0x1800893e6  mov     [rbp+57h+var_48], rdx
0x1800893ea  cmp     r13d, [rcx+0Ch]
0x1800893ee  jnb     short loc_18008943C
0x1800893f0  mov     eax, r9d
0x1800893f3  lea     rcx, ds:0[r13*2]
0x1800893fb  add     rcx, r13
0x1800893fe  lea     rdx, [rdx+rcx*8]; pvargSrc
0x180089402  lea     rcx, [rax+rax*2]
0x180089406  lea     rcx, [r8+rcx*8]; pvargDest
0x18008940a  call    cs:__imp_VariantCopy
0x180089411  nop     dword ptr [rax+rax+00h]
0x180089416  mov     ebx, eax
0x180089418  test    eax, eax
0x18008941a  js      loc_1800894CB
0x180089420  mov     r9d, dword ptr [rbp+57h+arg_18]
0x180089424  add     r13d, r14d
0x180089427  mov     rcx, [rbp+57h+var_70]
0x18008942b  add     r9d, r14d
0x18008942e  mov     r8, [rbp+57h+var_58]
0x180089432  mov     rdx, [rbp+57h+var_48]
0x180089436  mov     dword ptr [rbp+57h+arg_18], r9d
0x18008943a  jmp     short loc_1800893EA
0x18008943c  mov     rdx, [rcx+10h]; struct CHashTable *
0x180089440  mov     rcx, rsi; this
0x180089443  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180089448  mov     ebx, eax
0x18008944a  test    eax, eax
0x18008944c  js      short loc_1800894CB
0x18008944e  mov     r13d, [rbp+57h+arg_8]
0x180089452  mov     r9d, dword ptr [rbp+57h+arg_18]
0x180089456  mov     eax, [rbp+57h+var_80]
0x180089459  add     eax, r14d
0x18008945c  jmp     loc_1800893B6
0x180089461  mov     rdx, rdi; struct CHashTable *
0x180089464  mov     rcx, rsi; this
0x180089467  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x18008946c  mov     ebx, eax
0x18008946e  test    eax, eax
0x180089470  js      short loc_1800894CB
0x180089472  mov     ecx, 60h ; '`'; Size
0x180089477  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008947c  test    rax, rax
0x18008947f  jz      loc_180089239
0x180089485  mov     rcx, rax; this
0x180089488  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18008948d  mov     rbx, rax
0x180089490  test    rax, rax
0x180089493  jz      loc_180089239
0x180089499  test    rdi, rdi
0x18008949c  jz      short loc_1800894A6
0x18008949e  mov     rcx, rdi; this
0x1800894a1  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800894a6  mov     eax, dword ptr [rbp+57h+var_68]
0x1800894a9  mov     [rbx+18h], r15
0x1800894ad  mov     [rbx+0Ch], eax
0x1800894b0  mov     [rbx+10h], rsi
0x1800894b4  mov     rax, [rbp+57h+ppctlib]
0x1800894b8  mov     [rbx+20h], rax
0x1800894bc  mov     rax, [rbp+57h+arg_10]
0x1800894c0  mov     [rax], rbx
0x1800894c3  xor     eax, eax
0x1800894c5  jmp     short loc_180089510
0x1800894c7  mov     rsi, [rbp+57h+var_70]
0x1800894cb  mov     rcx, [rbp+57h+ppctlib]
0x1800894cf  test    rcx, rcx
0x1800894d2  jz      short loc_1800894E0
0x1800894d4  mov     rax, [rcx]
0x1800894d7  mov     rax, [rax+10h]
0x1800894db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894e0  test    r15, r15
0x1800894e3  jz      short loc_1800894F4
0x1800894e5  mov     rcx, r15; psa
0x1800894e8  call    cs:__imp_SafeArrayDestroy
0x1800894ef  nop     dword ptr [rax+rax+00h]
0x1800894f4  test    rdi, rdi
0x1800894f7  jz      short loc_180089501
0x1800894f9  mov     rcx, rdi; this
0x1800894fc  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180089501  test    rsi, rsi
0x180089504  jz      short loc_18008950E
0x180089506  mov     rcx, rsi; this
0x180089509  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x18008950e  mov     eax, ebx
0x180089510  add     rsp, 88h
0x180089517  pop     r15
0x180089519  pop     r14
0x18008951b  pop     r13
0x18008951d  pop     r12
0x18008951f  pop     rdi
0x180089520  pop     rsi
0x180089521  pop     rbx
0x180089522  pop     rbp
0x180089523  retn
```
