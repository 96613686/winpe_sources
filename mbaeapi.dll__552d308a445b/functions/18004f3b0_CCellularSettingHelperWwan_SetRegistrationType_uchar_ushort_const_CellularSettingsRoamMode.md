# CCellularSettingHelperWwan::SetRegistrationType(uchar,ushort const *,CellularSettingsRoamMode)

- ea: `0x18004f3b0`
- end: `0x18004f8ce`
- name: `?SetRegistrationType@CCellularSettingHelperWwan@@UEAAJEPEBGW4CellularSettingsRoamMode@@@Z`
- size: `1310`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18004cdac`
- `0x18004f3b0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f78d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f78d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f53d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f603`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f690`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f89a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f53d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f603`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f690`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f89a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f5c6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f5f7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f684`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f88e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f5c6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f5f7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f684`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f88e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004f4c8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004f4c8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004f5a5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004f5a5`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanRegister` at `0x18004f653`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanRegister` at `0x18004f653`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCellularSettingHelperWwan::SetRegistrationType(
        __int64 a1,
        unsigned __int8 a2,
        __int64 a3,
        unsigned int a4)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // ebx
  unsigned int Interface; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r8
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  unsigned int v26; // [rsp+28h] [rbp-79h]
  unsigned int v27; // [rsp+28h] [rbp-79h]
  unsigned int v28[2]; // [rsp+28h] [rbp-79h]
  unsigned int v29[2]; // [rsp+28h] [rbp-79h]
  int *v30; // [rsp+30h] [rbp-71h]
  __int64 v31; // [rsp+48h] [rbp-59h] BYREF
  unsigned __int16 *v32[2]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v33; // [rsp+60h] [rbp-41h]
  __int64 v34; // [rsp+68h] [rbp-39h] BYREF
  unsigned __int16 *v35[2]; // [rsp+70h] [rbp-31h] BYREF
  __int64 v36; // [rsp+80h] [rbp-21h]
  int v37; // [rsp+88h] [rbp-19h] BYREF
  unsigned int v38[2]; // [rsp+90h] [rbp-11h] BYREF
  int v39; // [rsp+98h] [rbp-9h] BYREF
  unsigned int v40; // [rsp+9Ch] [rbp-5h] BYREF
  int v41; // [rsp+A0h] [rbp-1h] BYREF
  _QWORD v42[4]; // [rsp+A8h] [rbp+7h] BYREF
  char v43; // [rsp+C8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]
  unsigned __int8 v45; // [rsp+110h] [rbp+6Fh] BYREF
  __int64 v46; // [rsp+118h] [rbp+77h] BYREF
  unsigned int v47; // [rsp+120h] [rbp+7Fh] BYREF

  v47 = a4;
  v46 = a3;
  v45 = a2;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  std::vector<unsigned short>::resize(v32);
  std::vector<unsigned short>::resize(v35);
  StringCchPrintfW(v32[0], v32[1] - v32[0], L"Enter");
  v26 = 393;
  StringCchPrintfW(v35[0], v35[1] - v35[0], L"%S(%d):%s", "CCellularSettingHelperWwan::SetRegistrationType");
  v5 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    *(unsigned __int16 **)v38 = v35[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)byte_18007955B,
      v6,
      v7,
      (const unsigned __int16 **)v38);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  v37 = 0;
  v42[0] = &v37;
  v42[1] = &v45;
  v42[2] = &v47;
  v42[3] = &v46;
  v43 = 1;
  v34 = 0;
  v39 = 0;
  v8 = WwanOpenHandle(1, 0, &v39, &v34);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x199,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
           (const char *)v8,
           v26);
    if ( v43 )
    {
      v43 = 0;
      CCellularSettingHelperWwan::SetRegistrationType_::_2_::_lambda_1_::operator()(v42);
    }
    return v9;
  }
  if ( v45 )
  {
    v11 = 1;
  }
  else
  {
    if ( !v46 )
    {
      v9 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
        (const char *)0x80070057LL,
        v26);
      WwanCloseHandle(v34, 0);
      if ( v43 )
      {
        v43 = 0;
        CCellularSettingHelperWwan::SetRegistrationType_::_2_::_lambda_1_::operator()(v42);
      }
      return v9;
    }
    v11 = 2;
  }
  v31 = 0;
  v40 = 0;
  v32[0] = (unsigned __int16 *)&v31;
  v32[1] = 0;
  LOBYTE(v33) = 1;
  Interface = WwanQueryInterface(v34, a1 + 8, 62);
  if ( (_BYTE)v33 )
  {
    v13 = *(_QWORD *)v32[0];
    *(_QWORD *)v32[0] = v32[1];
    if ( v13 )
      WwanFreeMemory(v13);
  }
  if ( Interface )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1AA,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
           (const char *)Interface,
           (unsigned int)&v40);
    v14 = v31;
    v31 = 0;
    if ( v14 )
      WwanFreeMemory(v14);
    WwanCloseHandle(v34, 0);
    if ( v43 )
    {
      v43 = 0;
      CCellularSettingHelperWwan::SetRegistrationType_::_2_::_lambda_1_::operator()(v42);
    }
    return v9;
  }
  v41 = 0;
  v30 = &v41;
  v27 = *(_DWORD *)(v31 + 16);
  v15 = WwanRegister(v34, a1 + 8, v11, v46);
  if ( v15 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1AE,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
           (const char *)v15,
           v27);
    v16 = v31;
    v31 = 0;
    if ( v16 )
      WwanFreeMemory(v16);
    WwanCloseHandle(v34, 0);
    if ( v43 )
    {
      v43 = 0;
      CCellularSettingHelperWwan::SetRegistrationType_::_2_::_lambda_1_::operator()(v42);
    }
    return v9;
  }
  *(_OWORD *)v35 = 0;
  v36 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  std::vector<unsigned short>::resize(v35);
  std::vector<unsigned short>::resize(v32);
  LODWORD(v30) = *(_DWORD *)(v31 + 16);
  StringCchPrintfW(
    v35[0],
    v35[1] - v35[0],
    L"WwanRegister succeeded, with automaticRegistration: %d, operator Id: %ls and supported data classes: 0x%x",
    v45,
    v46,
    v30);
  v28[0] = 436;
  StringCchPrintfW(
    v32[0],
    v32[1] - v32[0],
    L"%S(%d):%s",
    "CCellularSettingHelperWwan::SetRegistrationType",
    *(_QWORD *)v28,
    v35[0]);
  v17 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v17 > 4u )
  {
    *(unsigned __int16 **)v38 = v32[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v17,
      (__int64)&word_18007957E,
      v18,
      v19,
      (const unsigned __int16 **)v38);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
  v37 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v20 = *(_QWORD *)(a1 + 24);
  if ( v20 )
  {
    v21 = v47;
    LOBYTE(v21) = v45;
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64, unsigned int))(*(_QWORD *)v20 + 224LL))(
      v20,
      a1 + 8,
      v21,
      v46,
      v47);
  }
  if ( a1 != -48 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  *(_OWORD *)v35 = 0;
  v36 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  std::vector<unsigned short>::resize(v35);
  std::vector<unsigned short>::resize(v32);
  StringCchPrintfW(v35[0], v35[1] - v35[0], L"Exit");
  v29[0] = 448;
  StringCchPrintfW(
    v32[0],
    v32[1] - v32[0],
    L"%S(%d):%s",
    "CCellularSettingHelperWwan::SetRegistrationType",
    *(_QWORD *)v29,
    v35[0]);
  v22 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v22 > 5u )
  {
    *(unsigned __int16 **)v38 = v32[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v22,
      (__int64)qword_180079538,
      v23,
      v24,
      (const unsigned __int16 **)v38);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
  v25 = v31;
  v31 = 0;
  if ( v25 )
    WwanFreeMemory(v25);
  WwanCloseHandle(v34, 0);
  if ( v43 )
  {
    v43 = 0;
    CCellularSettingHelperWwan::SetRegistrationType_::_2_::_lambda_1_::operator()(v42);
  }
  return 0;
}

```

## disassembly

```asm
0x18004f3b0  mov     rax, rsp
0x18004f3b3  mov     [rax+8], rbx
0x18004f3b7  mov     [rax+20h], r9d
0x18004f3bb  mov     [rax+18h], r8
0x18004f3bf  mov     [rax+10h], dl
0x18004f3c2  push    rbp
0x18004f3c3  push    rsi
0x18004f3c4  push    rdi
0x18004f3c5  push    r14
0x18004f3c7  push    r15
0x18004f3c9  lea     rbp, [rax-5Fh]
0x18004f3cd  sub     rsp, 0D0h
0x18004f3d4  mov     r14, rcx
0x18004f3d7  xorps   xmm0, xmm0
0x18004f3da  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x18004f3df  xor     r15d, r15d
0x18004f3e2  mov     [rbp+57h+var_98], r15
0x18004f3e6  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004f3eb  mov     [rbp+57h+var_78], r15
0x18004f3ef  lea     rcx, [rbp+57h+var_A8]
0x18004f3f3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f3f8  lea     rcx, [rbp+57h+var_88]
0x18004f3fc  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f401  mov     rdx, [rbp+57h+var_A8+8]
0x18004f405  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x18004f409  sub     rdx, rcx
0x18004f40c  sar     rdx, 1; unsigned __int64
0x18004f40f  lea     r8, aEnter; "Enter"
0x18004f416  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f41b  mov     rdx, [rbp+57h+var_88+8]
0x18004f41f  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x18004f423  sub     rdx, rcx
0x18004f426  sar     rdx, 1; unsigned __int64
0x18004f429  mov     rax, [rbp+57h+var_A8]
0x18004f42d  mov     [rsp+0F0h+var_C8], rax
0x18004f432  mov     [rsp+0F0h+var_D0], 189h
0x18004f43a  lea     r9, aCcellularsetti_26; "CCellularSettingHelperWwan::SetRegistra"...
0x18004f441  lea     r8, aSDS; "%S(%d):%s"
0x18004f448  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f44d  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004f452  mov     ecx, [rax]
0x18004f454  cmp     ecx, 5
0x18004f457  jbe     short loc_18004F479
0x18004f459  mov     rcx, [rbp+57h+var_88]
0x18004f45d  mov     qword ptr [rbp+57h+var_68], rcx
0x18004f461  lea     rcx, [rbp+57h+var_68]
0x18004f465  mov     qword ptr [rsp+0F0h+var_D0], rcx; int
0x18004f46a  lea     rdx, byte_18007955B
0x18004f471  mov     rcx, rax
0x18004f474  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004f479  lea     rcx, [rbp+57h+var_88]
0x18004f47d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f482  lea     rcx, [rbp+57h+var_A8]
0x18004f486  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f48b  mov     [rbp+57h+var_70], r15d
0x18004f48f  lea     rax, [rbp+57h+var_70]
0x18004f493  mov     [rbp+57h+var_50], rax
0x18004f497  lea     rax, [rbp+57h+arg_8]
0x18004f49b  mov     [rbp+57h+var_48], rax
0x18004f49f  lea     rax, [rbp+57h+arg_18]
0x18004f4a3  mov     [rbp+57h+var_40], rax
0x18004f4a7  lea     rax, [rbp+57h+arg_10]
0x18004f4ab  mov     [rbp+57h+var_38], rax
0x18004f4af  mov     [rbp+57h+var_30], 1
0x18004f4b3  mov     [rbp+57h+var_90], r15
0x18004f4b7  mov     [rbp+57h+var_60], r15d
0x18004f4bb  lea     r9, [rbp+57h+var_90]
0x18004f4bf  lea     r8, [rbp+57h+var_60]
0x18004f4c3  xor     edx, edx
0x18004f4c5  lea     ecx, [rdx+1]
0x18004f4c8  call    cs:__imp_WwanOpenHandle
0x18004f4ce  test    eax, eax
0x18004f4d0  jz      short loc_18004F507
0x18004f4d2  mov     rcx, [rbp+5Fh]; this
0x18004f4d6  mov     r9d, eax; char *
0x18004f4d9  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f4e0  mov     edx, 199h; void *
0x18004f4e5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f4ea  mov     ebx, eax
0x18004f4ec  cmp     [rbp+57h+var_30], r15b
0x18004f4f0  jz      short loc_18004F500
0x18004f4f2  mov     [rbp+57h+var_30], r15b
0x18004f4f6  lea     rcx, [rbp+57h+var_50]
0x18004f4fa  call    _CCellularSettingHelperWwan__SetRegistrationType____2____lambda_1___operator__
0x18004f4ff  nop
0x18004f500  mov     eax, ebx
0x18004f502  jmp     loc_18004F8B7
0x18004f507  cmp     [rbp+57h+arg_8], r15b
0x18004f50b  jz      short loc_18004F514
0x18004f50d  mov     ebx, 1
0x18004f512  jmp     short loc_18004F55F
0x18004f514  cmp     [rbp+57h+arg_10], r15
0x18004f518  jnz     short loc_18004F55A
0x18004f51a  mov     rcx, [rbp+5Fh]; this
0x18004f51e  mov     ebx, 80070057h
0x18004f523  mov     r9d, ebx; char *
0x18004f526  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f52d  mov     edx, 1A3h; void *
0x18004f532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f537  xor     edx, edx
0x18004f539  mov     rcx, [rbp+57h+var_90]
0x18004f53d  call    cs:__imp_WwanCloseHandle
0x18004f543  nop
0x18004f544  cmp     [rbp+57h+var_30], r15b
0x18004f548  jz      short loc_18004F558
0x18004f54a  mov     [rbp+57h+var_30], r15b
0x18004f54e  lea     rcx, [rbp+57h+var_50]
0x18004f552  call    _CCellularSettingHelperWwan__SetRegistrationType____2____lambda_1___operator__
0x18004f557  nop
0x18004f558  jmp     short loc_18004F500
0x18004f55a  mov     ebx, 2
0x18004f55f  mov     [rbp+57h+var_B0], r15
0x18004f563  mov     [rbp+57h+var_5C], r15d
0x18004f567  lea     rax, [rbp+57h+var_B0]
0x18004f56b  mov     [rbp+57h+var_A8], rax
0x18004f56f  mov     [rbp+57h+var_A8+8], r15
0x18004f573  mov     byte ptr [rbp+57h+var_98], 1
0x18004f577  lea     rsi, [r14+8]
0x18004f57b  mov     [rsp+38h], r15
0x18004f580  mov     [rsp+0F0h+var_C0], r15
0x18004f585  lea     rax, [rbp+57h+var_A8+8]
0x18004f589  mov     [rsp+0F0h+var_C8], rax
0x18004f58e  lea     rax, [rbp+57h+var_5C]
0x18004f592  mov     qword ptr [rsp+0F0h+var_D0], rax; unsigned int
0x18004f597  xor     r9d, r9d
0x18004f59a  lea     r8d, [r9+3Eh]
0x18004f59e  mov     rdx, rsi
0x18004f5a1  mov     rcx, [rbp+57h+var_90]
0x18004f5a5  call    cs:__imp_WwanQueryInterface
0x18004f5ab  mov     edi, eax
0x18004f5ad  cmp     byte ptr [rbp+57h+var_98], r15b
0x18004f5b1  jz      short loc_18004F5CC
0x18004f5b3  mov     r8, [rbp+57h+var_A8]
0x18004f5b7  mov     rcx, [r8]
0x18004f5ba  mov     rdx, [rbp+57h+var_A8+8]
0x18004f5be  mov     [r8], rdx
0x18004f5c1  test    rcx, rcx
0x18004f5c4  jz      short loc_18004F5CC
0x18004f5c6  call    cs:__imp_WwanFreeMemory
0x18004f5cc  test    edi, edi
0x18004f5ce  jz      short loc_18004F623
0x18004f5d0  mov     rcx, [rbp+5Fh]; this
0x18004f5d4  mov     r9d, edi; char *
0x18004f5d7  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f5de  mov     edx, 1AAh; void *
0x18004f5e3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f5e8  mov     ebx, eax
0x18004f5ea  mov     rcx, [rbp+57h+var_B0]
0x18004f5ee  mov     [rbp+57h+var_B0], r15
0x18004f5f2  test    rcx, rcx
0x18004f5f5  jz      short loc_18004F5FD
0x18004f5f7  call    cs:__imp_WwanFreeMemory
0x18004f5fd  xor     edx, edx
0x18004f5ff  mov     rcx, [rbp+57h+var_90]
0x18004f603  call    cs:__imp_WwanCloseHandle
0x18004f609  nop
0x18004f60a  cmp     [rbp+57h+var_30], r15b
0x18004f60e  jz      short loc_18004F61E
0x18004f610  mov     [rbp+57h+var_30], r15b
0x18004f614  lea     rcx, [rbp+57h+var_50]
0x18004f618  call    _CCellularSettingHelperWwan__SetRegistrationType____2____lambda_1___operator__
0x18004f61d  nop
0x18004f61e  jmp     loc_18004F500
0x18004f623  mov     [rbp+57h+var_58], r15d
0x18004f627  mov     [rsp+38h], r15
0x18004f62c  mov     [rsp+0F0h+var_C0], r15
0x18004f631  lea     rax, [rbp+57h+var_58]
0x18004f635  mov     [rsp+0F0h+var_C8], rax
0x18004f63a  mov     rax, [rbp+57h+var_B0]
0x18004f63e  mov     edx, [rax+10h]
0x18004f641  mov     [rsp+0F0h+var_D0], edx; unsigned int
0x18004f645  mov     r9, [rbp+57h+arg_10]
0x18004f649  mov     r8d, ebx
0x18004f64c  mov     rdx, rsi
0x18004f64f  mov     rcx, [rbp+57h+var_90]
0x18004f653  call    cs:__imp_WwanRegister
0x18004f659  test    eax, eax
0x18004f65b  jz      short loc_18004F6B0
0x18004f65d  mov     rcx, [rbp+5Fh]; this
0x18004f661  mov     r9d, eax; char *
0x18004f664  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f66b  mov     edx, 1AEh; void *
0x18004f670  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f675  mov     ebx, eax
0x18004f677  mov     rcx, [rbp+57h+var_B0]
0x18004f67b  mov     [rbp+57h+var_B0], r15
0x18004f67f  test    rcx, rcx
0x18004f682  jz      short loc_18004F68A
0x18004f684  call    cs:__imp_WwanFreeMemory
0x18004f68a  xor     edx, edx
0x18004f68c  mov     rcx, [rbp+57h+var_90]
0x18004f690  call    cs:__imp_WwanCloseHandle
0x18004f696  nop
0x18004f697  cmp     [rbp+57h+var_30], r15b
0x18004f69b  jz      short loc_18004F6AB
0x18004f69d  mov     [rbp+57h+var_30], r15b
0x18004f6a1  lea     rcx, [rbp+57h+var_50]
0x18004f6a5  call    _CCellularSettingHelperWwan__SetRegistrationType____2____lambda_1___operator__
0x18004f6aa  nop
0x18004f6ab  jmp     loc_18004F500
0x18004f6b0  xorps   xmm0, xmm0
0x18004f6b3  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004f6b8  mov     [rbp+57h+var_78], r15
0x18004f6bc  xorps   xmm1, xmm1
0x18004f6bf  movdqu  xmmword ptr [rbp+57h+var_A8], xmm1
0x18004f6c4  mov     [rbp+57h+var_98], r15
0x18004f6c8  lea     rcx, [rbp+57h+var_88]
0x18004f6cc  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f6d1  lea     rcx, [rbp+57h+var_A8]
0x18004f6d5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f6da  movzx   r9d, [rbp+57h+arg_8]
0x18004f6df  mov     rdx, [rbp+57h+var_88+8]
0x18004f6e3  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x18004f6e7  sub     rdx, rcx
0x18004f6ea  sar     rdx, 1; unsigned __int64
0x18004f6ed  mov     rax, [rbp+57h+var_B0]
0x18004f6f1  mov     r8d, [rax+10h]
0x18004f6f5  mov     dword ptr [rsp+0F0h+var_C8], r8d
0x18004f6fa  mov     rax, [rbp+57h+arg_10]
0x18004f6fe  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18004f703  lea     r8, aWwanregisterSu; "WwanRegister succeeded, with automaticR"...
0x18004f70a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f70f  mov     rdx, [rbp+57h+var_A8+8]
0x18004f713  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x18004f717  sub     rdx, rcx
0x18004f71a  sar     rdx, 1; unsigned __int64
0x18004f71d  mov     rax, [rbp+57h+var_88]
0x18004f721  mov     [rsp+0F0h+var_C8], rax
0x18004f726  mov     [rsp+0F0h+var_D0], 1B4h
0x18004f72e  lea     r9, aCcellularsetti_26; "CCellularSettingHelperWwan::SetRegistra"...
0x18004f735  lea     r8, aSDS; "%S(%d):%s"
0x18004f73c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f741  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004f746  mov     ecx, [rax]
0x18004f748  cmp     ecx, 4
0x18004f74b  jbe     short loc_18004F76D
0x18004f74d  mov     rcx, [rbp+57h+var_A8]
0x18004f751  mov     qword ptr [rbp+57h+var_68], rcx
0x18004f755  lea     rcx, [rbp+57h+var_68]
0x18004f759  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x18004f75e  lea     rdx, word_18007957E
0x18004f765  mov     rcx, rax
0x18004f768  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004f76d  lea     rcx, [rbp+57h+var_A8]
0x18004f771  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f776  lea     rcx, [rbp+57h+var_88]
0x18004f77a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f77f  mov     [rbp+57h+var_70], 1
0x18004f786  lea     rbx, [r14+30h]
0x18004f78a  mov     rcx, rbx; lpCriticalSection
0x18004f78d  call    cs:__imp_EnterCriticalSection
0x18004f793  mov     rcx, [r14+18h]
0x18004f797  test    rcx, rcx
0x18004f79a  jz      short loc_18004F7BF
0x18004f79c  mov     rax, [rcx]
0x18004f79f  mov     r8d, [rbp+57h+arg_18]
0x18004f7a3  mov     [rsp+0F0h+var_D0], r8d
0x18004f7a8  mov     r9, [rbp+57h+arg_10]
0x18004f7ac  mov     r8b, [rbp+57h+arg_8]
0x18004f7b0  mov     rdx, rsi
0x18004f7b3  mov     rax, [rax+0E0h]
0x18004f7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7bf  test    rbx, rbx
0x18004f7c2  jz      short loc_18004F7CD
0x18004f7c4  mov     rcx, rbx; lpCriticalSection
0x18004f7c7  call    cs:__imp_LeaveCriticalSection
0x18004f7cd  xorps   xmm0, xmm0
0x18004f7d0  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004f7d5  mov     [rbp+57h+var_78], r15
0x18004f7d9  xorps   xmm1, xmm1
0x18004f7dc  movdqu  xmmword ptr [rbp+57h+var_A8], xmm1
0x18004f7e1  mov     [rbp+57h+var_98], r15
0x18004f7e5  lea     rcx, [rbp+57h+var_88]
0x18004f7e9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f7ee  lea     rcx, [rbp+57h+var_A8]
0x18004f7f2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f7f7  mov     rdx, [rbp+57h+var_88+8]
0x18004f7fb  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x18004f7ff  sub     rdx, rcx
0x18004f802  sar     rdx, 1; unsigned __int64
0x18004f805  lea     r8, aExit; "Exit"
0x18004f80c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f811  mov     rdx, [rbp+57h+var_A8+8]
0x18004f815  mov     rcx, [rbp+57h+var_A8]; unsigned __int16 *
0x18004f819  sub     rdx, rcx
0x18004f81c  sar     rdx, 1; unsigned __int64
0x18004f81f  mov     rax, [rbp+57h+var_88]
0x18004f823  mov     [rsp+0F0h+var_C8], rax
0x18004f828  mov     [rsp+0F0h+var_D0], 1C0h
0x18004f830  lea     r9, aCcellularsetti_26; "CCellularSettingHelperWwan::SetRegistra"...
0x18004f837  lea     r8, aSDS; "%S(%d):%s"
0x18004f83e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f843  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004f848  mov     ecx, [rax]
0x18004f84a  cmp     ecx, 5
0x18004f84d  jbe     short loc_18004F86F
0x18004f84f  mov     rcx, [rbp+57h+var_A8]
0x18004f853  mov     qword ptr [rbp+57h+var_68], rcx
0x18004f857  lea     rcx, [rbp+57h+var_68]
0x18004f85b  mov     qword ptr [rsp+0F0h+var_D0], rcx
  ... truncated ...
```
