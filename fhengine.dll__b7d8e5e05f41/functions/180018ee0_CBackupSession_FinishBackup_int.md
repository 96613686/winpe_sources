# CBackupSession::FinishBackup(int)

- ea: `0x180018ee0`
- end: `0x1800196f0`
- name: `?FinishBackup@CBackupSession@@UEAAJH@Z`
- size: `2064`
- prototype: `__int64 __fastcall(CBackupSession *this, int, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800077f0`
- `0x180007818`
- `0x1800094ec`
- `0x18000e078`
- `0x1800122d8`
- `0x1800127b0`
- `0x1800163cc`
- `0x180018ee0`
- `0x18001a4a8`
- `0x18002204c`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x180019507`
- `ADVAPI32!RegSetKeyValueW` at `0x180019507`
- `ADVAPI32!SetThreadToken` at `0x18001921a`
- `ADVAPI32!SetThreadToken` at `0x18001964f`
- `ADVAPI32!SetThreadToken` at `0x18001921a`
- `ADVAPI32!SetThreadToken` at `0x18001964f`
- `KERNEL32!GetLastError` at `0x180019224`
- `KERNEL32!GetLastError` at `0x1800195e8`
- `KERNEL32!GetLastError` at `0x18001966b`
- `KERNEL32!GetLastError` at `0x180019224`
- `KERNEL32!GetLastError` at `0x1800195e8`
- `KERNEL32!GetLastError` at `0x18001966b`
- `KERNEL32!CloseHandle` at `0x18001963a`
- `KERNEL32!CloseHandle` at `0x18001963a`
- `KERNEL32!DeleteFileW` at `0x1800195de`
- `KERNEL32!DeleteFileW` at `0x1800195de`
- `OLEAUT32!__imp_SysFreeString` at `0x180019040`
- `OLEAUT32!__imp_SysFreeString` at `0x1800190ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001915b`
- `OLEAUT32!__imp_SysFreeString` at `0x180019040`
- `OLEAUT32!__imp_SysFreeString` at `0x1800190ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18001915b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::FinishBackup(CBackupSession *this, int a2, __int64 a3)
{
  signed int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, unsigned __int64 *, __int64); // r14
  _QWORD *v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, unsigned __int64 *, __int64); // r14
  _QWORD *v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, unsigned __int64 *, __int64); // r14
  _QWORD *v17; // rax
  int v18; // r13d
  signed int LastError; // eax
  signed __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  unsigned __int64 v23; // r8
  BOOL v24; // r12d
  PVOID *v25; // rcx
  int v26; // r13d
  CBackupSession *v27; // rcx
  LSTATUS v28; // eax
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // r8
  signed int v32; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v35; // [rsp+38h] [rbp-70h] BYREF
  __int64 v36; // [rsp+40h] [rbp-68h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-58h] BYREF
  CBackupSession *v38; // [rsp+60h] [rbp-48h] BYREF

  v38 = this;
  v35 = 0;
  v36 = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, CatalogFlushStart, a3, 1, bstrString);
  if ( (*((_DWORD *)this + 86) & 0x20000000) != 0 )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    goto LABEL_102;
  }
  CBackupSession::CalculateSessionStatistics(this);
  v35 = *((unsigned int *)this + 196) + ((unsigned __int64)*((unsigned int *)this + 197) << 32);
  if ( *((_DWORD *)this + 38) )
  {
    v5 = -2147220479;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 52;
LABEL_11:
      v8 = (unsigned int)v5;
LABEL_12:
      WPP_SF_d(v6[2], v7, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v8);
      goto LABEL_101;
    }
    goto LABEL_101;
  }
  v9 = *((_QWORD *)this + 3);
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *, __int64))(*(_QWORD *)v9 + 168LL);
  v11 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"LastBackupTime");
  v5 = v10(v9, *v11, &v35, 8);
  SysFreeString(bstrString[0]);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)v5);
    goto LABEL_101;
  }
  if ( !*((_QWORD *)this + 16) )
  {
    v12 = *((_QWORD *)this + 3);
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *, __int64))(*(_QWORD *)v12 + 168LL);
    v14 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"FirstBackupTime");
    v5 = v13(v12, *v14, &v35, 8);
    SysFreeString(bstrString[0]);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v5);
      goto LABEL_101;
    }
  }
  if ( *((_DWORD *)this + 39) )
  {
    v15 = *((_QWORD *)this + 3);
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *, __int64))(*(_QWORD *)v15 + 168LL);
    v17 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"LastTargetPresentTime");
    v5 = v16(v15, *v17, &v35, 8);
    SysFreeString(bstrString[0]);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v5);
      goto LABEL_101;
    }
  }
  v18 = 0;
  if ( *((_DWORD *)this + 40) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    v18 = 1;
  }
  if ( !SetThreadToken(0, *((HANDLE *)this + 48)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)v5);
    goto LABEL_100;
  }
  _m_prefetchw((char *)this + 432);
  v20 = _InterlockedOr64((volatile signed __int64 *)this + 54, 0);
  if ( v20 == -1
    || v20 * (*((_DWORD *)this + 11) - *((_DWORD *)this + 50)) > (unsigned __int64)(20LL * *((_QWORD *)this + 53)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    *((_DWORD *)this + 94) = 1;
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 2) + 64LL))(
          *((_QWORD *)this + 2),
          0,
          &v36);
  v5 = v21;
  if ( v21 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 60;
      v8 = (unsigned int)v21;
      goto LABEL_12;
    }
    goto LABEL_101;
  }
  v22 = *((_QWORD *)this + 26);
  v23 = v35;
  if ( v35 - v22 > 80000000 * v36 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v22 = *((_QWORD *)this + 26);
      v23 = v35;
    }
    *((_DWORD *)this + 94) = 1;
  }
  if ( v23 - v22 > 0xC92A69C000LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    *((_DWORD *)this + 94) = 1;
  }
  v24 = *((_DWORD *)this + 39) && !v18 && (a2 || *((_DWORD *)this + 94));
  if ( a2 )
  {
    if ( v18 )
    {
      v25 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        v25 = (PVOID *)WPP_GLOBAL_Control;
      }
      v26 = -2147220479;
    }
    else
    {
      v25 = (PVOID *)WPP_GLOBAL_Control;
      v26 = 0;
    }
    if ( !*((_DWORD *)this + 39) )
    {
      if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
        WPP_SF_(v25[2], 64, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
      v26 = -2147220478;
    }
  }
  else
  {
    v26 = 0;
  }
  v5 = CSessionBaseRW::FlushAndBackupCatalog(
         (CBackupSession *)((char *)this + 8),
         v24,
         (const enum _PRIORITY_HINT *)this + 87,
         (int *)this + 100,
         (struct _FILETIME)&SystemTimeAsFileTime);
  if ( v5 < 0 )
  {
    if ( !SystemTimeAsFileTime.dwLowDateTime )
      goto LABEL_96;
    if ( !a2 )
      v5 = 0;
  }
  CBackupSession::CalculateSessionStatistics(this);
  if ( !*((_DWORD *)this + 287) && !*((_DWORD *)this + 286)
    || (LODWORD(bstrString[0]) = 1,
        (v28 = RegSetKeyValueW(
                 HKEY_CURRENT_USER,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
                 L"RestoreAllowed",
                 4u,
                 bstrString,
                 4u)) == 0) )
  {
    if ( SystemTimeAsFileTime.dwLowDateTime )
    {
      *((_DWORD *)this + 89) |= v5 == -2147024784;
      *((_DWORD *)this + 90) |= CBackupSession::IsChkDskRequired(v27, v5);
      if ( v5 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 66;
          goto LABEL_11;
        }
LABEL_101:
        if ( !SystemTimeAsFileTime.dwLowDateTime )
          goto LABEL_108;
        goto LABEL_102;
      }
      goto LABEL_99;
    }
    if ( v5 >= 0 )
    {
LABEL_99:
      v5 = v26;
      goto LABEL_100;
    }
LABEL_96:
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 67;
      goto LABEL_11;
    }
    goto LABEL_101;
  }
  if ( v28 > 0 )
    v5 = (unsigned __int16)v28 | 0x80070000;
  else
    v5 = v28;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
      (__int64)L"RestoreAllowed",
      v5);
LABEL_100:
  if ( v5 < 0 )
    goto LABEL_101;
LABEL_102:
  if ( *((_DWORD *)this + 101)
    && !DeleteFileW(*((LPCWSTR *)this + 15))
    && GetLastError() != 2
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (int)"FALSE",
      (__int64)"Restore Log deletion should not fail");
  }
LABEL_108:
  v29 = (void *)*((_QWORD *)this + 51);
  if ( v29 != (void *)-1LL )
  {
    CloseHandle(v29);
    *((_QWORD *)this + 51) = -1;
  }
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v32);
  }
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v30, CatalogFlushStop, v31, 1, &v38);
  *((_DWORD *)this + 199) = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018ee0  mov     r11, rsp
0x180018ee3  mov     [r11+18h], rbx
0x180018ee7  mov     [r11+20h], rsi
0x180018eeb  mov     [rsp+arg_8], edx
0x180018eef  push    rdi
0x180018ef0  push    r12
0x180018ef2  push    r13
0x180018ef4  push    r14
0x180018ef6  push    r15
0x180018ef8  sub     rsp, 80h
0x180018eff  mov     rax, cs:__security_cookie
0x180018f06  xor     rax, rsp
0x180018f09  mov     [rsp+0A8h+var_38], rax
0x180018f0e  mov     r12d, edx
0x180018f11  mov     rsi, rcx
0x180018f14  mov     [rsp+0A8h+var_48], rcx
0x180018f19  xor     ebx, ebx
0x180018f1b  mov     [r11-70h], rbx
0x180018f1f  mov     [r11-68h], rbx
0x180018f23  mov     [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], ebx
0x180018f27  lea     r15d, [rbx+1]
0x180018f2b  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, r15b
0x180018f32  jz      short loc_180018F4C
0x180018f34  lea     rax, [r11-58h]
0x180018f38  mov     [rsp+0A8h+lpData], rax
0x180018f3d  mov     r9d, r15d
0x180018f40  lea     rdx, CatalogFlushStart
0x180018f47  call    McGenEventWrite_EventWriteTransfer
0x180018f4c  test    dword ptr [rsi+158h], 20000000h
0x180018f56  jz      short loc_180018F95
0x180018f58  mov     edi, ebx
0x180018f5a  lea     r14, WPP_GLOBAL_Control
0x180018f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f68  cmp     rcx, r14
0x180018f6b  jz      loc_1800195D2
0x180018f71  test    byte ptr [rcx+1Ch], 8
0x180018f75  jz      loc_1800195D2
0x180018f7b  mov     edx, 33h ; '3'
0x180018f80  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180018f87  mov     rcx, [rcx+10h]
0x180018f8b  call    WPP_SF_
0x180018f90  jmp     loc_1800195D2
0x180018f95  mov     rcx, rsi; this
0x180018f98  call    ?CalculateSessionStatistics@CBackupSession@@AEAAXXZ; CBackupSession::CalculateSessionStatistics(void)
0x180018f9d  mov     ecx, [rsi+314h]
0x180018fa3  shl     rcx, 20h
0x180018fa7  mov     eax, [rsi+310h]
0x180018fad  add     rcx, rax
0x180018fb0  mov     [rsp+0A8h+var_70], rcx
0x180018fb5  cmp     [rsi+98h], ebx
0x180018fbb  jz      short loc_180019000
0x180018fbd  mov     edi, 80040401h
0x180018fc2  lea     r14, WPP_GLOBAL_Control
0x180018fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fd0  cmp     rcx, r14
0x180018fd3  jz      loc_1800195CC
0x180018fd9  test    [rcx+1Ch], r15b
0x180018fdd  jz      loc_1800195CC
0x180018fe3  mov     edx, 34h ; '4'
0x180018fe8  mov     r9d, edi
0x180018feb  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180018ff2  mov     rcx, [rcx+10h]
0x180018ff6  call    WPP_SF_d
0x180018ffb  jmp     loc_1800195CC
0x180019000  mov     rdi, [rsi+18h]
0x180019004  mov     rax, [rdi]
0x180019007  mov     r14, [rax+0A8h]
0x18001900e  lea     rdx, aLastbackuptime; "LastBackupTime"
0x180019015  lea     rcx, [rsp+0A8h+bstrString]; this
0x18001901a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001901f  nop
0x180019020  mov     r9d, 8
0x180019026  lea     r8, [rsp+0A8h+var_70]
0x18001902b  mov     rdx, [rax]
0x18001902e  mov     rcx, rdi
0x180019031  mov     rax, r14
0x180019034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019039  mov     edi, eax
0x18001903b  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180019040  call    cs:__imp_SysFreeString
0x180019046  test    edi, edi
0x180019048  jns     short loc_180019081
0x18001904a  lea     r14, WPP_GLOBAL_Control
0x180019051  mov     rcx, cs:WPP_GLOBAL_Control
0x180019058  cmp     rcx, r14
0x18001905b  jz      short loc_18001907C
0x18001905d  test    [rcx+1Ch], r15b
0x180019061  jz      short loc_18001907C
0x180019063  mov     edx, 35h ; '5'
0x180019068  mov     r9d, edi
0x18001906b  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180019072  mov     rcx, [rcx+10h]
0x180019076  call    WPP_SF_d
0x18001907b  nop
0x18001907c  jmp     loc_1800195CC
0x180019081  cmp     [rsi+80h], rbx
0x180019088  jnz     loc_18001910F
0x18001908e  mov     rdi, [rsi+18h]
0x180019092  mov     rax, [rdi]
0x180019095  mov     r14, [rax+0A8h]
0x18001909c  lea     rdx, aFirstbackuptim; "FirstBackupTime"
0x1800190a3  lea     rcx, [rsp+0A8h+bstrString]; this
0x1800190a8  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800190ad  nop
0x1800190ae  mov     r9d, 8
0x1800190b4  lea     r8, [rsp+0A8h+var_70]
0x1800190b9  mov     rdx, [rax]
0x1800190bc  mov     rcx, rdi
0x1800190bf  mov     rax, r14
0x1800190c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190c7  mov     edi, eax
0x1800190c9  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x1800190ce  call    cs:__imp_SysFreeString
0x1800190d4  test    edi, edi
0x1800190d6  jns     short loc_18001910F
0x1800190d8  lea     r14, WPP_GLOBAL_Control
0x1800190df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190e6  cmp     rcx, r14
0x1800190e9  jz      short loc_18001910A
0x1800190eb  test    [rcx+1Ch], r15b
0x1800190ef  jz      short loc_18001910A
0x1800190f1  mov     edx, 36h ; '6'
0x1800190f6  mov     r9d, edi
0x1800190f9  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180019100  mov     rcx, [rcx+10h]
0x180019104  call    WPP_SF_d
0x180019109  nop
0x18001910a  jmp     loc_1800195CC
0x18001910f  cmp     [rsi+9Ch], ebx
0x180019115  jz      loc_18001919C
0x18001911b  mov     rdi, [rsi+18h]
0x18001911f  mov     rax, [rdi]
0x180019122  mov     r14, [rax+0A8h]
0x180019129  lea     rdx, aLasttargetpres; "LastTargetPresentTime"
0x180019130  lea     rcx, [rsp+0A8h+bstrString]; this
0x180019135  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001913a  nop
0x18001913b  mov     r9d, 8
0x180019141  lea     r8, [rsp+0A8h+var_70]
0x180019146  mov     rdx, [rax]
0x180019149  mov     rcx, rdi
0x18001914c  mov     rax, r14
0x18001914f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019154  mov     edi, eax
0x180019156  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18001915b  call    cs:__imp_SysFreeString
0x180019161  test    edi, edi
0x180019163  jns     short loc_18001919C
0x180019165  lea     r14, WPP_GLOBAL_Control
0x18001916c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019173  cmp     rcx, r14
0x180019176  jz      short loc_180019197
0x180019178  test    [rcx+1Ch], r15b
0x18001917c  jz      short loc_180019197
0x18001917e  mov     edx, 37h ; '7'
0x180019183  mov     r9d, edi
0x180019186  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001918d  mov     rcx, [rcx+10h]
0x180019191  call    WPP_SF_d
0x180019196  nop
0x180019197  jmp     loc_1800195CC
0x18001919c  jmp     short loc_1800191CC
0x18001919e  xor     ebx, ebx
0x1800191a0  lea     r15d, [rbx+1]
0x1800191a4  lea     r14, WPP_GLOBAL_Control
0x1800191ab  mov     edi, dword ptr [rsp+0A8h+bstrString]
0x1800191af  mov     rsi, [rsp+0A8h+var_48]
0x1800191b4  jmp     loc_1800195C8
0x1800191b9  xor     ebx, ebx
0x1800191bb  lea     r15d, [rbx+1]
0x1800191bf  mov     rsi, [rsp+0A8h+var_48]
0x1800191c4  mov     r12d, [rsp+0A8h+arg_8]
0x1800191cc  mov     r13d, ebx
0x1800191cf  cmp     [rsi+0A0h], ebx
0x1800191d5  jz      short loc_18001920A
0x1800191d7  lea     r14, WPP_GLOBAL_Control
0x1800191de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191e5  cmp     rcx, r14
0x1800191e8  jz      short loc_180019205
0x1800191ea  test    byte ptr [rcx+1Ch], 8
0x1800191ee  jz      short loc_180019205
0x1800191f0  mov     edx, 39h ; '9'
0x1800191f5  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x1800191fc  mov     rcx, [rcx+10h]
0x180019200  call    WPP_SF_
0x180019205  mov     r13d, r15d
0x180019208  jmp     short loc_180019211
0x18001920a  lea     r14, WPP_GLOBAL_Control
0x180019211  mov     rdx, [rsi+180h]; Token
0x180019218  xor     ecx, ecx; Thread
0x18001921a  call    cs:__imp_SetThreadToken
0x180019220  test    eax, eax
0x180019222  jnz     short loc_180019270
0x180019224  call    cs:__imp_GetLastError
0x18001922a  mov     edi, eax
0x18001922c  test    eax, eax
0x18001922e  jle     short loc_180019239
0x180019230  movzx   edi, ax
0x180019233  or      edi, 80070000h
0x180019239  mov     rcx, cs:WPP_GLOBAL_Control
0x180019240  cmp     rcx, r14
0x180019243  jz      loc_1800195C8
0x180019249  test    [rcx+1Ch], r15b
0x18001924d  jz      loc_1800195C8
0x180019253  mov     edx, 3Ah ; ':'
0x180019258  mov     r9d, edi
0x18001925b  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180019262  mov     rcx, [rcx+10h]
0x180019266  call    WPP_SF_d
0x18001926b  jmp     loc_1800195C8
0x180019270  prefetchw byte ptr [rsi+1B0h]
0x180019277  mov     rax, [rsi+1B0h]
0x18001927e  mov     rcx, rax
0x180019281  or      rcx, rbx
0x180019284  lock cmpxchg [rsi+1B0h], rcx
0x18001928d  jnz     short loc_18001927E
0x18001928f  mov     rcx, rax
0x180019292  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019296  jz      short loc_1800192BC
0x180019298  mov     eax, [rsi+2Ch]
0x18001929b  sub     eax, [rsi+0C8h]
0x1800192a1  movsxd  rdx, eax
0x1800192a4  imul    rdx, rcx
0x1800192a8  mov     rax, [rsi+1A8h]
0x1800192af  lea     rcx, [rax+rax*4]
0x1800192b3  shl     rcx, 2
0x1800192b7  cmp     rdx, rcx
0x1800192ba  jbe     short loc_1800192EA
0x1800192bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192c3  cmp     rcx, r14
0x1800192c6  jz      short loc_1800192E3
0x1800192c8  test    byte ptr [rcx+1Ch], 8
0x1800192cc  jz      short loc_1800192E3
0x1800192ce  mov     edx, 3Bh ; ';'
0x1800192d3  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x1800192da  mov     rcx, [rcx+10h]
0x1800192de  call    WPP_SF_
0x1800192e3  mov     [rsi+178h], r15d
0x1800192ea  mov     rcx, [rsi+10h]
0x1800192ee  mov     rax, [rcx]
0x1800192f1  lea     r8, [rsp+0A8h+var_68]
0x1800192f6  xor     edx, edx
0x1800192f8  mov     rax, [rax+40h]
0x1800192fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019301  mov     edi, eax
0x180019303  test    eax, eax
0x180019305  jns     short loc_18001932E
0x180019307  mov     rcx, cs:WPP_GLOBAL_Control
0x18001930e  cmp     rcx, r14
0x180019311  jz      loc_1800195CC
0x180019317  test    [rcx+1Ch], r15b
0x18001931b  jz      loc_1800195CC
0x180019321  mov     edx, 3Ch ; '<'
0x180019326  mov     r9d, eax
0x180019329  jmp     loc_180018FEB
0x18001932e  mov     rdx, [rsi+0D0h]
0x180019335  mov     r8, [rsp+0A8h+var_70]
0x18001933a  mov     rcx, r8
0x18001933d  sub     rcx, rdx
0x180019340  imul    rax, [rsp+0A8h+var_68], 4C4B400h
0x180019349  cmp     rcx, rax
0x18001934c  jbe     short loc_180019388
0x18001934e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019355  cmp     rcx, r14
0x180019358  jz      short loc_180019381
0x18001935a  test    byte ptr [rcx+1Ch], 8
0x18001935e  jz      short loc_180019381
0x180019360  mov     edx, 3Dh ; '='
0x180019365  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001936c  mov     rcx, [rcx+10h]
0x180019370  call    WPP_SF_
0x180019375  mov     rdx, [rsi+0D0h]
0x18001937c  mov     r8, [rsp+0A8h+var_70]
0x180019381  mov     [rsi+178h], r15d
0x180019388  sub     r8, rdx
0x18001938b  mov     rax, 0C92A69C000h
0x180019395  cmp     r8, rax
0x180019398  jbe     short loc_1800193C8
0x18001939a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193a1  cmp     rcx, r14
0x1800193a4  jz      short loc_1800193C1
0x1800193a6  test    byte ptr [rcx+1Ch], 8
0x1800193aa  jz      short loc_1800193C1
0x1800193ac  mov     edx, 3Eh ; '>'
0x1800193b1  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x1800193b8  mov     rcx, [rcx+10h]
0x1800193bc  call    WPP_SF_
0x1800193c1  mov     [rsi+178h], r15d
0x1800193c8  cmp     [rsi+9Ch], ebx
0x1800193ce  jz      short loc_1800193E7
0x1800193d0  test    r13d, r13d
0x1800193d3  jnz     short loc_1800193E7
0x1800193d5  test    r12d, r12d
0x1800193d8  jnz     short loc_1800193E2
0x1800193da  cmp     [rsi+178h], ebx
0x1800193e0  jz      short loc_1800193E7
0x1800193e2  mov     r12d, r15d
0x1800193e5  jmp     short loc_1800193EA
0x1800193e7  mov     r12d, ebx
0x1800193ea  cmp     [rsp+0A8h+arg_8], ebx
  ... truncated ...
```
