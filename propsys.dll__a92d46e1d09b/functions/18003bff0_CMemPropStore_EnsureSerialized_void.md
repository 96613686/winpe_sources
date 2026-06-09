# CMemPropStore::_EnsureSerialized(void)

- ea: `0x18003bff0`
- end: `0x18003c863`
- name: `?_EnsureSerialized@CMemPropStore@@AEAAJXZ`
- size: `2163`
- prototype: `__int64 __fastcall(CMemPropStore *__hidden this)`
- caller_count: `5`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b8c0`
- `0x18003bcd0`
- `0x18003bd30`
- `0x18003bf10`
- `0x18007fda0`

## callees

- `0x18003b838`
- `0x18003ba10`
- `0x18003bff0`
- `0x18003cac0`
- `0x18003ccb0`
- `0x18003cce0`
- `0x18003d500`
- `0x18003d630`
- `0x18003ef7c`
- `0x1800488b0`
- `0x18004cf00`
- `0x18004d3b0`
- `0x18004db30`
- `0x18006ed20`
- `0x18006fb80`
- `0x18006fb8c`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c242`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c242`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c03a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c03a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003c6aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003c79a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003c6aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003c79a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003c311`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003c311`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c1cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c672`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c1cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c6f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c6f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c504`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c177`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c177`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c1d8`
- `SHCORE!__imp_ualstrcmpiW` at `0x18003c3cf`
- `SHCORE!__imp_ualstrcmpiW` at `0x18003c3cf`

## pseudocode

```c
__int64 __fastcall CMemPropStore::_EnsureSerialized(CMemPropStore *this)
{
  __int64 v2; // rcx
  HRESULT UnserializedNamedValue; // edi
  RTL_SRWLOCK *v4; // rbx
  _QWORD *v5; // r14
  int v6; // r12d
  int v7; // edx
  void *v8; // rcx
  int v9; // edx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  struct _DSA *v12; // rcx
  unsigned __int16 *v13; // rbx
  int v14; // r14d
  const OLECHAR **ItemPtr; // rax
  signed int v16; // ecx
  int v17; // r9d
  __int64 v18; // r10
  __int64 v19; // rcx
  unsigned int v21; // r8d
  unsigned __int64 i; // r9
  int v23; // edx
  unsigned int v24; // edx
  int v25; // ecx
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rcx
  unsigned int *j; // r14
  __int64 v30; // rax
  bool v31; // sf
  __int64 v32; // rax
  int *k; // rbx
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // r15d
  int v37; // ecx
  void *v38; // r12
  int v39; // edi
  bool v40; // sf
  int v41; // ecx
  unsigned int v42; // r10d
  int v43; // r12d
  unsigned int v44; // r13d
  unsigned int v45; // edx
  unsigned int v46; // r13d
  __int64 v47; // rax
  __int64 v48; // r13
  void *v49; // rcx
  void *v50; // rbx
  LPVOID v51; // rax
  int v52; // r15d
  unsigned int v53; // ebx
  LPVOID v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r14
  __int64 v57; // rbx
  __int64 v58; // rax
  SIZE_T cb; // [rsp+50h] [rbp-69h] BYREF
  int v60; // [rsp+58h] [rbp-61h]
  _QWORD *v61; // [rsp+60h] [rbp-59h]
  int v62[2]; // [rsp+68h] [rbp-51h] BYREF
  void *Src; // [rsp+70h] [rbp-49h] BYREF
  void **p_Src; // [rsp+78h] [rbp-41h] BYREF
  __int128 pitem; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v66; // [rsp+90h] [rbp-29h]
  struct tagPROPVARIANT pvar; // [rsp+98h] [rbp-21h] BYREF
  PROPVARIANT pvarDest[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v69; // [rsp+C0h] [rbp+7h]

  v2 = *((_QWORD *)this + 28);
  UnserializedNamedValue = 0;
  v4 = (RTL_SRWLOCK *)((char *)this + 248);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  else
    AcquireSRWLockExclusive((PSRWLOCK)this + 31);
  if ( *((_QWORD *)this + 25) )
    goto LABEL_35;
  v60 = 0;
  v5 = (_QWORD *)((char *)this + 120);
  pitem = 0;
  v66 = 0;
  v6 = 0;
LABEL_5:
  v61 = v5;
  if ( !*((_QWORD *)this + 21) )
  {
    v7 = *((_DWORD *)this + 26);
    Src = 0;
    Src = g_pfn_DSA_Create(20, v7);
    v8 = Src;
    if ( !Src )
      goto LABEL_20;
    if ( *((_DWORD *)this + 26) )
    {
      p_Src = &Src;
      *(_QWORD *)v62 = &p_Src;
      if ( *v5 )
      {
        v9 = 1;
        v10 = 0;
        do
        {
          if ( v10 >= *((_DWORD *)this + 27) )
            break;
          v11 = 56LL * v10;
          if ( *(_DWORD *)(v11 + *v5) == 1 )
            v9 = CSimpleHashTable<_tagpropertykey,CMemPropStore::CACHEDPROPERTY,CDefaultHashPolicy<_tagpropertykey>,CDefaultKeyCompare<_tagpropertykey>,CMemPropStoreResizePolicy,CDefaultRehashPolicy>::s_EnumAdaptor<_lambda_5ea173085f1a26f70939f45d8dbf8520_>(
                   v62,
                   v11 + *v5 + 4LL,
                   v11 + *v5 + 24LL);
          ++v10;
        }
        while ( v9 );
        v8 = Src;
      }
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 21, (signed __int64)v8, 0) )
    {
      v12 = (struct _DSA *)Src;
    }
    else
    {
      v12 = 0;
      Src = 0;
    }
    if ( v12 )
      DSA_Destroy(v12);
  }
  if ( DSA_GetItem(*((HDSA *)this + 21), v6, &pitem) )
  {
    v18 = *v5;
    v69 = 0;
    *(_OWORD *)pvarDest = 0;
    if ( !v18 )
      goto LABEL_32;
    v21 = 314159269;
    for ( i = 0; i < 0x14; ++i )
    {
      v23 = *((unsigned __int8 *)&pitem + i);
      v21 ^= (v21 >> 2) + 2080 * v21 + v23;
    }
    v24 = (v21 & 0x7FFFFFFF) % *((_DWORD *)this + 27);
    v25 = -1;
    while ( 1 )
    {
      v26 = 56LL * v24;
      v27 = *(_DWORD *)(v26 + v18);
      if ( v27 == 2 )
      {
        if ( v25 == -1 )
          v25 = v24;
      }
      else
      {
        if ( !v27 )
        {
          if ( v25 != -1 )
            v24 = v25;
LABEL_49:
          v28 = 56LL * v24;
          if ( *(_DWORD *)(v28 + v18) != 1 )
          {
LABEL_32:
            UnserializedNamedValue = -2147319765;
            goto LABEL_33;
          }
          UnserializedNamedValue = PropVariantCopy(pvarDest, (const PROPVARIANT *)(v28 + v18 + 32));
          if ( UnserializedNamedValue < 0 )
            goto LABEL_33;
          j = 0;
          if ( *((_QWORD *)this + 25) )
          {
            for ( j = (unsigned int *)*((_QWORD *)this + 25); *j; j = (unsigned int *)((char *)j + *j) )
            {
              v30 = pitem - *((_QWORD *)j + 1);
              if ( (_QWORD)pitem == *((_QWORD *)j + 1) )
                v30 = *((_QWORD *)&pitem + 1) - *((_QWORD *)j + 2);
              if ( !v30 )
              {
                UnserializedNamedValue = 0;
                goto LABEL_59;
              }
            }
LABEL_76:
            if ( *((_DWORD *)this + 52) + 284 < (unsigned int)(*((_DWORD *)this + 52) + 28) )
            {
              UnserializedNamedValue = -2147024362;
              goto LABEL_108;
            }
            v52 = *((_DWORD *)this + 50);
            v53 = (*((_DWORD *)this + 52) + 283) & 0xFFFFFF00;
            UnserializedNamedValue = 0;
            if ( v53 <= *((_DWORD *)this + 53) )
            {
LABEL_125:
              v55 = *((_QWORD *)this + 25);
              v56 = (unsigned int)((_DWORD)j - v52);
              v57 = (unsigned int)v56;
              j = (unsigned int *)(v55 + v56);
              memmove_0((void *)(v55 + (unsigned int)(v57 + 28)), j, (unsigned int)(*((_DWORD *)this + 52) - v57));
              v58 = *((_QWORD *)this + 25);
              *(_OWORD *)(v57 + v58) = 0;
              *(_OWORD *)(v57 + v58 + 12) = 0;
              *((_DWORD *)this + 52) += 28;
            }
            else
            {
              v54 = CoTaskMemRealloc(*((LPVOID *)this + 25), v53);
              if ( v54 )
              {
                *((_QWORD *)this + 25) = v54;
                *((_DWORD *)this + 53) = v53;
                goto LABEL_125;
              }
              UnserializedNamedValue = -2147024882;
            }
            v31 = UnserializedNamedValue < 0;
            if ( UnserializedNamedValue >= 0 )
            {
              *j = 28;
              j[1] = 1397773105;
              *(_OWORD *)(j + 2) = pitem;
              goto LABEL_64;
            }
          }
          else
          {
            UnserializedNamedValue = CMemPropStore::_Alloc(this, 4u);
            if ( UnserializedNamedValue >= 0 )
            {
              j = (unsigned int *)*((_QWORD *)this + 25);
              UnserializedNamedValue = 1;
              *((_DWORD *)this + 52) = 4;
              *j = 0;
LABEL_59:
              if ( !*j )
                goto LABEL_76;
            }
            v31 = UnserializedNamedValue < 0;
          }
          if ( v31 )
            j = 0;
          if ( UnserializedNamedValue >= 0 )
          {
LABEL_64:
            if ( (*((_BYTE *)this + 184) & 1) != 0 )
            {
              for ( k = (int *)(j + 6); ; k = (int *)((char *)k + v35) )
              {
                v35 = (unsigned int)*k;
                if ( !(_DWORD)v35 )
                  break;
              }
              goto LABEL_85;
            }
            v32 = *((_QWORD *)j + 1) - *(_QWORD *)&FMTID_UserDefinedProperties.Data1;
            p_Src = 0;
            if ( !v32 )
              v32 = *((_QWORD *)j + 2) - *(_QWORD *)FMTID_UserDefinedProperties.Data4;
            if ( v32 )
            {
              for ( k = (int *)(j + 6); *k && v66 != k[1]; k = (int *)((char *)k + (unsigned int)*k) )
                ;
LABEL_85:
              v62[0] = 0;
              v36 = 0;
              Src = 0;
              cb = 0;
              if ( LOWORD(pvarDest[0]) )
              {
                memset(&pvar, 0, sizeof(pvar));
                if ( LOWORD(pvarDest[0]) == 13
                  && pvarDest[1]
                  && (**(int (__fastcall ***)(PROPVARIANT, GUID *, ULONG *))pvarDest[1])(
                       pvarDest[1],
                       &GUID_0000000c_0000_0000_c000_000000000046,
                       &pvar.ulVal) >= 0 )
                {
                  pvar.vt = 66;
                  v39 = StgSerializePropVariantEx(1, &pvar, &cb, v62);
                  (*((void (__fastcall **)(LARGE_INTEGER))*pvar.pbstrVal + 2))(pvar.hVal);
                  v36 = v62[0];
                  Src = (void *)cb;
                  goto LABEL_91;
                }
                LODWORD(cb) = 0;
                v62[0] = 0;
                StgConvertVariantToPropertyNoEH(1, pvarDest);
                v37 = v62[0];
                if ( v62[0] < 0 )
                {
                  v38 = 0;
                  goto LABEL_115;
                }
                v38 = CoTaskMemAlloc((unsigned int)cb);
                if ( !v38 )
                {
                  v39 = -2147024882;
                  goto LABEL_91;
                }
                v36 = cb;
                StgConvertVariantToPropertyNoEH(1, pvarDest);
                v37 = v62[0];
                if ( v62[0] >= 0 )
                {
                  v39 = 0;
                  Src = v38;
                  goto LABEL_91;
                }
LABEL_115:
                v39 = MapNTStatusToHResult(v37);
                v40 = v39 < 0;
                if ( v39 < 0 )
                {
                  if ( v38 )
                    CoTaskMemFree(v38);
LABEL_91:
                  v40 = v39 < 0;
                }
                if ( v40 )
                  v36 = 0;
                if ( v36 )
                  v36 += 9;
              }
              v62[0] = *((_DWORD *)this + 50);
              v41 = v62[0];
              v42 = *k + (_DWORD)k - v62[0];
              v43 = v36 - *k;
              UnserializedNamedValue = 0;
              p_Src = (void **)v42;
              if ( v43 <= 0 )
              {
LABEL_101:
                v48 = v42;
                memmove_0(
                  (void *)(*((_QWORD *)this + 25) + v42 + v43),
                  (const void *)(*((_QWORD *)this + 25) + v42),
                  *((_DWORD *)this + 52) - v42);
                if ( v43 > 0 )
                  memset_0((void *)(v48 + *((_QWORD *)this + 25)), 0, v43);
                *((_DWORD *)this + 52) += v43;
                if ( v36 && (*k = v36, *((_BYTE *)k + 8) = 0, k[1] = v66, LOWORD(pvarDest[0])) )
                {
                  v49 = (char *)k + 9;
                  v50 = Src;
                  memcpy_0(v49, Src, (unsigned int)(v36 - 9));
                }
                else
                {
                  v50 = Src;
                }
                *j += v43;
              }
              else
              {
                v44 = v43 + *((_DWORD *)this + 52);
                v45 = (_DWORD)j - v62[0];
                LODWORD(cb) = (_DWORD)j - v62[0];
                if ( v44 + 256 < v44 )
                {
                  UnserializedNamedValue = -2147024362;
                }
                else
                {
                  UnserializedNamedValue = 0;
                  v46 = (v44 + 255) & 0xFFFFFF00;
                  if ( v46 > *((_DWORD *)this + 53) )
                  {
                    v51 = CoTaskMemRealloc(*((LPVOID *)this + 25), v46);
                    v41 = v62[0];
                    v45 = cb;
                    v42 = (unsigned int)p_Src;
                    if ( v51 )
                    {
                      *((_QWORD *)this + 25) = v51;
                      *((_DWORD *)this + 53) = v46;
                    }
                    else
                    {
                      UnserializedNamedValue = -2147024882;
                    }
                  }
                }
                if ( UnserializedNamedValue >= 0 )
                {
                  v47 = *((_QWORD *)this + 25);
                  j = (unsigned int *)(v47 + v45);
                  k = (int *)(v47 + (unsigned int)((_DWORD)k - v41));
                  goto LABEL_101;
                }
                v50 = Src;
              }
              CoTaskMemFree(v50);
              v6 = v60;
            }
            else
            {
              UnserializedNamedValue = -2147467259;
            }
          }
LABEL_108:
          PropVariantClear(pvarDest);
          if ( UnserializedNamedValue < 0 )
            break;
          v5 = v61;
          v60 = ++v6;
          goto LABEL_5;
        }
        if ( v27 == 1 && *(_DWORD *)(v26 + v18 + 20) == v66 )
        {
          v34 = *(_QWORD *)(v26 + v18 + 4) - pitem;
          if ( !v34 )
            v34 = *(_QWORD *)(v26 + v18 + 12) - *((_QWORD *)&pitem + 1);
          if ( !v34 )
            goto LABEL_49;
        }
      }
      v24 = (v24 + 1) % *((_DWORD *)this + 27);
    }
  }
LABEL_20:
  v13 = 0;
  v14 = 0;
  if ( UnserializedNamedValue < 0 )
  {
LABEL_33:
    CoTaskMemFree(*((LPVOID *)this + 25));
    *((_QWORD *)this + 25) = 0;
    *((_QWORD *)this + 26) = 0;
    goto LABEL_34;
  }
  while ( *((_QWORD *)this + 18) )
  {
    if ( (int)CMemPropStore::_EnsureGetAtArray(this, 0) >= 0 )
    {
      ItemPtr = (const OLECHAR **)g_pfn_DSA_GetItemPtr(*((HDSA *)this + 22), v14);
      if ( ItemPtr )
      {
        v13 = SysAllocString(*ItemPtr);
        v16 = v13 == 0 ? 0x8007000E : 0;
      }
      else
      {
        v16 = -2147467259;
      }
      if ( v16 >= 0 )
      {
        memset(&pvar, 0, sizeof(pvar));
        UnserializedNamedValue = CMemPropStore::_GetUnserializedNamedValue(this, v13, &pvar);
        if ( UnserializedNamedValue >= 0 )
        {
          UnserializedNamedValue = CMemPropStore::_SerializeValue(this, 0, v13, v17, &pvar);
          PropVariantClear((PROPVARIANT *)&pvar);
        }
        SysFreeString(v13);
        ++v14;
        if ( UnserializedNamedValue >= 0 )
          continue;
      }
    }
    if ( UnserializedNamedValue < 0 )
      goto LABEL_33;
    break;
  }
LABEL_34:
  v4 = (RTL_SRWLOCK *)((char *)this + 248);
LABEL_35:
  v19 = *((_QWORD *)this + 28);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
  else
    ReleaseSRWLockExclusive(v4);
  return (unsigned int)UnserializedNamedValue;
}

```

## disassembly

```asm
0x18003bff0  push    rbp
0x18003bff2  push    rbx
0x18003bff3  push    rsi
0x18003bff4  push    rdi
0x18003bff5  push    r12
0x18003bff7  push    r13
0x18003bff9  push    r14
0x18003bffb  push    r15
0x18003bffd  lea     rbp, [rsp-1Fh]
0x18003c002  sub     rsp, 0D8h
0x18003c009  mov     rax, cs:__security_cookie
0x18003c010  xor     rax, rsp
0x18003c013  mov     [rbp+57h+var_48], rax
0x18003c017  mov     rsi, rcx
0x18003c01a  xor     r13d, r13d
0x18003c01d  mov     rcx, [rcx+0E0h]
0x18003c024  mov     edi, r13d
0x18003c027  lea     rbx, [rsi+0F8h]
0x18003c02e  test    rcx, rcx
0x18003c031  jnz     loc_18003C438
0x18003c037  mov     rcx, rbx; SRWLock
0x18003c03a  call    cs:__imp_AcquireSRWLockExclusive
0x18003c040  cmp     [rsi+0C8h], r13
0x18003c047  jnz     loc_18003C22F
0x18003c04d  xorps   xmm0, xmm0
0x18003c050  mov     [rbp+57h+var_B8], r13d
0x18003c054  xor     eax, eax
0x18003c056  lea     r14, [rsi+78h]
0x18003c05a  movups  [rbp+57h+pitem], xmm0
0x18003c05e  mov     [rbp+57h+var_80], eax
0x18003c061  mov     r12d, r13d
0x18003c064  mov     [rbp+57h+var_B0], r14
0x18003c068  cmp     [rsi+0A8h], r13
0x18003c06f  jnz     loc_18003C112
0x18003c075  mov     edx, [rsi+68h]; cItemGrow
0x18003c078  mov     ecx, 14h; cbItem
0x18003c07d  mov     [rbp+57h+Src], r13
0x18003c081  call    cs:g_pfn_DSA_Create
0x18003c087  mov     [rbp+57h+Src], rax
0x18003c08b  mov     rcx, rax
0x18003c08e  test    rax, rax
0x18003c091  jz      loc_18003C12E
0x18003c097  cmp     [rsi+68h], r13d
0x18003c09b  jz      short loc_18003C0F1
0x18003c09d  lea     rax, [rbp+57h+Src]
0x18003c0a1  mov     [rbp+57h+var_98], rax
0x18003c0a5  lea     rax, [rbp+57h+var_98]
0x18003c0a9  mov     qword ptr [rbp+57h+var_A8], rax
0x18003c0ad  cmp     [r14], r13
0x18003c0b0  jz      short loc_18003C0F1
0x18003c0b2  mov     edx, 1
0x18003c0b7  mov     ebx, r13d
0x18003c0ba  cmp     ebx, [rsi+6Ch]
0x18003c0bd  jnb     short loc_18003C0ED
0x18003c0bf  mov     eax, ebx
0x18003c0c1  imul    rcx, rax, 38h ; '8'
0x18003c0c5  mov     rax, [r14]
0x18003c0c8  cmp     dword ptr [rcx+rax], 1
0x18003c0cc  jnz     short loc_18003C0E7
0x18003c0ce  lea     r8, [rax+18h]
0x18003c0d2  lea     rdx, [rax+4]
0x18003c0d6  add     r8, rcx
0x18003c0d9  add     rdx, rcx
0x18003c0dc  lea     rcx, [rbp+57h+var_A8]
0x18003c0e0  call    ??$s_EnumAdaptor@V_lambda_5ea173085f1a26f70939f45d8dbf8520_@@@?$CSimpleHashTable@U_tagpropertykey@@UCACHEDPROPERTY@CMemPropStore@@V?$CDefaultHashPolicy@U_tagpropertykey@@@@V?$CDefaultKeyCompare@U_tagpropertykey@@@@VCMemPropStoreResizePolicy@@VCDefaultRehashPolicy@@@@CAHPEBV_lambda_5ea173085f1a26f70939f45d8dbf8520_@@AEBU_tagpropertykey@@AEAUCACHEDPROPERTY@CMemPropStore@@@Z; CSimpleHashTable<_tagpropertykey,CMemPropStore::CACHEDPROPERTY,CDefaultHashPolicy<_tagpropertykey>,CDefaultKeyCompare<_tagpropertykey>,CMemPropStoreResizePolicy,CDefaultRehashPolicy>::s_EnumAdaptor<_lambda_5ea173085f1a26f70939f45d8dbf8520_>(_lambda_5ea173085f1a26f70939f45d8dbf8520_ const *,_tagpropertykey const &,CMemPropStore::CACHEDPROPERTY &)
0x18003c0e5  mov     edx, eax
0x18003c0e7  inc     ebx
0x18003c0e9  test    edx, edx
0x18003c0eb  jnz     short loc_18003C0BA
0x18003c0ed  mov     rcx, [rbp+57h+Src]
0x18003c0f1  xor     eax, eax
0x18003c0f3  lock cmpxchg [rsi+0A8h], rcx
0x18003c0fc  jnz     loc_18003C2E6
0x18003c102  mov     rcx, r13; hdsa
0x18003c105  mov     [rbp+57h+Src], rcx
0x18003c109  test    rcx, rcx
0x18003c10c  jnz     loc_18003C2DB
0x18003c112  mov     rcx, [rsi+0A8h]; hdsa
0x18003c119  lea     r8, [rbp+57h+pitem]; pitem
0x18003c11d  mov     edx, r12d; i
0x18003c120  call    cs:__imp_DSA_GetItem
0x18003c126  test    eax, eax
0x18003c128  jnz     loc_18003C1EF
0x18003c12e  mov     rbx, r13
0x18003c131  mov     r14d, r13d
0x18003c134  test    edi, edi
0x18003c136  js      loc_18003C209
0x18003c13c  cmp     [rsi+90h], r13
0x18003c143  jz      loc_18003C228
0x18003c149  xor     edx, edx; int
0x18003c14b  mov     rcx, rsi; this
0x18003c14e  call    ?_EnsureGetAtArray@CMemPropStore@@AEAAJH@Z; CMemPropStore::_EnsureGetAtArray(int)
0x18003c153  test    eax, eax
0x18003c155  js      loc_18003C1E9
0x18003c15b  mov     rcx, [rsi+0B0h]; hdsa
0x18003c162  mov     edx, r14d; i
0x18003c165  call    cs:g_pfn_DSA_GetItemPtr
0x18003c16b  test    rax, rax
0x18003c16e  jz      loc_18003C47E
0x18003c174  mov     rcx, [rax]; psz
0x18003c177  call    cs:__imp_SysAllocString
0x18003c17d  mov     rbx, rax
0x18003c180  neg     rax
0x18003c183  sbb     ecx, ecx
0x18003c185  not     ecx
0x18003c187  and     ecx, 8007000Eh
0x18003c18d  test    ecx, ecx
0x18003c18f  js      short loc_18003C1E9
0x18003c191  xorps   xmm0, xmm0
0x18003c194  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18003c198  xor     eax, eax
0x18003c19a  mov     rdx, rbx; unsigned __int16 *
0x18003c19d  mov     rcx, rsi; this
0x18003c1a0  mov     [rbp+57h+var_68], rax
0x18003c1a4  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003c1a8  call    ?_GetUnserializedNamedValue@CMemPropStore@@AEAAJPEBGPEAUtagPROPVARIANT@@@Z; CMemPropStore::_GetUnserializedNamedValue(ushort const *,tagPROPVARIANT *)
0x18003c1ad  mov     edi, eax
0x18003c1af  test    eax, eax
0x18003c1b1  js      short loc_18003C1D5
0x18003c1b3  lea     rax, [rbp+57h+pvar]
0x18003c1b7  mov     r8, rbx; unsigned __int16 *
0x18003c1ba  xor     edx, edx; struct _tagpropertykey *
0x18003c1bc  mov     [rsp+110h+var_F0], rax; struct tagPROPVARIANT *
0x18003c1c1  mov     rcx, rsi; this
0x18003c1c4  call    ?_SerializeValue@CMemPropStore@@AEAAJPEBU_tagpropertykey@@PEBGHPEBUtagPROPVARIANT@@@Z; CMemPropStore::_SerializeValue(_tagpropertykey const *,ushort const *,int,tagPROPVARIANT const *)
0x18003c1c9  lea     rcx, [rbp+57h+pvar]; pvar
0x18003c1cd  mov     edi, eax
0x18003c1cf  call    cs:__imp_PropVariantClear
0x18003c1d5  mov     rcx, rbx; bstrString
0x18003c1d8  call    cs:__imp_SysFreeString
0x18003c1de  inc     r14d
0x18003c1e1  test    edi, edi
0x18003c1e3  jns     loc_18003C13C
0x18003c1e9  test    edi, edi
0x18003c1eb  js      short loc_18003C209
0x18003c1ed  jmp     short loc_18003C228
0x18003c1ef  mov     r10, [r14]
0x18003c1f2  xor     eax, eax
0x18003c1f4  mov     [rbp+57h+var_50], rax
0x18003c1f8  xorps   xmm0, xmm0
0x18003c1fb  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x18003c1ff  test    r10, r10
0x18003c202  jnz     short loc_18003C26A
0x18003c204  mov     edi, 8002802Bh
0x18003c209  mov     rcx, [rsi+0C8h]; pv
0x18003c210  call    cs:__imp_CoTaskMemFree
0x18003c216  mov     [rsi+0C8h], r13
0x18003c21d  mov     qword ptr [rsi+0D0h], 0
0x18003c228  lea     rbx, [rsi+0F8h]
0x18003c22f  mov     rcx, [rsi+0E0h]
0x18003c236  test    rcx, rcx
0x18003c239  jnz     loc_18003C427
0x18003c23f  mov     rcx, rbx; SRWLock
0x18003c242  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c248  mov     eax, edi
0x18003c24a  mov     rcx, [rbp+57h+var_48]
0x18003c24e  xor     rcx, rsp; StackCookie
0x18003c251  call    __security_check_cookie
0x18003c256  add     rsp, 0D8h
0x18003c25d  pop     r15
0x18003c25f  pop     r14
0x18003c261  pop     r13
0x18003c263  pop     r12
0x18003c265  pop     rdi
0x18003c266  pop     rsi
0x18003c267  pop     rbx
0x18003c268  pop     rbp
0x18003c269  retn
0x18003c26a  mov     r8d, 12B9B0A5h
0x18003c270  mov     r9, r13
0x18003c273  movzx   edx, byte ptr [rbp+r9+57h+pitem]
0x18003c279  mov     ecx, r8d
0x18003c27c  imul    eax, r8d, 820h
0x18003c283  inc     r9
0x18003c286  shr     ecx, 2
0x18003c289  add     edx, eax
0x18003c28b  add     edx, ecx
0x18003c28d  xor     r8d, edx
0x18003c290  cmp     r9, 14h
0x18003c294  jb      short loc_18003C273
0x18003c296  mov     r9d, [rbp+57h+var_80]
0x18003c29a  btr     r8d, 1Fh
0x18003c29f  xor     edx, edx
0x18003c2a1  mov     eax, r8d
0x18003c2a4  div     dword ptr [rsi+6Ch]
0x18003c2a7  or      ecx, 0FFFFFFFFh
0x18003c2aa  mov     eax, edx
0x18003c2ac  imul    r8, rax, 38h ; '8'
0x18003c2b0  mov     eax, [r8+r10]
0x18003c2b4  cmp     eax, 2
0x18003c2b7  jz      loc_18003C830
0x18003c2bd  test    eax, eax
0x18003c2bf  jz      short loc_18003C2EF
0x18003c2c1  cmp     eax, 1
0x18003c2c4  jnz     short loc_18003C2D1
0x18003c2c6  cmp     [r8+r10+14h], r9d
0x18003c2cb  jz      loc_18003C3E4
0x18003c2d1  lea     eax, [rdx+1]
0x18003c2d4  xor     edx, edx
0x18003c2d6  div     dword ptr [rsi+6Ch]
0x18003c2d9  jmp     short loc_18003C2AA
0x18003c2db  call    cs:__imp_DSA_Destroy
0x18003c2e1  jmp     loc_18003C112
0x18003c2e6  mov     rcx, [rbp+57h+Src]
0x18003c2ea  jmp     loc_18003C109
0x18003c2ef  cmp     ecx, 0FFFFFFFFh
0x18003c2f2  cmovnz  edx, ecx
0x18003c2f5  mov     eax, edx
0x18003c2f7  imul    rcx, rax, 38h ; '8'
0x18003c2fb  cmp     dword ptr [rcx+r10], 1
0x18003c300  jnz     loc_18003C204
0x18003c306  lea     rdx, [r10+20h]
0x18003c30a  add     rdx, rcx; pvarSrc
0x18003c30d  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x18003c311  call    cs:__imp_PropVariantCopy
0x18003c317  mov     edi, eax
0x18003c319  test    eax, eax
0x18003c31b  js      loc_18003C209
0x18003c321  mov     rax, [rsi+0C8h]
0x18003c328  mov     r14, r13
0x18003c32b  test    rax, rax
0x18003c32e  jz      loc_18003C449
0x18003c334  mov     r14, rax
0x18003c337  mov     edi, 1
0x18003c33c  cmp     [r14], r13d
0x18003c33f  jz      loc_18003C406
0x18003c345  mov     rax, qword ptr [rbp+57h+pitem]
0x18003c349  sub     rax, [r14+8]
0x18003c34d  jnz     short loc_18003C357
0x18003c34f  mov     rax, qword ptr [rbp+57h+pitem+8]
0x18003c353  sub     rax, [r14+10h]
0x18003c357  test    rax, rax
0x18003c35a  jz      short loc_18003C364
0x18003c35c  mov     eax, [r14]
0x18003c35f  add     r14, rax
0x18003c362  jmp     short loc_18003C33C
0x18003c364  mov     edi, r13d
0x18003c367  cmp     [r14], r13d
0x18003c36a  jz      loc_18003C406
0x18003c370  test    edi, edi
0x18003c372  cmovs   r14, r13
0x18003c376  test    edi, edi
0x18003c378  js      loc_18003C66E
0x18003c37e  test    byte ptr [rsi+0B8h], 1
0x18003c385  jnz     loc_18003C488
0x18003c38b  mov     rax, [r14+8]
0x18003c38f  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data1
0x18003c396  mov     [rbp+57h+var_98], r13
0x18003c39a  jnz     short loc_18003C3A7
0x18003c39c  mov     rax, [r14+10h]
0x18003c3a0  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data4
0x18003c3a7  test    rax, rax
0x18003c3aa  jz      loc_18003C81E
0x18003c3b0  mov     edi, [rbp+57h+var_80]
0x18003c3b3  lea     rbx, [r14+18h]
0x18003c3b7  cmp     [rbx], r13d
0x18003c3ba  jz      loc_18003C496
0x18003c3c0  test    r13d, r13d
0x18003c3c3  jz      loc_18003C828
0x18003c3c9  lea     rcx, [rbx+9]
0x18003c3cd  xor     edx, edx
0x18003c3cf  call    cs:__imp_ualstrcmpiW
0x18003c3d5  test    eax, eax
0x18003c3d7  jz      loc_18003C496
0x18003c3dd  mov     eax, [rbx]
0x18003c3df  add     rbx, rax
0x18003c3e2  jmp     short loc_18003C3B7
0x18003c3e4  mov     rax, [r8+r10+4]
0x18003c3e9  sub     rax, qword ptr [rbp+57h+pitem]
0x18003c3ed  jnz     short loc_18003C3F8
0x18003c3ef  mov     rax, [r8+r10+0Ch]
0x18003c3f4  sub     rax, qword ptr [rbp+57h+pitem+8]
0x18003c3f8  test    rax, rax
0x18003c3fb  jnz     loc_18003C2D1
0x18003c401  jmp     loc_18003C2F5
0x18003c406  mov     ebx, [rsi+0D0h]
0x18003c40c  add     ebx, 1Ch
0x18003c40f  lea     eax, [rbx+100h]
0x18003c415  cmp     eax, ebx
0x18003c417  jnb     loc_18003C773
0x18003c41d  mov     edi, 80070216h
0x18003c422  jmp     loc_18003C66E
0x18003c427  mov     rax, [rcx]
0x18003c42a  mov     rax, [rax+20h]
0x18003c42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c433  jmp     loc_18003C248
0x18003c438  mov     rax, [rcx]
0x18003c43b  mov     rax, [rax+18h]
0x18003c43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c444  jmp     loc_18003C040
0x18003c449  mov     edx, 4; unsigned int
0x18003c44e  mov     rcx, rsi; this
0x18003c451  call    ?_Alloc@CMemPropStore@@AEAAJI@Z; CMemPropStore::_Alloc(uint)
0x18003c456  mov     edi, eax
0x18003c458  test    eax, eax
0x18003c45a  js      loc_18003C370
0x18003c460  mov     r14, [rsi+0C8h]
0x18003c467  mov     edi, 1
0x18003c46c  mov     dword ptr [rsi+0D0h], 4
0x18003c476  mov     [r14], r13d
  ... truncated ...
```
