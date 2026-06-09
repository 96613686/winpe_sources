# _StrictPropVariantCoerceType(tagPROPVARIANT *,tagPROPVARIANT const &,int,ushort)

- ea: `0x180009590`
- end: `0x180009d9c`
- name: `?_StrictPropVariantCoerceType@@YAJPEAUtagPROPVARIANT@@AEBU1@HG@Z`
- size: `2060`
- prototype: `__int64 __fastcall(VARIANT *pVar, const struct tagPROPVARIANT *, int, unsigned __int16)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009240`
- `0x180009590`

## callees

- `0x180007f40`
- `0x180009240`
- `0x180009590`
- `0x180009db0`
- `0x18000b410`
- `0x180015170`
- `0x18002ab10`
- `0x18003feb0`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009c3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009c86`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009c3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000985d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000985d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800099be`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800099be`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800099f6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800099f6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800099d9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800099d9`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x18000994d`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x18000994d`

## pseudocode

```c
__int64 __fastcall _StrictPropVariantCoerceType(PROPVARIANT *pVar, const struct tagPROPVARIANT *a2, int a3, VARTYPE a4)
{
  int v5; // r11d
  unsigned int vt; // r8d
  unsigned __int16 v7; // r10
  __int16 v8; // r9
  VARIANT *v10; // r14
  __int16 v11; // r12
  wchar_t v12; // cx
  char v13; // r15
  unsigned int ulVal; // edi
  int v15; // r8d
  __int64 v16; // rcx
  const PROPVARIANT *p_puuid; // r14
  char v18; // bl
  HRESULT ElemPtr; // ebx
  PROPVARIANT *v20; // rbx
  void *v21; // rdi
  unsigned int v23; // r15d
  unsigned __int64 v24; // rcx
  char *v25; // rax
  char *v26; // r14
  size_t v27; // rax
  PROPVARIANT *v28; // r12
  unsigned int v29; // esi
  void *v30; // rax
  size_t v31; // rax
  ULONG ElementCount; // eax
  VARTYPE v33; // ax
  SAFEARRAY *v34; // rcx
  HRESULT v35; // eax
  BYTE *pData; // rax
  int v37; // ebx
  SAFEARRAY *parray; // rbx
  int v39; // eax
  PROPVARIANT *v40; // rdi
  LARGE_INTEGER hVal; // rax
  const PROPVARIANT *v42; // rdx
  unsigned __int16 v43; // [rsp+30h] [rbp-39h]
  unsigned __int16 v44; // [rsp+34h] [rbp-35h]
  PROPVARIANT *pvar; // [rsp+40h] [rbp-29h] BYREF
  LONG rgIndices[2]; // [rsp+48h] [rbp-21h] BYREF
  void *ppvData; // [rsp+50h] [rbp-19h] BYREF
  VARIANT pPropVar; // [rsp+58h] [rbp-11h] BYREF

  pvar = pVar;
  v5 = a3;
  vt = a2->vt;
  v7 = a4 & 0xFFF;
  v44 = v7;
  v8 = vt & 0xFFF;
  v10 = (VARIANT *)pVar;
  v43 = vt & 0xFFF;
  v11 = 4112;
  if ( v7 > 0x1Fu )
  {
    if ( (unsigned int)v7 - 64 > 9 )
    {
      LOBYTE(v12) = 32;
      if ( v7 == 4095 )
        LOBYTE(v12) = 16;
    }
    else
    {
      v12 = aAggregateprope[v7 + 4];
    }
  }
  else
  {
    v12 = *((_WORD *)&CRGTypeSizes::m_ucTypeSizesA + v7);
  }
  v13 = v12;
  if ( vt == 8 )
    goto LABEL_4;
  if ( vt <= 0xFFF )
  {
    if ( vt != 4095 )
    {
      switch ( a2->vt )
      {
        case 2u:
        case 3u:
        case 4u:
        case 5u:
        case 6u:
        case 7u:
        case 9u:
        case 0xAu:
        case 0xBu:
        case 0xCu:
        case 0xDu:
        case 0xEu:
        case 0x10u:
        case 0x11u:
        case 0x12u:
        case 0x13u:
        case 0x14u:
        case 0x15u:
        case 0x16u:
        case 0x17u:
        case 0x1Eu:
        case 0x1Fu:
        case 0x40u:
        case 0x41u:
        case 0x42u:
        case 0x43u:
        case 0x44u:
        case 0x45u:
        case 0x47u:
        case 0x48u:
        case 0x49u:
          goto LABEL_4;
        default:
          goto LABEL_37;
      }
    }
    goto LABEL_4;
  }
LABEL_37:
  if ( (vt & 0x4000) != 0 )
  {
LABEL_4:
    ulVal = 1;
    goto LABEL_5;
  }
  if ( (vt & 0x1000) != 0 )
  {
    ulVal = a2->ulVal;
  }
  else
  {
    ulVal = 0;
    if ( (vt & 0x2000) != 0 )
    {
      parray = a2->parray;
      if ( SafeArrayGetDim(parray) == 1
        && (rgIndices[0] = 0, SafeArrayGetLBound(parray, 1u, rgIndices) >= 0)
        && (LODWORD(ppvData) = 0, SafeArrayGetUBound(parray, 1u, (LONG *)&ppvData) >= 0) )
      {
        v8 = v43;
        v7 = v44;
        v5 = a3;
        if ( (int)ppvData < rgIndices[0] )
          ulVal = 0;
        else
          ulVal = (_DWORD)ppvData - rgIndices[0] + 1;
      }
      else
      {
        v8 = v43;
        v7 = v44;
        v5 = a3;
      }
    }
  }
LABEL_5:
  if ( (a4 & 0x1000) != 0 )
  {
    v23 = v13 & 0x1F;
    v24 = v23 * (unsigned __int64)ulVal;
    if ( v24 > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v25 = (char *)CoTaskMemAlloc((unsigned int)v24);
      v26 = v25;
      if ( v25 )
      {
        v27 = CTCoAllocPolicy::_CoTaskMemSize(v25);
        memset_0(v26, 0, v27);
        ElemPtr = 0;
      }
      else
      {
        ElemPtr = -2147024882;
      }
      if ( ElemPtr >= 0 )
      {
        v28 = pvar;
        *(_WORD *)pvar = a4;
        v29 = 0;
        v28[2] = v26;
        while ( v29 < ulVal )
        {
          pvar = 0;
          ElemPtr = PropVariantGetElemPtr(a2, v29, (void **)&pvar);
          if ( ElemPtr < 0 || (ElemPtr = _StrictElementCoerceType(v43, pvar, v44, &v26[v23 * v29], a3), ElemPtr < 0) )
          {
            PropVariantClear(v28);
            return (unsigned int)ElemPtr;
          }
          ++*((_DWORD *)v28 + 2);
          ++v29;
        }
      }
    }
  }
  else
  {
    if ( (a4 & 0x2000) == 0 )
    {
      v15 = a2->vt;
      if ( (((_WORD)v15 - 4113) & 0xEFFF) == 0 && ulVal == 16 )
      {
        v8 = 72;
        ulVal = 1;
        v43 = 72;
      }
      if ( (a4 & 0x4000) != 0 )
      {
        if ( ulVal == 1 )
        {
          pvar = 0;
          ElemPtr = CTCoAllocPolicy::Alloc((void *)0xEFFF, 1u, v13 & 0x1F, (void **)&pvar);
          if ( ElemPtr >= 0 )
          {
            *(_QWORD *)rgIndices = 0;
            v39 = PropVariantGetElemPtr(a2, 0, (void **)rgIndices);
            v40 = pvar;
            ElemPtr = v39;
            if ( v39 < 0
              || (ElemPtr = _StrictElementCoerceType(v43, *(const void **)rgIndices, v44, pvar, a3), ElemPtr < 0) )
            {
              CoTaskMemFree(v40);
            }
            else
            {
              v10->llVal = (LONGLONG)v40;
            }
          }
          goto LABEL_22;
        }
      }
      else
      {
        if ( ulVal == 1 )
        {
          rgIndices[0] = 0;
          v16 = v15 & 0xFFF;
          p_puuid = 0;
          if ( (unsigned int)v16 > 0x1F )
          {
            if ( (unsigned int)(v16 - 64) > 9 )
            {
              if ( (_DWORD)v16 == 4095 )
              {
                v18 = 16;
              }
              else
              {
                v18 = 32;
                v11 = 32;
              }
            }
            else
            {
              _mm_lfence();
              v11 = aAggregateprope[v16 + 4];
              v18 = v11;
            }
          }
          else
          {
            _mm_lfence();
            v11 = *((_WORD *)&CRGTypeSizes::m_ucTypeSizesA + v16);
            v18 = v11;
          }
          if ( (v11 & 0x20) != 0 )
            goto LABEL_15;
          if ( (v15 & 0xFFFFF000) != 0 )
          {
            if ( (v15 & 0x8000u) != 0
              || (v15 & 0x1000) != 0 && ((v15 & 0x6000) != 0 || (v11 & 0x1000) == 0)
              || (v15 & 0x2000) != 0 && ((v15 & 0x5000) != 0 || (v11 & 0x2000) == 0)
              || (v15 & 0x4000) != 0 && ((v15 & 0x3000) != 0 || (v11 & 0x4000) == 0) )
            {
              goto LABEL_15;
            }
          }
          else if ( v11 >= 0 )
          {
LABEL_15:
            ElemPtr = -2147024809;
LABEL_16:
            if ( ElemPtr < 0 )
            {
LABEL_21:
              v10 = (VARIANT *)pvar;
              goto LABEL_22;
            }
            if ( v8 == 12 )
            {
              v42 = p_puuid;
              v10 = (VARIANT *)pvar;
              ElemPtr = PropVariantChangeType(pvar, v42, a3, a4);
LABEL_22:
              if ( !ElemPtr )
                v10->vt = a4;
              return (unsigned int)ElemPtr;
            }
LABEL_18:
            v20 = pvar + 1;
            if ( a4 == 72 )
            {
              v30 = CoTaskMemAlloc(0x10u);
              v21 = v30;
              if ( !v30 )
              {
                ElemPtr = -2147024882;
                goto LABEL_81;
              }
              v31 = CTCoAllocPolicy::_CoTaskMemSize(v30);
              memset_0(v21, 0, v31);
              *v20 = v21;
              v20 = (PROPVARIANT *)v21;
            }
            else
            {
              v21 = 0;
            }
            ElemPtr = _StrictElementCoerceType(v43, p_puuid, a4, v20, a3);
            if ( ElemPtr >= 0 )
              goto LABEL_21;
LABEL_81:
            CoTaskMemFree(v21);
            return (unsigned int)ElemPtr;
          }
          ElementCount = PropVariantGetElementCount((const PROPVARIANT *const)a2);
          if ( ElementCount <= rgIndices[0] )
          {
            v8 = v43;
            ElemPtr = -2147319765;
            goto LABEL_16;
          }
          v33 = a2->vt;
          if ( (a2->vt & 0x1000) == 0 )
          {
            if ( (v33 & 0x2000) != 0 )
            {
              v34 = a2->parray;
              ppvData = 0;
              v35 = SafeArrayPtrOfIndex(v34, rgIndices, &ppvData);
              p_puuid = (const PROPVARIANT *)ppvData;
              ElemPtr = v35;
            }
            else
            {
              if ( (v33 & 0x4000) == 0 )
              {
                if ( (unsigned __int16)(v33 - 71) > 1u )
                {
                  p_puuid = (const PROPVARIANT *)&a2->puuid;
                }
                else
                {
                  if ( !a2->hVal.QuadPart )
                  {
LABEL_60:
                    v8 = v43;
                    ElemPtr = -2147024809;
                    goto LABEL_16;
                  }
                  p_puuid = a2->pvarVal;
                }
LABEL_57:
                ElemPtr = 0;
LABEL_58:
                if ( (a2->vt & 0xFFF) != 0x49 )
                {
                  switch ( a2->vt & 0xFFF )
                  {
                    case 0xD:
                    case 0x1E:
                    case 0x1F:
                    case 0x42:
                    case 0x43:
                    case 0x44:
                    case 0x45:
                      goto LABEL_59;
                    case 0x41:
                    case 0x46:
                      v8 = v43;
                      if ( !*((_QWORD *)p_puuid + 1) )
                        ElemPtr = -2147024809;
                      break;
                    default:
                      goto LABEL_63;
                  }
                  goto LABEL_16;
                }
LABEL_59:
                if ( !*p_puuid )
                  goto LABEL_60;
LABEL_63:
                v8 = v43;
                goto LABEL_16;
              }
              hVal = a2->hVal;
              if ( hVal.QuadPart )
                p_puuid = a2->pvarVal;
              ElemPtr = 0;
              if ( !hVal.QuadPart )
                ElemPtr = -2147024809;
            }
            if ( ElemPtr < 0 )
              goto LABEL_63;
            goto LABEL_58;
          }
          pData = a2->bstrblobVal.pData;
          if ( !pData )
          {
            ElemPtr = -2147024809;
            goto LABEL_63;
          }
          v37 = v18 & 0x1F;
          if ( !v37 )
          {
            ElemPtr = -2147467263;
            goto LABEL_63;
          }
          p_puuid = (const PROPVARIANT *)&pData[rgIndices[0] * v37];
          goto LABEL_57;
        }
        if ( !ulVal && !v8 )
        {
          p_puuid = 0;
          goto LABEL_18;
        }
      }
      return (unsigned int)-2147316576;
    }
    memset(&pPropVar, 0, sizeof(pPropVar));
    ElemPtr = _StrictPropVariantCoerceType(&pPropVar, a2, v5, v7 | 0x1000u);
    if ( ElemPtr >= 0 )
    {
      ElemPtr = PropVariantToVariant((const PROPVARIANT *)&pPropVar, v10);
      PropVariantClear((PROPVARIANT *)&pPropVar);
    }
  }
  return (unsigned int)ElemPtr;
}

```

## disassembly

```asm
0x180009590  push    rbp
0x180009592  push    rbx
0x180009593  push    rsi
0x180009594  push    rdi
0x180009595  push    r12
0x180009597  push    r13
0x180009599  push    r14
0x18000959b  push    r15
0x18000959d  lea     rbp, [rsp-1Fh]
0x1800095a2  sub     rsp, 88h
0x1800095a9  mov     rax, cs:__security_cookie
0x1800095b0  xor     rax, rsp
0x1800095b3  mov     [rbp+57h+var_50], rax
0x1800095b7  movzx   esi, r9w
0x1800095bb  mov     [rbp+57h+flags], r8d
0x1800095bf  mov     ebx, 0FFFh
0x1800095c4  mov     [rbp+57h+pvar], rcx
0x1800095c8  mov     r11d, r8d
0x1800095cb  movzx   r10d, si
0x1800095cf  movzx   r8d, word ptr [rdx]
0x1800095d3  and     r10w, bx
0x1800095d7  movzx   r9d, r8w
0x1800095db  mov     [rbp+57h+var_8C], r10w
0x1800095e0  and     r9w, bx
0x1800095e4  mov     r13, rdx
0x1800095e7  movzx   edx, r10w
0x1800095eb  mov     r14, rcx
0x1800095ee  mov     [rbp+57h+var_90], r9d
0x1800095f2  mov     r12d, 1010h
0x1800095f8  lea     rcx, __ImageBase
0x1800095ff  cmp     edx, 1Fh
0x180009602  ja      loc_180009A32
0x180009608  movsxd  rax, edx
0x18000960b  movzx   ecx, ds:rva ?m_ucTypeSizesA@CRGTypeSizes@@0QBGB[rcx+rax*2]; ushort const near * const CRGTypeSizes::m_ucTypeSizesA ...
0x180009613  movzx   r15d, cx
0x180009617  mov     eax, r8d
0x18000961a  mov     edx, 2000h
0x18000961f  mov     ebx, 4000h
0x180009624  cmp     r8d, 8
0x180009628  jnz     loc_1800097F9
0x18000962e  mov     edi, 1; jumptable 0000000180009C36 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x180009633  mov     ecx, 1000h
0x180009638  test    cx, si
0x18000963b  jnz     loc_180009745
0x180009641  test    dx, si
0x180009644  jnz     loc_180009C46
0x18000964a  movzx   r8d, word ptr [r13+0]
0x18000964f  mov     ecx, 1011h
0x180009654  movzx   eax, r8w
0x180009658  sub     ax, cx
0x18000965b  mov     ecx, 0EFFFh; void *
0x180009660  test    cx, ax
0x180009663  jz      loc_180009831
0x180009669  test    bx, si
0x18000966c  jnz     loc_180009A98
0x180009672  cmp     edi, 1
0x180009675  jnz     loc_180009966
0x18000967b  mov     ecx, r8d
0x18000967e  mov     [rbp+57h+rgIndices], 0
0x180009685  and     ecx, 0FFFh
0x18000968b  xor     r14d, r14d
0x18000968e  cmp     ecx, 1Fh
0x180009691  ja      loc_180009A70
0x180009697  lfence
0x18000969a  lea     r10, __ImageBase
0x1800096a1  movzx   r12d, ds:rva ?m_ucTypeSizesA@CRGTypeSizes@@0QBGB[r10+rcx*2]; ushort const near * const CRGTypeSizes::m_ucTypeSizesA ...
0x1800096aa  movzx   ebx, r12w
0x1800096ae  test    r12b, 20h
0x1800096b2  jnz     short loc_1800096CB
0x1800096b4  test    r8d, 0FFFFF000h
0x1800096bb  jnz     loc_18000988F
0x1800096c1  test    r12w, r12w
0x1800096c5  js      loc_180009CC1
0x1800096cb  mov     ebx, 80070057h
0x1800096d0  test    ebx, ebx
0x1800096d2  js      short loc_180009717
0x1800096d4  cmp     r9w, 0Ch
0x1800096d9  jz      loc_180009CE5
0x1800096df  mov     rbx, [rbp+57h+pvar]
0x1800096e3  add     rbx, 8
0x1800096e7  cmp     si, 48h ; 'H'
0x1800096eb  jz      loc_180009858
0x1800096f1  xor     edi, edi
0x1800096f3  mov     eax, [rbp+57h+flags]
0x1800096f6  mov     r9, rbx; void *
0x1800096f9  movzx   ecx, word ptr [rbp+57h+var_90]; unsigned __int16
0x1800096fd  movzx   r8d, si; unsigned __int16
0x180009701  mov     rdx, r14; void *
0x180009704  mov     [rsp+0C0h+var_A0], eax; int
0x180009708  call    ?_StrictElementCoerceType@@YAJGPEBXGPEAXH@Z; _StrictElementCoerceType(ushort,void const *,ushort,void *,int)
0x18000970d  mov     ebx, eax
0x18000970f  test    eax, eax
0x180009711  js      loc_180009A62
0x180009717  mov     r14, [rbp+57h+pvar]
0x18000971b  test    ebx, ebx
0x18000971d  jnz     short loc_180009723
0x18000971f  mov     [r14], si
0x180009723  mov     eax, ebx
0x180009725  mov     rcx, [rbp+57h+var_50]
0x180009729  xor     rcx, rsp; StackCookie
0x18000972c  call    __security_check_cookie
0x180009731  add     rsp, 88h
0x180009738  pop     r15
0x18000973a  pop     r14
0x18000973c  pop     r13
0x18000973e  pop     r12
0x180009740  pop     rdi
0x180009741  pop     rsi
0x180009742  pop     rbx
0x180009743  pop     rbp
0x180009744  retn
0x180009745  and     r15d, 1Fh
0x180009749  mov     ecx, edi
0x18000974b  mov     eax, r15d
0x18000974e  imul    rcx, rax
0x180009752  mov     eax, 0FFFFFFFFh
0x180009757  cmp     rcx, rax
0x18000975a  ja      loc_18000984E
0x180009760  mov     ecx, ecx; cb
0x180009762  call    cs:__imp_CoTaskMemAlloc
0x180009768  mov     r14, rax
0x18000976b  test    rax, rax
0x18000976e  jz      loc_1800099A1
0x180009774  mov     rcx, rax; void *
0x180009777  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000977c  mov     r8, rax; Size
0x18000977f  xor     edx, edx; Val
0x180009781  mov     rcx, r14; void *
0x180009784  call    memset_0
0x180009789  xor     ebx, ebx
0x18000978b  test    ebx, ebx
0x18000978d  js      short loc_180009723
0x18000978f  mov     r12, [rbp+57h+pvar]
0x180009793  mov     [r12], si
0x180009798  xor     esi, esi
0x18000979a  mov     [r12+10h], r14
0x18000979f  cmp     esi, edi
0x1800097a1  jnb     short loc_180009723
0x1800097a3  lea     r8, [rbp+57h+pvar]; void **
0x1800097a7  mov     [rbp+57h+pvar], 0
0x1800097af  mov     edx, esi; unsigned int
0x1800097b1  mov     rcx, r13; struct tagPROPVARIANT *
0x1800097b4  call    ?PropVariantGetElemPtr@@YAJAEBUtagPROPVARIANT@@KPEAPEAX@Z; PropVariantGetElemPtr(tagPROPVARIANT const &,ulong,void * *)
0x1800097b9  mov     ebx, eax
0x1800097bb  test    eax, eax
0x1800097bd  js      loc_180009C38
0x1800097c3  mov     eax, [rbp+57h+flags]
0x1800097c6  mov     r9d, esi
0x1800097c9  movzx   r8d, [rbp+57h+var_8C]; unsigned __int16
0x1800097ce  mov     rdx, [rbp+57h+pvar]; void *
0x1800097d2  movzx   ecx, word ptr [rbp+57h+var_90]; unsigned __int16
0x1800097d6  imul    r9d, r15d
0x1800097da  mov     [rsp+0C0h+var_A0], eax; int
0x1800097de  add     r9, r14; void *
0x1800097e1  call    ?_StrictElementCoerceType@@YAJGPEBXGPEAXH@Z; _StrictElementCoerceType(ushort,void const *,ushort,void *,int)
0x1800097e6  mov     ebx, eax
0x1800097e8  test    eax, eax
0x1800097ea  js      loc_180009C38
0x1800097f0  inc     dword ptr [r12+8]
0x1800097f5  inc     esi
0x1800097f7  jmp     short loc_18000979F
0x1800097f9  cmp     eax, 0FFFh
0x1800097fe  ja      short def_180009C36; jumptable 0000000180009C36 default case, cases 8,15,24-29,32-63,70
0x180009800  jz      loc_18000962E; jumptable 0000000180009C36 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x180009806  add     eax, 0FFFFFFFEh; switch 72 cases
0x180009809  cmp     eax, 47h
0x18000980c  jbe     loc_180009C14
0x180009812  test    bx, r8w; jumptable 0000000180009C36 default case, cases 8,15,24-29,32-63,70
0x180009816  jnz     loc_18000962E; jumptable 0000000180009C36 cases 2-7,9-14,16-23,30,31,64-69,71-73
0x18000981c  bt      r8w, 0Ch
0x180009822  jnb     loc_1800099AB
0x180009828  mov     edi, [r13+8]
0x18000982c  jmp     loc_180009633
0x180009831  cmp     edi, 10h
0x180009834  jnz     loc_180009669
0x18000983a  mov     r9d, 48h ; 'H'
0x180009840  mov     edi, 1
0x180009845  mov     [rbp+57h+var_90], r9d
0x180009849  jmp     loc_180009669
0x18000984e  mov     ebx, 80070216h
0x180009853  jmp     loc_180009723
0x180009858  mov     ecx, 10h; cb
0x18000985d  call    cs:__imp_CoTaskMemAlloc
0x180009863  mov     rdi, rax
0x180009866  test    rax, rax
0x180009869  jz      loc_180009A5D
0x18000986f  mov     rcx, rax; void *
0x180009872  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180009877  mov     r8, rax; Size
0x18000987a  xor     edx, edx; Val
0x18000987c  mov     rcx, rdi; void *
0x18000987f  call    memset_0
0x180009884  mov     [rbx], rdi
0x180009887  mov     rbx, rdi
0x18000988a  jmp     loc_1800096F3
0x18000988f  test    r8w, r8w
0x180009893  js      loc_1800096CB
0x180009899  mov     edi, 1000h
0x18000989e  test    di, r8w
0x1800098a2  jnz     loc_180009C03
0x1800098a8  mov     r15d, 2000h
0x1800098ae  test    r15w, r8w
0x1800098b2  jnz     loc_180009CAD
0x1800098b8  bt      r8w, 0Eh
0x1800098be  jb      loc_180009B73
0x1800098c4  mov     rcx, r13; propvar
0x1800098c7  call    PropVariantGetElementCount
0x1800098cc  mov     ecx, [rbp+57h+rgIndices]
0x1800098cf  cmp     eax, ecx
0x1800098d1  jbe     loc_180009BD0
0x1800098d7  movzx   eax, word ptr [r13+0]
0x1800098dc  test    di, ax
0x1800098df  jnz     loc_180009978
0x1800098e5  mov     edi, 80070057h
0x1800098ea  test    r15w, ax
0x1800098ee  jnz     short loc_18000993D
0x1800098f0  bt      ax, 0Eh
0x1800098f5  jb      loc_180009BB8
0x1800098fb  sub     ax, 47h ; 'G'
0x1800098ff  cmp     ax, 1
0x180009903  ja      short loc_180009913
0x180009905  mov     rax, [r13+8]
0x180009909  test    rax, rax
0x18000990c  jz      short loc_180009932
0x18000990e  mov     r14, rax
0x180009911  jmp     short loc_180009917
0x180009913  lea     r14, [r13+8]
0x180009917  xor     ebx, ebx
0x180009919  movzx   eax, word ptr [r13+0]
0x18000991e  and     eax, 0FFFh
0x180009923  cmp     eax, 49h ; 'I'
0x180009926  jnz     loc_180009B34
0x18000992c  cmp     qword ptr [r14], 0; jumptable 0000000180009B5B cases 13,30,31,66-69
0x180009930  jnz     short def_180009B5B; jumptable 0000000180009B5B default case, cases 14-29,32-64
0x180009932  mov     r9d, [rbp+57h+var_90]
0x180009936  mov     ebx, edi
0x180009938  jmp     loc_1800096D0
0x18000993d  mov     rcx, [r13+8]; psa
0x180009941  lea     r8, [rbp+57h+ppvData]; ppvData
0x180009945  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180009949  mov     [rbp+57h+ppvData], r14
0x18000994d  call    cs:__imp_SafeArrayPtrOfIndex
0x180009953  mov     r14, [rbp+57h+ppvData]
0x180009957  mov     ebx, eax
0x180009959  test    ebx, ebx
0x18000995b  jns     short loc_180009919
0x18000995d  mov     r9d, [rbp+57h+var_90]; jumptable 0000000180009B5B default case, cases 14-29,32-64
0x180009961  jmp     loc_1800096D0
0x180009966  test    edi, edi
0x180009968  jz      loc_180009A4B
0x18000996e  mov     ebx, 80028CA0h
0x180009973  jmp     loc_180009723
0x180009978  mov     rax, [r13+10h]
0x18000997c  test    rax, rax
0x18000997f  jz      loc_180009CDB
0x180009985  and     ebx, 1Fh
0x180009988  jz      loc_180009CD1
0x18000998e  imul    ebx, ecx
0x180009991  mov     edi, 80070057h
0x180009996  mov     r14d, ebx
0x180009999  add     r14, rax
0x18000999c  jmp     loc_180009917
0x1800099a1  mov     ebx, 8007000Eh
0x1800099a6  jmp     loc_18000978B
0x1800099ab  xor     edi, edi
0x1800099ad  test    dx, r8w
0x1800099b1  jz      loc_180009633
0x1800099b7  mov     rbx, [r13+8]
0x1800099bb  mov     rcx, rbx; psa
0x1800099be  call    cs:__imp_SafeArrayGetDim
0x1800099c4  cmp     eax, 1
0x1800099c7  jnz     loc_180009B18
0x1800099cd  lea     r8, [rbp+57h+rgIndices]; plLbound
0x1800099d1  mov     [rbp+57h+rgIndices], edi
0x1800099d4  mov     edx, eax; nDim
0x1800099d6  mov     rcx, rbx; psa
0x1800099d9  call    cs:__imp_SafeArrayGetLBound
0x1800099df  test    eax, eax
0x1800099e1  js      loc_180009B18
0x1800099e7  lea     r8, [rbp+57h+ppvData]; plUbound
0x1800099eb  mov     dword ptr [rbp+57h+ppvData], edi
0x1800099ee  mov     edx, 1; nDim
0x1800099f3  mov     rcx, rbx; psa
0x1800099f6  call    cs:__imp_SafeArrayGetUBound
0x1800099fc  test    eax, eax
0x1800099fe  js      loc_180009B18
0x180009a04  mov     edi, dword ptr [rbp+57h+ppvData]
0x180009a07  mov     edx, 2000h
0x180009a0c  mov     eax, [rbp+57h+rgIndices]
0x180009a0f  mov     ebx, 4000h
0x180009a14  mov     r9d, [rbp+57h+var_90]
0x180009a18  movzx   r10d, [rbp+57h+var_8C]
0x180009a1d  mov     r11d, [rbp+57h+flags]
0x180009a21  cmp     edi, eax
0x180009a23  jl      loc_180009BDE
0x180009a29  sub     edi, eax
0x180009a2b  inc     edi
0x180009a2d  jmp     loc_180009633
0x180009a32  lea     eax, [rdx-40h]
0x180009a35  cmp     eax, 9
  ... truncated ...
```
