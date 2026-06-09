# CCellularSettingHelperWwan::SetExecutorRadioState(MBN_RADIO)

- ea: `0x18004f120`
- end: `0x18004f3a4`
- name: `?SetExecutorRadioState@CCellularSettingHelperWwan@@UEAAJW4MBN_RADIO@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this, enum MBN_RADIO)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x18004f120`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f38b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f38b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004f23a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004f23a`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004f29e`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18004f29e`

## pseudocode

```c
int __fastcall CCellularSettingHelperWwan::SetExecutorRadioState(CCellularSettingHelperWwan *this, unsigned int a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // ebx
  unsigned int v7; // eax
  unsigned int v9; // eax
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // [rsp+20h] [rbp-60h]
  unsigned int *v14; // [rsp+20h] [rbp-60h]
  __int64 v15; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v16[2]; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v17[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  unsigned __int16 *v19[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v20; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  unsigned int v22; // [rsp+98h] [rbp+18h] BYREF
  int v23; // [rsp+A0h] [rbp+20h] BYREF
  int v24; // [rsp+A8h] [rbp+28h]

  v22 = a2;
  v20 = 0;
  v18 = 0;
  *(_OWORD *)v19 = 0;
  *(_OWORD *)v17 = 0;
  std::vector<unsigned short>::resize(v19);
  std::vector<unsigned short>::resize(v17);
  StringCchPrintfW(v19[0], v19[1] - v19[0], L"Enter");
  v13 = 470;
  StringCchPrintfW(v17[0], v17[1] - v17[0], L"%S(%d):%s", "CCellularSettingHelperWwan::SetExecutorRadioState");
  v3 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    *(unsigned __int16 **)v16 = v17[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v3,
      (__int64)&dword_180079484,
      v4,
      v5,
      (const unsigned __int16 **)v16);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v17);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
  if ( v22 < 2 )
  {
    v15 = 0;
    v23 = 0;
    v7 = WwanOpenHandle(1, 0, &v23, &v15);
    if ( v7 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1E5,
               (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
               (const char *)v7,
               v13);
    v24 = 0;
    v14 = &v22;
    v9 = WwanSetInterface(v15, (char *)this + 8, 1, 4);
    if ( v9 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1E9,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
             (const char *)v9,
             (unsigned int)&v22);
    }
    else
    {
      v18 = 0;
      v20 = 0;
      *(_OWORD *)v17 = 0;
      *(_OWORD *)v19 = 0;
      std::vector<unsigned short>::resize(v17);
      std::vector<unsigned short>::resize(v19);
      StringCchPrintfW(v17[0], v17[1] - v17[0], L"Exit");
      LODWORD(v14) = 491;
      StringCchPrintfW(
        v19[0],
        v19[1] - v19[0],
        L"%S(%d):%s",
        "CCellularSettingHelperWwan::SetExecutorRadioState",
        v14,
        v17[0],
        0,
        0);
      v10 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v10 > 5u )
      {
        *(unsigned __int16 **)v16 = v19[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v10,
          (__int64)&byte_1800794A7,
          v11,
          v12,
          (const unsigned __int16 **)v16);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v17);
      v6 = 0;
    }
    WwanCloseHandle(v15, 0);
  }
  else
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)0x80070057LL,
      v13);
  }
  return v6;
}

```

## disassembly

```asm
0x18004f120  mov     [rsp-8+arg_0], rbx
0x18004f125  mov     [rsp-8+arg_8], edx
0x18004f129  push    rbp
0x18004f12a  mov     rbp, rsp
0x18004f12d  sub     rsp, 80h
0x18004f134  xorps   xmm0, xmm0
0x18004f137  mov     [rbp+var_8], 0
0x18004f13f  mov     rbx, rcx
0x18004f142  mov     [rbp+var_20], 0
0x18004f14a  lea     rcx, [rbp+var_18]
0x18004f14e  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18004f153  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18004f158  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f15d  lea     rcx, [rbp+var_30]
0x18004f161  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f166  mov     rdx, [rbp+var_18+8]
0x18004f16a  lea     r8, aEnter; "Enter"
0x18004f171  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18004f175  sub     rdx, rcx
0x18004f178  sar     rdx, 1; unsigned __int64
0x18004f17b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f180  mov     rdx, [rbp+var_30+8]
0x18004f184  lea     r9, aCcellularsetti_30; "CCellularSettingHelperWwan::SetExecutor"...
0x18004f18b  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18004f18f  lea     r8, aSDS; "%S(%d):%s"
0x18004f196  mov     rax, [rbp+var_18]
0x18004f19a  sub     rdx, rcx
0x18004f19d  mov     [rsp+80h+var_58], rax
0x18004f1a2  sar     rdx, 1; unsigned __int64
0x18004f1a5  mov     [rsp+80h+var_60], 1D6h
0x18004f1ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f1b2  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004f1b7  mov     ecx, [rax]
0x18004f1b9  cmp     ecx, 5
0x18004f1bc  jbe     short loc_18004F1DE
0x18004f1be  mov     rcx, [rbp+var_30]
0x18004f1c2  lea     rdx, dword_180079484
0x18004f1c9  mov     qword ptr [rbp+var_38], rcx
0x18004f1cd  lea     rcx, [rbp+var_38]
0x18004f1d1  mov     qword ptr [rsp+80h+var_60], rcx; unsigned int
0x18004f1d6  mov     rcx, rax
0x18004f1d9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004f1de  lea     rcx, [rbp+var_30]
0x18004f1e2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f1e7  lea     rcx, [rbp+var_18]
0x18004f1eb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f1f0  mov     ecx, [rbp+arg_8]
0x18004f1f3  test    ecx, ecx
0x18004f1f5  jz      short loc_18004F21E
0x18004f1f7  cmp     ecx, 1
0x18004f1fa  jz      short loc_18004F21E
0x18004f1fc  mov     rcx, [rbp+8]; this
0x18004f200  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f207  mov     ebx, 80070057h
0x18004f20c  mov     edx, 1E1h; void *
0x18004f211  mov     r9d, ebx; char *
0x18004f214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f219  jmp     loc_18004F391
0x18004f21e  xor     edx, edx
0x18004f220  mov     [rbp+var_40], 0
0x18004f228  lea     r9, [rbp+var_40]
0x18004f22c  mov     [rbp+arg_10], 0
0x18004f233  lea     r8, [rbp+arg_10]
0x18004f237  lea     ecx, [rdx+1]
0x18004f23a  call    cs:__imp_WwanOpenHandle
0x18004f240  test    eax, eax
0x18004f242  jz      short loc_18004F261
0x18004f244  mov     rcx, [rbp+8]; this
0x18004f248  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f24f  mov     r9d, eax; char *
0x18004f252  mov     edx, 1E5h; void *
0x18004f257  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f25c  jmp     loc_18004F393
0x18004f261  mov     rcx, [rbp+var_40]
0x18004f265  lea     rax, [rbp+arg_18]
0x18004f269  mov     [rsp+80h+var_48], 0
0x18004f272  lea     rdx, [rbx+8]
0x18004f276  mov     r9d, 4
0x18004f27c  mov     [rsp+80h+var_50], 0
0x18004f285  mov     [rsp+80h+var_58], rax
0x18004f28a  lea     rax, [rbp+arg_8]
0x18004f28e  mov     [rbp+arg_18], 0
0x18004f295  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x18004f29a  lea     r8d, [r9-3]
0x18004f29e  call    cs:__imp_WwanSetInterface
0x18004f2a4  test    eax, eax
0x18004f2a6  jz      short loc_18004F2C7
0x18004f2a8  mov     rcx, [rbp+8]; this
0x18004f2ac  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004f2b3  mov     r9d, eax; char *
0x18004f2b6  mov     edx, 1E9h; void *
0x18004f2bb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f2c0  mov     ebx, eax
0x18004f2c2  jmp     loc_18004F385
0x18004f2c7  xorps   xmm0, xmm0
0x18004f2ca  mov     [rbp+var_20], 0
0x18004f2d2  xorps   xmm1, xmm1
0x18004f2d5  mov     [rbp+var_8], 0
0x18004f2dd  lea     rcx, [rbp+var_30]
0x18004f2e1  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18004f2e6  movdqu  xmmword ptr [rbp+var_18], xmm1
0x18004f2eb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f2f0  lea     rcx, [rbp+var_18]
0x18004f2f4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f2f9  mov     rdx, [rbp+var_30+8]
0x18004f2fd  lea     r8, aExit; "Exit"
0x18004f304  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18004f308  sub     rdx, rcx
0x18004f30b  sar     rdx, 1; unsigned __int64
0x18004f30e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f313  mov     rdx, [rbp+var_18+8]
0x18004f317  lea     r9, aCcellularsetti_30; "CCellularSettingHelperWwan::SetExecutor"...
0x18004f31e  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18004f322  lea     r8, aSDS; "%S(%d):%s"
0x18004f329  mov     rax, [rbp+var_30]
0x18004f32d  sub     rdx, rcx
0x18004f330  mov     [rsp+80h+var_58], rax
0x18004f335  sar     rdx, 1; unsigned __int64
0x18004f338  mov     [rsp+80h+var_60], 1EBh
0x18004f340  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f345  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004f34a  mov     ecx, [rax]
0x18004f34c  cmp     ecx, 5
0x18004f34f  jbe     short loc_18004F371
0x18004f351  mov     rcx, [rbp+var_18]
0x18004f355  lea     rdx, byte_1800794A7
0x18004f35c  mov     qword ptr [rbp+var_38], rcx
0x18004f360  lea     rcx, [rbp+var_38]
0x18004f364  mov     qword ptr [rsp+80h+var_60], rcx
0x18004f369  mov     rcx, rax
0x18004f36c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004f371  lea     rcx, [rbp+var_18]
0x18004f375  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f37a  lea     rcx, [rbp+var_30]
0x18004f37e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004f383  xor     ebx, ebx
0x18004f385  mov     rcx, [rbp+var_40]
0x18004f389  xor     edx, edx
0x18004f38b  call    cs:__imp_WwanCloseHandle
0x18004f391  mov     eax, ebx
0x18004f393  mov     rbx, [rsp+80h+arg_0]
0x18004f39b  add     rsp, 80h
0x18004f3a2  pop     rbp
0x18004f3a3  retn
```
