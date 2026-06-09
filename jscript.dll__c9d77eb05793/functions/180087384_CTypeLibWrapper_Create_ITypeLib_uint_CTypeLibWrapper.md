# CTypeLibWrapper::Create(ITypeLib * *,uint,CTypeLibWrapper * *)

- ea: `0x180087384`
- end: `0x1800876f0`
- name: `?Create@CTypeLibWrapper@@SAJPEAPEAUITypeLib@@IPEAPEAV1@@Z`
- size: `876`
- prototype: `static int(struct ITypeLib **, unsigned int, struct CTypeLibWrapper **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18007e0b0`
- `0x180082d70`

## callees

- `0x180049b58`
- `0x180049bcc`
- `0x18004cafc`
- `0x1800576a0`
- `0x180087314`
- `0x18008735c`
- `0x180087384`
- `0x1800876f8`
- `0x18009428e`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800874f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800874f3`
- `OLEAUT32!__imp_VariantCopy` at `0x1800875e2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800875e2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18008740f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18008740f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800876ba`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800876ba`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18008751e`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18008751e`
- `OLEAUT32!__imp_CreateTypeLib` at `0x1800873ed`
- `OLEAUT32!__imp_CreateTypeLib` at `0x1800873ed`

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
0x180087384  mov     [rsp-8+arg_10], r8
0x180087389  mov     [rsp-8+arg_0], rcx
0x18008738e  push    rbp
0x18008738f  push    rbx
0x180087390  push    rsi
0x180087391  push    rdi
0x180087392  push    r12
0x180087394  push    r13
0x180087396  push    r14
0x180087398  push    r15
0x18008739a  lea     rbp, [rsp-1Fh]
0x18008739f  sub     rsp, 88h
0x1800873a6  xor     esi, esi
0x1800873a8  mov     r12d, edx
0x1800873ab  xor     edi, edi
0x1800873ad  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x1800873b5  mov     [rbp+57h+var_70], rsi
0x1800873b9  mov     [rbp+57h+arg_18], rdi
0x1800873bd  mov     [rbp+57h+var_68], rsi
0x1800873c1  mov     [rbp+57h+ppctlib], rsi
0x1800873c5  mov     [rbp+57h+bstrString], rsi
0x1800873c9  mov     [r8], rsi
0x1800873cc  test    edx, edx
0x1800873ce  jnz     short loc_1800873D8
0x1800873d0  lea     eax, [rsi+1]
0x1800873d3  jmp     loc_1800876DC
0x1800873d8  xor     r15d, r15d
0x1800873db  lea     r8, [rbp+57h+ppctlib]; ppctlib
0x1800873df  lea     rdx, aConstdebTlb; "ConstDeb.tlb"
0x1800873e6  lea     r14d, [r15+1]
0x1800873ea  mov     ecx, r14d; syskind
0x1800873ed  call    cs:__imp_CreateTypeLib
0x1800873f3  mov     ebx, eax
0x1800873f5  test    eax, eax
0x1800873f7  js      loc_18008769D
0x1800873fd  lea     ecx, [r15+0Ch]; vt
0x180087401  mov     [rbp+57h+rgsabound.cElements], r12d
0x180087405  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180087409  mov     [rbp+57h+rgsabound.lLbound], esi
0x18008740c  mov     edx, r14d; cDims
0x18008740f  call    cs:__imp_SafeArrayCreate
0x180087415  mov     r15, rax
0x180087418  test    rax, rax
0x18008741b  jnz     short loc_180087427
0x18008741d  mov     ebx, 8007000Eh
0x180087422  jmp     loc_18008769D
0x180087427  mov     rax, [rax+10h]
0x18008742b  lea     rdx, [rbp+57h+arg_18]; struct CHashTable **
0x18008742f  mov     ecx, r12d; unsigned int
0x180087432  mov     [rbp+57h+var_58], rax
0x180087436  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18008743b  mov     rdi, [rbp+57h+arg_18]
0x18008743f  mov     ebx, eax
0x180087441  test    eax, eax
0x180087443  js      loc_18008769D
0x180087449  mov     [rbp+57h+arg_8], esi
0x18008744c  xor     r13d, r13d
0x18008744f  cmp     r13d, r12d
0x180087452  jnb     loc_180087509
0x180087458  mov     rcx, [rbp+57h+arg_0]
0x18008745c  lea     r8, [rbp+57h+var_68]; struct CTypeLibWrapper **
0x180087460  mov     eax, r12d
0x180087463  sub     eax, r13d
0x180087466  sub     eax, r14d
0x180087469  mov     rax, [rcx+rax*8]
0x18008746d  mov     rcx, [rbp+57h+ppctlib]; struct ICreateTypeLib *
0x180087471  mov     rdx, rax; struct ITypeLib *
0x180087474  mov     [rbp+57h+arg_18], rax
0x180087478  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)
0x18008747d  mov     ebx, eax
0x18008747f  test    eax, eax
0x180087481  js      loc_18008769D
0x180087487  mov     rdx, [rbp+57h+var_58]
0x18008748b  lea     rcx, ds:0[r13*2]
0x180087493  mov     rax, [rbp+57h+var_68]
0x180087497  add     rcx, r13
0x18008749a  mov     word ptr [rdx+rcx*8], 9
0x1800874a0  mov     [rdx+rcx*8+8], rax
0x1800874a5  test    rax, rax
0x1800874a8  jz      short loc_1800874B3
0x1800874aa  mov     ecx, [rbp+57h+arg_8]
0x1800874ad  add     ecx, [rax+0Ch]
0x1800874b0  mov     [rbp+57h+arg_8], ecx
0x1800874b3  mov     rcx, [rbp+57h+arg_18]
0x1800874b7  lea     r8, [rbp+57h+bstrString]
0x1800874bb  mov     [rsp+0C0h+var_98], rsi
0x1800874c0  xor     r9d, r9d
0x1800874c3  or      edx, 0FFFFFFFFh
0x1800874c6  mov     [rsp+0C0h+var_A0], rsi
0x1800874cb  mov     rax, [rcx]
0x1800874ce  mov     rax, [rax+48h]
0x1800874d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800874d7  mov     ebx, eax
0x1800874d9  test    eax, eax
0x1800874db  js      loc_18008769D
0x1800874e1  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800874e5  mov     rcx, rdi; this
0x1800874e8  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x1800874ed  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800874f1  mov     ebx, eax
0x1800874f3  call    cs:__imp_SysFreeString
0x1800874f9  test    ebx, ebx
0x1800874fb  js      loc_18008769D
0x180087501  add     r13d, r14d
0x180087504  jmp     loc_18008744F
0x180087509  mov     r13d, [rbp+57h+arg_8]
0x18008750d  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180087511  mov     rcx, r15; psa
0x180087514  lea     eax, [r12+r13]
0x180087518  mov     dword ptr [rbp+57h+var_68], eax
0x18008751b  mov     [rbp+57h+rgsabound.cElements], eax
0x18008751e  call    cs:__imp_SafeArrayRedim
0x180087524  mov     ebx, eax
0x180087526  test    eax, eax
0x180087528  js      loc_18008769D
0x18008752e  mov     rsi, [r15+10h]
0x180087532  lea     rdx, [rbp+57h+var_70]; struct CHashTable **
0x180087536  lea     ecx, [r12+r13]; unsigned int
0x18008753a  mov     [rbp+57h+var_58], rsi
0x18008753e  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x180087543  mov     ebx, eax
0x180087545  test    eax, eax
0x180087547  js      loc_180087699
0x18008754d  lea     rcx, ds:0[r13*2]
0x180087555  mov     rdx, rsi; Src
0x180087558  add     rcx, r13
0x18008755b  lea     r8, [r12+r12*2]
0x18008755f  shl     r8, 3; Size
0x180087563  lea     rbx, ds:0[rcx*8]
0x18008756b  lea     rcx, [rbx+rsi]; void *
0x18008756f  call    memmove_0
0x180087574  mov     r8, rbx; Size
0x180087577  xor     edx, edx; Val
0x180087579  mov     rcx, rsi; void *
0x18008757c  call    memset_0
0x180087581  mov     rsi, [rbp+57h+var_70]
0x180087585  xor     r9d, r9d
0x180087588  mov     dword ptr [rbp+57h+arg_18], r9d
0x18008758c  xor     eax, eax
0x18008758e  mov     [rbp+57h+var_80], eax
0x180087591  cmp     eax, r12d
0x180087594  jnb     loc_180087633
0x18008759a  mov     r8, [rbp+57h+var_58]
0x18008759e  add     eax, r13d
0x1800875a1  lea     rax, [rax+rax*2]
0x1800875a5  mov     rcx, [r8+rax*8+8]
0x1800875aa  mov     [rbp+57h+var_70], rcx
0x1800875ae  test    rcx, rcx
0x1800875b1  jz      short loc_180087628
0x1800875b3  mov     rax, [rcx+18h]
0x1800875b7  xor     r13d, r13d
0x1800875ba  mov     rdx, [rax+10h]
0x1800875be  mov     [rbp+57h+var_48], rdx
0x1800875c2  cmp     r13d, [rcx+0Ch]
0x1800875c6  jnb     short loc_18008760E
0x1800875c8  mov     eax, r9d
0x1800875cb  lea     rcx, ds:0[r13*2]
0x1800875d3  add     rcx, r13
0x1800875d6  lea     rdx, [rdx+rcx*8]; pvargSrc
0x1800875da  lea     rcx, [rax+rax*2]
0x1800875de  lea     rcx, [r8+rcx*8]; pvargDest
0x1800875e2  call    cs:__imp_VariantCopy
0x1800875e8  mov     ebx, eax
0x1800875ea  test    eax, eax
0x1800875ec  js      loc_18008769D
0x1800875f2  mov     r9d, dword ptr [rbp+57h+arg_18]
0x1800875f6  add     r13d, r14d
0x1800875f9  mov     rcx, [rbp+57h+var_70]
0x1800875fd  add     r9d, r14d
0x180087600  mov     r8, [rbp+57h+var_58]
0x180087604  mov     rdx, [rbp+57h+var_48]
0x180087608  mov     dword ptr [rbp+57h+arg_18], r9d
0x18008760c  jmp     short loc_1800875C2
0x18008760e  mov     rdx, [rcx+10h]; struct CHashTable *
0x180087612  mov     rcx, rsi; this
0x180087615  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x18008761a  mov     ebx, eax
0x18008761c  test    eax, eax
0x18008761e  js      short loc_18008769D
0x180087620  mov     r13d, [rbp+57h+arg_8]
0x180087624  mov     r9d, dword ptr [rbp+57h+arg_18]
0x180087628  mov     eax, [rbp+57h+var_80]
0x18008762b  add     eax, r14d
0x18008762e  jmp     loc_18008758E
0x180087633  mov     rdx, rdi; struct CHashTable *
0x180087636  mov     rcx, rsi; this
0x180087639  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x18008763e  mov     ebx, eax
0x180087640  test    eax, eax
0x180087642  js      short loc_18008769D
0x180087644  mov     ecx, 60h ; '`'; Size
0x180087649  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008764e  test    rax, rax
0x180087651  jz      loc_18008741D
0x180087657  mov     rcx, rax; this
0x18008765a  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18008765f  mov     rbx, rax
0x180087662  test    rax, rax
0x180087665  jz      loc_18008741D
0x18008766b  test    rdi, rdi
0x18008766e  jz      short loc_180087678
0x180087670  mov     rcx, rdi; this
0x180087673  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180087678  mov     eax, dword ptr [rbp+57h+var_68]
0x18008767b  mov     [rbx+18h], r15
0x18008767f  mov     [rbx+0Ch], eax
0x180087682  mov     [rbx+10h], rsi
0x180087686  mov     rax, [rbp+57h+ppctlib]
0x18008768a  mov     [rbx+20h], rax
0x18008768e  mov     rax, [rbp+57h+arg_10]
0x180087692  mov     [rax], rbx
0x180087695  xor     eax, eax
0x180087697  jmp     short loc_1800876DC
0x180087699  mov     rsi, [rbp+57h+var_70]
0x18008769d  mov     rcx, [rbp+57h+ppctlib]
0x1800876a1  test    rcx, rcx
0x1800876a4  jz      short loc_1800876B2
0x1800876a6  mov     rax, [rcx]
0x1800876a9  mov     rax, [rax+10h]
0x1800876ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876b2  test    r15, r15
0x1800876b5  jz      short loc_1800876C0
0x1800876b7  mov     rcx, r15; psa
0x1800876ba  call    cs:__imp_SafeArrayDestroy
0x1800876c0  test    rdi, rdi
0x1800876c3  jz      short loc_1800876CD
0x1800876c5  mov     rcx, rdi; this
0x1800876c8  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800876cd  test    rsi, rsi
0x1800876d0  jz      short loc_1800876DA
0x1800876d2  mov     rcx, rsi; this
0x1800876d5  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800876da  mov     eax, ebx
0x1800876dc  add     rsp, 88h
0x1800876e3  pop     r15
0x1800876e5  pop     r14
0x1800876e7  pop     r13
0x1800876e9  pop     r12
0x1800876eb  pop     rdi
0x1800876ec  pop     rsi
0x1800876ed  pop     rbx
0x1800876ee  pop     rbp
0x1800876ef  retn
```
