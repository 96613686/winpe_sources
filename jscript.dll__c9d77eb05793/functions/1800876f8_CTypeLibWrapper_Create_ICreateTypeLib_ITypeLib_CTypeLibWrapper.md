# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)

- ea: `0x1800876f8`
- end: `0x180087b3c`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z`
- size: `1092`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeLib *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180087384`

## callees

- `0x180049b58`
- `0x180049bcc`
- `0x18004c838`
- `0x18004cafc`
- `0x1800576a0`
- `0x180087314`
- `0x18008735c`
- `0x1800876f8`
- `0x180087f90`
- `0x18009428e`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180087908`
- `OLEAUT32!__imp_SysFreeString` at `0x180087908`
- `OLEAUT32!__imp_VariantCopy` at `0x180087a75`
- `OLEAUT32!__imp_VariantCopy` at `0x180087a75`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800877b7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800877b7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180087949`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180087949`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800879d5`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800879d5`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Create(struct ICreateTypeLib *a1, struct ITypeLib *a2, struct CTypeLibWrapper **a3)
{
  struct ITypeLibVtbl *lpVtbl; // rax
  struct CTypeLibWrapper *v5; // rdi
  UINT (__stdcall *GetTypeInfoCount)(ITypeLib *); // rax
  CHashTable *v7; // r14
  unsigned int v8; // eax
  ULONG v9; // esi
  unsigned int i; // r15d
  HRESULT v11; // ebx
  SAFEARRAY *v13; // rax
  int v14; // eax
  CHashTable *v15; // r13
  __int64 v16; // r15
  unsigned int j; // ebx
  int v18; // eax
  _QWORD *v19; // rbx
  struct CTypeLibWrapper *v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  SAFEARRAY *v23; // r12
  unsigned int v24; // edx
  unsigned int v25; // r15d
  char *v26; // r14
  size_t v27; // rbx
  unsigned int v28; // r9d
  ULONG k; // eax
  _QWORD *v30; // r8
  struct CHashTable *v31; // rcx
  struct CTypeLibWrapper *v32; // rdx
  __int64 v33; // rax
  CTypeLibWrapper *v34; // rax
  CTypeLibWrapper *v35; // rax
  struct CTypeLibWrapper **v36; // rax
  unsigned int v37; // [rsp+40h] [rbp-39h]
  unsigned int v38; // [rsp+40h] [rbp-39h]
  unsigned int v39; // [rsp+44h] [rbp-35h]
  int v40; // [rsp+44h] [rbp-35h]
  int v41; // [rsp+48h] [rbp-31h]
  ULONG v42; // [rsp+48h] [rbp-31h]
  SAFEARRAY *psa; // [rsp+50h] [rbp-29h]
  struct CTypeLibWrapper *v44; // [rsp+58h] [rbp-21h] BYREF
  struct ITypeInfo *v45; // [rsp+60h] [rbp-19h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp-11h] BYREF
  struct CHashTable *v47; // [rsp+70h] [rbp-9h] BYREF
  _QWORD *pvData; // [rsp+78h] [rbp-1h]
  BSTR bstrString[10]; // [rsp+80h] [rbp+7h] BYREF
  CHashTable *v51; // [rsp+E8h] [rbp+6Fh] BYREF
  struct CTypeLibWrapper **v52; // [rsp+F0h] [rbp+77h]
  int v53; // [rsp+F8h] [rbp+7Fh] BYREF

  v52 = a3;
  lpVtbl = a2->lpVtbl;
  v53 = 0;
  rgsabound = 0;
  bstrString[0] = 0;
  v5 = 0;
  GetTypeInfoCount = lpVtbl->GetTypeInfoCount;
  v7 = 0;
  v44 = 0;
  v45 = 0;
  v51 = 0;
  v47 = 0;
  *a3 = 0;
  v8 = ((__int64 (__fastcall *)(struct ITypeLib *))GetTypeInfoCount)(a2);
  v37 = v8;
  v9 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v11 = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, int *))a2->lpVtbl->GetTypeInfoType)(a2, i, &v53);
    if ( v11 < 0 )
      goto LABEL_34;
    if ( (v53 & 0xFFFFFFFD) == 0 )
      ++v9;
    v8 = v37;
  }
  if ( !v9 )
    return 1;
  rgsabound.cElements = v9;
  rgsabound.lLbound = 0;
  v13 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  psa = v13;
  if ( v13 )
  {
    pvData = v13->pvData;
    v14 = CHashTable::Create(v9, &v51);
    v15 = v51;
    v11 = v14;
    if ( v14 >= 0 )
    {
      v16 = 0;
      LODWORD(v51) = 0;
      for ( j = 0; ; ++j )
      {
        v39 = j;
        if ( j >= v37 )
          break;
        ((void (__fastcall *)(struct ITypeLib *, _QWORD, int *))a2->lpVtbl->GetTypeInfoType)(a2, j, &v53);
        if ( (v53 & 0xFFFFFFFD) == 0 )
        {
          v11 = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, struct ITypeInfo **))a2->lpVtbl->GetTypeInfo)(
                  a2,
                  j,
                  &v45);
          if ( v11 < 0 )
            goto LABEL_28;
          v18 = CTypeLibWrapper::Create(a1, v45, &v44);
          v11 = v18;
          if ( v18 < 0 )
          {
            v5 = v44;
            goto LABEL_28;
          }
          if ( v18 == 1 )
          {
            if ( --v9 != (_DWORD)v16 )
            {
              v19 = pvData;
              memmove_0(&pvData[3 * v16], &pvData[3 * (unsigned int)(v16 + 1)], 24LL * (v9 - (unsigned int)v16));
              LOWORD(v19[3 * v9 - 3]) = 0;
            }
            v5 = v44;
          }
          else
          {
            v20 = v44;
            v21 = 3 * v16;
            v5 = 0;
            v44 = 0;
            v41 = *((_DWORD *)v20 + 3);
            v22 = pvData;
            pvData[v21 + 1] = v20;
            LOWORD(v22[v21]) = 9;
            v11 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, BSTR *, _QWORD, _QWORD, _QWORD))v45->lpVtbl->GetDocumentation)(
                    v45,
                    0xFFFFFFFFLL,
                    bstrString,
                    0,
                    0,
                    0);
            if ( v11 < 0 )
              goto LABEL_28;
            v11 = CHashTable::Add(v15, bstrString[0]);
            SysFreeString(bstrString[0]);
            if ( v11 < 0 )
              goto LABEL_28;
            LODWORD(v51) = v41 + (_DWORD)v51;
            v16 = (unsigned int)(v16 + 1);
          }
          ((void (__fastcall *)(struct ITypeInfo *))v45->lpVtbl->Release)(v45);
          v45 = 0;
          if ( (_DWORD)v16 == v9 )
            break;
          j = v39;
        }
      }
      v25 = v9 + (_DWORD)v51;
      if ( v9 + (_DWORD)v51 )
      {
        v23 = psa;
        v11 = CHashTable::Create(v25, &v47);
        if ( v11 < 0 || (rgsabound.cElements = v25, v11 = SafeArrayRedim(psa, &rgsabound), v11 < 0) )
        {
          v7 = v47;
        }
        else
        {
          pvData = psa->pvData;
          v26 = (char *)pvData;
          v27 = 24LL * (unsigned int)v51;
          memmove_0(&v26[v27], v26, 24LL * v9);
          memset_0(v26, 0, v27);
          v7 = v47;
          v28 = 0;
          v38 = 0;
          for ( k = 0; ; k = v42 + 1 )
          {
            v42 = k;
            if ( k >= v9 )
              break;
            v30 = pvData;
            v31 = (struct CHashTable *)pvData[3 * (unsigned int)v51 + 1 + 3 * k];
            v47 = v31;
            v32 = *(struct CTypeLibWrapper **)(*((_QWORD *)v31 + 3) + 16LL);
            v33 = 0;
            v44 = v32;
            while ( 1 )
            {
              v40 = v33;
              if ( (unsigned int)v33 >= *((_DWORD *)v31 + 3) )
                break;
              v11 = VariantCopy((VARIANTARG *)&v30[3 * v28], (const VARIANTARG *)v32 + v33);
              if ( v11 < 0 )
                goto LABEL_29;
              v31 = v47;
              v33 = (unsigned int)(v40 + 1);
              v30 = pvData;
              v28 = v38 + 1;
              v32 = v44;
              ++v38;
            }
            v11 = CHashTable::Add(v7, *((struct CHashTable **)v31 + 2));
            if ( v11 < 0 )
              goto LABEL_29;
            v28 = v38;
          }
          CHashTable::Add(v7, v15);
          v34 = (CTypeLibWrapper *)operator new(0x60u);
          if ( v34 )
          {
            v35 = CTypeLibWrapper::CTypeLibWrapper(v34);
            v5 = v35;
            if ( v35 )
            {
              *((_QWORD *)v35 + 3) = psa;
              *((_DWORD *)v35 + 3) = v25;
              *((_QWORD *)v35 + 2) = v7;
              v7 = 0;
              ((void (__fastcall *)(struct ICreateTypeLib *))a1->lpVtbl->AddRef)(a1);
              v36 = v52;
              *((_QWORD *)v5 + 4) = a1;
              *v36 = v5;
              v5 = 0;
              v11 = 0;
              goto LABEL_30;
            }
          }
          else
          {
            v5 = 0;
          }
          v11 = -2147024882;
        }
LABEL_29:
        SafeArrayDestroy(v23);
LABEL_30:
        if ( v7 )
          CHashTable::`scalar deleting destructor'(v7, v24);
        if ( v15 )
          CHashTable::`scalar deleting destructor'(v15, v24);
        goto LABEL_34;
      }
      v11 = 1;
    }
LABEL_28:
    v23 = psa;
    goto LABEL_29;
  }
  v11 = -2147024882;
LABEL_34:
  if ( v45 )
    ((void (__fastcall *)(struct ITypeInfo *))v45->lpVtbl->Release)(v45);
  if ( v5 )
    CTypeLibWrapper::Release(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800876f8  mov     [rsp-8+arg_10], r8
0x1800876fd  mov     [rsp-8+arg_0], rcx
0x180087702  push    rbp
0x180087703  push    rbx
0x180087704  push    rsi
0x180087705  push    rdi
0x180087706  push    r12
0x180087708  push    r13
0x18008770a  push    r14
0x18008770c  push    r15
0x18008770e  lea     rbp, [rsp-1Fh]
0x180087713  sub     rsp, 98h
0x18008771a  mov     rax, [rdx]
0x18008771d  xor     ebx, ebx
0x18008771f  mov     rcx, rdx
0x180087722  mov     [rbp+57h+arg_18], ebx
0x180087725  mov     r12, rdx
0x180087728  mov     qword ptr [rbp+57h+rgsabound.cElements], rbx
0x18008772c  mov     [rbp+57h+bstrString], rbx
0x180087730  mov     edi, ebx
0x180087732  mov     rax, [rax+18h]
0x180087736  mov     r14d, ebx
0x180087739  mov     [rbp+57h+var_78], rbx
0x18008773d  mov     [rbp+57h+var_70], rbx
0x180087741  mov     [rbp+57h+arg_8], rbx
0x180087745  mov     [rbp+57h+var_60], rbx
0x180087749  mov     [r8], rbx
0x18008774c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087751  mov     [rbp+57h+var_90], eax
0x180087754  lea     r13d, [rbx+1]
0x180087758  mov     esi, ebx
0x18008775a  mov     r15d, ebx
0x18008775d  cmp     r15d, eax
0x180087760  jnb     short loc_180087797
0x180087762  mov     rcx, [r12]
0x180087766  lea     r8, [rbp+57h+arg_18]
0x18008776a  mov     edx, r15d
0x18008776d  mov     rax, [rcx+28h]
0x180087771  mov     rcx, r12
0x180087774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087779  mov     ebx, eax
0x18008777b  test    eax, eax
0x18008777d  js      loc_180087969
0x180087783  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x18008778a  jnz     short loc_18008778F
0x18008778c  add     esi, r13d
0x18008778f  mov     eax, [rbp+57h+var_90]
0x180087792  add     r15d, r13d
0x180087795  jmp     short loc_18008775D
0x180087797  xor     ebx, ebx
0x180087799  test    esi, esi
0x18008779b  jnz     short loc_1800877A5
0x18008779d  mov     eax, r13d
0x1800877a0  jmp     loc_18008798D
0x1800877a5  mov     ecx, 0Ch; vt
0x1800877aa  mov     [rbp+57h+rgsabound.cElements], esi
0x1800877ad  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800877b1  mov     [rbp+57h+rgsabound.lLbound], ebx
0x1800877b4  mov     edx, r13d; cDims
0x1800877b7  call    cs:__imp_SafeArrayCreate
0x1800877bd  mov     [rbp+57h+psa], rax
0x1800877c1  test    rax, rax
0x1800877c4  jnz     short loc_1800877D0
0x1800877c6  mov     ebx, 8007000Eh
0x1800877cb  jmp     loc_180087969
0x1800877d0  mov     rcx, [rax+10h]
0x1800877d4  lea     rdx, [rbp+57h+arg_8]; struct CHashTable **
0x1800877d8  mov     [rbp+57h+var_58], rcx
0x1800877dc  mov     ecx, esi; unsigned int
0x1800877de  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x1800877e3  mov     r13, [rbp+57h+arg_8]
0x1800877e7  mov     ebx, eax
0x1800877e9  test    eax, eax
0x1800877eb  js      loc_180087942
0x1800877f1  xor     r15d, r15d
0x1800877f4  mov     dword ptr [rbp+57h+arg_8], edi
0x1800877f7  xor     ebx, ebx
0x1800877f9  mov     [rbp+57h+var_8C], ebx
0x1800877fc  cmp     ebx, [rbp+57h+var_90]
0x1800877ff  jnb     loc_1800879A1
0x180087805  mov     rax, [r12]
0x180087809  lea     r8, [rbp+57h+arg_18]
0x18008780d  mov     edx, ebx
0x18008780f  mov     rcx, r12
0x180087812  mov     rax, [rax+28h]
0x180087816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008781b  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x180087822  jnz     loc_180087937
0x180087828  mov     rax, [r12]
0x18008782c  lea     r8, [rbp+57h+var_70]
0x180087830  mov     edx, ebx
0x180087832  mov     rcx, r12
0x180087835  mov     rax, [rax+20h]
0x180087839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008783e  mov     ebx, eax
0x180087840  test    eax, eax
0x180087842  js      loc_180087942
0x180087848  mov     rdx, [rbp+57h+var_70]; struct ITypeInfo *
0x18008784c  lea     r8, [rbp+57h+var_78]; struct CTypeLibWrapper **
0x180087850  mov     rcx, [rbp+57h+arg_0]; struct ICreateTypeLib *
0x180087854  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)
0x180087859  mov     ebx, eax
0x18008785b  test    eax, eax
0x18008785d  js      loc_18008793E
0x180087863  cmp     eax, 1
0x180087866  jnz     short loc_1800878A9
0x180087868  dec     esi
0x18008786a  mov     eax, esi
0x18008786c  sub     eax, r15d
0x18008786f  jz      short loc_1800878A3
0x180087871  mov     rbx, [rbp+57h+var_58]
0x180087875  lea     r8, [rax+rax*2]
0x180087879  lea     eax, [r15+1]
0x18008787d  shl     r8, 3; Size
0x180087881  lea     rax, [rax+rax*2]
0x180087885  lea     rcx, [r15+r15*2]
0x180087889  lea     rdx, [rbx+rax*8]; Src
0x18008788d  lea     rcx, [rbx+rcx*8]; void *
0x180087891  call    memmove_0
0x180087896  lea     eax, [rsi-1]
0x180087899  lea     rdx, [rax+rax*2]
0x18008789d  xor     eax, eax
0x18008789f  mov     [rbx+rdx*8], ax
0x1800878a3  mov     rdi, [rbp+57h+var_78]
0x1800878a7  jmp     short loc_18008791B
0x1800878a9  mov     rdx, [rbp+57h+var_78]
0x1800878ad  lea     rcx, [r15+r15*2]
0x1800878b1  xor     edi, edi
0x1800878b3  lea     r8, [rbp+57h+bstrString]
0x1800878b7  mov     [rsp+0D0h+var_A8], rdi
0x1800878bc  xor     r9d, r9d
0x1800878bf  mov     [rbp+57h+var_78], rdi
0x1800878c3  mov     eax, [rdx+0Ch]
0x1800878c6  mov     [rbp+57h+var_88], eax
0x1800878c9  mov     rax, [rbp+57h+var_58]
0x1800878cd  mov     [rsp+0D0h+var_B0], rdi
0x1800878d2  mov     [rax+rcx*8+8], rdx
0x1800878d7  or      edx, 0FFFFFFFFh
0x1800878da  mov     word ptr [rax+rcx*8], 9
0x1800878e0  mov     rcx, [rbp+57h+var_70]
0x1800878e4  mov     rax, [rcx]
0x1800878e7  mov     rax, [rax+60h]
0x1800878eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800878f0  mov     ebx, eax
0x1800878f2  test    eax, eax
0x1800878f4  js      short loc_180087942
0x1800878f6  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800878fa  mov     rcx, r13; this
0x1800878fd  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x180087902  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180087906  mov     ebx, eax
0x180087908  call    cs:__imp_SysFreeString
0x18008790e  test    ebx, ebx
0x180087910  js      short loc_180087942
0x180087912  mov     eax, [rbp+57h+var_88]
0x180087915  add     dword ptr [rbp+57h+arg_8], eax
0x180087918  inc     r15d
0x18008791b  mov     rcx, [rbp+57h+var_70]
0x18008791f  mov     rax, [rcx]
0x180087922  mov     rax, [rax+10h]
0x180087926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008792b  mov     [rbp+57h+var_70], r14
0x18008792f  cmp     r15d, esi
0x180087932  jz      short loc_1800879A1
0x180087934  mov     ebx, [rbp+57h+var_8C]
0x180087937  inc     ebx
0x180087939  jmp     loc_1800877F9
0x18008793e  mov     rdi, [rbp+57h+var_78]
0x180087942  mov     r12, [rbp+57h+psa]
0x180087946  mov     rcx, r12; psa
0x180087949  call    cs:__imp_SafeArrayDestroy
0x18008794f  test    r14, r14
0x180087952  jz      short loc_18008795C
0x180087954  mov     rcx, r14; this
0x180087957  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x18008795c  test    r13, r13
0x18008795f  jz      short loc_180087969
0x180087961  mov     rcx, r13; this
0x180087964  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x180087969  mov     rcx, [rbp+57h+var_70]
0x18008796d  test    rcx, rcx
0x180087970  jz      short loc_18008797E
0x180087972  mov     rax, [rcx]
0x180087975  mov     rax, [rax+10h]
0x180087979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008797e  test    rdi, rdi
0x180087981  jz      short loc_18008798B
0x180087983  mov     rcx, rdi; this
0x180087986  call    ?Release@CTypeLibWrapper@@UEAAKXZ; CTypeLibWrapper::Release(void)
0x18008798b  mov     eax, ebx
0x18008798d  add     rsp, 98h
0x180087994  pop     r15
0x180087996  pop     r14
0x180087998  pop     r13
0x18008799a  pop     r12
0x18008799c  pop     rdi
0x18008799d  pop     rsi
0x18008799e  pop     rbx
0x18008799f  pop     rbp
0x1800879a0  retn
0x1800879a1  mov     r15d, dword ptr [rbp+57h+arg_8]
0x1800879a5  add     r15d, esi
0x1800879a8  jnz     short loc_1800879B0
0x1800879aa  lea     ebx, [r15+1]
0x1800879ae  jmp     short loc_180087942
0x1800879b0  lea     rdx, [rbp+57h+var_60]; struct CHashTable **
0x1800879b4  mov     ecx, r15d; unsigned int
0x1800879b7  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x1800879bc  mov     r12, [rbp+57h+psa]
0x1800879c0  mov     ebx, eax
0x1800879c2  test    eax, eax
0x1800879c4  js      loc_180087B33
0x1800879ca  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x1800879ce  mov     [rbp+57h+rgsabound.cElements], r15d
0x1800879d2  mov     rcx, r12; psa
0x1800879d5  call    cs:__imp_SafeArrayRedim
0x1800879db  mov     ebx, eax
0x1800879dd  test    eax, eax
0x1800879df  js      loc_180087B33
0x1800879e5  mov     r14, [r12+10h]
0x1800879ea  mov     eax, dword ptr [rbp+57h+arg_8]
0x1800879ed  mov     rdx, r14; Src
0x1800879f0  mov     [rbp+57h+var_58], r14
0x1800879f4  lea     rcx, [rax+rax*2]
0x1800879f8  mov     eax, esi
0x1800879fa  lea     rbx, ds:0[rcx*8]
0x180087a02  lea     rcx, [rbx+r14]; void *
0x180087a06  lea     r8, [rax+rax*2]
0x180087a0a  shl     r8, 3; Size
0x180087a0e  call    memmove_0
0x180087a13  mov     r8, rbx; Size
0x180087a16  xor     edx, edx; Val
0x180087a18  mov     rcx, r14; void *
0x180087a1b  call    memset_0
0x180087a20  mov     r14, [rbp+57h+var_60]
0x180087a24  xor     r9d, r9d
0x180087a27  mov     [rbp+57h+var_90], r9d
0x180087a2b  xor     eax, eax
0x180087a2d  mov     [rbp+57h+var_88], eax
0x180087a30  cmp     eax, esi
0x180087a32  jnb     loc_180087AC7
0x180087a38  add     eax, dword ptr [rbp+57h+arg_8]
0x180087a3b  mov     r8, [rbp+57h+var_58]
0x180087a3f  lea     rax, [rax+rax*2]
0x180087a43  mov     rcx, [r8+rax*8+8]
0x180087a48  mov     [rbp+57h+var_60], rcx
0x180087a4c  mov     rax, [rcx+18h]
0x180087a50  mov     rdx, [rax+10h]
0x180087a54  xor     eax, eax
0x180087a56  mov     [rbp+57h+var_78], rdx
0x180087a5a  mov     [rbp+57h+var_8C], eax
0x180087a5d  cmp     eax, [rcx+0Ch]
0x180087a60  jnb     short loc_180087AA3
0x180087a62  lea     rcx, [rax+rax*2]
0x180087a66  mov     eax, r9d
0x180087a69  lea     rdx, [rdx+rcx*8]; pvargSrc
0x180087a6d  lea     rcx, [rax+rax*2]
0x180087a71  lea     rcx, [r8+rcx*8]; pvargDest
0x180087a75  call    cs:__imp_VariantCopy
0x180087a7b  mov     ebx, eax
0x180087a7d  test    eax, eax
0x180087a7f  js      loc_180087946
0x180087a85  mov     r9d, [rbp+57h+var_90]
0x180087a89  mov     eax, [rbp+57h+var_8C]
0x180087a8c  mov     rcx, [rbp+57h+var_60]
0x180087a90  inc     eax
0x180087a92  mov     r8, [rbp+57h+var_58]
0x180087a96  inc     r9d
0x180087a99  mov     rdx, [rbp+57h+var_78]
0x180087a9d  mov     [rbp+57h+var_90], r9d
0x180087aa1  jmp     short loc_180087A5A
0x180087aa3  mov     rdx, [rcx+10h]; struct CHashTable *
0x180087aa7  mov     rcx, r14; this
0x180087aaa  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180087aaf  mov     ebx, eax
0x180087ab1  test    eax, eax
0x180087ab3  js      loc_180087946
0x180087ab9  mov     eax, [rbp+57h+var_88]
0x180087abc  mov     r9d, [rbp+57h+var_90]
0x180087ac0  inc     eax
0x180087ac2  jmp     loc_180087A2D
0x180087ac7  mov     rdx, r13; struct CHashTable *
0x180087aca  mov     rcx, r14; this
0x180087acd  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180087ad2  mov     ecx, 60h ; '`'; Size
0x180087ad7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087adc  test    rax, rax
0x180087adf  jz      short loc_180087B27
0x180087ae1  mov     rcx, rax; this
0x180087ae4  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x180087ae9  mov     rdi, rax
0x180087aec  test    rax, rax
0x180087aef  jz      short loc_180087B29
0x180087af1  mov     rbx, [rbp+57h+arg_0]
0x180087af5  mov     [rax+18h], r12
0x180087af9  mov     rcx, rbx
0x180087afc  mov     [rax+0Ch], r15d
0x180087b00  mov     [rax+10h], r14
0x180087b04  xor     r14d, r14d
0x180087b07  mov     rax, [rbx]
  ... truncated ...
```
