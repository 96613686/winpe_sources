# StringFromTrigger(_TASK_TRIGGER * const,ushort * *,_SHELLDETAILS *)

- ea: `0x180008688`
- end: `0x180009010`
- name: `?StringFromTrigger@@YAJQEAU_TASK_TRIGGER@@PEAPEAGPEAU_SHELLDETAILS@@@Z`
- size: `2440`
- prototype: `__int64 __fastcall(struct _TASK_TRIGGER *const, unsigned __int16 **, struct _SHELLDETAILS *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000db60`
- `0x180013504`

## callees

- `0x180001840`
- `0x180008688`
- `0x18000c4dc`
- `0x18000c78c`
- `0x18000ca54`
- `0x18001aa9a`
- `0x18001aac0`
- `0x18001ab50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800087fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000889a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000893b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800089a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008a8b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008afa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008b5d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008b92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008c10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008c91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008da9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008e05`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008f94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800087fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000889a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000893b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800089a9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008a8b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008afa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008b5d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008b92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008c10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008c91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008da9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008e05`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180008f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b6b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800088d2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008b31`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008e42`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008eef`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800088d2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008b31`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008e42`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008eef`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180008be8`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180008d16`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180008be8`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180008d16`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180008e8f`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180008f43`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180008e8f`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180008f43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800089d4`

## pseudocode

```c
signed int __fastcall StringFromTrigger(
        struct _TASK_TRIGGER *const a1,
        unsigned __int16 **a2,
        struct _SHELLDETAILS *a3)
{
  bool v5; // zf
  UINT v6; // r15d
  UINT v7; // edi
  TASK_TRIGGER_TYPE TriggerType; // ecx
  __int32 v9; // ecx
  __int32 v10; // ecx
  __int32 v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  signed int result; // eax
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  WORD rgfMonths; // cx
  UINT v19; // edx
  DWORD StringW; // eax
  unsigned __int16 v21; // r14
  __int16 v22; // bx
  unsigned __int16 i; // dx
  UINT v24; // edx
  __int64 DaysInterval; // r9
  DWORD v26; // eax
  __int64 v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int16 *v29; // rax
  unsigned int v30; // r8d
  UINT v31; // edx
  WORD wStartHour; // ax
  DWORD MinutesInterval; // edi
  __int64 v34; // r9
  unsigned int v35; // ebx
  unsigned __int16 j; // cx
  UINT v37; // edx
  DWORD MinutesDuration; // edi
  __int64 v39; // r9
  unsigned int v40; // ebx
  UINT v41; // edx
  SYSTEMTIME Time; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h]
  WCHAR *v45; // [rsp+70h] [rbp-90h]
  unsigned __int16 v46[2]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v47; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 v48[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-70h]
  WCHAR Source[80]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v51[16]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v52[16]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Buffer[32]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR TimeStr[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR v55[32]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR v56[32]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR DateStr[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR lpBuffer[256]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR v59[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v60[256]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR v61[256]; // [rsp+780h] [rbp+680h] BYREF
  WCHAR v62[512]; // [rsp+980h] [rbp+880h] BYREF
  unsigned __int16 v63[512]; // [rsp+D80h] [rbp+C80h] BYREF

  *a2 = 0;
  *(_DWORD *)v46 = *(_DWORD *)L"%d";
  v47 = aD[2];
  *(_OWORD *)v48 = 0;
  v49 = 0;
  memset_0(v60, 0, sizeof(v60));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v63, 0, sizeof(v63));
  memset_0(Source, 0, sizeof(Source));
  memset_0(lpBuffer, 0, sizeof(lpBuffer));
  v5 = (a1->rgFlags & 0x10000) == 0;
  v45 = 0;
  *(_OWORD *)Arguments = 0;
  v6 = 1078;
  v44 = 0;
  if ( !v5 )
  {
    v7 = 1123;
    goto LABEL_35;
  }
  TriggerType = a1->TriggerType;
  v7 = 0;
  if ( TriggerType )
  {
    v9 = TriggerType - 1;
    if ( !v9 )
    {
      if ( a1->Type.Daily.DaysInterval == 1 )
      {
        StringW = LoadStringW(g_hInstance, 0x458u, lpBuffer, 256);
LABEL_56:
        if ( !StringW )
          goto LABEL_57;
        goto LABEL_35;
      }
      if ( !LoadStringW(g_hInstance, 0x457u, Source, 80) )
        goto LABEL_57;
      DaysInterval = a1->Type.Daily.DaysInterval;
LABEL_34:
      StringCchPrintfW(lpBuffer, 0x100u, Source, DaysInterval);
      goto LABEL_35;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return -2147024883;
              v7 = 1130;
            }
            else
            {
              v7 = 1091;
            }
          }
          else
          {
            v7 = 1090;
          }
          goto LABEL_35;
        }
        if ( !LoadStringW(g_hInstance, a1->Type.Daily.DaysInterval + 1078, Buffer, 32) )
          goto LABEL_57;
        result = GetDaysOfWeekString(a1->Type.Weekly.rgfDaysOfTheWeek, v60, v16);
        if ( result < 0 )
          return result;
        rgfMonths = a1->Type.MonthlyDate.rgfMonths;
        if ( rgfMonths == 4095 )
        {
          v19 = 1118;
          Arguments[0] = (va_list)Buffer;
          Arguments[1] = (va_list)v60;
        }
        else
        {
          result = GetMonthsString(rgfMonths, v63, v17);
          if ( result < 0 )
            return result;
          v19 = 1119;
          Arguments[0] = (va_list)Buffer;
          Arguments[1] = (va_list)v60;
          *(_QWORD *)&v44 = v63;
        }
        if ( !LoadStringW(g_hInstance, v19, Source, 80) )
          goto LABEL_57;
        StringW = FormatMessageW(0x2400u, Source, 0, 0, lpBuffer, 0x100u, Arguments);
        goto LABEL_56;
      }
      v21 = 0;
      v22 = 0;
      for ( i = 0; i < 0x1Fu; ++i )
      {
        if ( ((a1->Type.MonthlyDate.rgfDays >> i) & 1) != 0 && ++v22 == 1 )
          v21 = i + 1;
      }
      if ( a1->Type.MonthlyDate.rgfMonths == 4095 )
      {
        v24 = 1116;
        if ( v22 != 1 )
          v24 = 1124;
        if ( !LoadStringW(g_hInstance, v24, Source, 80) )
          goto LABEL_57;
        DaysInterval = v21;
        goto LABEL_34;
      }
      StringCchPrintfW(v48, 0x10u, v46, v21);
      result = GetMonthsString(a1->Type.MonthlyDate.rgfMonths, v63, v30);
      if ( result < 0 )
        return result;
      v31 = 1117;
      Arguments[0] = (va_list)v48;
      Arguments[1] = (va_list)v63;
      if ( v22 != 1 )
        v31 = 1125;
    }
    else
    {
      result = GetDaysOfWeekString(a1->Type.Weekly.rgfDaysOfTheWeek, v60, 1u);
      if ( result < 0 )
        return result;
      if ( a1->Type.Daily.DaysInterval == 1 )
      {
        if ( !LoadStringW(g_hInstance, 0x45Au, Source, 80) )
          goto LABEL_57;
        StringCchPrintfW(lpBuffer, 0x100u, Source, v60);
        goto LABEL_35;
      }
      StringCchPrintfW(v48, 0x10u, v46, a1->Type.Daily.DaysInterval);
      v31 = 1115;
      Arguments[0] = (va_list)v60;
      Arguments[1] = (va_list)v48;
    }
    if ( !LoadStringW(g_hInstance, v31, Source, 80)
      || !FormatMessageW(0x2400u, Source, 0, 0, lpBuffer, 0x100u, Arguments) )
    {
      goto LABEL_57;
    }
  }
LABEL_35:
  if ( v7 )
  {
    v26 = LoadStringW(g_hInstance, v7, v62, 512);
    goto LABEL_37;
  }
  wStartHour = a1->wStartHour;
  Time = 0;
  Time.wHour = wStartHour;
  Time.wMinute = a1->wStartMinute;
  if ( !GetTimeFormatW(0x400u, 2u, &Time, 0, TimeStr, 32) )
    goto LABEL_57;
  MinutesInterval = a1->MinutesInterval;
  if ( MinutesInterval )
  {
    v34 = MinutesInterval;
    v35 = 60 * (MinutesInterval / 0x3C);
    if ( MinutesInterval == v35 )
      v34 = MinutesInterval / 0x3C;
    StringCchPrintfW(v51, 0x10u, v46, v34);
    if ( !LoadStringW(g_hInstance, (MinutesInterval != v35) + 1097, v56, 32) )
      goto LABEL_57;
    if ( (a1->rgFlags & 0x20000) != 0 )
    {
      for ( j = a1->wStartMinute + LOWORD(a1->MinutesDuration) + 60 * a1->wStartHour; j > 0x5A0u; j -= 1440 )
        ;
      Time.wHour = j / 0x3Cu;
      Time.wMinute = j % 0x3Cu;
      if ( !GetTimeFormatW(0x400u, 2u, &Time, 0, v55, 32) )
        goto LABEL_57;
      v37 = 1094;
      Arguments[0] = (va_list)v51;
      Arguments[1] = (va_list)v56;
      *(_QWORD *)&v44 = TimeStr;
      *((_QWORD *)&v44 + 1) = v55;
    }
    else
    {
      MinutesDuration = a1->MinutesDuration;
      v39 = MinutesDuration;
      v40 = 60 * (MinutesDuration / 0x3C);
      if ( MinutesDuration == v40 )
        v39 = MinutesDuration / 0x3C;
      StringCchPrintfW(v52, 0x10u, v46, v39);
      if ( MinutesDuration == v40 )
        v6 = 1097;
      if ( !LoadStringW(g_hInstance, v6, v55, 32) )
        goto LABEL_57;
      v37 = 1122;
      Arguments[0] = (va_list)v51;
      Arguments[1] = (va_list)v56;
      *(_QWORD *)&v44 = TimeStr;
      *((_QWORD *)&v44 + 1) = v52;
      v45 = v55;
    }
    if ( !LoadStringW(g_hInstance, v37, Source, 80) || !FormatMessageW(0x2400u, Source, 0, 0, v61, 0x100u, Arguments) )
      goto LABEL_57;
  }
  else
  {
    if ( !LoadStringW(g_hInstance, 0x445u, Source, 80) )
      goto LABEL_57;
    StringCchPrintfW(v61, 0x100u, Source, TimeStr);
  }
  Time.wYear = a1->wBeginYear;
  Time.wMonth = a1->wBeginMonth;
  Time.wDay = a1->wBeginDay;
  if ( !GetDateFormatW(0x400u, 1u, &Time, 0, DateStr, 64) )
    goto LABEL_57;
  if ( a1->TriggerType )
  {
    if ( (a1->rgFlags & 1) != 0 )
    {
      Time.wYear = a1->wEndYear;
      Time.wMonth = a1->wEndMonth;
      Time.wDay = a1->wEndDay;
      if ( !GetDateFormatW(0x400u, 1u, &Time, 0, v59, 64) )
        goto LABEL_57;
      v41 = 1095;
      Arguments[0] = (va_list)v61;
      Arguments[1] = (va_list)lpBuffer;
      *(_QWORD *)&v44 = DateStr;
      *((_QWORD *)&v44 + 1) = v59;
    }
    else
    {
      v41 = 1096;
      Arguments[0] = (va_list)v61;
      Arguments[1] = (va_list)lpBuffer;
      *(_QWORD *)&v44 = DateStr;
    }
  }
  else
  {
    v41 = 1110;
    Arguments[0] = (va_list)v61;
    Arguments[1] = (va_list)DateStr;
  }
  if ( LoadStringW(g_hInstance, v41, Source, 80) )
  {
    v26 = FormatMessageW(0x2400u, Source, 0, 0, v62, 0x200u, Arguments);
LABEL_37:
    if ( v26 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v62[v27] );
      v28 = (unsigned int)(v27 + 1);
      v29 = (unsigned __int16 *)CoTaskMemAlloc(2 * v28);
      *a2 = v29;
      if ( !v29 )
        return -2147024882;
      StringCchCopyW(v29, v28, v62);
      return 0;
    }
  }
LABEL_57:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008688  mov     [rsp-8+arg_10], rbx
0x18000868d  push    rbp
0x18000868e  push    rsi
0x18000868f  push    rdi
0x180008690  push    r12
0x180008692  push    r13
0x180008694  push    r14
0x180008696  push    r15
0x180008698  lea     rbp, [rsp-1090h]
0x1800086a0  mov     eax, 1190h
0x1800086a5  call    _alloca_probe
0x1800086aa  sub     rsp, rax
0x1800086ad  mov     rax, cs:__security_cookie
0x1800086b4  xor     rax, rsp
0x1800086b7  mov     [rbp+10C0h+var_40], rax
0x1800086be  xorps   xmm0, xmm0
0x1800086c1  mov     r12, rdx
0x1800086c4  mov     rsi, rcx
0x1800086c7  xor     r13d, r13d
0x1800086ca  mov     [rdx], r13
0x1800086cd  lea     rcx, [rbp+10C0h+var_C40]; void *
0x1800086d4  mov     eax, dword ptr cs:aD; "%d"
0x1800086da  mov     ebx, 200h
0x1800086df  mov     dword ptr [rsp+11C0h+var_1148], eax
0x1800086e3  mov     r8d, ebx; Size
0x1800086e6  movzx   eax, word ptr cs:aD+4; ""
0x1800086ed  xor     edx, edx; Val
0x1800086ef  mov     [rsp+11C0h+var_1144], ax
0x1800086f4  movups  xmmword ptr [rbp+10C0h+var_1140], xmm0
0x1800086f8  movups  [rbp+10C0h+var_1130], xmm0
0x1800086fc  call    memset_0
0x180008701  xor     edx, edx; Val
0x180008703  lea     r8d, [r13+40h]; Size
0x180008707  lea     rcx, [rbp+10C0h+Buffer]; void *
0x18000870e  call    memset_0
0x180008713  xor     edx, edx; Val
0x180008715  lea     rcx, [rbp+10C0h+var_440]; void *
0x18000871c  mov     r8d, 400h; Size
0x180008722  call    memset_0
0x180008727  xor     edx, edx; Val
0x180008729  lea     rcx, [rbp+10C0h+Source]; void *
0x18000872d  mov     r8d, 0A0h; Size
0x180008733  call    memset_0
0x180008738  mov     r8d, ebx; Size
0x18000873b  lea     rcx, [rbp+10C0h+var_EC0]; void *
0x180008742  xor     edx, edx; Val
0x180008744  call    memset_0
0x180008749  xor     eax, eax
0x18000874b  lea     r8d, [r13+1]; unsigned int
0x18000874f  test    dword ptr [rsi+1Ch], 10000h
0x180008756  lea     r9d, [r13+1Fh]
0x18000875a  xorps   xmm0, xmm0
0x18000875d  mov     [rsp+11C0h+var_1150], rax
0x180008762  movups  xmmword ptr [rsp+11C0h+var_1170], xmm0
0x180008767  lea     ebx, [rax+50h]
0x18000876a  mov     r15d, 436h
0x180008770  movups  [rsp+11C0h+var_1160], xmm0
0x180008775  mov     r14d, 100h
0x18000877b  jz      short loc_180008789
0x18000877d  lea     edi, [r15+2Dh]
0x180008781  mov     r14d, r8d
0x180008784  jmp     loc_18000896E
0x180008789  mov     ecx, [rsi+20h]
0x18000878c  mov     edi, r13d
0x18000878f  test    ecx, ecx
0x180008791  jz      short loc_180008781
0x180008793  sub     ecx, r8d
0x180008796  jz      loc_180008B40
0x18000879c  sub     ecx, r8d
0x18000879f  jz      loc_180008A53
0x1800087a5  sub     ecx, r8d
0x1800087a8  jz      loc_1800088DD
0x1800087ae  sub     ecx, r8d
0x1800087b1  jz      short loc_1800087E1
0x1800087b3  sub     ecx, r8d
0x1800087b6  jz      short loc_1800087DA
0x1800087b8  sub     ecx, r8d
0x1800087bb  jz      short loc_1800087D3
0x1800087bd  cmp     ecx, r8d
0x1800087c0  jz      short loc_1800087CC
0x1800087c2  mov     eax, 8007000Dh
0x1800087c7  jmp     loc_180008FE6
0x1800087cc  mov     edi, 46Ah
0x1800087d1  jmp     short loc_180008781
0x1800087d3  mov     edi, 443h
0x1800087d8  jmp     short loc_180008781
0x1800087da  mov     edi, 442h
0x1800087df  jmp     short loc_180008781
0x1800087e1  movzx   edx, word ptr [rsi+24h]
0x1800087e5  lea     r8, [rbp+10C0h+Buffer]; lpBuffer
0x1800087ec  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800087f3  add     edx, r15d; uID
0x1800087f6  mov     r9d, 20h ; ' '; cchBufferMax
0x1800087fc  call    cs:__imp_LoadStringW
0x180008802  test    eax, eax
0x180008804  jz      loc_180008B6B
0x18000880a  movzx   ecx, word ptr [rsi+26h]; unsigned __int16
0x18000880e  lea     rdx, [rbp+10C0h+var_C40]; unsigned __int16 *
0x180008815  call    ?GetDaysOfWeekString@@YAJGPEAGI@Z; GetDaysOfWeekString(ushort,ushort *,uint)
0x18000881a  test    eax, eax
0x18000881c  js      loc_180008FE6
0x180008822  movzx   ecx, word ptr [rsi+28h]; unsigned __int16
0x180008826  mov     eax, 0FFFh
0x18000882b  cmp     cx, ax
0x18000882e  jnz     short loc_18000884F
0x180008830  lea     rax, [rbp+10C0h+Buffer]
0x180008837  mov     edx, 45Eh
0x18000883c  mov     [rsp+11C0h+var_1170], rax
0x180008841  lea     rax, [rbp+10C0h+var_C40]
0x180008848  mov     [rsp+11C0h+var_1170+8], rax
0x18000884d  jmp     short loc_18000888C
0x18000884f  lea     rdx, [rbp+10C0h+var_440]; unsigned __int16 *
0x180008856  call    ?GetMonthsString@@YAJGPEAGI@Z; GetMonthsString(ushort,ushort *,uint)
0x18000885b  test    eax, eax
0x18000885d  js      loc_180008FE6
0x180008863  lea     rax, [rbp+10C0h+Buffer]
0x18000886a  mov     edx, 45Fh; uID
0x18000886f  mov     [rsp+11C0h+var_1170], rax
0x180008874  lea     rax, [rbp+10C0h+var_C40]
0x18000887b  mov     [rsp+11C0h+var_1170+8], rax
0x180008880  lea     rax, [rbp+10C0h+var_440]
0x180008887  mov     qword ptr [rsp+11C0h+var_1160], rax
0x18000888c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180008893  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x180008897  mov     r9d, ebx; cchBufferMax
0x18000889a  call    cs:__imp_LoadStringW
0x1800088a0  test    eax, eax
0x1800088a2  jz      loc_180008B6B
0x1800088a8  lea     rax, [rsp+11C0h+var_1170]
0x1800088ad  xor     r9d, r9d; dwLanguageId
0x1800088b0  mov     [rsp+11C0h+Arguments], rax; Arguments
0x1800088b5  lea     rdx, [rbp+10C0h+Source]; lpSource
0x1800088b9  lea     rax, [rbp+10C0h+var_EC0]
0x1800088c0  mov     [rsp+11C0h+nSize], r14d; nSize
0x1800088c5  xor     r8d, r8d; dwMessageId
0x1800088c8  mov     [rsp+11C0h+lpBuffer], rax; lpBuffer
0x1800088cd  mov     ecx, 2400h; dwFlags
0x1800088d2  call    cs:__imp_FormatMessageW
0x1800088d8  jmp     loc_180008B63
0x1800088dd  mov     r14d, r13d
0x1800088e0  mov     ebx, r13d
0x1800088e3  mov     edx, r13d
0x1800088e6  mov     eax, [rsi+24h]
0x1800088e9  mov     cl, dl
0x1800088eb  shr     eax, cl
0x1800088ed  test    r8b, al
0x1800088f0  jz      short loc_180008900
0x1800088f2  add     bx, r8w
0x1800088f6  cmp     bx, r8w
0x1800088fa  jnz     short loc_180008900
0x1800088fc  lea     r14d, [r8+rdx]
0x180008900  add     dx, r8w
0x180008904  cmp     dx, r9w
0x180008908  jb      short loc_1800088E6
0x18000890a  mov     eax, 0FFFh
0x18000890f  cmp     [rsi+28h], ax
0x180008913  jnz     loc_1800089F1
0x180008919  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180008920  cmp     bx, r8w
0x180008924  mov     edx, 45Ch
0x180008929  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x18000892d  mov     ebx, 50h ; 'P'
0x180008932  mov     r9d, ebx; cchBufferMax
0x180008935  lea     eax, [rdx+8]
0x180008938  cmovnz  edx, eax; uID
0x18000893b  call    cs:__imp_LoadStringW
0x180008941  test    eax, eax
0x180008943  jz      loc_180008B6B
0x180008949  movzx   r9d, r14w
0x18000894d  mov     edx, 100h; unsigned __int64
0x180008952  lea     r8, [rbp+10C0h+Source]; unsigned __int16 *
0x180008956  lea     rcx, [rbp+10C0h+var_EC0]; unsigned __int16 *
0x18000895d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008962  mov     r14d, 1
0x180008968  mov     r9d, 1Fh
0x18000896e  mov     eax, edi
0x180008970  test    edi, edi
0x180008972  jz      loc_180008BA9
0x180008978  sub     eax, 442h
0x18000897d  jz      short loc_180008993
0x18000897f  sub     eax, 1
0x180008982  jz      short loc_180008993
0x180008984  sub     eax, 1
0x180008987  jz      short loc_180008993
0x180008989  sub     eax, r9d
0x18000898c  jz      short loc_180008993
0x18000898e  cmp     eax, 7
0x180008991  jnz     short loc_1800089B7
0x180008993  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000899a  lea     r8, [rbp+10C0h+var_840]; lpBuffer
0x1800089a1  mov     r9d, 200h; cchBufferMax
0x1800089a7  mov     edx, edi; uID
0x1800089a9  call    cs:__imp_LoadStringW
0x1800089af  test    eax, eax
0x1800089b1  jz      loc_180008B6B
0x1800089b7  lea     rcx, [rbp+10C0h+var_840]
0x1800089be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800089c2  inc     rax
0x1800089c5  cmp     [rcx+rax*2], r13w
0x1800089ca  jnz     short loc_1800089C2
0x1800089cc  inc     eax
0x1800089ce  mov     ebx, eax
0x1800089d0  lea     rcx, [rax+rax]; cb
0x1800089d4  call    cs:__imp_CoTaskMemAlloc
0x1800089da  mov     [r12], rax
0x1800089de  test    rax, rax
0x1800089e1  jnz     loc_180008FD2
0x1800089e7  mov     eax, 8007000Eh
0x1800089ec  jmp     loc_180008FE6
0x1800089f1  movzx   r9d, r14w
0x1800089f5  lea     r8, [rsp+11C0h+var_1148]; unsigned __int16 *
0x1800089fa  mov     edx, 10h; unsigned __int64
0x1800089ff  lea     rcx, [rbp+10C0h+var_1140]; unsigned __int16 *
0x180008a03  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008a08  movzx   ecx, word ptr [rsi+28h]; unsigned __int16
0x180008a0c  lea     rdx, [rbp+10C0h+var_440]; unsigned __int16 *
0x180008a13  call    ?GetMonthsString@@YAJGPEAGI@Z; GetMonthsString(ushort,ushort *,uint)
0x180008a18  test    eax, eax
0x180008a1a  js      loc_180008FE6
0x180008a20  lea     rax, [rbp+10C0h+var_1140]
0x180008a24  mov     edx, 45Dh
0x180008a29  mov     [rsp+11C0h+var_1170], rax
0x180008a2e  mov     r14d, 1
0x180008a34  lea     rax, [rbp+10C0h+var_440]
0x180008a3b  cmp     bx, r14w
0x180008a3f  mov     [rsp+11C0h+var_1170+8], rax
0x180008a44  lea     eax, [rdx+8]
0x180008a47  cmovnz  edx, eax
0x180008a4a  lea     ebx, [r14+4Fh]
0x180008a4e  jmp     loc_180008AEC
0x180008a53  movzx   ecx, word ptr [rsi+26h]; unsigned __int16
0x180008a57  lea     rdx, [rbp+10C0h+var_C40]; unsigned __int16 *
0x180008a5e  call    ?GetDaysOfWeekString@@YAJGPEAGI@Z; GetDaysOfWeekString(ushort,ushort *,uint)
0x180008a63  test    eax, eax
0x180008a65  js      loc_180008FE6
0x180008a6b  mov     r14d, 1
0x180008a71  cmp     [rsi+24h], r14w
0x180008a76  jnz     short loc_180008ABA
0x180008a78  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180008a7f  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x180008a83  mov     r9d, ebx; cchBufferMax
0x180008a86  mov     edx, 45Ah; uID
0x180008a8b  call    cs:__imp_LoadStringW
0x180008a91  test    eax, eax
0x180008a93  jz      loc_180008B6B
0x180008a99  lea     r9, [rbp+10C0h+var_C40]
0x180008aa0  mov     edx, 100h; unsigned __int64
0x180008aa5  lea     r8, [rbp+10C0h+Source]; unsigned __int16 *
0x180008aa9  lea     rcx, [rbp+10C0h+var_EC0]; unsigned __int16 *
0x180008ab0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008ab5  jmp     loc_180008968
0x180008aba  movzx   r9d, word ptr [rsi+24h]
0x180008abf  lea     r8, [rsp+11C0h+var_1148]; unsigned __int16 *
0x180008ac4  mov     edx, 10h; unsigned __int64
0x180008ac9  lea     rcx, [rbp+10C0h+var_1140]; unsigned __int16 *
0x180008acd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008ad2  lea     rax, [rbp+10C0h+var_C40]
0x180008ad9  mov     edx, 45Bh; uID
0x180008ade  mov     [rsp+11C0h+var_1170], rax
0x180008ae3  lea     rax, [rbp+10C0h+var_1140]
0x180008ae7  mov     [rsp+11C0h+var_1170+8], rax
0x180008aec  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180008af3  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x180008af7  mov     r9d, ebx; cchBufferMax
0x180008afa  call    cs:__imp_LoadStringW
0x180008b00  test    eax, eax
0x180008b02  jz      short loc_180008B6B
0x180008b04  lea     rax, [rsp+11C0h+var_1170]
0x180008b09  xor     r9d, r9d; dwLanguageId
0x180008b0c  mov     [rsp+11C0h+Arguments], rax; Arguments
0x180008b11  lea     rdx, [rbp+10C0h+Source]; lpSource
0x180008b15  lea     rax, [rbp+10C0h+var_EC0]
0x180008b1c  mov     [rsp+11C0h+nSize], 100h; nSize
0x180008b24  xor     r8d, r8d; dwMessageId
0x180008b27  mov     [rsp+11C0h+lpBuffer], rax; lpBuffer
0x180008b2c  mov     ecx, 2400h; dwFlags
0x180008b31  call    cs:__imp_FormatMessageW
0x180008b37  test    eax, eax
0x180008b39  jz      short loc_180008B6B
0x180008b3b  jmp     loc_180008968
0x180008b40  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180008b47  cmp     [rsi+24h], r8w
0x180008b4c  jnz     short loc_180008B86
0x180008b4e  mov     r9d, r14d; cchBufferMax
0x180008b51  lea     r8, [rbp+10C0h+var_EC0]; lpBuffer
0x180008b58  mov     edx, 458h; uID
0x180008b5d  call    cs:__imp_LoadStringW
0x180008b63  test    eax, eax
0x180008b65  jnz     loc_180008962
0x180008b6b  call    cs:__imp_GetLastError
0x180008b71  test    eax, eax
0x180008b73  jle     loc_180008FE6
0x180008b79  movzx   eax, ax
0x180008b7c  or      eax, 80070000h
0x180008b81  jmp     loc_180008FE6
0x180008b86  mov     r9d, ebx; cchBufferMax
0x180008b89  lea     r8, [rbp+10C0h+Source]; lpBuffer
0x180008b8d  mov     edx, 457h; uID
0x180008b92  call    cs:__imp_LoadStringW
0x180008b98  test    eax, eax
  ... truncated ...
```
