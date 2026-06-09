# CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation(void)

- ea: `0x18004b05c`
- end: `0x18004b3ef`
- name: `?_GetAdminProvisionedDataProfileInformation@CCellularSettingHelperCommon@@IEAAJXZ`
- size: `915`
- prototype: `int __fastcall(CCellularSettingHelperCommon *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180047de0`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180036a68`
- `0x180036c78`
- `0x18004b05c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004b3d4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004b3d4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b24a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b25e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b3c6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b24a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b25e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004b3c6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004b14a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004b14a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b1d5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b296`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b1d5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004b296`

## string_xrefs

- `0x18004b15b`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b229`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b2a5`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x18004b0db`: `CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation`
- `0x18004b369`: `CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation(
        CCellularSettingHelperCommon *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // eax
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rcx
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // [rsp+20h] [rbp-59h]
  unsigned int *v22; // [rsp+20h] [rbp-59h]
  __int64 v23; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v24[4]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v25; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v26[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v27; // [rsp+70h] [rbp-9h]
  unsigned __int16 *v28[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v29; // [rsp+88h] [rbp+Fh]
  unsigned __int16 *v30[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v31; // [rsp+A0h] [rbp+27h]
  unsigned __int16 *v32[2]; // [rsp+A8h] [rbp+2Fh] BYREF
  __int64 v33; // [rsp+B8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v35; // [rsp+E8h] [rbp+6Fh] BYREF
  int v36; // [rsp+F0h] [rbp+77h] BYREF
  int v37; // [rsp+F8h] [rbp+7Fh] BYREF

  *(_OWORD *)v26 = 0;
  v27 = 0;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  std::vector<unsigned short>::resize(v26);
  std::vector<unsigned short>::resize(v28);
  StringCchPrintfW(v26[0], v26[1] - v26[0], L"Enter");
  v21 = 959;
  StringCchPrintfW(
    v28[0],
    v28[1] - v28[0],
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v24 = v28[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&word_180078A4E,
      v3,
      v4,
      (const unsigned __int16 **)v24);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v28);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  v25 = 0;
  v37 = 0;
  v5 = WwanOpenHandle(1, 0, &v37, &v25);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3C2,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v5,
             v21);
  v26[0] = (unsigned __int16 *)&v25;
  LOBYTE(v26[1]) = 1;
  v23 = 0;
  v35 = 0;
  v36 = 0;
  v28[0] = (unsigned __int16 *)&v23;
  LOBYTE(v28[1]) = 1;
  Interface = WwanQueryInterface(v25, (char *)this + 8, 33);
  if ( !Interface )
  {
    v9 = v35;
    v10 = v23;
    *(_OWORD *)v24 = 0;
    v11 = *((_QWORD *)this + 5);
    if ( v11 )
    {
      *(_QWORD *)v24 = *((_QWORD *)this + 4);
      *(_QWORD *)&v24[2] = v11;
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    }
    v12 = CWwanTranslator::ProcessHighestConnCategoryChange(v24, (char *)this + 8, v10, v9);
    v13 = v12;
    if ( v12 >= 0 )
    {
      if ( v23 )
        WwanFreeMemory(v23);
      v22 = &v35;
      Interface = WwanQueryInterface(v25, (char *)this + 8, 34);
      if ( Interface )
      {
        v8 = 984;
        goto LABEL_18;
      }
      v15 = v35;
      v16 = v23;
      *(_OWORD *)v24 = 0;
      v17 = *((_QWORD *)this + 5);
      if ( v17 )
      {
        *(_QWORD *)v24 = *((_QWORD *)this + 4);
        *(_QWORD *)&v24[2] = v17;
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 12));
      }
      v12 = CWwanTranslator::ProcessEnterpriseAPNParams(v24, (char *)this + 8, v16, v15);
      v13 = v12;
      if ( v12 >= 0 )
      {
        *(_OWORD *)v32 = 0;
        v33 = 0;
        *(_OWORD *)v30 = 0;
        v31 = 0;
        std::vector<unsigned short>::resize(v32);
        std::vector<unsigned short>::resize(v30);
        StringCchPrintfW(v32[0], v32[1] - v32[0], L"Exit");
        LODWORD(v22) = 987;
        StringCchPrintfW(
          v30[0],
          v30[1] - v30[0],
          L"%S(%d):%s",
          "CCellularSettingHelperCommon::_GetAdminProvisionedDataProfileInformation",
          v22,
          v32[0],
          &v36,
          0);
        v18 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v18 > 5u )
        {
          *(unsigned __int16 **)v24 = v30[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v18,
            (__int64)qword_180078A08,
            v19,
            v20,
            (const unsigned __int16 **)v24);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
        if ( v23 )
          WwanFreeMemory(v23);
        v13 = 0;
        goto LABEL_28;
      }
      v14 = 985;
    }
    else
    {
      v14 = 976;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)(unsigned int)v12,
      (int)&v35);
    goto LABEL_12;
  }
  v8 = 975;
LABEL_18:
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v8,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
          (const char *)Interface,
          (unsigned int)&v35);
LABEL_12:
  if ( v23 )
    WwanFreeMemory(v23);
LABEL_28:
  WwanCloseHandle(v25, 0);
  return v13;
}

```

## disassembly

```asm
0x18004b05c  mov     [rsp-8+arg_0], rbx
0x18004b061  push    rbp
0x18004b062  push    rsi
0x18004b063  push    rdi
0x18004b064  lea     rbp, [rsp-47h]
0x18004b069  sub     rsp, 0C0h
0x18004b070  mov     rdi, rcx
0x18004b073  xorps   xmm0, xmm0
0x18004b076  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18004b07b  mov     [rbp+57h+var_60], 0
0x18004b083  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18004b088  mov     [rbp+57h+var_48], 0
0x18004b090  lea     rcx, [rbp+57h+var_70]
0x18004b094  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b099  lea     rcx, [rbp+57h+var_58]
0x18004b09d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b0a2  mov     rdx, [rbp+57h+var_70+8]
0x18004b0a6  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18004b0aa  sub     rdx, rcx
0x18004b0ad  sar     rdx, 1; unsigned __int64
0x18004b0b0  lea     r8, aEnter; "Enter"
0x18004b0b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b0bc  mov     rdx, [rbp+57h+var_58+8]
0x18004b0c0  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x18004b0c4  sub     rdx, rcx
0x18004b0c7  sar     rdx, 1; unsigned __int64
0x18004b0ca  mov     rax, [rbp+57h+var_70]
0x18004b0ce  mov     [rsp+0D0h+var_A8], rax
0x18004b0d3  mov     [rsp+0D0h+var_B0], 3BFh
0x18004b0db  lea     r9, aCcellularsetti_5; "CCellularSettingHelperCommon::_GetAdmin"...
0x18004b0e2  lea     r8, aSDS; "%S(%d):%s"
0x18004b0e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b0ee  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004b0f3  mov     ecx, [rax]
0x18004b0f5  cmp     ecx, 5
0x18004b0f8  jbe     short loc_18004B11B
0x18004b0fa  mov     rcx, [rbp+57h+var_58]
0x18004b0fe  mov     qword ptr [rbp+57h+var_88], rcx
0x18004b102  lea     rcx, [rbp+57h+var_88]
0x18004b106  mov     qword ptr [rsp+0D0h+var_B0], rcx; unsigned int
0x18004b10b  lea     rdx, word_180078A4E
0x18004b112  mov     rcx, rax
0x18004b115  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b11a  nop
0x18004b11b  lea     rcx, [rbp+57h+var_58]
0x18004b11f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b124  nop
0x18004b125  lea     rcx, [rbp+57h+var_70]
0x18004b129  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b12e  mov     [rbp+57h+var_78], 0
0x18004b136  mov     [rbp+57h+arg_18], 0
0x18004b13d  lea     r9, [rbp+57h+var_78]
0x18004b141  lea     r8, [rbp+57h+arg_18]
0x18004b145  xor     edx, edx
0x18004b147  lea     ecx, [rdx+1]
0x18004b14a  call    cs:__imp_WwanOpenHandle
0x18004b150  test    eax, eax
0x18004b152  jz      short loc_18004B171
0x18004b154  mov     rcx, [rbp+5Fh]; this
0x18004b158  mov     r9d, eax; char *
0x18004b15b  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b162  mov     edx, 3C2h; void *
0x18004b167  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b16c  jmp     loc_18004B3DC
0x18004b171  lea     rax, [rbp+57h+var_78]
0x18004b175  mov     [rbp+57h+var_70], rax
0x18004b179  mov     byte ptr [rbp+57h+var_70+8], 1
0x18004b17d  mov     [rbp+57h+var_90], 0
0x18004b185  mov     [rbp+57h+arg_8], 0
0x18004b18c  mov     [rbp+57h+arg_10], 0
0x18004b193  lea     rax, [rbp+57h+var_90]
0x18004b197  mov     [rbp+57h+var_58], rax
0x18004b19b  mov     byte ptr [rbp+57h+var_58+8], 1
0x18004b19f  lea     rsi, [rdi+8]
0x18004b1a3  mov     [rsp+0D0h+var_98], 0
0x18004b1ac  lea     rax, [rbp+57h+arg_10]
0x18004b1b0  mov     [rsp+0D0h+var_A0], rax
0x18004b1b5  lea     rax, [rbp+57h+var_90]
0x18004b1b9  mov     [rsp+0D0h+var_A8], rax
0x18004b1be  lea     rax, [rbp+57h+arg_8]
0x18004b1c2  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18004b1c7  xor     r9d, r9d
0x18004b1ca  lea     r8d, [r9+21h]
0x18004b1ce  mov     rdx, rsi
0x18004b1d1  mov     rcx, [rbp+57h+var_78]
0x18004b1d5  call    cs:__imp_WwanQueryInterface
0x18004b1db  test    eax, eax
0x18004b1dd  jz      short loc_18004B1E9
0x18004b1df  mov     edx, 3CFh
0x18004b1e4  jmp     loc_18004B2A5
0x18004b1e9  mov     r9d, [rbp+57h+arg_8]
0x18004b1ed  mov     r8, [rbp+57h+var_90]
0x18004b1f1  xorps   xmm0, xmm0
0x18004b1f4  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004b1f9  mov     rcx, [rdi+28h]
0x18004b1fd  test    rcx, rcx
0x18004b200  jz      short loc_18004B212
0x18004b202  mov     rax, [rdi+20h]
0x18004b206  mov     qword ptr [rbp+57h+var_88], rax
0x18004b20a  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004b20e  lock inc dword ptr [rcx+0Ch]
0x18004b212  mov     rdx, rsi
0x18004b215  lea     rcx, [rbp+57h+var_88]
0x18004b219  call    ?ProcessHighestConnCategoryChange@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessHighestConnCategoryChange(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004b21e  mov     ebx, eax
0x18004b220  test    eax, eax
0x18004b222  jns     short loc_18004B255
0x18004b224  mov     edx, 3D0h; void *
0x18004b229  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b230  mov     r9d, eax; char *
0x18004b233  mov     rcx, [rbp+5Fh]; this
0x18004b237  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b23c  nop
0x18004b23d  mov     rcx, [rbp+57h+var_90]
0x18004b241  test    rcx, rcx
0x18004b244  jz      loc_18004B3CE
0x18004b24a  call    cs:__imp_WwanFreeMemory
0x18004b250  jmp     loc_18004B3CE
0x18004b255  mov     rcx, [rbp+57h+var_90]
0x18004b259  test    rcx, rcx
0x18004b25c  jz      short loc_18004B264
0x18004b25e  call    cs:__imp_WwanFreeMemory
0x18004b264  mov     [rsp+0D0h+var_98], 0
0x18004b26d  lea     rax, [rbp+57h+arg_10]
0x18004b271  mov     [rsp+0D0h+var_A0], rax
0x18004b276  lea     rax, [rbp+57h+var_90]
0x18004b27a  mov     [rsp+0D0h+var_A8], rax
0x18004b27f  lea     rax, [rbp+57h+arg_8]
0x18004b283  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x18004b288  xor     r9d, r9d
0x18004b28b  lea     r8d, [r9+22h]
0x18004b28f  mov     rdx, rsi
0x18004b292  mov     rcx, [rbp+57h+var_78]
0x18004b296  call    cs:__imp_WwanQueryInterface
0x18004b29c  test    eax, eax
0x18004b29e  jz      short loc_18004B2BC
0x18004b2a0  mov     edx, 3D8h; void *
0x18004b2a5  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004b2ac  mov     r9d, eax; char *
0x18004b2af  mov     rcx, [rbp+5Fh]; this
0x18004b2b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b2b8  mov     ebx, eax
0x18004b2ba  jmp     short loc_18004B23D
0x18004b2bc  mov     r9d, [rbp+57h+arg_8]
0x18004b2c0  mov     r8, [rbp+57h+var_90]
0x18004b2c4  xorps   xmm0, xmm0
0x18004b2c7  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18004b2cc  mov     rcx, [rdi+28h]
0x18004b2d0  test    rcx, rcx
0x18004b2d3  jz      short loc_18004B2E5
0x18004b2d5  mov     rax, [rdi+20h]
0x18004b2d9  mov     qword ptr [rbp+57h+var_88], rax
0x18004b2dd  mov     qword ptr [rbp+57h+var_88+8], rcx
0x18004b2e1  lock inc dword ptr [rcx+0Ch]
0x18004b2e5  mov     rdx, rsi
0x18004b2e8  lea     rcx, [rbp+57h+var_88]
0x18004b2ec  call    ?ProcessEnterpriseAPNParams@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessEnterpriseAPNParams(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004b2f1  mov     ebx, eax
0x18004b2f3  test    eax, eax
0x18004b2f5  jns     short loc_18004B301
0x18004b2f7  mov     edx, 3D9h
0x18004b2fc  jmp     loc_18004B229
0x18004b301  xorps   xmm0, xmm0
0x18004b304  movdqu  xmmword ptr [rbp+57h+var_28], xmm0
0x18004b309  mov     [rbp+57h+var_18], 0
0x18004b311  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18004b316  mov     [rbp+57h+var_30], 0
0x18004b31e  lea     rcx, [rbp+57h+var_28]
0x18004b322  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b327  lea     rcx, [rbp+57h+var_40]
0x18004b32b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004b330  mov     rdx, [rbp+57h+var_28+8]
0x18004b334  mov     rcx, [rbp+57h+var_28]; unsigned __int16 *
0x18004b338  sub     rdx, rcx
0x18004b33b  sar     rdx, 1; unsigned __int64
0x18004b33e  lea     r8, aExit; "Exit"
0x18004b345  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b34a  mov     rdx, [rbp+57h+var_40+8]
0x18004b34e  mov     rcx, [rbp+57h+var_40]; unsigned __int16 *
0x18004b352  sub     rdx, rcx
0x18004b355  sar     rdx, 1; unsigned __int64
0x18004b358  mov     rax, [rbp+57h+var_28]
0x18004b35c  mov     [rsp+0D0h+var_A8], rax
0x18004b361  mov     [rsp+0D0h+var_B0], 3DBh
0x18004b369  lea     r9, aCcellularsetti_5; "CCellularSettingHelperCommon::_GetAdmin"...
0x18004b370  lea     r8, aSDS; "%S(%d):%s"
0x18004b377  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b37c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004b381  mov     ecx, [rax]
0x18004b383  cmp     ecx, 5
0x18004b386  jbe     short loc_18004B3A9
0x18004b388  mov     rcx, [rbp+57h+var_40]
0x18004b38c  mov     qword ptr [rbp+57h+var_88], rcx
0x18004b390  lea     rcx, [rbp+57h+var_88]
0x18004b394  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18004b399  lea     rdx, qword_180078A08
0x18004b3a0  mov     rcx, rax
0x18004b3a3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004b3a8  nop
0x18004b3a9  lea     rcx, [rbp+57h+var_40]
0x18004b3ad  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b3b2  nop
0x18004b3b3  lea     rcx, [rbp+57h+var_28]
0x18004b3b7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004b3bc  nop
0x18004b3bd  mov     rcx, [rbp+57h+var_90]
0x18004b3c1  test    rcx, rcx
0x18004b3c4  jz      short loc_18004B3CC
0x18004b3c6  call    cs:__imp_WwanFreeMemory
0x18004b3cc  xor     ebx, ebx
0x18004b3ce  xor     edx, edx
0x18004b3d0  mov     rcx, [rbp+57h+var_78]
0x18004b3d4  call    cs:__imp_WwanCloseHandle
0x18004b3da  mov     eax, ebx
0x18004b3dc  mov     rbx, [rsp+0D0h+arg_0]
0x18004b3e4  add     rsp, 0C0h
0x18004b3eb  pop     rdi
0x18004b3ec  pop     rsi
0x18004b3ed  pop     rbp
0x18004b3ee  retn
```
