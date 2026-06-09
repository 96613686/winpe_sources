# SCHEMA_ATTRIBUTE::CopyString(ushort const *,ATTRIBUTE_VALUE *,CONFIG_FILE *,VALIDATION_EXCEPTION * *,ulong,int *)

- ea: `0x1800124bc`
- end: `0x180012fe3`
- name: `?CopyString@SCHEMA_ATTRIBUTE@@QEAAJPEBGPEAVATTRIBUTE_VALUE@@PEAVCONFIG_FILE@@PEAPEAVVALIDATION_EXCEPTION@@KPEAH@Z`
- size: `2855`
- prototype: `__int64 __fastcall(SCHEMA_ATTRIBUTE *this, wchar_t *String1, struct ATTRIBUTE_VALUE *, const unsigned __int16 **, struct VALIDATION_EXCEPTION **, char, int *)`
- caller_count: `4`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e6b0`
- `0x180011e94`
- `0x180035114`
- `0x1800364e8`

## callees

- `0x1800124bc`
- `0x180016aa0`
- `0x180017e90`
- `0x18001844c`
- `0x180018954`
- `0x180018e10`
- `0x1800192e0`
- `0x180019f88`
- `0x18001bdc4`
- `0x18001c250`
- `0x18001d2fc`
- `0x18001d584`
- `0x18001d5c4`
- `0x18001d640`
- `0x18001d680`
- `0x18001d6c0`
- `0x18001d700`
- `0x18001d760`
- `0x18001d7f0`
- `0x18001d830`
- `0x180025fac`
- `0x180026c3c`
- `0x18002d45c`
- `0x180036768`
- `0x18003c664`
- `0x1800478a8`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c02`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcschr` at `0x18001262f`
- `msvcrt!wcschr` at `0x18001262f`
- `msvcrt!wcsstr` at `0x18001268f`
- `msvcrt!wcsstr` at `0x18001268f`
- `msvcrt!_errno` at `0x18001286f`
- `msvcrt!_errno` at `0x1800128bf`
- `msvcrt!_errno` at `0x180012cfa`
- `msvcrt!_errno` at `0x180012d6f`
- `msvcrt!_errno` at `0x180012daa`
- `msvcrt!_errno` at `0x180012df4`
- `msvcrt!_errno` at `0x180012e3b`
- `msvcrt!_errno` at `0x180012eae`
- `msvcrt!_errno` at `0x18001286f`
- `msvcrt!_errno` at `0x1800128bf`
- `msvcrt!_errno` at `0x180012cfa`
- `msvcrt!_errno` at `0x180012d6f`
- `msvcrt!_errno` at `0x180012daa`
- `msvcrt!_errno` at `0x180012df4`
- `msvcrt!_errno` at `0x180012e3b`
- `msvcrt!_errno` at `0x180012eae`
- `msvcrt!wcstol` at `0x1800128a7`
- `msvcrt!wcstol` at `0x1800128a7`
- `msvcrt!wcstoul` at `0x180012d30`
- `msvcrt!wcstoul` at `0x180012d30`
- `msvcrt!_wcstoi64` at `0x180012de9`
- `msvcrt!_wcstoi64` at `0x180012de9`
- `msvcrt!_wcstoui64` at `0x180012e72`
- `msvcrt!_wcstoui64` at `0x180012e72`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012ac3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012acd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012ad8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012ae2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012ac3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012acd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012ad8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012ae2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012545`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001256b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012590`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800125b5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012545`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001256b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180012590`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800125b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012616`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012674`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012765`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012783`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012797`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012919`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001292f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800129b4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800129ca`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012a36`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012a4c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012b6f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012b85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012ca6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012cbc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012efe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012f14`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012616`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012674`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012765`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012783`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012797`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012919`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001292f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800129b4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800129ca`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012a36`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012a4c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012b6f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012b85`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012ca6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012cbc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012efe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012f14`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180012952`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18001296b`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180012952`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18001296b`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180012650`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800126b6`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180012650`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800126b6`

## pseudocode

```c
__int64 __fastcall SCHEMA_ATTRIBUTE::CopyString(
        SCHEMA_ATTRIBUTE *this,
        wchar_t *String1,
        struct ATTRIBUTE_VALUE *a3,
        const unsigned __int16 **a4,
        struct VALIDATION_EXCEPTION **a5,
        char a6,
        int *a7)
{
  signed int ProviderEntry; // edi
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  wchar_t *v14; // rax
  struct PROVIDER_ENTRY *v15; // r12
  va_list v16; // rbx
  const unsigned __int16 *v17; // rdx
  int v18; // r15d
  VALIDATION_EXCEPTION *v19; // rax
  VALIDATION_EXCEPTION *v20; // rax
  STRU *v21; // rcx
  DWORD v22; // ecx
  int v23; // r12d
  int v24; // ebx
  int v25; // eax
  char v26; // dl
  int v27; // ebx
  VALIDATION_EXCEPTION *v28; // rax
  VALIDATION_EXCEPTION *v29; // rax
  DWORD v30; // ecx
  int v31; // edx
  VALIDATION_EXCEPTION *v32; // rax
  VALIDATION_EXCEPTION *v33; // rax
  VALIDATION_EXCEPTION *v34; // rax
  VALIDATION_EXCEPTION *v35; // rax
  unsigned int v36; // r8d
  VALIDATION_EXCEPTION *v37; // rcx
  VALIDATION_EXCEPTION *v39; // rax
  VALIDATION_EXCEPTION *v40; // rax
  unsigned int *v41; // r12
  unsigned int v42; // r12d
  __int64 v43; // rbx
  VALIDATION_EXCEPTION *v44; // rax
  VALIDATION_EXCEPTION *v45; // rax
  DWORD v46; // ecx
  unsigned int v47; // ebx
  unsigned __int64 v48; // rcx
  wchar_t *v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r13
  unsigned __int64 v52; // rbx
  unsigned __int64 v53; // rcx
  wchar_t *v54; // rdx
  __int64 v55; // r8
  VALIDATION_EXCEPTION *v56; // rax
  VALIDATION_EXCEPTION *v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rcx
  VALIDATION_EXCEPTION *v60; // [rsp+30h] [rbp-D0h] BYREF
  int v61; // [rsp+38h] [rbp-C8h]
  int v62; // [rsp+3Ch] [rbp-C4h]
  va_list Arguments; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v65; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v66; // [rsp+54h] [rbp-ACh] BYREF
  struct VALIDATION_EXCEPTION **v67; // [rsp+58h] [rbp-A8h]
  PROVIDER_ENTRY *v68; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v69; // [rsp+68h] [rbp-98h] BYREF
  int *v70; // [rsp+70h] [rbp-90h]
  _BYTE v71[32]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+98h] [rbp-68h]
  _BYTE v73[32]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v74; // [rsp+D0h] [rbp-30h]
  _BYTE v75[32]; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t *v76; // [rsp+108h] [rbp+8h]
  _BYTE v77[32]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *String1a; // [rsp+140h] [rbp+40h]
  unsigned __int16 v79[256]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v80[256]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v81[256]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v82[256]; // [rsp+760h] [rbp+660h] BYREF

  v70 = a7;
  v67 = a5;
  v66 = 0;
  v65 = 0;
  v69 = 0;
  v60 = 0;
  memset_0(v79, 0, sizeof(v79));
  STRU::STRU((STRU *)v77, v79, 0x100u);
  memset_0(v80, 0, sizeof(v80));
  STRU::STRU((STRU *)v71, v80, 0x100u);
  memset_0(v81, 0, sizeof(v81));
  STRU::STRU((STRU *)v73, v81, 0x100u);
  memset_0(v82, 0, sizeof(v82));
  STRU::STRU((STRU *)v75, v82, 0x100u);
  EndPtr = 0;
  Arguments = 0;
  v68 = 0;
  v61 = 0;
  if ( !String1 || !a3 || !a5 )
  {
    ProviderEntry = -2147024809;
    v18 = 0;
    goto LABEL_74;
  }
  ProviderEntry = 0;
  if ( !wcsncmp_0(String1, L"[enc:", 5u) )
  {
    ProviderEntry = STRU::Copy((STRU *)v71, String1 + 5);
    if ( ProviderEntry < 0 )
      goto LABEL_162;
    v12 = wcschr(Str, 0x3Au);
    v13 = v12;
    if ( !v12 )
      goto LABEL_29;
    STRU::SetLen((STRU *)v71, v12 - Str);
    ProviderEntry = ATTRIBUTE_VALUE::SetProviderName(a3, Str);
    if ( ProviderEntry < 0 || (ProviderEntry = STRU::Copy((STRU *)v73, v13 + 1), ProviderEntry < 0) )
    {
LABEL_162:
      v18 = 0;
      goto LABEL_74;
    }
    v14 = wcsstr(v74, L":enc]");
    if ( v14 && !v14[5] )
    {
      STRU::SetLen((STRU *)v73, v14 - v74);
      if ( a4 )
      {
        ProviderEntry = CONFIG_FILE::GetProviderEntry((CONFIG_FILE *)a4, Str, &v68);
        if ( ProviderEntry >= 0 )
        {
          v15 = v68;
          v16 = (va_list)&szDomain;
          v17 = &szDomain;
          if ( a4[5] )
            v17 = a4[5];
          ProviderEntry = PROVIDER_ENTRY::DecryptValue(v68, v17, a4[13], v74, (struct STRU *)v77);
          if ( ProviderEntry < 0 )
          {
            v18 = 1;
            if ( (a6 & 8) == 0 )
            {
LABEL_74:
              if ( !v60 )
                goto LABEL_77;
              VALIDATION_EXCEPTION::DereferenceValidationException(v60);
              goto LABEL_76;
            }
            if ( *((_QWORD *)this + 3) )
              v16 = (va_list)*((_QWORD *)this + 3);
            Arguments = v16;
            v19 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
            if ( v19 )
            {
              v20 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v19);
              v60 = v20;
              if ( !v20 )
              {
LABEL_26:
                ProviderEntry = 0;
                goto LABEL_74;
              }
              STRU::Copy((VALIDATION_EXCEPTION *)((char *)v20 + 96), String1);
              v21 = (VALIDATION_EXCEPTION *)((char *)v60 + 40);
              if ( ProviderEntry == -2146893802 )
              {
                STRU::Copy(v21, L"BadKeyset");
                v22 = -1073739035;
              }
              else
              {
                STRU::Copy(v21, L"InvalidValue");
                v22 = -1073739091;
              }
              AdminFormatMessage(v22, &Arguments, (VALIDATION_EXCEPTION *)((char *)v60 + 208), 0);
              *v67 = v60;
            }
            v60 = 0;
            goto LABEL_26;
          }
          String1 = String1a;
          ATTRIBUTE_VALUE::SetProviderEntry(a3, v15);
        }
      }
      else
      {
        String1 = (wchar_t *)&szDomain;
      }
    }
  }
LABEL_29:
  v23 = 1;
  v62 = 1;
  v24 = 10;
  if ( (unsigned int)SCHEMA_ATTRIBUTE::IsTypeHexCompatible(this) && (unsigned int)IsNumberInHexFormat(String1) )
    v24 = 16;
  v25 = *((_DWORD *)this + 10);
  v26 = a6;
  switch ( v25 )
  {
    case 1:
      if ( *((char *)this + 20) >= 0 || (a6 & 0x20) == 0 )
        goto LABEL_37;
      ProviderEntry = ExpandEnvironmentVariables(String1, (struct STRU *)v75);
      if ( ProviderEntry >= 0 )
      {
        String1 = v76;
LABEL_37:
        ProviderEntry = ATTRIBUTE_VALUE::SetString(a3, String1, 0);
        goto LABEL_155;
      }
LABEL_73:
      v18 = v61;
      goto LABEL_74;
    case 2:
      *_errno() = 0;
      if ( (*((_BYTE *)this + 20) & 0x20) != 0 && !wcscmp_0(String1, L"Infinite") )
      {
        v27 = 0x7FFFFFFF;
        v23 = 0;
      }
      else
      {
        v27 = wcstol(String1, &EndPtr, v24);
        if ( v27 == 0x7FFFFFFF && (*((_BYTE *)this + 20) & 0x20) != 0 )
          v23 = 0;
      }
      if ( !*_errno() && (!EndPtr || !*EndPtr) )
      {
        ATTRIBUTE_VALUE::SetInt(a3, v27);
        goto LABEL_155;
      }
      goto LABEL_49;
    case 4:
      if ( IsStringEqualOrdinalIgnoreCase(String1, L"true") )
      {
        v31 = 1;
      }
      else
      {
        if ( !IsStringEqualOrdinalIgnoreCase(String1, L"false") )
        {
          v32 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
          if ( v32 )
          {
            v33 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v32);
            v60 = v33;
            if ( v33 )
            {
              STRU::Copy((VALIDATION_EXCEPTION *)((char *)v33 + 96), String1);
              STRU::Copy((VALIDATION_EXCEPTION *)((char *)v60 + 40), L"InvalidValue");
              v30 = -1073739081;
              goto LABEL_152;
            }
LABEL_154:
            ProviderEntry = -2147024883;
LABEL_155:
            if ( ProviderEntry >= 0 )
              goto LABEL_156;
            goto LABEL_68;
          }
LABEL_153:
          v60 = 0;
          goto LABEL_154;
        }
        v31 = 0;
      }
      ATTRIBUTE_VALUE::SetBool(a3, v31);
      goto LABEL_155;
    case 5:
      ProviderEntry = SCHEMA_ATTRIBUTE::GetStringFlagsValue(this, String1, &v65);
      if ( ProviderEntry >= 0 )
      {
        ATTRIBUTE_VALUE::SetFlags(a3, v65);
        goto LABEL_156;
      }
      v34 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
      if ( v34 )
      {
        v35 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v34);
        v60 = v35;
        if ( !v35 )
        {
LABEL_68:
          v26 = a6;
LABEL_69:
          v37 = v60;
          if ( v60 )
          {
            v60 = 0;
            *v67 = v37;
          }
          if ( (v26 & 1) != 0 )
            ProviderEntry = 0;
          goto LABEL_73;
        }
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v35 + 96), String1);
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v60 + 40), L"InvalidValue");
        v36 = -1073739078;
LABEL_67:
        SCHEMA_ATTRIBUTE::CreateInvalidEnumMessage(this, v60, v36);
        goto LABEL_68;
      }
      goto LABEL_82;
    case 6:
      ProviderEntry = SCHEMA_ATTRIBUTE::GetStringEnumValue(this, String1, &v66);
      if ( ProviderEntry >= 0 )
      {
        ATTRIBUTE_VALUE::SetEnum(a3, v66);
        goto LABEL_156;
      }
      v39 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
      if ( v39 )
      {
        v40 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v39);
        v60 = v40;
        if ( !v40 )
          goto LABEL_68;
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v40 + 96), String1);
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v60 + 40), L"InvalidValue");
        v36 = -1073739079;
        goto LABEL_67;
      }
LABEL_82:
      v60 = 0;
      goto LABEL_68;
  }
  if ( v25 != 7 )
  {
    switch ( v25 )
    {
      case 9:
        *_errno() = 0;
        if ( (*((_BYTE *)this + 20) & 0x20) != 0 && !wcscmp_0(String1, L"Infinite") )
        {
          v47 = -1;
          v23 = 0;
        }
        else
        {
          v47 = wcstoul(String1, &EndPtr, v24);
        }
        v48 = *String1;
        v49 = String1;
        if ( (_WORD)v48 )
        {
          v50 = 0x100002200LL;
          do
          {
            if ( (unsigned __int16)v48 > 0x20u )
              break;
            if ( !_bittest64(&v50, v48) )
              break;
            v48 = *++v49;
          }
          while ( (_WORD)v48 );
        }
        if ( *v49 != 45 && !*_errno() && (!EndPtr || !*EndPtr) )
        {
          ATTRIBUTE_VALUE::SetUInt(a3, v47);
          goto LABEL_155;
        }
        break;
      case 3:
        *_errno() = 0;
        if ( (*((_BYTE *)this + 20) & 0x20) != 0 && !wcscmp_0(String1, L"Infinite") )
        {
          v51 = 0x7FFFFFFFFFFFFFFFLL;
          v23 = 0;
        }
        else
        {
          v51 = _wcstoi64(String1, &EndPtr, v24);
        }
        if ( !*_errno() && (!EndPtr || !*EndPtr) )
        {
          ATTRIBUTE_VALUE::SetInt64(a3, v51);
          goto LABEL_155;
        }
LABEL_49:
        v28 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
        if ( v28 )
        {
          v29 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v28);
          v60 = v29;
          if ( v29 )
          {
            STRU::Copy((VALIDATION_EXCEPTION *)((char *)v29 + 96), String1);
            STRU::Copy((VALIDATION_EXCEPTION *)((char *)v60 + 40), L"InvalidValue");
            v30 = -1073739082;
LABEL_152:
            AdminFormatMessage(v30, &Arguments, (VALIDATION_EXCEPTION *)((char *)v60 + 208), 0);
            goto LABEL_154;
          }
          goto LABEL_154;
        }
        goto LABEL_153;
      case 10:
        *_errno() = 0;
        if ( (*((_BYTE *)this + 20) & 0x20) != 0 && !wcscmp_0(String1, L"Infinite") )
        {
          v52 = -1;
          v23 = 0;
        }
        else
        {
          v52 = _wcstoui64(String1, &EndPtr, v24);
        }
        v53 = *String1;
        v54 = String1;
        if ( (_WORD)v53 )
        {
          v55 = 0x100002200LL;
          do
          {
            if ( (unsigned __int16)v53 > 0x20u )
              break;
            if ( !_bittest64(&v55, v53) )
              break;
            v53 = *++v54;
          }
          while ( (_WORD)v53 );
        }
        if ( *v54 != 45 && !*_errno() && (!EndPtr || !*EndPtr) )
        {
          ATTRIBUTE_VALUE::SetUInt64(a3, v52);
          goto LABEL_155;
        }
        break;
      default:
        ProviderEntry = -2147024883;
        goto LABEL_69;
    }
    v56 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
    if ( v56 )
    {
      v57 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v56);
      v60 = v57;
      if ( v57 )
      {
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v57 + 96), String1);
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v60 + 40), L"InvalidValue");
        v30 = -1073739042;
        goto LABEL_152;
      }
      goto LABEL_154;
    }
    goto LABEL_153;
  }
  v41 = (unsigned int *)*((_QWORD *)this + 7);
  if ( v41 )
    v42 = *v41;
  else
    v42 = 0;
  ProviderEntry = TIMESPAN_PARSER::ParseFromString(&v69, String1, v42, (*((_DWORD *)this + 5) >> 5) & 1);
  if ( ProviderEntry < 0 )
  {
    v44 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
    if ( v44 )
    {
      v45 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v44);
      v60 = v45;
      if ( v45 )
      {
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v45 + 96), String1);
        STRU::Copy((VALIDATION_EXCEPTION *)((char *)v60 + 40), L"InvalidValue");
        if ( v42 )
          v46 = -1073739082;
        else
          v46 = -1073739083;
        AdminFormatMessage(v46, &Arguments, (VALIDATION_EXCEPTION *)((char *)v60 + 208), 0);
      }
      goto LABEL_68;
    }
    goto LABEL_82;
  }
  v43 = v69;
  ProviderEntry = ATTRIBUTE_VALUE::SetTimeSpan(a3, v69);
  if ( ProviderEntry < 0 )
    goto LABEL_73;
  if ( (*((_BYTE *)this + 20) & 0x20) != 0
    && (v43 == 0x7FFFFFFFFFFFFFFFLL
     || v42 == 1 && v43 / 10000000 == 0x7FFFFFFF
     || v42 == 2 && v43 / 600000000 == 0x7FFFFFFF) )
  {
    v23 = 0;
  }
  else
  {
    v23 = v62;
  }
LABEL_156:
  v58 = *((_QWORD *)this + 6);
  if ( !v58 )
    goto LABEL_73;
  v59 = *(_QWORD *)(v58 + 16);
  if ( !v59 )
    goto LABEL_73;
  if ( !v23 )
    goto LABEL_73;
  ProviderEntry = (*(__int64 (__fastcall **)(__int64, struct ATTRIBUTE_VALUE *, wchar_t *, VALIDATION_EXCEPTION **))(*(_QWORD *)v59 + 16LL))(
                    v59,
                    a3,
                    String1,
                    &v60);
  if ( ProviderEntry < 0 )
    goto LABEL_73;
  v18 = v61;
  if ( v60 )
  {
    *v67 = v60;
    ProviderEntry = (a6 & 2) == 0 ? 0x8007000D : 0;
LABEL_76:
    v60 = 0;
  }
LABEL_77:
  if ( v68 )
    PROVIDER_ENTRY::DereferenceProviderEntry(v68);
  if ( v70 )
    *v70 = v18;
  STRU::~STRU((STRU *)v75);
  STRU::~STRU((STRU *)v73);
  STRU::~STRU((STRU *)v71);
  STRU::~STRU((STRU *)v77);
  return (unsigned int)ProviderEntry;
}

```

## disassembly

```asm
0x1800124bc  push    rbp
0x1800124be  push    rbx
0x1800124bf  push    rsi
0x1800124c0  push    rdi
0x1800124c1  push    r12
0x1800124c3  push    r13
0x1800124c5  push    r14
0x1800124c7  push    r15
0x1800124c9  lea     rbp, [rsp-878h]
0x1800124d1  sub     rsp, 978h
0x1800124d8  mov     rax, cs:__security_cookie
0x1800124df  xor     rax, rsp
0x1800124e2  mov     [rbp+8B0h+var_50], rax
0x1800124e9  mov     rax, [rbp+8B0h+arg_30]
0x1800124f0  mov     r15, r8
0x1800124f3  mov     rbx, [rbp+8B0h+arg_20]
0x1800124fa  mov     rsi, rdx
0x1800124fd  mov     [rsp+9B0h+var_940], rax
0x180012502  mov     r14, rcx
0x180012505  xor     eax, eax
0x180012507  mov     [rsp+9B0h+var_958], rbx
0x18001250c  mov     r12d, 200h
0x180012512  mov     [rsp+9B0h+var_95C], eax
0x180012516  mov     r8d, r12d; Size
0x180012519  mov     [rsp+9B0h+var_960], eax
0x18001251d  xor     edx, edx; Val
0x18001251f  mov     [rsp+9B0h+var_948], rax
0x180012524  lea     rcx, [rbp+8B0h+var_850]; void *
0x180012528  mov     [rsp+9B0h+var_980], rax
0x18001252d  mov     r13, r9
0x180012530  call    memset_0
0x180012535  mov     edi, 100h
0x18001253a  lea     rdx, [rbp+8B0h+var_850]
0x18001253e  mov     r8d, edi
0x180012541  lea     rcx, [rbp+8B0h+var_890]
0x180012545  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001254b  mov     r8d, r12d; Size
0x18001254e  lea     rcx, [rbp+8B0h+var_650]; void *
0x180012555  xor     edx, edx; Val
0x180012557  call    memset_0
0x18001255c  mov     r8d, edi
0x18001255f  lea     rdx, [rbp+8B0h+var_650]
0x180012566  lea     rcx, [rsp+9B0h+var_938]
0x18001256b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180012571  mov     r8d, r12d; Size
0x180012574  lea     rcx, [rbp+8B0h+var_450]; void *
0x18001257b  xor     edx, edx; Val
0x18001257d  call    memset_0
0x180012582  mov     r8d, edi
0x180012585  lea     rdx, [rbp+8B0h+var_450]
0x18001258c  lea     rcx, [rbp+8B0h+var_900]
0x180012590  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180012596  mov     r8d, r12d; Size
0x180012599  lea     rcx, [rbp+8B0h+var_250]; void *
0x1800125a0  xor     edx, edx; Val
0x1800125a2  call    memset_0
0x1800125a7  mov     r8d, edi
0x1800125aa  lea     rdx, [rbp+8B0h+var_250]
0x1800125b1  lea     rcx, [rbp+8B0h+var_8C8]
0x1800125b5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800125bb  xor     eax, eax
0x1800125bd  xor     r12d, r12d
0x1800125c0  mov     [rsp+9B0h+EndPtr], rax
0x1800125c5  mov     [rsp+9B0h+Arguments], rax
0x1800125ca  mov     [rsp+9B0h+var_950], rax
0x1800125cf  mov     [rsp+9B0h+var_978], r12d
0x1800125d4  test    rsi, rsi
0x1800125d7  jz      loc_180012FD9
0x1800125dd  test    r15, r15
0x1800125e0  jz      loc_180012FD9
0x1800125e6  test    rbx, rbx
0x1800125e9  jz      loc_180012FD9
0x1800125ef  lea     r8d, [rax+5]; MaxCount
0x1800125f3  mov     rcx, rsi; String1
0x1800125f6  lea     rdx, aEnc; "[enc:"
0x1800125fd  mov     edi, r12d
0x180012600  call    wcsncmp_0
0x180012605  test    eax, eax
0x180012607  jnz     loc_1800127ED
0x18001260d  lea     rdx, [rsi+0Ah]
0x180012611  lea     rcx, [rsp+9B0h+var_938]
0x180012616  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001261c  mov     edi, eax
0x18001261e  test    eax, eax
0x180012620  js      loc_180012FC4
0x180012626  mov     rcx, [rbp+8B0h+Str]; Str
0x18001262a  lea     edx, [r12+3Ah]; Ch
0x18001262f  call    cs:__imp_wcschr
0x180012635  mov     rbx, rax
0x180012638  test    rax, rax
0x18001263b  jz      loc_1800127ED
0x180012641  mov     rdx, rax
0x180012644  lea     rcx, [rsp+9B0h+var_938]
0x180012649  sub     rdx, [rbp+8B0h+Str]
0x18001264d  sar     rdx, 1
0x180012650  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180012656  mov     rdx, [rbp+8B0h+Str]; String
0x18001265a  mov     rcx, r15; this
0x18001265d  call    ?SetProviderName@ATTRIBUTE_VALUE@@QEAAJPEBG@Z; ATTRIBUTE_VALUE::SetProviderName(ushort const *)
0x180012662  mov     edi, eax
0x180012664  test    eax, eax
0x180012666  js      loc_180012FC4
0x18001266c  lea     rdx, [rbx+2]
0x180012670  lea     rcx, [rbp+8B0h+var_900]
0x180012674  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001267a  mov     edi, eax
0x18001267c  test    eax, eax
0x18001267e  js      loc_180012FC4
0x180012684  mov     rcx, [rbp+8B0h+var_8E0]; Str
0x180012688  lea     rdx, aEnc_0; ":enc]"
0x18001268f  call    cs:__imp_wcsstr
0x180012695  test    rax, rax
0x180012698  jz      loc_1800127ED
0x18001269e  cmp     [rax+0Ah], r12w
0x1800126a3  jnz     loc_1800127ED
0x1800126a9  sub     rax, [rbp+8B0h+var_8E0]
0x1800126ad  lea     rcx, [rbp+8B0h+var_900]
0x1800126b1  sar     rax, 1
0x1800126b4  mov     edx, eax
0x1800126b6  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800126bc  test    r13, r13
0x1800126bf  jz      loc_1800127E6
0x1800126c5  mov     rdx, [rbp+8B0h+Str]; unsigned __int16 *
0x1800126c9  lea     r8, [rsp+9B0h+var_950]; struct PROVIDER_ENTRY **
0x1800126ce  mov     rcx, r13; this
0x1800126d1  call    ?GetProviderEntry@CONFIG_FILE@@QEAAJPEBGPEAPEAVPROVIDER_ENTRY@@@Z; CONFIG_FILE::GetProviderEntry(ushort const *,PROVIDER_ENTRY * *)
0x1800126d6  mov     edi, eax
0x1800126d8  test    eax, eax
0x1800126da  js      loc_1800127ED
0x1800126e0  cmp     [r13+28h], r12
0x1800126e4  lea     rax, [rbp+8B0h+var_890]
0x1800126e8  mov     r12, [rsp+9B0h+var_950]
0x1800126ed  lea     rbx, szDomain
0x1800126f4  mov     r9, [rbp+8B0h+var_8E0]; unsigned __int16 *
0x1800126f8  mov     rdx, rbx
0x1800126fb  cmovnz  rdx, [r13+28h]; unsigned __int16 *
0x180012700  mov     rcx, r12; this
0x180012703  mov     r8, [r13+68h]; unsigned __int16 *
0x180012707  mov     [rsp+9B0h+var_990], rax; struct STRU *
0x18001270c  call    ?DecryptValue@PROVIDER_ENTRY@@QEAAJPEBG00PEAVSTRU@@@Z; PROVIDER_ENTRY::DecryptValue(ushort const *,ushort const *,ushort const *,STRU *)
0x180012711  xor     r13d, r13d
0x180012714  mov     edi, eax
0x180012716  test    eax, eax
0x180012718  jns     loc_1800127D5
0x18001271e  test    [rbp+8B0h+arg_28], 8
0x180012725  lea     r15d, [r13+1]
0x180012729  jz      loc_180012A8F
0x18001272f  cmp     [r14+18h], r13
0x180012733  mov     ecx, 1E8h; Size
0x180012738  cmovnz  rbx, [r14+18h]
0x18001273d  mov     [rsp+9B0h+Arguments], rbx
0x180012742  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012747  test    rax, rax
0x18001274a  jz      short loc_1800127C8
0x18001274c  mov     rcx, rax; this
0x18001274f  call    ??0VALIDATION_EXCEPTION@@QEAA@XZ; VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(void)
0x180012754  mov     [rsp+9B0h+var_980], rax
0x180012759  test    rax, rax
0x18001275c  jz      short loc_1800127CD
0x18001275e  lea     rcx, [rax+60h]
0x180012762  mov     rdx, rsi
0x180012765  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001276b  mov     rcx, [rsp+9B0h+var_980]
0x180012770  add     rcx, 28h ; '('
0x180012774  cmp     edi, 80090016h
0x18001277a  jnz     short loc_180012790
0x18001277c  lea     rdx, aBadkeyset; "BadKeyset"
0x180012783  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012789  mov     ecx, 0C0000AE5h
0x18001278e  jmp     short loc_1800127A2
0x180012790  lea     rdx, aInvalidvalue; "InvalidValue"
0x180012797  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001279d  mov     ecx, 0C0000AADh; dwMessageId
0x1800127a2  mov     r8, [rsp+9B0h+var_980]
0x1800127a7  lea     rdx, [rsp+9B0h+Arguments]; Arguments
0x1800127ac  add     r8, 0D0h; struct STRU *
0x1800127b3  xor     r9d, r9d; struct SMALL_STRU *
0x1800127b6  call    ?AdminFormatMessage@@YAJKQEAPEBDPEAVSTRU@@PEAVSMALL_STRU@@@Z; AdminFormatMessage(ulong,char const * * const,STRU *,SMALL_STRU *)
0x1800127bb  mov     r8, [rsp+9B0h+var_958]
0x1800127c0  mov     rax, [rsp+9B0h+var_980]
0x1800127c5  mov     [r8], rax
0x1800127c8  mov     [rsp+9B0h+var_980], r13
0x1800127cd  mov     edi, r13d
0x1800127d0  jmp     loc_180012A8F
0x1800127d5  mov     rsi, [rbp+8B0h+String1]
0x1800127d9  mov     rdx, r12; struct PROVIDER_ENTRY *
0x1800127dc  mov     rcx, r15; this
0x1800127df  call    ?SetProviderEntry@ATTRIBUTE_VALUE@@QEAAXPEAVPROVIDER_ENTRY@@@Z; ATTRIBUTE_VALUE::SetProviderEntry(PROVIDER_ENTRY *)
0x1800127e4  jmp     short loc_1800127F0
0x1800127e6  lea     rsi, szDomain
0x1800127ed  xor     r13d, r13d
0x1800127f0  mov     r12d, 1
0x1800127f6  mov     rcx, r14; this
0x1800127f9  mov     [rsp+9B0h+var_974], r12d
0x1800127fe  lea     ebx, [r12+9]
0x180012803  call    ?IsTypeHexCompatible@SCHEMA_ATTRIBUTE@@QEBAHXZ; SCHEMA_ATTRIBUTE::IsTypeHexCompatible(void)
0x180012808  test    eax, eax
0x18001280a  jz      short loc_18001281C
0x18001280c  mov     rcx, rsi; unsigned __int16 *
0x18001280f  call    ?IsNumberInHexFormat@@YAHPEBG@Z; IsNumberInHexFormat(ushort const *)
0x180012814  test    eax, eax
0x180012816  lea     ecx, [rbx+6]
0x180012819  cmovnz  ebx, ecx
0x18001281c  mov     eax, [r14+28h]
0x180012820  mov     edx, dword ptr [rbp+8B0h+arg_28]
0x180012826  cmp     eax, r12d
0x180012829  jnz     short loc_180012866
0x18001282b  test    byte ptr [r14+14h], 80h
0x180012830  jz      short loc_180012851
0x180012832  test    dl, 20h
0x180012835  jz      short loc_180012851
0x180012837  lea     rdx, [rbp+8B0h+var_8C8]; struct STRU *
0x18001283b  mov     rcx, rsi; lpSrc
0x18001283e  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x180012843  mov     edi, eax
0x180012845  test    eax, eax
0x180012847  js      loc_180012A8A
0x18001284d  mov     rsi, [rbp+8B0h+var_8A8]
0x180012851  xor     r8d, r8d; int
0x180012854  mov     rdx, rsi; Src
0x180012857  mov     rcx, r15; this
0x18001285a  call    ?SetString@ATTRIBUTE_VALUE@@QEAAJPEBGH@Z; ATTRIBUTE_VALUE::SetString(ushort const *,int)
0x18001285f  mov     edi, eax
0x180012861  jmp     loc_180012F44
0x180012866  cmp     eax, 2
0x180012869  jnz     loc_18001293F
0x18001286f  call    cs:__imp__errno
0x180012875  mov     [rax], r13d
0x180012878  test    byte ptr [r14+14h], 20h
0x18001287d  jz      short loc_18001289C
0x18001287f  lea     rdx, aInfinite; "Infinite"
0x180012886  mov     rcx, rsi; String1
0x180012889  call    wcscmp_0
0x18001288e  test    eax, eax
0x180012890  jnz     short loc_18001289C
0x180012892  mov     ebx, 7FFFFFFFh
0x180012897  mov     r12d, r13d
0x18001289a  jmp     short loc_1800128BF
0x18001289c  mov     r8d, ebx; Radix
0x18001289f  lea     rdx, [rsp+9B0h+EndPtr]; EndPtr
0x1800128a4  mov     rcx, rsi; String
0x1800128a7  call    cs:__imp_wcstol
0x1800128ad  mov     ebx, eax
0x1800128af  cmp     eax, 7FFFFFFFh
0x1800128b4  jnz     short loc_1800128BF
0x1800128b6  test    byte ptr [r14+14h], 20h
0x1800128bb  cmovnz  r12d, r13d
0x1800128bf  call    cs:__imp__errno
0x1800128c5  cmp     [rax], r13d
0x1800128c8  jnz     short loc_1800128E9
0x1800128ca  mov     rax, [rsp+9B0h+EndPtr]
0x1800128cf  test    rax, rax
0x1800128d2  jz      short loc_1800128DA
0x1800128d4  cmp     [rax], r13w
0x1800128d8  jnz     short loc_1800128E9
0x1800128da  mov     edx, ebx; int
0x1800128dc  mov     rcx, r15; this
0x1800128df  call    ?SetInt@ATTRIBUTE_VALUE@@QEAAJH@Z; ATTRIBUTE_VALUE::SetInt(int)
0x1800128e4  jmp     loc_180012F44
0x1800128e9  mov     ecx, 1E8h; Size
0x1800128ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800128f3  test    rax, rax
0x1800128f6  jz      loc_180012F3A
0x1800128fc  mov     rcx, rax; this
0x1800128ff  call    ??0VALIDATION_EXCEPTION@@QEAA@XZ; VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(void)
0x180012904  mov     [rsp+9B0h+var_980], rax
0x180012909  test    rax, rax
0x18001290c  jz      loc_180012F3F
0x180012912  lea     rcx, [rax+60h]
0x180012916  mov     rdx, rsi
0x180012919  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001291f  mov     rcx, [rsp+9B0h+var_980]
0x180012924  lea     rdx, aInvalidvalue; "InvalidValue"
0x18001292b  add     rcx, 28h ; '('
0x18001292f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012935  mov     ecx, 0C0000AB6h
0x18001293a  jmp     loc_180012F1F
0x18001293f  cmp     eax, 4
0x180012942  jnz     loc_1800129DA
0x180012948  lea     rdx, aTrue; "true"
0x18001294f  mov     rcx, rsi
0x180012952  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180012958  test    al, al
0x18001295a  jz      short loc_180012961
0x18001295c  mov     edx, r12d
0x18001295f  jmp     short loc_180012977
0x180012961  lea     rdx, aFalse; "false"
0x180012968  mov     rcx, rsi
0x18001296b  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x180012971  test    al, al
0x180012973  jz      short loc_180012984
0x180012975  xor     edx, edx; int
0x180012977  mov     rcx, r15; this
0x18001297a  call    ?SetBool@ATTRIBUTE_VALUE@@QEAAJH@Z; ATTRIBUTE_VALUE::SetBool(int)
0x18001297f  jmp     loc_180012F44
0x180012984  mov     ecx, 1E8h; Size
0x180012989  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001298e  test    rax, rax
0x180012991  jz      loc_180012F3A
0x180012997  mov     rcx, rax; this
  ... truncated ...
```
