# CWbemInstance::GetPropQualifier(CPropertyInformation *,ushort const *,CVar *,long *,long *)

- ea: `0x1800145d0`
- end: `0x180014f21`
- name: `?GetPropQualifier@CWbemInstance@@UEAAJPEAVCPropertyInformation@@PEBGPEAVCVar@@PEAJ3@Z`
- size: `2385`
- prototype: `int(CWbemInstance *__hidden this, struct CPropertyInformation *, const unsigned __int16 *, struct CVar *, int *, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180005fc4`
- `0x1800088d0`
- `0x18000aae0`
- `0x18000b070`
- `0x180013ac0`
- `0x1800145d0`
- `0x180014f30`
- `0x180035b08`
- `0x180037120`
- `0x1800503f0`
- `0x18006fa4c`
- `0x180071c50`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180014863`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800148bc`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180014a50`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180014aa9`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180014863`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800148bc`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180014a50`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180014aa9`
- `wbemcomn!GetMemLogObject` at `0x180014dc5`
- `wbemcomn!GetMemLogObject` at `0x180014e39`
- `wbemcomn!GetMemLogObject` at `0x180014ebe`
- `wbemcomn!GetMemLogObject` at `0x180014dc5`
- `wbemcomn!GetMemLogObject` at `0x180014e39`
- `wbemcomn!GetMemLogObject` at `0x180014ebe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014dd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014e47`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014ecc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014dd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014e47`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014ecc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014b5a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014cb6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014d53`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014b5a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014cb6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014d53`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWbemInstance::GetPropQualifier(
        CWbemInstance *this,
        struct CPropertyInformation *a2,
        unsigned __int16 *a3,
        struct CVar *a4,
        int *a5,
        int *a6)
{
  unsigned __int16 *v6; // rsi
  int v9; // edi
  unsigned int v10; // ecx
  int v11; // r9d
  int *v12; // rdx
  _BYTE *v13; // rbx
  unsigned int *v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // r13
  unsigned int *v17; // rbx
  int KnownStringIndex; // edx
  unsigned __int64 v19; // r12
  __int64 v20; // rdi
  char * near *v21; // rcx
  _BYTE *v22; // r14
  int v23; // r15d
  unsigned __int16 *v24; // rsi
  WCHAR v25; // di
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // eax
  unsigned int v30; // ecx
  _QWORD *v31; // r13
  unsigned __int64 v32; // r12
  __int64 v33; // rdi
  char * near *v34; // rcx
  _BYTE *v35; // r15
  int v36; // esi
  unsigned __int16 *v37; // r14
  WCHAR v38; // di
  int v39; // eax
  int v40; // eax
  int v41; // ecx
  int v42; // eax
  unsigned int v43; // ecx
  BSTR *v44; // rax
  int v46; // ecx
  int v47; // ecx
  int v48; // eax
  int *v49; // rdx
  __int64 v50; // r9
  unsigned __int64 v51; // rdi
  int i; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v54; // rax
  int v55; // ecx
  CMemoryLog *v56; // rax
  WCHAR DestStr[2]; // [rsp+30h] [rbp-99h] BYREF
  int v58; // [rsp+34h] [rbp-95h]
  unsigned __int64 v59; // [rsp+38h] [rbp-91h]
  void **v60; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v61; // [rsp+48h] [rbp-81h]
  unsigned int *v62; // [rsp+50h] [rbp-79h]
  _QWORD *v63; // [rsp+58h] [rbp-71h]
  __int64 v64; // [rsp+60h] [rbp-69h]
  __int64 v65; // [rsp+68h] [rbp-61h]
  void ***v66; // [rsp+70h] [rbp-59h]
  int *v67; // [rsp+78h] [rbp-51h]
  int v68; // [rsp+80h] [rbp-49h] BYREF
  void *v69; // [rsp+84h] [rbp-45h]
  int v70; // [rsp+8Ch] [rbp-3Dh]
  void **v71; // [rsp+90h] [rbp-39h] BYREF
  char *v72; // [rsp+98h] [rbp-31h]
  int v73; // [rsp+A0h] [rbp-29h]
  char *v74; // [rsp+A8h] [rbp-21h]
  unsigned int v75; // [rsp+B0h] [rbp-19h]
  int v76; // [rsp+B8h] [rbp-11h] BYREF
  _DWORD *v77; // [rsp+C0h] [rbp-9h]
  char *v78; // [rsp+C8h] [rbp-1h]
  CWbemInstance *pExceptionObject; // [rsp+120h] [rbp+57h] BYREF
  WCHAR SrcStr; // [rsp+128h] [rbp+5Fh] BYREF
  unsigned __int16 *v81; // [rsp+130h] [rbp+67h]
  CVar *v82; // [rsp+138h] [rbp+6Fh]

  v82 = a4;
  v81 = a3;
  pExceptionObject = this;
  v6 = a3;
  IExtendedQualifierSet::IExtendedQualifierSet((IExtendedQualifierSet *)&v60);
  v60 = &CQualifierSet::`vftable';
  v9 = 1;
  v64 = 1;
  v68 = 0;
  v69 = 0;
  v70 = -1;
  _InterlockedIncrement(&dword_1800D7E9C);
  ((void (__fastcall *)(void *, void ***))*g_LifeControl)(&g_LifeControl, &v60);
  v60 = &CInstancePropertyQualifierSet::`vftable';
  v71 = &CInstancePQSContainer::`vftable';
  v72 = 0;
  v74 = 0;
  v10 = (_DWORD)a2 - *((_DWORD *)this + 112) + 14;
  v11 = *((unsigned __int16 *)a2 + 2);
  v72 = (char *)this + 336;
  v73 = v11;
  v74 = (char *)this + 400;
  v75 = v10;
  v12 = (int *)(*((_QWORD *)this + 56) + v10);
  v76 = *v12;
  v78 = (char *)this + 600;
  v77 = v12 + 1;
  v13 = (_BYTE *)*((_QWORD *)this + 43);
  if ( *v13 == 1 )
    goto LABEL_2;
  v14 = (unsigned int *)(v13 + 1);
  v46 = 0;
  if ( v11 )
  {
    do
    {
      v14 = (unsigned int *)((char *)v14 + *v14);
      ++v46;
    }
    while ( v46 < v11 );
  }
  if ( !v14 )
LABEL_2:
    v14 = &mstatic_EmptySet;
  v15 = ((__int64 (__fastcall *)(void ***))*v71)(&v71);
  v61 = *v14;
  v62 = v14 + 1;
  v63 = (_QWORD *)v15;
  v66 = &v71;
  v67 = &v76;
  v65 = ((__int64 (__fastcall *)(void ***))v71[1])(&v71);
  v16 = v63;
  v17 = v62;
  KnownStringIndex = CKnownStringTable::GetKnownStringIndex(v6);
  v58 = KnownStringIndex;
  v19 = (unsigned __int64)v17 + *(v17 - 1) - 4;
  v59 = v19;
  if ( KnownStringIndex >= 0 )
  {
    while ( (unsigned __int64)v17 < v19 )
    {
      if ( KnownStringIndex == (*v17 ^ 0x80000000) )
        goto LABEL_39;
      v47 = *(unsigned int *)((char *)v17 + 5);
      if ( (v47 & 0xFFFu) > 0x7F )
      {
        v17 = (unsigned int *)((char *)v17 + 9);
      }
      else
      {
        if ( (v47 & 0x2000) != 0 )
          v48 = 4;
        else
          v48 = *((_DWORD *)&m_staticLengths + (v47 & 0xFFF));
        v17 = (unsigned int *)((char *)v17 + (unsigned int)(v48 + 4) + 5);
      }
    }
    v17 = 0;
  }
  else
  {
    while ( (unsigned __int64)v17 < v19 )
    {
      v20 = *v17;
      if ( CFastHeap::IsFakeAddress(*v17) )
      {
        if ( !mstatic_nNumStrings )
          mstatic_nNumStrings = 11;
        LODWORD(v20) = v20 & 0x7FFFFFFF;
        if ( (unsigned int)v20 >= 0xB )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
              "CX_Exception()");
          }
          throw (CX_Exception *)&pExceptionObject;
        }
        _mm_lfence();
        v21 = (&mstatic_aszStrings)[v20];
      }
      else
      {
        if ( (unsigned int)v20 > *(_DWORD *)(v16[1] + 4LL) )
          throw (CX_Exception *)&pExceptionObject;
        v21 = (char * near *)(*v16 + (unsigned int)v20);
      }
      v22 = (char *)v21 + 1;
      if ( *(_BYTE *)v21 == 1 )
      {
        v27 = wbem_unaligned_wcsicmp((const unsigned __int16 *)((char *)v21 + 1), v6);
      }
      else
      {
        v23 = 117440512;
        v24 = v81;
        v19 = v59;
        while ( v23 && (*v22 || *v24) )
        {
          v25 = *v24;
          if ( *v24 > 0x7Fu )
          {
            SrcStr = *v24;
            DestStr[0] = 0;
            if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, DestStr, 1) )
              v25 = DestStr[0];
            else
              v25 = SrcStr;
          }
          else if ( (unsigned __int16)(v25 - 65) <= 0x19u )
          {
            v25 += 32;
          }
          v30 = (unsigned __int8)*v22;
          if ( v30 > 0x7F )
          {
            SrcStr = (unsigned __int8)*v22;
            DestStr[0] = 0;
            if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, DestStr, 1) )
              LOWORD(v30) = DestStr[0];
            else
              LOWORD(v30) = SrcStr;
          }
          else if ( (unsigned __int16)(v30 - 65) <= 0x19u )
          {
            LOWORD(v30) = v30 + 32;
          }
          v26 = v25 - (unsigned __int16)v30;
          if ( v26 )
            goto LABEL_18;
          --v23;
          ++v22;
          ++v24;
        }
        v26 = 0;
LABEL_18:
        v27 = -v26;
        v6 = v81;
      }
      if ( !v27 )
        goto LABEL_38;
      v28 = *(unsigned int *)((char *)v17 + 5);
      if ( (v28 & 0xFFFu) > 0x7F )
      {
        v17 = (unsigned int *)((char *)v17 + 9);
      }
      else
      {
        if ( (v28 & 0x2000) != 0 )
          v29 = 4;
        else
          v29 = *((_DWORD *)&m_staticLengths + (v28 & 0xFFF));
        v17 = (unsigned int *)((char *)v17 + (unsigned int)(v29 + 4) + 5);
      }
    }
    v17 = 0;
LABEL_38:
    KnownStringIndex = v58;
    v9 = 1;
  }
LABEL_39:
  if ( v17 )
    goto LABEL_93;
  if ( (_DWORD)v64 != 2 )
  {
    v17 = (unsigned int *)*((_QWORD *)v67 + 1);
    if ( KnownStringIndex >= 0 )
    {
      v51 = (unsigned __int64)v17 + *(v17 - 1) - 4;
      while ( (unsigned __int64)v17 < v51 )
      {
        if ( KnownStringIndex == (*v17 ^ 0x80000000) )
          goto LABEL_76;
        v17 = (unsigned int *)((char *)v17 + CType::GetLength(*(unsigned int *)((char *)v17 + 5)) + 9);
        KnownStringIndex = v58;
      }
    }
    else
    {
      v31 = (_QWORD *)*((_QWORD *)v67 + 2);
      v32 = (unsigned __int64)v17 + *(v17 - 1) - 4;
      v59 = v32;
      while ( (unsigned __int64)v17 < v32 )
      {
        v33 = *v17;
        if ( CFastHeap::IsFakeAddress(*v17) )
        {
          if ( !mstatic_nNumStrings )
            mstatic_nNumStrings = 11;
          LODWORD(v33) = v33 & 0x7FFFFFFF;
          if ( (unsigned int)v33 >= 0xB )
          {
            v54 = GetMemLogObject();
            CMemoryLog::Write(v54, -2);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
                "CX_Exception()");
            }
            throw (CX_Exception *)&pExceptionObject;
          }
          _mm_lfence();
          v34 = (&mstatic_aszStrings)[v33];
        }
        else
        {
          if ( (unsigned int)v33 > *(_DWORD *)(v31[1] + 4LL) )
            throw (CX_Exception *)&pExceptionObject;
          v34 = (char * near *)(*v31 + (unsigned int)v33);
        }
        v35 = (char *)v34 + 1;
        if ( *(_BYTE *)v34 == 1 )
        {
          v40 = wbem_unaligned_wcsicmp((const unsigned __int16 *)((char *)v34 + 1), v6);
        }
        else
        {
          v36 = 117440512;
          v37 = v81;
          v32 = v59;
          while ( v36 && (*v35 || *v37) )
          {
            v38 = *v37;
            if ( *v37 > 0x7Fu )
            {
              SrcStr = *v37;
              DestStr[0] = 0;
              if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, DestStr, 1) )
                v38 = DestStr[0];
              else
                v38 = SrcStr;
            }
            else if ( (unsigned __int16)(v38 - 65) <= 0x19u )
            {
              v38 += 32;
            }
            v43 = (unsigned __int8)*v35;
            if ( v43 > 0x7F )
            {
              SrcStr = (unsigned __int8)*v35;
              DestStr[0] = 0;
              if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, DestStr, 1) )
                LOWORD(v43) = DestStr[0];
              else
                LOWORD(v43) = SrcStr;
            }
            else if ( (unsigned __int16)(v43 - 65) <= 0x19u )
            {
              LOWORD(v43) = v43 + 32;
            }
            v39 = v38 - (unsigned __int16)v43;
            if ( v38 != (unsigned __int16)v43 )
              goto LABEL_56;
            --v36;
            ++v35;
            ++v37;
          }
          v39 = 0;
LABEL_56:
          v40 = -v39;
          v6 = v81;
        }
        if ( !v40 )
          goto LABEL_76;
        v41 = *(unsigned int *)((char *)v17 + 5);
        if ( (v41 & 0xFFFu) > 0x7F )
        {
          v42 = 0;
        }
        else if ( (v41 & 0x2000) != 0 )
        {
          v42 = 4;
        }
        else
        {
          v42 = *((_DWORD *)&m_staticLengths + (v41 & 0xFFF));
        }
        v17 = (unsigned int *)((char *)v17 + (unsigned int)(v42 + 4) + 5);
      }
    }
    v17 = 0;
LABEL_76:
    if ( v17 && ((_BYTE)v17[1] & (unsigned __int8)v64) != 0 )
    {
      v9 = 0;
LABEL_93:
      v49 = a5;
      if ( a5 )
      {
        v55 = *((unsigned __int8 *)v17 + 4);
        *a5 = v55;
        *(_BYTE *)v49 = v55 & 0x9F | (32 * (v9 ^ 1));
      }
      if ( a6 )
        *a6 = *(unsigned int *)((char *)v17 + 5);
      if ( !v82 )
        goto LABEL_101;
      v50 = 360;
      if ( !v9 )
        v50 = 600;
      if ( !CUntypedValue::StoreToCVar(
              (unsigned int *)((char *)v17 + 9),
              *(unsigned int *)((char *)v17 + 5),
              v82,
              (CWbemInstance *)((char *)pExceptionObject + v50),
              0) )
      {
        v56 = GetMemLogObject();
        CMemoryLog::Write(v56, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749894LL);
        }
        CInstancePropertyQualifierSet::~CInstancePropertyQualifierSet((CInstancePropertyQualifierSet *)&v60);
        return 2147749894LL;
      }
      else
      {
LABEL_101:
        v60 = &CQualifierSet::`vftable';
        CFixedBSTRArray::Free((CFixedBSTRArray *)&v68);
        _InterlockedDecrement(&dword_1800D7E9C);
        (*(void (__fastcall **)(void *, void ***))(g_LifeControl + 8LL))(&g_LifeControl, &v60);
        CWin32DefaultArena::WbemMemFree(v69);
        return 0;
      }
    }
  }
  v60 = &CQualifierSet::`vftable';
  v44 = (BSTR *)v69;
  if ( v69 )
  {
    for ( i = 0; i < v68; v44 = (BSTR *)v69 )
      SysFreeString(v44[i++]);
    CWin32DefaultArena::WbemMemFree(v44);
    v69 = 0;
  }
  v68 = 0;
  _InterlockedDecrement(&dword_1800D7E9C);
  (*(void (__fastcall **)(void *, void ***))(g_LifeControl + 8LL))(&g_LifeControl, &v60);
  CWin32DefaultArena::WbemMemFree(v69);
  return 2147749890LL;
}

```

## disassembly

```asm
0x1800145d0  mov     [rsp-8+arg_18], r9
0x1800145d5  mov     [rsp-8+arg_10], r8
0x1800145da  mov     [rsp-8+pExceptionObject], rcx
0x1800145df  push    rbp
0x1800145e0  push    rbx
0x1800145e1  push    rsi
0x1800145e2  push    rdi
0x1800145e3  push    r12
0x1800145e5  push    r13
0x1800145e7  push    r14
0x1800145e9  push    r15
0x1800145eb  lea     rbp, [rsp-0Fh]
0x1800145f0  sub     rsp, 0D8h
0x1800145f7  mov     rsi, r8
0x1800145fa  mov     rbx, rdx
0x1800145fd  mov     r14, rcx
0x180014600  lea     rcx, [rsp+110h+var_D0]; this
0x180014605  call    ??0IExtendedQualifierSet@@QEAA@XZ; IExtendedQualifierSet::IExtendedQualifierSet(void)
0x18001460a  lea     rax, ??_7CQualifierSet@@6B@; const CQualifierSet::`vftable'
0x180014611  mov     [rsp+110h+var_D0], rax
0x180014616  mov     edi, 1
0x18001461b  mov     [rbp+47h+var_B0], rdi
0x18001461f  xor     r15d, r15d
0x180014622  mov     [rbp+47h+var_90], r15d
0x180014626  mov     [rbp+47h+var_8C], r15
0x18001462a  mov     [rbp+47h+var_84], 0FFFFFFFFh
0x180014631  lock inc cs:dword_1800D7E9C
0x180014638  mov     rax, cs:?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18001463f  lea     rdx, [rsp+110h+var_D0]
0x180014644  lea     rcx, ?g_LifeControl@@3VCDllLifeControl@@A; CDllLifeControl g_LifeControl
0x18001464b  mov     rax, [rax]
0x18001464e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014653  nop
0x180014654  lea     rax, ??_7CInstanceQualifierSet@@6B@; const CInstanceQualifierSet::`vftable'
0x18001465b  mov     [rsp+110h+var_D0], rax
0x180014660  lea     rax, ??_7CInstancePropertyQualifierSet@@6B@; const CInstancePropertyQualifierSet::`vftable'
0x180014667  mov     [rsp+110h+var_D0], rax
0x18001466c  lea     rax, ??_7CQualifierSetContainer@@6B@; const CQualifierSetContainer::`vftable'
0x180014673  mov     [rbp+47h+var_80], rax
0x180014677  lea     rax, ??_7CInstancePQSContainer@@6B@; const CInstancePQSContainer::`vftable'
0x18001467e  mov     [rbp+47h+var_80], rax
0x180014682  mov     [rbp+47h+var_78], r15
0x180014686  mov     [rbp+47h+var_68], r15
0x18001468a  mov     ecx, ebx
0x18001468c  sub     ecx, [r14+1C0h]
0x180014693  add     ecx, 0Eh
0x180014696  movzx   r9d, word ptr [rbx+4]
0x18001469b  lea     r8, [r14+150h]
0x1800146a2  mov     [rbp+47h+var_78], r8
0x1800146a6  mov     [rbp+47h+var_70], r9d
0x1800146aa  lea     rax, [r14+190h]
0x1800146b1  mov     [rbp+47h+var_68], rax
0x1800146b5  mov     [rbp+47h+var_60], ecx
0x1800146b8  mov     edx, ecx
0x1800146ba  add     rdx, [r14+1C0h]
0x1800146c1  mov     eax, [rdx]
0x1800146c3  mov     [rbp+47h+var_58], eax
0x1800146c6  add     rdx, 4
0x1800146ca  mov     [rbp+47h+var_50], rdx
0x1800146ce  lea     rax, [r14+258h]
0x1800146d5  mov     [rbp+47h+var_48], rax
0x1800146d9  mov     [rbp+47h+var_50], rdx
0x1800146dd  mov     rbx, [r8+8]
0x1800146e1  cmp     [rbx], dil
0x1800146e4  jnz     loc_180014B79
0x1800146ea  lea     rbx, ?mstatic_EmptySet@@3KA; ulong mstatic_EmptySet
0x1800146f1  jmp     short loc_1800146F8
0x1800146f3  test    rbx, rbx
0x1800146f6  jz      short loc_1800146EA
0x1800146f8  mov     rax, [rbp+47h+var_80]
0x1800146fc  lea     rcx, [rbp+47h+var_80]
0x180014700  mov     rax, [rax]
0x180014703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014708  mov     ecx, [rbx]
0x18001470a  mov     [rsp+110h+var_C8], ecx
0x18001470e  lea     rcx, [rbx+4]
0x180014712  mov     [rbp+47h+var_C0], rcx
0x180014716  mov     [rbp+47h+var_B8], rax
0x18001471a  lea     rax, [rbp+47h+var_80]
0x18001471e  mov     [rbp+47h+var_A0], rax
0x180014722  lea     rax, [rbp+47h+var_58]
0x180014726  mov     [rbp+47h+var_98], rax
0x18001472a  mov     rax, [rbp+47h+var_80]
0x18001472e  lea     rcx, [rbp+47h+var_80]
0x180014732  mov     rax, [rax+8]
0x180014736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001473b  mov     [rbp+47h+var_A8], rax
0x18001473f  mov     r13, [rbp+47h+var_B8]
0x180014743  mov     rbx, [rbp+47h+var_C0]
0x180014747  mov     rcx, rsi; unsigned __int16 *
0x18001474a  call    ?GetKnownStringIndex@CKnownStringTable@@SAHPEBG@Z; CKnownStringTable::GetKnownStringIndex(ushort const *)
0x18001474f  mov     edx, eax
0x180014751  mov     [rsp+110h+var_DC], eax
0x180014755  mov     ecx, [rbx-4]
0x180014758  lea     r12, [rbx-4]
0x18001475c  add     r12, rcx
0x18001475f  mov     [rsp+110h+var_D8], r12
0x180014764  lea     r15, __ImageBase
0x18001476b  test    eax, eax
0x18001476d  jns     loc_180014BA1
0x180014773  cmp     rbx, r12
0x180014776  jnb     loc_18001491B
0x18001477c  mov     edi, [rbx]
0x18001477e  mov     ecx, edi; unsigned int
0x180014780  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x180014785  test    al, al
0x180014787  jnz     loc_1800148EB
0x18001478d  mov     rax, [r13+8]
0x180014791  cmp     edi, [rax+4]
0x180014794  ja      loc_180014D77
0x18001479a  mov     ecx, edi
0x18001479c  add     rcx, [r13+0]
0x1800147a0  lea     r14, [rcx+1]
0x1800147a4  cmp     byte ptr [rcx], 1
0x1800147a7  jz      loc_180014CD3
0x1800147ad  mov     r15d, 7000000h
0x1800147b3  mov     rsi, [rbp+47h+arg_10]
0x1800147b7  mov     r12, [rsp+110h+var_D8]
0x1800147bc  test    r15d, r15d
0x1800147bf  jz      short loc_1800147EC
0x1800147c1  cmp     byte ptr [r14], 0
0x1800147c5  jnz     short loc_1800147CD
0x1800147c7  cmp     word ptr [rsi], 0
0x1800147cb  jz      short loc_1800147EC
0x1800147cd  movzx   edi, word ptr [rsi]
0x1800147d0  cmp     di, 7Fh
0x1800147d4  ja      short loc_180014834
0x1800147d6  lea     eax, [rdi-41h]
0x1800147d9  cmp     ax, 19h
0x1800147dd  ja      loc_180014875
0x1800147e3  add     di, 20h ; ' '
0x1800147e7  jmp     loc_180014875
0x1800147ec  xor     ecx, ecx
0x1800147ee  neg     ecx
0x1800147f0  mov     rsi, [rbp+47h+arg_10]
0x1800147f4  lea     r15, __ImageBase
0x1800147fb  test    ecx, ecx
0x1800147fd  jz      loc_18001491D
0x180014803  mov     ecx, [rbx+5]
0x180014806  mov     eax, ecx
0x180014808  and     eax, 0FFFh
0x18001480d  cmp     eax, 7Fh
0x180014810  ja      loc_180014D8F
0x180014816  bt      ecx, 0Dh
0x18001481a  jnb     loc_180014C03
0x180014820  mov     eax, 4
0x180014825  lea     ecx, [rax+4]
0x180014828  add     rbx, 5
0x18001482c  add     rbx, rcx
0x18001482f  jmp     loc_180014773
0x180014834  mov     [rbp+47h+SrcStr], di
0x180014838  xor     eax, eax
0x18001483a  mov     [rsp+110h+DestStr], ax
0x18001483f  mov     eax, 1
0x180014844  mov     [rsp+110h+cchDest], eax; cchDest
0x180014848  lea     rcx, [rsp+110h+DestStr]
0x18001484d  mov     [rsp+110h+lpDestStr], rcx; lpDestStr
0x180014852  mov     r9d, eax; cchSrc
0x180014855  lea     r8, [rbp+47h+SrcStr]; lpSrcStr
0x180014859  mov     edx, 100h; dwMapFlags
0x18001485e  mov     ecx, 7Fh; Locale
0x180014863  call    cs:__imp_LCMapStringW
0x180014869  test    eax, eax
0x18001486b  jnz     loc_180014DB1
0x180014871  movzx   edi, [rbp+47h+SrcStr]
0x180014875  movzx   ecx, byte ptr [r14]
0x180014879  cmp     ecx, 7Fh
0x18001487c  ja      short loc_18001488D
0x18001487e  lea     eax, [rcx-41h]
0x180014881  cmp     ax, 19h
0x180014885  ja      short loc_1800148CE
0x180014887  add     cx, 20h ; ' '
0x18001488b  jmp     short loc_1800148CE
0x18001488d  mov     [rbp+47h+SrcStr], cx
0x180014891  xor     eax, eax
0x180014893  mov     [rsp+110h+DestStr], ax
0x180014898  mov     eax, 1
0x18001489d  mov     [rsp+110h+cchDest], eax; cchDest
0x1800148a1  lea     rcx, [rsp+110h+DestStr]
0x1800148a6  mov     [rsp+110h+lpDestStr], rcx; lpDestStr
0x1800148ab  mov     r9d, eax; cchSrc
0x1800148ae  lea     r8, [rbp+47h+SrcStr]; lpSrcStr
0x1800148b2  mov     edx, 100h; dwMapFlags
0x1800148b7  mov     ecx, 7Fh; Locale
0x1800148bc  call    cs:__imp_LCMapStringW
0x1800148c2  test    eax, eax
0x1800148c4  jnz     loc_180014DBB
0x1800148ca  movzx   ecx, [rbp+47h+SrcStr]
0x1800148ce  movzx   eax, cx
0x1800148d1  movzx   ecx, di
0x1800148d4  sub     ecx, eax
0x1800148d6  jnz     loc_1800147EE
0x1800148dc  dec     r15d
0x1800148df  inc     r14
0x1800148e2  add     rsi, 2
0x1800148e6  jmp     loc_1800147BC
0x1800148eb  cmp     cs:?mstatic_nNumStrings@@3HA, 0; int mstatic_nNumStrings
0x1800148f2  jnz     short loc_1800148FE
0x1800148f4  mov     cs:?mstatic_nNumStrings@@3HA, 0Bh; int mstatic_nNumStrings
0x1800148fe  btr     edi, 1Fh
0x180014902  cmp     edi, 0Bh
0x180014905  jnb     loc_180014DC5
0x18001490b  lfence
0x18001490e  mov     rcx, ds:rva ?mstatic_aszStrings@@3PAPEADA[r15+rdi*8]; char * near * mstatic_aszStrings ...
0x180014916  jmp     loc_1800147A0
0x18001491b  xor     ebx, ebx
0x18001491d  mov     edx, [rsp+110h+var_DC]
0x180014921  mov     edi, 1
0x180014926  test    rbx, rbx
0x180014929  jnz     loc_180014C25
0x18001492f  cmp     dword ptr [rbp+47h+var_B0], 2
0x180014933  jz      loc_180014B12
0x180014939  mov     rax, [rbp+47h+var_98]
0x18001493d  mov     rbx, [rax+8]
0x180014941  test    edx, edx
0x180014943  jns     loc_180014CE5
0x180014949  mov     r13, [rax+10h]
0x18001494d  lea     rax, [rbx-4]
0x180014951  mov     r12d, [rax]
0x180014954  add     r12, rax
0x180014957  mov     [rsp+110h+var_D8], r12
0x18001495c  nop     dword ptr [rax+00h]
0x180014960  cmp     rbx, r12
0x180014963  jnb     loc_180014B07
0x180014969  mov     edi, [rbx]
0x18001496b  mov     ecx, edi; unsigned int
0x18001496d  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x180014972  test    al, al
0x180014974  jnz     loc_180014AD7
0x18001497a  mov     rax, [r13+8]
0x18001497e  cmp     edi, [rax+4]
0x180014981  ja      loc_180014D66
0x180014987  mov     ecx, edi
0x180014989  add     rcx, [r13+0]
0x18001498d  lea     r15, [rcx+1]
0x180014991  cmp     byte ptr [rcx], 1
0x180014994  jz      loc_180014CC3
0x18001499a  mov     esi, 7000000h
0x18001499f  mov     r14, [rbp+47h+arg_10]
0x1800149a3  mov     r12, [rsp+110h+var_D8]
0x1800149a8  test    esi, esi
0x1800149aa  jz      short loc_1800149D9
0x1800149ac  cmp     byte ptr [r15], 0
0x1800149b0  jnz     short loc_1800149B9
0x1800149b2  cmp     word ptr [r14], 0
0x1800149b7  jz      short loc_1800149D9
0x1800149b9  movzx   edi, word ptr [r14]
0x1800149bd  cmp     di, 7Fh
0x1800149c1  ja      short loc_180014A21
0x1800149c3  lea     eax, [rdi-41h]
0x1800149c6  cmp     ax, 19h
0x1800149ca  ja      loc_180014A62
0x1800149d0  add     di, 20h ; ' '
0x1800149d4  jmp     loc_180014A62
0x1800149d9  xor     eax, eax
0x1800149db  neg     eax
0x1800149dd  mov     rsi, [rbp+47h+arg_10]
0x1800149e1  test    eax, eax
0x1800149e3  jz      loc_180014B09
0x1800149e9  mov     ecx, [rbx+5]
0x1800149ec  mov     eax, ecx
0x1800149ee  and     eax, 0FFFh
0x1800149f3  cmp     eax, 7Fh
0x1800149f6  ja      loc_180014D88
0x1800149fc  bt      ecx, 0Dh
0x180014a00  jnb     loc_180014BEA
0x180014a06  mov     eax, 4
0x180014a0b  lea     ecx, [rax+4]
0x180014a0e  add     rbx, 5
0x180014a12  add     rbx, rcx
0x180014a15  lea     r15, __ImageBase
0x180014a1c  jmp     loc_180014960
0x180014a21  mov     [rbp+47h+SrcStr], di
0x180014a25  xor     eax, eax
0x180014a27  mov     [rsp+110h+DestStr], ax
0x180014a2c  mov     eax, 1
0x180014a31  mov     [rsp+110h+cchDest], eax; cchDest
0x180014a35  lea     rcx, [rsp+110h+DestStr]
0x180014a3a  mov     [rsp+110h+lpDestStr], rcx; lpDestStr
0x180014a3f  mov     r9d, eax; cchSrc
0x180014a42  lea     r8, [rbp+47h+SrcStr]; lpSrcStr
0x180014a46  mov     edx, 100h; dwMapFlags
0x180014a4b  mov     ecx, 7Fh; Locale
0x180014a50  call    cs:__imp_LCMapStringW
0x180014a56  test    eax, eax
0x180014a58  jnz     loc_180014E25
0x180014a5e  movzx   edi, [rbp+47h+SrcStr]
0x180014a62  movzx   ecx, byte ptr [r15]
0x180014a66  cmp     ecx, 7Fh
0x180014a69  ja      short loc_180014A7A
0x180014a6b  lea     eax, [rcx-41h]
0x180014a6e  cmp     ax, 19h
0x180014a72  ja      short loc_180014ABB
0x180014a74  add     cx, 20h ; ' '
0x180014a78  jmp     short loc_180014ABB
0x180014a7a  mov     [rbp+47h+SrcStr], cx
0x180014a7e  xor     eax, eax
0x180014a80  mov     [rsp+110h+DestStr], ax
0x180014a85  mov     eax, 1
0x180014a8a  mov     [rsp+110h+cchDest], eax; cchDest
  ... truncated ...
```
