# CWbemObject::Next(long,ushort * *,tagVARIANT *,long *,long *)

- ea: `0x18002e1e0`
- end: `0x18002eb61`
- name: `?Next@CWbemObject@@UEAAJJPEAPEAGPEAUtagVARIANT@@PEAJ2@Z`
- size: `2433`
- prototype: `__int64 __usercall@<rax>(CWbemObject *__hidden this@<rcx>, int@<edx>, unsigned __int16 **@<r8>, struct tagVARIANT *@<r9>, int *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800052f0`
- `0x18000b360`
- `0x18000b900`
- `0x18000dde0`
- `0x18002e1e0`
- `0x18002ee30`
- `0x18002ee60`
- `0x18002ef94`
- `0x180037120`
- `0x18006fa4c`
- `0x180071c50`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002e8a1`
- `wbemcomn!GetMemLogObject` at `0x18002e925`
- `wbemcomn!GetMemLogObject` at `0x18002e992`
- `wbemcomn!GetMemLogObject` at `0x18002ea4f`
- `wbemcomn!GetMemLogObject` at `0x18002eaa8`
- `wbemcomn!GetMemLogObject` at `0x18002e8a1`
- `wbemcomn!GetMemLogObject` at `0x18002e925`
- `wbemcomn!GetMemLogObject` at `0x18002e992`
- `wbemcomn!GetMemLogObject` at `0x18002ea4f`
- `wbemcomn!GetMemLogObject` at `0x18002eaa8`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18002e551`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18002e6bd`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18002e551`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18002e6bd`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18002e5bf`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18002e71f`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18002e5bf`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18002e71f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e8af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e933`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e9a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ea5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e8af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e933`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e9a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ea5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eab6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002e5dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002e75e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002e7c8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002ea7f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002e5dd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002e75e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002e7c8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002ea7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e642`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e7b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e911`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e642`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e7b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e911`
- `OLEAUT32!__imp_VariantInit` at `0x18002e231`
- `OLEAUT32!__imp_VariantInit` at `0x18002e231`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemObject::Next(
        CWbemObject *this,
        int a2,
        unsigned __int16 **a3,
        struct tagVARIANT *a4,
        int *a5,
        int *a6)
{
  unsigned __int64 v10; // r8
  _QWORD *v11; // r13
  __int64 v12; // rcx
  int v13; // eax
  _DWORD *v14; // rdx
  unsigned int *v15; // r12
  __int64 v16; // rcx
  CPropertyInformation *v17; // rcx
  _DWORD *v18; // rdx
  int v19; // ecx
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rsi
  unsigned int v24; // edi
  struct CCompressedString *KnownString; // rdx
  const unsigned __int16 *v26; // rax
  int j; // esi
  const unsigned __int16 *v28; // r14
  _BYTE *v29; // r15
  int v30; // eax
  int v31; // edi
  int v32; // ecx
  int v33; // eax
  CPropertyInformation *v34; // rsi
  __int64 result; // rax
  int v36; // edi
  unsigned int v37; // edi
  CCompressedString *v38; // rax
  OLECHAR *BSTRCopy; // rdi
  int v40; // esi
  OLECHAR *v41; // rdi
  int v42; // edx
  int SystemProperty; // esi
  bool v44; // zf
  int i; // ecx
  __int64 v46; // r15
  const unsigned __int16 *v47; // rsi
  unsigned __int16 *v48; // r14
  __int64 v49; // rax
  int v50; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v52; // rax
  CMemoryLog *v53; // rax
  CMemoryLog *v54; // rax
  CMemoryLog *v55; // rax
  CMemoryLog *v56; // rax
  CMemoryLog *v57; // rax
  int v58; // [rsp+30h] [rbp-E8h] BYREF
  char pExceptionObject; // [rsp+34h] [rbp-E4h] BYREF
  char v60; // [rsp+35h] [rbp-E3h] BYREF
  char v61; // [rsp+36h] [rbp-E2h] BYREF
  BSTR v62; // [rsp+38h] [rbp-E0h]
  int v63; // [rsp+40h] [rbp-D8h]
  int v64; // [rsp+44h] [rbp-D4h]
  CPropertyInformation *v65; // [rsp+48h] [rbp-D0h]
  int v66; // [rsp+50h] [rbp-C8h]
  __int64 v67; // [rsp+58h] [rbp-C0h]
  unsigned __int16 *v68; // [rsp+60h] [rbp-B8h]
  const unsigned __int16 *v69; // [rsp+68h] [rbp-B0h]
  const unsigned __int16 *v70; // [rsp+70h] [rbp-A8h]
  char *v71; // [rsp+78h] [rbp-A0h]
  const unsigned __int16 *v72; // [rsp+80h] [rbp-98h]
  const unsigned __int16 *v73; // [rsp+88h] [rbp-90h]
  _BYTE v74[32]; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v75[32]; // [rsp+B0h] [rbp-68h] BYREF
  CWbemObject *v76; // [rsp+D0h] [rbp-48h]

  v62 = 0;
  try
  {
    v76 = this;
    (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 280LL))(this, 0);
    if ( a4 )
      VariantInit(a4);
    if ( a3 )
      *a3 = 0;
    if ( a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      return 2147749896LL;
    }
    if ( *((_DWORD *)this + 12) == 0x7FFFFFFF )
    {
      v53 = GetMemLogObject();
      CMemoryLog::Write(v53, -2147217379);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749917LL);
      }
      (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      return 2147749917LL;
    }
    v11 = (_QWORD *)(*(__int64 (__fastcall **)(CWbemObject *))(*(_QWORD *)this + 800LL))(this);
    while ( 1 )
    {
      v12 = *((int *)this + 12);
      if ( (int)v12 >= 0 )
        break;
      v41 = COleAuto::_SysAllocString((const unsigned __int16 *)(&m_awszPropNames)[-v12]);
      v62 = v41;
      if ( !v41 )
      {
        v52 = GetMemLogObject();
        CMemoryLog::Write(v52, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            2147749894LL);
        }
        (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        return 2147749894LL;
      }
      CVar::CVar((CVar *)v74);
      v42 = *((_DWORD *)this + 12);
      *((_DWORD *)this + 12) = v42 + 1;
      SystemProperty = CWbemObject::GetSystemProperty(this, -v42, (struct CVar *)v74);
      if ( SystemProperty >= 0 )
      {
        CSystemProperties::GetPropertyType(v41, a5, a6);
        if ( a4 )
          CVar::FillVariant((CVar *)v74, a4, 1);
        if ( a3 )
        {
          *a3 = v41;
        }
        else
        {
          SysFreeString(v41);
          v62 = 0;
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)SystemProperty);
        }
        CVar::~CVar((CVar *)v74);
        (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        return (unsigned int)SystemProperty;
      }
      SysFreeString(v41);
      v62 = 0;
      CVar::~CVar((CVar *)v74);
    }
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          while ( 1 )
          {
            v13 = *((_DWORD *)this + 12);
            *((_DWORD *)this + 12) = v13 + 1;
            v14 = (_DWORD *)v11[19];
            if ( v13 >= *v14 || (v15 = &v14[2 * v13 + 1]) == 0 )
            {
              (*(void (__fastcall **)(CWbemObject *, _QWORD, unsigned __int64, __int64))(*(_QWORD *)this + 288LL))(
                this,
                0,
                v10,
                1);
              return 262149;
            }
            v16 = v15[1];
            if ( (unsigned int)v16 > *(_DWORD *)(v11[26] + 4LL) )
              throw (CX_Exception *)&pExceptionObject;
            v17 = (CPropertyInformation *)(v11[25] + v16);
            v65 = v17;
            if ( (*((_BYTE *)this + 52) & 4) == 0 )
              break;
            v18 = (_DWORD *)((char *)v17 + 18);
            v10 = (unsigned __int64)v17 + *(unsigned int *)((char *)v17 + 14) + 14;
            while ( (unsigned __int64)v18 < v10 )
            {
              if ( (*v18 ^ 0x80000000) == 1 )
              {
                v17 = v65;
                goto LABEL_22;
              }
              v19 = *(_DWORD *)((char *)v18 + 5);
              v20 = v19 & 0xFFF;
              if ( (unsigned int)v20 > 0x7F )
              {
                v21 = 0;
              }
              else if ( (v19 & 0x2000) != 0 )
              {
                v21 = 4;
              }
              else
              {
                v21 = *((_DWORD *)&m_staticLengths + v20);
              }
              v18 = (_DWORD *)((char *)v18 + (unsigned int)(v21 + 4) + 5);
            }
          }
LABEL_22:
          ;
        }
        while ( (*((_BYTE *)this + 52) & 8) != 0 && (*(_DWORD *)v17 & 0x2FFF) != 0x66 );
        v58 = 0;
        (*(void (__fastcall **)(CWbemObject *, CPropertyInformation *, _QWORD, int *))(*(_QWORD *)this + 856LL))(
          this,
          v17,
          0,
          &v58);
        v22 = *((_DWORD *)this + 13) & 0x70;
        if ( v22 != 16 )
          break;
        v44 = v58 == 32;
LABEL_80:
        if ( !v44 )
          goto LABEL_26;
      }
      if ( v22 == 32 )
      {
        v44 = v58 == 0;
        goto LABEL_80;
      }
LABEL_26:
      v23 = (*(__int64 (__fastcall **)(CWbemObject *))(*(_QWORD *)this + 800LL))(this);
      v24 = *v15;
      if ( CFastHeap::IsFakeAddress(*v15) )
      {
        KnownString = CKnownStringTable::GetKnownString(v24 & 0x7FFFFFFF);
      }
      else
      {
        if ( v24 > *(_DWORD *)(*(_QWORD *)(v23 + 208) + 4LL) )
          throw (CX_Exception *)&v60;
        KnownString = (struct CCompressedString *)(*(_QWORD *)(v23 + 200) + v24);
      }
      v26 = L"__";
      if ( *(_BYTE *)KnownString == 1 )
      {
        v70 = L"__";
        v63 = 0;
        for ( i = 0; ; ++i )
        {
          v63 = i;
          if ( !*(_BYTE *)v26 && !*((_BYTE *)v26 + 1) )
            break;
          v70 = ++v26;
        }
        v46 = i;
        v67 = i;
        v47 = L"__";
        v69 = L"__";
        v48 = (unsigned __int16 *)((char *)KnownString + 1);
        v68 = (unsigned __int16 *)((char *)KnownString + 1);
        while ( 1 )
        {
          v49 = v46;
          v67 = --v46;
          if ( !v49 || !*v48 && !*v47 )
            break;
          v50 = wbem_towlower(*v48);
          v36 = v50 - wbem_towlower(*v47);
          if ( v36 )
            goto LABEL_47;
          v68 = ++v48;
          v69 = ++v47;
        }
        v36 = 0;
LABEL_47:
        v32 = *((_DWORD *)this + 13);
        v33 = v32 & 0x70;
        if ( v36 )
          goto LABEL_48;
LABEL_41:
        if ( v33 != 64 && (v32 & 0x300) == 0 && ((v33 - 16) & 0xFFFFFFEF) != 0 || (*((_BYTE *)this + 56) & 1) != 0 )
        {
          v34 = v65;
LABEL_52:
          v37 = *v15;
          if ( CFastHeap::IsFakeAddress(*v15) )
          {
            v38 = CKnownStringTable::GetKnownString(v37 & 0x7FFFFFFF);
          }
          else
          {
            if ( v37 > *(_DWORD *)(v11[26] + 4LL) )
              throw (CX_Exception *)&v61;
            v38 = (CCompressedString *)(v11[25] + v37);
          }
          BSTRCopy = CCompressedString::CreateBSTRCopy(v38);
          v62 = BSTRCopy;
          if ( BSTRCopy )
          {
            CVar::CVar((CVar *)v75);
            v40 = (*(__int64 (__fastcall **)(CWbemObject *, CPropertyInformation *, _BYTE *))(*(_QWORD *)this + 784LL))(
                    this,
                    v34,
                    v75);
            if ( v40 < 0 )
            {
              v54 = GetMemLogObject();
              CMemoryLog::Write(v54, v40);
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  39,
                  WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
                  (unsigned int)v40);
              }
              CVar::~CVar((CVar *)v75);
              (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
              return (unsigned int)v40;
            }
            else
            {
              (*(void (__fastcall **)(CWbemObject *, OLECHAR *, int *, int *))(*(_QWORD *)this + 864LL))(
                this,
                BSTRCopy,
                a5,
                a6);
              if ( a4 )
                CVar::FillVariant((CVar *)v75, a4, 1);
              if ( a3 )
              {
                *a3 = BSTRCopy;
              }
              else
              {
                SysFreeString(BSTRCopy);
                v62 = 0;
              }
              CVar::~CVar((CVar *)v75);
              (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
              return 0;
            }
          }
          else
          {
            v55 = GetMemLogObject();
            CMemoryLog::Write(v55, -2147217402);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                38,
                WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
                2147749894LL);
            }
            (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return 2147749894LL;
          }
        }
      }
      else
      {
        v73 = L"__";
        v64 = 0;
        for ( j = 0; ; ++j )
        {
          v64 = j;
          if ( !*(_BYTE *)v26 && !*((_BYTE *)v26 + 1) )
            break;
          v73 = ++v26;
        }
        v66 = j;
        v28 = L"__";
        v72 = L"__";
        v29 = (char *)KnownString + 1;
        v71 = (char *)KnownString + 1;
        while ( 1 )
        {
          v30 = j--;
          v66 = j;
          if ( !v30 || !*v29 && !*v28 )
          {
            v32 = *((_DWORD *)this + 13);
            v33 = v32 & 0x70;
            goto LABEL_41;
          }
          v31 = wbem_towlower((unsigned __int8)*v29);
          if ( wbem_towlower(*v28) != v31 )
            break;
          v71 = ++v29;
          v72 = ++v28;
        }
        v32 = *((_DWORD *)this + 13);
        v33 = v32 & 0x70;
LABEL_48:
        if ( v33 != 48 )
        {
          if ( (v32 & 0x300) == 0x100 )
          {
            if ( v58 )
            {
              v34 = v65;
              if ( (unsigned int)CPropertyInformation::IsOverriden(v65, (struct CDataTable *)(v11 + 21)) )
                goto LABEL_51;
            }
          }
          else
          {
            v34 = v65;
LABEL_51:
            if ( (*((_DWORD *)this + 13) & 0x300) != 0x200
              || !v58
              || (unsigned int)CPropertyInformation::IsOverriden(v34, (struct CDataTable *)(v11 + 21)) )
            {
              goto LABEL_52;
            }
          }
        }
      }
    }
  }
  catch ( CX_MemoryException )
  {
    *((_DWORD *)this + 12) = 0x7FFFFFFF;
    if ( v62 )
      SysFreeString(v62);
    v56 = GetMemLogObject();
    CMemoryLog::Write(v56, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    *((_DWORD *)this + 12) = 0x7FFFFFFF;
    if ( v62 )
      SysFreeString(v62);
    v57 = GetMemLogObject();
    CMemoryLog::Write(v57, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002e1e0  mov     rax, rsp
0x18002e1e3  mov     [rax+20h], r9
0x18002e1e7  mov     [rax+18h], r8
0x18002e1eb  mov     [rax+8], rcx
0x18002e1ef  push    rbx
0x18002e1f0  push    rsi
0x18002e1f1  push    rdi
0x18002e1f2  push    r12
0x18002e1f4  push    r13
0x18002e1f6  push    r14
0x18002e1f8  push    r15
0x18002e1fa  sub     rsp, 0E0h
0x18002e201  mov     r15, r9
0x18002e204  mov     r14, r8
0x18002e207  mov     edi, edx
0x18002e209  mov     rbx, rcx
0x18002e20c  xor     esi, esi
0x18002e20e  mov     [rsp+118h+var_E0], rsi
0x18002e213  mov     [rax-48h], rcx
0x18002e217  mov     rax, [rcx]
0x18002e21a  xor     edx, edx
0x18002e21c  mov     rax, [rax+118h]
0x18002e223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e228  nop
0x18002e229  test    r15, r15
0x18002e22c  jz      short loc_18002E237
0x18002e22e  mov     rcx, r15; pvarg
0x18002e231  call    cs:__imp_VariantInit
0x18002e237  test    r14, r14
0x18002e23a  jz      short loc_18002E23F
0x18002e23c  mov     [r14], rsi
0x18002e23f  test    edi, edi
0x18002e241  jnz     loc_18002E8A1
0x18002e247  cmp     dword ptr [rbx+30h], 7FFFFFFFh
0x18002e24e  jz      loc_18002E992
0x18002e254  mov     rax, [rbx]
0x18002e257  mov     rcx, rbx
0x18002e25a  mov     rax, [rax+320h]
0x18002e261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e266  mov     r13, rax
0x18002e269  movsxd  rcx, dword ptr [rbx+30h]
0x18002e26d  test    ecx, ecx
0x18002e26f  js      loc_18002E68B
0x18002e275  lea     r10, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x18002e27c  mov     r9d, 1
0x18002e282  nop     dword ptr [rax+00h]
0x18002e286  nop     word ptr [rax+rax+00000000h]
0x18002e290  mov     eax, [rbx+30h]
0x18002e293  lea     ecx, [rax+1]
0x18002e296  mov     [rbx+30h], ecx
0x18002e299  mov     rdx, [r13+98h]
0x18002e2a0  cmp     eax, [rdx]
0x18002e2a2  jge     loc_18002E4A3
0x18002e2a8  lea     eax, ds:0[rax*8]
0x18002e2af  movsxd  r12, eax
0x18002e2b2  add     r12, 4
0x18002e2b6  add     r12, rdx
0x18002e2b9  jz      loc_18002E4A3
0x18002e2bf  mov     ecx, [r12+4]
0x18002e2c4  mov     rax, [r13+0D0h]
0x18002e2cb  cmp     ecx, [rax+4]
0x18002e2ce  ja      loc_18002E653
0x18002e2d4  add     rcx, [r13+0C8h]
0x18002e2db  mov     [rsp+118h+var_D0], rcx
0x18002e2e0  test    byte ptr [rbx+34h], 4
0x18002e2e4  jz      short loc_18002E33D
0x18002e2e6  lea     rax, [rcx+0Eh]
0x18002e2ea  lea     rdx, [rax+4]
0x18002e2ee  mov     r8d, [rax]
0x18002e2f1  add     r8, rax
0x18002e2f4  cmp     rdx, r8
0x18002e2f7  jnb     short loc_18002E333
0x18002e2f9  mov     eax, [rdx]
0x18002e2fb  xor     eax, 80000000h
0x18002e300  cmp     r9d, eax
0x18002e303  jz      short loc_18002E338
0x18002e305  mov     ecx, [rdx+5]
0x18002e308  mov     eax, ecx
0x18002e30a  and     eax, 0FFFh
0x18002e30f  cmp     eax, 7Fh
0x18002e312  ja      loc_18002E7D3
0x18002e318  bt      ecx, 0Dh
0x18002e31c  jnb     loc_18002E49A
0x18002e322  mov     eax, 4
0x18002e327  lea     ecx, [rax+4]
0x18002e32a  add     rdx, 5
0x18002e32e  add     rdx, rcx
0x18002e331  jmp     short loc_18002E2F4
0x18002e333  jmp     loc_18002E290
0x18002e338  mov     rcx, [rsp+118h+var_D0]
0x18002e33d  test    byte ptr [rbx+34h], 8
0x18002e341  jz      short loc_18002E34F
0x18002e343  mov     eax, [rcx]
0x18002e345  and     eax, 2FFFh
0x18002e34a  cmp     eax, 66h ; 'f'
0x18002e34d  jnz     short loc_18002E333
0x18002e34f  mov     [rsp+118h+var_E8], esi
0x18002e353  mov     rax, [rbx]
0x18002e356  lea     r9, [rsp+118h+var_E8]
0x18002e35b  xor     r8d, r8d
0x18002e35e  mov     rdx, rcx
0x18002e361  mov     rcx, rbx
0x18002e364  mov     rax, [rax+358h]
0x18002e36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e370  mov     eax, [rbx+34h]
0x18002e373  and     eax, 70h
0x18002e376  cmp     eax, 10h
0x18002e379  jz      loc_18002E780
0x18002e37f  cmp     eax, 20h ; ' '
0x18002e382  jz      loc_18002EA26
0x18002e388  mov     rax, [rbx]
0x18002e38b  mov     rcx, rbx
0x18002e38e  mov     rax, [rax+320h]
0x18002e395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e39a  mov     rsi, rax
0x18002e39d  mov     edi, [r12]
0x18002e3a1  mov     ecx, edi; unsigned int
0x18002e3a3  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18002e3a8  test    al, al
0x18002e3aa  jnz     loc_18002E60D
0x18002e3b0  mov     rax, [rsi+0D0h]
0x18002e3b7  cmp     edi, [rax+4]
0x18002e3ba  ja      loc_18002E790
0x18002e3c0  mov     edx, edi
0x18002e3c2  add     rdx, [rsi+0C8h]
0x18002e3c9  lea     rax, asc_1800A61F8; "__"
0x18002e3d0  cmp     byte ptr [rdx], 1
0x18002e3d3  jz      loc_18002E7DA
0x18002e3d9  mov     [rsp+118h+var_90], rax
0x18002e3e1  mov     [rsp+118h+var_D4], 0
0x18002e3e9  xor     esi, esi
0x18002e3eb  mov     [rsp+118h+var_D4], esi
0x18002e3ef  cmp     byte ptr [rax], 0
0x18002e3f2  jz      short loc_18002E404
0x18002e3f4  add     rax, 2
0x18002e3f8  mov     [rsp+118h+var_90], rax
0x18002e400  inc     esi
0x18002e402  jmp     short loc_18002E3EB
0x18002e404  cmp     byte ptr [rax+1], 0
0x18002e408  jnz     short loc_18002E3F4
0x18002e40a  mov     [rsp+118h+var_C8], esi
0x18002e40e  lea     r14, asc_1800A61F8; "__"
0x18002e415  mov     [rsp+118h+var_98], r14
0x18002e41d  lea     r15, [rdx+1]
0x18002e421  mov     [rsp+118h+var_A0], r15
0x18002e426  mov     eax, esi
0x18002e428  dec     esi
0x18002e42a  mov     [rsp+118h+var_C8], esi
0x18002e42e  test    eax, eax
0x18002e430  jz      short loc_18002E476
0x18002e432  movzx   eax, byte ptr [r15]
0x18002e436  test    al, al
0x18002e438  jnz     short loc_18002E441
0x18002e43a  cmp     word ptr [r14], 0
0x18002e43f  jz      short loc_18002E476
0x18002e441  movzx   ecx, ax; unsigned __int16
0x18002e444  call    ?wbem_towlower@@YAGG@Z; wbem_towlower(ushort)
0x18002e449  movzx   edi, ax
0x18002e44c  movzx   ecx, word ptr [r14]; unsigned __int16
0x18002e450  call    ?wbem_towlower@@YAGG@Z; wbem_towlower(ushort)
0x18002e455  movzx   eax, ax
0x18002e458  cmp     eax, edi
0x18002e45a  jnz     loc_18002E630
0x18002e460  inc     r15
0x18002e463  mov     [rsp+118h+var_A0], r15
0x18002e468  add     r14, 2
0x18002e46c  mov     [rsp+118h+var_98], r14
0x18002e474  jmp     short loc_18002E426
0x18002e476  mov     ecx, [rbx+34h]
0x18002e479  mov     eax, ecx
0x18002e47b  and     eax, 70h
0x18002e47e  xor     esi, esi
0x18002e480  cmp     eax, 40h ; '@'
0x18002e483  jnz     loc_18002EA30
0x18002e489  test    byte ptr [rbx+38h], 1
0x18002e48d  jz      loc_18002E78B
0x18002e493  mov     rsi, [rsp+118h+var_D0]
0x18002e498  jmp     short loc_18002E504
0x18002e49a  mov     eax, [r10+rax*4]
0x18002e49e  jmp     loc_18002E327
0x18002e4a3  mov     rax, [rbx]
0x18002e4a6  xor     edx, edx
0x18002e4a8  mov     rcx, rbx
0x18002e4ab  mov     rax, [rax+120h]
0x18002e4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4b7  mov     eax, 40005h
0x18002e4bc  jmp     loc_18002E5FA
0x18002e4c1  xor     esi, esi
0x18002e4c3  mov     edi, esi
0x18002e4c5  mov     ecx, [rbx+34h]
0x18002e4c8  mov     eax, ecx
0x18002e4ca  and     eax, 70h
0x18002e4cd  test    edi, edi
0x18002e4cf  jz      short loc_18002E480
0x18002e4d1  cmp     eax, 30h ; '0'
0x18002e4d4  jz      loc_18002E78B
0x18002e4da  and     ecx, 300h
0x18002e4e0  cmp     ecx, 100h
0x18002e4e6  jz      loc_18002E877
0x18002e4ec  mov     rsi, [rsp+118h+var_D0]
0x18002e4f1  mov     eax, [rbx+34h]
0x18002e4f4  and     eax, 300h
0x18002e4f9  cmp     eax, 200h
0x18002e4fe  jz      loc_18002E664
0x18002e504  mov     edi, [r12]
0x18002e508  mov     ecx, edi; unsigned int
0x18002e50a  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18002e50f  test    al, al
0x18002e511  jnz     loc_18002E620
0x18002e517  mov     rax, [r13+0D0h]
0x18002e51e  cmp     edi, [rax+4]
0x18002e521  ja      loc_18002E7A1
0x18002e527  mov     eax, edi
0x18002e529  add     rax, [r13+0C8h]
0x18002e530  mov     rcx, rax; this
0x18002e533  call    ?CreateBSTRCopy@CCompressedString@@QEBAPEAGXZ; CCompressedString::CreateBSTRCopy(void)
0x18002e538  mov     rdi, rax
0x18002e53b  mov     [rsp+118h+var_E0], rax
0x18002e540  test    rax, rax
0x18002e543  jz      loc_18002EAA8
0x18002e549  lea     rcx, [rsp+118h+var_68]
0x18002e551  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18002e557  nop
0x18002e558  mov     rax, [rbx]
0x18002e55b  lea     r8, [rsp+118h+var_68]
0x18002e563  mov     rdx, rsi
0x18002e566  mov     rcx, rbx
0x18002e569  mov     rax, [rax+310h]
0x18002e570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e575  mov     esi, eax
0x18002e577  test    eax, eax
0x18002e579  js      loc_18002EA4F
0x18002e57f  mov     rax, [rbx]
0x18002e582  mov     r9, [rsp+118h+arg_28]
0x18002e58a  mov     r8, [rsp+118h+arg_20]
0x18002e592  mov     rdx, rdi
0x18002e595  mov     rcx, rbx
0x18002e598  mov     rax, [rax+360h]
0x18002e59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5a4  mov     rdx, [rsp+118h+arg_18]
0x18002e5ac  test    rdx, rdx
0x18002e5af  jz      short loc_18002E5C5
0x18002e5b1  mov     r8d, 1
0x18002e5b7  lea     rcx, [rsp+118h+var_68]
0x18002e5bf  call    cs:__imp_?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z; CVar::FillVariant(tagVARIANT *,int)
0x18002e5c5  mov     rax, [rsp+118h+arg_10]
0x18002e5cd  test    rax, rax
0x18002e5d0  jz      short loc_18002E63F
0x18002e5d2  mov     [rax], rdi
0x18002e5d5  lea     rcx, [rsp+118h+var_68]
0x18002e5dd  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18002e5e3  nop
0x18002e5e4  mov     rax, [rbx]
0x18002e5e7  xor     edx, edx
0x18002e5e9  mov     rcx, rbx
0x18002e5ec  mov     rax, [rax+120h]
0x18002e5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5f8  xor     eax, eax
0x18002e5fa  add     rsp, 0E0h
0x18002e601  pop     r15
0x18002e603  pop     r14
0x18002e605  pop     r13
0x18002e607  pop     r12
0x18002e609  pop     rdi
0x18002e60a  pop     rsi
0x18002e60b  pop     rbx
0x18002e60c  retn
0x18002e60d  btr     edi, 1Fh
0x18002e611  mov     ecx, edi; int
0x18002e613  call    ?GetKnownString@CKnownStringTable@@SAAEAVCCompressedString@@H@Z; CKnownStringTable::GetKnownString(int)
0x18002e618  mov     rdx, rax
0x18002e61b  jmp     loc_18002E3C9
0x18002e620  btr     edi, 1Fh
0x18002e624  mov     ecx, edi; int
0x18002e626  call    ?GetKnownString@CKnownStringTable@@SAAEAVCCompressedString@@H@Z; CKnownStringTable::GetKnownString(int)
0x18002e62b  jmp     loc_18002E530
0x18002e630  mov     ecx, [rbx+34h]
0x18002e633  mov     eax, ecx
0x18002e635  and     eax, 70h
0x18002e638  xor     esi, esi
0x18002e63a  jmp     loc_18002E4D1
0x18002e63f  mov     rcx, rdi; bstrString
0x18002e642  call    cs:__imp_SysFreeString
0x18002e648  mov     [rsp+118h+var_E0], 0
0x18002e651  jmp     short loc_18002E5D5
0x18002e653  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18002e65a  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18002e65f  call    _CxxThrowException_0
0x18002e664  cmp     [rsp+118h+var_E8], 0
0x18002e669  jz      loc_18002E504
0x18002e66f  lea     rdx, [r13+0A8h]; struct CDataTable *
0x18002e676  mov     rcx, rsi; this
0x18002e679  call    ?IsOverriden@CPropertyInformation@@QEAAHPEAVCDataTable@@@Z; CPropertyInformation::IsOverriden(CDataTable *)
0x18002e67e  test    eax, eax
0x18002e680  jnz     loc_18002E504
0x18002e686  jmp     loc_18002EAA1
0x18002e68b  mov     rdx, rcx
0x18002e68e  shl     rdx, 3
0x18002e692  lea     rcx, ?m_awszPropNames@@3PAPEAGA; ushort * near * m_awszPropNames
0x18002e699  sub     rcx, rdx
  ... truncated ...
```
