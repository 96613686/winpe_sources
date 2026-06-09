# CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)

- ea: `0x180006dd0`
- end: `0x1800072f9`
- name: `?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z`
- size: `1321`
- prototype: `__int64 __fastcall(__int64, const FILETIME ***)`
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003f00`
- `0x1800065c0`
- `0x180007330`
- `0x180009fd0`
- `0x18000a148`
- `0x18000a254`

## callees

- `0x180004e50`
- `0x180006dd0`
- `0x1800076a0`
- `0x1800078d0`
- `0x180008550`
- `0x18000ba44`
- `0x18000ca14`
- `0x18000daf0`
- `0x1800100b8`
- `0x180011980`
- `0x180013010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180006e6e`
- `ADVAPI32!SetThreadToken` at `0x180007202`
- `ADVAPI32!SetThreadToken` at `0x180006e6e`
- `ADVAPI32!SetThreadToken` at `0x180007202`
- `KERNEL32!GetLastError` at `0x180006e78`
- `KERNEL32!GetLastError` at `0x180006f32`
- `KERNEL32!GetLastError` at `0x180006f88`
- `KERNEL32!GetLastError` at `0x180006ff3`
- `KERNEL32!GetLastError` at `0x180007059`
- `KERNEL32!GetLastError` at `0x180007210`
- `KERNEL32!GetLastError` at `0x180007237`
- `KERNEL32!GetLastError` at `0x180006e78`
- `KERNEL32!GetLastError` at `0x180006f32`
- `KERNEL32!GetLastError` at `0x180006f88`
- `KERNEL32!GetLastError` at `0x180006ff3`
- `KERNEL32!GetLastError` at `0x180007059`
- `KERNEL32!GetLastError` at `0x180007210`
- `KERNEL32!GetLastError` at `0x180007237`
- `KERNEL32!FileTimeToSystemTime` at `0x180006f28`
- `KERNEL32!FileTimeToSystemTime` at `0x180006f28`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180006f7e`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180006f7e`
- `KERNEL32!GetDateFormatEx` at `0x180006fe6`
- `KERNEL32!GetDateFormatEx` at `0x1800070e3`
- `KERNEL32!GetDateFormatEx` at `0x180006fe6`
- `KERNEL32!GetDateFormatEx` at `0x1800070e3`
- `KERNEL32!GetTimeFormatEx` at `0x18000704c`
- `KERNEL32!GetTimeFormatEx` at `0x18000714f`
- `KERNEL32!GetTimeFormatEx` at `0x18000704c`
- `KERNEL32!GetTimeFormatEx` at `0x18000714f`

## pseudocode

```c
__int64 __fastcall CManagerThread::PublishProtectionState(__int64 a1, const FILETIME ***a2)
{
  const FILETIME ***v2; // rdi
  WCHAR *v3; // rax
  WCHAR *lpDateStr; // rsi
  __int64 v5; // rbx
  signed int LastError; // eax
  signed int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  const FILETIME *v10; // rcx
  unsigned int dwLowDateTime; // r13d
  int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  int DateFormat; // eax
  __int64 cchDate; // r15
  signed int v17; // eax
  int TimeFormat; // eax
  int v19; // r12d
  signed int v20; // eax
  unsigned int v21; // r14d
  signed int v22; // eax
  PVOID *v23; // rcx
  signed int v24; // eax
  signed __int32 v25; // eax
  bool v26; // cc
  __int64 result; // rax
  WCHAR *v28; // [rsp+40h] [rbp-78h] BYREF
  signed int v29; // [rsp+48h] [rbp-70h]
  unsigned int v30; // [rsp+4Ch] [rbp-6Ch]
  const FILETIME ***v31; // [rsp+50h] [rbp-68h]
  int v32; // [rsp+58h] [rbp-60h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+60h] [rbp-58h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-48h] BYREF

  v2 = a2;
  v31 = a2;
  v3 = (WCHAR *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  lpDateStr = v3 + 12;
  v28 = v3 + 12;
  if ( *((_DWORD *)v3 + 2) )
  {
    if ( *((int *)v3 + 4) >= 0 )
    {
      v5 = *(_QWORD *)v3;
      ATL::CStringData::Release((ATL::CStringData *)v3);
      lpDateStr = (WCHAR *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5) + 24);
      v28 = lpDateStr;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetLength(&v28, 0);
    }
  }
  if ( !SetThreadToken(0, *(HANDLE *)&(**v2)[1]) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 126;
LABEL_11:
      WPP_SF_d(v8[2], v9, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, (unsigned int)v7);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v7 = 0;
  v10 = **v2;
  dwLowDateTime = v10[18].dwLowDateTime;
  if ( dwLowDateTime <= 8 )
    goto LABEL_56;
  SystemTime = 0;
  LocalTime = 0;
  v12 = dwLowDateTime | 0xFF;
  if ( (_BYTE)dwLowDateTime != 0xF0 )
    v12 = dwLowDateTime;
  dwLowDateTime = v12;
  v30 = v12;
  v10 = (const FILETIME *)((char *)v10 + 148);
  if ( !v10->dwHighDateTime && !v10->dwLowDateTime )
  {
LABEL_56:
    if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 1) != 0 )
      McTemplateU0qz_EventWriteTransfer(v10, FhStateChanged, dwLowDateTime, lpDateStr);
    goto LABEL_58;
  }
  if ( FileTimeToSystemTime(v10, &SystemTime) )
  {
    if ( !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 128;
        goto LABEL_11;
      }
      goto LABEL_58;
    }
    DateFormat = GetDateFormatEx(0, 0x41u, &LocalTime, 0, 0, 0, 0);
    cchDate = DateFormat;
    if ( DateFormat <= 0 )
    {
      v17 = GetLastError();
      v7 = v17;
      if ( v17 > 0 )
        v7 = (unsigned __int16)v17 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 129;
        goto LABEL_11;
      }
      goto LABEL_58;
    }
    TimeFormat = GetTimeFormatEx(0, 2u, &LocalTime, 0, 0, 0);
    v19 = TimeFormat;
    if ( TimeFormat <= 0 )
    {
      v20 = GetLastError();
      v7 = v20;
      if ( v20 > 0 )
        v7 = (unsigned __int16)v20 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 130;
        goto LABEL_11;
      }
      goto LABEL_58;
    }
    v21 = TimeFormat + cchDate;
    if ( (int)((*((_DWORD *)lpDateStr - 3) - (TimeFormat + cchDate)) | (1 - *((_DWORD *)lpDateStr - 2))) < 0 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((__int64 *)&v28, v21);
        lpDateStr = v28;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v32) )
        {
          v29 = v32;
          if ( v32 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                133,
                &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                (unsigned int)v32);
            lpDateStr = v28;
            v7 = v29;
            v2 = v31;
            __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800071B4);
            goto LABEL_58;
          }
          lpDateStr = v28;
          v7 = v29;
          v2 = v31;
          dwLowDateTime = v30;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800071C4);
          goto LABEL_55;
        }
      }
    }
    if ( GetDateFormatEx(0, 0x41u, &LocalTime, 0, lpDateStr, cchDate, 0) != (_DWORD)cchDate )
    {
      v7 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          131,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          2147500037LL);
      goto LABEL_58;
    }
    lpDateStr[cchDate - 1] = 32;
    if ( GetTimeFormatEx(0, 2u, &LocalTime, 0, &lpDateStr[cchDate], v19) != v19 )
    {
      v7 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          132,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          2147500037LL);
      goto LABEL_58;
    }
    if ( v21 == -1 )
      v21 = ATL::CSimpleStringT<unsigned short,0>::StringLength(lpDateStr);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(&v28, v21);
LABEL_55:
    dwLowDateTime |= 0x200u;
    goto LABEL_56;
  }
  v13 = GetLastError();
  v7 = v13;
  if ( v13 > 0 )
    v7 = (unsigned __int16)v13 | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 127;
    goto LABEL_11;
  }
LABEL_58:
  if ( SetThreadToken(0, 0) )
  {
LABEL_67:
    v23 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_68;
  }
  if ( v7 >= 0 )
  {
    v22 = GetLastError();
    v7 = v22;
    if ( v22 > 0 )
      v7 = (unsigned __int16)v22 | 0x80070000;
  }
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      134,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      (unsigned int)v24);
    goto LABEL_67;
  }
LABEL_68:
  if ( v7 < 0 && v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 4) != 0 )
    WPP_SF_s(v23[2], 135, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, "SUCCEEDED(hr)");
  v25 = _InterlockedExchangeAdd((volatile signed __int32 *)lpDateStr - 2, 0xFFFFFFFF);
  v26 = v25 <= 1;
  result = (unsigned int)(v25 - 1);
  if ( v26 )
    result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)lpDateStr - 3) + 8LL))(*((_QWORD *)lpDateStr - 3));
  if ( *v2 )
    return ((__int64 (__fastcall *)(const FILETIME **))SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs)(*v2);
  return result;
}

```

## disassembly

```asm
0x180006dd0  mov     [rsp+arg_0], rbx
0x180006dd5  mov     [rsp+arg_10], rsi
0x180006dda  push    rdi
0x180006ddb  push    r12
0x180006ddd  push    r13
0x180006ddf  push    r14
0x180006de1  push    r15
0x180006de3  sub     rsp, 90h
0x180006dea  mov     rax, cs:__security_cookie
0x180006df1  xor     rax, rsp
0x180006df4  mov     [rsp+0B8h+var_38], rax
0x180006dfc  mov     rdi, rdx
0x180006dff  mov     [rsp+0B8h+var_68], rdx
0x180006e04  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006e0b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006e12  mov     rax, [rax+18h]
0x180006e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1b  lea     rsi, [rax+18h]
0x180006e1f  mov     [rsp+0B8h+var_78], rsi
0x180006e24  lea     rcx, [rsi-18h]; this
0x180006e28  cmp     dword ptr [rcx+8], 0
0x180006e2c  jz      short loc_180006E62
0x180006e2e  cmp     dword ptr [rcx+10h], 0
0x180006e32  jge     short loc_180006E42
0x180006e34  xor     edx, edx
0x180006e36  lea     rcx, [rsp+0B8h+var_78]
0x180006e3b  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180006e40  jmp     short loc_180006E62
0x180006e42  mov     rbx, [rcx]
0x180006e45  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180006e4a  mov     rax, [rbx]
0x180006e4d  mov     rcx, rbx
0x180006e50  mov     rax, [rax+18h]
0x180006e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e59  lea     rsi, [rax+18h]
0x180006e5d  mov     [rsp+0B8h+var_78], rsi
0x180006e62  mov     rax, [rdi]
0x180006e65  mov     rdx, [rax]
0x180006e68  mov     rdx, [rdx+8]; Token
0x180006e6c  xor     ecx, ecx; Thread
0x180006e6e  call    cs:__imp_SetThreadToken
0x180006e74  test    eax, eax
0x180006e76  jnz     short loc_180006ECB
0x180006e78  call    cs:__imp_GetLastError
0x180006e7e  mov     ebx, eax
0x180006e80  test    eax, eax
0x180006e82  jle     short loc_180006E8D
0x180006e84  movzx   ebx, ax
0x180006e87  or      ebx, 80070000h
0x180006e8d  lea     r14, WPP_GLOBAL_Control
0x180006e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e9b  cmp     rcx, r14
0x180006e9e  jz      loc_1800071FE
0x180006ea4  test    byte ptr [rcx+1Ch], 1
0x180006ea8  jz      loc_1800071FE
0x180006eae  mov     edx, 7Eh ; '~'
0x180006eb3  mov     r9d, ebx
0x180006eb6  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006ebd  mov     rcx, [rcx+10h]
0x180006ec1  call    WPP_SF_d
0x180006ec6  jmp     loc_1800071FE
0x180006ecb  xor     r14d, r14d
0x180006ece  mov     ebx, r14d
0x180006ed1  mov     rax, [rdi]
0x180006ed4  mov     rcx, [rax]
0x180006ed7  mov     r13d, [rcx+90h]
0x180006ede  cmp     r13d, 8
0x180006ee2  jbe     loc_1800071DC
0x180006ee8  xorps   xmm0, xmm0
0x180006eeb  movups  xmmword ptr [rsp+0B8h+SystemTime.wYear], xmm0
0x180006ef0  xorps   xmm1, xmm1
0x180006ef3  movups  xmmword ptr [rsp+0B8h+LocalTime.wYear], xmm1
0x180006ef8  mov     eax, r13d
0x180006efb  or      eax, 0FFh
0x180006f00  cmp     r13b, 0F0h
0x180006f04  cmovnz  eax, r13d
0x180006f08  mov     r13d, eax
0x180006f0b  mov     [rsp+0B8h+var_6C], eax
0x180006f0f  add     rcx, 94h; lpFileTime
0x180006f16  cmp     [rcx+4], ebx
0x180006f19  jnz     short loc_180006F23
0x180006f1b  cmp     [rcx], ebx
0x180006f1d  jz      loc_1800071DC
0x180006f23  lea     rdx, [rsp+0B8h+SystemTime]; lpSystemTime
0x180006f28  call    cs:__imp_FileTimeToSystemTime
0x180006f2e  test    eax, eax
0x180006f30  jnz     short loc_180006F72
0x180006f32  call    cs:__imp_GetLastError
0x180006f38  mov     ebx, eax
0x180006f3a  test    eax, eax
0x180006f3c  jle     short loc_180006F47
0x180006f3e  movzx   ebx, ax
0x180006f41  or      ebx, 80070000h
0x180006f47  lea     r14, WPP_GLOBAL_Control
0x180006f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f55  cmp     rcx, r14
0x180006f58  jz      loc_1800071FE
0x180006f5e  test    byte ptr [rcx+1Ch], 1
0x180006f62  jz      loc_1800071FE
0x180006f68  mov     edx, 7Fh
0x180006f6d  jmp     loc_180006EB3
0x180006f72  lea     r8, [rsp+0B8h+LocalTime]; lpLocalTime
0x180006f77  lea     rdx, [rsp+0B8h+SystemTime]; lpUniversalTime
0x180006f7c  xor     ecx, ecx; lpTimeZoneInformation
0x180006f7e  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180006f84  test    eax, eax
0x180006f86  jnz     short loc_180006FC8
0x180006f88  call    cs:__imp_GetLastError
0x180006f8e  mov     ebx, eax
0x180006f90  test    eax, eax
0x180006f92  jle     short loc_180006F9D
0x180006f94  movzx   ebx, ax
0x180006f97  or      ebx, 80070000h
0x180006f9d  lea     r14, WPP_GLOBAL_Control
0x180006fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fab  cmp     rcx, r14
0x180006fae  jz      loc_1800071FE
0x180006fb4  test    byte ptr [rcx+1Ch], 1
0x180006fb8  jz      loc_1800071FE
0x180006fbe  mov     edx, 80h
0x180006fc3  jmp     loc_180006EB3
0x180006fc8  mov     [rsp+0B8h+lpCalendar], r14; lpCalendar
0x180006fcd  mov     [rsp+0B8h+cchDate], r14d; cchDate
0x180006fd2  mov     [rsp+0B8h+lpDateStr], r14; lpDateStr
0x180006fd7  xor     r9d, r9d; lpFormat
0x180006fda  lea     r8, [rsp+0B8h+LocalTime]; lpDate
0x180006fdf  mov     edx, 41h ; 'A'; dwFlags
0x180006fe4  xor     ecx, ecx; lpLocaleName
0x180006fe6  call    cs:__imp_GetDateFormatEx
0x180006fec  movsxd  r15, eax
0x180006fef  test    eax, eax
0x180006ff1  jg      short loc_180007033
0x180006ff3  call    cs:__imp_GetLastError
0x180006ff9  mov     ebx, eax
0x180006ffb  test    eax, eax
0x180006ffd  jle     short loc_180007008
0x180006fff  movzx   ebx, ax
0x180007002  or      ebx, 80070000h
0x180007008  lea     r14, WPP_GLOBAL_Control
0x18000700f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007016  cmp     rcx, r14
0x180007019  jz      loc_1800071FE
0x18000701f  test    byte ptr [rcx+1Ch], 1
0x180007023  jz      loc_1800071FE
0x180007029  mov     edx, 81h
0x18000702e  jmp     loc_180006EB3
0x180007033  mov     [rsp+0B8h+cchDate], r14d; cchTime
0x180007038  mov     [rsp+0B8h+lpDateStr], r14; lpTimeStr
0x18000703d  xor     r9d, r9d; lpFormat
0x180007040  lea     r8, [rsp+0B8h+LocalTime]; lpTime
0x180007045  mov     edx, 2; dwFlags
0x18000704a  xor     ecx, ecx; lpLocaleName
0x18000704c  call    cs:__imp_GetTimeFormatEx
0x180007052  mov     r12d, eax
0x180007055  test    eax, eax
0x180007057  jg      short loc_180007099
0x180007059  call    cs:__imp_GetLastError
0x18000705f  mov     ebx, eax
0x180007061  test    eax, eax
0x180007063  jle     short loc_18000706E
0x180007065  movzx   ebx, ax
0x180007068  or      ebx, 80070000h
0x18000706e  lea     r14, WPP_GLOBAL_Control
0x180007075  mov     rcx, cs:WPP_GLOBAL_Control
0x18000707c  cmp     rcx, r14
0x18000707f  jz      loc_1800071FE
0x180007085  test    byte ptr [rcx+1Ch], 1
0x180007089  jz      loc_1800071FE
0x18000708f  mov     edx, 82h
0x180007094  jmp     loc_180006EB3
0x180007099  lea     r14d, [rax+r15]
0x18000709d  mov     ecx, 1
0x1800070a2  sub     ecx, [rsi-8]
0x1800070a5  mov     eax, [rsi-0Ch]
0x1800070a8  sub     eax, r14d
0x1800070ab  or      ecx, eax
0x1800070ad  jge     short loc_1800070C1
0x1800070af  mov     edx, r14d
0x1800070b2  lea     rcx, [rsp+0B8h+var_78]
0x1800070b7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800070bc  mov     rsi, [rsp+0B8h+var_78]
0x1800070c1  mov     [rsp+0B8h+lpCalendar], 0; lpCalendar
0x1800070ca  mov     [rsp+0B8h+cchDate], r15d; cchDate
0x1800070cf  mov     [rsp+0B8h+lpDateStr], rsi; lpDateStr
0x1800070d4  xor     r9d, r9d; lpFormat
0x1800070d7  lea     r8, [rsp+0B8h+LocalTime]; lpDate
0x1800070dc  mov     edx, 41h ; 'A'; dwFlags
0x1800070e1  xor     ecx, ecx; lpLocaleName
0x1800070e3  call    cs:__imp_GetDateFormatEx
0x1800070e9  cmp     eax, r15d
0x1800070ec  jz      short loc_18000712A
0x1800070ee  mov     ebx, 80004005h
0x1800070f3  lea     r14, WPP_GLOBAL_Control
0x1800070fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007101  cmp     rcx, r14
0x180007104  jz      short loc_180007125
0x180007106  test    byte ptr [rcx+1Ch], 1
0x18000710a  jz      short loc_180007125
0x18000710c  mov     edx, 83h
0x180007111  mov     r9d, ebx
0x180007114  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000711b  mov     rcx, [rcx+10h]
0x18000711f  call    WPP_SF_d
0x180007124  nop
0x180007125  jmp     loc_1800071FE
0x18000712a  mov     word ptr [rsi+r15*2-2], 20h ; ' '
0x180007132  lea     rax, [rsi+r15*2]
0x180007136  mov     [rsp+0B8h+cchDate], r12d; cchTime
0x18000713b  mov     [rsp+0B8h+lpDateStr], rax; lpTimeStr
0x180007140  xor     r9d, r9d; lpFormat
0x180007143  lea     r8, [rsp+0B8h+LocalTime]; lpTime
0x180007148  mov     edx, 2; dwFlags
0x18000714d  xor     ecx, ecx; lpLocaleName
0x18000714f  call    cs:__imp_GetTimeFormatEx
0x180007155  cmp     eax, r12d
0x180007158  jz      short loc_180007193
0x18000715a  mov     ebx, 80004005h
0x18000715f  lea     r14, WPP_GLOBAL_Control
0x180007166  mov     rcx, cs:WPP_GLOBAL_Control
0x18000716d  cmp     rcx, r14
0x180007170  jz      short loc_180007191
0x180007172  test    byte ptr [rcx+1Ch], 1
0x180007176  jz      short loc_180007191
0x180007178  mov     edx, 84h
0x18000717d  mov     r9d, ebx
0x180007180  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180007187  mov     rcx, [rcx+10h]
0x18000718b  call    WPP_SF_d
0x180007190  nop
0x180007191  jmp     short loc_1800071FE
0x180007193  cmp     r14d, 0FFFFFFFFh
0x180007197  jnz     short loc_1800071A4
0x180007199  mov     rcx, rsi
0x18000719c  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x1800071a1  mov     r14d, eax
0x1800071a4  mov     edx, r14d
0x1800071a7  lea     rcx, [rsp+0B8h+var_78]
0x1800071ac  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800071b1  nop
0x1800071b2  jmp     short loc_1800071D7
0x1800071b4  mov     rsi, [rsp+0B8h+var_78]
0x1800071b9  mov     ebx, [rsp+0B8h+var_70]
0x1800071bd  mov     rdi, [rsp+0B8h+var_68]
0x1800071c2  jmp     short loc_1800071F7
0x1800071c4  mov     rsi, [rsp+0B8h+var_78]
0x1800071c9  mov     ebx, [rsp+0B8h+var_70]
0x1800071cd  mov     rdi, [rsp+0B8h+var_68]
0x1800071d2  mov     r13d, [rsp+0B8h+var_6C]
0x1800071d7  bts     r13d, 9
0x1800071dc  test    cs:Microsoft_Windows_FileHistory_CoreEnableBits, 1
0x1800071e3  jz      short loc_1800071F7
0x1800071e5  mov     r9, rsi
0x1800071e8  mov     r8d, r13d
0x1800071eb  lea     rdx, FhStateChanged
0x1800071f2  call    McTemplateU0qz_EventWriteTransfer
0x1800071f7  lea     r14, WPP_GLOBAL_Control
0x1800071fe  xor     edx, edx; Token
0x180007200  xor     ecx, ecx; Thread
0x180007202  call    cs:__imp_SetThreadToken
0x180007208  test    eax, eax
0x18000720a  jnz     short loc_180007268
0x18000720c  test    ebx, ebx
0x18000720e  js      short loc_180007225
0x180007210  call    cs:__imp_GetLastError
0x180007216  mov     ebx, eax
0x180007218  test    eax, eax
0x18000721a  jle     short loc_180007225
0x18000721c  movzx   ebx, ax
0x18000721f  or      ebx, 80070000h
0x180007225  mov     rcx, cs:WPP_GLOBAL_Control
0x18000722c  cmp     rcx, r14
0x18000722f  jz      short loc_18000726F
0x180007231  test    byte ptr [rcx+1Ch], 1
0x180007235  jz      short loc_18000726F
0x180007237  call    cs:__imp_GetLastError
0x18000723d  test    eax, eax
0x18000723f  jle     short loc_180007249
0x180007241  movzx   eax, ax
0x180007244  or      eax, 80070000h
0x180007249  mov     edx, 86h
0x18000724e  mov     r9d, eax
0x180007251  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180007258  mov     rcx, cs:WPP_GLOBAL_Control
0x18000725f  mov     rcx, [rcx+10h]
0x180007263  call    WPP_SF_d
0x180007268  mov     rcx, cs:WPP_GLOBAL_Control
0x18000726f  test    ebx, ebx
0x180007271  jns     short loc_18000729B
0x180007273  cmp     rcx, r14
0x180007276  jz      short loc_18000729B
0x180007278  test    byte ptr [rcx+1Ch], 4
0x18000727c  jz      short loc_18000729B
0x18000727e  mov     edx, 87h
0x180007283  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x18000728a  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180007291  mov     rcx, [rcx+10h]
0x180007295  call    WPP_SF_s
0x18000729a  nop
0x18000729b  lea     rdx, [rsi-18h]
0x18000729f  mov     eax, 0FFFFFFFFh
  ... truncated ...
```
