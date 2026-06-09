# CCellularSettingHelperCommon::SetMultiSimActiveSlot(ulong)

- ea: `0x180048df0`
- end: `0x18004903f`
- name: `?SetMultiSimActiveSlot@CCellularSettingHelperCommon@@UEAAJK@Z`
- size: `591`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x180048df0`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180049026`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180049026`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180048edc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180048edc`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048f39`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048f39`

## string_xrefs

- `0x180048eea`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048f47`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048e54`: `CCellularSettingHelperCommon::SetMultiSimActiveSlot`
- `0x180048fb2`: `CCellularSettingHelperCommon::SetMultiSimActiveSlot`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::SetMultiSimActiveSlot(CCellularSettingHelperCommon *this, unsigned int a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // eax
  unsigned int v8; // eax
  int v9; // ebx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // [rsp+20h] [rbp-60h]
  unsigned int *v14; // [rsp+20h] [rbp-60h]
  unsigned int v15[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v16[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v18[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v19; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  unsigned int v21; // [rsp+98h] [rbp+18h] BYREF
  int v22; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v23; // [rsp+A8h] [rbp+28h] BYREF

  v21 = a2;
  v19 = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  *(_OWORD *)v16 = 0;
  std::vector<unsigned short>::resize(v18);
  std::vector<unsigned short>::resize(v16);
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"Enter");
  v13 = 455;
  StringCchPrintfW(v16[0], v16[1] - v16[0], L"%S(%d):%s", "CCellularSettingHelperCommon::SetMultiSimActiveSlot");
  v3 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    *(unsigned __int16 **)v15 = v16[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)&word_180078EB6,
      v4,
      v5,
      (const unsigned __int16 **)v15);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  v23 = 0;
  v22 = 0;
  v6 = WwanOpenHandle(1, 0, &v22, &v23);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1CA,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v6,
             v13);
  v14 = &v21;
  v8 = WwanSetInterface(v23, (char *)this + 8, 47, 4);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1CD,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
           (const char *)v8,
           (unsigned int)&v21);
  }
  else
  {
    v17 = 0;
    v19 = 0;
    *(_OWORD *)v16 = 0;
    *(_OWORD *)v18 = 0;
    std::vector<unsigned short>::resize(v16);
    std::vector<unsigned short>::resize(v18);
    StringCchPrintfW(v16[0], v16[1] - v16[0], L"Exit");
    LODWORD(v14) = 463;
    StringCchPrintfW(
      v18[0],
      v18[1] - v18[0],
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::SetMultiSimActiveSlot",
      v14,
      v16[0],
      0,
      0);
    v10 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      *(unsigned __int16 **)v15 = v18[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)byte_180078ED9,
        v11,
        v12,
        (const unsigned __int16 **)v15);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
    v9 = 0;
  }
  WwanCloseHandle(v23, 0);
  return v9;
}

```

## disassembly

```asm
0x180048df0  mov     [rsp-8+arg_0], rbx
0x180048df5  mov     [rsp-8+arg_8], edx
0x180048df9  push    rbp
0x180048dfa  mov     rbp, rsp
0x180048dfd  sub     rsp, 80h
0x180048e04  xorps   xmm0, xmm0
0x180048e07  mov     [rbp+var_10], 0
0x180048e0f  mov     rbx, rcx
0x180048e12  mov     [rbp+var_28], 0
0x180048e1a  lea     rcx, [rbp+var_20]
0x180048e1e  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180048e23  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180048e28  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048e2d  lea     rcx, [rbp+var_38]
0x180048e31  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048e36  mov     rdx, [rbp+var_20+8]
0x180048e3a  lea     r8, aEnter; "Enter"
0x180048e41  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180048e45  sub     rdx, rcx
0x180048e48  sar     rdx, 1; unsigned __int64
0x180048e4b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048e50  mov     rdx, [rbp+var_38+8]
0x180048e54  lea     r9, aCcellularsetti_29; "CCellularSettingHelperCommon::SetMultiS"...
0x180048e5b  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180048e5f  lea     r8, aSDS; "%S(%d):%s"
0x180048e66  mov     rax, [rbp+var_20]
0x180048e6a  sub     rdx, rcx
0x180048e6d  mov     [rsp+80h+var_58], rax
0x180048e72  sar     rdx, 1; unsigned __int64
0x180048e75  mov     [rsp+80h+var_60], 1C7h
0x180048e7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048e82  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048e87  mov     ecx, [rax]
0x180048e89  cmp     ecx, 5
0x180048e8c  jbe     short loc_180048EAE
0x180048e8e  mov     rcx, [rbp+var_38]
0x180048e92  lea     rdx, word_180078EB6
0x180048e99  mov     qword ptr [rbp+var_40], rcx
0x180048e9d  lea     rcx, [rbp+var_40]
0x180048ea1  mov     qword ptr [rsp+80h+var_60], rcx; unsigned int
0x180048ea6  mov     rcx, rax
0x180048ea9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048eae  lea     rcx, [rbp+var_38]
0x180048eb2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048eb7  lea     rcx, [rbp+var_20]
0x180048ebb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048ec0  xor     edx, edx
0x180048ec2  mov     [rbp+arg_18], 0
0x180048eca  lea     r9, [rbp+arg_18]
0x180048ece  mov     [rbp+arg_10], 0
0x180048ed5  lea     r8, [rbp+arg_10]
0x180048ed9  lea     ecx, [rdx+1]
0x180048edc  call    cs:__imp_WwanOpenHandle
0x180048ee2  test    eax, eax
0x180048ee4  jz      short loc_180048F03
0x180048ee6  mov     rcx, [rbp+8]; this
0x180048eea  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048ef1  mov     r9d, eax; char *
0x180048ef4  mov     edx, 1CAh; void *
0x180048ef9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048efe  jmp     loc_18004902E
0x180048f03  mov     rcx, [rbp+arg_18]
0x180048f07  lea     rax, [rbp+arg_8]
0x180048f0b  mov     [rsp+80h+var_48], 0
0x180048f14  lea     rdx, [rbx+8]
0x180048f18  mov     r9d, 4
0x180048f1e  mov     [rsp+80h+var_50], 0
0x180048f27  mov     [rsp+80h+var_58], 0
0x180048f30  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x180048f35  lea     r8d, [r9+2Bh]
0x180048f39  call    cs:__imp_WwanSetInterface
0x180048f3f  test    eax, eax
0x180048f41  jz      short loc_180048F62
0x180048f43  mov     rcx, [rbp+8]; this
0x180048f47  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048f4e  mov     r9d, eax; char *
0x180048f51  mov     edx, 1CDh; void *
0x180048f56  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048f5b  mov     ebx, eax
0x180048f5d  jmp     loc_180049020
0x180048f62  xorps   xmm0, xmm0
0x180048f65  mov     [rbp+var_28], 0
0x180048f6d  xorps   xmm1, xmm1
0x180048f70  mov     [rbp+var_10], 0
0x180048f78  lea     rcx, [rbp+var_38]
0x180048f7c  movdqu  xmmword ptr [rbp+var_38], xmm0
0x180048f81  movdqu  xmmword ptr [rbp+var_20], xmm1
0x180048f86  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048f8b  lea     rcx, [rbp+var_20]
0x180048f8f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048f94  mov     rdx, [rbp+var_38+8]
0x180048f98  lea     r8, aExit; "Exit"
0x180048f9f  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180048fa3  sub     rdx, rcx
0x180048fa6  sar     rdx, 1; unsigned __int64
0x180048fa9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048fae  mov     rdx, [rbp+var_20+8]
0x180048fb2  lea     r9, aCcellularsetti_29; "CCellularSettingHelperCommon::SetMultiS"...
0x180048fb9  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180048fbd  lea     r8, aSDS; "%S(%d):%s"
0x180048fc4  mov     rax, [rbp+var_38]
0x180048fc8  sub     rdx, rcx
0x180048fcb  mov     [rsp+80h+var_58], rax
0x180048fd0  sar     rdx, 1; unsigned __int64
0x180048fd3  mov     [rsp+80h+var_60], 1CFh
0x180048fdb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048fe0  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048fe5  mov     ecx, [rax]
0x180048fe7  cmp     ecx, 5
0x180048fea  jbe     short loc_18004900C
0x180048fec  mov     rcx, [rbp+var_20]
0x180048ff0  lea     rdx, byte_180078ED9
0x180048ff7  mov     qword ptr [rbp+var_40], rcx
0x180048ffb  lea     rcx, [rbp+var_40]
0x180048fff  mov     qword ptr [rsp+80h+var_60], rcx
0x180049004  mov     rcx, rax
0x180049007  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004900c  lea     rcx, [rbp+var_20]
0x180049010  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180049015  lea     rcx, [rbp+var_38]
0x180049019  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004901e  xor     ebx, ebx
0x180049020  mov     rcx, [rbp+arg_18]
0x180049024  xor     edx, edx
0x180049026  call    cs:__imp_WwanCloseHandle
0x18004902c  mov     eax, ebx
0x18004902e  mov     rbx, [rsp+80h+arg_0]
0x180049036  add     rsp, 80h
0x18004903d  pop     rbp
0x18004903e  retn
```
