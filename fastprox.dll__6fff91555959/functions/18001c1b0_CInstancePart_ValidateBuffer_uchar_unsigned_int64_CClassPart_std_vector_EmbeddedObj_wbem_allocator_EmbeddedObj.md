# CInstancePart::ValidateBuffer(uchar *,unsigned __int64,CClassPart &,std::vector<EmbeddedObj,wbem_allocator<EmbeddedObj>> &)

- ea: `0x18001c1b0`
- end: `0x18001caf4`
- name: `?ValidateBuffer@CInstancePart@@SA_KPEAE_KAEAVCClassPart@@AEAV?$vector@UEmbeddedObj@@V?$wbem_allocator@UEmbeddedObj@@@@@std@@@Z`
- size: `2372`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64 pExceptionObject, int **, __int64)`
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180018f50`
- `0x18001a6d0`
- `0x18001ac00`
- `0x18007ab50`

## callees

- `0x180011e40`
- `0x180012a50`
- `0x180013ac0`
- `0x180017de0`
- `0x18001c1b0`
- `0x18001cb00`
- `0x18001d3b0`
- `0x18001d8d0`
- `0x180035b08`
- `0x1800564c0`
- `0x18006fa4c`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001c570`
- `wbemcomn!GetMemLogObject` at `0x18001c6d9`
- `wbemcomn!GetMemLogObject` at `0x18001c742`
- `wbemcomn!GetMemLogObject` at `0x18001c7ab`
- `wbemcomn!GetMemLogObject` at `0x18001c814`
- `wbemcomn!GetMemLogObject` at `0x18001c87d`
- `wbemcomn!GetMemLogObject` at `0x18001c8e6`
- `wbemcomn!GetMemLogObject` at `0x18001c94f`
- `wbemcomn!GetMemLogObject` at `0x18001c9cc`
- `wbemcomn!GetMemLogObject` at `0x18001ca2a`
- `wbemcomn!GetMemLogObject` at `0x18001ca93`
- `wbemcomn!GetMemLogObject` at `0x18001c570`
- `wbemcomn!GetMemLogObject` at `0x18001c6d9`
- `wbemcomn!GetMemLogObject` at `0x18001c742`
- `wbemcomn!GetMemLogObject` at `0x18001c7ab`
- `wbemcomn!GetMemLogObject` at `0x18001c814`
- `wbemcomn!GetMemLogObject` at `0x18001c87d`
- `wbemcomn!GetMemLogObject` at `0x18001c8e6`
- `wbemcomn!GetMemLogObject` at `0x18001c94f`
- `wbemcomn!GetMemLogObject` at `0x18001c9cc`
- `wbemcomn!GetMemLogObject` at `0x18001ca2a`
- `wbemcomn!GetMemLogObject` at `0x18001ca93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c57e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c6e7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c750`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c7b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c822`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c88b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c8f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c95d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c9da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ca38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001caa1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c57e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c6e7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c750`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c7b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c822`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c88b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c8f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c95d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c9da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ca38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001caa1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c517`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c5f5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c517`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c5f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c5e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CInstancePart::ValidateBuffer(
        unsigned __int8 *a1,
        unsigned __int64 pExceptionObject,
        int **a3,
        __int64 a4)
{
  unsigned __int64 v5; // rsi
  unsigned __int8 *v6; // r14
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rdi
  unsigned __int8 *v13; // r13
  __int64 v14; // r12
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // r9
  int *v17; // r8
  int v18; // ecx
  unsigned __int8 *v19; // r10
  unsigned __int8 *v20; // rax
  unsigned __int8 *v21; // rcx
  _DWORD *v22; // r11
  int v23; // ecx
  unsigned __int64 v24; // rcx
  __int64 v25; // rbx
  BSTR *v26; // rax
  CMemoryLog *v28; // rax
  int i; // edi
  int v30; // eax
  int v31; // esi
  int v32; // r14d
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  int v45; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pExceptionObjecta[4]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v47; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 *v48; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v49; // [rsp+48h] [rbp-B8h]
  void **v50; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  _QWORD *v52; // [rsp+60h] [rbp-A0h]
  _DWORD *v53; // [rsp+68h] [rbp-98h]
  unsigned __int8 *v54; // [rsp+70h] [rbp-90h]
  _DWORD v55[4]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h]
  _DWORD *v57; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v58; // [rsp+98h] [rbp-68h]
  _DWORD v59[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-50h]
  _QWORD v61[10]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v62[4]; // [rsp+110h] [rbp+10h] BYREF
  int v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+134h] [rbp+34h]
  int v65; // [rsp+150h] [rbp+50h]
  BSTR *v66; // [rsp+154h] [rbp+54h]
  int v67; // [rsp+15Ch] [rbp+5Ch]

  v51 = a4;
  v5 = pExceptionObject;
  v49 = pExceptionObject;
  v6 = a1;
  v48 = a1;
  if ( pExceptionObject < 9 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    v45 = 87;
    throw (SafeIntException *)&v45;
  }
  if ( *(unsigned int *)a1 > pExceptionObject )
  {
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    v45 = 13;
    throw (SafeIntException *)&v45;
  }
  if ( *a3[19] < 0 )
  {
    v45 = 534;
    throw (SafeIntException *)&v45;
  }
  v7 = *(unsigned int *)((char *)a3[6] + 9);
  v47 = *a3[19];
  SafeInt<unsigned __int64>::operator*=<int>(&v47, 2);
  v8 = v47 >> 3;
  if ( (v47 & 7) != 0 )
  {
    SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v47, v47 >> 3, 1);
    LODWORD(v8) = v47;
  }
  if ( (int)v8 > v7 )
  {
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_8db10d0debd535326cee342840d89e0d_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    v45 = 13;
    throw (SafeIntException *)&v45;
  }
  v9 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&v47, 9, v7);
  if ( v5 < v9 )
  {
    v45 = 534;
    throw (SafeIntException *)&v45;
  }
  if ( v5 - v9 < 4 )
  {
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    v45 = 87;
    throw (SafeIntException *)&v45;
  }
  v10 = *(unsigned int *)&v6[v9];
  if ( v10 > v5 - v9 )
  {
    v39 = GetMemLogObject();
    CMemoryLog::Write(v39, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    v45 = 13;
    throw (SafeIntException *)&v45;
  }
  v11 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&v47, v9, v10);
  if ( v5 < v11 )
  {
    v45 = 534;
    throw (SafeIntException *)&v45;
  }
  v12 = v5 - v11;
  if ( v5 == v11 )
  {
    v40 = GetMemLogObject();
    CMemoryLog::Write(v40, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    v45 = 87;
    throw (SafeIntException *)&v45;
  }
  v13 = &v6[v11];
  v14 = 1;
  if ( v6[v11] != 1 )
  {
    v30 = *a3[19];
    v45 = 0;
    if ( v30 > 0 )
    {
      v31 = v45;
      v32 = v30;
      do
      {
        v33 = SafeInt<unsigned __int64>::subtraction(v12, v14);
        v34 = CBasicQualifierSet::ValidateBuffer(&v13[v14], v33);
        v14 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&v47, v14, v34);
        ++v31;
      }
      while ( v31 < v32 );
      v5 = v49;
      v6 = v48;
    }
  }
  v15 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&v48, v11, v14);
  if ( v5 < v15 )
  {
    LODWORD(v47) = 534;
    throw (SafeIntException *)&v47;
  }
  v16 = v5 - v15;
  if ( v5 - v15 < 4 )
  {
    v41 = GetMemLogObject();
    CMemoryLog::Write(v41, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)pExceptionObjecta;
  }
  v17 = (int *)&v6[v15];
  v56 = 0;
  v18 = *(_DWORD *)&v6[v15];
  if ( v18 < 0 )
  {
    v53 = v17 + 1;
    v54 = (unsigned __int8 *)v55;
    v55[0] = v18 & 0x7FFFFFFF;
    v55[1] = v18 & 0x7FFFFFFF;
    v55[2] = 0;
    v19 = (unsigned __int8 *)v55;
    v20 = (unsigned __int8 *)v55;
    v21 = (unsigned __int8 *)v55;
LABEL_17:
    v22 = v17 + 3;
    goto LABEL_18;
  }
  v54 = &v6[v15];
  v22 = v17 + 3;
  v53 = v17 + 3;
  if ( v17 == v55 )
  {
    v20 = &v6[v15];
    v21 = &v6[v15];
    v19 = &v6[v15];
    goto LABEL_17;
  }
  if ( v16 < 0xC )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)pExceptionObjecta;
  }
  v20 = &v6[v15];
  v21 = &v6[v15];
  v19 = &v6[v15];
LABEL_18:
  if ( v19 != (unsigned __int8 *)v55 )
    v20 = v21;
  v23 = 4;
  if ( v19 != (unsigned __int8 *)v55 )
    v23 = 12;
  v24 = (unsigned int)(*((_DWORD *)v20 + 1) + v23);
  if ( v24 > v16 )
  {
    v42 = GetMemLogObject();
    CMemoryLog::Write(v42, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)pExceptionObjecta;
  }
  v60 = 0;
  if ( *v17 >= 0 )
  {
    v58 = &v6[v15];
    v57 = v22;
  }
  else
  {
    v57 = v17 + 1;
    v58 = (unsigned __int8 *)v59;
    v59[0] = *v17 & 0x7FFFFFFF;
    v59[1] = v59[0];
    v59[2] = 0;
  }
  if ( *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&v48, v15, v24) > (unsigned __int64)*(unsigned int *)v6 )
  {
    v43 = GetMemLogObject();
    CMemoryLog::Write(v43, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    LODWORD(v47) = 13;
    throw (SafeIntException *)&v47;
  }
  v50 = &DummyInstancePartContainer::`vftable';
  v61[0] = &CInstancePart::`vftable'{for `CHeapContainer'};
  v61[1] = &CInstancePart::`vftable'{for `CDataTableContainer'};
  v61[2] = &CInstancePart::`vftable'{for `CQualifierSetContainer'};
  v61[3] = &CInstancePart::`vftable'{for `CQualifierSetListContainer'};
  v48 = (unsigned __int8 *)v62;
  IExtendedQualifierSet::IExtendedQualifierSet((IExtendedQualifierSet *)v62);
  v62[0] = &CQualifierSet::`vftable';
  v63 = 1;
  v64 = 1;
  v65 = 0;
  v66 = 0;
  v67 = -1;
  _InterlockedIncrement(&dword_1800D7E9C);
  ((void (__fastcall *)(void *, _QWORD *))*g_LifeControl)(&g_LifeControl, v62);
  v62[0] = &CInstanceQualifierSet::`vftable';
  CInstancePart::SetData((CInstancePart *)v61, v6, (struct CInstancePartContainer *)&v50, (struct CClassPart *)a3, v5);
  if ( (int)CInstancePart::IsValidInstancePart(v61, a3, v51) < 0 )
  {
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)pExceptionObjecta;
  }
  v25 = *(unsigned int *)v6;
  v52 = v62;
  v62[0] = &CQualifierSet::`vftable';
  v26 = v66;
  if ( v66 )
  {
    for ( i = 0; i < v65; v26 = v66 )
      SysFreeString(v26[i++]);
    CWin32DefaultArena::WbemMemFree(v26);
    v66 = 0;
  }
  v65 = 0;
  _InterlockedDecrement(&dword_1800D7E9C);
  (*(void (__fastcall **)(void *, _QWORD *))(g_LifeControl + 8LL))(&g_LifeControl, v62);
  CWin32DefaultArena::WbemMemFree(v66);
  return v25;
}

```

## disassembly

```asm
0x18001c1b0  mov     [rsp-8+arg_8], rbx
0x18001c1b5  push    rbp
0x18001c1b6  push    rsi
0x18001c1b7  push    rdi
0x18001c1b8  push    r12
0x18001c1ba  push    r13
0x18001c1bc  push    r14
0x18001c1be  push    r15
0x18001c1c0  lea     rbp, [rsp-0B0h]
0x18001c1c8  sub     rsp, 1B0h
0x18001c1cf  mov     rax, cs:__security_cookie
0x18001c1d6  xor     rax, rsp
0x18001c1d9  mov     [rbp+0E0h+var_40], rax
0x18001c1e0  mov     [rsp+1E0h+var_188], r9
0x18001c1e5  mov     r15, r8
0x18001c1e8  mov     rsi, rdx
0x18001c1eb  mov     [rsp+1E0h+var_198], rdx
0x18001c1f0  mov     r14, rcx
0x18001c1f3  mov     [rsp+1E0h+var_1A0], rcx
0x18001c1f8  cmp     rdx, 9
0x18001c1fc  jb      loc_18001C6D9
0x18001c202  mov     eax, [rcx]
0x18001c204  cmp     rax, rdx
0x18001c207  ja      loc_18001C742
0x18001c20d  mov     rax, [r8+98h]
0x18001c214  movsxd  rcx, dword ptr [rax]
0x18001c217  test    ecx, ecx
0x18001c219  js      loc_18001C652
0x18001c21f  mov     rax, [r8+30h]
0x18001c223  mov     ebx, [rax+9]
0x18001c226  mov     [rsp+1E0h+var_1A8], rcx
0x18001c22b  mov     edx, 2
0x18001c230  lea     rcx, [rsp+1E0h+var_1A8]
0x18001c235  call    ??$?XH@?$SafeInt@_K@@QEAAAEAV0@H@Z; SafeInt<unsigned __int64>::operator*=<int>(int)
0x18001c23a  mov     rcx, [rsp+1E0h+var_1A8]
0x18001c23f  mov     rax, rcx
0x18001c242  and     eax, 7
0x18001c245  shr     rcx, 3
0x18001c249  test    rax, rax
0x18001c24c  jz      short loc_18001C265
0x18001c24e  mov     r8d, 1
0x18001c254  mov     rdx, rcx
0x18001c257  lea     rcx, [rsp+1E0h+var_1A8]
0x18001c25c  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18001c261  mov     ecx, dword ptr [rsp+1E0h+var_1A8]
0x18001c265  mov     r8, rbx
0x18001c268  movsxd  rax, ecx
0x18001c26b  cmp     rax, rbx
0x18001c26e  ja      loc_18001C7AB
0x18001c274  mov     edx, 9
0x18001c279  lea     rcx, [rsp+1E0h+var_1A8]
0x18001c27e  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x18001c283  mov     rdx, [rax]
0x18001c286  cmp     rsi, rdx
0x18001c289  jb      loc_18001C604
0x18001c28f  mov     rax, rsi
0x18001c292  sub     rax, rdx
0x18001c295  cmp     rax, 4
0x18001c299  jb      loc_18001C814
0x18001c29f  mov     r8d, [r14+rdx]
0x18001c2a3  cmp     r8, rax
0x18001c2a6  ja      loc_18001C87D
0x18001c2ac  lea     rcx, [rsp+1E0h+var_1A8]
0x18001c2b1  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x18001c2b6  mov     rbx, [rax]
0x18001c2b9  cmp     rsi, rbx
0x18001c2bc  jb      loc_18001C61E
0x18001c2c2  mov     rdi, rsi
0x18001c2c5  sub     rdi, rbx
0x18001c2c8  cmp     rdi, 1
0x18001c2cc  jb      loc_18001C8E6
0x18001c2d2  lea     r13, [r14+rbx]
0x18001c2d6  mov     r12d, 1
0x18001c2dc  cmp     [r13+0], r12b
0x18001c2e0  jnz     loc_18001C679
0x18001c2e6  mov     r8, r12
0x18001c2e9  mov     rdx, rbx
0x18001c2ec  lea     rcx, [rsp+1E0h+var_1A0]
0x18001c2f1  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x18001c2f6  mov     rdx, [rax]
0x18001c2f9  cmp     rsi, rdx
0x18001c2fc  jb      loc_18001C638
0x18001c302  mov     r9, rsi
0x18001c305  sub     r9, rdx
0x18001c308  cmp     r9, 4
0x18001c30c  jb      loc_18001C94F
0x18001c312  lea     r8, [r14+rdx]
0x18001c316  xor     r12d, r12d
0x18001c319  mov     [rbp+0E0h+var_158], r12
0x18001c31d  mov     ecx, [r8]
0x18001c320  test    ecx, ecx
0x18001c322  jns     loc_18001C54A
0x18001c328  lea     rax, [r8+4]
0x18001c32c  mov     [rsp+1E0h+var_178], rax
0x18001c331  lea     rax, [rsp+1E0h+var_168]
0x18001c336  mov     [rsp+1E0h+var_170], rax
0x18001c33b  btr     ecx, 1Fh
0x18001c33f  mov     [rsp+1E0h+var_168], ecx
0x18001c343  mov     [rsp+1E0h+var_164], ecx
0x18001c347  mov     [rbp+0E0h+var_160], r12d
0x18001c34b  lea     r10, [rsp+1E0h+var_168]
0x18001c350  lea     rax, [rsp+1E0h+var_168]
0x18001c355  lea     rcx, [rsp+1E0h+var_168]
0x18001c35a  lea     r11, [r8+0Ch]
0x18001c35e  lea     rbx, [rsp+1E0h+var_168]
0x18001c363  cmp     r10, rbx
0x18001c366  cmovnz  rax, rcx
0x18001c36a  mov     ecx, 4
0x18001c36f  mov     edi, 0Ch
0x18001c374  lea     rbx, [rsp+1E0h+var_168]
0x18001c379  cmp     r10, rbx
0x18001c37c  cmovnz  ecx, edi
0x18001c37f  add     ecx, [rax+4]
0x18001c382  cmp     rcx, r9
0x18001c385  ja      loc_18001C9CC
0x18001c38b  mov     [rbp+0E0h+var_130], r12
0x18001c38f  cmp     [r8], r12d
0x18001c392  jge     loc_18001C66C
0x18001c398  lea     rax, [r8+4]
0x18001c39c  mov     [rbp+0E0h+var_150], rax
0x18001c3a0  lea     rax, [rbp+0E0h+var_140]
0x18001c3a4  mov     [rbp+0E0h+var_148], rax
0x18001c3a8  mov     eax, [r8]
0x18001c3ab  btr     eax, 1Fh
0x18001c3af  mov     [rbp+0E0h+var_140], eax
0x18001c3b2  mov     [rbp+0E0h+var_13C], eax
0x18001c3b5  mov     [rbp+0E0h+var_138], r12d
0x18001c3b9  mov     r8, rcx
0x18001c3bc  lea     rcx, [rsp+1E0h+var_1A0]
0x18001c3c1  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x18001c3c6  mov     ecx, [r14]
0x18001c3c9  cmp     [rax], rcx
0x18001c3cc  ja      loc_18001CA2A
0x18001c3d2  lea     rax, ??_7DummyInstancePartContainer@@6B@; const DummyInstancePartContainer::`vftable'
0x18001c3d9  mov     [rsp+1E0h+var_190], rax
0x18001c3de  lea     rax, ??_7CHeapContainer@@6B@; const CHeapContainer::`vftable'
0x18001c3e5  mov     [rbp+0E0h+var_120], rax
0x18001c3e9  lea     rax, ??_7CHeapContainer@@6B@; const CHeapContainer::`vftable'
0x18001c3f0  mov     [rbp+0E0h+var_118], rax
0x18001c3f4  lea     rax, ??_7CQualifierSetContainer@@6B@; const CQualifierSetContainer::`vftable'
0x18001c3fb  mov     [rbp+0E0h+var_110], rax
0x18001c3ff  lea     rax, ??_7CQualifierSetListContainer@@6B@; const CQualifierSetListContainer::`vftable'
0x18001c406  mov     [rbp+0E0h+var_108], rax
0x18001c40a  lea     rax, ??_7CInstancePart@@6BCHeapContainer@@@; const CInstancePart::`vftable'{for `CHeapContainer'}
0x18001c411  mov     [rbp+0E0h+var_120], rax
0x18001c415  lea     rax, ??_7CInstancePart@@6BCDataTableContainer@@@; const CInstancePart::`vftable'{for `CDataTableContainer'}
0x18001c41c  mov     [rbp+0E0h+var_118], rax
0x18001c420  lea     rax, ??_7CInstancePart@@6BCQualifierSetContainer@@@; const CInstancePart::`vftable'{for `CQualifierSetContainer'}
0x18001c427  mov     [rbp+0E0h+var_110], rax
0x18001c42b  lea     rax, ??_7CInstancePart@@6BCQualifierSetListContainer@@@; const CInstancePart::`vftable'{for `CQualifierSetListContainer'}
0x18001c432  mov     [rbp+0E0h+var_108], rax
0x18001c436  lea     rax, [rbp+0E0h+var_D0]
0x18001c43a  mov     [rsp+1E0h+var_1A0], rax
0x18001c43f  lea     rcx, [rbp+0E0h+var_D0]; this
0x18001c443  call    ??0IExtendedQualifierSet@@QEAA@XZ; IExtendedQualifierSet::IExtendedQualifierSet(void)
0x18001c448  lea     rdi, ??_7CQualifierSet@@6B@; const CQualifierSet::`vftable'
0x18001c44f  mov     [rbp+0E0h+var_D0], rdi
0x18001c453  mov     [rbp+0E0h+var_B0], 1
0x18001c45a  mov     [rbp+0E0h+var_AC], 1
0x18001c461  mov     [rbp+0E0h+var_90], r12d
0x18001c465  mov     [rbp+0E0h+var_8C], r12
0x18001c469  mov     [rbp+0E0h+var_84], 0FFFFFFFFh
0x18001c470  lock inc cs:dword_1800D7E9C
0x18001c477  mov     rax, cs:?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18001c47e  lea     rdx, [rbp+0E0h+var_D0]
0x18001c482  lea     rcx, ?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18001c489  mov     rax, [rax]
0x18001c48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c491  nop
0x18001c492  lea     rax, ??_7CInstanceQualifierSet@@6B@; const CInstanceQualifierSet::`vftable'
0x18001c499  mov     [rbp+0E0h+var_D0], rax
0x18001c49d  mov     [rsp+1E0h+var_1C0], rsi; pExceptionObject
0x18001c4a2  mov     r9, r15; struct CClassPart *
0x18001c4a5  lea     r8, [rsp+1E0h+var_190]; struct CInstancePartContainer *
0x18001c4aa  mov     rdx, r14; unsigned __int8 *
0x18001c4ad  lea     rcx, [rbp+0E0h+var_120]; this
0x18001c4b1  call    ?SetData@CInstancePart@@QEAAXPEAEPEAVCInstancePartContainer@@AEAVCClassPart@@_K@Z; CInstancePart::SetData(uchar *,CInstancePartContainer *,CClassPart &,unsigned __int64)
0x18001c4b6  mov     r8, [rsp+1E0h+var_188]
0x18001c4bb  mov     rdx, r15
0x18001c4be  lea     rcx, [rbp+0E0h+var_120]
0x18001c4c2  call    ?IsValidInstancePart@CInstancePart@@QEAAJPEAVCClassPart@@AEAV?$vector@UEmbeddedObj@@V?$wbem_allocator@UEmbeddedObj@@@@@std@@@Z; CInstancePart::IsValidInstancePart(CClassPart *,std::vector<EmbeddedObj,wbem_allocator<EmbeddedObj>> &)
0x18001c4c7  test    eax, eax
0x18001c4c9  js      loc_18001CA93
0x18001c4cf  mov     ebx, [r14]
0x18001c4d2  lea     rax, [rbp+0E0h+var_D0]
0x18001c4d6  mov     [rsp+1E0h+var_180], rax
0x18001c4db  mov     [rbp+0E0h+var_D0], rdi
0x18001c4df  mov     rax, [rbp+0E0h+var_8C]
0x18001c4e3  test    rax, rax
0x18001c4e6  jnz     loc_18001C5D1
0x18001c4ec  mov     [rbp+0E0h+var_90], r12d
0x18001c4f0  lock dec cs:dword_1800D7E9C
0x18001c4f7  mov     rdx, cs:?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18001c4fe  mov     rax, [rdx+8]
0x18001c502  lea     rdx, [rbp+0E0h+var_D0]
0x18001c506  lea     rcx, ?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18001c50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c512  nop
0x18001c513  mov     rcx, [rbp+0E0h+var_8C]
0x18001c517  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c51d  mov     rax, rbx
0x18001c520  mov     rcx, [rbp+0E0h+var_40]
0x18001c527  xor     rcx, rsp; StackCookie
0x18001c52a  call    __security_check_cookie
0x18001c52f  mov     rbx, [rsp+1E0h+arg_8]
0x18001c537  add     rsp, 1B0h
0x18001c53e  pop     r15
0x18001c540  pop     r14
0x18001c542  pop     r13
0x18001c544  pop     r12
0x18001c546  pop     rdi
0x18001c547  pop     rsi
0x18001c548  pop     rbp
0x18001c549  retn
0x18001c54a  mov     [rsp+1E0h+var_170], r8
0x18001c54f  lea     r11, [r8+0Ch]
0x18001c553  mov     [rsp+1E0h+var_178], r11
0x18001c558  lea     rax, [rsp+1E0h+var_168]
0x18001c55d  cmp     r8, rax
0x18001c560  jz      loc_18001C9B0
0x18001c566  cmp     r9, 0Ch
0x18001c56a  jnb     loc_18001C9BE
0x18001c570  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c576  mov     edx, 0FFFFFFFEh
0x18001c57b  mov     rcx, rax
0x18001c57e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c584  lea     rax, WPP_GLOBAL_Control
0x18001c58b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c592  cmp     rcx, rax
0x18001c595  jz      short loc_18001C5BF
0x18001c597  test    byte ptr [rcx+1Ch], 1
0x18001c59b  jz      short loc_18001C5BF
0x18001c59d  cmp     byte ptr [rcx+19h], 2
0x18001c5a1  jb      short loc_18001C5BF
0x18001c5a3  mov     edx, 0Bh
0x18001c5a8  lea     r9, aCxException; "CX_Exception()"
0x18001c5af  lea     r8, WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids
0x18001c5b6  mov     rcx, [rcx+10h]
0x18001c5ba  call    WPP_SF_s
0x18001c5bf  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001c5c6  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x18001c5cb  call    _CxxThrowException_0
0x18001c5d1  mov     edi, r12d
0x18001c5d4  cmp     [rbp+0E0h+var_90], r12d
0x18001c5d8  jle     short loc_18001C5F2
0x18001c5da  movsxd  rcx, edi
0x18001c5dd  mov     rcx, [rax+rcx*8]; bstrString
0x18001c5e1  call    cs:__imp_SysFreeString
0x18001c5e7  inc     edi
0x18001c5e9  mov     rax, [rbp+0E0h+var_8C]
0x18001c5ed  cmp     edi, [rbp+0E0h+var_90]
0x18001c5f0  jl      short loc_18001C5DA
0x18001c5f2  mov     rcx, rax
0x18001c5f5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001c5fb  mov     [rbp+0E0h+var_8C], r12
0x18001c5ff  jmp     loc_18001C4EC
0x18001c604  mov     [rsp+1E0h+var_1B0], 216h
0x18001c60c  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001c613  lea     rcx, [rsp+1E0h+var_1B0]; pExceptionObject
0x18001c618  call    _CxxThrowException_0
0x18001c61e  mov     [rsp+1E0h+var_1B0], 216h
0x18001c626  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001c62d  lea     rcx, [rsp+1E0h+var_1B0]; pExceptionObject
0x18001c632  call    _CxxThrowException_0
0x18001c638  mov     dword ptr [rsp+1E0h+var_1A8], 216h
0x18001c640  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001c647  lea     rcx, [rsp+1E0h+var_1A8]; pExceptionObject
0x18001c64c  call    _CxxThrowException_0
0x18001c652  mov     [rsp+1E0h+var_1B0], 216h
0x18001c65a  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001c661  lea     rcx, [rsp+1E0h+var_1B0]; pExceptionObject
0x18001c666  call    _CxxThrowException_0
0x18001c66c  mov     [rbp+0E0h+var_148], r8
0x18001c670  mov     [rbp+0E0h+var_150], r11
0x18001c674  jmp     loc_18001C3B9
0x18001c679  mov     rax, [r15+98h]
0x18001c680  mov     eax, [rax]
0x18001c682  mov     [rsp+1E0h+var_1B0], 0
0x18001c68a  test    eax, eax
0x18001c68c  jle     loc_18001C2E6
0x18001c692  mov     esi, [rsp+1E0h+var_1B0]
0x18001c696  mov     r14d, eax
0x18001c699  mov     rdx, r12
0x18001c69c  mov     rcx, rdi
0x18001c69f  call    ?subtraction@?$SafeInt@_K@@CA_K_K0@Z; SafeInt<unsigned __int64>::subtraction(unsigned __int64,unsigned __int64)
0x18001c6a4  lea     rcx, [r12+r13]; unsigned __int8 *
0x18001c6a8  mov     rdx, rax; unsigned __int64
0x18001c6ab  call    ?ValidateBuffer@CBasicQualifierSet@@SA_KPEAE_K@Z; CBasicQualifierSet::ValidateBuffer(uchar *,unsigned __int64)
0x18001c6b0  mov     r8, rax
0x18001c6b3  mov     rdx, r12
0x18001c6b6  lea     rcx, [rsp+1E0h+var_1A8]
0x18001c6bb  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x18001c6c0  mov     r12, [rax]
0x18001c6c3  inc     esi
0x18001c6c5  cmp     esi, r14d
0x18001c6c8  jl      short loc_18001C699
0x18001c6ca  mov     rsi, [rsp+1E0h+var_198]
0x18001c6cf  mov     r14, [rsp+1E0h+var_1A0]
0x18001c6d4  jmp     loc_18001C2E6
0x18001c6d9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
  ... truncated ...
```
