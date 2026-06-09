# BuildTimeSyncRepairMsg(int,__int64,__int64,ushort * *)

- ea: `0x180010718`
- end: `0x180010ad3`
- name: `?BuildTimeSyncRepairMsg@@YAJH_J0PEAPEAG@Z`
- size: `955`
- prototype: `__int64 __fastcall(int, __int64, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000da10`

## callees

- `0x180010718`
- `0x18001223c`
- `0x180014660`
- `0x180018bf8`
- `0x180018d1c`
- `0x18001919c`
- `0x180019d34`
- `0x18001a5e0`

## import_xrefs

- `KERNEL32!GetDateFormatEx` at `0x180010969`
- `KERNEL32!GetDateFormatEx` at `0x1800109d6`
- `KERNEL32!GetDateFormatEx` at `0x180010969`
- `KERNEL32!GetDateFormatEx` at `0x1800109d6`
- `KERNEL32!GetTimeFormatEx` at `0x1800108df`
- `KERNEL32!GetTimeFormatEx` at `0x180010947`
- `KERNEL32!GetTimeFormatEx` at `0x1800108df`
- `KERNEL32!GetTimeFormatEx` at `0x180010947`
- `KERNEL32!FileTimeToSystemTime` at `0x1800108b6`
- `KERNEL32!FileTimeToSystemTime` at `0x1800108b6`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180010877`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180010877`
- `KERNEL32!GetProcessHeap` at `0x1800108fa`
- `KERNEL32!GetProcessHeap` at `0x180010987`
- `KERNEL32!GetProcessHeap` at `0x180010a73`
- `KERNEL32!GetProcessHeap` at `0x180010a8c`
- `KERNEL32!GetProcessHeap` at `0x1800108fa`
- `KERNEL32!GetProcessHeap` at `0x180010987`
- `KERNEL32!GetProcessHeap` at `0x180010a73`
- `KERNEL32!GetProcessHeap` at `0x180010a8c`
- `KERNEL32!HeapAlloc` at `0x18001090b`
- `KERNEL32!HeapAlloc` at `0x180010998`
- `KERNEL32!HeapAlloc` at `0x18001090b`
- `KERNEL32!HeapAlloc` at `0x180010998`
- `KERNEL32!HeapFree` at `0x180010a81`
- `KERNEL32!HeapFree` at `0x180010a9a`
- `KERNEL32!HeapFree` at `0x180010a81`
- `KERNEL32!HeapFree` at `0x180010a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a68`

## string_xrefs

- `0x18001088c`: `BuildTimeSyncRepairMsg`
- `0x180010a39`: `BuildTimeSyncRepairMsg`

## pseudocode

```c
__int64 __fastcall BuildTimeSyncRepairMsg(int a1, __int64 a2, __int64 a3, unsigned __int16 **a4)
{
  WCHAR *v7; // r15
  WCHAR *v8; // r12
  int v9; // r14d
  unsigned __int128 v10; // rax
  unsigned __int64 v11; // rdi
  signed int XML; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  unsigned int v15; // ebx
  void *v16; // r13
  unsigned int v17; // r9d
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  unsigned int v20; // r9d
  int TimeFormat; // eax
  __int64 cchTime; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *lpTimeStr; // rax
  const struct _EVENT_DESCRIPTOR *v25; // rdx
  CEventLogger *v26; // rcx
  int DateFormat; // eax
  __int64 v28; // rsi
  HANDLE v29; // rax
  WCHAR *v30; // rax
  const struct _EVENT_DESCRIPTOR *v31; // rdx
  CEventLogger *v32; // rcx
  HANDLE v33; // rax
  HANDLE v34; // rax
  FILETIME FileTime; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-21h] BYREF
  CEventLogger *v38; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+60h] [rbp-9h] BYREF
  __int64 v41; // [rsp+68h] [rbp-1h]
  unsigned __int16 **v42; // [rsp+70h] [rbp+7h]
  _SYSTEMTIME SystemTime; // [rsp+78h] [rbp+Fh] BYREF

  v42 = a4;
  v41 = a2;
  pv = 0;
  v37 = 0;
  FileTime = 0;
  LocalFileTime = 0;
  SystemTime = 0;
  v7 = 0;
  v8 = 0;
  DiagnosisTextBuilder::DiagnosisTextBuilder((DiagnosisTextBuilder *)&v38, hInstance);
  *a4 = 0;
  if ( a3 >= 3600 )
  {
    if ( a3 >= 86400 )
    {
      v9 = 405;
      v10 = (unsigned __int64)a3 * (unsigned __int128)0xC22E450672894AB7uLL;
      v11 = a3 / 0x15180uLL;
    }
    else
    {
      v9 = 406;
      v10 = (unsigned __int64)a3 * (unsigned __int128)0x23456789ABCDF013uLL;
      v11 = a3 / 0xE10uLL;
    }
  }
  else
  {
    v9 = 407;
    *((_QWORD *)&v10 + 1) = (unsigned __int128)(a3 * (__int128)(__int64)0x8888888888888889uLL) >> 64;
    v11 = a3 / 60;
  }
  XML = StringCchCopyWithAlloc((unsigned __int16 **)&pv, SDWORD2(v10), (a1 != 1) + 403);
  v15 = XML;
  v16 = pv;
  if ( XML < 0 )
  {
    v17 = 2080;
    goto LABEL_30;
  }
  XML = StringCchCopyWithAlloc(&v37, (int)v13, v9);
  v15 = XML;
  if ( XML < 0 )
  {
    v17 = 2088;
    goto LABEL_30;
  }
  FileTime = (FILETIME)(10000000 * (v41 + 0x2B6109100LL));
  if ( !FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
  {
    v20 = 2101;
LABEL_12:
    CEventLogger::LogError(
      v19,
      v18,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      v20,
      L"BuildTimeSyncRepairMsg",
      0);
    v15 = -2147467259;
    goto LABEL_31;
  }
  if ( !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    v20 = 2108;
    goto LABEL_12;
  }
  TimeFormat = GetTimeFormatEx(0, 2u, &SystemTime, 0, 0, 0);
  cchTime = TimeFormat;
  if ( !TimeFormat )
  {
    v20 = 2121;
    goto LABEL_12;
  }
  ProcessHeap = GetProcessHeap();
  lpTimeStr = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * cchTime);
  v7 = lpTimeStr;
  if ( !lpTimeStr )
  {
    v15 = -2147024882;
    CEventLogger::LogError(
      v26,
      v25,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x84Bu,
      L"BuildTimeSyncRepairMsg",
      0x8007000E);
    goto LABEL_31;
  }
  GetTimeFormatEx(0, 2u, &SystemTime, 0, lpTimeStr, cchTime);
  DateFormat = GetDateFormatEx(0, 1u, &SystemTime, 0, 0, 0, 0);
  v28 = DateFormat;
  if ( !DateFormat )
  {
    v20 = 2142;
    goto LABEL_12;
  }
  v29 = GetProcessHeap();
  v30 = (WCHAR *)HeapAlloc(v29, 8u, 2 * v28);
  v8 = v30;
  if ( !v30 )
  {
    v15 = -2147024882;
    CEventLogger::LogError(
      v32,
      v31,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x860u,
      L"BuildTimeSyncRepairMsg",
      0x8007000E);
    goto LABEL_31;
  }
  GetDateFormatEx(0, 1u, &SystemTime, 0, v30, v28, 0);
  XML = DiagnosisTextBuilder::SetTextV(
          (DiagnosisTextBuilder *)&v38,
          (const unsigned __int16 *)0x25E,
          v11,
          v37,
          v16,
          v8,
          v7);
  v15 = XML;
  if ( XML >= 0 )
  {
    v14 = v38;
    if ( v38 )
    {
      XML = DiagnosisTextBuilderImpl::GetXML(v38, v42);
      v15 = XML;
      if ( XML >= 0 )
        goto LABEL_31;
    }
    else
    {
      v15 = -2147024882;
      XML = -2147024882;
    }
    v17 = 2169;
  }
  else
  {
    v17 = 2164;
  }
LABEL_30:
  CEventLogger::LogError(
    v14,
    v13,
    L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
    v17,
    L"BuildTimeSyncRepairMsg",
    XML);
LABEL_31:
  if ( v16 )
    CoTaskMemFree(v16);
  if ( v37 )
    CoTaskMemFree(v37);
  if ( v8 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v8);
  }
  if ( v7 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v7);
  }
  DiagnosisTextBuilder::~DiagnosisTextBuilder((DiagnosisTextBuilder *)&v38);
  return v15;
}

```

## disassembly

```asm
0x180010718  mov     [rsp-8+arg_0], rbx
0x18001071d  push    rbp
0x18001071e  push    rsi
0x18001071f  push    rdi
0x180010720  push    r12
0x180010722  push    r13
0x180010724  push    r14
0x180010726  push    r15
0x180010728  lea     rbp, [rsp-27h]
0x18001072d  sub     rsp, 90h
0x180010734  mov     rax, cs:__security_cookie
0x18001073b  xor     rax, rsp
0x18001073e  mov     [rbp+57h+var_38], rax
0x180010742  mov     rdi, r9
0x180010745  mov     [rbp+57h+var_50], r9
0x180010749  mov     rsi, r8
0x18001074c  mov     [rbp+57h+var_58], rdx
0x180010750  mov     ebx, ecx
0x180010752  xor     r14d, r14d
0x180010755  mov     [rbp+57h+pv], r14
0x180010759  mov     [rbp+57h+var_78], r14
0x18001075d  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180010761  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], r14
0x180010765  xorps   xmm0, xmm0
0x180010768  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001076c  mov     r15d, r14d
0x18001076f  mov     r12d, r14d
0x180010772  mov     rdx, cs:hInstance; HINSTANCE
0x180010779  lea     rcx, [rbp+57h+var_70]; this
0x18001077d  call    ??0DiagnosisTextBuilder@@QEAA@PEAUHINSTANCE__@@@Z; DiagnosisTextBuilder::DiagnosisTextBuilder(HINSTANCE__ *)
0x180010782  nop
0x180010783  mov     [rdi], r14
0x180010786  mov     r8d, r14d
0x180010789  cmp     ebx, 1
0x18001078c  setnz   r8b
0x180010790  add     r8d, 193h; int
0x180010797  cmp     rsi, 0E10h
0x18001079e  jge     short loc_1800107C7
0x1800107a0  mov     rax, 8888888888888889h
0x1800107aa  mov     r14d, 197h
0x1800107b0  imul    rsi
0x1800107b3  lea     rdi, [rsi+rdx]
0x1800107b7  sar     rdi, 5
0x1800107bb  mov     rax, rdi
0x1800107be  shr     rax, 3Fh
0x1800107c2  add     rdi, rax
0x1800107c5  jmp     short loc_18001080F
0x1800107c7  cmp     rsi, 15180h
0x1800107ce  jge     short loc_1800107F5
0x1800107d0  mov     r14d, 196h
0x1800107d6  mov     rdi, rsi
0x1800107d9  mov     rax, 23456789ABCDF013h
0x1800107e3  mul     rsi
0x1800107e6  sub     rdi, rdx
0x1800107e9  shr     rdi, 1
0x1800107ec  add     rdi, rdx
0x1800107ef  shr     rdi, 0Bh
0x1800107f3  jmp     short loc_18001080F
0x1800107f5  mov     rax, 0C22E450672894AB7h
0x1800107ff  mov     r14d, 195h
0x180010805  mul     rsi
0x180010808  mov     rdi, rdx
0x18001080b  shr     rdi, 10h
0x18001080f  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x180010813  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x180010818  mov     ebx, eax
0x18001081a  mov     r13, [rbp+57h+pv]
0x18001081e  test    eax, eax
0x180010820  jns     short loc_18001082D
0x180010822  mov     r9d, 820h
0x180010828  jmp     loc_180010A35
0x18001082d  mov     r8d, r14d; int
0x180010830  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x180010834  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x180010839  mov     ebx, eax
0x18001083b  xor     r14d, r14d
0x18001083e  test    eax, eax
0x180010840  jns     short loc_18001084D
0x180010842  mov     r9d, 828h
0x180010848  jmp     loc_180010A35
0x18001084d  mov     rcx, 2B6109100h
0x180010857  mov     rax, [rbp+57h+var_58]
0x18001085b  add     rax, rcx
0x18001085e  imul    rax, 989680h
0x180010865  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180010868  shr     rax, 20h
0x18001086c  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x18001086f  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x180010873  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180010877  call    cs:__imp_FileTimeToLocalFileTime
0x18001087d  test    eax, eax
0x18001087f  jnz     short loc_1800108AE
0x180010881  mov     r9d, 835h; unsigned int
0x180010887  mov     [rsp+0C0h+cchTime], r14d; unsigned int
0x18001088c  lea     rax, aBuildtimesyncr; "BuildTimeSyncRepairMsg"
0x180010893  mov     [rsp+0C0h+lpTimeStr], rax; unsigned __int16 *
0x180010898  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18001089f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800108a4  mov     ebx, 80004005h
0x1800108a9  jmp     loc_180010A51
0x1800108ae  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800108b2  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x1800108b6  call    cs:__imp_FileTimeToSystemTime
0x1800108bc  mov     [rsp+0C0h+cchTime], r14d; cchTime
0x1800108c1  test    eax, eax
0x1800108c3  jnz     short loc_1800108CD
0x1800108c5  mov     r9d, 83Ch
0x1800108cb  jmp     short loc_18001088C
0x1800108cd  mov     [rsp+0C0h+lpTimeStr], r14; lpTimeStr
0x1800108d2  xor     r9d, r9d; lpFormat
0x1800108d5  lea     r8, [rbp+57h+SystemTime]; lpTime
0x1800108d9  lea     edx, [r9+2]; dwFlags
0x1800108dd  xor     ecx, ecx; lpLocaleName
0x1800108df  call    cs:__imp_GetTimeFormatEx
0x1800108e5  movsxd  rsi, eax
0x1800108e8  test    eax, eax
0x1800108ea  jnz     short loc_1800108F4
0x1800108ec  mov     r9d, 849h
0x1800108f2  jmp     short loc_180010887
0x1800108f4  mov     rbx, rsi
0x1800108f7  add     rbx, rbx
0x1800108fa  call    cs:__imp_GetProcessHeap
0x180010900  mov     rcx, rax; hHeap
0x180010903  mov     r8, rbx; dwBytes
0x180010906  mov     edx, 8; dwFlags
0x18001090b  call    cs:__imp_HeapAlloc
0x180010911  mov     r15, rax
0x180010914  test    rax, rax
0x180010917  jnz     short loc_180010931
0x180010919  mov     ebx, 8007000Eh
0x18001091e  mov     [rsp+0C0h+cchTime], 8007000Eh
0x180010926  mov     r9d, 84Bh
0x18001092c  jmp     loc_180010A39
0x180010931  mov     [rsp+0C0h+cchTime], esi; cchTime
0x180010935  mov     [rsp+0C0h+lpTimeStr], r15; lpTimeStr
0x18001093a  xor     r9d, r9d; lpFormat
0x18001093d  lea     r8, [rbp+57h+SystemTime]; lpTime
0x180010941  lea     edx, [r9+2]; dwFlags
0x180010945  xor     ecx, ecx; lpLocaleName
0x180010947  call    cs:__imp_GetTimeFormatEx
0x18001094d  mov     [rsp+0C0h+lpCalendar], r14; lpCalendar
0x180010952  mov     [rsp+0C0h+cchTime], r14d; cchDate
0x180010957  mov     [rsp+0C0h+lpTimeStr], r14; lpDateStr
0x18001095c  xor     r9d, r9d; lpFormat
0x18001095f  lea     r8, [rbp+57h+SystemTime]; lpDate
0x180010963  lea     edx, [r9+1]; dwFlags
0x180010967  xor     ecx, ecx; lpLocaleName
0x180010969  call    cs:__imp_GetDateFormatEx
0x18001096f  movsxd  rsi, eax
0x180010972  test    eax, eax
0x180010974  jnz     short loc_180010981
0x180010976  mov     r9d, 85Eh
0x18001097c  jmp     loc_180010887
0x180010981  mov     rbx, rsi
0x180010984  add     rbx, rbx
0x180010987  call    cs:__imp_GetProcessHeap
0x18001098d  mov     rcx, rax; hHeap
0x180010990  mov     r8, rbx; dwBytes
0x180010993  mov     edx, 8; dwFlags
0x180010998  call    cs:__imp_HeapAlloc
0x18001099e  mov     r12, rax
0x1800109a1  test    rax, rax
0x1800109a4  jnz     short loc_1800109BB
0x1800109a6  mov     ebx, 8007000Eh
0x1800109ab  mov     [rsp+0C0h+cchTime], 8007000Eh
0x1800109b3  mov     r9d, 860h
0x1800109b9  jmp     short loc_180010A39
0x1800109bb  mov     [rsp+0C0h+lpCalendar], r14; lpCalendar
0x1800109c0  mov     [rsp+0C0h+cchTime], esi; cchDate
0x1800109c4  mov     [rsp+0C0h+lpTimeStr], r12; lpDateStr
0x1800109c9  xor     r9d, r9d; lpFormat
0x1800109cc  lea     r8, [rbp+57h+SystemTime]; lpDate
0x1800109d0  lea     edx, [r9+1]; dwFlags
0x1800109d4  xor     ecx, ecx; lpLocaleName
0x1800109d6  call    cs:__imp_GetDateFormatEx
0x1800109dc  mov     [rsp+0C0h+lpCalendar], r15
0x1800109e1  mov     qword ptr [rsp+0C0h+cchTime], r12
0x1800109e6  mov     [rsp+0C0h+lpTimeStr], r13
0x1800109eb  mov     r9, [rbp+57h+var_78]
0x1800109ef  mov     r8, rdi
0x1800109f2  mov     edx, 25Eh; unsigned __int16 *
0x1800109f7  lea     rcx, [rbp+57h+var_70]; this
0x1800109fb  call    ?SetTextV@DiagnosisTextBuilder@@QEAAJPEBGZZ; DiagnosisTextBuilder::SetTextV(ushort const *,...)
0x180010a00  mov     ebx, eax
0x180010a02  test    eax, eax
0x180010a04  jns     short loc_180010A0E
0x180010a06  mov     r9d, 874h
0x180010a0c  jmp     short loc_180010A35
0x180010a0e  mov     rcx, [rbp+57h+var_70]; this
0x180010a12  test    rcx, rcx
0x180010a15  jz      short loc_180010A28
0x180010a17  mov     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x180010a1b  call    ?GetXML@DiagnosisTextBuilderImpl@@QEAAJPEAPEAG@Z; DiagnosisTextBuilderImpl::GetXML(ushort * *)
0x180010a20  mov     ebx, eax
0x180010a22  test    eax, eax
0x180010a24  jns     short loc_180010A51
0x180010a26  jmp     short loc_180010A2F
0x180010a28  mov     ebx, 8007000Eh
0x180010a2d  mov     eax, ebx
0x180010a2f  mov     r9d, 879h; unsigned int
0x180010a35  mov     [rsp+0C0h+cchTime], eax; unsigned int
0x180010a39  lea     rax, aBuildtimesyncr; "BuildTimeSyncRepairMsg"
0x180010a40  mov     [rsp+0C0h+lpTimeStr], rax; unsigned __int16 *
0x180010a45  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180010a4c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180010a51  test    r13, r13
0x180010a54  jz      short loc_180010A5F
0x180010a56  mov     rcx, r13; pv
0x180010a59  call    cs:__imp_CoTaskMemFree
0x180010a5f  mov     rcx, [rbp+57h+var_78]; pv
0x180010a63  test    rcx, rcx
0x180010a66  jz      short loc_180010A6E
0x180010a68  call    cs:__imp_CoTaskMemFree
0x180010a6e  test    r12, r12
0x180010a71  jz      short loc_180010A87
0x180010a73  call    cs:__imp_GetProcessHeap
0x180010a79  mov     rcx, rax; hHeap
0x180010a7c  mov     r8, r12; lpMem
0x180010a7f  xor     edx, edx; dwFlags
0x180010a81  call    cs:__imp_HeapFree
0x180010a87  test    r15, r15
0x180010a8a  jz      short loc_180010AA1
0x180010a8c  call    cs:__imp_GetProcessHeap
0x180010a92  mov     rcx, rax; hHeap
0x180010a95  mov     r8, r15; lpMem
0x180010a98  xor     edx, edx; dwFlags
0x180010a9a  call    cs:__imp_HeapFree
0x180010aa0  nop
0x180010aa1  lea     rcx, [rbp+57h+var_70]; this
0x180010aa5  call    ??1DiagnosisTextBuilder@@QEAA@XZ; DiagnosisTextBuilder::~DiagnosisTextBuilder(void)
0x180010aaa  mov     eax, ebx
0x180010aac  mov     rcx, [rbp+57h+var_38]
0x180010ab0  xor     rcx, rsp; StackCookie
0x180010ab3  call    __security_check_cookie
0x180010ab8  mov     rbx, [rsp+0C0h+arg_0]
0x180010ac0  add     rsp, 90h
0x180010ac7  pop     r15
0x180010ac9  pop     r14
0x180010acb  pop     r13
0x180010acd  pop     r12
0x180010acf  pop     rdi
0x180010ad0  pop     rsi
0x180010ad1  pop     rbp
0x180010ad2  retn
```
