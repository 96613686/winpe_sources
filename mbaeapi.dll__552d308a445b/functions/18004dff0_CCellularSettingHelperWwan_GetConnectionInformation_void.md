# CCellularSettingHelperWwan::GetConnectionInformation(void)

- ea: `0x18004dff0`
- end: `0x18004e3c2`
- name: `?GetConnectionInformation@CCellularSettingHelperWwan@@UEAAJXZ`
- size: `978`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180031df8`
- `0x18004dff0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e1f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e1f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e1c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e1c9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004e39e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004e39e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004e392`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004e392`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004e0ef`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004e0ef`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004e14b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004e14b`

## pseudocode

```c
int __fastcall CCellularSettingHelperWwan::GetConnectionInformation(CCellularSettingHelperWwan *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  int v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  unsigned int *v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v22[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  unsigned int v24; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v25[2]; // [rsp+78h] [rbp-88h] BYREF
  int v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[112]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_OWORD *)v22 = 0;
  v23 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  std::vector<unsigned short>::resize(v22);
  std::vector<unsigned short>::resize(v20);
  StringCchPrintfW(v22[0], v22[1] - v22[0], L"Enter");
  v17 = 509;
  StringCchPrintfW(v20[0], v20[1] - v20[0], L"%S(%d):%s", "CCellularSettingHelperWwan::GetConnectionInformation");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v25 = v20[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&word_18007941E,
      v3,
      v4,
      (const unsigned __int16 **)v25);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
  v28 = 0;
  v26 = 0;
  v5 = WwanOpenHandle(1, 0, &v26, &v28);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1FF,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
             (const char *)v5,
             v17);
  v24 = 0;
  v27 = 0;
  v18 = &v24;
  Interface = WwanQueryInterface(v28, (char *)this + 8, 3);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x208,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
           (const char *)Interface,
           (unsigned int)&v24);
  }
  else
  {
    v9 = v27;
    v8 = 0;
    if ( v24 < 208 * *(_DWORD *)(v27 + 220) + 228 )
      v8 = 8;
    if ( v8 )
      v8 |= 0x80070000;
    if ( v8 < 0 )
    {
      v21 = 0;
      v23 = 0;
      *(_OWORD *)v20 = 0;
      *(_OWORD *)v22 = 0;
      std::vector<unsigned short>::resize(v20);
      std::vector<unsigned short>::resize(v22);
      StringCchPrintfW(
        v20[0],
        v20[1] - v20[0],
        L"Error getting connection information. Returned hr=0x%08x",
        (unsigned int)v8,
        &v24,
        &v27,
        0,
        0);
      v19[0] = 546;
      StringCchPrintfW(
        v22[0],
        v22[1] - v22[0],
        L"%S(%d):%s",
        "CCellularSettingHelperWwan::GetConnectionInformation",
        *(_QWORD *)v19,
        v20[0]);
      v11 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v11 > 2u )
      {
        *(unsigned __int16 **)v25 = v22[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v11,
          (__int64)word_1800793DA,
          v12,
          v13,
          (const unsigned __int16 **)v25);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
    }
    else
    {
      memset_0(v29, 0, 0x6Cu);
      CellularSettingUtils::GetCSRegStateFromWwanRegState(
        (const struct _WWAN_REGISTRATION_STATE *)(v9 + 8),
        (struct CellularSettingsRegistrationState *)v29);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      v10 = *((_QWORD *)this + 3);
      if ( v10 )
        (*(void (__fastcall **)(__int64, char *, _BYTE *))(*(_QWORD *)v10 + 72LL))(v10, (char *)this + 8, v29);
      if ( this != (CCellularSettingHelperWwan *)-48LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    }
    v21 = 0;
    v23 = 0;
    *(_OWORD *)v20 = 0;
    *(_OWORD *)v22 = 0;
    std::vector<unsigned short>::resize(v20);
    std::vector<unsigned short>::resize(v22);
    StringCchPrintfW(v20[0], v20[1] - v20[0], L"Exit");
    LODWORD(v18) = 549;
    StringCchPrintfW(
      v22[0],
      v22[1] - v22[0],
      L"%S(%d):%s",
      "CCellularSettingHelperWwan::GetConnectionInformation",
      v18,
      v20[0]);
    v14 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v14 > 5u )
    {
      *(unsigned __int16 **)v25 = v22[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)&byte_1800793B7,
        v15,
        v16,
        (const unsigned __int16 **)v25);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v22);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v20);
  }
  WwanFreeMemory(v27);
  WwanCloseHandle(v28, 0);
  return v8;
}

```

## disassembly

```asm
0x18004dff0  push    rbp
0x18004dff2  push    rbx
0x18004dff3  push    rsi
0x18004dff4  push    rdi
0x18004dff5  push    r14
0x18004dff7  push    r15
0x18004dff9  lea     rbp, [rsp-28h]
0x18004dffe  sub     rsp, 128h
0x18004e005  mov     rax, cs:__security_cookie
0x18004e00c  xor     rax, rsp
0x18004e00f  mov     [rbp+50h+var_40], rax
0x18004e013  xorps   xmm0, xmm0
0x18004e016  mov     rsi, rcx
0x18004e019  xor     r15d, r15d
0x18004e01c  lea     rcx, [rsp+150h+var_F8]
0x18004e021  movdqu  xmmword ptr [rsp+150h+var_F8], xmm0
0x18004e027  mov     [rsp+150h+var_E8], r15
0x18004e02c  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x18004e032  mov     [rsp+150h+var_100], r15
0x18004e037  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e03c  lea     rcx, [rsp+150h+var_110]
0x18004e041  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e046  mov     rdx, [rsp+150h+var_F8+8]
0x18004e04b  lea     r8, aEnter; "Enter"
0x18004e052  mov     rcx, [rsp+150h+var_F8]; unsigned __int16 *
0x18004e057  sub     rdx, rcx
0x18004e05a  sar     rdx, 1; unsigned __int64
0x18004e05d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e062  mov     rdx, [rsp+150h+var_110+8]
0x18004e067  lea     r9, aCcellularsetti_18; "CCellularSettingHelperWwan::GetConnecti"...
0x18004e06e  mov     rcx, [rsp+150h+var_110]; unsigned __int16 *
0x18004e073  lea     r8, aSDS; "%S(%d):%s"
0x18004e07a  mov     rax, [rsp+150h+var_F8]
0x18004e07f  sub     rdx, rcx
0x18004e082  mov     [rsp+150h+var_128], rax
0x18004e087  sar     rdx, 1; unsigned __int64
0x18004e08a  mov     [rsp+150h+var_130], 1FDh
0x18004e092  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e097  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004e09c  mov     ecx, [rax]
0x18004e09e  cmp     ecx, 5
0x18004e0a1  jbe     short loc_18004E0C6
0x18004e0a3  mov     rcx, [rsp+150h+var_110]
0x18004e0a8  lea     rdx, word_18007941E
0x18004e0af  mov     qword ptr [rsp+150h+var_D8], rcx
0x18004e0b4  lea     rcx, [rsp+150h+var_D8]
0x18004e0b9  mov     qword ptr [rsp+150h+var_130], rcx; unsigned int
0x18004e0be  mov     rcx, rax
0x18004e0c1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004e0c6  lea     rcx, [rsp+150h+var_110]
0x18004e0cb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e0d0  lea     rcx, [rsp+150h+var_F8]
0x18004e0d5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e0da  xor     edx, edx
0x18004e0dc  mov     [rbp+50h+var_C0], r15
0x18004e0e0  lea     r9, [rbp+50h+var_C0]
0x18004e0e4  mov     [rbp+50h+var_D0], r15d
0x18004e0e8  lea     r8, [rbp+50h+var_D0]
0x18004e0ec  lea     ecx, [rdx+1]
0x18004e0ef  call    cs:__imp_WwanOpenHandle
0x18004e0f5  test    eax, eax
0x18004e0f7  jz      short loc_18004E116
0x18004e0f9  mov     rcx, [rbp+58h]; this
0x18004e0fd  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004e104  mov     r9d, eax; char *
0x18004e107  mov     edx, 1FFh; void *
0x18004e10c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e111  jmp     loc_18004E3A6
0x18004e116  mov     rcx, [rbp+50h+var_C0]
0x18004e11a  lea     rax, [rbp+50h+var_C8]
0x18004e11e  mov     [rsp+150h+var_118], r15
0x18004e123  lea     rdx, [rsi+8]
0x18004e127  xor     r9d, r9d
0x18004e12a  mov     [rsp+150h+var_120], r15
0x18004e12f  mov     [rsp+150h+var_128], rax
0x18004e134  lea     rax, [rsp+150h+var_E0]
0x18004e139  mov     [rsp+150h+var_E0], r15d
0x18004e13e  mov     [rbp+50h+var_C8], r15
0x18004e142  lea     r8d, [r9+3]
0x18004e146  mov     qword ptr [rsp+150h+var_130], rax; unsigned int
0x18004e14b  call    cs:__imp_WwanQueryInterface
0x18004e151  test    eax, eax
0x18004e153  jz      short loc_18004E174
0x18004e155  mov     rcx, [rbp+58h]; this
0x18004e159  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004e160  mov     r9d, eax; char *
0x18004e163  mov     edx, 208h; void *
0x18004e168  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e16d  mov     ebx, eax
0x18004e16f  jmp     loc_18004E38E
0x18004e174  mov     rdi, [rbp+50h+var_C8]
0x18004e178  mov     ebx, r15d
0x18004e17b  mov     ecx, 8
0x18004e180  imul    eax, [rdi+0DCh], 0D0h
0x18004e18a  add     eax, 0E4h
0x18004e18f  cmp     [rsp+150h+var_E0], eax
0x18004e193  cmovb   ebx, ecx
0x18004e196  mov     eax, ebx
0x18004e198  or      eax, 80070000h
0x18004e19d  test    ebx, ebx
0x18004e19f  cmovnz  ebx, eax
0x18004e1a2  test    ebx, ebx
0x18004e1a4  js      short loc_18004E203
0x18004e1a6  lea     r8d, [rcx+64h]; Size
0x18004e1aa  xor     edx, edx; Val
0x18004e1ac  lea     rcx, [rbp+50h+var_B0]; void *
0x18004e1b0  call    memset_0
0x18004e1b5  lea     rcx, [rdi+8]; struct _WWAN_REGISTRATION_STATE *
0x18004e1b9  lea     rdx, [rbp+50h+var_B0]; struct CellularSettingsRegistrationState *
0x18004e1bd  call    ?GetCSRegStateFromWwanRegState@CellularSettingUtils@@SAJAEBU_WWAN_REGISTRATION_STATE@@AEAUCellularSettingsRegistrationState@@@Z; CellularSettingUtils::GetCSRegStateFromWwanRegState(_WWAN_REGISTRATION_STATE const &,CellularSettingsRegistrationState &)
0x18004e1c2  lea     rdi, [rsi+30h]
0x18004e1c6  mov     rcx, rdi; lpCriticalSection
0x18004e1c9  call    cs:__imp_EnterCriticalSection
0x18004e1cf  mov     rcx, [rsi+18h]
0x18004e1d3  test    rcx, rcx
0x18004e1d6  jz      short loc_18004E1EC
0x18004e1d8  mov     rax, [rcx]
0x18004e1db  lea     r8, [rbp+50h+var_B0]
0x18004e1df  lea     rdx, [rsi+8]
0x18004e1e3  mov     rax, [rax+48h]
0x18004e1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1ec  test    rdi, rdi
0x18004e1ef  jz      loc_18004E2CA
0x18004e1f5  mov     rcx, rdi; lpCriticalSection
0x18004e1f8  call    cs:__imp_LeaveCriticalSection
0x18004e1fe  jmp     loc_18004E2CA
0x18004e203  xorps   xmm0, xmm0
0x18004e206  mov     [rsp+150h+var_100], r15
0x18004e20b  xorps   xmm1, xmm1
0x18004e20e  mov     [rsp+150h+var_E8], r15
0x18004e213  lea     rcx, [rsp+150h+var_110]
0x18004e218  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x18004e21e  movdqu  xmmword ptr [rsp+150h+var_F8], xmm1
0x18004e224  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e229  lea     rcx, [rsp+150h+var_F8]
0x18004e22e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e233  mov     rdx, [rsp+150h+var_110+8]
0x18004e238  lea     r8, aErrorGettingCo; "Error getting connection information. R"...
0x18004e23f  mov     rcx, [rsp+150h+var_110]; unsigned __int16 *
0x18004e244  mov     r9d, ebx
0x18004e247  sub     rdx, rcx
0x18004e24a  sar     rdx, 1; unsigned __int64
0x18004e24d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e252  mov     rdx, [rsp+150h+var_F8+8]
0x18004e257  lea     r9, aCcellularsetti_18; "CCellularSettingHelperWwan::GetConnecti"...
0x18004e25e  mov     rcx, [rsp+150h+var_F8]; unsigned __int16 *
0x18004e263  lea     r8, aSDS; "%S(%d):%s"
0x18004e26a  mov     rax, [rsp+150h+var_110]
0x18004e26f  sub     rdx, rcx
0x18004e272  mov     [rsp+150h+var_128], rax
0x18004e277  sar     rdx, 1; unsigned __int64
0x18004e27a  mov     [rsp+150h+var_130], 222h
0x18004e282  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e287  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004e28c  mov     ecx, [rax]
0x18004e28e  cmp     ecx, 2
0x18004e291  jbe     short loc_18004E2B6
0x18004e293  mov     rcx, [rsp+150h+var_F8]
0x18004e298  lea     rdx, word_1800793DA
0x18004e29f  mov     qword ptr [rsp+150h+var_D8], rcx
0x18004e2a4  lea     rcx, [rsp+150h+var_D8]
0x18004e2a9  mov     qword ptr [rsp+150h+var_130], rcx
0x18004e2ae  mov     rcx, rax
0x18004e2b1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004e2b6  lea     rcx, [rsp+150h+var_F8]
0x18004e2bb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e2c0  lea     rcx, [rsp+150h+var_110]
0x18004e2c5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e2ca  xorps   xmm0, xmm0
0x18004e2cd  mov     [rsp+150h+var_100], r15
0x18004e2d2  xorps   xmm1, xmm1
0x18004e2d5  mov     [rsp+150h+var_E8], r15
0x18004e2da  lea     rcx, [rsp+150h+var_110]
0x18004e2df  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x18004e2e5  movdqu  xmmword ptr [rsp+150h+var_F8], xmm1
0x18004e2eb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e2f0  lea     rcx, [rsp+150h+var_F8]
0x18004e2f5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e2fa  mov     rdx, [rsp+150h+var_110+8]
0x18004e2ff  lea     r8, aExit; "Exit"
0x18004e306  mov     rcx, [rsp+150h+var_110]; unsigned __int16 *
0x18004e30b  sub     rdx, rcx
0x18004e30e  sar     rdx, 1; unsigned __int64
0x18004e311  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e316  mov     rdx, [rsp+150h+var_F8+8]
0x18004e31b  lea     r9, aCcellularsetti_18; "CCellularSettingHelperWwan::GetConnecti"...
0x18004e322  mov     rcx, [rsp+150h+var_F8]; unsigned __int16 *
0x18004e327  lea     r8, aSDS; "%S(%d):%s"
0x18004e32e  mov     rax, [rsp+150h+var_110]
0x18004e333  sub     rdx, rcx
0x18004e336  mov     [rsp+150h+var_128], rax
0x18004e33b  sar     rdx, 1; unsigned __int64
0x18004e33e  mov     [rsp+150h+var_130], 225h
0x18004e346  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e34b  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004e350  mov     ecx, [rax]
0x18004e352  cmp     ecx, 5
0x18004e355  jbe     short loc_18004E37A
0x18004e357  mov     rcx, [rsp+150h+var_F8]
0x18004e35c  lea     rdx, byte_1800793B7
0x18004e363  mov     qword ptr [rsp+150h+var_D8], rcx
0x18004e368  lea     rcx, [rsp+150h+var_D8]
0x18004e36d  mov     qword ptr [rsp+150h+var_130], rcx
0x18004e372  mov     rcx, rax
0x18004e375  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004e37a  lea     rcx, [rsp+150h+var_F8]
0x18004e37f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e384  lea     rcx, [rsp+150h+var_110]
0x18004e389  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e38e  mov     rcx, [rbp+50h+var_C8]
0x18004e392  call    cs:__imp_WwanFreeMemory
0x18004e398  mov     rcx, [rbp+50h+var_C0]
0x18004e39c  xor     edx, edx
0x18004e39e  call    cs:__imp_WwanCloseHandle
0x18004e3a4  mov     eax, ebx
0x18004e3a6  mov     rcx, [rbp+50h+var_40]
0x18004e3aa  xor     rcx, rsp; StackCookie
0x18004e3ad  call    __security_check_cookie
0x18004e3b2  add     rsp, 128h
0x18004e3b9  pop     r15
0x18004e3bb  pop     r14
0x18004e3bd  pop     rdi
0x18004e3be  pop     rsi
0x18004e3bf  pop     rbx
0x18004e3c0  pop     rbp
0x18004e3c1  retn
```
