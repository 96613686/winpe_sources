# CCellularSettingHelperCommon::GetSubscriberInformation(void)

- ea: `0x180047470`
- end: `0x1800478cc`
- name: `?GetSubscriberInformation@CCellularSettingHelperCommon@@UEAAJXZ`
- size: `1116`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180039f54`
- `0x180047470`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047622`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047716`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047622`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047716`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800478b2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800478b2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180047600`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800477cb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800478a3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180047600`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800477cb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800478a3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180047553`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180047553`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800475b8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800475b8`

## string_xrefs

- `0x180047561`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x1800475e5`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x1800477a0`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x1800474d2`: `CCellularSettingHelperCommon::GetSubscriberInformation`
- `0x1800476a3`: `CCellularSettingHelperCommon::GetSubscriberInformation`
- `0x18004782e`: `CCellularSettingHelperCommon::GetSubscriberInformation`
- `0x180047689`: `No telephone number information in readyInfo.`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::GetSubscriberInformation(CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // r15
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  __int64 v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // edi
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // [rsp+20h] [rbp-49h]
  unsigned int *v25; // [rsp+20h] [rbp-49h]
  __int64 v26; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v27[4]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 *v28[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+70h] [rbp+7h]
  unsigned __int16 *v30[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v33; // [rsp+D8h] [rbp+6Fh] BYREF
  int v34; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v35; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_OWORD *)v30 = 0;
  v31 = 0;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  std::vector<unsigned short>::resize(v30);
  std::vector<unsigned short>::resize(v28);
  StringCchPrintfW(v30[0], v30[1] - v30[0], L"Enter");
  v24 = 292;
  StringCchPrintfW(v28[0], v28[1] - v28[0], L"%S(%d):%s", "CCellularSettingHelperCommon::GetSubscriberInformation");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v27 = v28[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&byte_180079057,
      v3,
      v4,
      (const unsigned __int16 **)v27);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v28);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  v26 = 0;
  v33 = 0;
  v5 = WwanOpenHandle(1, 0, &v33, &v26);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x126,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v24);
  v35 = 0;
  v25 = &v35;
  v34 = 0;
  Interface = WwanQueryInterface(v26, (char *)this + 8, 7);
  if ( Interface )
  {
    v8 = Interface;
    v9 = 306;
  }
  else
  {
    v8 = MEMORY[0x400];
    if ( !MEMORY[0x400] )
    {
      if ( MEMORY[0x3F0] )
      {
        v11 = MEMORY[0x3F8];
        v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
        v13 = *((_QWORD *)this + 3);
        if ( v13 )
          (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v13 + 80LL))(v13, (char *)this + 8, v11);
        if ( this != (CCellularSettingHelperCommon *)-48LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      }
      else
      {
        v29 = 0;
        v31 = 0;
        *(_OWORD *)v28 = 0;
        *(_OWORD *)v30 = 0;
        std::vector<unsigned short>::resize(v28);
        std::vector<unsigned short>::resize(v30);
        StringCchPrintfW(v28[0], v28[1] - v28[0], L"No telephone number information in readyInfo.");
        LODWORD(v25) = 325;
        StringCchPrintfW(
          v30[0],
          v30[1] - v30[0],
          L"%S(%d):%s",
          "CCellularSettingHelperCommon::GetSubscriberInformation");
        v14 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v14 > 4u )
        {
          *(unsigned __int16 **)v27 = v30[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v14,
            (__int64)&byte_180079037,
            v15,
            v16,
            (const unsigned __int16 **)v27);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v28);
        v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
      }
      EnterCriticalSection(v12);
      v17 = *((_QWORD *)this + 3);
      if ( !v17 )
        goto LABEL_25;
      (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v17 + 96LL))(v17, (char *)this + 8, 952);
      (*(void (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 3) + 248LL))(
        *((_QWORD *)this + 3),
        (char *)this + 8,
        920);
      v18 = *((_QWORD *)this + 5);
      *(_OWORD *)v27 = 0;
      if ( v18 )
      {
        *(_QWORD *)v27 = *((_QWORD *)this + 4);
        *(_QWORD *)&v27[2] = v18;
        _InterlockedIncrement((volatile signed __int32 *)(v18 + 12));
      }
      v19 = CWwanTranslator::SetAdapterSimIccIdImsi(v27, (char *)this + 8, 952, 920);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x154,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
          (const char *)(unsigned int)v19,
          (int)v25);
        if ( v12 )
          LeaveCriticalSection(v12);
        v10 = v20;
      }
      else
      {
LABEL_25:
        if ( v12 )
          LeaveCriticalSection(v12);
        v29 = 0;
        v31 = 0;
        *(_OWORD *)v28 = 0;
        *(_OWORD *)v30 = 0;
        std::vector<unsigned short>::resize(v28);
        std::vector<unsigned short>::resize(v30);
        StringCchPrintfW(v28[0], v28[1] - v28[0], L"Exit");
        LODWORD(v25) = 344;
        StringCchPrintfW(
          v30[0],
          v30[1] - v30[0],
          L"%S(%d):%s",
          "CCellularSettingHelperCommon::GetSubscriberInformation",
          v25,
          v28[0],
          &v34,
          0);
        v21 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v21 > 5u )
        {
          *(unsigned __int16 **)v27 = v30[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v21,
            (__int64)byte_180078FF1,
            v22,
            v23,
            (const unsigned __int16 **)v27);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v28);
        v10 = 0;
      }
      goto LABEL_30;
    }
    v9 = 309;
  }
  v10 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v9,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
          (const char *)v8,
          (unsigned int)&v35);
LABEL_30:
  WwanCloseHandle(v26, 0);
  return v10;
}

```

## disassembly

```asm
0x180047470  push    rbp
0x180047472  push    rbx
0x180047473  push    rsi
0x180047474  push    rdi
0x180047475  push    r12
0x180047477  push    r14
0x180047479  push    r15
0x18004747b  lea     rbp, [rsp-27h]
0x180047480  sub     rsp, 90h
0x180047487  xorps   xmm0, xmm0
0x18004748a  mov     rdi, rcx
0x18004748d  xor     r12d, r12d
0x180047490  lea     rcx, [rbp+57h+var_48]
0x180047494  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x180047499  mov     [rbp+57h+var_38], r12
0x18004749d  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800474a2  mov     [rbp+57h+var_50], r12
0x1800474a6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800474ab  lea     rcx, [rbp+57h+var_60]
0x1800474af  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800474b4  mov     rdx, [rbp+57h+var_48+8]
0x1800474b8  lea     r8, aEnter; "Enter"
0x1800474bf  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x1800474c3  sub     rdx, rcx
0x1800474c6  sar     rdx, 1; unsigned __int64
0x1800474c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800474ce  mov     rdx, [rbp+57h+var_60+8]
0x1800474d2  lea     r9, aCcellularsetti_10; "CCellularSettingHelperCommon::GetSubscr"...
0x1800474d9  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x1800474dd  lea     r8, aSDS; "%S(%d):%s"
0x1800474e4  mov     rax, [rbp+57h+var_48]
0x1800474e8  sub     rdx, rcx
0x1800474eb  mov     [rsp+0C0h+var_98], rax
0x1800474f0  sar     rdx, 1; unsigned __int64
0x1800474f3  mov     [rsp+0C0h+var_A0], 124h
0x1800474fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047500  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047505  mov     ecx, [rax]
0x180047507  cmp     ecx, 5
0x18004750a  jbe     short loc_18004752C
0x18004750c  mov     rcx, [rbp+57h+var_60]
0x180047510  lea     rdx, byte_180079057
0x180047517  mov     qword ptr [rbp+57h+var_70], rcx
0x18004751b  lea     rcx, [rbp+57h+var_70]
0x18004751f  mov     qword ptr [rsp+0C0h+var_A0], rcx; unsigned int
0x180047524  mov     rcx, rax
0x180047527  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004752c  lea     rcx, [rbp+57h+var_60]
0x180047530  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047535  lea     rcx, [rbp+57h+var_48]
0x180047539  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004753e  xor     edx, edx
0x180047540  mov     [rbp+57h+var_78], r12
0x180047544  lea     r9, [rbp+57h+var_78]
0x180047548  mov     [rbp+57h+arg_8], r12d
0x18004754c  lea     r8, [rbp+57h+arg_8]
0x180047550  lea     ecx, [rdx+1]
0x180047553  call    cs:__imp_WwanOpenHandle
0x180047559  test    eax, eax
0x18004755b  jz      short loc_18004757A
0x18004755d  mov     rcx, [rbp+5Fh]; this
0x180047561  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047568  mov     r9d, eax; char *
0x18004756b  mov     edx, 126h; void *
0x180047570  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047575  jmp     loc_1800478BA
0x18004757a  mov     rcx, [rbp+57h+var_78]
0x18004757e  lea     rax, [rbp+57h+arg_10]
0x180047582  mov     [rsp+0C0h+var_88], r12
0x180047587  lea     r14, [rdi+8]
0x18004758b  mov     [rsp+0C0h+var_90], rax
0x180047590  xor     r9d, r9d
0x180047593  lea     rax, [rbp+57h+var_80]
0x180047597  mov     [rbp+57h+var_80], r12
0x18004759b  mov     [rsp+0C0h+var_98], rax
0x1800475a0  mov     rdx, r14
0x1800475a3  lea     rax, [rbp+57h+arg_18]
0x1800475a7  mov     [rbp+57h+arg_18], r12d
0x1800475ab  lea     r8d, [r9+7]
0x1800475af  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x1800475b4  mov     [rbp+57h+arg_10], r12d
0x1800475b8  call    cs:__imp_WwanQueryInterface
0x1800475be  test    eax, eax
0x1800475c0  jz      short loc_1800475CC
0x1800475c2  mov     r9d, eax
0x1800475c5  mov     edx, 132h
0x1800475ca  jmp     short loc_1800475E1
0x1800475cc  mov     rsi, [rbp+57h+var_80]
0x1800475d0  mov     r9d, [rsi+400h]; char *
0x1800475d7  test    r9d, r9d
0x1800475da  jz      short loc_18004760B
0x1800475dc  mov     edx, 135h; void *
0x1800475e1  mov     rcx, [rbp+5Fh]; this
0x1800475e5  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800475ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800475f1  mov     rcx, [rbp+57h+var_80]
0x1800475f5  mov     ebx, eax
0x1800475f7  test    rcx, rcx
0x1800475fa  jz      loc_1800478AC
0x180047600  call    cs:__imp_WwanFreeMemory
0x180047606  jmp     loc_1800478AC
0x18004760b  cmp     [rsi+3F0h], r12d
0x180047612  jbe     short loc_18004765B
0x180047614  mov     r15, [rsi+3F8h]
0x18004761b  lea     rbx, [rdi+30h]
0x18004761f  mov     rcx, rbx; lpCriticalSection
0x180047622  call    cs:__imp_EnterCriticalSection
0x180047628  mov     rcx, [rdi+18h]
0x18004762c  test    rcx, rcx
0x18004762f  jz      short loc_180047644
0x180047631  mov     rax, [rcx]
0x180047634  lea     r8, [r15+rsi]
0x180047638  mov     rdx, r14
0x18004763b  mov     rax, [rax+50h]
0x18004763f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047644  test    rbx, rbx
0x180047647  jz      loc_180047713
0x18004764d  mov     rcx, rbx; lpCriticalSection
0x180047650  call    cs:__imp_LeaveCriticalSection
0x180047656  jmp     loc_180047713
0x18004765b  xorps   xmm0, xmm0
0x18004765e  mov     [rbp+57h+var_50], r12
0x180047662  xorps   xmm1, xmm1
0x180047665  mov     [rbp+57h+var_38], r12
0x180047669  lea     rcx, [rbp+57h+var_60]
0x18004766d  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180047672  movdqu  xmmword ptr [rbp+57h+var_48], xmm1
0x180047677  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004767c  lea     rcx, [rbp+57h+var_48]
0x180047680  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047685  mov     rdx, [rbp+57h+var_60+8]
0x180047689  lea     r8, aNoTelephoneNum; "No telephone number information in read"...
0x180047690  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x180047694  sub     rdx, rcx
0x180047697  sar     rdx, 1; unsigned __int64
0x18004769a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004769f  mov     rdx, [rbp+57h+var_48+8]
0x1800476a3  lea     r9, aCcellularsetti_10; "CCellularSettingHelperCommon::GetSubscr"...
0x1800476aa  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x1800476ae  lea     r8, aSDS; "%S(%d):%s"
0x1800476b5  mov     rax, [rbp+57h+var_60]
0x1800476b9  sub     rdx, rcx
0x1800476bc  mov     [rsp+0C0h+var_98], rax
0x1800476c1  sar     rdx, 1; unsigned __int64
0x1800476c4  mov     [rsp+0C0h+var_A0], 145h
0x1800476cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800476d1  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800476d6  mov     ecx, [rax]
0x1800476d8  cmp     ecx, 4
0x1800476db  jbe     short loc_1800476FD
0x1800476dd  mov     rcx, [rbp+57h+var_48]
0x1800476e1  lea     rdx, byte_180079037
0x1800476e8  mov     qword ptr [rbp+57h+var_70], rcx
0x1800476ec  lea     rcx, [rbp+57h+var_70]
0x1800476f0  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x1800476f5  mov     rcx, rax
0x1800476f8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800476fd  lea     rcx, [rbp+57h+var_48]
0x180047701  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047706  lea     rcx, [rbp+57h+var_60]
0x18004770a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004770f  lea     rbx, [rdi+30h]
0x180047713  mov     rcx, rbx; lpCriticalSection
0x180047716  call    cs:__imp_EnterCriticalSection
0x18004771c  mov     rcx, [rdi+18h]
0x180047720  test    rcx, rcx
0x180047723  jz      loc_1800477D8
0x180047729  mov     rax, [rcx]
0x18004772c  lea     r15, [rsi+3B8h]
0x180047733  mov     r8, r15
0x180047736  mov     rdx, r14
0x180047739  mov     rax, [rax+60h]
0x18004773d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047742  mov     rcx, [rdi+18h]
0x180047746  lea     r8, [rsi+398h]
0x18004774d  mov     rdx, r14
0x180047750  mov     rax, [rcx]
0x180047753  mov     rax, [rax+0F8h]
0x18004775a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004775f  mov     rcx, [rdi+28h]
0x180047763  xorps   xmm0, xmm0
0x180047766  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18004776b  test    rcx, rcx
0x18004776e  jz      short loc_180047780
0x180047770  mov     rax, [rdi+20h]
0x180047774  mov     qword ptr [rbp+57h+var_70], rax
0x180047778  mov     qword ptr [rbp+57h+var_70+8], rcx
0x18004777c  lock inc dword ptr [rcx+0Ch]
0x180047780  lea     r9, [rsi+398h]
0x180047787  mov     r8, r15
0x18004778a  mov     rdx, r14
0x18004778d  lea     rcx, [rbp+57h+var_70]
0x180047791  call    ?SetAdapterSimIccIdImsi@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEBG2@Z; CWwanTranslator::SetAdapterSimIccIdImsi(std::weak_ptr<CWwanTranslator>,_GUID const &,ushort const *,ushort const *)
0x180047796  mov     edi, eax
0x180047798  test    eax, eax
0x18004779a  jns     short loc_1800477D8
0x18004779c  mov     rcx, [rbp+5Fh]; this
0x1800477a0  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800477a7  mov     r9d, eax; char *
0x1800477aa  mov     edx, 154h; void *
0x1800477af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800477b4  test    rbx, rbx
0x1800477b7  jz      short loc_1800477C2
0x1800477b9  mov     rcx, rbx; lpCriticalSection
0x1800477bc  call    cs:__imp_LeaveCriticalSection
0x1800477c2  mov     rcx, [rbp+57h+var_80]
0x1800477c6  test    rcx, rcx
0x1800477c9  jz      short loc_1800477D1
0x1800477cb  call    cs:__imp_WwanFreeMemory
0x1800477d1  mov     ebx, edi
0x1800477d3  jmp     loc_1800478AC
0x1800477d8  test    rbx, rbx
0x1800477db  jz      short loc_1800477E6
0x1800477dd  mov     rcx, rbx; lpCriticalSection
0x1800477e0  call    cs:__imp_LeaveCriticalSection
0x1800477e6  xorps   xmm0, xmm0
0x1800477e9  mov     [rbp+57h+var_50], r12
0x1800477ed  xorps   xmm1, xmm1
0x1800477f0  mov     [rbp+57h+var_38], r12
0x1800477f4  lea     rcx, [rbp+57h+var_60]
0x1800477f8  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1800477fd  movdqu  xmmword ptr [rbp+57h+var_48], xmm1
0x180047802  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047807  lea     rcx, [rbp+57h+var_48]
0x18004780b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047810  mov     rdx, [rbp+57h+var_60+8]
0x180047814  lea     r8, aExit; "Exit"
0x18004781b  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004781f  sub     rdx, rcx
0x180047822  sar     rdx, 1; unsigned __int64
0x180047825  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004782a  mov     rdx, [rbp+57h+var_48+8]
0x18004782e  lea     r9, aCcellularsetti_10; "CCellularSettingHelperCommon::GetSubscr"...
0x180047835  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x180047839  lea     r8, aSDS; "%S(%d):%s"
0x180047840  mov     rax, [rbp+57h+var_60]
0x180047844  sub     rdx, rcx
0x180047847  mov     [rsp+0C0h+var_98], rax
0x18004784c  sar     rdx, 1; unsigned __int64
0x18004784f  mov     [rsp+0C0h+var_A0], 158h
0x180047857  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004785c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047861  mov     ecx, [rax]
0x180047863  cmp     ecx, 5
0x180047866  jbe     short loc_180047888
0x180047868  mov     rcx, [rbp+57h+var_48]
0x18004786c  lea     rdx, byte_180078FF1
0x180047873  mov     qword ptr [rbp+57h+var_70], rcx
0x180047877  lea     rcx, [rbp+57h+var_70]
0x18004787b  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180047880  mov     rcx, rax
0x180047883  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047888  lea     rcx, [rbp+57h+var_48]
0x18004788c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047891  lea     rcx, [rbp+57h+var_60]
0x180047895  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004789a  mov     rcx, [rbp+57h+var_80]
0x18004789e  test    rcx, rcx
0x1800478a1  jz      short loc_1800478A9
0x1800478a3  call    cs:__imp_WwanFreeMemory
0x1800478a9  mov     ebx, r12d
0x1800478ac  mov     rcx, [rbp+57h+var_78]
0x1800478b0  xor     edx, edx
0x1800478b2  call    cs:__imp_WwanCloseHandle
0x1800478b8  mov     eax, ebx
0x1800478ba  add     rsp, 90h
0x1800478c1  pop     r15
0x1800478c3  pop     r14
0x1800478c5  pop     r12
0x1800478c7  pop     rdi
0x1800478c8  pop     rsi
0x1800478c9  pop     rbx
0x1800478ca  pop     rbp
0x1800478cb  retn
```
