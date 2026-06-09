# _StrictElementCoercePrimaryType(ushort,void const *,ushort,void *,int)

- ea: `0x18000a220`
- end: `0x18000b3fe`
- name: `?_StrictElementCoercePrimaryType@@YAJGPEBXGPEAXH@Z`
- size: `4574`
- prototype: `__int64 __fastcall(unsigned __int16, const void *, unsigned __int16, void *, int)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009db0`
- `0x18000a220`

## callees

- `0x18000a220`
- `0x180024418`
- `0x18002568c`
- `0x18002d070`
- `0x18004d0ac`
- `0x18004e930`
- `0x1800525fc`
- `0x1800526e0`
- `0x180058ab4`
- `0x180058b48`
- `0x180058bdc`
- `0x180058c74`
- `0x180058d0c`
- `0x180058da0`
- `0x180058e34`
- `0x18006ed20`
- `0x18006fb98`
- `0x18006fc8c`
- `0x180088648`
- `0x1800886dc`
- `0x180088774`
- `0x18008e394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000af43`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000af43`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000a756`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000a756`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000af8f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000af8f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000a7e3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000a7e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a2d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a2d9`
- `OLEAUT32!__imp_VarI2FromR8` at `0x18000aeaa`
- `OLEAUT32!__imp_VarI2FromR8` at `0x18000aeaa`
- `OLEAUT32!__imp_VarI4FromR8` at `0x18000aecc`
- `OLEAUT32!__imp_VarI4FromR8` at `0x18000aecc`
- `OLEAUT32!__imp_VarBoolFromR8` at `0x18000ae77`
- `OLEAUT32!__imp_VarBoolFromR8` at `0x18000ae77`
- `OLEAUT32!__imp_VarBoolFromStr` at `0x18000a542`
- `OLEAUT32!__imp_VarBoolFromStr` at `0x18000a542`
- `OLEAUT32!__imp_VarUI1FromR8` at `0x18000ae99`
- `OLEAUT32!__imp_VarUI1FromR8` at `0x18000ae99`
- `OLEAUT32!__imp_VarI1FromR8` at `0x18000ae88`
- `OLEAUT32!__imp_VarI1FromR8` at `0x18000ae88`
- `OLEAUT32!__imp_VarUI2FromR8` at `0x18000aebb`
- `OLEAUT32!__imp_VarUI2FromR8` at `0x18000aebb`
- `OLEAUT32!__imp_VarUI4FromR8` at `0x18000aedd`
- `OLEAUT32!__imp_VarUI4FromR8` at `0x18000aedd`
- `OLEAUT32!__imp_VarI8FromR8` at `0x18000aeee`
- `OLEAUT32!__imp_VarI8FromR8` at `0x18000aeee`
- `OLEAUT32!__imp_VarUI8FromR8` at `0x18000aeff`
- `OLEAUT32!__imp_VarUI8FromR8` at `0x18000aeff`
- `SHCORE!__imp_GUIDFromStringW` at `0x18000a59b`
- `SHCORE!__imp_GUIDFromStringW` at `0x18000a59b`

## pseudocode

```c
__int64 __fastcall _StrictElementCoercePrimaryType(
        __int64 a1,
        FILETIME *a2,
        unsigned __int16 a3,
        struct _FILETIME *a4,
        unsigned int a5)
{
  struct _FILETIME v5; // xmm0_8
  const WCHAR *v8; // rdi
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // r12
  unsigned int v11; // r14d
  unsigned int Error; // r15d
  _WORD *v14; // r10
  unsigned __int64 v15; // rcx
  _WORD *v16; // rdx
  __int64 v17; // r8
  _WORD *v18; // rax
  __int64 v19; // r9
  __int64 v20; // r12
  GUID v21; // xmm0
  DOUBLE v22; // xmm0_8
  unsigned __int64 dwLowDateTime_low; // r9
  int v24; // ebx
  unsigned __int16 v25; // r14
  bool v26; // cc
  char v27; // al
  unsigned __int16 v28; // ax
  VARIANT_BOOL *v29; // r9
  int v30; // ecx
  struct _FILETIME v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  struct _FILETIME *v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rbx
  char v38; // cl
  bool v39; // cf
  __int16 v40; // cx
  int v41; // eax
  int v42; // ecx
  __int64 v43; // rbx
  char v44; // cl
  unsigned __int16 v45; // ax
  char v46; // al
  __int16 dwLowDateTime; // cx
  __int64 v48; // rbx
  __int16 v49; // bx
  unsigned int v50; // eax
  char v51; // al
  __int16 v52; // bx
  __int16 v53; // ax
  __int64 v54; // rbx
  __int16 v55; // bx
  __int16 v56; // bx
  __int16 v57; // ax
  __int64 v58; // rbx
  __int16 v59; // bx
  int v60; // ebx
  double v61; // xmm0_8
  __int64 v62; // rax
  __int16 v63; // cx
  __int64 v64; // rbx
  FILETIME FileTime; // [rsp+50h] [rbp-51h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-49h] BYREF
  int v67; // [rsp+68h] [rbp-39h] BYREF
  unsigned __int16 v68[32]; // [rsp+70h] [rbp-31h] BYREF

  if ( (unsigned __int16)a1 == 31 )
  {
    v8 = (const WCHAR *)*a2;
    if ( a3 == 31 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v10 = v9 + 1;
      *a4 = 0;
      if ( v9 + 1 >= v9 && is_mul_ok(v10, 2u) )
      {
        v14 = CoTaskMemAlloc(2 * v10);
        *a4 = (struct _FILETIME)v14;
        v11 = 0;
        if ( v14 )
        {
          if ( v10 > 0x7FFFFFFF )
            goto LABEL_243;
          if ( v9 < 0x7FFFFFFF )
          {
            if ( !v8 )
            {
              v8 = &Src;
              v9 = 0;
            }
            if ( v10 )
            {
              v15 = v10;
              v16 = v14;
              v17 = 0;
              do
              {
                if ( !v9 )
                  break;
                if ( !*v8 )
                  break;
                *v16++ = *v8++;
                --v9;
                ++v17;
                --v15;
              }
              while ( v15 );
              v18 = v16 - 1;
              v19 = v17 - 1;
              if ( v15 )
              {
                v18 = v16;
                v19 = v17;
              }
              *v18 = 0;
              if ( v15 )
              {
                v39 = v10 == v19;
                v20 = v10 - v19;
                if ( !v39 && v20 != 1 && (unsigned __int64)(2 * v20) > 2 )
                  memset_0(&v14[v19 + 1], 0, 2 * v20 - 2);
              }
            }
            return v11;
          }
          if ( v9 != -1 )
LABEL_243:
            *v14 = 0;
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        return (unsigned int)-2147024362;
      }
      return v11;
    }
    v25 = 21;
    switch ( a3 )
    {
      case 2u:
      case 3u:
      case 0x10u:
        v25 = 20;
        goto LABEL_40;
      case 5u:
        FileTime = 0;
        _o_wcstod(v8, &FileTime);
        v63 = *(_WORD *)FileTime.dwLowDateTime;
        if ( *(_WORD *)FileTime.dwLowDateTime )
          v5 = 0;
        *a4 = v5;
        return v63 != 0 ? 0x80028CA0 : 0;
      case 0xBu:
        v28 = MapVariantFlagsFromChangeFlags(a5);
        return (unsigned int)VarBoolFromStr(v8, 0x7Fu, v28, v29);
      case 0x11u:
      case 0x12u:
      case 0x13u:
LABEL_40:
        FileTime = 0;
        Error = _StrictElementCoercePrimaryType(a1, a2, v25, &FileTime, a5);
        if ( (Error & 0x80000000) == 0 )
          return (unsigned int)_StrictElementCoercePrimaryType(v25, &FileTime, a3, a4, a5);
        return Error;
      case 0x14u:
        return (unsigned int)StrToInt64Impl<__int64,unsigned short *>(a2, a4, a5);
      case 0x15u:
        return (unsigned int)StrToInt64Impl<unsigned __int64,unsigned short *>(a2, a4, a5);
      case 0x40u:
        Error = 0;
        v67 = 0;
        SystemTime = 0;
        if ( swscanf_s(
               v8,
               L"%hu/%hu/%hu:%hu:%hu:%hu.%hu%n",
               &SystemTime,
               &SystemTime.wMonth,
               &SystemTime.wDay,
               &SystemTime.wHour,
               &SystemTime.wMinute,
               &SystemTime.wSecond,
               &SystemTime.wMilliseconds,
               &v67) != 7 )
          goto LABEL_82;
        v64 = -1;
        do
          ++v64;
        while ( v8[v64] );
        if ( v67 == (_DWORD)v64 )
        {
          if ( !SystemTimeToFileTime(&SystemTime, a4) )
            Error = ResultFromKnownLastError();
        }
        else
        {
LABEL_82:
          FileTime.dwLowDateTime = 0;
          Error = ISO8601ToFILETIMEW(v8, a4, (enum Iso8601ParsingStage *)&FileTime);
          if ( (Error & 0x80000000) != 0 )
            goto LABEL_53;
        }
        break;
      case 0x48u:
        Error = 0;
        if ( !(unsigned int)GUIDFromStringW(v8, a4) )
          return (unsigned int)-2147024809;
        return Error;
      default:
        goto LABEL_53;
    }
  }
  else
  {
    Error = 0;
    switch ( (__int16)a1 )
    {
      case 0:
        if ( a3 == 11 )
        {
LABEL_31:
          LOWORD(a4->dwLowDateTime) = 0;
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
            case 0x12u:
              goto LABEL_31;
            case 3u:
            case 0x13u:
              a4->dwLowDateTime = 0;
              break;
            case 5u:
            case 0x14u:
            case 0x15u:
              *a4 = 0;
              break;
            case 0x10u:
            case 0x11u:
              LOBYTE(a4->dwLowDateTime) = 0;
              break;
            case 0x1Fu:
              Error = _AllocString<CTCoAllocPolicy>(a1, &_ImageBase, &Src, a4);
              break;
            case 0x48u:
              v21 = GUID_NULL;
              goto LABEL_29;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 2:
        dwLowDateTime_low = SLOWORD(a2->dwLowDateTime);
        switch ( a3 )
        {
          case 2u:
            goto LABEL_76;
          case 3u:
            goto LABEL_80;
          case 5u:
            goto LABEL_118;
          case 0xBu:
            goto LABEL_147;
          case 0x10u:
            v45 = dwLowDateTime_low + 128;
            if ( (unsigned __int16)(dwLowDateTime_low + 128) > 0xFFu )
              LOBYTE(dwLowDateTime_low) = -1;
            LOBYTE(a4->dwLowDateTime) = dwLowDateTime_low;
            return v45 > 0xFFu ? 0x80070216 : 0;
          case 0x11u:
            goto LABEL_148;
          case 0x12u:
            dwLowDateTime = -1;
            if ( (dwLowDateTime_low & 0x8000u) == 0LL )
              dwLowDateTime = a2->dwLowDateTime;
            Error = ((int)dwLowDateTime_low >> 15) & 0x80070216;
            LOWORD(a4->dwLowDateTime) = dwLowDateTime;
            return Error;
          case 0x13u:
            v41 = SLOWORD(a2->dwLowDateTime);
            if ( (dwLowDateTime_low & 0x8000u) != 0LL )
              goto LABEL_133;
            v42 = SLOWORD(a2->dwLowDateTime);
            goto LABEL_134;
          case 0x14u:
            goto LABEL_117;
          case 0x15u:
            v48 = SLOWORD(a2->dwLowDateTime);
            if ( (dwLowDateTime_low & 0x8000u) != 0LL )
              v48 = -1;
            *a4 = (struct _FILETIME)v48;
            return ((int)dwLowDateTime_low >> 15) & 0x80070216;
          case 0x1Fu:
            v34 = a5;
            v35 = a4;
            v36 = (unsigned __int16)dwLowDateTime_low;
            return (unsigned int)NumericToString<short,&long VarBstrFromI2(short,unsigned long,unsigned long,unsigned short * *)>(
                                   v36,
                                   v34,
                                   v35);
          default:
            goto LABEL_53;
        }
      case 3:
        dwLowDateTime_low = (int)a2->dwLowDateTime;
        if ( a3 == 19 )
        {
          v30 = -1;
          if ( (dwLowDateTime_low & 0x80000000) == 0LL )
            v30 = a2->dwLowDateTime;
          Error = ((int)dwLowDateTime_low >> 31) & 0x80070216;
          a4->dwLowDateTime = v30;
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
              v52 = -1;
              if ( (unsigned int)(dwLowDateTime_low + 0x8000) > 0xFFFF )
                Error = -2147024362;
              else
                v52 = a2->dwLowDateTime;
              LOWORD(a4->dwLowDateTime) = v52;
              break;
            case 3u:
              goto LABEL_80;
            case 5u:
              goto LABEL_118;
            case 0xBu:
              goto LABEL_165;
            case 0x10u:
              v50 = dwLowDateTime_low + 128;
              if ( (unsigned int)(dwLowDateTime_low + 128) > 0xFF )
                LOBYTE(dwLowDateTime_low) = -1;
              LOBYTE(a4->dwLowDateTime) = dwLowDateTime_low;
              if ( v50 > 0xFF )
                Error = -2147024362;
              break;
            case 0x11u:
              v51 = a2->dwLowDateTime;
              if ( (unsigned int)dwLowDateTime_low > 0xFF )
                v51 = -1;
              LOBYTE(a4->dwLowDateTime) = v51;
              if ( (unsigned int)dwLowDateTime_low > 0xFF )
                Error = -2147024362;
              break;
            case 0x12u:
              v53 = -1;
              if ( (unsigned int)dwLowDateTime_low > 0xFFFF )
                Error = -2147024362;
              else
                v53 = a2->dwLowDateTime;
              LOWORD(a4->dwLowDateTime) = v53;
              break;
            case 0x14u:
              goto LABEL_117;
            case 0x15u:
              v54 = (int)a2->dwLowDateTime;
              if ( (dwLowDateTime_low & 0x80000000) != 0LL )
                v54 = -1;
              Error = ((int)dwLowDateTime_low >> 31) & 0x80070216;
              *a4 = (struct _FILETIME)v54;
              break;
            case 0x1Fu:
              Error = NumericToString<long,&long VarBstrFromI4(long,unsigned long,unsigned long,unsigned short * *)>(
                        (unsigned int)dwLowDateTime_low,
                        a5,
                        a4);
              break;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 5:
        v22 = *(double *)a2;
        if ( a3 == 5 )
        {
          *(DOUBLE *)a4 = v22;
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
              Error = VarI2FromR8(v22, (SHORT *)a4);
              break;
            case 3u:
              Error = VarI4FromR8(v22, (LONG *)a4);
              break;
            case 0xBu:
              Error = VarBoolFromR8(v22, (VARIANT_BOOL *)a4);
              break;
            case 0x10u:
              Error = VarI1FromR8(v22, (CHAR *)a4);
              break;
            case 0x11u:
              Error = VarUI1FromR8(v22, (BYTE *)a4);
              break;
            case 0x12u:
              Error = VarUI2FromR8(v22, (USHORT *)a4);
              break;
            case 0x13u:
              Error = VarUI4FromR8(v22, (ULONG *)a4);
              break;
            case 0x14u:
              Error = VarI8FromR8(v22, (LONG64 *)a4);
              break;
            case 0x15u:
              Error = VarUI8FromR8(v22, (ULONG64 *)a4);
              break;
            case 0x1Fu:
              Error = _PropvarStrFromR8(v22, a5, (unsigned __int16 **)a4);
              break;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 11:
        dwLowDateTime_low = SLOWORD(a2->dwLowDateTime);
        if ( a3 == 11 )
          goto LABEL_76;
        if ( a3 != 31 )
        {
          switch ( a3 )
          {
            case 2u:
            case 0x12u:
              goto LABEL_76;
            case 3u:
            case 0x13u:
              goto LABEL_80;
            case 5u:
              goto LABEL_118;
            case 0x10u:
            case 0x11u:
              goto LABEL_43;
            case 0x14u:
            case 0x15u:
              goto LABEL_117;
            default:
              goto LABEL_53;
          }
        }
        v34 = a5;
        v35 = a4;
        v36 = (unsigned __int16)dwLowDateTime_low;
        if ( (a5 & 2) != 0 )
          return (unsigned int)NumericToString<short,&long VarBstrFromBool(short,unsigned long,unsigned long,unsigned short * *)>(
                                 (unsigned __int16)dwLowDateTime_low,
                                 a5,
                                 a4);
        else
          return (unsigned int)NumericToString<short,&long VarBstrFromI2(short,unsigned long,unsigned long,unsigned short * *)>(
                                 v36,
                                 v34,
                                 v35);
      case 16:
        dwLowDateTime_low = SLOBYTE(a2->dwLowDateTime);
        switch ( a3 )
        {
          case 2u:
            goto LABEL_76;
          case 3u:
            goto LABEL_80;
          case 5u:
            goto LABEL_118;
          case 0xBu:
            goto LABEL_124;
          case 0x10u:
            goto LABEL_43;
          case 0x11u:
            v38 = -1;
            if ( (dwLowDateTime_low & 0x80u) == 0LL )
              v38 = a2->dwLowDateTime;
            Error = ((int)dwLowDateTime_low >> 7) & 0x80070216;
            LOBYTE(a4->dwLowDateTime) = v38;
            break;
          case 0x12u:
            if ( (dwLowDateTime_low & 0x80u) != 0LL )
              v40 = -1;
            else
              v40 = SLOBYTE(a2->dwLowDateTime);
            LOWORD(a4->dwLowDateTime) = v40;
            Error = ((int)dwLowDateTime_low >> 7) & 0x80070216;
            break;
          case 0x13u:
            v41 = SLOBYTE(a2->dwLowDateTime);
            if ( (dwLowDateTime_low & 0x80u) != 0LL )
LABEL_133:
              v42 = -1;
            else
              v42 = SLOBYTE(a2->dwLowDateTime);
LABEL_134:
            Error = (v41 >> 31) & 0x80070216;
            a4->dwLowDateTime = v42;
            break;
          case 0x14u:
            goto LABEL_117;
          case 0x15u:
            v43 = SLOBYTE(a2->dwLowDateTime);
            if ( (dwLowDateTime_low & 0x80u) != 0LL )
              v43 = -1;
            *a4 = (struct _FILETIME)v43;
            Error = ((int)dwLowDateTime_low >> 7) & 0x80070216;
            break;
          case 0x1Fu:
            Error = NumericToString<char,&long VarBstrFromI1(char,unsigned long,unsigned long,unsigned short * *)>(
                      (unsigned __int8)dwLowDateTime_low,
                      a5,
                      a4);
            break;
          default:
            goto LABEL_53;
        }
        return Error;
      case 17:
        dwLowDateTime_low = LOBYTE(a2->dwLowDateTime);
        if ( a3 == 17 )
        {
LABEL_43:
          LOBYTE(a4->dwLowDateTime) = dwLowDateTime_low;
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
            case 0x12u:
              goto LABEL_76;
            case 3u:
            case 0x13u:
              goto LABEL_80;
            case 5u:
              goto LABEL_118;
            case 0xBu:
LABEL_124:
              v39 = (_BYTE)dwLowDateTime_low != 0;
              goto LABEL_126;
            case 0x10u:
              v44 = -1;
              if ( (unsigned __int8)dwLowDateTime_low > 0x7Fu )
                Error = -2147024362;
              else
                v44 = a2->dwLowDateTime;
              LOBYTE(a4->dwLowDateTime) = v44;
              break;
            case 0x14u:
            case 0x15u:
              goto LABEL_117;
            case 0x1Fu:
              Error = NumericToString<unsigned char,&long VarBstrFromUI1(unsigned char,unsigned long,unsigned long,unsigned short * *)>(
                        (unsigned __int8)dwLowDateTime_low,
                        a5,
                        a4);
              break;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 18:
        dwLowDateTime_low = LOWORD(a2->dwLowDateTime);
        if ( a3 == 16 )
        {
          v26 = (unsigned __int16)dwLowDateTime_low <= 0x7Fu;
          goto LABEL_46;
        }
        switch ( a3 )
        {
          case 2u:
            v49 = -1;
            if ( (unsigned __int16)dwLowDateTime_low <= 0x7FFFu )
              v49 = a2->dwLowDateTime;
            LOWORD(a4->dwLowDateTime) = v49;
            Error = (unsigned __int16)dwLowDateTime_low > 0x7FFFu ? 0x80070216 : 0;
            break;
          case 3u:
          case 0x13u:
            goto LABEL_80;
          case 5u:
LABEL_118:
            *(double *)a4 = (double)(int)dwLowDateTime_low;
            break;
          case 0xBu:
LABEL_147:
            v39 = (_WORD)dwLowDateTime_low != 0;
            goto LABEL_126;
          case 0x11u:
LABEL_148:
            v46 = dwLowDateTime_low;
            if ( (unsigned __int16)dwLowDateTime_low > 0xFFu )
              v46 = -1;
            LOBYTE(a4->dwLowDateTime) = v46;
            Error = (unsigned __int16)dwLowDateTime_low > 0xFFu ? 0x80070216 : 0;
            break;
          case 0x12u:
            goto LABEL_76;
          case 0x14u:
          case 0x15u:
            goto LABEL_117;
          case 0x1Fu:
            Error = NumericToString<unsigned short,&long VarBstrFromUI2(unsigned short,unsigned long,unsigned long,unsigned short * *)>(
                      (unsigned __int16)dwLowDateTime_low,
                      a5,
                      a4);
            break;
          default:
            goto LABEL_53;
        }
        return Error;
      case 19:
        dwLowDateTime_low = a2->dwLowDateTime;
        if ( a3 == 3 )
        {
          v24 = -1;
          if ( (unsigned int)dwLowDateTime_low > 0x7FFFFFFF )
            Error = -2147024362;
          else
            v24 = a2->dwLowDateTime;
          a4->dwLowDateTime = v24;
        }
        else if ( a3 == 16 )
        {
          v26 = (unsigned int)dwLowDateTime_low <= 0x7F;
LABEL_46:
          v27 = dwLowDateTime_low;
          if ( !v26 )
            v27 = -1;
LABEL_48:
          LOBYTE(a4->dwLowDateTime) = v27;
LABEL_49:
          if ( !v26 )
            return (unsigned int)-2147024362;
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
              v55 = -1;
              v26 = (unsigned int)dwLowDateTime_low <= 0x7FFF;
              if ( (unsigned int)dwLowDateTime_low <= 0x7FFF )
                v55 = a2->dwLowDateTime;
              LOWORD(a4->dwLowDateTime) = v55;
              goto LABEL_49;
            case 5u:
              goto LABEL_193;
            case 0xBu:
LABEL_165:
              v39 = (_DWORD)dwLowDateTime_low != 0;
              goto LABEL_126;
            case 0x11u:
              v27 = a2->dwLowDateTime;
              v26 = (unsigned int)dwLowDateTime_low <= 0xFF;
              if ( (unsigned int)dwLowDateTime_low > 0xFF )
                v27 = -1;
              goto LABEL_48;
            case 0x12u:
              if ( (unsigned int)dwLowDateTime_low > 0xFFFF )
              {
                Error = -2147024362;
                LOWORD(dwLowDateTime_low) = -1;
              }
              goto LABEL_76;
            case 0x13u:
              goto LABEL_80;
            case 0x14u:
            case 0x15u:
              goto LABEL_117;
            case 0x1Fu:
              Error = NumericToString<unsigned long,&long VarBstrFromUI4(unsigned long,unsigned long,unsigned long,unsigned short * *)>(
                        (unsigned int)dwLowDateTime_low,
                        a5,
                        a4);
              break;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 20:
        dwLowDateTime_low = (unsigned __int64)*a2;
        if ( a3 == 3 )
        {
          if ( dwLowDateTime_low + 0x80000000 > 0xFFFFFFFF )
          {
            Error = -2147024362;
            LODWORD(dwLowDateTime_low) = -1;
          }
LABEL_80:
          a4->dwLowDateTime = dwLowDateTime_low;
        }
        else if ( a3 == 19 )
        {
          if ( dwLowDateTime_low > 0xFFFFFFFF )
          {
            Error = -2147024362;
            LODWORD(dwLowDateTime_low) = -1;
          }
          a4->dwLowDateTime = dwLowDateTime_low;
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
              v26 = dwLowDateTime_low + 0x8000 <= 0xFFFF;
              v56 = -1;
              if ( dwLowDateTime_low + 0x8000 <= 0xFFFF )
                v56 = (__int16)*a2;
              LOWORD(a4->dwLowDateTime) = v56;
              goto LABEL_49;
            case 5u:
LABEL_193:
              *(double *)a4 = (double)(int)dwLowDateTime_low;
              break;
            case 0xBu:
              goto LABEL_125;
            case 0x10u:
              v26 = dwLowDateTime_low + 128 <= 0xFF;
              if ( dwLowDateTime_low + 128 > 0xFF )
                LOBYTE(dwLowDateTime_low) = -1;
              LOBYTE(a4->dwLowDateTime) = dwLowDateTime_low;
              goto LABEL_49;
            case 0x11u:
              goto LABEL_92;
            case 0x12u:
              v26 = dwLowDateTime_low <= 0xFFFF;
              v57 = -1;
              if ( dwLowDateTime_low <= 0xFFFF )
                v57 = (__int16)*a2;
              LOWORD(a4->dwLowDateTime) = v57;
              goto LABEL_49;
            case 0x14u:
              goto LABEL_117;
            case 0x15u:
              v58 = -1;
              if ( (dwLowDateTime_low & 0x8000000000000000uLL) != 0LL )
                Error = -2147024362;
              else
                v58 = (__int64)*a2;
              *a4 = (struct _FILETIME)v58;
              break;
            case 0x1Fu:
              Error = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))NumericToString<__int64,&long VarBstrFromI8(__int64,unsigned long,unsigned long,unsigned short * *)>)(
                        *a2,
                        a5,
                        a4);
              break;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 21:
        dwLowDateTime_low = (unsigned __int64)*a2;
        if ( a3 == 19 )
        {
          return (unsigned int)ULongLongToULong((unsigned __int64)*a2, (unsigned int *)a4);
        }
        else if ( a3 == 18 )
        {
          if ( dwLowDateTime_low <= 0xFFFF )
          {
LABEL_76:
            LOWORD(a4->dwLowDateTime) = dwLowDateTime_low;
          }
          else
          {
            Error = -2147024362;
            LOWORD(a4->dwLowDateTime) = -1;
          }
        }
        else
        {
          switch ( a3 )
          {
            case 2u:
              v59 = -1;
              v26 = dwLowDateTime_low <= 0x7FFF;
              if ( dwLowDateTime_low <= 0x7FFF )
                v59 = (__int16)*a2;
              LOWORD(a4->dwLowDateTime) = v59;
              goto LABEL_49;
            case 3u:
              v26 = dwLowDateTime_low <= 0x7FFFFFFF;
              v60 = -1;
              if ( dwLowDateTime_low <= 0x7FFFFFFF )
                v60 = (int)*a2;
              a4->dwLowDateTime = v60;
              goto LABEL_49;
            case 5u:
              if ( (dwLowDateTime_low & 0x8000000000000000uLL) != 0LL )
              {
                v62 = *(_QWORD *)a2 & 1LL | (*(unsigned __int64 *)a2 >> 1);
                v61 = (double)(int)v62 + (double)(int)v62;
              }
              else
              {
                v61 = (double)(int)dwLowDateTime_low;
              }
              *(double *)a4 = v61;
              break;
            case 0xBu:
LABEL_125:
              v39 = dwLowDateTime_low != 0;
LABEL_126:
              LOWORD(a4->dwLowDateTime) = -v39;
              break;
            case 0x10u:
              v26 = dwLowDateTime_low <= 0x7F;
              goto LABEL_46;
            case 0x11u:
LABEL_92:
              v27 = dwLowDateTime_low;
              v26 = dwLowDateTime_low <= 0xFF;
              if ( dwLowDateTime_low <= 0xFF )
                goto LABEL_48;
              LOBYTE(a4->dwLowDateTime) = -1;
              Error = -2147024362;
              break;
            case 0x14u:
              v37 = -1;
              if ( dwLowDateTime_low > 0x7FFFFFFFFFFFFFFFLL )
                Error = -2147024362;
              else
                v37 = (__int64)*a2;
              *a4 = (struct _FILETIME)v37;
              break;
            case 0x15u:
LABEL_117:
              *a4 = (struct _FILETIME)dwLowDateTime_low;
              break;
            case 0x1Fu:
              Error = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))NumericToString<unsigned __int64,&long VarBstrFromUI8(unsigned __int64,unsigned long,unsigned long,unsigned short * *)>)(
                        *a2,
                        a5,
                        a4);
              break;
            default:
              goto LABEL_53;
          }
        }
        return Error;
      case 64:
        v31 = *a2;
        FileTime = *a2;
        if ( a3 == 31 )
        {
          SystemTime = 0;
          if ( FileTimeToSystemTime(&FileTime, &SystemTime)
            || (Error = ResultFromKnownLastError(), (Error & 0x80000000) == 0) )
          {
            Error = StringCchPrintfW(
                      v68,
                      0x20u,
                      L"%04u/%02u/%02u:%02u:%02u:%02u.%03u",
                      SystemTime.wYear,
                      SystemTime.wMonth,
                      SystemTime.wDay,
                      SystemTime.wHour,
                      SystemTime.wMinute,
                      SystemTime.wSecond,
                      SystemTime.wMilliseconds,
                      FileTime);
            if ( (Error & 0x80000000) == 0 )
              Error = _AllocString<CTCoAllocPolicy>(v33, v32, v68, a4);
          }
        }
        else
        {
          if ( a3 != 64 )
            goto LABEL_53;
          *a4 = v31;
        }
        break;
      case 72:
        v21 = *(GUID *)&a2->dwLowDateTime;
        SystemTime = *(_SYSTEMTIME *)&a2->dwLowDateTime;
        if ( a3 == 72 )
        {
LABEL_29:
          *(GUID *)&a4->dwLowDateTime = v21;
        }
        else if ( a3 == 31 )
        {
          Error = StringFromCLSID((const IID *const)&SystemTime, (LPOLESTR *)a4);
        }
        else
        {
LABEL_53:
          Error = -2147316576;
        }
        break;
      default:
        goto LABEL_53;
    }
  }
  return Error;
}

```

## disassembly

```asm
0x18000a220  push    rbp
0x18000a222  push    rbx
0x18000a223  push    rsi
0x18000a224  push    rdi
0x18000a225  push    r14
0x18000a227  push    r15
0x18000a229  lea     rbp, [rsp-27h]
0x18000a22e  sub     rsp, 0C8h
0x18000a235  mov     rax, cs:__security_cookie
0x18000a23c  xor     rax, rsp
0x18000a23f  mov     [rbp+4Fh+var_40], rax
0x18000a243  movzx   r11d, cx
0x18000a247  mov     rsi, r9
0x18000a24a  movzx   ebx, r8w
0x18000a24e  mov     r10, rdx
0x18000a251  mov     eax, r11d
0x18000a254  cmp     r11d, 1Fh
0x18000a258  jnz     loc_18000A39A
0x18000a25e  mov     rdi, [rdx]
0x18000a261  mov     eax, ebx
0x18000a263  cmp     ebx, r11d
0x18000a266  jnz     loc_18000A43B
0x18000a26c  mov     [rsp+0F0h+var_30], r12
0x18000a274  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a27b  nop     dword ptr [rax+rax+00h]
0x18000a280  inc     rbx
0x18000a283  cmp     word ptr [rdi+rbx*2], 0
0x18000a288  jnz     short loc_18000A280
0x18000a28a  xor     r15d, r15d
0x18000a28d  lea     r12, [rbx+1]
0x18000a291  mov     [r9], r15
0x18000a294  cmp     r12, rbx
0x18000a297  jnb     short loc_18000A2C9
0x18000a299  mov     r14d, 80070216h
0x18000a29f  mov     r12, [rsp+0F0h+var_30]
0x18000a2a7  mov     r15d, r14d
0x18000a2aa  mov     eax, r15d
0x18000a2ad  mov     rcx, [rbp+4Fh+var_40]
0x18000a2b1  xor     rcx, rsp; StackCookie
0x18000a2b4  call    __security_check_cookie
0x18000a2b9  add     rsp, 0C8h
0x18000a2c0  pop     r15
0x18000a2c2  pop     r14
0x18000a2c4  pop     rdi
0x18000a2c5  pop     rsi
0x18000a2c6  pop     rbx
0x18000a2c7  pop     rbp
0x18000a2c8  retn
0x18000a2c9  mov     eax, 2
0x18000a2ce  mul     r12
0x18000a2d1  test    rdx, rdx
0x18000a2d4  jnz     short loc_18000A299
0x18000a2d6  mov     rcx, rax; cb
0x18000a2d9  call    cs:__imp_CoTaskMemAlloc
0x18000a2df  mov     r10, rax
0x18000a2e2  mov     [rsi], rax
0x18000a2e5  test    r10, r10
0x18000a2e8  mov     r14d, r15d
0x18000a2eb  mov     eax, 8007000Eh
0x18000a2f0  cmovz   r14d, eax
0x18000a2f4  jz      short loc_18000A29F
0x18000a2f6  cmp     r12, 7FFFFFFFh
0x18000a2fd  ja      loc_18000AFB3
0x18000a303  cmp     rbx, 7FFFFFFFh
0x18000a30a  jnb     loc_18000AFAA
0x18000a310  test    rdi, rdi
0x18000a313  jz      loc_18000AFBC
0x18000a319  test    r12, r12
0x18000a31c  jz      short loc_18000A29F
0x18000a31e  mov     rcx, r12
0x18000a321  mov     rdx, r10
0x18000a324  mov     r8, r15
0x18000a327  test    rbx, rbx
0x18000a32a  jz      short loc_18000A34B
0x18000a32c  movzx   eax, word ptr [rdi]
0x18000a32f  test    ax, ax
0x18000a332  jz      short loc_18000A34B
0x18000a334  mov     [rdx], ax
0x18000a337  add     rdi, 2
0x18000a33b  add     rdx, 2
0x18000a33f  dec     rbx
0x18000a342  inc     r8
0x18000a345  sub     rcx, 1
0x18000a349  jnz     short loc_18000A327
0x18000a34b  test    rcx, rcx
0x18000a34e  lea     rax, [rdx-2]
0x18000a352  lea     r9, [r8-1]
0x18000a356  cmovnz  rax, rdx
0x18000a35a  cmovnz  r9, r8
0x18000a35e  mov     [rax], r15w
0x18000a362  jz      loc_18000A29F
0x18000a368  sub     r12, r9
0x18000a36b  cmp     r12, 1
0x18000a36f  jbe     loc_18000A29F
0x18000a375  lea     r8, [r12+r12]
0x18000a379  cmp     r8, 2
0x18000a37d  jbe     loc_18000A29F
0x18000a383  inc     r9
0x18000a386  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000a38a  xor     edx, edx; Val
0x18000a38c  lea     rcx, [r10+r9*2]; void *
0x18000a390  call    memset_0
0x18000a395  jmp     loc_18000A29F
0x18000a39a  cmp     eax, 48h; switch 73 cases
0x18000a39d  ja      def_18000A3C0; jumptable 000000018000A3C0 default case, cases 1,4,6-10,12-15,22-63,65-71
0x18000a3a3  lea     rdx, __ImageBase
0x18000a3aa  xor     r15d, r15d
0x18000a3ad  movzx   eax, ds:(byte_18000B004 - 180000000h)[rdx+r11]
0x18000a3b6  mov     ecx, ds:(jpt_18000A3C0 - 180000000h)[rdx+rax*4]
0x18000a3bd  add     rcx, rdx
0x18000a3c0  jmp     rcx; switch jump
0x18000a3c2  movups  xmm0, xmmword ptr [r10]; jumptable 000000018000A3C0 case 72
0x18000a3c6  movups  xmmword ptr [rbp+4Fh+SystemTime.wYear], xmm0
0x18000a3ca  cmp     ebx, 48h ; 'H'
0x18000a3cd  jnz     loc_18000A7D3
0x18000a3d3  movups  xmmword ptr [r9], xmm0
0x18000a3d7  jmp     loc_18000A2AA
0x18000a3dc  mov     eax, ebx; jumptable 000000018000A3C0 case 0
0x18000a3de  cmp     ebx, 0Bh
0x18000a3e1  jnz     loc_18000A919
0x18000a3e7  mov     [r9], r15w; jumptable 000000018000A939 cases 2,18
0x18000a3eb  jmp     loc_18000A2AA
0x18000a3f0  movsd   xmm0, qword ptr [r10]; jumptable 000000018000A3C0 case 5
0x18000a3f5  mov     eax, ebx
0x18000a3f7  cmp     ebx, 5
0x18000a3fa  jnz     loc_18000A4F2
0x18000a400  movsd   qword ptr [r9], xmm0
0x18000a405  jmp     loc_18000A2AA
0x18000a40a  mov     r9d, [r10]; jumptable 000000018000A3C0 case 19
0x18000a40d  mov     eax, ebx
0x18000a40f  cmp     ebx, 3
0x18000a412  jnz     loc_18000A4CE
0x18000a418  cmp     r9d, 7FFFFFFFh
0x18000a41f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a426  mov     r14d, 80070216h
0x18000a42c  cmovbe  ebx, r9d
0x18000a430  cmova   r15d, r14d
0x18000a434  mov     [rsi], ebx
0x18000a436  jmp     loc_18000A2AA
0x18000a43b  add     eax, 0FFFFFFFEh; switch 71 cases
0x18000a43e  cmp     eax, 46h
0x18000a441  ja      def_18000A3C0; jumptable 000000018000A3C0 default case, cases 1,4,6-10,12-15,22-63,65-71
0x18000a447  lea     rdx, __ImageBase
0x18000a44e  cdqe
0x18000a450  mov     r14d, 15h
0x18000a456  movzx   eax, ds:(byte_18000B074 - 180000000h)[rdx+rax]
0x18000a45e  mov     ecx, ds:(jpt_18000A468 - 180000000h)[rdx+rax*4]
0x18000a465  add     rcx, rdx
0x18000a468  jmp     rcx; switch jump
0x18000a46a  mov     edi, [rbp+4Fh+arg_20]; jumptable 000000018000A468 cases 17-19
0x18000a46d  lea     r9, [rbp+4Fh+FileTime]; void *
0x18000a471  xor     r15d, r15d
0x18000a474  mov     [rsp+0F0h+var_D0], edi; int
0x18000a478  movzx   r8d, r14w; unsigned __int16
0x18000a47c  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], r15
0x18000a480  mov     rdx, r10; void *
0x18000a483  movzx   ecx, r11w; unsigned __int16
0x18000a487  call    ?_StrictElementCoercePrimaryType@@YAJGPEBXGPEAXH@Z; _StrictElementCoercePrimaryType(ushort,void const *,ushort,void *,int)
0x18000a48c  mov     r15d, eax
0x18000a48f  test    eax, eax
0x18000a491  js      loc_18000A2AA
0x18000a497  mov     r9, rsi; void *
0x18000a49a  mov     [rsp+0F0h+var_D0], edi; int
0x18000a49e  movzx   r8d, bx; unsigned __int16
0x18000a4a2  lea     rdx, [rbp+4Fh+FileTime]; void *
0x18000a4a6  movzx   ecx, r14w; unsigned __int16
0x18000a4aa  call    ?_StrictElementCoercePrimaryType@@YAJGPEBXGPEAXH@Z; _StrictElementCoercePrimaryType(ushort,void const *,ushort,void *,int)
0x18000a4af  mov     r15d, eax
0x18000a4b2  jmp     loc_18000A2AA
0x18000a4b7  movzx   r9d, byte ptr [r10]; jumptable 000000018000A3C0 case 17
0x18000a4bb  mov     eax, ebx
0x18000a4bd  cmp     ebx, 11h
0x18000a4c0  jnz     loc_18000A70E
0x18000a4c6  mov     [rsi], r9b; jumptable 000000018000A98B cases 16,17
0x18000a4c9  jmp     loc_18000A2AA
0x18000a4ce  cmp     eax, 10h
0x18000a4d1  jnz     loc_18000A613
0x18000a4d7  cmp     r9d, 7Fh
0x18000a4db  movzx   eax, r9b
0x18000a4df  ja      short loc_18000A52A
0x18000a4e1  mov     [rsi], al
0x18000a4e3  mov     r14d, 80070216h
0x18000a4e9  cmova   r15d, r14d
0x18000a4ed  jmp     loc_18000A2AA
0x18000a4f2  add     eax, 0FFFFFFFEh; switch 30 cases
0x18000a4f5  cmp     eax, 1Dh
0x18000a4f8  jbe     loc_18000AE5E
0x18000a4fe  mov     r15d, 80028CA0h; jumptable 000000018000A3C0 default case, cases 1,4,6-10,12-15,22-63,65-71
0x18000a504  jmp     loc_18000A2AA
0x18000a509  mov     r9, [r10]; jumptable 000000018000A3C0 case 21
0x18000a50c  mov     eax, ebx
0x18000a50e  cmp     ebx, 13h
0x18000a511  jnz     loc_18000A5EE
0x18000a517  mov     rdx, rsi; unsigned int *
0x18000a51a  mov     rcx, r9; unsigned __int64
0x18000a51d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000a522  mov     r15d, eax
0x18000a525  jmp     loc_18000A2AA
0x18000a52a  mov     al, 0FFh
0x18000a52c  jmp     short loc_18000A4E1
0x18000a52e  mov     ecx, [rbp+4Fh+arg_20]; jumptable 000000018000A468 case 11
0x18000a531  call    ?MapVariantFlagsFromChangeFlags@@YAGH@Z; MapVariantFlagsFromChangeFlags(int)
0x18000a536  movzx   r8d, ax; dwFlags
0x18000a53a  mov     edx, 7Fh; lcid
0x18000a53f  mov     rcx, rdi; strIn
0x18000a542  call    cs:__imp_VarBoolFromStr
0x18000a548  mov     r15d, eax
0x18000a54b  jmp     loc_18000A2AA
0x18000a550  movsxd  r9, dword ptr [r10]; jumptable 000000018000A3C0 case 3
0x18000a553  mov     eax, ebx
0x18000a555  cmp     ebx, 13h
0x18000a558  jnz     loc_18000A871
0x18000a55e  test    r9d, r9d
0x18000a561  mov     ecx, 0FFFFFFFFh
0x18000a566  mov     r15d, 80070216h
0x18000a56c  cmovns  ecx, r9d
0x18000a570  sar     r9d, 1Fh
0x18000a574  and     r15d, r9d
0x18000a577  mov     [rsi], ecx
0x18000a579  jmp     loc_18000A2AA
0x18000a57e  mov     r8d, [rbp+4Fh+arg_20]; jumptable 000000018000A468 case 21
0x18000a582  mov     rdx, rsi
0x18000a585  mov     rcx, r10
0x18000a588  call    ??$StrToInt64Impl@_KPEAG@@YAJPEBXPEAXH@Z; StrToInt64Impl<unsigned __int64,ushort *>(void const *,void *,int)
0x18000a58d  mov     r15d, eax
0x18000a590  jmp     loc_18000A2AA
0x18000a595  mov     rdx, rsi; jumptable 000000018000A468 case 72
0x18000a598  mov     rcx, rdi
0x18000a59b  call    cs:__imp_GUIDFromStringW
0x18000a5a1  xor     r15d, r15d
0x18000a5a4  mov     ecx, 80070057h
0x18000a5a9  test    eax, eax
0x18000a5ab  cmovz   r15d, ecx
0x18000a5af  jmp     loc_18000A2AA
0x18000a5b4  mov     rax, [r10]; jumptable 000000018000A3C0 case 64
0x18000a5b7  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], rax
0x18000a5bb  cmp     ebx, 1Fh
0x18000a5be  jz      loc_18000A747
0x18000a5c4  cmp     ebx, 40h ; '@'
0x18000a5c7  jnz     def_18000A3C0; jumptable 000000018000A3C0 default case, cases 1,4,6-10,12-15,22-63,65-71
0x18000a5cd  mov     [r9], rax
0x18000a5d0  jmp     loc_18000A2AA
0x18000a5d5  movzx   r9d, word ptr [r10]; jumptable 000000018000A3C0 case 18
0x18000a5d9  mov     eax, ebx
0x18000a5db  cmp     ebx, 10h
0x18000a5de  jnz     loc_18000ABAA
0x18000a5e4  cmp     r9w, 7Fh
0x18000a5e9  jmp     loc_18000A4DB
0x18000a5ee  cmp     eax, 12h
0x18000a5f1  jnz     loc_18000A7F1
0x18000a5f7  mov     ecx, 0FFFFh
0x18000a5fc  cmp     r9, rcx
0x18000a5ff  jbe     short loc_18000A649; jumptable 000000018000A72E cases 2,18
0x18000a601  mov     r15d, 80070216h
0x18000a607  mov     [rsi], cx
0x18000a60a  movzx   r9d, cx
0x18000a60e  jmp     loc_18000A2AA
0x18000a613  add     eax, 0FFFFFFFEh; switch 30 cases
0x18000a616  cmp     eax, 1Dh
0x18000a619  ja      def_18000A3C0; jumptable 000000018000A3C0 default case, cases 1,4,6-10,12-15,22-63,65-71
0x18000a61f  cdqe
0x18000a621  movzx   eax, ds:(byte_18000B0E0 - 180000000h)[rdx+rax]
0x18000a629  mov     ecx, ds:(jpt_18000A633 - 180000000h)[rdx+rax*4]
0x18000a630  add     rcx, rdx
0x18000a633  jmp     rcx; switch jump
0x18000a635  mov     ecx, 0FFFFh; jumptable 000000018000A633 case 18
0x18000a63a  cmp     r9d, ecx
0x18000a63d  jbe     short loc_18000A649; jumptable 000000018000A72E cases 2,18
0x18000a63f  mov     r15d, 80070216h
0x18000a645  movzx   r9d, cx
0x18000a649  mov     [rsi], r9w; jumptable 000000018000A72E cases 2,18
0x18000a64d  jmp     loc_18000A2AA
0x18000a652  mov     r9, [r10]; jumptable 000000018000A3C0 case 20
0x18000a655  mov     eax, ebx
0x18000a657  cmp     ebx, 3
0x18000a65a  jnz     loc_18000A8CB
0x18000a660  mov     eax, 80000000h
0x18000a665  mov     ecx, 0FFFFFFFFh
0x18000a66a  add     rax, r9
0x18000a66d  cmp     rax, rcx
0x18000a670  jbe     short loc_18000A67F; jumptable 000000018000A633 case 19
0x18000a672  mov     r15d, 80070216h
0x18000a678  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18000a67f  mov     [rsi], r9d; jumptable 000000018000A633 case 19
0x18000a682  jmp     loc_18000A2AA
0x18000a687  lea     rax, [rbp+4Fh+var_88]; jumptable 000000018000A468 case 64
0x18000a68b  xorps   xmm0, xmm0
0x18000a68e  mov     [rsp+0F0h+var_A8], rax
0x18000a693  lea     r9, [rbp+4Fh+SystemTime.wMonth]
0x18000a697  lea     rax, [rbp+4Fh+SystemTime.wMilliseconds]
0x18000a69b  xor     r15d, r15d
0x18000a69e  mov     [rsp+0F0h+var_B0], rax
0x18000a6a3  lea     r8, [rbp+4Fh+SystemTime]
0x18000a6a7  lea     rax, [rbp+4Fh+SystemTime.wSecond]
0x18000a6ab  mov     [rbp+4Fh+var_88], r15d
0x18000a6af  mov     [rsp+0F0h+var_B8], rax
0x18000a6b4  lea     rdx, aHuHuHuHuHuHuHu; "%hu/%hu/%hu:%hu:%hu:%hu.%hu%n"
0x18000a6bb  lea     rax, [rbp+4Fh+SystemTime.wMinute]
0x18000a6bf  mov     rcx, rdi; Buffer
0x18000a6c2  mov     [rsp+0F0h+var_C0], rax
  ... truncated ...
```
