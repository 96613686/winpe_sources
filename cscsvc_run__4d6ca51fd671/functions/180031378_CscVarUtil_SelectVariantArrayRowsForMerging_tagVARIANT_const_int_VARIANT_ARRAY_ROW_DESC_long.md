# CscVarUtil_SelectVariantArrayRowsForMerging(tagVARIANT const *,int,VARIANT_ARRAY_ROW_DESC * *,long *)

- ea: `0x180031378`
- end: `0x1800315a2`
- name: `?CscVarUtil_SelectVariantArrayRowsForMerging@@YAJPEBUtagVARIANT@@HPEAPEAUVARIANT_ARRAY_ROW_DESC@@PEAJ@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct tagVARIANT *, int, struct VARIANT_ARRAY_ROW_DESC **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800803c0`

## callees

- `0x18000d640`
- `0x18001be00`
- `0x180029dd0`
- `0x180031378`
- `0x18007fdd0`
- `0x180080324`
- `0x1800805a8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18003148a`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003148a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180031558`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180031558`
- `KERNEL32!CompareStringW` at `0x180031514`
- `KERNEL32!CompareStringW` at `0x180031514`

## pseudocode

```c
__int64 __fastcall CscVarUtil_SelectVariantArrayRowsForMerging(
        struct tagVARIANT *a1,
        int a2,
        struct VARIANT_ARRAY_ROW_DESC **a3,
        int *a4)
{
  const struct tagVARIANT *v6; // r9
  int SafeArrayBounds; // ebx
  int v8; // r14d
  int v9; // edi
  const struct tagVARIANT *v10; // rcx
  int v11; // eax
  void *v12; // rdx
  struct tagVARIANT *v13; // r9
  int v14; // eax
  unsigned __int64 v15; // rdi
  int i; // r14d
  const struct tagVARIANT *v17; // r12
  SAFEARRAY *parray; // r13
  int j; // r15d
  __int64 v20; // r12
  int *v21; // rdx
  bool v22; // zf
  const struct tagVARIANT *v24; // [rsp+30h] [rbp-28h]
  PCNZWCH lpString2; // [rsp+38h] [rbp-20h] BYREF
  PCNZWCH lpString1; // [rsp+40h] [rbp-18h] BYREF
  int v28; // [rsp+A8h] [rbp+50h] BYREF
  SIZE_T dwBytes; // [rsp+B0h] [rbp+58h] BYREF
  int *v30; // [rsp+B8h] [rbp+60h]

  v30 = a4;
  v28 = a2;
  *a3 = 0;
  v6 = a1;
  SafeArrayBounds = 0;
  v8 = 0;
  v9 = 0;
  *a4 = 0;
  while ( v9 < 5 )
  {
    v10 = &v6[v9];
    if ( v10->vt
      && (v28 = 0, v11 = CscVarUtil_Validate2DimensionalArrayVariant(v10, &v28),
                   v6 = a1,
                   SafeArrayBounds = v11,
                   v11 >= 0) )
    {
      v8 += v28;
      ++v9;
    }
    else
    {
      ++v9;
      if ( SafeArrayBounds < 0 )
        return (unsigned int)SafeArrayBounds;
    }
  }
  *a3 = 0;
  dwBytes = 0;
  SafeArrayBounds = ULongLongMult(v8, 8u, &dwBytes);
  if ( SafeArrayBounds >= 0 )
  {
    v14 = CscUtil_HeapAlloc(dwBytes, 1, (void **)a3, v13);
    v13 = a1;
    SafeArrayBounds = v14;
  }
  if ( SafeArrayBounds >= 0 )
  {
    v15 = 0;
    for ( i = 0; ; ++i )
    {
      while ( 1 )
      {
        if ( i >= 5 )
        {
          *v30 = v15;
          return (unsigned int)SafeArrayBounds;
        }
        v17 = &v13[i];
        v24 = v17;
        if ( v17->vt )
          break;
LABEL_29:
        ++i;
        if ( SafeArrayBounds < 0 )
        {
          CscUtil_HeapFree(*a3, v12);
          *a3 = 0;
          return (unsigned int)SafeArrayBounds;
        }
      }
      parray = v17->parray;
      LODWORD(dwBytes) = 0;
      v28 = 0;
      SafeArrayBounds = CscVarUtil_GetSafeArrayBounds(parray, 2u, (int *)&dwBytes, &v28);
      if ( SafeArrayBounds < 0 || (SafeArrayBounds = SafeArrayLock(parray), SafeArrayBounds < 0) )
      {
        v13 = a1;
        goto LABEL_29;
      }
      for ( j = dwBytes; j <= v28; ++j )
      {
        lpString1 = 0;
        if ( (int)CscVarUtil_ColumnZeroString(v17, j, &lpString1) >= 0 )
        {
          v20 = 0;
          if ( v15 )
          {
            while ( 1 )
            {
              v21 = (int *)*a3;
              lpString2 = 0;
              if ( (int)CscVarUtil_ColumnZeroString(&a1[v21[2 * v20]], v21[2 * v20 + 1], &lpString2) >= 0
                && CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) == 2 )
              {
                break;
              }
              if ( ++v20 >= v15 )
                goto LABEL_22;
            }
            v17 = v24;
          }
          else
          {
LABEL_22:
            v22 = v20 == v15;
            v17 = v24;
            if ( v22 )
            {
              *((_DWORD *)*a3 + 2 * v15) = i;
              *((_DWORD *)*a3 + 2 * v15++ + 1) = j;
            }
          }
        }
      }
      SafeArrayUnlock(parray);
      v13 = a1;
    }
  }
  return (unsigned int)SafeArrayBounds;
}

```

## disassembly

```asm
0x180031378  mov     [rsp-40h+arg_18], r9
0x18003137d  mov     [rsp-40h+arg_8], edx
0x180031381  mov     [rsp-40h+arg_0], rcx
0x180031386  push    rbp
0x180031387  push    rbx
0x180031388  push    rsi
0x180031389  push    rdi
0x18003138a  push    r12
0x18003138c  push    r13
0x18003138e  push    r14
0x180031390  push    r15
0x180031392  mov     rbp, rsp
0x180031395  sub     rsp, 58h
0x180031399  xor     r15d, r15d
0x18003139c  mov     r10, r9
0x18003139f  mov     rsi, r8
0x1800313a2  mov     [r8], r15
0x1800313a5  mov     r9, rcx
0x1800313a8  mov     ebx, r15d
0x1800313ab  mov     r14d, r15d
0x1800313ae  mov     edi, r15d
0x1800313b1  mov     [r10], r15d
0x1800313b4  cmp     edi, 5
0x1800313b7  jge     short loc_1800313F4
0x1800313b9  movsxd  rax, edi
0x1800313bc  lea     rcx, [rax+rax*2]
0x1800313c0  lea     rcx, [r9+rcx*8]; struct tagVARIANT *
0x1800313c4  cmp     r15w, [rcx]
0x1800313c8  jz      short loc_1800313E9
0x1800313ca  lea     rdx, [rbp+arg_8]; int *
0x1800313ce  mov     [rbp+arg_8], r15d
0x1800313d2  call    ?CscVarUtil_Validate2DimensionalArrayVariant@@YAJAEBUtagVARIANT@@PEAJ@Z; CscVarUtil_Validate2DimensionalArrayVariant(tagVARIANT const &,long *)
0x1800313d7  mov     r9, [rbp+arg_0]
0x1800313db  mov     ebx, eax
0x1800313dd  test    eax, eax
0x1800313df  js      short loc_1800313E9
0x1800313e1  add     r14d, [rbp+arg_8]
0x1800313e5  inc     edi
0x1800313e7  jmp     short loc_1800313B4
0x1800313e9  inc     edi
0x1800313eb  test    ebx, ebx
0x1800313ed  jns     short loc_1800313B4
0x1800313ef  jmp     loc_18003158F
0x1800313f4  movsxd  rcx, r14d; unsigned __int64
0x1800313f7  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x1800313fb  mov     edx, 8; unsigned __int64
0x180031400  mov     [rsi], r15
0x180031403  mov     [rbp+dwBytes], r15
0x180031407  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003140c  mov     ebx, eax
0x18003140e  test    eax, eax
0x180031410  js      short loc_180031429
0x180031412  mov     rcx, [rbp+dwBytes]; dwBytes
0x180031416  mov     r8, rsi; void **
0x180031419  mov     edx, 1; int
0x18003141e  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180031423  mov     r9, [rbp+arg_0]
0x180031427  mov     ebx, eax
0x180031429  test    ebx, ebx
0x18003142b  js      loc_18003158F
0x180031431  mov     rdi, r15
0x180031434  mov     r14d, r15d
0x180031437  cmp     r14d, 5
0x18003143b  jge     loc_180031589
0x180031441  movsxd  rax, r14d
0x180031444  lea     rcx, [rax+rax*2]
0x180031448  lea     r12, [r9+rcx*8]
0x18003144c  mov     [rbp+var_28], r12
0x180031450  cmp     r15w, [r12]
0x180031455  jz      loc_180031571
0x18003145b  mov     r13, [r12+8]
0x180031460  lea     r9, [rbp+arg_8]; int *
0x180031464  mov     rcx, r13; psa
0x180031467  mov     dword ptr [rbp+dwBytes], r15d
0x18003146b  lea     r8, [rbp+dwBytes]; int *
0x18003146f  mov     [rbp+arg_8], r15d
0x180031473  mov     edx, 2; nDim
0x180031478  call    ?CscVarUtil_GetSafeArrayBounds@@YAJPEBUtagSAFEARRAY@@IPEAJ1@Z; CscVarUtil_GetSafeArrayBounds(tagSAFEARRAY const *,uint,long *,long *)
0x18003147d  mov     ebx, eax
0x18003147f  test    eax, eax
0x180031481  js      loc_18003156D
0x180031487  mov     rcx, r13; psa
0x18003148a  call    cs:__imp_SafeArrayLock
0x180031490  mov     ebx, eax
0x180031492  test    eax, eax
0x180031494  js      loc_18003156D
0x18003149a  mov     r15d, dword ptr [rbp+dwBytes]
0x18003149e  jmp     loc_18003154B
0x1800314a3  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x1800314a7  mov     [rbp+lpString1], 0
0x1800314af  mov     edx, r15d; int
0x1800314b2  mov     rcx, r12; struct tagVARIANT *
0x1800314b5  call    ?CscVarUtil_ColumnZeroString@@YAJPEBUtagVARIANT@@HPEAPEBG@Z; CscVarUtil_ColumnZeroString(tagVARIANT const *,int,ushort const * *)
0x1800314ba  test    eax, eax
0x1800314bc  js      loc_180031548
0x1800314c2  xor     r12d, r12d
0x1800314c5  test    rdi, rdi
0x1800314c8  jz      short loc_180031527
0x1800314ca  mov     rdx, [rsi]
0x1800314cd  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800314d1  mov     [rbp+var_20], 0
0x1800314d9  movsxd  rax, dword ptr [rdx+r12*8]
0x1800314dd  mov     edx, [rdx+r12*8+4]; int
0x1800314e2  lea     rcx, [rax+rax*2]
0x1800314e6  mov     rax, [rbp+arg_0]
0x1800314ea  lea     rcx, [rax+rcx*8]; struct tagVARIANT *
0x1800314ee  call    ?CscVarUtil_ColumnZeroString@@YAJPEBUtagVARIANT@@HPEAPEBG@Z; CscVarUtil_ColumnZeroString(tagVARIANT const *,int,ushort const * *)
0x1800314f3  test    eax, eax
0x1800314f5  js      short loc_18003151F
0x1800314f7  mov     rax, [rbp+var_20]
0x1800314fb  or      ecx, 0FFFFFFFFh
0x1800314fe  mov     r8, [rbp+lpString1]; lpString1
0x180031502  mov     r9d, ecx; cchCount1
0x180031505  mov     [rsp+58h+cchCount2], ecx; cchCount2
0x180031509  mov     [rsp+58h+lpString2], rax; lpString2
0x18003150e  lea     edx, [rcx+2]; dwCmpFlags
0x180031511  lea     ecx, [rdx+7Eh]; Locale
0x180031514  call    cs:__imp_CompareStringW
0x18003151a  cmp     eax, 2
0x18003151d  jz      short loc_180031544
0x18003151f  inc     r12
0x180031522  cmp     r12, rdi
0x180031525  jb      short loc_1800314CA
0x180031527  cmp     r12, rdi
0x18003152a  mov     r12, [rbp+var_28]
0x18003152e  jnz     short loc_180031548
0x180031530  mov     rax, [rsi]
0x180031533  mov     [rax+rdi*8], r14d
0x180031537  mov     rax, [rsi]
0x18003153a  mov     [rax+rdi*8+4], r15d
0x18003153f  inc     rdi
0x180031542  jmp     short loc_180031548
0x180031544  mov     r12, [rbp+var_28]
0x180031548  inc     r15d
0x18003154b  cmp     r15d, [rbp+arg_8]
0x18003154f  jle     loc_1800314A3
0x180031555  mov     rcx, r13; psa
0x180031558  call    cs:__imp_SafeArrayUnlock
0x18003155e  mov     r9, [rbp+arg_0]
0x180031562  inc     r14d
0x180031565  xor     r15d, r15d
0x180031568  jmp     loc_180031437
0x18003156d  mov     r9, [rbp+arg_0]
0x180031571  inc     r14d
0x180031574  test    ebx, ebx
0x180031576  jns     loc_180031437
0x18003157c  mov     rcx, [rsi]; lpMem
0x18003157f  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180031584  mov     [rsi], r15
0x180031587  jmp     short loc_18003158F
0x180031589  mov     rax, [rbp+arg_18]
0x18003158d  mov     [rax], edi
0x18003158f  mov     eax, ebx
0x180031591  add     rsp, 58h
0x180031595  pop     r15
0x180031597  pop     r14
0x180031599  pop     r13
0x18003159b  pop     r12
0x18003159d  pop     rdi
0x18003159e  pop     rsi
0x18003159f  pop     rbx
0x1800315a0  pop     rbp
0x1800315a1  retn
```
