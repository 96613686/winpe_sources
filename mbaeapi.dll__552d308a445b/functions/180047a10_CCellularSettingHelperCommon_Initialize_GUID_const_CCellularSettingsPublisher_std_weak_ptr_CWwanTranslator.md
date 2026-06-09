# CCellularSettingHelperCommon::Initialize(_GUID const &,CCellularSettingsPublisher *,std::weak_ptr<CWwanTranslator>)

- ea: `0x180047a10`
- end: `0x180047dce`
- name: `?Initialize@CCellularSettingHelperCommon@@UEAAJAEBU_GUID@@PEAVCCellularSettingsPublisher@@V?$weak_ptr@VCWwanTranslator@@@std@@@Z`
- size: `958`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180047a10`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047c8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047c8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047c6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047c6e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180047b82`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180047c1c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180047d9e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180047b82`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180047c1c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180047d9e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180047c0f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180047d91`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180047c0f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180047d91`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180047b11`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180047b11`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180047b58`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180047b58`

## string_xrefs

- `0x180047b22`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180047b69`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180047bf9`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180047aa2`: `CCellularSettingHelperCommon::Initialize`
- `0x180047d39`: `CCellularSettingHelperCommon::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCellularSettingHelperCommon::Initialize(__int64 a1, _QWORD *a2, __int64 a3, __int64 *a4)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // eax
  volatile signed __int32 *v14; // rcx
  void (*v15)(void); // rax
  unsigned int v16; // ecx
  __int64 v17; // r8
  volatile signed __int32 *v18; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  volatile signed __int32 *v22; // rcx
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  volatile signed __int32 *v26; // rcx
  unsigned int v27[2]; // [rsp+28h] [rbp-39h]
  __int64 v28; // [rsp+38h] [rbp-29h] BYREF
  _DWORD *v29; // [rsp+40h] [rbp-21h] BYREF
  unsigned __int16 *v30[2]; // [rsp+48h] [rbp-19h] BYREF
  __int64 v31; // [rsp+58h] [rbp-9h]
  int v32; // [rsp+60h] [rbp-1h] BYREF
  unsigned int v33[2]; // [rsp+68h] [rbp+7h] BYREF
  char v34; // [rsp+70h] [rbp+Fh]
  unsigned __int16 *v35[2]; // [rsp+78h] [rbp+17h] BYREF
  __int64 v36; // [rsp+88h] [rbp+27h]
  unsigned __int16 *v37[2]; // [rsp+90h] [rbp+2Fh] BYREF
  __int64 v38; // [rsp+A0h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  *(_OWORD *)v30 = 0;
  v31 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  std::vector<unsigned short>::resize(v30);
  std::vector<unsigned short>::resize(v35);
  StringCchPrintfW(v30[0], v30[1] - v30[0], L"Enter");
  v27[0] = 39;
  StringCchPrintfW(v35[0], v35[1] - v35[0], L"%S(%d):%s", "CCellularSettingHelperCommon::Initialize");
  v8 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    *(unsigned __int16 **)v33 = v35[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)byte_180079371,
      v9,
      v10,
      (const unsigned __int16 **)v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  v28 = 0;
  v32 = 0;
  v11 = WwanOpenHandle(1, 0, &v32, &v28);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
            (const char *)v11,
            v27[0]);
    goto LABEL_14;
  }
  *(_QWORD *)v33 = &v28;
  v34 = 1;
  v29 = 0;
  v13 = WwanEnumerateInterfaces(v28, 0, &v29);
  if ( v13 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
            (const char *)v13,
            v27[0]);
    WwanCloseHandle(v28, 0);
    v14 = (volatile signed __int32 *)a4[1];
    if ( !v14 || _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) != 1 )
      return v12;
    v15 = *(void (**)(void))(*(_QWORD *)v14 + 8LL);
    goto LABEL_17;
  }
  v35[0] = (unsigned __int16 *)&v29;
  LOBYTE(v35[1]) = 1;
  v16 = 0;
  if ( !*v29 )
  {
LABEL_13:
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
      (const char *)0x80070057LL,
      v27[0]);
    WwanFreeMemory(v29);
    WwanCloseHandle(v28, 0);
LABEL_14:
    v18 = (volatile signed __int32 *)a4[1];
    if ( !v18 || _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) != 1 )
      return v12;
    v15 = *(void (**)(void))(*(_QWORD *)v18 + 8LL);
LABEL_17:
    v15();
    return v12;
  }
  while ( 1 )
  {
    v17 = 147LL * v16;
    if ( *a2 == *(_QWORD *)&v29[v17 + 1] && a2[1] == *(_QWORD *)&v29[v17 + 3] )
      break;
    if ( ++v16 >= *v29 )
      goto LABEL_13;
  }
  *(_OWORD *)(a1 + 8) = *(_OWORD *)a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  *(_QWORD *)(a1 + 24) = (a3 + 8) & -(__int64)(a3 != 0);
  if ( a1 != -48 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v20 = a4[1];
  if ( v20 )
  {
    v21 = *a4;
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 12));
  }
  else
  {
    v21 = 0;
  }
  *(_QWORD *)(a1 + 32) = v21;
  v22 = *(volatile signed __int32 **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v20;
  if ( v22 && _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
  *(_OWORD *)v37 = 0;
  v38 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  std::vector<unsigned short>::resize(v37);
  std::vector<unsigned short>::resize(v30);
  StringCchPrintfW(v37[0], v37[1] - v37[0], L"Exit");
  v27[0] = 68;
  StringCchPrintfW(
    v30[0],
    v30[1] - v30[0],
    L"%S(%d):%s",
    "CCellularSettingHelperCommon::Initialize",
    *(_QWORD *)v27,
    v37[0]);
  v23 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v23 > 5u )
  {
    *(unsigned __int16 **)v33 = v30[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v23,
      (__int64)&dword_180079394,
      v24,
      v25,
      (const unsigned __int16 **)v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v37);
  WwanFreeMemory(v29);
  WwanCloseHandle(v28, 0);
  v26 = (volatile signed __int32 *)a4[1];
  if ( v26 && _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x180047a10  mov     rax, rsp
0x180047a13  mov     [rax+8], rbx
0x180047a17  mov     [rax+10h], rsi
0x180047a1b  mov     [rax+20h], r9
0x180047a1f  push    rbp
0x180047a20  push    rdi
0x180047a21  push    r14
0x180047a23  lea     rbp, [rax-5Fh]
0x180047a27  sub     rsp, 0A0h
0x180047a2e  mov     rbx, r9
0x180047a31  mov     r14, r8
0x180047a34  mov     rsi, rdx
0x180047a37  mov     rdi, rcx
0x180047a3a  xorps   xmm0, xmm0
0x180047a3d  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180047a42  mov     [rbp+57h+var_60], 0
0x180047a4a  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x180047a4f  mov     [rbp+57h+var_30], 0
0x180047a57  lea     rcx, [rbp+57h+var_70]
0x180047a5b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047a60  lea     rcx, [rbp+57h+var_40]
0x180047a64  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047a69  mov     rdx, [rbp+57h+var_70+8]
0x180047a6d  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180047a71  sub     rdx, rcx
0x180047a74  sar     rdx, 1; unsigned __int64
0x180047a77  lea     r8, aEnter; "Enter"
0x180047a7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047a83  mov     rdx, [rbp+57h+var_40+8]
0x180047a87  mov     rcx, [rbp+57h+var_40]; unsigned __int16 *
0x180047a8b  sub     rdx, rcx
0x180047a8e  sar     rdx, 1; unsigned __int64
0x180047a91  mov     rax, [rbp+57h+var_70]
0x180047a95  mov     [rsp+0B0h+var_88], rax
0x180047a9a  mov     [rsp+0B0h+var_90], 27h ; '''
0x180047aa2  lea     r9, aCcellularsetti_4; "CCellularSettingHelperCommon::Initializ"...
0x180047aa9  lea     r8, aSDS; "%S(%d):%s"
0x180047ab0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047ab5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047aba  mov     ecx, [rax]
0x180047abc  cmp     ecx, 5
0x180047abf  jbe     short loc_180047AE2
0x180047ac1  mov     rcx, [rbp+57h+var_40]
0x180047ac5  mov     qword ptr [rbp+57h+var_50], rcx
0x180047ac9  lea     rcx, [rbp+57h+var_50]
0x180047acd  mov     qword ptr [rsp+0B0h+var_90], rcx; int
0x180047ad2  lea     rdx, byte_180079371
0x180047ad9  mov     rcx, rax
0x180047adc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047ae1  nop
0x180047ae2  lea     rcx, [rbp+57h+var_40]
0x180047ae6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047aeb  nop
0x180047aec  lea     rcx, [rbp+57h+var_70]
0x180047af0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047af5  mov     [rbp+57h+var_80], 0
0x180047afd  mov     [rbp+57h+var_58], 0
0x180047b04  lea     r9, [rbp+57h+var_80]
0x180047b08  lea     r8, [rbp+57h+var_58]
0x180047b0c  xor     edx, edx
0x180047b0e  lea     ecx, [rdx+1]
0x180047b11  call    cs:__imp_WwanOpenHandle
0x180047b17  test    eax, eax
0x180047b19  jz      short loc_180047B3A
0x180047b1b  mov     rcx, [rbp+5Fh]; this
0x180047b1f  mov     r9d, eax; char *
0x180047b22  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047b29  mov     edx, 29h ; ')'; void *
0x180047b2e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047b33  mov     edi, eax
0x180047b35  jmp     loc_180047C23
0x180047b3a  lea     rax, [rbp+57h+var_80]
0x180047b3e  mov     qword ptr [rbp+57h+var_50], rax
0x180047b42  mov     [rbp+57h+var_48], 1
0x180047b46  mov     [rbp+57h+var_78], 0
0x180047b4e  lea     r8, [rbp+57h+var_78]
0x180047b52  xor     edx, edx
0x180047b54  mov     rcx, [rbp+57h+var_80]
0x180047b58  call    cs:__imp_WwanEnumerateInterfaces
0x180047b5e  test    eax, eax
0x180047b60  jz      short loc_180047BB3
0x180047b62  mov     rcx, [rbp+5Fh]; this
0x180047b66  mov     r9d, eax; char *
0x180047b69  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047b70  mov     edx, 2Ch ; ','; void *
0x180047b75  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047b7a  mov     edi, eax
0x180047b7c  xor     edx, edx
0x180047b7e  mov     rcx, [rbp+57h+var_80]
0x180047b82  call    cs:__imp_WwanCloseHandle
0x180047b88  nop
0x180047b89  mov     rcx, [rbx+8]
0x180047b8d  test    rcx, rcx
0x180047b90  jz      loc_180047C45
0x180047b96  or      edx, 0FFFFFFFFh
0x180047b99  lock xadd [rcx+0Ch], edx
0x180047b9e  cmp     edx, 1
0x180047ba1  jnz     loc_180047C45
0x180047ba7  mov     rax, [rcx]
0x180047baa  mov     rax, [rax+8]
0x180047bae  jmp     loc_180047C40
0x180047bb3  lea     rax, [rbp+57h+var_78]
0x180047bb7  mov     [rbp+57h+var_40], rax
0x180047bbb  mov     byte ptr [rbp+57h+var_40+8], 1
0x180047bbf  xor     ecx, ecx
0x180047bc1  mov     rdx, [rbp+57h+var_78]
0x180047bc5  cmp     [rdx], ecx
0x180047bc7  jbe     short loc_180047BED
0x180047bc9  mov     eax, ecx
0x180047bcb  imul    r8, rax, 24Ch
0x180047bd2  mov     rax, [rsi]
0x180047bd5  cmp     rax, [r8+rdx+4]
0x180047bda  jnz     short loc_180047BE7
0x180047bdc  mov     rax, [rsi+8]
0x180047be0  cmp     rax, [r8+rdx+0Ch]
0x180047be5  jz      short loc_180047C5F
0x180047be7  inc     ecx
0x180047be9  cmp     ecx, [rdx]
0x180047beb  jb      short loc_180047BC9
0x180047bed  mov     rcx, [rbp+5Fh]; this
0x180047bf1  mov     edi, 80070057h
0x180047bf6  mov     r9d, edi; char *
0x180047bf9  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180047c00  mov     edx, 3Ah ; ':'; void *
0x180047c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047c0a  nop
0x180047c0b  mov     rcx, [rbp+57h+var_78]
0x180047c0f  call    cs:__imp_WwanFreeMemory
0x180047c15  nop
0x180047c16  xor     edx, edx
0x180047c18  mov     rcx, [rbp+57h+var_80]
0x180047c1c  call    cs:__imp_WwanCloseHandle
0x180047c22  nop
0x180047c23  mov     rcx, [rbx+8]
0x180047c27  test    rcx, rcx
0x180047c2a  jz      short loc_180047C45
0x180047c2c  or      edx, 0FFFFFFFFh
0x180047c2f  lock xadd [rcx+0Ch], edx
0x180047c34  cmp     edx, 1
0x180047c37  jnz     short loc_180047C45
0x180047c39  mov     rdx, [rcx]
0x180047c3c  mov     rax, [rdx+8]
0x180047c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c45  mov     eax, edi
0x180047c47  lea     r11, [rsp+0B0h+var_10]
0x180047c4f  mov     rbx, [r11+20h]
0x180047c53  mov     rsi, [r11+28h]
0x180047c57  mov     rsp, r11
0x180047c5a  pop     r14
0x180047c5c  pop     rdi
0x180047c5d  pop     rbp
0x180047c5e  retn
0x180047c5f  movups  xmm0, xmmword ptr [rsi]
0x180047c62  movdqu  xmmword ptr [rdi+8], xmm0
0x180047c67  lea     rsi, [rdi+30h]
0x180047c6b  mov     rcx, rsi; lpCriticalSection
0x180047c6e  call    cs:__imp_EnterCriticalSection
0x180047c74  lea     rdx, [r14+8]
0x180047c78  neg     r14
0x180047c7b  sbb     rax, rax
0x180047c7e  and     rax, rdx
0x180047c81  mov     [rdi+18h], rax
0x180047c85  test    rsi, rsi
0x180047c88  jz      short loc_180047C93
0x180047c8a  mov     rcx, rsi; lpCriticalSection
0x180047c8d  call    cs:__imp_LeaveCriticalSection
0x180047c93  mov     rax, [rbx+8]
0x180047c97  test    rax, rax
0x180047c9a  jz      short loc_180047CA5
0x180047c9c  mov     rcx, [rbx]
0x180047c9f  lock inc dword ptr [rax+0Ch]
0x180047ca3  jmp     short loc_180047CA7
0x180047ca5  xor     ecx, ecx
0x180047ca7  mov     [rdi+20h], rcx
0x180047cab  mov     rcx, [rdi+28h]
0x180047caf  mov     [rdi+28h], rax
0x180047cb3  test    rcx, rcx
0x180047cb6  jz      short loc_180047CD1
0x180047cb8  or      eax, 0FFFFFFFFh
0x180047cbb  lock xadd [rcx+0Ch], eax
0x180047cc0  cmp     eax, 1
0x180047cc3  jnz     short loc_180047CD1
0x180047cc5  mov     rax, [rcx]
0x180047cc8  mov     rax, [rax+8]
0x180047ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cd1  xorps   xmm0, xmm0
0x180047cd4  movdqu  xmmword ptr [rbp+57h+var_28], xmm0
0x180047cd9  mov     [rbp+57h+var_18], 0
0x180047ce1  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180047ce6  mov     [rbp+57h+var_60], 0
0x180047cee  lea     rcx, [rbp+57h+var_28]
0x180047cf2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047cf7  lea     rcx, [rbp+57h+var_70]
0x180047cfb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180047d00  mov     rdx, [rbp+57h+var_28+8]
0x180047d04  mov     rcx, [rbp+57h+var_28]; unsigned __int16 *
0x180047d08  sub     rdx, rcx
0x180047d0b  sar     rdx, 1; unsigned __int64
0x180047d0e  lea     r8, aExit; "Exit"
0x180047d15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047d1a  mov     rdx, [rbp+57h+var_70+8]
0x180047d1e  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180047d22  sub     rdx, rcx
0x180047d25  sar     rdx, 1; unsigned __int64
0x180047d28  mov     rax, [rbp+57h+var_28]
0x180047d2c  mov     [rsp+0B0h+var_88], rax
0x180047d31  mov     [rsp+0B0h+var_90], 44h ; 'D'
0x180047d39  lea     r9, aCcellularsetti_4; "CCellularSettingHelperCommon::Initializ"...
0x180047d40  lea     r8, aSDS; "%S(%d):%s"
0x180047d47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047d4c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180047d51  mov     ecx, [rax]
0x180047d53  cmp     ecx, 5
0x180047d56  jbe     short loc_180047D79
0x180047d58  mov     rcx, [rbp+57h+var_70]
0x180047d5c  mov     qword ptr [rbp+57h+var_50], rcx
0x180047d60  lea     rcx, [rbp+57h+var_50]
0x180047d64  mov     qword ptr [rsp+0B0h+var_90], rcx
0x180047d69  lea     rdx, dword_180079394
0x180047d70  mov     rcx, rax
0x180047d73  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180047d78  nop
0x180047d79  lea     rcx, [rbp+57h+var_70]
0x180047d7d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047d82  nop
0x180047d83  lea     rcx, [rbp+57h+var_28]
0x180047d87  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180047d8c  nop
0x180047d8d  mov     rcx, [rbp+57h+var_78]
0x180047d91  call    cs:__imp_WwanFreeMemory
0x180047d97  nop
0x180047d98  xor     edx, edx
0x180047d9a  mov     rcx, [rbp+57h+var_80]
0x180047d9e  call    cs:__imp_WwanCloseHandle
0x180047da4  nop
0x180047da5  mov     rcx, [rbx+8]
0x180047da9  test    rcx, rcx
0x180047dac  jz      short loc_180047DC7
0x180047dae  or      eax, 0FFFFFFFFh
0x180047db1  lock xadd [rcx+0Ch], eax
0x180047db6  cmp     eax, 1
0x180047db9  jnz     short loc_180047DC7
0x180047dbb  mov     rax, [rcx]
0x180047dbe  mov     rax, [rax+8]
0x180047dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dc7  xor     eax, eax
0x180047dc9  jmp     loc_180047C47
```
