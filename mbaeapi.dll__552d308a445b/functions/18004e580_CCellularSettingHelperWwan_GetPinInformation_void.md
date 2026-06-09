# CCellularSettingHelperWwan::GetPinInformation(void)

- ea: `0x18004e580`
- end: `0x18004e801`
- name: `?GetPinInformation@CCellularSettingHelperWwan@@UEAAJXZ`
- size: `641`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000178c`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18004e580`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004e7e8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004e7e8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004e70a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004e7da`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004e70a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004e7da`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004e66a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004e66a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004e6d9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004e6d9`

## pseudocode

```c
int __fastcall CCellularSettingHelperWwan::GetPinInformation(CCellularSettingHelperWwan *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  unsigned int Interface; // eax
  int v8; // ebx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // [rsp+20h] [rbp-19h]
  unsigned int *v13; // [rsp+20h] [rbp-19h]
  __int64 v14; // [rsp+48h] [rbp+Fh] BYREF
  unsigned int v15[2]; // [rsp+50h] [rbp+17h] BYREF
  unsigned __int16 *v16[2]; // [rsp+58h] [rbp+1Fh] BYREF
  __int64 v17; // [rsp+68h] [rbp+2Fh]
  unsigned __int16 *v18[2]; // [rsp+70h] [rbp+37h] BYREF
  __int64 v19; // [rsp+80h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  int v21; // [rsp+A8h] [rbp+6Fh] BYREF
  int v22; // [rsp+B0h] [rbp+77h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp+7Fh] BYREF

  v19 = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  *(_OWORD *)v16 = 0;
  std::vector<unsigned short>::resize(v18);
  std::vector<unsigned short>::resize(v16);
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"Enter");
  v12 = 288;
  StringCchPrintfW(v16[0], v16[1] - v16[0], L"%S(%d):%s", "CCellularSettingHelperWwan::GetPinInformation");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v15 = v16[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)word_180079722,
      v3,
      v4,
      (const unsigned __int16 **)v15);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  v14 = 0;
  v21 = 0;
  v5 = WwanOpenHandle(1, 0, &v21, &v14);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x122,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
             (const char *)v5,
             v12);
  v23 = 0;
  v13 = &v23;
  v22 = 0;
  Interface = WwanQueryInterface(v14, (char *)this + 8, 0);
  if ( Interface )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x12E,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
           (const char *)Interface,
           (unsigned int)&v23);
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
    LODWORD(v13) = 304;
    StringCchPrintfW(
      v18[0],
      v18[1] - v18[0],
      L"%S(%d):%s",
      "CCellularSettingHelperWwan::GetPinInformation",
      v13,
      v16[0],
      &v22,
      0);
    v9 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      *(unsigned __int16 **)v15 = v18[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v9,
        (__int64)&dword_18007969C,
        v10,
        v11,
        (const unsigned __int16 **)v15);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
    v8 = 0;
  }
  WwanCloseHandle(v14, 0);
  return v8;
}

```

## disassembly

```asm
0x18004e580  mov     [rsp-8+arg_0], rbx
0x18004e585  push    rbp
0x18004e586  lea     rbp, [rsp-57h]
0x18004e58b  sub     rsp, 90h
0x18004e592  xorps   xmm0, xmm0
0x18004e595  mov     [rbp+57h+var_10], 0
0x18004e59d  mov     rbx, rcx
0x18004e5a0  mov     [rbp+57h+var_28], 0
0x18004e5a8  lea     rcx, [rbp+57h+var_20]
0x18004e5ac  movdqu  xmmword ptr [rbp+57h+var_20], xmm0
0x18004e5b1  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x18004e5b6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e5bb  lea     rcx, [rbp+57h+var_38]
0x18004e5bf  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e5c4  mov     rdx, [rbp+57h+var_20+8]
0x18004e5c8  lea     r8, aEnter; "Enter"
0x18004e5cf  mov     rcx, [rbp+57h+var_20]; unsigned __int16 *
0x18004e5d3  sub     rdx, rcx
0x18004e5d6  sar     rdx, 1; unsigned __int64
0x18004e5d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e5de  mov     rdx, [rbp+57h+var_38+8]
0x18004e5e2  lea     r9, aCcellularsetti_20; "CCellularSettingHelperWwan::GetPinInfor"...
0x18004e5e9  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x18004e5ed  lea     r8, aSDS; "%S(%d):%s"
0x18004e5f4  mov     rax, [rbp+57h+var_20]
0x18004e5f8  sub     rdx, rcx
0x18004e5fb  mov     [rsp+90h+var_68], rax
0x18004e600  sar     rdx, 1; unsigned __int64
0x18004e603  mov     [rsp+90h+var_70], 120h
0x18004e60b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e610  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004e615  mov     ecx, [rax]
0x18004e617  cmp     ecx, 5
0x18004e61a  jbe     short loc_18004E63C
0x18004e61c  mov     rcx, [rbp+57h+var_38]
0x18004e620  lea     rdx, word_180079722
0x18004e627  mov     qword ptr [rbp+57h+var_40], rcx
0x18004e62b  lea     rcx, [rbp+57h+var_40]
0x18004e62f  mov     qword ptr [rsp+90h+var_70], rcx; unsigned int
0x18004e634  mov     rcx, rax
0x18004e637  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004e63c  lea     rcx, [rbp+57h+var_38]
0x18004e640  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e645  lea     rcx, [rbp+57h+var_20]
0x18004e649  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e64e  xor     edx, edx
0x18004e650  mov     [rbp+57h+var_48], 0
0x18004e658  lea     r9, [rbp+57h+var_48]
0x18004e65c  mov     [rbp+57h+arg_8], 0
0x18004e663  lea     r8, [rbp+57h+arg_8]
0x18004e667  lea     ecx, [rdx+1]
0x18004e66a  call    cs:__imp_WwanOpenHandle
0x18004e670  test    eax, eax
0x18004e672  jz      short loc_18004E691
0x18004e674  mov     rcx, [rbp+5Fh]; this
0x18004e678  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004e67f  mov     r9d, eax; char *
0x18004e682  mov     edx, 122h; void *
0x18004e687  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e68c  jmp     loc_18004E7F0
0x18004e691  mov     rcx, [rbp+57h+var_48]
0x18004e695  lea     rax, [rbp+57h+arg_10]
0x18004e699  mov     [rsp+90h+var_58], 0
0x18004e6a2  lea     rdx, [rbx+8]
0x18004e6a6  mov     [rsp+90h+var_60], rax
0x18004e6ab  xor     r9d, r9d
0x18004e6ae  lea     rax, [rbp+57h+var_50]
0x18004e6b2  mov     [rbp+57h+var_50], 0
0x18004e6ba  mov     [rsp+90h+var_68], rax
0x18004e6bf  xor     r8d, r8d
0x18004e6c2  lea     rax, [rbp+57h+arg_18]
0x18004e6c6  mov     [rbp+57h+arg_18], 0
0x18004e6cd  mov     qword ptr [rsp+90h+var_70], rax; unsigned int
0x18004e6d2  mov     [rbp+57h+arg_10], 0
0x18004e6d9  call    cs:__imp_WwanQueryInterface
0x18004e6df  test    eax, eax
0x18004e6e1  jz      short loc_18004E715
0x18004e6e3  mov     rcx, [rbp+5Fh]; this
0x18004e6e7  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004e6ee  mov     r9d, eax; char *
0x18004e6f1  mov     edx, 12Eh; void *
0x18004e6f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e6fb  mov     rcx, [rbp+57h+var_50]
0x18004e6ff  mov     ebx, eax
0x18004e701  test    rcx, rcx
0x18004e704  jz      loc_18004E7E2
0x18004e70a  call    cs:__imp_WwanFreeMemory
0x18004e710  jmp     loc_18004E7E2
0x18004e715  xorps   xmm0, xmm0
0x18004e718  mov     [rbp+57h+var_28], 0
0x18004e720  xorps   xmm1, xmm1
0x18004e723  mov     [rbp+57h+var_10], 0
0x18004e72b  lea     rcx, [rbp+57h+var_38]
0x18004e72f  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x18004e734  movdqu  xmmword ptr [rbp+57h+var_20], xmm1
0x18004e739  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e73e  lea     rcx, [rbp+57h+var_20]
0x18004e742  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004e747  mov     rdx, [rbp+57h+var_38+8]
0x18004e74b  lea     r8, aExit; "Exit"
0x18004e752  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x18004e756  sub     rdx, rcx
0x18004e759  sar     rdx, 1; unsigned __int64
0x18004e75c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e761  mov     rdx, [rbp+57h+var_20+8]
0x18004e765  lea     r9, aCcellularsetti_20; "CCellularSettingHelperWwan::GetPinInfor"...
0x18004e76c  mov     rcx, [rbp+57h+var_20]; unsigned __int16 *
0x18004e770  lea     r8, aSDS; "%S(%d):%s"
0x18004e777  mov     rax, [rbp+57h+var_38]
0x18004e77b  sub     rdx, rcx
0x18004e77e  mov     [rsp+90h+var_68], rax
0x18004e783  sar     rdx, 1; unsigned __int64
0x18004e786  mov     [rsp+90h+var_70], 130h
0x18004e78e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004e793  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004e798  mov     ecx, [rax]
0x18004e79a  cmp     ecx, 5
0x18004e79d  jbe     short loc_18004E7BF
0x18004e79f  mov     rcx, [rbp+57h+var_20]
0x18004e7a3  lea     rdx, dword_18007969C
0x18004e7aa  mov     qword ptr [rbp+57h+var_40], rcx
0x18004e7ae  lea     rcx, [rbp+57h+var_40]
0x18004e7b2  mov     qword ptr [rsp+90h+var_70], rcx
0x18004e7b7  mov     rcx, rax
0x18004e7ba  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004e7bf  lea     rcx, [rbp+57h+var_20]
0x18004e7c3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e7c8  lea     rcx, [rbp+57h+var_38]
0x18004e7cc  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004e7d1  mov     rcx, [rbp+57h+var_50]
0x18004e7d5  test    rcx, rcx
0x18004e7d8  jz      short loc_18004E7E0
0x18004e7da  call    cs:__imp_WwanFreeMemory
0x18004e7e0  xor     ebx, ebx
0x18004e7e2  mov     rcx, [rbp+57h+var_48]
0x18004e7e6  xor     edx, edx
0x18004e7e8  call    cs:__imp_WwanCloseHandle
0x18004e7ee  mov     eax, ebx
0x18004e7f0  mov     rbx, [rsp+90h+arg_0]
0x18004e7f8  add     rsp, 90h
0x18004e7ff  pop     rbp
0x18004e800  retn
```
