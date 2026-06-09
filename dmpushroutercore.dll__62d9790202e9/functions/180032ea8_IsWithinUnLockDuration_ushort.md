# IsWithinUnLockDuration(ushort *)

- ea: `0x180032ea8`
- end: `0x1800331c9`
- name: `?IsWithinUnLockDuration@@YAHPEAG@Z`
- size: `801`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011690`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000bab4`
- `0x18000c63c`
- `0x180010bd8`
- `0x180010f74`
- `0x180012314`
- `0x18001bc10`
- `0x18001c030`
- `0x180031af8`
- `0x180032ea8`
- `0x1800331d0`
- `0x180033920`
- `0x180033a5c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180032f40`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180032f40`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180032f7f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800330c4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180032f7f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800330c4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180032f5e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800330a3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180032f5e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800330a3`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180032f30`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180032f30`

## pseudocode

```c
__int64 __fastcall IsWithinUnLockDuration(unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rdx
  int v3; // edi
  const unsigned __int16 *v4; // rdx
  const unsigned __int16 *v5; // r8
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *p_Src; // r8
  CConfigLockLogger *Logger; // rax
  __int64 v11; // [rsp+20h] [rbp-E0h]
  int wMonth; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+28h] [rbp-D8h]
  int wDay; // [rsp+28h] [rbp-D8h]
  int v15; // [rsp+30h] [rbp-D0h]
  int wHour; // [rsp+30h] [rbp-D0h]
  int v17; // [rsp+38h] [rbp-C8h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+40h] [rbp-C0h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+48h] [rbp-B8h]
  int wMilliseconds; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp-A8h] BYREF
  FILETIME FileTime1; // [rsp+60h] [rbp-A0h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+68h] [rbp-98h] BYREF
  __int128 Src; // [rsp+78h] [rbp-88h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v30[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v23 = 0;
  if ( TrackingFileExists(a1, L"2bf1e654-2be5-42e4-ab28-b80a4dc9eeee", &v23) < 0 )
    return 0;
  if ( !v23 )
    return 0;
  FileTime2 = 0;
  v3 = ReadFileTimeFromTrackingFile(a1, v2, &FileTime2);
  if ( v3 < 0 )
    return 0;
  FileTime1 = 0;
  GetSystemTimePreciseAsFileTime(&FileTime1);
  if ( CompareFileTime(&FileTime1, &FileTime2) >= 0 )
  {
    v7 = DeleteTrackingFile(a1, L"2bf1e654-2be5-42e4-ab28-b80a4dc930d2");
    if ( v7 >= 0 )
      DeleteTrackingFile(a1, L"2bf1e654-2be5-42e4-ab28-b80a4dc9eeee");
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)(unsigned int)v7,
        v11);
    SystemTime = 0;
    if ( FileTimeToSystemTime(&FileTime2, &SystemTime) )
    {
      LocalTime = 0;
      SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime);
      memset_0(v30, 0, 0x208u);
      wMilliseconds = LocalTime.wMilliseconds;
      wSecond = LocalTime.wSecond;
      wMinute = LocalTime.wMinute;
      wHour = LocalTime.wHour;
      wDay = LocalTime.wDay;
      LODWORD(v11) = LocalTime.wMonth;
      if ( (int)StringCchPrintfW(
                  v30,
                  0x104u,
                  L"%d-%02d-%02d %02d:%02d:%02d.%03d",
                  LocalTime.wYear,
                  v11,
                  wDay,
                  wHour,
                  wMinute,
                  wSecond,
                  wMilliseconds) >= 0 )
      {
        Src = 0;
        v28 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&Src, L"INFO  Unlock duration expired at: ", 0x22u);
        std::wstring::append(&Src, v30);
        p_Src = (const unsigned __int16 *)&Src;
        if ( *((_QWORD *)&v28 + 1) > 7u )
          p_Src = (const unsigned __int16 *)Src;
        WriteToLogFile(a1, v8, p_Src);
        Logger = CConfigLockLogger::GetLogger();
        CConfigLockLogger::LogUnlockDurationExpired(Logger, v30, v3);
        std::wstring::~wstring((char **)&Src);
      }
    }
    return 0;
  }
  SystemTime = 0;
  if ( FileTimeToSystemTime(&FileTime2, &SystemTime) )
  {
    LocalTime = 0;
    SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime);
    memset_0(v30, 0, 0x208u);
    v21 = LocalTime.wMilliseconds;
    v19 = LocalTime.wSecond;
    v17 = LocalTime.wMinute;
    v15 = LocalTime.wHour;
    v13 = LocalTime.wDay;
    wMonth = LocalTime.wMonth;
    if ( (int)StringCchPrintfW(
                v30,
                0x104u,
                L"%d-%02d-%02d %02d:%02d:%02d.%03d",
                LocalTime.wYear,
                wMonth,
                v13,
                v15,
                v17,
                v19,
                v21) >= 0 )
    {
      Src = 0;
      v28 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&Src, L"INFO  Unlock duration expires at: ", 0x22u);
      std::wstring::append(&Src, v30);
      v5 = (const unsigned __int16 *)&Src;
      if ( *((_QWORD *)&v28 + 1) > 7u )
        v5 = (const unsigned __int16 *)Src;
      WriteToLogFile(a1, v4, v5);
      std::wstring::~wstring((char **)&Src);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180032ea8  mov     [rsp-8+arg_8], rbx
0x180032ead  mov     [rsp-8+arg_10], rdi
0x180032eb2  push    rbp
0x180032eb3  lea     rbp, [rsp-1D0h]
0x180032ebb  sub     rsp, 2D0h
0x180032ec2  mov     rax, cs:__security_cookie
0x180032ec9  xor     rax, rsp
0x180032ecc  mov     [rbp+1D0h+var_10], rax
0x180032ed3  mov     rbx, rcx
0x180032ed6  mov     [rsp+2D0h+var_280], 0
0x180032ede  lea     r8, [rsp+2D0h+var_280]; int *
0x180032ee3  lea     rdx, a2bf1e6542be542; "2bf1e654-2be5-42e4-ab28-b80a4dc9eeee"
0x180032eea  call    ?TrackingFileExists@@YAJPEBG0PEAH@Z; TrackingFileExists(ushort const *,ushort const *,int *)
0x180032eef  test    eax, eax
0x180032ef1  js      loc_1800331A3
0x180032ef7  cmp     [rsp+2D0h+var_280], 0
0x180032efc  jz      loc_1800331A3
0x180032f02  mov     qword ptr [rsp+2D0h+FileTime2.dwLowDateTime], 0
0x180032f0b  lea     r8, [rsp+2D0h+FileTime2]; struct _FILETIME *
0x180032f10  mov     rcx, rbx; unsigned __int16 *
0x180032f13  call    ?ReadFileTimeFromTrackingFile@@YAJPEBG0PEAU_FILETIME@@@Z; ReadFileTimeFromTrackingFile(ushort const *,ushort const *,_FILETIME *)
0x180032f18  mov     edi, eax
0x180032f1a  test    eax, eax
0x180032f1c  js      loc_1800331A3
0x180032f22  mov     qword ptr [rsp+2D0h+FileTime1.dwLowDateTime], 0
0x180032f2b  lea     rcx, [rsp+2D0h+FileTime1]
0x180032f30  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180032f36  lea     rdx, [rsp+2D0h+FileTime2]; lpFileTime2
0x180032f3b  lea     rcx, [rsp+2D0h+FileTime1]; lpFileTime1
0x180032f40  call    cs:__imp_CompareFileTime
0x180032f46  test    eax, eax
0x180032f48  jns     loc_180033054
0x180032f4e  xorps   xmm0, xmm0
0x180032f51  movups  xmmword ptr [rbp+1D0h+SystemTime.wYear], xmm0
0x180032f55  lea     rdx, [rbp+1D0h+SystemTime]; lpSystemTime
0x180032f59  lea     rcx, [rsp+2D0h+FileTime2]; lpFileTime
0x180032f5e  call    cs:__imp_FileTimeToSystemTime
0x180032f64  test    eax, eax
0x180032f66  jz      loc_18003304A
0x180032f6c  xorps   xmm0, xmm0
0x180032f6f  movups  xmmword ptr [rsp+2D0h+LocalTime.wYear], xmm0
0x180032f74  lea     r8, [rsp+2D0h+LocalTime]; lpLocalTime
0x180032f79  lea     rdx, [rbp+1D0h+SystemTime]; lpUniversalTime
0x180032f7d  xor     ecx, ecx; lpTimeZoneInformation
0x180032f7f  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180032f85  xor     edx, edx; Val
0x180032f87  mov     r8d, 208h; Size
0x180032f8d  lea     rcx, [rbp+1D0h+var_220]; void *
0x180032f91  call    memset_0
0x180032f96  movzx   eax, [rsp+2D0h+LocalTime.wMilliseconds]
0x180032f9b  movzx   ecx, [rsp+2D0h+LocalTime.wSecond]
0x180032fa0  movzx   edx, [rsp+2D0h+LocalTime.wMinute]
0x180032fa5  movzx   r8d, [rsp+2D0h+LocalTime.wHour]
0x180032fab  movzx   r10d, [rsp+2D0h+LocalTime.wDay]
0x180032fb1  movzx   r11d, [rsp+2D0h+LocalTime.wMonth]
0x180032fb7  movzx   r9d, [rsp+2D0h+LocalTime.wYear]
0x180032fbd  mov     [rsp+2D0h+var_288], eax
0x180032fc1  mov     [rsp+2D0h+var_290], ecx
0x180032fc5  mov     [rsp+2D0h+var_298], edx
0x180032fc9  mov     [rsp+2D0h+var_2A0], r8d
0x180032fce  mov     [rsp+2D0h+var_2A8], r10d
0x180032fd3  mov     dword ptr [rsp+2D0h+var_2B0], r11d
0x180032fd8  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d.%03d"
0x180032fdf  mov     edx, 104h; unsigned __int64
0x180032fe4  lea     rcx, [rbp+1D0h+var_220]; unsigned __int16 *
0x180032fe8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032fed  test    eax, eax
0x180032fef  js      short loc_18003304A
0x180032ff1  xorps   xmm0, xmm0
0x180032ff4  movups  [rsp+2D0h+Src], xmm0
0x180032ff9  xorps   xmm1, xmm1
0x180032ffc  movdqu  [rbp+1D0h+var_248], xmm1
0x180033001  mov     r8d, 22h ; '"'
0x180033007  lea     rdx, aInfoUnlockDura_0; "INFO  Unlock duration expires at: "
0x18003300e  lea     rcx, [rsp+2D0h+Src]
0x180033013  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180033018  nop
0x180033019  lea     rdx, [rbp+1D0h+var_220]; void *
0x18003301d  lea     rcx, [rsp+2D0h+Src]; Src
0x180033022  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180033027  lea     r8, [rsp+2D0h+Src]
0x18003302c  cmp     qword ptr [rbp+1D0h+var_248+8], 7
0x180033031  cmova   r8, qword ptr [rsp+2D0h+Src]; unsigned __int16 *
0x180033037  mov     rcx, rbx; unsigned __int16 *
0x18003303a  call    ?WriteToLogFile@@YAJPEBG00@Z; WriteToLogFile(ushort const *,ushort const *,ushort const *)
0x18003303f  nop
0x180033040  lea     rcx, [rsp+2D0h+Src]
0x180033045  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003304a  mov     eax, 1
0x18003304f  jmp     loc_1800331A5
0x180033054  lea     rdx, a2bf1e6542be542_0; "2bf1e654-2be5-42e4-ab28-b80a4dc930d2"
0x18003305b  mov     rcx, rbx; unsigned __int16 *
0x18003305e  call    ?DeleteTrackingFile@@YAJPEBG0@Z; DeleteTrackingFile(ushort const *,ushort const *)
0x180033063  test    eax, eax
0x180033065  jns     short loc_180033084
0x180033067  mov     rcx, [rbp+1D8h]; this
0x18003306e  mov     r9d, eax; char *
0x180033071  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033078  mov     edx, 0ACh; void *
0x18003307d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033082  jmp     short loc_180033093
0x180033084  lea     rdx, a2bf1e6542be542; "2bf1e654-2be5-42e4-ab28-b80a4dc9eeee"
0x18003308b  mov     rcx, rbx; unsigned __int16 *
0x18003308e  call    ?DeleteTrackingFile@@YAJPEBG0@Z; DeleteTrackingFile(ushort const *,ushort const *)
0x180033093  xorps   xmm0, xmm0
0x180033096  movups  xmmword ptr [rbp+1D0h+SystemTime.wYear], xmm0
0x18003309a  lea     rdx, [rbp+1D0h+SystemTime]; lpSystemTime
0x18003309e  lea     rcx, [rsp+2D0h+FileTime2]; lpFileTime
0x1800330a3  call    cs:__imp_FileTimeToSystemTime
0x1800330a9  test    eax, eax
0x1800330ab  jz      loc_1800331A3
0x1800330b1  xorps   xmm0, xmm0
0x1800330b4  movups  xmmword ptr [rsp+2D0h+LocalTime.wYear], xmm0
0x1800330b9  lea     r8, [rsp+2D0h+LocalTime]; lpLocalTime
0x1800330be  lea     rdx, [rbp+1D0h+SystemTime]; lpUniversalTime
0x1800330c2  xor     ecx, ecx; lpTimeZoneInformation
0x1800330c4  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x1800330ca  xor     edx, edx; Val
0x1800330cc  mov     r8d, 208h; Size
0x1800330d2  lea     rcx, [rbp+1D0h+var_220]; void *
0x1800330d6  call    memset_0
0x1800330db  movzx   eax, [rsp+2D0h+LocalTime.wMilliseconds]
0x1800330e0  movzx   ecx, [rsp+2D0h+LocalTime.wSecond]
0x1800330e5  movzx   edx, [rsp+2D0h+LocalTime.wMinute]
0x1800330ea  movzx   r8d, [rsp+2D0h+LocalTime.wHour]
0x1800330f0  movzx   r10d, [rsp+2D0h+LocalTime.wDay]
0x1800330f6  movzx   r11d, [rsp+2D0h+LocalTime.wMonth]
0x1800330fc  movzx   r9d, [rsp+2D0h+LocalTime.wYear]
0x180033102  mov     [rsp+2D0h+var_288], eax
0x180033106  mov     [rsp+2D0h+var_290], ecx
0x18003310a  mov     [rsp+2D0h+var_298], edx
0x18003310e  mov     [rsp+2D0h+var_2A0], r8d
0x180033113  mov     [rsp+2D0h+var_2A8], r10d
0x180033118  mov     dword ptr [rsp+2D0h+var_2B0], r11d
0x18003311d  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d.%03d"
0x180033124  mov     edx, 104h; unsigned __int64
0x180033129  lea     rcx, [rbp+1D0h+var_220]; unsigned __int16 *
0x18003312d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033132  test    eax, eax
0x180033134  js      short loc_1800331A3
0x180033136  xorps   xmm0, xmm0
0x180033139  movups  [rsp+2D0h+Src], xmm0
0x18003313e  xorps   xmm1, xmm1
0x180033141  movdqu  [rbp+1D0h+var_248], xmm1
0x180033146  mov     r8d, 22h ; '"'
0x18003314c  lea     rdx, aInfoUnlockDura; "INFO  Unlock duration expired at: "
0x180033153  lea     rcx, [rsp+2D0h+Src]
0x180033158  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003315d  nop
0x18003315e  lea     rdx, [rbp+1D0h+var_220]; void *
0x180033162  lea     rcx, [rsp+2D0h+Src]; Src
0x180033167  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003316c  lea     r8, [rsp+2D0h+Src]
0x180033171  cmp     qword ptr [rbp+1D0h+var_248+8], 7
0x180033176  cmova   r8, qword ptr [rsp+2D0h+Src]; unsigned __int16 *
0x18003317c  mov     rcx, rbx; unsigned __int16 *
0x18003317f  call    ?WriteToLogFile@@YAJPEBG00@Z; WriteToLogFile(ushort const *,ushort const *,ushort const *)
0x180033184  call    ?GetLogger@CConfigLockLogger@@SAPEAV1@XZ; CConfigLockLogger::GetLogger(void)
0x180033189  mov     r8d, edi; int
0x18003318c  lea     rdx, [rbp+1D0h+var_220]; unsigned __int16 *
0x180033190  mov     rcx, rax; this
0x180033193  call    ?LogUnlockDurationExpired@CConfigLockLogger@@QEAAXPEBGJ@Z; CConfigLockLogger::LogUnlockDurationExpired(ushort const *,long)
0x180033198  nop
0x180033199  lea     rcx, [rsp+2D0h+Src]
0x18003319e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800331a3  xor     eax, eax
0x1800331a5  mov     rcx, [rbp+1D0h+var_10]
0x1800331ac  xor     rcx, rsp; StackCookie
0x1800331af  call    __security_check_cookie
0x1800331b4  lea     r11, [rsp+2D0h+var_s0]
0x1800331bc  mov     rbx, [r11+18h]
0x1800331c0  mov     rdi, [r11+20h]
0x1800331c4  mov     rsp, r11
0x1800331c7  pop     rbp
0x1800331c8  retn
```
