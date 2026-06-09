# CSdtEvent::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,ushort const *,void * *)

- ea: `0x180045cb0`
- end: `0x1800465aa`
- name: `?GetTable@CSdtEvent@@UEAAJAEBU_GUID@@0PEAX1KKPEBGPEAPEAX@Z`
- size: `2298`
- prototype: `int(CSdtEvent *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x1800113fc`
- `0x180014ec8`
- `0x180045cb0`
- `0x180055816`
- `0x18005582e`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004644a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004644a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180046137`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x180046137`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046318`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046318`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004601b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004639b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046407`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004601b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004639b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046407`

## pseudocode

```c
__int64 __fastcall CSdtEvent::GetTable(
        struct _GUID *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        _QWORD *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        const unsigned __int16 *a8,
        void **a9)
{
  __int64 v13; // r13
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 near **v14; // r14
  unsigned __int16 * near **v15; // r12
  unsigned int v16; // r14d
  __int64 v17; // r8
  __int64 v18; // r10
  __int64 v19; // rbx
  void *v20; // rcx
  __int64 v21; // rbx
  unsigned __int64 v22; // rbx
  unsigned __int16 *v23; // rax
  HRESULT hr; // ebx
  COSERVERINFO *p_pServerInfo; // rcx
  DWORD v26; // eax
  IUnknown *pItf; // rdi
  unsigned __int16 * near **v28; // r12
  unsigned int v29; // eax
  int v30; // ecx
  unsigned int v31; // eax
  bool v32; // cc
  const unsigned __int16 *v33; // r8
  _DWORD *v34; // r9
  OLECHAR *v35; // r8
  __int64 v36; // rbx
  void *v37; // rax
  __int64 v38; // rbx
  void *v39; // rax
  unsigned __int8 *Data4; // rcx
  __int64 v41; // [rsp+0h] [rbp-988h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-938h]
  IUnknown *v43; // [rsp+58h] [rbp-930h]
  __int64 v44; // [rsp+60h] [rbp-928h]
  unsigned int v45; // [rsp+68h] [rbp-920h]
  int v46; // [rsp+6Ch] [rbp-91Ch]
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 near **v47; // [rsp+70h] [rbp-918h]
  unsigned __int16 * near **v48; // [rsp+78h] [rbp-910h]
  LPVOID ppv; // [rsp+80h] [rbp-908h] BYREF
  int v50; // [rsp+88h] [rbp-900h]
  unsigned int v51; // [rsp+8Ch] [rbp-8FCh]
  __int64 *v52; // [rsp+90h] [rbp-8F8h]
  int v53; // [rsp+98h] [rbp-8F0h]
  COSERVERINFO *v54; // [rsp+A0h] [rbp-8E8h]
  void **v55; // [rsp+A8h] [rbp-8E0h]
  MULTI_QI pResults; // [rsp+B0h] [rbp-8D8h] BYREF
  GUID *v57; // [rsp+C8h] [rbp-8C0h]
  __int128 v58; // [rsp+D0h] [rbp-8B8h]
  COSERVERINFO pServerInfo; // [rsp+E0h] [rbp-8A8h] BYREF
  OLECHAR sz[40]; // [rsp+100h] [rbp-888h] BYREF
  unsigned __int16 Src[1024]; // [rsp+150h] [rbp-838h] BYREF

  v52 = &v41;
  v55 = a9;
  ppv = 0;
  memset(&pServerInfo, 0, sizeof(pServerInfo));
  if ( *(_OWORD *)a2 != didCOMSERVICES || !a4 )
    return 2147942487LL;
  if ( !a9 )
    return 2147500035LL;
  v43 = 0;
  v13 = 0;
  v44 = 0;
  v54 = 0;
  v50 = 23;
  v46 = 0;
  this[6] = *a3;
  if ( a6 - 1 > 1 )
    return 2148599811LL;
  if ( *(_QWORD *)&a3->Data1 == tidEVENTCLASSES && *(_QWORD *)a3->Data4 == 0x30202C3078302990LL )
  {
    *(_DWORD *)this[3].Data4 = 0;
    v14 = &eventClassMeta;
    v15 = &eventClassColumns;
    v42 = 10;
LABEL_10:
    v48 = v15;
    v47 = v14;
    goto LABEL_27;
  }
  if ( *(_QWORD *)&a3->Data1 == tidSUBSCRIPTIONS && *(_QWORD *)a3->Data4 == 0x30202C3078302990LL
    || *(_QWORD *)&a3->Data1 == tidTRANSIENTSUBSCRIPTIONS && *(_QWORD *)a3->Data4 == 0x432C75F800021B1LL )
  {
    *(_DWORD *)this[3].Data4 = 1;
    v14 = &subscriptionMeta;
    v15 = &subscriptionColumns;
    v42 = 21;
    goto LABEL_10;
  }
  if ( *(_QWORD *)&a3->Data1 == tidPUBLISHERPROPERTIES && *(_QWORD *)a3->Data4 == 0x30202C3078302990LL
    || *(_QWORD *)&a3->Data1 == tidTRANSIENTPUBLISHERPROPERTIES && *(_QWORD *)a3->Data4 == 0x432C75F800023B1LL )
  {
    *(_DWORD *)this[3].Data4 = 2;
    v14 = &propertyBagMeta;
    v47 = &propertyBagMeta;
    v48 = &propertyBagColumns;
  }
  else
  {
    if ( (*(_QWORD *)&a3->Data1 != tidSUBSCRIBERPROPERTIES || *(_QWORD *)a3->Data4 != 0x30202C3078302990LL)
      && (*(_QWORD *)&a3->Data1 != tidTRANSIENTSUBSCRIBERPROPERTIES || *(_QWORD *)a3->Data4 != 0x432C75F800023B1LL) )
    {
LABEL_111:
      hr = -2147024809;
      goto LABEL_112;
    }
    *(_DWORD *)this[3].Data4 = 3;
    v47 = &propertyBagMeta;
    v48 = &propertyBagColumns;
    v14 = &propertyBagMeta;
  }
  v42 = 6;
LABEL_27:
  if ( a6 == 1 )
  {
    Src[0] = 0;
    v16 = 0;
    v45 = 0;
    v17 = tidTRANSIENTSUBSCRIPTIONS;
    v18 = tidTRANSIENTPUBLISHERPROPERTIES;
    v19 = tidTRANSIENTSUBSCRIBERPROPERTIES;
    while ( v16 < (unsigned int)a5 && HIDWORD(a4[3 * v16 + 1]) > 0xF0000000 )
    {
      if ( HIDWORD(a4[3 * v16 + 1]) == -268435454 )
      {
        if ( !a4[3 * v16] )
        {
          local_unwind_0(v52, &loc_180045F88);
          return 2148599811LL;
        }
        v20 = *(void **)this[5].Data4;
        if ( v20 )
        {
          operator delete[](v20);
          LOWORD(v20) = 0;
          *(_QWORD *)this[5].Data4 = 0;
          v17 = tidTRANSIENTSUBSCRIPTIONS;
          v18 = tidTRANSIENTPUBLISHERPROPERTIES;
          v19 = tidTRANSIENTSUBSCRIBERPROPERTIES;
        }
        if ( *(_QWORD *)&a3->Data1 == v17 && *(_QWORD *)a3->Data4 == 0x432C75F800021B1LL
          || *(_QWORD *)&a3->Data1 == v18 && *(_QWORD *)a3->Data4 == 0x432C75F800023B1LL
          || *(_QWORD *)&a3->Data1 == v19 && *(_QWORD *)a3->Data4 == 0x432C75F800023B1LL )
        {
          v21 = -1;
          do
            ++v21;
          while ( *(_WORD *)(a4[3 * v16] + 2 * v21) != (_WORD)v20 );
          v22 = v21 + 1;
          v23 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v22, 2u));
          *(_QWORD *)this[5].Data4 = v23;
          hr = StringCchCopyW(v23, v22, (const unsigned __int16 *)a4[3 * v16]);
          if ( hr < 0 )
          {
            operator delete[](*(void **)this[5].Data4);
            *(_QWORD *)this[5].Data4 = 0;
            goto LABEL_46;
          }
          v17 = tidTRANSIENTSUBSCRIPTIONS;
          v18 = tidTRANSIENTPUBLISHERPROPERTIES;
          v19 = tidTRANSIENTSUBSCRIBERPROPERTIES;
        }
      }
      v45 = ++v16;
    }
    if ( *(_QWORD *)this[5].Data4 )
    {
      pServerInfo.pwszName = *(LPWSTR *)this[5].Data4;
      pServerInfo.pAuthInfo = 0;
      pServerInfo.dwReserved1 = 0;
      pServerInfo.dwReserved2 = 0;
      p_pServerInfo = &pServerInfo;
      v26 = 16;
    }
    else
    {
      p_pServerInfo = v54;
      v26 = v50;
    }
    pResults.pItf = 0;
    *(_QWORD *)&pResults.hr = 0;
    v58 = 0;
    pResults.pIID = &IID_IEventSystem;
    v57 = &IID_IEventSystem2;
    hr = CoCreateInstanceEx(&CLSID_CEventSystem, 0, v26, p_pServerInfo, 2u, &pResults);
    if ( hr < 0 )
      goto LABEL_46;
    if ( pResults.hr < 0 )
    {
      hr = pResults.hr;
      goto LABEL_46;
    }
    pItf = pResults.pItf;
    v43 = pResults.pItf;
    hr = DWORD2(v58);
    if ( (SDWORD2(v58) & 0x80000000) == 0 )
    {
      v44 = v58;
      hr = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)v58 + 104LL))(v58, &this[7].Data2);
      if ( hr < 0 )
        goto LABEL_46;
      goto LABEL_59;
    }
    if ( DWORD2(v58) == -2147467262 )
    {
      *(_DWORD *)&this[7].Data2 = 1;
LABEL_59:
      v28 = v48;
      while ( 1 )
      {
        v51 = v16;
        if ( v16 >= (unsigned int)a5 )
        {
          v36 = -1;
          do
            ++v36;
          while ( Src[v36] );
          v37 = CoTaskMemAlloc(saturated_mul(v36 + 1, 2u));
          *(_QWORD *)&this[4].Data1 = v37;
          if ( !v37 )
            goto LABEL_97;
          memcpy_0(v37, Src, 2 * v36 + 2);
          v14 = v47;
LABEL_104:
          hr = CoCreateInstance(&clsidSTDISP, 0, 0x17u, &IID_ISimpleTableDispenser, &ppv);
          if ( hr >= 0 )
          {
            hr = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, _QWORD, _QWORD, unsigned int, int, unsigned __int8 *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   didMEMORY,
                   tidMEMORY_SHAPEABLE,
                   0,
                   0,
                   a6,
                   8,
                   this[2].Data4);
            if ( hr >= 0 )
            {
              hr = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))this[2].Data4)(
                     *(_QWORD *)this[2].Data4,
                     &IID_ISimpleTableControl,
                     (char *)&this[3]);
              if ( hr >= 0 )
              {
                hr = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct __MIDL___MIDL_itf_stable_0000_0000_0001 near **))(**(_QWORD **)&this[3].Data1 + 24LL))(
                       *(_QWORD *)&this[3].Data1,
                       8,
                       v42,
                       v14);
                if ( hr >= 0 )
                {
                  Data4 = this->Data4;
                  if ( this == (struct _GUID *)8 )
                    Data4 = 0;
                  *v55 = Data4;
                  (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)Data4 + 8LL))(Data4);
                  _InterlockedIncrement((volatile signed __int32 *)&this[2]);
                  hr = 0;
                }
              }
            }
          }
          goto LABEL_46;
        }
        v29 = HIDWORD(a4[3 * v16 + 1]);
        if ( v29 > v42 )
        {
          local_unwind_0(v52, &loc_1800461F1);
          return 2148599811LL;
        }
        if ( *(int *)&this[7].Data2 < 2 )
          break;
LABEL_75:
        if ( v46 )
        {
          hr = StringCchCatW(Src, 0x400u, L" AND ");
          if ( hr < 0 )
            goto LABEL_46;
        }
        hr = StringCchCatW(Src, 0x400u, (const unsigned __int16 *)v28[HIDWORD(a4[3 * v16 + 1])]);
        if ( hr < 0 )
          goto LABEL_46;
        v33 = L"==";
        if ( LODWORD(a4[3 * v16 + 1]) )
          v33 = L"<>";
        hr = StringCchCatW(Src, 0x400u, v33);
        if ( hr < 0 )
          goto LABEL_46;
        v34 = (_DWORD *)a4[3 * v16];
        if ( v34 )
        {
          switch ( LODWORD(a4[3 * v16 + 2]) )
          {
            case 3:
              v35 = (OLECHAR *)L"false";
              if ( *v34 )
                v35 = (OLECHAR *)L"true";
              break;
            case 0x48:
              StringFromGUID2((const GUID *const)a4[3 * v16], sz, 39);
              v35 = sz;
              break;
            case 0x82:
              v35 = (OLECHAR *)a4[3 * v16];
              break;
            default:
              local_unwind_0(v52, &loc_1800462F8);
              return 2148599811LL;
          }
        }
        else
        {
          v35 = L"null";
        }
        hr = StringCchCatW(Src, 0x400u, v35);
        if ( hr < 0 )
          goto LABEL_46;
        v46 = 1;
        v53 = 1;
LABEL_93:
        ++v16;
      }
      v30 = *(_DWORD *)this[3].Data4;
      if ( v30 )
      {
        if ( v30 == 1 )
        {
          v32 = v29 - 17 <= 3;
LABEL_67:
          if ( v32 )
            goto LABEL_93;
          goto LABEL_75;
        }
        if ( v30 != 2 && v30 != 3 )
        {
          v13 = v44;
          goto LABEL_111;
        }
        v31 = v29 - 1;
      }
      else
      {
        v31 = v29 - 8;
      }
      v32 = v31 <= 1;
      goto LABEL_67;
    }
    v13 = v44;
    goto LABEL_113;
  }
  v38 = -1;
  do
    ++v38;
  while ( *((_WORD *)a4 + v38) );
  v39 = CoTaskMemAlloc(saturated_mul(v38 + 1, 2u));
  *(_QWORD *)&this[4].Data1 = v39;
  if ( v39 )
  {
    memcpy_0(v39, a4, 2 * v38 + 2);
    goto LABEL_104;
  }
LABEL_97:
  hr = -2147024882;
LABEL_46:
  v13 = v44;
LABEL_112:
  pItf = v43;
LABEL_113:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( pItf )
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x180045cb0  mov     [rsp+arg_8], rbx
0x180045cb5  mov     [rsp+arg_10], rsi
0x180045cba  push    rdi
0x180045cbb  push    r12
0x180045cbd  push    r13
0x180045cbf  push    r14
0x180045cc1  push    r15
0x180045cc3  sub     rsp, 960h
0x180045cca  mov     rax, cs:__security_cookie
0x180045cd1  xor     rax, rsp
0x180045cd4  mov     [rsp+988h+var_38], rax
0x180045cdc  mov     [rsp+988h+var_8F8], rsp
0x180045ce4  mov     r15, r9
0x180045ce7  mov     rdi, r8
0x180045cea  mov     rsi, rcx
0x180045ced  mov     rcx, [rsp+988h+arg_40]
0x180045cf5  mov     [rsp+988h+var_8E0], rcx
0x180045cfd  xor     r12d, r12d
0x180045d00  mov     [rsp+988h+ppv], r12
0x180045d08  xorps   xmm0, xmm0
0x180045d0b  movups  xmmword ptr [rsp+988h+pServerInfo.dwReserved1], xmm0
0x180045d13  movups  xmmword ptr [rsp+988h+pServerInfo.pAuthInfo], xmm0
0x180045d1b  mov     rax, [rdx]
0x180045d1e  cmp     rax, qword ptr cs:didCOMSERVICES
0x180045d25  jnz     loc_180046578
0x180045d2b  mov     rax, [rdx+8]
0x180045d2f  cmp     rax, qword ptr cs:didCOMSERVICES+8
0x180045d36  jnz     loc_180046578
0x180045d3c  test    r9, r9
0x180045d3f  jz      loc_180046578
0x180045d45  test    rcx, rcx
0x180045d48  jnz     short loc_180045D54
0x180045d4a  mov     eax, 80004003h
0x180045d4f  jmp     loc_18004657D
0x180045d54  mov     [rsp+988h+var_930], r12
0x180045d59  mov     r13, r12
0x180045d5c  mov     [rsp+988h+var_928], r12
0x180045d61  mov     [rsp+988h+var_8E8], r12
0x180045d69  mov     [rsp+988h+var_900], 17h
0x180045d74  mov     [rsp+988h+var_91C], r12d
0x180045d79  movups  xmm0, xmmword ptr [r8]
0x180045d7d  movdqu  xmmword ptr [rsi+60h], xmm0
0x180045d82  mov     edx, [rsp+988h+arg_28]
0x180045d89  lea     eax, [rdx-1]
0x180045d8c  cmp     eax, 1
0x180045d8f  jbe     short loc_180045D9B
0x180045d91  mov     eax, 80110803h
0x180045d96  jmp     loc_18004657D
0x180045d9b  mov     rax, [r8]
0x180045d9e  cmp     rax, cs:tidEVENTCLASSES
0x180045da5  jnz     short loc_180045DE0
0x180045da7  mov     rax, [r8+8]
0x180045dab  cmp     rax, cs:qword_1800621C0
0x180045db2  jnz     short loc_180045DE0
0x180045db4  mov     [rsi+38h], r12d
0x180045db8  lea     r14, ?eventClassMeta@@3PAU__MIDL___MIDL_itf_stable_0000_0000_0001@@A; __MIDL___MIDL_itf_stable_0000_0000_0001 near * eventClassMeta
0x180045dbf  lea     r12, ?eventClassColumns@@3PAPEAGA; ushort * near * eventClassColumns
0x180045dc6  mov     [rsp+988h+var_938], 0Ah
0x180045dce  mov     [rsp+988h+var_910], r12
0x180045dd3  mov     [rsp+988h+var_918], r14
0x180045dd8  xor     r12d, r12d
0x180045ddb  jmp     loc_180045EEB
0x180045de0  mov     rax, [r8]
0x180045de3  cmp     rax, cs:tidSUBSCRIPTIONS
0x180045dea  jnz     short loc_180045DF9
0x180045dec  mov     rax, [r8+8]
0x180045df0  cmp     rax, cs:qword_1800621B0
0x180045df7  jz      short loc_180045E12
0x180045df9  mov     rax, [r8]
0x180045dfc  cmp     rax, cs:tidTRANSIENTSUBSCRIPTIONS
0x180045e03  jnz     short loc_180045E31
0x180045e05  mov     rax, [r8+8]
0x180045e09  cmp     rax, cs:qword_180061388
0x180045e10  jnz     short loc_180045E31
0x180045e12  mov     dword ptr [rsi+38h], 1
0x180045e19  lea     r14, ?subscriptionMeta@@3PAU__MIDL___MIDL_itf_stable_0000_0000_0001@@A; __MIDL___MIDL_itf_stable_0000_0000_0001 near * subscriptionMeta
0x180045e20  lea     r12, ?subscriptionColumns@@3PAPEAGA; ushort * near * subscriptionColumns
0x180045e27  mov     [rsp+988h+var_938], 15h
0x180045e2f  jmp     short loc_180045DCE
0x180045e31  mov     rax, [r8]
0x180045e34  cmp     rax, cs:tidPUBLISHERPROPERTIES
0x180045e3b  jnz     short loc_180045E4A
0x180045e3d  mov     rax, [r8+8]
0x180045e41  cmp     rax, cs:qword_1800621A0
0x180045e48  jz      short loc_180045E63
0x180045e4a  mov     rax, [r8]
0x180045e4d  cmp     rax, cs:tidTRANSIENTPUBLISHERPROPERTIES
0x180045e54  jnz     short loc_180045E87
0x180045e56  mov     rax, [r8+8]
0x180045e5a  cmp     rax, cs:qword_180062170
0x180045e61  jnz     short loc_180045E87
0x180045e63  mov     dword ptr [rsi+38h], 2
0x180045e6a  lea     r14, ?propertyBagMeta@@3PAU__MIDL___MIDL_itf_stable_0000_0000_0001@@A; __MIDL___MIDL_itf_stable_0000_0000_0001 near * propertyBagMeta
0x180045e71  mov     [rsp+988h+var_918], r14
0x180045e76  lea     r12, ?propertyBagColumns@@3PAPEAGA; ushort * near * propertyBagColumns
0x180045e7d  mov     [rsp+988h+var_910], r12
0x180045e82  xor     r12d, r12d
0x180045e85  jmp     short loc_180045EE3
0x180045e87  mov     rax, [r8]
0x180045e8a  cmp     rax, cs:tidSUBSCRIBERPROPERTIES
0x180045e91  jnz     short loc_180045EA0
0x180045e93  mov     rax, [r8+8]
0x180045e97  cmp     rax, cs:qword_180062190
0x180045e9e  jz      short loc_180045EC1
0x180045ea0  mov     rax, [r8]
0x180045ea3  cmp     rax, cs:tidTRANSIENTSUBSCRIBERPROPERTIES
0x180045eaa  jnz     loc_180046528
0x180045eb0  mov     rax, [r8+8]
0x180045eb4  cmp     rax, cs:qword_180062180
0x180045ebb  jnz     loc_180046528
0x180045ec1  mov     dword ptr [rsi+38h], 3
0x180045ec8  lea     rcx, ?propertyBagMeta@@3PAU__MIDL___MIDL_itf_stable_0000_0000_0001@@A; __MIDL___MIDL_itf_stable_0000_0000_0001 near * propertyBagMeta
0x180045ecf  mov     [rsp+988h+var_918], rcx
0x180045ed4  lea     rax, ?propertyBagColumns@@3PAPEAGA; ushort * near * propertyBagColumns
0x180045edb  mov     [rsp+988h+var_910], rax
0x180045ee0  mov     r14, rcx
0x180045ee3  mov     [rsp+988h+var_938], 6
0x180045eeb  or      r13, 0FFFFFFFFFFFFFFFFh
0x180045eef  cmp     edx, 1
0x180045ef2  jnz     loc_1800463E7
0x180045ef8  mov     [rsp+988h+var_920], r12d
0x180045efd  mov     [rsp+988h+Src], r12w
0x180045f06  mov     r14d, r12d
0x180045f09  mov     [rsp+988h+var_920], r12d
0x180045f0e  mov     rdx, cs:qword_180061388
0x180045f15  mov     r8, cs:tidTRANSIENTSUBSCRIPTIONS
0x180045f1c  mov     r9, cs:qword_180062170
0x180045f23  mov     r10, cs:tidTRANSIENTPUBLISHERPROPERTIES
0x180045f2a  mov     r11, cs:qword_180062180
0x180045f31  mov     rbx, cs:tidTRANSIENTSUBSCRIBERPROPERTIES
0x180045f38  cmp     r14d, dword ptr [rsp+988h+arg_20]
0x180045f40  jnb     loc_180046093
0x180045f46  mov     eax, r14d
0x180045f49  lea     r12, [rax+rax*2]
0x180045f4d  cmp     dword ptr [r15+r12*8+0Ch], 0F0000000h
0x180045f56  jbe     loc_180046090
0x180045f5c  cmp     dword ptr [r15+r12*8+0Ch], 0F0000002h
0x180045f65  jnz     loc_180046080
0x180045f6b  xor     eax, eax
0x180045f6d  cmp     [r15+r12*8], rax
0x180045f71  jnz     short loc_180045F92
0x180045f73  lea     rdx, loc_180045F88
0x180045f7a  mov     rcx, [rsp+988h+var_8F8]
0x180045f82  call    _local_unwind_0
0x180045f87  nop
0x180045f88  mov     eax, 80110803h
0x180045f8d  jmp     loc_18004657D
0x180045f92  mov     rcx, [rsi+58h]; void *
0x180045f96  test    rcx, rcx
0x180045f99  jz      short loc_180045FD0
0x180045f9b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180045fa0  xor     ecx, ecx
0x180045fa2  mov     [rsi+58h], rcx
0x180045fa6  mov     rdx, cs:qword_180061388
0x180045fad  mov     r8, cs:tidTRANSIENTSUBSCRIPTIONS
0x180045fb4  mov     r9, cs:qword_180062170
0x180045fbb  mov     r10, cs:tidTRANSIENTPUBLISHERPROPERTIES
0x180045fc2  mov     r11, cs:qword_180062180
0x180045fc9  mov     rbx, cs:tidTRANSIENTSUBSCRIBERPROPERTIES
0x180045fd0  cmp     [rdi], r8
0x180045fd3  jnz     short loc_180045FDB
0x180045fd5  cmp     [rdi+8], rdx
0x180045fd9  jz      short loc_180045FF9
0x180045fdb  cmp     [rdi], r10
0x180045fde  jnz     short loc_180045FE6
0x180045fe0  cmp     [rdi+8], r9
0x180045fe4  jz      short loc_180045FF9
0x180045fe6  cmp     [rdi], rbx
0x180045fe9  jnz     loc_180046080
0x180045fef  cmp     [rdi+8], r11
0x180045ff3  jnz     loc_180046080
0x180045ff9  mov     rax, [r15+r12*8]
0x180045ffd  mov     rbx, r13
0x180046000  inc     rbx
0x180046003  cmp     [rax+rbx*2], cx
0x180046007  jnz     short loc_180046000
0x180046009  inc     rbx
0x18004600c  mov     eax, 2
0x180046011  mul     rbx
0x180046014  cmovb   rax, r13
0x180046018  mov     rcx, rax; cb
0x18004601b  call    cs:__imp_CoTaskMemAlloc
0x180046021  mov     [rsi+58h], rax
0x180046025  mov     r8, [r15+r12*8]; unsigned __int16 *
0x180046029  mov     rdx, rbx; unsigned __int64
0x18004602c  mov     rcx, rax; unsigned __int16 *
0x18004602f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046034  mov     ebx, eax
0x180046036  xor     r12d, r12d
0x180046039  test    eax, eax
0x18004603b  jns     short loc_180046054
0x18004603d  mov     rcx, [rsi+58h]; void *
0x180046041  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180046046  mov     [rsi+58h], r12
0x18004604a  mov     r13, [rsp+988h+var_928]
0x18004604f  jmp     loc_18004652D
0x180046054  mov     rdx, cs:qword_180061388
0x18004605b  mov     r8, cs:tidTRANSIENTSUBSCRIPTIONS
0x180046062  mov     r9, cs:qword_180062170
0x180046069  mov     r10, cs:tidTRANSIENTPUBLISHERPROPERTIES
0x180046070  mov     r11, cs:qword_180062180
0x180046077  mov     rbx, cs:tidTRANSIENTSUBSCRIBERPROPERTIES
0x18004607e  jmp     short loc_180046083
0x180046080  xor     r12d, r12d
0x180046083  inc     r14d
0x180046086  mov     [rsp+988h+var_920], r14d
0x18004608b  jmp     loc_180045F38
0x180046090  xor     r12d, r12d
0x180046093  mov     rax, [rsi+58h]
0x180046097  test    rax, rax
0x18004609a  jz      short loc_1800460CB
0x18004609c  mov     [rsp+988h+pServerInfo.pwszName], rax
0x1800460a4  mov     [rsp+988h+pServerInfo.pAuthInfo], r12
0x1800460ac  mov     [rsp+988h+pServerInfo.dwReserved1], r12d
0x1800460b4  mov     [rsp+988h+pServerInfo.dwReserved2], r12d
0x1800460bc  lea     rcx, [rsp+988h+pServerInfo]
0x1800460c4  mov     eax, 10h
0x1800460c9  jmp     short loc_1800460DA
0x1800460cb  mov     rcx, [rsp+988h+var_8E8]
0x1800460d3  mov     eax, [rsp+988h+var_900]
0x1800460da  xorps   xmm0, xmm0
0x1800460dd  movups  xmmword ptr [rsp+988h+var_8D8.pIID], xmm0
0x1800460e5  movups  xmmword ptr [rsp+988h+var_8D8.hr], xmm0
0x1800460ed  movups  [rsp+988h+var_8B8], xmm0
0x1800460f5  lea     rdx, IID_IEventSystem
0x1800460fc  mov     [rsp+988h+var_8D8.pIID], rdx
0x180046104  lea     rdx, IID_IEventSystem2
0x18004610b  mov     [rsp+988h+var_8C0], rdx
0x180046113  lea     rdx, [rsp+988h+var_8D8]
0x18004611b  mov     [rsp+988h+pResults], rdx; pResults
0x180046120  mov     [rsp+988h+dwCount], 2; dwCount
0x180046128  mov     r9, rcx; pServerInfo
0x18004612b  mov     r8d, eax; dwClsCtx
0x18004612e  xor     edx, edx; punkOuter
0x180046130  lea     rcx, CLSID_CEventSystem; Clsid
0x180046137  call    cs:__imp_CoCreateInstanceEx
0x18004613d  mov     ebx, eax
0x18004613f  test    eax, eax
0x180046141  js      loc_18004604A
0x180046147  cmp     [rsp+988h+var_8D8.hr], r12d
0x18004614f  jl      loc_1800463D3
0x180046155  mov     rdi, [rsp+988h+var_8D8.pItf]
0x18004615d  mov     [rsp+988h+var_930], rdi
0x180046162  mov     ebx, dword ptr [rsp+988h+var_8B8+8]
0x180046169  test    ebx, ebx
0x18004616b  jns     short loc_180046188
0x18004616d  cmp     ebx, 80004002h
0x180046173  jnz     short loc_18004617E
0x180046175  mov     dword ptr [rsi+74h], 1
0x18004617c  jmp     short loc_1800461AF
0x18004617e  mov     r13, [rsp+988h+var_928]
0x180046183  jmp     loc_180046532
0x180046188  mov     rcx, qword ptr [rsp+988h+var_8B8]
0x180046190  mov     [rsp+988h+var_928], rcx
0x180046195  mov     rax, [rcx]
0x180046198  lea     rdx, [rsi+74h]
0x18004619c  mov     rax, [rax+68h]
0x1800461a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461a5  mov     ebx, eax
0x1800461a7  test    eax, eax
0x1800461a9  js      loc_18004604A
0x1800461af  mov     r12, [rsp+988h+var_910]
0x1800461b4  mov     [rsp+988h+var_8FC], r14d
0x1800461bc  cmp     r14d, dword ptr [rsp+988h+arg_20]
0x1800461c4  jnb     loc_180046370
0x1800461ca  mov     eax, r14d
0x1800461cd  lea     rdi, [rax+rax*2]
0x1800461d1  mov     eax, [r15+rdi*8+0Ch]
0x1800461d6  cmp     eax, [rsp+988h+var_938]
0x1800461da  jbe     short loc_1800461FB
0x1800461dc  lea     rdx, loc_1800461F1
0x1800461e3  mov     rcx, [rsp+988h+var_8F8]
0x1800461eb  call    _local_unwind_0
0x1800461f0  nop
0x1800461f1  mov     eax, 80110803h
0x1800461f6  jmp     loc_18004657D
0x1800461fb  cmp     dword ptr [rsi+74h], 2
0x1800461ff  jge     short loc_18004623A
0x180046201  mov     ecx, [rsi+38h]
0x180046204  test    ecx, ecx
0x180046206  jnz     short loc_180046215
0x180046208  add     eax, 0FFFFFFF8h
0x18004620b  cmp     eax, 1
0x18004620e  ja      short loc_18004623A
0x180046210  jmp     loc_180046368
0x180046215  cmp     ecx, 1
0x180046218  jnz     short loc_180046222
0x18004621a  add     eax, 0FFFFFFEFh
0x18004621d  cmp     eax, 3
0x180046220  jmp     short loc_18004620E
0x180046222  cmp     ecx, 2
0x180046225  jnz     short loc_18004622B
0x180046227  dec     eax
0x180046229  jmp     short loc_18004620B
0x18004622b  cmp     ecx, 3
0x18004622e  jz      short loc_180046227
0x180046230  mov     r13, [rsp+988h+var_928]
0x180046235  jmp     loc_180046528
0x18004623a  cmp     [rsp+988h+var_91C], 0
0x18004623f  jz      short loc_180046264
  ... truncated ...
```
