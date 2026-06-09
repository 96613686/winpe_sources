# GetClrStartupFlagsFromSettings(HKEY__ *,ushort const *)

- ea: `0x140013100`
- end: `0x140013450`
- name: `?GetClrStartupFlagsFromSettings@@YAKPEAUHKEY__@@PEBG@Z`
- size: `848`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140004a0c`
- `0x140007740`
- `0x14000b118`
- `0x140013100`
- `0x1400287d4`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400133dc`
- `ADVAPI32!RegCloseKey` at `0x140013412`
- `ADVAPI32!RegCloseKey` at `0x1400133dc`
- `ADVAPI32!RegCloseKey` at `0x140013412`
- `KERNEL32!GetSystemInfo` at `0x140013275`
- `KERNEL32!GetSystemInfo` at `0x140013275`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001318e`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400131a2`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001322a`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001326b`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400132bc`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001333b`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001334b`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001335f`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400133a2`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400133b6`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400133ca`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001318e`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400131a2`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001322a`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001326b`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400132bc`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001333b`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001334b`
- `KERNEL32!SetEnvironmentVariableW` at `0x14001335f`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400133a2`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400133b6`
- `KERNEL32!SetEnvironmentVariableW` at `0x1400133ca`
- `KERNEL32!GetEnvironmentVariableW` at `0x140013151`
- `KERNEL32!GetEnvironmentVariableW` at `0x140013151`

## string_xrefs

- `0x14001314a`: `COMPLUS_GCHeapCount`
- `0x140013187`: `COMPLUS_GCHeapCount`
- `0x140013334`: `COMPLUS_GCHeapCount`
- `0x1400133af`: `COMPLUS_GCHeapCount`
- `0x140013223`: `GCExpConfigUsedInSession`
- `0x140013264`: `GCExpConfigUsedInSession`
- `0x140013358`: `GCExpConfigUsedInSession`
- `0x140013388`: `GCExpConfigUsedInSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetClrStartupFlagsFromSettings(HKEY a1, const unsigned __int16 *a2)
{
  HKEY v3; // rbx
  unsigned int v4; // ebx
  const WCHAR *v5; // rdx
  WCHAR *p_Buffer; // rdx
  const WCHAR *v7; // rdx
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v9; // rbx
  struct ATL::IAtlStringMgr *v10; // rax
  const WCHAR *v11; // rdx
  unsigned __int16 *v12; // rdx
  LPCWSTR v14; // [rsp+30h] [rbp-19h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-9h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-1h] BYREF
  LPCWSTR lpValue; // [rsp+50h] [rbp+7h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp+Fh] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+60h] [rbp+17h] BYREF
  WCHAR Buffer; // [rsp+90h] [rbp+47h] BYREF

  hKey = 0;
  v19 = 0;
  CVsRegKeyW::Combine((unsigned int)&v19, (_DWORD)a2, (unsigned int)L"VSPerf\\GCMode", 0);
  dword_14009D450 = GetEnvironmentVariableW(L"COMPLUS_GCHeapCount", &Buffer, 4u);
  if ( CVsRegKeyW::Open((CVsRegKeyW *)&hKey, a1, v19, 0x20019u) < 0 )
  {
    if ( !dword_14009D450 )
    {
      SetEnvironmentVariableW(L"COMPLUS_GCHeapCount", L"2");
      SetEnvironmentVariableW(L"VS_Perf_Session_GCHeapCount", L"2");
    }
    v3 = hKey;
    goto LABEL_37;
  }
  v17 = -1;
  if ( CVsRegKeyW::QueryValue((CVsRegKeyW *)&hKey, L"IsPrioritizePerformanceEnabled", &v17) < 0 )
    v17 = 0;
  v4 = 3;
  v15 = 3;
  if ( CVsRegKeyW::QueryValue((CVsRegKeyW *)&hKey, L"GCFlight", &v15) >= 0 )
    v4 = v15;
  else
    v15 = 3;
  if ( !dword_14009D450 )
  {
    if ( v17 == 1 )
    {
      if ( v4 == 2 )
      {
        v7 = L"5";
      }
      else
      {
        v7 = L"4";
        if ( v4 != 1 )
          v7 = L"6";
      }
      SetEnvironmentVariableW(L"GCExpConfigUsedInSession", v7);
      GetSystemInfo(&SystemInfo);
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      lpValue = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                        + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpValue,
        L"%u",
        SystemInfo.dwNumberOfProcessors);
      v9 = lpValue;
      SetEnvironmentVariableW(L"VS_Perf_Session_GCHeapCount", lpValue);
LABEL_28:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
      }
      goto LABEL_35;
    }
    LODWORD(lpValue) = 0;
    if ( v4 == 2 )
    {
      if ( CVsRegKeyW::QueryValue((CVsRegKeyW *)&hKey, L"ServerGCNHeaps", (unsigned int *)&lpValue) >= 0
        && (_DWORD)lpValue )
      {
        v10 = ATL::CAtlStringMgr::GetInstance();
        if ( !v10 )
          ATL::AtlThrowImpl(-2147467259);
        v14 = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v10 + 24LL))(v10) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v14,
          L"%u",
          (unsigned int)lpValue);
        v9 = v14;
        SetEnvironmentVariableW(L"COMPLUS_GCHeapCount", v14);
        SetEnvironmentVariableW(L"VS_Perf_Session_GCHeapCount", v9);
        SetEnvironmentVariableW(L"GCExpConfigUsedInSession", L"2");
        goto LABEL_28;
      }
      v4 = v15;
    }
    v11 = L"1";
    if ( v4 != 1 )
      v11 = L"3";
    SetEnvironmentVariableW(L"GCExpConfigUsedInSession", v11);
    SetEnvironmentVariableW(L"COMPLUS_GCHeapCount", L"2");
    p_Buffer = (WCHAR *)L"2";
    goto LABEL_34;
  }
  if ( v4 == 2 )
  {
    v5 = L"8";
  }
  else
  {
    v5 = L"7";
    if ( v4 != 1 )
      v5 = L"9";
  }
  SetEnvironmentVariableW(L"GCExpConfigUsedInSession", v5);
  p_Buffer = &Buffer;
LABEL_34:
  SetEnvironmentVariableW(L"VS_Perf_Session_GCHeapCount", p_Buffer);
LABEL_35:
  v3 = hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    v3 = 0;
    hKey = 0;
  }
LABEL_37:
  v12 = v19 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
  }
  if ( v3 )
    RegCloseKey(v3);
  return 135173;
}

```

## disassembly

```asm
0x140013100  mov     [rsp-8+arg_10], rbx
0x140013105  push    rbp
0x140013106  lea     rbp, [rsp-57h]
0x14001310b  sub     rsp, 0A0h
0x140013112  mov     rax, cs:__security_cookie
0x140013119  xor     rax, rsp
0x14001311c  mov     [rbp+57h+var_8], rax
0x140013120  mov     rbx, rcx
0x140013123  and     [rbp+57h+hKey], 0
0x140013128  and     [rbp+57h+var_48], 0
0x14001312d  xor     r9d, r9d
0x140013130  lea     r8, aVsperfGcmode; "VSPerf\\GCMode"
0x140013137  lea     rcx, [rbp+57h+var_48]
0x14001313b  call    ?Combine@CVsRegKeyW@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG000@Z; CVsRegKeyW::Combine(ushort const *,ushort const *,ushort const *,ushort const *)
0x140013140  mov     r8d, 4; nSize
0x140013146  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x14001314a  lea     rcx, aComplusGcheapc; "COMPLUS_GCHeapCount"
0x140013151  call    cs:__imp_GetEnvironmentVariableW
0x140013157  mov     cs:dword_14009D450, eax
0x14001315d  mov     r9d, 20019h; unsigned int
0x140013163  mov     r8, [rbp+57h+var_48]; unsigned __int16 *
0x140013167  mov     rdx, rbx; HKEY
0x14001316a  lea     rcx, [rbp+57h+hKey]; this
0x14001316e  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x140013173  test    eax, eax
0x140013175  jns     short loc_1400131B1
0x140013177  cmp     cs:dword_14009D450, 0
0x14001317e  jnz     short loc_1400131A8
0x140013180  lea     rdx, a2; "2"
0x140013187  lea     rcx, aComplusGcheapc; "COMPLUS_GCHeapCount"
0x14001318e  call    cs:__imp_SetEnvironmentVariableW
0x140013194  lea     rdx, a2; "2"
0x14001319b  lea     rcx, aVsPerfSessionG; "VS_Perf_Session_GCHeapCount"
0x1400131a2  call    cs:__imp_SetEnvironmentVariableW
0x1400131a8  mov     rbx, [rbp+57h+hKey]
0x1400131ac  jmp     loc_1400133E8
0x1400131b1  or      [rbp+57h+var_58], 0FFFFFFFFh
0x1400131b5  lea     r8, [rbp+57h+var_58]; unsigned int *
0x1400131b9  lea     rdx, aIsprioritizepe; "IsPrioritizePerformanceEnabled"
0x1400131c0  lea     rcx, [rbp+57h+hKey]; this
0x1400131c4  call    ?QueryValue@CVsRegKeyW@@QEBAJPEBGPEAK@Z; CVsRegKeyW::QueryValue(ushort const *,ulong *)
0x1400131c9  test    eax, eax
0x1400131cb  jns     short loc_1400131D1
0x1400131cd  and     [rbp+57h+var_58], 0
0x1400131d1  mov     ebx, 3
0x1400131d6  mov     [rbp+57h+var_68], ebx
0x1400131d9  lea     r8, [rbp+57h+var_68]; unsigned int *
0x1400131dd  lea     rdx, aGcflight; "GCFlight"
0x1400131e4  lea     rcx, [rbp+57h+hKey]; this
0x1400131e8  call    ?QueryValue@CVsRegKeyW@@QEBAJPEBGPEAK@Z; CVsRegKeyW::QueryValue(ushort const *,ulong *)
0x1400131ed  test    eax, eax
0x1400131ef  jns     short loc_1400131F6
0x1400131f1  mov     [rbp+57h+var_68], ebx
0x1400131f4  jmp     short loc_1400131F9
0x1400131f6  mov     ebx, [rbp+57h+var_68]
0x1400131f9  cmp     cs:dword_14009D450, 0
0x140013200  jz      short loc_140013239
0x140013202  cmp     ebx, 2
0x140013205  jnz     short loc_140013210
0x140013207  lea     rdx, a8; "8"
0x14001320e  jmp     short loc_140013223
0x140013210  cmp     ebx, 1
0x140013213  lea     rdx, a7; "7"
0x14001321a  jz      short loc_140013223
0x14001321c  lea     rdx, a9; "9"
0x140013223  lea     rcx, aGcexpconfiguse; "GCExpConfigUsedInSession"
0x14001322a  call    cs:__imp_SetEnvironmentVariableW
0x140013230  lea     rdx, [rbp+57h+Buffer]
0x140013234  jmp     loc_1400133C3
0x140013239  cmp     [rbp+57h+var_58], 1
0x14001323d  jnz     loc_1400132C7
0x140013243  cmp     ebx, 2
0x140013246  jnz     short loc_140013251
0x140013248  lea     rdx, a5; "5"
0x14001324f  jmp     short loc_140013264
0x140013251  cmp     ebx, 1
0x140013254  lea     rdx, a4; "4"
0x14001325b  jz      short loc_140013264
0x14001325d  lea     rdx, a6; "6"
0x140013264  lea     rcx, aGcexpconfiguse; "GCExpConfigUsedInSession"
0x14001326b  call    cs:__imp_SetEnvironmentVariableW
0x140013271  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x140013275  call    cs:__imp_GetSystemInfo
0x14001327b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140013280  mov     rcx, rax
0x140013283  test    rax, rax
0x140013286  jz      loc_140013445
0x14001328c  mov     rax, [rax]
0x14001328f  call    qword ptr [rax+18h]
0x140013292  add     rax, 18h
0x140013296  mov     [rbp+57h+lpValue], rax
0x14001329a  mov     r8d, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x14001329e  lea     rdx, aU; "%u"
0x1400132a5  lea     rcx, [rbp+57h+lpValue]
0x1400132a9  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1400132ae  mov     rbx, [rbp+57h+lpValue]
0x1400132b2  mov     rdx, rbx; lpValue
0x1400132b5  lea     rcx, aVsPerfSessionG; "VS_Perf_Session_GCHeapCount"
0x1400132bc  call    cs:__imp_SetEnvironmentVariableW
0x1400132c2  jmp     loc_140013366
0x1400132c7  and     dword ptr [rbp+57h+lpValue], 0
0x1400132cb  cmp     ebx, 2
0x1400132ce  jnz     loc_140013388
0x1400132d4  lea     r8, [rbp+57h+lpValue]; unsigned int *
0x1400132d8  lea     rdx, aServergcnheaps; "ServerGCNHeaps"
0x1400132df  lea     rcx, [rbp+57h+hKey]; this
0x1400132e3  call    ?QueryValue@CVsRegKeyW@@QEBAJPEBGPEAK@Z; CVsRegKeyW::QueryValue(ushort const *,ulong *)
0x1400132e8  test    eax, eax
0x1400132ea  js      loc_140013385
0x1400132f0  cmp     dword ptr [rbp+57h+lpValue], 0
0x1400132f4  jbe     loc_140013385
0x1400132fa  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400132ff  mov     rcx, rax
0x140013302  test    rax, rax
0x140013305  jz      loc_14001343A
0x14001330b  mov     rax, [rax]
0x14001330e  call    qword ptr [rax+18h]
0x140013311  add     rax, 18h
0x140013315  mov     [rbp+57h+var_70], rax
0x140013319  mov     r8d, dword ptr [rbp+57h+lpValue]
0x14001331d  lea     rdx, aU; "%u"
0x140013324  lea     rcx, [rbp+57h+var_70]
0x140013328  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14001332d  mov     rbx, [rbp+57h+var_70]
0x140013331  mov     rdx, rbx; lpValue
0x140013334  lea     rcx, aComplusGcheapc; "COMPLUS_GCHeapCount"
0x14001333b  call    cs:__imp_SetEnvironmentVariableW
0x140013341  mov     rdx, rbx; lpValue
0x140013344  lea     rcx, aVsPerfSessionG; "VS_Perf_Session_GCHeapCount"
0x14001334b  call    cs:__imp_SetEnvironmentVariableW
0x140013351  lea     rdx, a2; "2"
0x140013358  lea     rcx, aGcexpconfiguse; "GCExpConfigUsedInSession"
0x14001335f  call    cs:__imp_SetEnvironmentVariableW
0x140013365  nop
0x140013366  lea     rdx, [rbx-18h]
0x14001336a  or      eax, 0FFFFFFFFh
0x14001336d  lock xadd [rdx+10h], eax
0x140013372  sub     eax, 1
0x140013375  jg      short loc_1400133D0
0x140013377  lfence
0x14001337a  mov     rcx, [rdx]
0x14001337d  mov     rax, [rcx]
0x140013380  call    qword ptr [rax+8]
0x140013383  jmp     short loc_1400133D0
0x140013385  mov     ebx, [rbp+57h+var_68]
0x140013388  lea     rcx, aGcexpconfiguse; "GCExpConfigUsedInSession"
0x14001338f  cmp     ebx, 1
0x140013392  lea     rdx, Value; "1"
0x140013399  jz      short loc_1400133A2
0x14001339b  lea     rdx, a3; "3"
0x1400133a2  call    cs:__imp_SetEnvironmentVariableW
0x1400133a8  lea     rdx, a2; "2"
0x1400133af  lea     rcx, aComplusGcheapc; "COMPLUS_GCHeapCount"
0x1400133b6  call    cs:__imp_SetEnvironmentVariableW
0x1400133bc  lea     rdx, a2; "2"
0x1400133c3  lea     rcx, aVsPerfSessionG; "VS_Perf_Session_GCHeapCount"
0x1400133ca  call    cs:__imp_SetEnvironmentVariableW
0x1400133d0  mov     rbx, [rbp+57h+hKey]
0x1400133d4  test    rbx, rbx
0x1400133d7  jz      short loc_1400133E8
0x1400133d9  mov     rcx, rbx; hKey
0x1400133dc  call    cs:__imp_RegCloseKey
0x1400133e2  xor     ebx, ebx
0x1400133e4  mov     [rbp+57h+hKey], rbx
0x1400133e8  mov     rdx, [rbp+57h+var_48]
0x1400133ec  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400133f0  or      eax, 0FFFFFFFFh
0x1400133f3  lock xadd [rdx+10h], eax
0x1400133f8  sub     eax, 1
0x1400133fb  jg      short loc_14001340A
0x1400133fd  lfence
0x140013400  mov     rcx, [rdx]
0x140013403  mov     rax, [rcx]
0x140013406  call    qword ptr [rax+8]
0x140013409  nop
0x14001340a  test    rbx, rbx
0x14001340d  jz      short loc_140013418
0x14001340f  mov     rcx, rbx; hKey
0x140013412  call    cs:__imp_RegCloseKey
0x140013418  mov     eax, 21005h
0x14001341d  mov     rcx, [rbp+57h+var_8]
0x140013421  xor     rcx, rsp; StackCookie
0x140013424  call    __security_check_cookie
0x140013429  mov     rbx, [rsp+0A0h+arg_10]
0x140013431  add     rsp, 0A0h
0x140013438  pop     rbp
0x140013439  retn
0x14001343a  mov     ecx, 80004005h; int
0x14001343f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140013445  mov     ecx, 80004005h; int
0x14001344a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
