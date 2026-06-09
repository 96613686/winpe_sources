# CRecordset::GetAttributes(ulong *)

- ea: `0x18002c440`
- end: `0x18002cd7b`
- name: `?GetAttributes@CRecordset@@QEAAJPEAK@Z`
- size: `2363`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x18002adc0`
- `0x1800b4f50`
- `0x1800b5efc`

## callees

- `0x18002c440`
- `0x18004f5dc`
- `0x1800504b0`
- `0x180051e14`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18002c4d6`
- `KERNEL32!TlsSetValue` at `0x18002c856`
- `KERNEL32!TlsSetValue` at `0x18002c4d6`
- `KERNEL32!TlsSetValue` at `0x18002c856`
- `KERNEL32!TlsGetValue` at `0x18002c48c`
- `KERNEL32!TlsGetValue` at `0x18002c48c`
- `ole32!CoTaskMemFree` at `0x18002cd3b`
- `ole32!CoTaskMemFree` at `0x18002cd57`
- `ole32!CoTaskMemFree` at `0x18002cd3b`
- `ole32!CoTaskMemFree` at `0x18002cd57`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002c921`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002c921`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::GetAttributes(CRecordset *this, unsigned int *a2)
{
  char *v4; // rcx
  _DWORD *Value; // rax
  __int64 v6; // rdx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // esi
  int v9; // esi
  _QWORD *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  int v15; // ecx
  _DWORD *v17; // rax
  IErrorInfo *v18; // rdx
  int v20; // eax
  int v21; // r14d
  unsigned int BidObjectID; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  __int64 v29; // r8
  unsigned int i; // esi
  __int64 v31; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *TlsValue; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h]
  __int64 v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+78h] [rbp-88h]
  __int16 v42; // [rsp+7Ch] [rbp-84h]
  char v43; // [rsp+7Eh] [rbp-82h]
  char *v44; // [rsp+80h] [rbp-80h]
  int v45; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+8Ch] [rbp-74h]
  _DWORD v47[20]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v48; // [rsp+E0h] [rbp-20h] BYREF
  int v49; // [rsp+E8h] [rbp-18h]
  GUID v50; // [rsp+ECh] [rbp-14h]
  int *v51; // [rsp+100h] [rbp+0h]
  int v52; // [rsp+108h] [rbp+8h]
  GUID v53; // [rsp+10Ch] [rbp+Ch]

  v4 = (char *)this + 32;
  if ( !this )
    v4 = 0;
  v44 = v4;
  v46 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v45 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v39 = 1;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  if ( *((_DWORD *)this + 174) == -268435456 )
  {
    v6 = *((_QWORD *)this + 141);
    if ( v6 )
    {
      *((_DWORD *)this + 174) = 0;
      v35 = 0;
      pv = 0;
      v33 = 0;
      v34 = 0;
      if ( (*((_BYTE *)this + 1136) & 1) != 0 )
      {
        if ( (_DWORD)v6 )
        {
          v34 = 0;
          v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)g_pStaticGlobals + 10) + 40LL))(
                  *((_QWORD *)g_pStaticGlobals + 10),
                  v6,
                  &IID_IRowset,
                  &v34);
          if ( v21 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
              {
                bidTraceW(
                  off_18012A208[0],
                  7089161,
                  L"<CRecordset::GetAttributes|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  (unsigned int)v21,
                  6923);
              }
              else
              {
                BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                bidTraceW(
                  off_18012A208[0],
                  7089161,
                  L"<CRecordset::GetAttributes|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  BidObjectID,
                  v21,
                  6923);
              }
            }
            goto LABEL_45;
          }
          v7 = v34;
LABEL_10:
          v8 = (**v7)(v7, &IID_IRowsetInfo, &v35);
          if ( v8 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
              {
                bidTraceW(
                  off_18012A208[0],
                  7092233,
                  L"<CRecordset::GetAttributes|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  (unsigned int)v8,
                  6926);
              }
              else
              {
                v23 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                bidTraceW(
                  off_18012A208[0],
                  7092233,
                  L"<CRecordset::GetAttributes|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v23,
                  v8,
                  6926);
              }
            }
          }
          else
          {
            v47[0] = 88;
            v47[1] = 87;
            v47[2] = 19;
            v47[3] = 21;
            v47[4] = 117;
            v47[5] = 130;
            v47[6] = 133;
            v47[7] = 134;
            v47[8] = 132;
            v47[9] = 124;
            v47[10] = 15;
            v47[11] = 204;
            v47[12] = 249;
            v47[13] = 236;
            v47[14] = 159;
            v47[15] = 279;
            v47[16] = 102;
            v36 = 7;
            v50 = DBPROPSET_ROWSET;
            v49 = 17;
            v48 = v47;
            v53 = DBPROPSET_PROVIDERROWSET;
            v52 = 1;
            v51 = &v36;
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, _DWORD **, unsigned int *, LPVOID *))(*(_QWORD *)v35 + 24LL))(
                   v35,
                   2,
                   &v48,
                   &v33,
                   &pv);
            if ( v9 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
                {
                  LODWORD(v31) = 6957;
                  bidTraceW(
                    off_18012A208[0],
                    7123977,
                    L"<CRecordset::GetAttributes|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                    (unsigned int)v9,
                    v31);
                }
                else
                {
                  v24 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                  LODWORD(v31) = v9;
                  bidTraceW(
                    off_18012A208[0],
                    7123977,
                    L"<CRecordset::GetAttributes|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                    v24,
                    v31,
                    6957);
                }
              }
            }
            else if ( v33 )
            {
              v10 = pv;
              if ( *((_DWORD *)pv + 2) )
              {
                if ( !*(_DWORD *)(*(_QWORD *)pv + 224LL) && *(_WORD *)(*(_QWORD *)pv + 272LL) == 0xFFFF )
                {
                  *((_DWORD *)this + 174) |= 0xC0u;
                  v20 = *((_DWORD *)this + 174);
                  if ( !*(_DWORD *)(*v10 + 8LL) && *(_WORD *)(*v10 + 56LL) == 0xFFFF )
                  {
                    v20 |= 0x20u;
                    *((_DWORD *)this + 174) = v20;
                  }
                  if ( !*(_DWORD *)(*v10 + 80LL) && *(_WORD *)(*v10 + 128LL) == 0xFFFF )
                    *((_DWORD *)this + 174) = v20 | 0x10;
                }
                if ( !*(_DWORD *)(*v10 + 152LL) )
                  *((_DWORD *)this + 174) |= *(_WORD *)(*v10 + 200LL) != 0 ? 0x100 : 0;
                v11 = *((unsigned int *)this + 174);
                if ( !*(_DWORD *)(*v10 + 224LL) )
                  *((_DWORD *)this + 174) = v11 | (*(_WORD *)(*v10 + 272LL) != 0 ? 0x200 : 0);
                if ( !*(_DWORD *)(*v10 + 296LL) )
                {
                  v25 = CRsetOptionalInterface<IRowsetChange,&_GUID const IID_IRowsetChange>::BoolCheck(
                          (char *)this + 408,
                          v10,
                          v11);
                  v10 = pv;
                  if ( v25 )
                  {
                    v26 = *(_DWORD *)(*(_QWORD *)pv + 344LL);
                    if ( (v26 & 1) != 0 )
                      *((_DWORD *)this + 174) |= 0x1008000u;
                    v27 = *((_DWORD *)this + 174);
                    if ( (v26 & 2) != 0 )
                    {
                      v27 |= 0x1000800u;
                      *((_DWORD *)this + 174) = v27;
                    }
                    if ( (v26 & 4) != 0 )
                      *((_DWORD *)this + 174) = v27 | 0x1000400;
                  }
                }
                if ( !*(_DWORD *)(*v10 + 368LL) )
                  *((_DWORD *)this + 174) |= *(_WORD *)(*v10 + 416LL) != 0 ? 0x2000 : 0;
                v12 = *((unsigned int *)this + 174);
                if ( !*(_DWORD *)(*v10 + 440LL) )
                  *((_DWORD *)this + 174) = v12 | (*(_WORD *)(*v10 + 488LL) != 0 ? 0x4000 : 0);
                if ( !*(_DWORD *)(*v10 + 512LL) )
                {
                  v28 = CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::BoolCheck(
                          (char *)this + 432,
                          v10,
                          v12);
                  v10 = pv;
                  if ( v28 )
                    *((_DWORD *)this + 174) |= *(_WORD *)(*(_QWORD *)pv + 560LL) != 0 ? 0x10000 : 0;
                }
                v13 = *v10;
                if ( !*(_DWORD *)(*v10 + 584LL) && *(_WORD *)(v13 + 632)
                  || !*(_DWORD *)(v13 + 872) && *(_WORD *)(v13 + 920) )
                {
                  *((_DWORD *)this + 174) |= 0x20000u;
                }
                if ( !*(_DWORD *)(*v10 + 656LL) )
                  *((_DWORD *)this + 174) |= *(_WORD *)(*v10 + 704LL) != 0 ? 0x40000 : 0;
                v14 = *((_DWORD *)this + 174);
                if ( !*(_DWORD *)(*v10 + 728LL) )
                  *((_DWORD *)this + 176) = *(__int16 *)(*v10 + 776LL);
                if ( (*(_DWORD *)(*v10 + 944LL) || *(_DWORD *)(*v10 + 992LL) != 2)
                  && (v33 <= 1 || (v29 = v10[4], *(_DWORD *)(v29 + 8)) || (*(_BYTE *)(v29 + 56) & 4) == 0) )
                {
                  v15 = v14;
                }
                else
                {
                  v15 = v14 | 0x8000000;
                  *((_DWORD *)this + 174) = v14 | 0x8000000;
                }
                if ( !*(_DWORD *)(*v10 + 1016LL) && *(_WORD *)(*v10 + 1064LL) )
                {
                  v15 |= 0x400000u;
                  *((_DWORD *)this + 174) = v15;
                }
                if ( !*(_DWORD *)(*v10 + 1088LL) && *(_WORD *)(*v10 + 1136LL) )
                {
                  v15 |= 0x800000u;
                  *((_DWORD *)this + 174) = v15;
                }
                if ( !*(_DWORD *)(*v10 + 1160LL) && *(_WORD *)(*v10 + 1208LL) )
                  *((_DWORD *)this + 174) = v15 | 0x2000000;
                if ( (*((_BYTE *)this + 520) & 4) != 0 )
                {
                  if ( *((_QWORD *)this + 64) )
                  {
LABEL_61:
                    *((_DWORD *)this + 174) |= 0x80000u;
                    goto LABEL_46;
                  }
                }
                else
                {
                  v37 = 0;
                  if ( (int)CRsetOptionalInterface<IRowsetFind,&_GUID const IID_IRowsetFind>::GetInterface(
                              (char *)this + 504,
                              &v37) >= 0 )
                  {
                    if ( v37 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                    v10 = pv;
                    goto LABEL_61;
                  }
                  v10 = pv;
                }
                if ( *(_DWORD *)(*v10 + 800LL) || !*(_WORD *)(*v10 + 848LL) )
                  goto LABEL_46;
                goto LABEL_61;
              }
LABEL_46:
              if ( v35 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                v35 = 0;
                v10 = pv;
              }
              if ( v10 )
              {
                for ( i = 0; i < v33; v10 = pv )
                  CoTaskMemFree((LPVOID)v10[4 * i++]);
                CoTaskMemFree(v10);
              }
              if ( v34 )
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v34)[2])(v34);
              goto LABEL_51;
            }
          }
LABEL_45:
          v10 = pv;
          goto LABEL_46;
        }
        v7 = 0;
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 141);
      }
      v34 = v7;
      goto LABEL_10;
    }
  }
LABEL_51:
  *a2 = *((_DWORD *)this + 174);
  if ( TlsValue[2]-- == 1 )
  {
    v17 = TlsValue;
    v18 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v18 )
    {
      SetErrorInfo(0, v18);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v17 = TlsValue;
    }
    if ( *((_BYTE *)v17 + 30) )
    {
      *((_QWORD *)v17 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002c440  mov     [rsp-8+arg_10], rbx
0x18002c445  push    rbp
0x18002c446  push    rsi
0x18002c447  push    rdi
0x18002c448  push    r14
0x18002c44a  push    r15
0x18002c44c  lea     rbp, [rsp-30h]
0x18002c451  sub     rsp, 130h
0x18002c458  mov     rax, cs:__security_cookie
0x18002c45f  xor     rax, rsp
0x18002c462  mov     [rbp+50h+var_30], rax
0x18002c466  mov     rdi, rdx
0x18002c469  mov     rbx, rcx
0x18002c46c  add     rcx, 20h ; ' '
0x18002c470  xor     r15d, r15d
0x18002c473  test    rbx, rbx
0x18002c476  cmovz   rcx, r15
0x18002c47a  mov     [rbp+50h+var_D0], rcx
0x18002c47e  mov     [rbp+50h+var_C4], r15d
0x18002c482  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002c489  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002c48c  call    cs:__imp_TlsGetValue
0x18002c493  nop     dword ptr [rax+rax+00h]
0x18002c498  mov     [rsp+150h+TlsValue], rax
0x18002c49d  mov     [rbp+50h+var_C8], r15d
0x18002c4a1  test    rax, rax
0x18002c4a4  jnz     loc_18002C889
0x18002c4aa  mov     [rsp+150h+var_E8], 1
0x18002c4b2  mov     [rsp+150h+var_E0], r15
0x18002c4b7  mov     [rsp+150h+var_D8], r15d
0x18002c4bc  mov     [rsp+150h+var_D4], r15w
0x18002c4c2  mov     [rsp+150h+var_D2], r15b
0x18002c4c7  lea     rdx, [rsp+150h+TlsValue]; lpTlsValue
0x18002c4cc  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002c4d3  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002c4d6  call    cs:__imp_TlsSetValue
0x18002c4dd  nop     dword ptr [rax+rax+00h]
0x18002c4e2  lea     rax, [rsp+150h+TlsValue]
0x18002c4e7  mov     [rsp+150h+TlsValue], rax
0x18002c4ec  cmp     dword ptr [rbx+2B8h], 0F0000000h
0x18002c4f6  jnz     loc_18002C81B
0x18002c4fc  mov     rdx, [rbx+468h]
0x18002c503  test    rdx, rdx
0x18002c506  jz      loc_18002C81B
0x18002c50c  mov     [rbx+2B8h], r15d
0x18002c513  mov     [rsp+150h+var_108], r15
0x18002c518  mov     [rsp+150h+pv], r15
0x18002c51d  mov     [rsp+150h+var_118], r15d
0x18002c522  mov     [rsp+150h+var_110], r15
0x18002c527  test    byte ptr [rbx+470h], 1
0x18002c52e  jnz     loc_18002C7CB
0x18002c534  mov     rax, [rdx]
0x18002c537  mov     rcx, rdx
0x18002c53a  mov     rax, [rax+8]
0x18002c53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c543  mov     rcx, [rbx+468h]
0x18002c54a  mov     [rsp+150h+var_110], rcx
0x18002c54f  mov     rax, [rcx]
0x18002c552  lea     r8, [rsp+150h+var_108]
0x18002c557  lea     rdx, IID_IRowsetInfo
0x18002c55e  mov     rax, [rax]
0x18002c561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c566  mov     esi, eax
0x18002c568  test    eax, eax
0x18002c56a  js      loc_18002C9FB
0x18002c570  mov     [rbp+50h+var_C0], 58h ; 'X'
0x18002c577  mov     [rbp+50h+var_BC], 57h ; 'W'
0x18002c57e  mov     [rbp+50h+var_B8], 13h
0x18002c585  mov     [rbp+50h+var_B4], 15h
0x18002c58c  mov     [rbp+50h+var_B0], 75h ; 'u'
0x18002c593  mov     [rbp+50h+var_AC], 82h
0x18002c59a  mov     [rbp+50h+var_A8], 85h
0x18002c5a1  mov     [rbp+50h+var_A4], 86h
0x18002c5a8  mov     [rbp+50h+var_A0], 84h
0x18002c5af  mov     [rbp+50h+var_9C], 7Ch ; '|'
0x18002c5b6  mov     [rbp+50h+var_98], 0Fh
0x18002c5bd  mov     [rbp+50h+var_94], 0CCh
0x18002c5c4  mov     [rbp+50h+var_90], 0F9h
0x18002c5cb  mov     [rbp+50h+var_8C], 0ECh
0x18002c5d2  mov     [rbp+50h+var_88], 9Fh
0x18002c5d9  mov     [rbp+50h+var_84], 117h
0x18002c5e0  mov     [rbp+50h+var_80], 66h ; 'f'
0x18002c5e7  mov     [rsp+150h+var_100], 7
0x18002c5ef  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x18002c5f6  movups  [rbp+50h+var_64], xmm0
0x18002c5fa  mov     [rbp+50h+var_68], 11h
0x18002c601  lea     rax, [rbp+50h+var_C0]
0x18002c605  mov     [rbp+50h+var_70], rax
0x18002c609  movups  xmm0, xmmword ptr cs:?DBPROPSET_PROVIDERROWSET@@3U_GUID@@B.Data1; _GUID const DBPROPSET_PROVIDERROWSET ...
0x18002c610  movups  [rbp+50h+var_44], xmm0
0x18002c614  mov     [rbp+50h+var_48], 1
0x18002c61b  lea     rax, [rsp+150h+var_100]
0x18002c620  mov     [rbp+50h+var_50], rax
0x18002c624  mov     rcx, [rsp+150h+var_108]
0x18002c629  mov     rax, [rcx]
0x18002c62c  lea     rdx, [rsp+150h+pv]
0x18002c631  mov     [rsp+150h+var_130], rdx
0x18002c636  lea     r9, [rsp+150h+var_118]
0x18002c63b  lea     r8, [rbp+50h+var_70]
0x18002c63f  mov     edx, 2
0x18002c644  mov     rax, [rax+18h]
0x18002c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c64d  mov     esi, eax
0x18002c64f  test    eax, eax
0x18002c651  js      loc_18002CA71
0x18002c657  cmp     [rsp+150h+var_118], 0
0x18002c65c  jz      loc_18002C7E8
0x18002c662  mov     rdx, [rsp+150h+pv]
0x18002c667  cmp     dword ptr [rdx+8], 0
0x18002c66b  jz      loc_18002C7ED
0x18002c671  mov     rax, [rdx]
0x18002c674  cmp     dword ptr [rax+0E0h], 0
0x18002c67b  jz      loc_18002C8C5
0x18002c681  mov     rax, [rdx]
0x18002c684  cmp     dword ptr [rax+98h], 0
0x18002c68b  jz      loc_18002CB03
0x18002c691  mov     r8d, [rbx+2B8h]
0x18002c698  mov     rax, [rdx]
0x18002c69b  cmp     dword ptr [rax+0E0h], 0
0x18002c6a2  jz      loc_18002CB20
0x18002c6a8  mov     rax, [rdx]
0x18002c6ab  cmp     dword ptr [rax+128h], 0
0x18002c6b2  jz      loc_18002CB40
0x18002c6b8  mov     rax, [rdx]
0x18002c6bb  cmp     dword ptr [rax+170h], 0
0x18002c6c2  jz      loc_18002CBA0
0x18002c6c8  mov     r8d, [rbx+2B8h]
0x18002c6cf  mov     rax, [rdx]
0x18002c6d2  cmp     dword ptr [rax+1B8h], 0
0x18002c6d9  jz      loc_18002CBBD
0x18002c6df  mov     rax, [rdx]
0x18002c6e2  cmp     dword ptr [rax+200h], 0
0x18002c6e9  jz      loc_18002CBDD
0x18002c6ef  mov     rax, [rdx]
0x18002c6f2  cmp     dword ptr [rax+248h], 0
0x18002c6f9  jz      loc_18002CC15
0x18002c6ff  cmp     dword ptr [rax+368h], 0
0x18002c706  jz      loc_18002CC24
0x18002c70c  mov     rax, [rdx]
0x18002c70f  cmp     dword ptr [rax+290h], 0
0x18002c716  jz      loc_18002CC41
0x18002c71c  mov     eax, [rbx+2B8h]
0x18002c722  mov     ecx, eax
0x18002c724  mov     r8, [rdx]
0x18002c727  cmp     dword ptr [r8+2D8h], 0
0x18002c72f  jz      loc_18002CC5E
0x18002c735  mov     r8, [rdx]
0x18002c738  cmp     dword ptr [r8+3B0h], 0
0x18002c740  jz      loc_18002CC73
0x18002c746  cmp     [rsp+150h+var_118], 1
0x18002c74b  ja      loc_18002CC82
0x18002c751  mov     ecx, eax
0x18002c753  mov     rax, [rdx]
0x18002c756  cmp     dword ptr [rax+3F8h], 0
0x18002c75d  jz      loc_18002CCAB
0x18002c763  mov     rax, [rdx]
0x18002c766  cmp     dword ptr [rax+440h], 0
0x18002c76d  jz      loc_18002CCC8
0x18002c773  mov     rax, [rdx]
0x18002c776  cmp     dword ptr [rax+488h], 0
0x18002c77d  jz      loc_18002CCE5
0x18002c783  lea     rcx, [rbx+1F8h]
0x18002c78a  test    byte ptr [rcx+10h], 4
0x18002c78e  jnz     loc_18002C891
0x18002c794  mov     [rsp+150h+var_F8], r15
0x18002c799  lea     rdx, [rsp+150h+var_F8]
0x18002c79e  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetFind@@$1?IID_IRowsetFind@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetFind@@@Z; CRsetOptionalInterface<IRowsetFind,&_GUID const IID_IRowsetFind>::GetInterface(IRowsetFind * *)
0x18002c7a3  test    eax, eax
0x18002c7a5  js      loc_18002CD02
0x18002c7ab  mov     rcx, [rsp+150h+var_F8]
0x18002c7b0  test    rcx, rcx
0x18002c7b3  jz      short loc_18002C7C1
0x18002c7b5  mov     rax, [rcx]
0x18002c7b8  mov     rax, [rax+10h]
0x18002c7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7c1  mov     rdx, [rsp+150h+pv]
0x18002c7c6  jmp     loc_18002C8B6
0x18002c7cb  test    edx, edx
0x18002c7cd  jnz     loc_18002C94C
0x18002c7d3  mov     rcx, r15
0x18002c7d6  jmp     loc_18002C54A
0x18002c7db  test    byte ptr cs:_bidGblFlags, 2
0x18002c7e2  jnz     loc_18002C989
0x18002c7e8  mov     rdx, [rsp+150h+pv]
0x18002c7ed  mov     rcx, [rsp+150h+var_108]
0x18002c7f2  test    rcx, rcx
0x18002c7f5  jnz     loc_18002CD0C
0x18002c7fb  test    rdx, rdx
0x18002c7fe  jnz     loc_18002CD27
0x18002c804  mov     rcx, [rsp+150h+var_110]
0x18002c809  test    rcx, rcx
0x18002c80c  jz      short loc_18002C81B
0x18002c80e  mov     rax, [rcx]
0x18002c811  mov     rax, [rax+10h]
0x18002c815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c81a  nop
0x18002c81b  mov     eax, [rbx+2B8h]
0x18002c821  mov     [rdi], eax
0x18002c823  mov     rax, [rsp+150h+TlsValue]
0x18002c828  add     dword ptr [rax+8], 0FFFFFFFFh
0x18002c82c  jnz     short loc_18002C863
0x18002c82e  mov     rax, [rsp+150h+TlsValue]
0x18002c833  mov     rdx, [rax+10h]; perrinfo
0x18002c837  test    rdx, rdx
0x18002c83a  jnz     loc_18002C91F
0x18002c840  cmp     byte ptr [rax+1Eh], 0
0x18002c844  jnz     loc_18002CD68
0x18002c84a  xor     edx, edx; lpTlsValue
0x18002c84c  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002c853  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002c856  call    cs:__imp_TlsSetValue
0x18002c85d  nop     dword ptr [rax+rax+00h]
0x18002c862  nop
0x18002c863  xor     eax, eax
0x18002c865  mov     rcx, [rbp+50h+var_30]
0x18002c869  xor     rcx, rsp; StackCookie
0x18002c86c  call    __security_check_cookie
0x18002c871  mov     rbx, [rsp+150h+arg_10]
0x18002c879  add     rsp, 130h
0x18002c880  pop     r15
0x18002c882  pop     r14
0x18002c884  pop     rdi
0x18002c885  pop     rsi
0x18002c886  pop     rbp
0x18002c887  retn
0x18002c889  inc     dword ptr [rax+8]
0x18002c88c  jmp     loc_18002C4EC
0x18002c891  cmp     qword ptr [rcx+8], 0
0x18002c896  jnz     short loc_18002C8B6
0x18002c898  mov     rax, [rdx]
0x18002c89b  cmp     dword ptr [rax+320h], 0
0x18002c8a2  jnz     loc_18002C7ED
0x18002c8a8  cmp     word ptr [rax+350h], 0
0x18002c8b0  jz      loc_18002C7ED
0x18002c8b6  or      dword ptr [rbx+2B8h], 80000h
0x18002c8c0  jmp     loc_18002C7ED
0x18002c8c5  mov     r8d, 0FFFFFFFFh
0x18002c8cb  cmp     r8w, [rax+110h]
0x18002c8d3  jnz     loc_18002C681
0x18002c8d9  or      dword ptr [rbx+2B8h], 0C0h
0x18002c8e3  mov     eax, [rbx+2B8h]
0x18002c8e9  mov     rcx, [rdx]
0x18002c8ec  cmp     dword ptr [rcx+8], 0
0x18002c8f0  jz      loc_18002CAEA
0x18002c8f6  mov     rcx, [rdx]
0x18002c8f9  cmp     dword ptr [rcx+50h], 0
0x18002c8fd  jnz     loc_18002C681
0x18002c903  cmp     r8w, [rcx+80h]
0x18002c90b  jnz     loc_18002C681
0x18002c911  or      eax, 10h
0x18002c914  mov     [rbx+2B8h], eax
0x18002c91a  jmp     loc_18002C681
0x18002c91f  xor     ecx, ecx; dwReserved
0x18002c921  call    cs:__imp_SetErrorInfo
0x18002c928  nop     dword ptr [rax+rax+00h]
0x18002c92d  mov     rax, [rsp+150h+TlsValue]
0x18002c932  mov     rcx, [rax+10h]
0x18002c936  mov     rax, [rcx]
0x18002c939  mov     rax, [rax+10h]
0x18002c93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c942  mov     rax, [rsp+150h+TlsValue]
0x18002c947  jmp     loc_18002C840
0x18002c94c  mov     [rsp+150h+var_110], r15
0x18002c951  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002c958  mov     rcx, [rax+50h]
0x18002c95c  mov     rax, [rcx]
0x18002c95f  lea     r9, [rsp+150h+var_110]
0x18002c964  lea     r8, IID_IRowset
0x18002c96b  mov     rax, [rax+28h]
0x18002c96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c974  mov     r14d, eax
0x18002c977  test    eax, eax
0x18002c979  js      loc_18002C7DB
0x18002c97f  mov     rcx, [rsp+150h+var_110]
0x18002c984  jmp     loc_18002C54F
0x18002c989  lea     rcx, [rbx+618h]; this
0x18002c990  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002c995  cmp     eax, 0FFFFFFFFh
0x18002c998  jz      short loc_18002C9D3
0x18002c99a  lea     rcx, [rbx+618h]; this
0x18002c9a1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002c9a6  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002c9ad  mov     [rsp+150h+var_128], 1B0Bh
0x18002c9b5  mov     dword ptr [rsp+150h+var_130], r14d
0x18002c9ba  mov     r9d, eax
0x18002c9bd  lea     r8, aCrecordsetGeta; "<CRecordset::GetAttributes|ADO|ERR> %u#"...
0x18002c9c4  mov     edx, 6C2C09h
0x18002c9c9  call    _bidTraceW
0x18002c9ce  jmp     loc_18002C7E8
0x18002c9d3  mov     dword ptr [rsp+150h+var_130], 1B0Bh
0x18002c9db  mov     r9d, r14d
0x18002c9de  lea     r8, aCrecordsetGeta_0; "<CRecordset::GetAttributes|ADO|ERR> 0x%"...
0x18002c9e5  mov     edx, 6C2C09h
0x18002c9ea  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002c9f1  call    _bidTraceW
0x18002c9f6  jmp     loc_18002C7E8
0x18002c9fb  test    byte ptr cs:_bidGblFlags, 2
0x18002ca02  jz      loc_18002C7E8
0x18002ca08  lea     rcx, [rbx+618h]; this
0x18002ca0f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
  ... truncated ...
```
