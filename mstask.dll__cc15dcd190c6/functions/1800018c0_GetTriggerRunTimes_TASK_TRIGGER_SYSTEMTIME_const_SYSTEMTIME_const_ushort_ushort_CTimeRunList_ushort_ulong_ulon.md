# GetTriggerRunTimes(_TASK_TRIGGER &,_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *,ulong,ulong,ushort,ushort)

- ea: `0x1800018c0`
- end: `0x18000251e`
- name: `?GetTriggerRunTimes@@YAJAEAU_TASK_TRIGGER@@PEBU_SYSTEMTIME@@1PEAGGPEAVCTimeRunList@@2KKGG@Z`
- size: `3166`
- prototype: `int(struct _TASK_TRIGGER *, const struct _SYSTEMTIME *, const struct _SYSTEMTIME *, unsigned __int16 *, unsigned __int16, struct CTimeRunList *, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16, unsigned __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007640`
- `0x1800092a8`

## callees

- `0x1800018c0`
- `0x180005240`
- `0x180007420`
- `0x18000a608`
- `0x18000d5ec`
- `0x180019554`
- `0x180019678`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bef`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001a9a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001ab1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001af4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001c25`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001c51`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001c67`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001a9a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001ab1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001af4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001c25`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001c51`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001c67`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000195a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001998`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800019d6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001c13`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001c3f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001d8b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800020da`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002247`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800024c0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000195a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001998`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800019d6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001c13`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001c3f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001d8b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800020da`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002247`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800024c0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001d9a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002027`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002256`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001d9a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002027`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002256`

## pseudocode

```c
int __fastcall GetTriggerRunTimes(
        struct _TASK_TRIGGER *a1,
        const struct _SYSTEMTIME *a2,
        const struct _SYSTEMTIME *a3,
        unsigned __int16 *a4,
        unsigned __int16 a5,
        struct CTimeRunList *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned __int16 a10,
        unsigned __int16 a11)
{
  DWORD rgFlags; // edx
  __int32 v15; // ecx
  int v16; // esi
  TASK_TRIGGER_TYPE TriggerType; // ecx
  int wBeginDay; // ebx
  int v19; // r15d
  int wDayOfWeek; // r14d
  WORD wBeginMonth; // r12
  int wBeginYear; // r13d
  __int64 MinutesDuration; // rdx
  __int64 MinutesInterval; // rax
  TASK_TRIGGER_TYPE v25; // ecx
  int DaysInterval; // edx
  __int64 v27; // rax
  __int64 v28; // rdx
  int result; // eax
  __int32 v30; // ecx
  __int32 v31; // ecx
  unsigned __int16 i1; // dx
  __int16 v33; // ax
  unsigned __int16 i2; // r8
  __int64 v35; // rax
  __int16 v36; // dx
  DWORD dwLowDateTime; // r8d
  DWORD v38; // r9d
  WORD v39; // r13
  unsigned int v40; // edx
  unsigned __int16 v41; // cx
  __int16 v42; // ax
  unsigned __int16 v43; // ax
  int v44; // edx
  int v45; // esi
  unsigned __int16 v46; // r15
  unsigned __int16 v47; // ax
  int v48; // eax
  DWORD rgfDays; // r9d
  unsigned __int16 jj; // r8
  char v51; // cl
  __int64 v52; // rax
  unsigned __int16 kk; // r8
  __int64 v54; // rax
  __int16 v55; // dx
  unsigned __int16 v56; // r14
  unsigned __int16 mm; // cx
  __int16 nn; // cx
  WORD v59; // ax
  int v60; // ebx
  unsigned __int16 i; // r8
  __int64 v62; // rax
  __int16 v63; // dx
  unsigned __int16 j; // dx
  unsigned __int16 v65; // ax
  unsigned __int16 v66; // r9
  FILETIME v67; // rbx
  FILETIME v68; // rax
  bool v69; // zf
  unsigned __int16 v70; // ax
  __int32 v71; // ecx
  __int32 v72; // ecx
  int v73; // r8d
  __int16 v74; // dx
  unsigned __int16 k; // cx
  WORD v76; // r12
  WORD v77; // bx
  WORD v78; // ax
  WORD v79; // si
  unsigned __int16 v80; // cx
  unsigned __int16 v81; // si
  unsigned __int16 v82; // ax
  int v83; // r15d
  int v84; // r14d
  unsigned __int16 v85; // cx
  unsigned __int16 m; // si
  unsigned __int16 v87; // r12
  unsigned __int16 v88; // ax
  __int16 n; // dx
  WORD v90; // ax
  __int16 v91; // cx
  int v92; // r9d
  unsigned __int16 ii; // dx
  __int16 v94; // ax
  __int64 v95; // r10
  unsigned __int16 v96; // r10
  WORD wEndYear; // ax
  WORD wEndMonth; // ax
  unsigned __int16 *v99; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v100[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v101[2]; // [rsp+54h] [rbp-ACh] BYREF
  int v102; // [rsp+58h] [rbp-A8h]
  int v103; // [rsp+5Ch] [rbp-A4h]
  FILETIME FileTime1; // [rsp+60h] [rbp-A0h] BYREF
  int v105; // [rsp+68h] [rbp-98h]
  struct _FILETIME v106; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME v107; // [rsp+78h] [rbp-88h] BYREF
  int v108; // [rsp+80h] [rbp-80h]
  FILETIME v109; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME v110; // [rsp+90h] [rbp-70h]
  FILETIME v111; // [rsp+98h] [rbp-68h] BYREF
  FILETIME v112; // [rsp+A0h] [rbp-60h] BYREF
  FILETIME FileTime2; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME FileTime; // [rsp+B0h] [rbp-50h] BYREF
  CTimeRunList *v115; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v116[12]; // [rsp+C0h] [rbp-40h]
  SYSTEMTIME SystemTime; // [rsp+120h] [rbp+20h] BYREF
  _WORD v118[8]; // [rsp+130h] [rbp+30h]

  v116[0] = a4;
  rgFlags = a1->rgFlags;
  v115 = a6;
  if ( (rgFlags & 0x10004) != 0 )
    return 267015;
  v15 = a1->TriggerType - 5;
  if ( !v15 || (unsigned int)(v15 - 1) < 2 )
  {
    if ( (rgFlags & 1) == 0 )
      return 267016;
    wEndYear = a1->wEndYear;
    if ( wEndYear > a2->wYear )
      return 267016;
    if ( wEndYear == a2->wYear )
    {
      wEndMonth = a1->wEndMonth;
      if ( wEndMonth > a2->wMonth || wEndMonth == a2->wMonth && a1->wEndDay >= a2->wDay )
        return 267016;
    }
    return 0;
  }
  v16 = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  *(_QWORD *)&SystemTime.wHour = 0;
  v112 = 0;
  v111 = 0;
  FileTime = 0;
  FileTime2 = 0;
  if ( !SystemTimeToFileTime(a2, &FileTime) )
    goto LABEL_34;
  SystemTime.wYear = a1->wBeginYear;
  SystemTime.wMonth = a1->wBeginMonth;
  SystemTime.wDay = a1->wBeginDay;
  SystemTime.wHour = a1->wStartHour;
  SystemTime.wMinute = a1->wStartMinute;
  if ( !SystemTimeToFileTime(&SystemTime, &v112) )
    goto LABEL_34;
  v69 = (a1->rgFlags & 1) == 0;
  *(_DWORD *)&SystemTime.wHour = 3866647;
  *(_DWORD *)&SystemTime.wSecond = 59;
  if ( v69 )
  {
    *(_DWORD *)&SystemTime.wYear = 788632;
    SystemTime.wDay = 31;
    if ( !SystemTimeToFileTime(&SystemTime, &v111) )
      goto LABEL_34;
  }
  else
  {
    SystemTime.wYear = a1->wEndYear;
    SystemTime.wMonth = a1->wEndMonth;
    SystemTime.wDay = a1->wEndDay;
    if ( !SystemTimeToFileTime(&SystemTime, &v111) )
      goto LABEL_34;
    if ( CompareFileTime(&v111, &FileTime) < 0 )
      return 0;
  }
  if ( !a3 )
  {
LABEL_9:
    FileTime2 = v111;
    goto LABEL_10;
  }
  if ( !SystemTimeToFileTime(a3, &FileTime2) )
  {
LABEL_34:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( CompareFileTime(&v112, &FileTime2) >= 0 )
    return 0;
  if ( CompareFileTime(&v111, &FileTime2) < 0 )
    goto LABEL_9;
LABEL_10:
  TriggerType = a1->TriggerType;
  FileTime1 = 0;
  wBeginDay = 0;
  v107 = 0;
  v19 = 0;
  v109 = 0;
  LOWORD(wDayOfWeek) = 0;
  v103 = 0;
  wBeginMonth = 0;
  v102 = 0;
  LOWORD(wBeginYear) = 0;
  *(_DWORD *)v101 = 0;
  v100[0] = 0;
  v108 = 0;
  v105 = 0;
  if ( (unsigned int)TriggerType <= TASK_TIME_TRIGGER_DAILY )
  {
    FileTime1 = v112;
    goto LABEL_12;
  }
  v30 = TriggerType - 2;
  if ( !v30 )
  {
    if ( a1->Type.Weekly.rgfDaysOfTheWeek )
    {
      FileTimeToSystemTime(&v112, &SystemTime);
      for ( i = 0; i < 7u; ++i )
      {
        v62 = i;
        v63 = (a1->Type.Weekly.rgfDaysOfTheWeek >> i) & 1;
        v118[v62] = v63;
      }
      for ( j = 0; j < 7u; ++j )
      {
        v65 = j + SystemTime.wDayOfWeek - 7;
        if ( (unsigned __int16)(j + SystemTime.wDayOfWeek) < 7u )
          v65 = j + SystemTime.wDayOfWeek;
        if ( v118[v65] )
        {
          FileTime1 = v112;
          AddDaysToFileTime(&FileTime1, j);
          LOWORD(wDayOfWeek) = v66;
          v102 = v66;
          break;
        }
        LOWORD(wDayOfWeek) = v65;
        v102 = v65;
      }
LABEL_12:
      if ( (unsigned int)(a1->TriggerType - 3) <= 1 )
      {
        SystemTime.wHour = a1->wStartHour;
        SystemTime.wMinute = a1->wStartMinute;
        SystemTime.wYear = wBeginYear;
        SystemTime.wMonth = wBeginMonth;
        SystemTime.wDay = wBeginDay;
        *(_DWORD *)&SystemTime.wSecond = 0;
        SystemTimeToFileTime(&SystemTime, &FileTime1);
      }
      MinutesDuration = a1->MinutesDuration;
      v109 = FileTime1;
      v107 = FileTime1;
      if ( (_DWORD)MinutesDuration )
      {
        v106 = FileTime1;
        v109 = (FILETIME)(600000000 * MinutesDuration + *(_QWORD *)&FileTime1);
      }
      while ( CompareFileTime(&FileTime1, &FileTime2) < 0 )
      {
        if ( CompareFileTime(&FileTime1, &FileTime) >= 0 )
        {
          if ( v115 )
          {
            v67 = (FILETIME)0x7FFFFFFFFFFFFFFFLL;
            if ( (a1->rgFlags & 2) != 0 )
              v67 = v109;
            if ( (a8 & 0x10) != 0 )
            {
              v106 = FileTime1;
              AddMinutesToFileTime(&v106, a11);
              v68 = minFileTime(v111, v106);
            }
            else
            {
              v68 = v111;
            }
            result = CTimeRunList::AddSorted(v115, FileTime1, v68, v67, v99, a8, a9, a10, v116[0], a5);
            if ( result < 0 )
              return result;
            if ( result == 1 )
              return 0;
            wBeginDay = *(_DWORD *)v101;
            LOWORD(v19) = v103;
          }
          else
          {
            v69 = *v116[0] == a5;
            if ( *v116[0] < a5 )
            {
              v70 = *v116[0] + 1;
              *v116[0] = v70;
              v69 = v70 == a5;
            }
            if ( v69 )
              return 0;
          }
        }
        MinutesInterval = a1->MinutesInterval;
        if ( (_DWORD)MinutesInterval )
        {
          *(_QWORD *)&FileTime1 += 600000000 * MinutesInterval;
          if ( CompareFileTime(&v109, &FileTime1) <= 0 )
            v16 = 1;
        }
        if ( !a1->MinutesInterval || v16 )
        {
          v25 = a1->TriggerType;
          if ( v25 == TASK_TIME_TRIGGER_DAILY )
          {
            DaysInterval = a1->Type.Daily.DaysInterval;
            if ( (_WORD)DaysInterval )
            {
              v27 = *(_QWORD *)&v107 + FILETIMES_PER_DAY * a1->Type.Daily.DaysInterval;
              v107.dwLowDateTime += FILETIMES_PER_DAY * DaysInterval;
              v107.dwHighDateTime = HIDWORD(v27);
            }
          }
          else
          {
            if ( v25 == TASK_TIME_TRIGGER_ONCE )
              return 0;
            v71 = v25 - 2;
            if ( v71 )
            {
              v72 = v71 - 1;
              if ( v72 )
              {
                if ( v72 != 1 )
                  return -2147467259;
                v73 = v105;
                v74 = 1;
                if ( !(_WORD)v105 )
                {
                  for ( k = 0; k < 0xCu; ++k )
                  {
                    v76 = wBeginMonth + 1;
                    v77 = wBeginYear + 1;
                    v78 = 1;
                    if ( v76 <= 0xCu )
                    {
                      v78 = v76;
                      v77 = wBeginYear;
                    }
                    v79 = v78;
                    if ( *((_WORD *)v116 + v78 + 3) )
                      break;
                    wBeginMonth = v78;
                    LOWORD(wBeginYear) = v77;
                  }
                  LOWORD(v19) = 1;
                  SystemTime.wDay = 1;
                  v103 = 1;
                  SystemTime.wMonth = v78;
                  SystemTime.wYear = v77;
                  SystemTimeToFileTime(&SystemTime, &FileTime1);
                  FileTimeToSystemTime(&FileTime1, &SystemTime);
                  v73 = (unsigned __int16)v108;
                  LOWORD(wBeginYear) = v77;
                  wDayOfWeek = SystemTime.wDayOfWeek;
                  v74 = 0;
                  wBeginDay = *(_DWORD *)v101;
                  wBeginMonth = v79;
                  v105 = (unsigned __int16)v108;
                  goto LABEL_147;
                }
                while ( (unsigned __int16)v74 <= 7u )
                {
                  v80 = wDayOfWeek + 1;
                  v81 = v19 + 1;
                  if ( !v74 )
                  {
                    v80 = wDayOfWeek;
                    v81 = v19;
                  }
                  v82 = v80 - 7;
                  if ( v80 < 7u )
                    v82 = v80;
                  wDayOfWeek = v82;
                  if ( v118[v82] )
                  {
                    LOWORD(v73) = v73 - 1;
                    wBeginDay = 7 * a1->Type.Daily.DaysInterval;
                    v105 = v73;
                    v101[0] = 0;
                    LOWORD(wBeginDay) = v81 + wBeginDay - 7;
                    MonthDays(wBeginMonth, wBeginYear, v101);
                    LOWORD(v19) = v81;
                    v102 = wDayOfWeek;
                    v103 = v81;
                    if ( (unsigned __int16)wBeginDay > v101[0] )
                      LOWORD(wBeginDay) = wBeginDay - 7;
                    *(_DWORD *)v101 = wBeginDay;
                    break;
                  }
                  LOWORD(v19) = v81;
                  ++v74;
                  v103 = v81;
LABEL_147:
                  v102 = wDayOfWeek;
                }
              }
              else
              {
                v83 = 0;
                v84 = 0;
                do
                {
                  MonthDays(wBeginMonth, wBeginYear, v100);
                  v85 = v100[0];
                  for ( m = 1; m <= v85; ++m )
                  {
                    LOWORD(wBeginDay) = wBeginDay + 1;
                    if ( (unsigned __int16)wBeginDay <= v85 )
                    {
                      *(_DWORD *)v101 = wBeginDay;
                    }
                    else
                    {
                      v87 = wBeginMonth + 1;
                      *(_DWORD *)v101 = 1;
                      v83 = 1;
                      if ( v87 > 0xCu )
                        LOWORD(wBeginYear) = wBeginYear + 1;
                      v88 = 1;
                      if ( v87 <= 0xCu )
                        v88 = v87;
                      wBeginMonth = v88;
                      MonthDays(v88, wBeginYear, v100);
                      v85 = v100[0];
                      wBeginDay = *(_DWORD *)v101;
                    }
                    if ( *((_WORD *)&v116[3] + (unsigned __int16)wBeginDay + 3) )
                    {
                      v84 = 1;
                      break;
                    }
                  }
                  if ( !v83 && v84 )
                    break;
                  for ( n = 1; (unsigned __int16)n <= 0xCu; ++n )
                  {
                    v90 = wBeginMonth;
                    if ( wBeginMonth > 0xCu )
                      wBeginMonth = 1;
                    v91 = wBeginYear + 1;
                    if ( v90 <= 0xCu )
                      v91 = wBeginYear;
                    LOWORD(wBeginYear) = v91;
                    if ( *((_WORD *)v116 + wBeginMonth + 3) )
                    {
                      v83 = 0;
                      break;
                    }
                    ++wBeginMonth;
                  }
                }
                while ( !v84 );
                LOWORD(v19) = v103;
                LOWORD(wDayOfWeek) = v102;
              }
            }
            else
            {
              v92 = 0;
              for ( ii = 1; ii <= 7u; ++ii )
              {
                v94 = -6;
                if ( (unsigned __int16)(wDayOfWeek + 1) >= 7u )
                  v92 = 1;
                else
                  v94 = 1;
                v95 = (unsigned __int16)(wDayOfWeek + v94);
                if ( v118[v95] )
                {
                  AddDaysToFileTime(&v107, ii);
                  LOWORD(wDayOfWeek) = v96;
                  v102 = v96;
                  break;
                }
                LOWORD(wDayOfWeek) = wDayOfWeek + v94;
                v102 = (unsigned __int16)v95;
              }
              if ( v92 )
                AddDaysToFileTime(&v107, 7 * a1->Type.Daily.DaysInterval - 7);
            }
          }
          if ( (unsigned int)(a1->TriggerType - 3) <= 1 )
          {
            SystemTime.wHour = a1->wStartHour;
            SystemTime.wMinute = a1->wStartMinute;
            *(_DWORD *)&SystemTime.wSecond = 0;
            SystemTime.wYear = wBeginYear;
            SystemTime.wMonth = wBeginMonth;
            SystemTime.wDay = wBeginDay;
            SystemTimeToFileTime(&SystemTime, &v107);
          }
          v28 = a1->MinutesDuration;
          v109 = v107;
          FileTime1 = v107;
          if ( (_DWORD)v28 )
          {
            v110 = v107;
            v109 = (FILETIME)(600000000 * v28 + *(_QWORD *)&v107);
          }
          v16 = 0;
        }
      }
    }
    return 0;
  }
  v31 = v30 - 1;
  if ( !v31 )
  {
    rgfDays = a1->Type.MonthlyDate.rgfDays;
    if ( rgfDays )
    {
      for ( jj = 0; jj < 0x1Fu; ++jj )
      {
        v51 = jj;
        v52 = jj;
        *((_WORD *)&v116[4] + v52) = (rgfDays >> v51) & 1;
      }
      for ( kk = 0; kk < 0xCu; ++kk )
      {
        v54 = kk;
        v55 = (a1->Type.MonthlyDate.rgfMonths >> kk) & 1;
        *((_WORD *)&v116[1] + v54) = v55;
      }
      wBeginYear = a1->wBeginYear;
      wBeginDay = a1->wBeginDay;
      wBeginMonth = a1->wBeginMonth;
      *(_DWORD *)v101 = wBeginDay;
      v56 = wBeginYear + 2;
      while ( 1 )
      {
        MonthDays(wBeginMonth, wBeginYear, v100);
        for ( mm = 0; mm < v100[0]; ++mm )
        {
          if ( (unsigned __int16)wBeginDay > v100[0] )
          {
            wBeginDay = 1;
            v19 = 1;
            *(_DWORD *)v101 = 1;
          }
          if ( *((_WORD *)&v116[3] + (unsigned __int16)wBeginDay + 3) )
          {
            v16 = 1;
            break;
          }
          LOWORD(wBeginDay) = wBeginDay + 1;
          *(_DWORD *)v101 = wBeginDay;
        }
        for ( nn = 0; ; nn = 1 )
        {
          while ( 1 )
          {
            v59 = wBeginMonth;
            if ( wBeginMonth > 0xCu )
              wBeginMonth = 1;
            v60 = wBeginYear + 1;
            if ( v59 <= 0xCu )
              LOWORD(v60) = wBeginYear;
            if ( *((_WORD *)v116 + wBeginMonth + 3) )
              break;
            ++wBeginMonth;
            ++nn;
            wBeginYear = (unsigned __int16)v60;
            if ( (unsigned __int16)nn >= 0xCu )
              goto LABEL_103;
          }
          if ( !v19 || nn )
            break;
          v19 = 0;
          ++wBeginMonth;
          wBeginYear = (unsigned __int16)v60;
        }
LABEL_103:
        if ( !v16 )
          break;
        MonthDays(wBeginMonth, v60, v100);
        if ( v101[0] <= v100[0] )
        {
          LOWORD(wBeginYear) = v60;
          wBeginDay = *(_DWORD *)v101;
LABEL_110:
          LOWORD(v19) = v103;
          LOWORD(wDayOfWeek) = v102;
LABEL_111:
          v16 = 0;
          goto LABEL_12;
        }
        v16 = 0;
        ++wBeginMonth;
        *(_DWORD *)v101 = 1;
        if ( wBeginMonth <= 0xCu )
          goto LABEL_108;
        wBeginMonth = 1;
        wBeginYear = v60 + 1;
LABEL_109:
        wBeginDay = *(_DWORD *)v101;
        if ( (unsigned __int16)wBeginYear >= v56 )
          goto LABEL_110;
      }
      *(_DWORD *)v101 = 1;
LABEL_108:
      wBeginYear = (unsigned __int16)v60;
      goto LABEL_109;
    }
    return 0;
  }
  if ( v31 == 1 )
  {
    v108 = 0;
    for ( i1 = 0; i1 < 7u; ++i1 )
    {
      if ( ((a1->Type.Weekly.rgfDaysOfTheWeek >> i1) & 1) != 0 )
      {
        LOWORD(v16) = v16 + 1;
        v33 = 1;
        v108 = v16;
      }
      else
      {
        if ( 2 * (unsigned __int64)i1 >= 0xE )
          _report_rangecheckfailure();
        v33 = 0;
      }
      v118[i1] = v33;
    }
    for ( i2 = 0; i2 < 0xCu; ++i2 )
    {
      v35 = i2;
      v36 = (a1->Type.MonthlyDate.rgfMonths >> i2) & 1;
      *((_WORD *)&v116[1] + v35) = v36;
    }
    dwLowDateTime = a1->wBeginMonth;
    v38 = a1->wBeginYear;
    v110.dwLowDateTime = dwLowDateTime;
    v106.dwLowDateTime = v38;
LABEL_57:
    v39 = wBeginMonth;
    v40 = wBeginMonth + 12;
    if ( wBeginMonth < v40 )
    {
      do
      {
        if ( *((_WORD *)v116 + (unsigned __int16)dwLowDateTime + 3) )
          break;
        ++v39;
        v41 = dwLowDateTime + 1;
        v42 = -11;
        if ( (unsigned __int16)(dwLowDateTime + 1) <= 0xCu )
          v42 = 1;
        LOWORD(dwLowDateTime) = v42 + dwLowDateTime;
        v43 = v38 + 1;
        if ( v41 <= 0xCu )
          v43 = v38;
        v38 = v43;
      }
      while ( v39 < v40 );
      v106.dwLowDateTime = v38;
      v110.dwLowDateTime = dwLowDateTime;
    }
    SystemTime.wMonth = dwLowDateTime;
    SystemTime.wDay = 1;
    SystemTime.wYear = v38;
    SystemTimeToFileTime(&SystemTime, &FileTime1);
    FileTimeToSystemTime(&FileTime1, &SystemTime);
    v44 = (unsigned __int16)v16;
    v45 = 0;
    v105 = v44;
    while ( (unsigned __int16)v45 < 7u )
    {
      v46 = v45 + 1;
      v47 = v45 + SystemTime.wDayOfWeek - 7;
      if ( (unsigned __int16)(v45 + SystemTime.wDayOfWeek) < 7u )
        v47 = v45 + SystemTime.wDayOfWeek;
      wDayOfWeek = v47;
      if ( v118[v47] )
      {
        LOWORD(v44) = v44 - 1;
        v48 = a1->Type.Daily.DaysInterval;
        wBeginDay = 7 * v48;
        v105 = v44;
        LOWORD(wBeginDay) = v45 + 1 + 7 * v48 - 7;
        MonthDays(v110.dwLowDateTime, v106.dwLowDateTime, v100);
        if ( (unsigned __int16)wBeginDay > v100[0] )
          LOWORD(wBeginDay) = wBeginDay - 7;
        v102 = (unsigned __int16)wDayOfWeek;
        *(_DWORD *)v101 = wBeginDay;
        if ( v39 || (v102 = (unsigned __int16)wDayOfWeek, (unsigned __int16)wBeginDay >= a1->wBeginDay) )
        {
          LOWORD(wDayOfWeek) = v102;
          break;
        }
        v44 = v105;
        if ( !(_WORD)v105 )
        {
          dwLowDateTime = v110.dwLowDateTime;
          ++wBeginMonth;
          v38 = v106.dwLowDateTime;
          LOWORD(v16) = v108;
          v102 = wDayOfWeek;
          goto LABEL_57;
        }
      }
      else
      {
        wBeginDay = v46;
        *(_DWORD *)v101 = v46;
      }
      v45 = v46;
      v102 = wDayOfWeek;
    }
    wBeginMonth = v110.dwLowDateTime;
    LOWORD(v19) = v45 + 1;
    LOWORD(wBeginYear) = v106.dwLowDateTime;
    v103 = v45 + 1;
    goto LABEL_111;
  }
  return -2147467259;
}

```

## disassembly

```asm
0x1800018c0  mov     r11, rsp
0x1800018c3  push    rbp
0x1800018c4  push    rbx
0x1800018c5  push    rdi
0x1800018c6  lea     rbp, [rsp-80h]
0x1800018cb  sub     rsp, 180h
0x1800018d2  mov     rax, cs:__security_cookie
0x1800018d9  xor     rax, rsp
0x1800018dc  mov     [rbp+90h+var_50], rax
0x1800018e0  mov     rax, [rbp+90h+arg_28]
0x1800018e7  mov     rbx, r8
0x1800018ea  mov     r8, rdx
0x1800018ed  mov     [rbp+90h+var_D0], r9
0x1800018f1  mov     edx, [rcx+1Ch]
0x1800018f4  mov     rdi, rcx
0x1800018f7  mov     [rbp+90h+var_D8], rax
0x1800018fb  test    edx, 10004h
0x180001901  jnz     loc_180002514
0x180001907  mov     ecx, [rcx+20h]
0x18000190a  mov     [r11-20h], rsi
0x18000190e  mov     [r11-28h], r12
0x180001912  mov     [r11-30h], r13
0x180001916  mov     [r11-38h], r14
0x18000191a  mov     [r11-40h], r15
0x18000191e  sub     ecx, 5
0x180001921  jz      loc_1800024D5
0x180001927  sub     ecx, 1
0x18000192a  jz      loc_1800024D5
0x180001930  cmp     ecx, 1
0x180001933  jz      loc_1800024D5
0x180001939  xor     esi, esi
0x18000193b  lea     rdx, [rbp+90h+FileTime]; lpFileTime
0x18000193f  mov     rcx, r8; lpSystemTime
0x180001942  mov     qword ptr [rbp+90h+SystemTime.wYear], rsi
0x180001946  mov     qword ptr [rbp+90h+SystemTime.wHour], rsi
0x18000194a  mov     qword ptr [rbp+90h+var_F0.dwLowDateTime], rsi
0x18000194e  mov     qword ptr [rbp+90h+var_F8.dwLowDateTime], rsi
0x180001952  mov     qword ptr [rbp+90h+FileTime.dwLowDateTime], rsi
0x180001956  mov     qword ptr [rbp+90h+FileTime2.dwLowDateTime], rsi
0x18000195a  call    cs:__imp_SystemTimeToFileTime
0x180001960  test    eax, eax
0x180001962  jz      loc_180001BEF
0x180001968  movzx   eax, word ptr [rdi+4]
0x18000196c  lea     rdx, [rbp+90h+var_F0]; lpFileTime
0x180001970  mov     [rbp+90h+SystemTime.wYear], ax
0x180001974  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x180001978  movzx   eax, word ptr [rdi+6]
0x18000197c  mov     [rbp+90h+SystemTime.wMonth], ax
0x180001980  movzx   eax, word ptr [rdi+8]
0x180001984  mov     [rbp+90h+SystemTime.wDay], ax
0x180001988  movzx   eax, word ptr [rdi+10h]
0x18000198c  mov     [rbp+90h+SystemTime.wHour], ax
0x180001990  movzx   eax, word ptr [rdi+12h]
0x180001994  mov     [rbp+90h+SystemTime.wMinute], ax
0x180001998  call    cs:__imp_SystemTimeToFileTime
0x18000199e  test    eax, eax
0x1800019a0  jz      loc_180001BEF
0x1800019a6  test    byte ptr [rdi+1Ch], 1
0x1800019aa  lea     rdx, [rbp+90h+var_F8]; lpFileTime
0x1800019ae  mov     dword ptr [rbp+90h+SystemTime.wHour], 3B0017h
0x1800019b5  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x1800019b9  mov     dword ptr [rbp+90h+SystemTime.wSecond], 3Bh ; ';'
0x1800019c0  jnz     loc_180001BFB
0x1800019c6  mov     eax, 1Fh
0x1800019cb  mov     dword ptr [rbp+90h+SystemTime.wYear], 0C0898h
0x1800019d2  mov     [rbp+90h+SystemTime.wDay], ax
0x1800019d6  call    cs:__imp_SystemTimeToFileTime
0x1800019dc  test    eax, eax
0x1800019de  jz      loc_180001BEF
0x1800019e4  test    rbx, rbx
0x1800019e7  jnz     loc_180001C38
0x1800019ed  mov     rax, qword ptr [rbp+90h+var_F8.dwLowDateTime]
0x1800019f1  mov     qword ptr [rbp+90h+FileTime2.dwLowDateTime], rax
0x1800019f5  mov     ecx, [rdi+20h]
0x1800019f8  mov     r10d, 1
0x1800019fe  mov     qword ptr [rsp+190h+FileTime1.dwLowDateTime], rsi
0x180001a03  mov     ebx, esi
0x180001a05  mov     qword ptr [rsp+190h+var_118.dwLowDateTime], rsi
0x180001a0a  mov     r15d, esi
0x180001a0d  mov     qword ptr [rbp+90h+var_108.dwLowDateTime], rsi
0x180001a11  mov     r14d, esi
0x180001a14  mov     [rsp+190h+var_134], esi
0x180001a18  mov     r12d, esi
0x180001a1b  mov     [rsp+190h+var_138], esi
0x180001a1f  mov     r13d, esi
0x180001a22  mov     dword ptr [rsp+190h+var_13C], ebx
0x180001a26  mov     [rsp+190h+var_140], si
0x180001a2b  mov     [rbp+90h+var_110], esi
0x180001a2e  mov     [rsp+190h+var_128], esi
0x180001a32  cmp     ecx, r10d
0x180001a35  jnz     loc_180001C7A
0x180001a3b  mov     rax, qword ptr [rbp+90h+var_F0.dwLowDateTime]
0x180001a3f  mov     qword ptr [rsp+190h+FileTime1.dwLowDateTime], rax
0x180001a44  mov     eax, [rdi+20h]
0x180001a47  sub     eax, 3
0x180001a4a  cmp     eax, 1
0x180001a4d  jbe     loc_1800020AC
0x180001a53  mov     rax, qword ptr [rsp+190h+FileTime1.dwLowDateTime]
0x180001a58  mov     edx, [rdi+14h]
0x180001a5b  mov     qword ptr [rbp+90h+var_108.dwLowDateTime], rax
0x180001a5f  mov     qword ptr [rsp+190h+var_118.dwLowDateTime], rax
0x180001a64  test    edx, edx
0x180001a66  jz      short loc_180001A91
0x180001a68  mov     ecx, [rsp+190h+FileTime1.dwLowDateTime]
0x180001a6c  shr     rax, 20h
0x180001a70  mov     [rsp+190h+var_120.dwHighDateTime], eax
0x180001a74  mov     [rsp+190h+var_120.dwLowDateTime], ecx
0x180001a78  mov     rax, qword ptr [rsp+190h+var_120.dwLowDateTime]
0x180001a7d  imul    rcx, rdx, 23C34600h
0x180001a84  add     rax, rcx
0x180001a87  mov     [rbp+90h+var_108.dwLowDateTime], eax
0x180001a8a  shr     rax, 20h
0x180001a8e  mov     [rbp+90h+var_108.dwHighDateTime], eax
0x180001a91  lea     rdx, [rbp+90h+FileTime2]; lpFileTime2
0x180001a95  lea     rcx, [rsp+190h+FileTime1]; lpFileTime1
0x180001a9a  call    cs:__imp_CompareFileTime
0x180001aa0  test    eax, eax
0x180001aa2  jns     loc_180001BA4
0x180001aa8  lea     rdx, [rbp+90h+FileTime]; lpFileTime2
0x180001aac  lea     rcx, [rsp+190h+FileTime1]; lpFileTime1
0x180001ab1  call    cs:__imp_CompareFileTime
0x180001ab7  test    eax, eax
0x180001ab9  jns     loc_1800020E5
0x180001abf  mov     eax, [rdi+18h]
0x180001ac2  test    eax, eax
0x180001ac4  jz      short loc_180001B04
0x180001ac6  mov     ecx, [rsp+190h+FileTime1.dwLowDateTime]
0x180001aca  mov     edx, [rsp+190h+FileTime1.dwHighDateTime]
0x180001ace  imul    rax, 23C34600h
0x180001ad5  shl     rdx, 20h
0x180001ad9  or      rdx, rcx
0x180001adc  lea     rcx, [rbp+90h+var_108]; lpFileTime1
0x180001ae0  add     rax, rdx
0x180001ae3  lea     rdx, [rsp+190h+FileTime1]; lpFileTime2
0x180001ae8  mov     [rsp+190h+FileTime1.dwLowDateTime], eax
0x180001aec  shr     rax, 20h
0x180001af0  mov     [rsp+190h+FileTime1.dwHighDateTime], eax
0x180001af4  call    cs:__imp_CompareFileTime
0x180001afa  test    eax, eax
0x180001afc  mov     eax, 1
0x180001b01  cmovle  esi, eax
0x180001b04  cmp     dword ptr [rdi+18h], 0
0x180001b08  jz      short loc_180001B0E
0x180001b0a  test    esi, esi
0x180001b0c  jz      short loc_180001A91
0x180001b0e  mov     ecx, [rdi+20h]
0x180001b11  cmp     ecx, 1
0x180001b14  jnz     loc_180001B9C
0x180001b1a  movzx   edx, word ptr [rdi+24h]
0x180001b1e  test    dx, dx
0x180001b21  jz      short loc_180001B4B
0x180001b23  mov     eax, [rsp+190h+var_118.dwLowDateTime]
0x180001b27  mov     ecx, [rsp+190h+var_118.dwHighDateTime]
0x180001b2b  shl     rcx, 20h
0x180001b2f  or      rcx, rax
0x180001b32  mov     eax, edx
0x180001b34  imul    rax, cs:?FILETIMES_PER_DAY@@3_JA; __int64 FILETIMES_PER_DAY
0x180001b3c  add     rax, rcx
0x180001b3f  mov     [rsp+190h+var_118.dwLowDateTime], eax
0x180001b43  shr     rax, 20h
0x180001b47  mov     [rsp+190h+var_118.dwHighDateTime], eax
0x180001b4b  mov     eax, [rdi+20h]
0x180001b4e  sub     eax, 3
0x180001b51  cmp     eax, 1
0x180001b54  jbe     loc_180002494
0x180001b5a  mov     rax, qword ptr [rsp+190h+var_118.dwLowDateTime]
0x180001b5f  mov     edx, [rdi+14h]
0x180001b62  mov     qword ptr [rbp+90h+var_108.dwLowDateTime], rax
0x180001b66  mov     qword ptr [rsp+190h+FileTime1.dwLowDateTime], rax
0x180001b6b  test    edx, edx
0x180001b6d  jz      short loc_180001B95
0x180001b6f  mov     ecx, [rsp+190h+var_118.dwLowDateTime]
0x180001b73  shr     rax, 20h
0x180001b77  mov     dword ptr [rbp+90h+var_100+4], eax
0x180001b7a  mov     dword ptr [rbp+90h+var_100], ecx
0x180001b7d  mov     rax, [rbp+90h+var_100]
0x180001b81  imul    rcx, rdx, 23C34600h
0x180001b88  add     rax, rcx
0x180001b8b  mov     [rbp+90h+var_108.dwLowDateTime], eax
0x180001b8e  shr     rax, 20h
0x180001b92  mov     [rbp+90h+var_108.dwHighDateTime], eax
0x180001b95  xor     esi, esi
0x180001b97  jmp     loc_180001A91
0x180001b9c  test    ecx, ecx
0x180001b9e  jnz     loc_1800021C6
0x180001ba4  xor     eax, eax
0x180001ba6  jmp     short loc_180001BB0
0x180001ba8  movzx   eax, ax
0x180001bab  or      eax, 80070000h
0x180001bb0  mov     r14, [rsp+190h+var_30]
0x180001bb8  mov     r13, [rsp+190h+var_28]
0x180001bc0  mov     r12, [rsp+190h+var_20]
0x180001bc8  mov     rsi, [rsp+190h+var_18]
0x180001bd0  mov     r15, [rsp+190h+var_38]
0x180001bd8  mov     rcx, [rbp+90h+var_50]
0x180001bdc  xor     rcx, rsp; StackCookie
0x180001bdf  call    __security_check_cookie
0x180001be4  add     rsp, 180h
0x180001beb  pop     rdi
0x180001bec  pop     rbx
0x180001bed  pop     rbp
0x180001bee  retn
0x180001bef  call    cs:__imp_GetLastError
0x180001bf5  test    eax, eax
0x180001bf7  jle     short loc_180001BB0
0x180001bf9  jmp     short loc_180001BA8
0x180001bfb  movzx   eax, word ptr [rdi+0Ah]
0x180001bff  mov     [rbp+90h+SystemTime.wYear], ax
0x180001c03  movzx   eax, word ptr [rdi+0Ch]
0x180001c07  mov     [rbp+90h+SystemTime.wMonth], ax
0x180001c0b  movzx   eax, word ptr [rdi+0Eh]
0x180001c0f  mov     [rbp+90h+SystemTime.wDay], ax
0x180001c13  call    cs:__imp_SystemTimeToFileTime
0x180001c19  test    eax, eax
0x180001c1b  jz      short loc_180001BEF
0x180001c1d  lea     rdx, [rbp+90h+FileTime]; lpFileTime2
0x180001c21  lea     rcx, [rbp+90h+var_F8]; lpFileTime1
0x180001c25  call    cs:__imp_CompareFileTime
0x180001c2b  test    eax, eax
0x180001c2d  js      loc_180001BA4
0x180001c33  jmp     loc_1800019E4
0x180001c38  lea     rdx, [rbp+90h+FileTime2]; lpFileTime
0x180001c3c  mov     rcx, rbx; lpSystemTime
0x180001c3f  call    cs:__imp_SystemTimeToFileTime
0x180001c45  test    eax, eax
0x180001c47  jz      short loc_180001BEF
0x180001c49  lea     rdx, [rbp+90h+FileTime2]; lpFileTime2
0x180001c4d  lea     rcx, [rbp+90h+var_F0]; lpFileTime1
0x180001c51  call    cs:__imp_CompareFileTime
0x180001c57  test    eax, eax
0x180001c59  jns     loc_180001BA4
0x180001c5f  lea     rdx, [rbp+90h+FileTime2]; lpFileTime2
0x180001c63  lea     rcx, [rbp+90h+var_F8]; lpFileTime1
0x180001c67  call    cs:__imp_CompareFileTime
0x180001c6d  test    eax, eax
0x180001c6f  jns     loc_1800019F5
0x180001c75  jmp     loc_1800019ED
0x180001c7a  test    ecx, ecx
0x180001c7c  jz      loc_180001A3B
0x180001c82  sub     ecx, 2
0x180001c85  jz      loc_180002015
0x180001c8b  sub     ecx, r10d
0x180001c8e  jz      loc_180001E8B
0x180001c94  cmp     ecx, r10d
0x180001c97  jnz     loc_1800024CB
0x180001c9d  mov     [rbp+90h+var_110], esi
0x180001ca0  xor     edx, edx
0x180001ca2  cmp     dx, 7
0x180001ca6  jnb     short loc_180001CE3
0x180001ca8  movzx   eax, dx
0x180001cab  movzx   ecx, dx
0x180001cae  lea     r8, [rax+rax]
0x180001cb2  movzx   eax, word ptr [rdi+26h]
0x180001cb6  shr     ax, cl
0x180001cb9  test    r10b, al
0x180001cbc  jz      short loc_180001CCA
0x180001cbe  inc     si
0x180001cc1  movzx   eax, r10w
0x180001cc5  mov     [rbp+90h+var_110], esi
0x180001cc8  jmp     short loc_180001CD2
0x180001cca  cmp     r8, 0Eh
0x180001cce  jnb     short loc_180001CDD
0x180001cd0  xor     eax, eax
0x180001cd2  mov     [rbp+r8+90h+var_60], ax
0x180001cd8  inc     dx
0x180001cdb  jmp     short loc_180001CA2
0x180001cdd  call    __report_rangecheckfailure
0x180001ce3  xor     r8d, r8d
0x180001ce6  movzx   edx, word ptr [rdi+28h]
0x180001cea  movzx   ecx, r8w
0x180001cee  shr     dx, cl
0x180001cf1  movzx   eax, r8w
0x180001cf5  and     dx, r10w
0x180001cf9  inc     r8w
0x180001cfd  mov     [rbp+rax*2+90h+var_C8], dx
0x180001d02  cmp     r8w, 0Ch
0x180001d07  jb      short loc_180001CE6
0x180001d09  movzx   r8d, word ptr [rdi+6]
0x180001d0e  movzx   r9d, word ptr [rdi+4]
0x180001d13  mov     dword ptr [rbp+90h+var_100], r8d
0x180001d17  mov     [rsp+190h+var_120.dwLowDateTime], r9d
0x180001d1c  movzx   eax, r12w
0x180001d20  movzx   r13d, r12w
0x180001d24  lea     edx, [rax+0Ch]
0x180001d27  cmp     eax, edx
0x180001d29  jnb     short loc_180001D73
0x180001d2b  movzx   eax, r8w
0x180001d2f  cmp     word ptr [rbp+rax*2+90h+var_D0+6], 0
0x180001d35  jnz     short loc_180001D6A
0x180001d37  inc     r13w
0x180001d3b  lea     ecx, [r8+1]
0x180001d3f  cmp     cx, 0Ch
0x180001d43  mov     eax, 0FFF5h
0x180001d48  cmovbe  ax, r10w
0x180001d4d  add     r8w, ax
0x180001d51  lea     eax, [r9+1]
0x180001d55  cmp     cx, 0Ch
0x180001d59  cmovbe  ax, r9w
0x180001d5e  movzx   r9d, ax
0x180001d62  movzx   eax, r13w
  ... truncated ...
```
