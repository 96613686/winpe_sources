# CTypeLibWrapper::Create(ICreateTypeLib *,ITypeLib *,CTypeLibWrapper * *)

- ea: `0x18008952c`
- end: `0x18008998f`
- name: `?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeLib@@PEAPEAV1@@Z`
- size: `1123`
- prototype: `__int64 __fastcall(struct ICreateTypeLib *, struct ITypeLib *, struct CTypeLibWrapper **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180089194`

## callees

- `0x18004a5ec`
- `0x18004a660`
- `0x18004d4cc`
- `0x18004d7ac`
- `0x1800585d0`
- `0x180089124`
- `0x18008916c`
- `0x18008952c`
- `0x180089e00`
- `0x18009669e`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180089742`
- `OLEAUT32!__imp_SysFreeString` at `0x180089742`
- `OLEAUT32!__imp_VariantCopy` at `0x1800898c2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800898c2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800895eb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800895eb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180089789`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180089789`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18008981c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18008981c`

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
0x18008952c  mov     [rsp-8+arg_10], r8
0x180089531  mov     [rsp-8+arg_0], rcx
0x180089536  push    rbp
0x180089537  push    rbx
0x180089538  push    rsi
0x180089539  push    rdi
0x18008953a  push    r12
0x18008953c  push    r13
0x18008953e  push    r14
0x180089540  push    r15
0x180089542  lea     rbp, [rsp-1Fh]
0x180089547  sub     rsp, 98h
0x18008954e  mov     rax, [rdx]
0x180089551  xor     ebx, ebx
0x180089553  mov     rcx, rdx
0x180089556  mov     [rbp+57h+arg_18], ebx
0x180089559  mov     r12, rdx
0x18008955c  mov     qword ptr [rbp+57h+rgsabound.cElements], rbx
0x180089560  mov     [rbp+57h+bstrString], rbx
0x180089564  mov     edi, ebx
0x180089566  mov     rax, [rax+18h]
0x18008956a  mov     r14d, ebx
0x18008956d  mov     [rbp+57h+var_78], rbx
0x180089571  mov     [rbp+57h+var_70], rbx
0x180089575  mov     [rbp+57h+arg_8], rbx
0x180089579  mov     [rbp+57h+var_60], rbx
0x18008957d  mov     [r8], rbx
0x180089580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089585  mov     [rbp+57h+var_90], eax
0x180089588  lea     r13d, [rbx+1]
0x18008958c  mov     esi, ebx
0x18008958e  mov     r15d, ebx
0x180089591  cmp     r15d, eax
0x180089594  jnb     short loc_1800895CB
0x180089596  mov     rcx, [r12]
0x18008959a  lea     r8, [rbp+57h+arg_18]
0x18008959e  mov     edx, r15d
0x1800895a1  mov     rax, [rcx+28h]
0x1800895a5  mov     rcx, r12
0x1800895a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895ad  mov     ebx, eax
0x1800895af  test    eax, eax
0x1800895b1  js      loc_1800897AF
0x1800895b7  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x1800895be  jnz     short loc_1800895C3
0x1800895c0  add     esi, r13d
0x1800895c3  mov     eax, [rbp+57h+var_90]
0x1800895c6  add     r15d, r13d
0x1800895c9  jmp     short loc_180089591
0x1800895cb  xor     ebx, ebx
0x1800895cd  test    esi, esi
0x1800895cf  jnz     short loc_1800895D9
0x1800895d1  mov     eax, r13d
0x1800895d4  jmp     loc_1800897D3
0x1800895d9  mov     ecx, 0Ch; vt
0x1800895de  mov     [rbp+57h+rgsabound.cElements], esi
0x1800895e1  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800895e5  mov     [rbp+57h+rgsabound.lLbound], ebx
0x1800895e8  mov     edx, r13d; cDims
0x1800895eb  call    cs:__imp_SafeArrayCreate
0x1800895f2  nop     dword ptr [rax+rax+00h]
0x1800895f7  mov     [rbp+57h+psa], rax
0x1800895fb  test    rax, rax
0x1800895fe  jnz     short loc_18008960A
0x180089600  mov     ebx, 8007000Eh
0x180089605  jmp     loc_1800897AF
0x18008960a  mov     rcx, [rax+10h]
0x18008960e  lea     rdx, [rbp+57h+arg_8]; struct CHashTable **
0x180089612  mov     [rbp+57h+var_58], rcx
0x180089616  mov     ecx, esi; unsigned int
0x180089618  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x18008961d  mov     r13, [rbp+57h+arg_8]
0x180089621  mov     ebx, eax
0x180089623  test    eax, eax
0x180089625  js      loc_180089782
0x18008962b  xor     r15d, r15d
0x18008962e  mov     dword ptr [rbp+57h+arg_8], edi
0x180089631  xor     ebx, ebx
0x180089633  mov     [rbp+57h+var_8C], ebx
0x180089636  cmp     ebx, [rbp+57h+var_90]
0x180089639  jnb     loc_1800897E8
0x18008963f  mov     rax, [r12]
0x180089643  lea     r8, [rbp+57h+arg_18]
0x180089647  mov     edx, ebx
0x180089649  mov     rcx, r12
0x18008964c  mov     rax, [rax+28h]
0x180089650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089655  test    [rbp+57h+arg_18], 0FFFFFFFDh
0x18008965c  jnz     loc_180089777
0x180089662  mov     rax, [r12]
0x180089666  lea     r8, [rbp+57h+var_70]
0x18008966a  mov     edx, ebx
0x18008966c  mov     rcx, r12
0x18008966f  mov     rax, [rax+20h]
0x180089673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089678  mov     ebx, eax
0x18008967a  test    eax, eax
0x18008967c  js      loc_180089782
0x180089682  mov     rdx, [rbp+57h+var_70]; struct ITypeInfo *
0x180089686  lea     r8, [rbp+57h+var_78]; struct CTypeLibWrapper **
0x18008968a  mov     rcx, [rbp+57h+arg_0]; struct ICreateTypeLib *
0x18008968e  call    ?Create@CTypeLibWrapper@@SAJPEAUICreateTypeLib@@PEAUITypeInfo@@PEAPEAV1@@Z; CTypeLibWrapper::Create(ICreateTypeLib *,ITypeInfo *,CTypeLibWrapper * *)
0x180089693  mov     ebx, eax
0x180089695  test    eax, eax
0x180089697  js      loc_18008977E
0x18008969d  cmp     eax, 1
0x1800896a0  jnz     short loc_1800896E3
0x1800896a2  dec     esi
0x1800896a4  mov     eax, esi
0x1800896a6  sub     eax, r15d
0x1800896a9  jz      short loc_1800896DD
0x1800896ab  mov     rbx, [rbp+57h+var_58]
0x1800896af  lea     r8, [rax+rax*2]
0x1800896b3  lea     eax, [r15+1]
0x1800896b7  shl     r8, 3; Size
0x1800896bb  lea     rax, [rax+rax*2]
0x1800896bf  lea     rcx, [r15+r15*2]
0x1800896c3  lea     rdx, [rbx+rax*8]; Src
0x1800896c7  lea     rcx, [rbx+rcx*8]; void *
0x1800896cb  call    memmove_0
0x1800896d0  lea     eax, [rsi-1]
0x1800896d3  lea     rdx, [rax+rax*2]
0x1800896d7  xor     eax, eax
0x1800896d9  mov     [rbx+rdx*8], ax
0x1800896dd  mov     rdi, [rbp+57h+var_78]
0x1800896e1  jmp     short loc_18008975B
0x1800896e3  mov     rdx, [rbp+57h+var_78]
0x1800896e7  lea     rcx, [r15+r15*2]
0x1800896eb  xor     edi, edi
0x1800896ed  lea     r8, [rbp+57h+bstrString]
0x1800896f1  mov     [rsp+0D0h+var_A8], rdi
0x1800896f6  xor     r9d, r9d
0x1800896f9  mov     [rbp+57h+var_78], rdi
0x1800896fd  mov     eax, [rdx+0Ch]
0x180089700  mov     [rbp+57h+var_88], eax
0x180089703  mov     rax, [rbp+57h+var_58]
0x180089707  mov     [rsp+0D0h+var_B0], rdi
0x18008970c  mov     [rax+rcx*8+8], rdx
0x180089711  or      edx, 0FFFFFFFFh
0x180089714  mov     word ptr [rax+rcx*8], 9
0x18008971a  mov     rcx, [rbp+57h+var_70]
0x18008971e  mov     rax, [rcx]
0x180089721  mov     rax, [rax+60h]
0x180089725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008972a  mov     ebx, eax
0x18008972c  test    eax, eax
0x18008972e  js      short loc_180089782
0x180089730  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180089734  mov     rcx, r13; this
0x180089737  call    ?Add@CHashTable@@QEAAJPEAG@Z; CHashTable::Add(ushort *)
0x18008973c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180089740  mov     ebx, eax
0x180089742  call    cs:__imp_SysFreeString
0x180089749  nop     dword ptr [rax+rax+00h]
0x18008974e  test    ebx, ebx
0x180089750  js      short loc_180089782
0x180089752  mov     eax, [rbp+57h+var_88]
0x180089755  add     dword ptr [rbp+57h+arg_8], eax
0x180089758  inc     r15d
0x18008975b  mov     rcx, [rbp+57h+var_70]
0x18008975f  mov     rax, [rcx]
0x180089762  mov     rax, [rax+10h]
0x180089766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008976b  mov     [rbp+57h+var_70], r14
0x18008976f  cmp     r15d, esi
0x180089772  jz      short loc_1800897E8
0x180089774  mov     ebx, [rbp+57h+var_8C]
0x180089777  inc     ebx
0x180089779  jmp     loc_180089633
0x18008977e  mov     rdi, [rbp+57h+var_78]
0x180089782  mov     r12, [rbp+57h+psa]
0x180089786  mov     rcx, r12; psa
0x180089789  call    cs:__imp_SafeArrayDestroy
0x180089790  nop     dword ptr [rax+rax+00h]
0x180089795  test    r14, r14
0x180089798  jz      short loc_1800897A2
0x18008979a  mov     rcx, r14; this
0x18008979d  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800897a2  test    r13, r13
0x1800897a5  jz      short loc_1800897AF
0x1800897a7  mov     rcx, r13; this
0x1800897aa  call    ??_GCHashTable@@QEAAPEAXI@Z; CHashTable::`scalar deleting destructor'(uint)
0x1800897af  mov     rcx, [rbp+57h+var_70]
0x1800897b3  test    rcx, rcx
0x1800897b6  jz      short loc_1800897C4
0x1800897b8  mov     rax, [rcx]
0x1800897bb  mov     rax, [rax+10h]
0x1800897bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800897c4  test    rdi, rdi
0x1800897c7  jz      short loc_1800897D1
0x1800897c9  mov     rcx, rdi; this
0x1800897cc  call    ?Release@CTypeLibWrapper@@UEAAKXZ; CTypeLibWrapper::Release(void)
0x1800897d1  mov     eax, ebx
0x1800897d3  add     rsp, 98h
0x1800897da  pop     r15
0x1800897dc  pop     r14
0x1800897de  pop     r13
0x1800897e0  pop     r12
0x1800897e2  pop     rdi
0x1800897e3  pop     rsi
0x1800897e4  pop     rbx
0x1800897e5  pop     rbp
0x1800897e6  retn
0x1800897e8  mov     r15d, dword ptr [rbp+57h+arg_8]
0x1800897ec  add     r15d, esi
0x1800897ef  jnz     short loc_1800897F7
0x1800897f1  lea     ebx, [r15+1]
0x1800897f5  jmp     short loc_180089782
0x1800897f7  lea     rdx, [rbp+57h+var_60]; struct CHashTable **
0x1800897fb  mov     ecx, r15d; unsigned int
0x1800897fe  call    ?Create@CHashTable@@SAJIPEAPEAV1@@Z; CHashTable::Create(uint,CHashTable * *)
0x180089803  mov     r12, [rbp+57h+psa]
0x180089807  mov     ebx, eax
0x180089809  test    eax, eax
0x18008980b  js      loc_180089986
0x180089811  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x180089815  mov     [rbp+57h+rgsabound.cElements], r15d
0x180089819  mov     rcx, r12; psa
0x18008981c  call    cs:__imp_SafeArrayRedim
0x180089823  nop     dword ptr [rax+rax+00h]
0x180089828  mov     ebx, eax
0x18008982a  test    eax, eax
0x18008982c  js      loc_180089986
0x180089832  mov     r14, [r12+10h]
0x180089837  mov     eax, dword ptr [rbp+57h+arg_8]
0x18008983a  mov     rdx, r14; Src
0x18008983d  mov     [rbp+57h+var_58], r14
0x180089841  lea     rcx, [rax+rax*2]
0x180089845  mov     eax, esi
0x180089847  lea     rbx, ds:0[rcx*8]
0x18008984f  lea     rcx, [rbx+r14]; void *
0x180089853  lea     r8, [rax+rax*2]
0x180089857  shl     r8, 3; Size
0x18008985b  call    memmove_0
0x180089860  mov     r8, rbx; Size
0x180089863  xor     edx, edx; Val
0x180089865  mov     rcx, r14; void *
0x180089868  call    memset_0
0x18008986d  mov     r14, [rbp+57h+var_60]
0x180089871  xor     r9d, r9d
0x180089874  mov     [rbp+57h+var_90], r9d
0x180089878  xor     eax, eax
0x18008987a  mov     [rbp+57h+var_88], eax
0x18008987d  cmp     eax, esi
0x18008987f  jnb     loc_18008991A
0x180089885  add     eax, dword ptr [rbp+57h+arg_8]
0x180089888  mov     r8, [rbp+57h+var_58]
0x18008988c  lea     rax, [rax+rax*2]
0x180089890  mov     rcx, [r8+rax*8+8]
0x180089895  mov     [rbp+57h+var_60], rcx
0x180089899  mov     rax, [rcx+18h]
0x18008989d  mov     rdx, [rax+10h]
0x1800898a1  xor     eax, eax
0x1800898a3  mov     [rbp+57h+var_78], rdx
0x1800898a7  mov     [rbp+57h+var_8C], eax
0x1800898aa  cmp     eax, [rcx+0Ch]
0x1800898ad  jnb     short loc_1800898F6
0x1800898af  lea     rcx, [rax+rax*2]
0x1800898b3  mov     eax, r9d
0x1800898b6  lea     rdx, [rdx+rcx*8]; pvargSrc
0x1800898ba  lea     rcx, [rax+rax*2]
0x1800898be  lea     rcx, [r8+rcx*8]; pvargDest
0x1800898c2  call    cs:__imp_VariantCopy
0x1800898c9  nop     dword ptr [rax+rax+00h]
0x1800898ce  mov     ebx, eax
0x1800898d0  test    eax, eax
0x1800898d2  js      loc_180089786
0x1800898d8  mov     r9d, [rbp+57h+var_90]
0x1800898dc  mov     eax, [rbp+57h+var_8C]
0x1800898df  mov     rcx, [rbp+57h+var_60]
0x1800898e3  inc     eax
0x1800898e5  mov     r8, [rbp+57h+var_58]
0x1800898e9  inc     r9d
0x1800898ec  mov     rdx, [rbp+57h+var_78]
0x1800898f0  mov     [rbp+57h+var_90], r9d
0x1800898f4  jmp     short loc_1800898A7
0x1800898f6  mov     rdx, [rcx+10h]; struct CHashTable *
0x1800898fa  mov     rcx, r14; this
0x1800898fd  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180089902  mov     ebx, eax
0x180089904  test    eax, eax
0x180089906  js      loc_180089786
0x18008990c  mov     eax, [rbp+57h+var_88]
0x18008990f  mov     r9d, [rbp+57h+var_90]
0x180089913  inc     eax
0x180089915  jmp     loc_18008987A
0x18008991a  mov     rdx, r13; struct CHashTable *
0x18008991d  mov     rcx, r14; this
0x180089920  call    ?Add@CHashTable@@QEAAJPEAV1@@Z; CHashTable::Add(CHashTable *)
0x180089925  mov     ecx, 60h ; '`'; Size
0x18008992a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008992f  test    rax, rax
0x180089932  jz      short loc_18008997A
0x180089934  mov     rcx, rax; this
0x180089937  call    ??0CTypeLibWrapper@@AEAA@XZ; CTypeLibWrapper::CTypeLibWrapper(void)
0x18008993c  mov     rdi, rax
0x18008993f  test    rax, rax
0x180089942  jz      short loc_18008997C
0x180089944  mov     rbx, [rbp+57h+arg_0]
0x180089948  mov     [rax+18h], r12
  ... truncated ...
```
