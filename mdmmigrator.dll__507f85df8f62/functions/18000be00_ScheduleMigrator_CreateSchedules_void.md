# ScheduleMigrator::CreateSchedules(void)

- ea: `0x18000be00`
- end: `0x18000c20c`
- name: `?CreateSchedules@ScheduleMigrator@@QEAAJXZ`
- size: `1036`
- prototype: `__int64 __fastcall(ScheduleMigrator *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ca90`

## callees

- `0x18000138c`
- `0x18000139c`
- `0x180001628`
- `0x180001824`
- `0x1800022e0`
- `0x180004224`
- `0x180007720`
- `0x180007b38`
- `0x180007bec`
- `0x180009850`
- `0x18000a888`
- `0x18000be00`
- `0x1800194bc`
- `0x18001a5c8`
- `0x18001c054`
- `0x18001c61c`
- `0x18001d3fc`
- `0x18001d75c`
- `0x18001d85c`
- `0x18001da98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c089`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c097`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c097`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18000c034`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18000c034`
- `dmEnrollEngine!GetEnrollmentType` at `0x18000c052`
- `dmEnrollEngine!GetEnrollmentType` at `0x18000c052`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000beba`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000beba`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000c018`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000c018`

## string_xrefs

- `0x18000bf8f`: `Failed to create renewal schedules.`
- `0x18000bffa`: `Failed to create OMA-DM client task.`
- `0x18000c186`: `Failed to create polling schedules.`
- `0x18000c0fe`: `ScheduleMigrator::CreateSchedules`
- `0x18000c1b2`: `ScheduleMigrator::CreateSchedules`
- `0x18000c0d2`: `Failed to create polling schedules for multiple session.`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateSchedules(ScheduleMigrator *this)
{
  unsigned __int64 v2; // r8
  __int64 v3; // rbx
  const wchar_t *v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  const wchar_t *v7; // rcx
  size_t v8; // r8
  int v9; // eax
  const unsigned __int16 *v10; // rbx
  __int64 result; // rax
  const unsigned __int16 *v12; // rdx
  signed int v13; // edi
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  const char *v17; // rax
  int *v18; // rdx
  __int64 v19; // r8
  signed int v20; // edi
  unsigned int v21; // ebx
  void *v22; // rdi
  HANDLE ProcessHeap; // rax
  const unsigned __int16 **v24; // rax
  const unsigned __int16 **v25; // r8
  const unsigned __int16 **v26; // r9
  unsigned int v27; // eax
  const unsigned __int16 **v28; // rax
  const unsigned __int16 **v29; // r8
  const unsigned __int16 **v30; // r9
  unsigned int v31; // eax
  int v32; // [rsp+20h] [rbp-79h]
  const unsigned __int16 *v33; // [rsp+30h] [rbp-69h]
  unsigned int v34; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-45h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-41h] BYREF
  int v37; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v38; // [rsp+68h] [rbp-31h] BYREF
  struct _FILETIME v39[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v40; // [rsp+80h] [rbp-19h]
  LPVOID lpMem; // [rsp+90h] [rbp-9h] BYREF
  wchar_t *S1[2]; // [rsp+98h] [rbp-1h] BYREF
  __int128 v43; // [rsp+A8h] [rbp+Fh]
  GUID pclsid; // [rsp+C0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *(_OWORD *)S1 = 0;
  v43 = 0;
  v2 = -1;
  do
    ++v2;
  while ( enrollmentIdRtv[v2] );
  std::wstring::_Construct<1,unsigned short const *>(S1, enrollmentIdRtv, v2);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
    (__int64)this + 8,
    v39,
    (__int64)S1);
  v3 = v40;
  if ( *(_BYTE *)(v40 + 25) )
    goto LABEL_12;
  v4 = (const wchar_t *)(v40 + 32);
  v5 = *(_QWORD *)(v40 + 48);
  if ( *(_QWORD *)(v40 + 56) > 7u )
    v4 = *(const wchar_t **)v4;
  v6 = v43;
  v7 = (const wchar_t *)S1;
  if ( *((_QWORD *)&v43 + 1) > 7u )
    v7 = S1[0];
  v8 = v43;
  if ( v5 < (unsigned __int64)v43 )
    v8 = *(_QWORD *)(v40 + 48);
  v9 = wmemcmp(v7, v4, v8);
  if ( v9 )
  {
    if ( v9 >= 0 )
      goto LABEL_14;
LABEL_12:
    std::_Xout_of_range("invalid map<K, T> key");
    __debugbreak();
  }
  if ( v6 < v5 )
    goto LABEL_12;
LABEL_14:
  v10 = (const unsigned __int16 *)(v3 + 64);
  if ( *((_QWORD *)v10 + 3) > 7u )
    v10 = *(const unsigned __int16 **)v10;
  std::wstring::~wstring((char **)S1);
  v39[0] = 0;
  result = GetDeviceCertExpiryTime(v10, v39);
  if ( (_DWORD)result != -2147024894 )
  {
    if ( (int)result < 0 )
      return result;
    v34 = 0;
    result = GetRenewPeriodInSeconds(v10, &v34);
    if ( (int)result < 0 )
      return result;
    v35 = 0;
    result = GetRenewRetryIntervalInSeconds(v10, 1, &v35);
    if ( (int)result < 0 )
      return result;
    v38 = 0;
    result = GetRenewRetryIntervalInSeconds(v10, 0, &v38);
    if ( (int)result < 0 )
      return result;
    v37 = 0;
    result = IsROBOMode(v10, &v37);
    if ( (int)result < 0 )
      return result;
    v13 = ScheduleRenewalSession(v10, v39[0], v34, v35, v38, v37, v33);
    if ( v13 < 0 )
    {
      v16 = (unsigned int)dword_18002B0C0;
      if ( (unsigned int)dword_18002B0C0 <= 5 )
        return (unsigned int)v13;
      v17 = "Failed to create renewal schedules.";
      v18 = &dword_18002582C;
LABEL_25:
      v39[0] = (struct _FILETIME)v17;
      v34 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v16,
        (__int64)v18,
        v14,
        v15,
        (const unsigned __int16 **)v39,
        (__int64)&v34);
      return (unsigned int)v13;
    }
  }
  v13 = ScheduleOMADMClientTask(v10, v12);
  if ( v13 < 0 )
  {
    v16 = (unsigned int)dword_18002B0C0;
    if ( (unsigned int)dword_18002B0C0 <= 5 )
      return (unsigned int)v13;
    v17 = "Failed to create OMA-DM client task.";
    v18 = (int *)&byte_1800257DF;
    goto LABEL_25;
  }
  pclsid = 0;
  CLSIDFromString(v10, &pclsid);
  lpMem = 0;
  *(GUID *)&v39[0].dwLowDateTime = pclsid;
  GetEnrollmentSID(v39, &lpMem);
  v36 = 63;
  *(GUID *)&v39[0].dwLowDateTime = pclsid;
  GetEnrollmentType(v39, &v36);
  v20 = SyncPollingOptions(v10, lpMem, v19, v36);
  if ( v20 < 0 )
  {
    if ( (unsigned int)dword_18002B0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002B0C0, 0x400000000000LL) )
    {
      _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v39, "Failed to create polling schedules.");
      v34 = v20;
      _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
        &v38,
        "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp");
      v35 = 103;
      v28 = (const unsigned __int16 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
                                         &v37,
                                         L"ScheduleMigrator::CreateSchedules");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&v35,
        (__int64)&dword_18002577C,
        (__int64)v29,
        (__int64)v30,
        v28,
        (__int64)&v35,
        v30,
        (__int64)&v34,
        v29);
    }
    v31 = wil::verify_hresult<long>((unsigned int)v20);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp",
      (const char *)v31,
      v32);
  }
  v21 = SyncPollingOptionsForMultipleSession(v10);
  if ( (v21 & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_18002B0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002B0C0, 0x400000000000LL) )
    {
      _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
        v39,
        "Failed to create polling schedules for multiple session.");
      v34 = v21;
      _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
        &v38,
        "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp");
      v35 = 110;
      v24 = (const unsigned __int16 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
                                         &v37,
                                         L"ScheduleMigrator::CreateSchedules");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&v35,
        (__int64)&dword_180025704,
        (__int64)v25,
        (__int64)v26,
        v24,
        (__int64)&v35,
        v25,
        (__int64)&v34,
        v26);
    }
    v27 = wil::verify_hresult<long>(v21);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp",
      (const char *)v27,
      v32);
  }
  v22 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
  }
  return v21;
}

```

## disassembly

```asm
0x18000be00  mov     [rsp-8+arg_8], rbx
0x18000be05  mov     [rsp-8+arg_10], rsi
0x18000be0a  push    rbp
0x18000be0b  push    rdi
0x18000be0c  push    r14
0x18000be0e  lea     rbp, [rsp-47h]
0x18000be13  sub     rsp, 0E0h
0x18000be1a  mov     rax, cs:__security_cookie
0x18000be21  xor     rax, rsp
0x18000be24  mov     [rbp+57h+var_20], rax
0x18000be28  mov     rbx, rcx
0x18000be2b  mov     rdx, cs:?enrollmentIdRtv@@3PEBGEB; ushort const * const enrollmentIdRtv
0x18000be32  xorps   xmm0, xmm0
0x18000be35  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18000be39  xorps   xmm1, xmm1
0x18000be3c  movdqu  [rbp+57h+var_48], xmm1
0x18000be41  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000be45  xor     r14d, r14d
0x18000be48  inc     r8
0x18000be4b  cmp     [rdx+r8*2], r14w
0x18000be50  jnz     short loc_18000BE48
0x18000be52  lea     rcx, [rbp+57h+S1]
0x18000be56  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000be5b  nop
0x18000be5c  lea     rcx, [rbx+8]
0x18000be60  lea     r8, [rbp+57h+S1]
0x18000be64  lea     rdx, [rbp+57h+var_80]
0x18000be68  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000be6d  mov     rbx, [rbp+57h+var_70]
0x18000be71  cmp     [rbx+19h], r14b
0x18000be75  jnz     short loc_18000BEB3
0x18000be77  lea     rdx, [rbx+20h]
0x18000be7b  mov     rdi, [rdx+10h]
0x18000be7f  cmp     qword ptr [rdx+18h], 7
0x18000be84  jbe     short loc_18000BE89
0x18000be86  mov     rdx, [rdx]; S2
0x18000be89  mov     rsi, qword ptr [rbp+57h+var_48]
0x18000be8d  lea     rcx, [rbp+57h+S1]
0x18000be91  cmp     qword ptr [rbp+57h+var_48+8], 7
0x18000be96  cmova   rcx, [rbp+57h+S1]; S1
0x18000be9b  mov     r8, rsi
0x18000be9e  cmp     rdi, rsi
0x18000bea1  cmovb   r8, rdi; N
0x18000bea5  call    wmemcmp
0x18000beaa  test    eax, eax
0x18000beac  jnz     short loc_18000BEC1
0x18000beae  cmp     rsi, rdi
0x18000beb1  jnb     short loc_18000BEC3
0x18000beb3  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18000beba  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000bec0  int     3; Trap to Debugger
0x18000bec1  js      short loc_18000BEB3
0x18000bec3  add     rbx, 40h ; '@'
0x18000bec7  cmp     qword ptr [rbx+18h], 7
0x18000becc  jbe     short loc_18000BED1
0x18000bece  mov     rbx, [rbx]
0x18000bed1  lea     rcx, [rbp+57h+S1]; void *
0x18000bed5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000beda  mov     qword ptr [rbp+57h+var_80.dwLowDateTime], r14
0x18000bede  lea     rdx, [rbp+57h+var_80]; struct _FILETIME *
0x18000bee2  mov     rcx, rbx; unsigned __int16 *
0x18000bee5  call    ?GetDeviceCertExpiryTime@@YAJPEBGPEAU_FILETIME@@@Z; GetDeviceCertExpiryTime(ushort const *,_FILETIME *)
0x18000beea  cmp     eax, 80070002h
0x18000beef  jz      loc_18000BFE1
0x18000bef5  test    eax, eax
0x18000bef7  js      loc_18000BFBD
0x18000befd  mov     [rbp+57h+var_A0], r14d
0x18000bf01  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x18000bf05  mov     rcx, rbx; unsigned __int16 *
0x18000bf08  call    ?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z; GetRenewPeriodInSeconds(ushort const *,ulong *)
0x18000bf0d  test    eax, eax
0x18000bf0f  js      loc_18000BFBD
0x18000bf15  mov     [rbp+57h+var_9C], r14d
0x18000bf19  lea     r8, [rbp+57h+var_9C]; unsigned int *
0x18000bf1d  mov     edx, 1; int
0x18000bf22  mov     rcx, rbx; unsigned __int16 *
0x18000bf25  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x18000bf2a  test    eax, eax
0x18000bf2c  js      loc_18000BFBD
0x18000bf32  mov     [rbp+57h+var_88], r14d
0x18000bf36  lea     r8, [rbp+57h+var_88]; unsigned int *
0x18000bf3a  xor     edx, edx; int
0x18000bf3c  mov     rcx, rbx; unsigned __int16 *
0x18000bf3f  call    ?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z; GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)
0x18000bf44  test    eax, eax
0x18000bf46  js      short loc_18000BFBD
0x18000bf48  mov     [rbp+57h+var_90], r14d
0x18000bf4c  lea     rdx, [rbp+57h+var_90]; int *
0x18000bf50  mov     rcx, rbx; unsigned __int16 *
0x18000bf53  call    ?IsROBOMode@@YAJPEBGPEAH@Z; IsROBOMode(ushort const *,int *)
0x18000bf58  test    eax, eax
0x18000bf5a  js      short loc_18000BFBD
0x18000bf5c  mov     eax, [rbp+57h+var_90]
0x18000bf5f  mov     [rsp+0F0h+var_C8], eax; int
0x18000bf63  mov     eax, [rbp+57h+var_88]
0x18000bf66  mov     [rsp+0F0h+var_D0], eax; unsigned int
0x18000bf6a  mov     r9d, [rbp+57h+var_9C]; unsigned int
0x18000bf6e  mov     r8d, [rbp+57h+var_A0]; unsigned int
0x18000bf72  mov     rdx, qword ptr [rbp+57h+var_80.dwLowDateTime]; struct _FILETIME
0x18000bf76  mov     rcx, rbx; unsigned __int16 *
0x18000bf79  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x18000bf7e  mov     edi, eax
0x18000bf80  test    eax, eax
0x18000bf82  jns     short loc_18000BFE1
0x18000bf84  mov     ecx, cs:dword_18002B0C0
0x18000bf8a  cmp     ecx, 5
0x18000bf8d  jbe     short loc_18000BFBB
0x18000bf8f  lea     rax, aFailedToCreate_1; "Failed to create renewal schedules."
0x18000bf96  lea     rdx, dword_18002582C
0x18000bf9d  mov     qword ptr [rbp+57h+var_80.dwLowDateTime], rax
0x18000bfa1  lea     rax, [rbp+57h+var_A0]
0x18000bfa5  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18000bfaa  lea     rax, [rbp+57h+var_80]
0x18000bfae  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18000bfb3  mov     [rbp+57h+var_A0], edi
0x18000bfb6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000bfbb  mov     eax, edi
0x18000bfbd  mov     rcx, [rbp+57h+var_20]
0x18000bfc1  xor     rcx, rsp; StackCookie
0x18000bfc4  call    __security_check_cookie
0x18000bfc9  lea     r11, [rsp+0F0h+var_10]
0x18000bfd1  mov     rbx, [r11+28h]
0x18000bfd5  mov     rsi, [r11+30h]
0x18000bfd9  mov     rsp, r11
0x18000bfdc  pop     r14
0x18000bfde  pop     rdi
0x18000bfdf  pop     rbp
0x18000bfe0  retn
0x18000bfe1  mov     rcx, rbx; unsigned __int16 *
0x18000bfe4  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x18000bfe9  mov     edi, eax
0x18000bfeb  test    eax, eax
0x18000bfed  jns     short loc_18000C00A
0x18000bfef  mov     ecx, cs:dword_18002B0C0
0x18000bff5  cmp     ecx, 5
0x18000bff8  jbe     short loc_18000BFBB
0x18000bffa  lea     rax, aFailedToCreate_0; "Failed to create OMA-DM client task."
0x18000c001  lea     rdx, byte_1800257DF
0x18000c008  jmp     short loc_18000BF9D
0x18000c00a  xorps   xmm0, xmm0
0x18000c00d  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18000c011  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18000c015  mov     rcx, rbx; lpsz
0x18000c018  call    cs:__imp_CLSIDFromString
0x18000c01e  nop
0x18000c01f  mov     [rbp+57h+lpMem], r14
0x18000c023  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18000c027  movdqa  xmmword ptr [rbp+57h+var_80.dwLowDateTime], xmm0
0x18000c02c  lea     rdx, [rbp+57h+lpMem]
0x18000c030  lea     rcx, [rbp+57h+var_80]
0x18000c034  call    cs:__imp_GetEnrollmentSID
0x18000c03a  mov     [rbp+57h+var_98], 3Fh ; '?'
0x18000c041  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18000c045  movdqa  xmmword ptr [rbp+57h+var_80.dwLowDateTime], xmm0
0x18000c04a  lea     rdx, [rbp+57h+var_98]
0x18000c04e  lea     rcx, [rbp+57h+var_80]
0x18000c052  call    cs:__imp_GetEnrollmentType
0x18000c058  mov     r9d, [rbp+57h+var_98]
0x18000c05c  mov     rdx, [rbp+57h+lpMem]
0x18000c060  mov     rcx, rbx
0x18000c063  call    ?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z; SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)
0x18000c068  mov     edi, eax
0x18000c06a  test    eax, eax
0x18000c06c  js      loc_18000C158
0x18000c072  mov     rcx, rbx; pszMore
0x18000c075  call    ?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z; SyncPollingOptionsForMultipleSession(ushort const *)
0x18000c07a  mov     ebx, eax
0x18000c07c  test    eax, eax
0x18000c07e  js      short loc_18000C0A4
0x18000c080  mov     rdi, [rbp+57h+lpMem]
0x18000c084  test    rdi, rdi
0x18000c087  jz      short loc_18000C09D
0x18000c089  call    cs:__imp_GetProcessHeap
0x18000c08f  mov     rcx, rax; hHeap
0x18000c092  mov     r8, rdi; lpMem
0x18000c095  xor     edx, edx; dwFlags
0x18000c097  call    cs:__imp_HeapFree
0x18000c09d  mov     eax, ebx
0x18000c09f  jmp     loc_18000BFBD
0x18000c0a4  mov     ecx, cs:dword_18002B0C0
0x18000c0aa  mov     edi, 6Eh ; 'n'
0x18000c0af  cmp     ecx, 5
0x18000c0b2  jbe     loc_18000C13B
0x18000c0b8  mov     rdx, 400000000000h
0x18000c0c2  lea     rcx, dword_18002B0C0
0x18000c0c9  call    _tlgKeywordOn
0x18000c0ce  test    al, al
0x18000c0d0  jz      short loc_18000C13B
0x18000c0d2  lea     rdx, aFailedToCreate; "Failed to create polling schedules for "...
0x18000c0d9  lea     rcx, [rbp+57h+var_80]
0x18000c0dd  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000c0e2  mov     r9, rax
0x18000c0e5  mov     [rbp+57h+var_A0], ebx
0x18000c0e8  lea     rdx, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000c0ef  lea     rcx, [rbp+57h+var_88]
0x18000c0f3  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000c0f8  mov     r8, rax
0x18000c0fb  mov     [rbp+57h+var_9C], edi
0x18000c0fe  lea     rdx, aSchedulemigrat; "ScheduleMigrator::CreateSchedules"
0x18000c105  lea     rcx, [rbp+57h+var_90]
0x18000c109  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000c10e  mov     [rsp+0F0h+var_B0], r9
0x18000c113  lea     rcx, [rbp+57h+var_A0]
0x18000c117  mov     [rsp+0F0h+var_B8], rcx
0x18000c11c  mov     [rsp+0F0h+var_C0], r8
0x18000c121  lea     rcx, [rbp+57h+var_9C]
0x18000c125  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x18000c12a  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18000c12f  lea     rdx, dword_180025704
0x18000c136  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c13b  mov     ecx, ebx
0x18000c13d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c142  mov     r9d, eax; char *
0x18000c145  mov     rcx, [rbp+5Fh]; this
0x18000c149  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000c150  mov     edx, edi; void *
0x18000c152  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c158  mov     ecx, cs:dword_18002B0C0
0x18000c15e  mov     ebx, 67h ; 'g'
0x18000c163  cmp     ecx, 5
0x18000c166  jbe     loc_18000C1EF
0x18000c16c  mov     rdx, 400000000000h
0x18000c176  lea     rcx, dword_18002B0C0
0x18000c17d  call    _tlgKeywordOn
0x18000c182  test    al, al
0x18000c184  jz      short loc_18000C1EF
0x18000c186  lea     rdx, aFailedToCreate_2; "Failed to create polling schedules."
0x18000c18d  lea     rcx, [rbp+57h+var_80]
0x18000c191  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000c196  mov     r8, rax
0x18000c199  mov     [rbp+57h+var_A0], edi
0x18000c19c  lea     rdx, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000c1a3  lea     rcx, [rbp+57h+var_88]
0x18000c1a7  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000c1ac  mov     r9, rax
0x18000c1af  mov     [rbp+57h+var_9C], ebx
0x18000c1b2  lea     rdx, aSchedulemigrat; "ScheduleMigrator::CreateSchedules"
0x18000c1b9  lea     rcx, [rbp+57h+var_90]
0x18000c1bd  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000c1c2  mov     [rsp+0F0h+var_B0], r8
0x18000c1c7  lea     rcx, [rbp+57h+var_A0]
0x18000c1cb  mov     [rsp+0F0h+var_B8], rcx
0x18000c1d0  mov     [rsp+0F0h+var_C0], r9
0x18000c1d5  lea     rcx, [rbp+57h+var_9C]
0x18000c1d9  mov     qword ptr [rsp+0F0h+var_C8], rcx
0x18000c1de  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18000c1e3  lea     rdx, dword_18002577C
0x18000c1ea  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c1ef  mov     ecx, edi
0x18000c1f1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000c1f6  mov     r9d, eax; char *
0x18000c1f9  mov     rcx, [rbp+5Fh]; this
0x18000c1fd  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000c204  mov     edx, ebx; void *
0x18000c206  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
