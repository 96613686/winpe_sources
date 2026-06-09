# CCellularSettingHelperCommon::SetInternetDataEnabled(uchar)

- ea: `0x1800488a0`
- end: `0x180048b29`
- name: `?SetInternetDataEnabled@CCellularSettingHelperCommon@@UEAAJE@Z`
- size: `649`
- prototype: `__int64 __fastcall(CCellularSettingHelperCommon *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x18001dd10`
- `0x1800488a0`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180048b00`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180048b00`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800489a0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800489a0`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048a13`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180048a13`

## string_xrefs

- `0x1800489ae`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048a21`: `onecoreuap\net\mobilebroadbandexperience\mbae\mbaeapi\lib\ccshelpercommon.cpp`
- `0x180048918`: `CCellularSettingHelperCommon::SetInternetDataEnabled`
- `0x180048a8c`: `CCellularSettingHelperCommon::SetInternetDataEnabled`

## pseudocode

```c
int __fastcall CCellularSettingHelperCommon::SetInternetDataEnabled(
        CCellularSettingHelperCommon *this,
        unsigned __int8 a2)
{
  int v2; // edi
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int v9; // eax
  int v10; // ebx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int v14; // [rsp+20h] [rbp-39h]
  unsigned int *v15; // [rsp+20h] [rbp-39h]
  unsigned __int16 *v16[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v17; // [rsp+50h] [rbp-9h]
  unsigned __int16 *v18[2]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v19; // [rsp+68h] [rbp+Fh]
  int v20; // [rsp+70h] [rbp+17h] BYREF
  __int64 v21; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned int v22[2]; // [rsp+80h] [rbp+27h] BYREF
  unsigned int v23[4]; // [rsp+88h] [rbp+2Fh] BYREF
  int v24; // [rsp+98h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = a2;
  v19 = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  *(_OWORD *)v16 = 0;
  std::vector<unsigned short>::resize(v18);
  std::vector<unsigned short>::resize(v16);
  StringCchPrintfW(v18[0], v18[1] - v18[0], L"Enter");
  v14 = 155;
  StringCchPrintfW(v16[0], v16[1] - v16[0], L"%S(%d):%s", "CCellularSettingHelperCommon::SetInternetDataEnabled");
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    *(unsigned __int16 **)v22 = v16[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&word_180079236,
      v5,
      v6,
      (const unsigned __int16 **)v22);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
  v21 = 0;
  v20 = 0;
  v7 = WwanOpenHandle(1, 0, &v20, &v21);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9D,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
             (const char *)v7,
             v14);
  v24 = v2;
  v15 = v23;
  *(_OWORD *)v23 = WWAN_PROFILE_SET_GUID_INTERNET_AO;
  v9 = WwanSetInterface(v21, (char *)this + 8, 15, 20);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xA5,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelpercommon.cpp",
            (const char *)v9,
            (unsigned int)v23);
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
    LODWORD(v15) = 167;
    StringCchPrintfW(
      v18[0],
      v18[1] - v18[0],
      L"%S(%d):%s",
      "CCellularSettingHelperCommon::SetInternetDataEnabled",
      v15,
      v16[0],
      0,
      0);
    v11 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      *(unsigned __int16 **)v22 = v18[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v11,
        (__int64)byte_180079259,
        v12,
        v13,
        (const unsigned __int16 **)v22);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v18);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v16);
    v10 = 0;
  }
  WwanCloseHandle(v21, 0);
  return v10;
}

```

## disassembly

```asm
0x1800488a0  mov     [rsp-8+arg_10], rbx
0x1800488a5  mov     [rsp-8+arg_18], rdi
0x1800488aa  push    rbp
0x1800488ab  lea     rbp, [rsp-57h]
0x1800488b0  sub     rsp, 0B0h
0x1800488b7  mov     rax, cs:__security_cookie
0x1800488be  xor     rax, rsp
0x1800488c1  mov     [rbp+57h+var_10], rax
0x1800488c5  xorps   xmm0, xmm0
0x1800488c8  movzx   edi, dl
0x1800488cb  mov     rbx, rcx
0x1800488ce  mov     [rbp+57h+var_48], 0
0x1800488d6  lea     rcx, [rbp+57h+var_58]
0x1800488da  mov     [rbp+57h+var_60], 0
0x1800488e2  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x1800488e7  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1800488ec  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800488f1  lea     rcx, [rbp+57h+var_70]
0x1800488f5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800488fa  mov     rdx, [rbp+57h+var_58+8]
0x1800488fe  lea     r8, aEnter; "Enter"
0x180048905  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x180048909  sub     rdx, rcx
0x18004890c  sar     rdx, 1; unsigned __int64
0x18004890f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048914  mov     rdx, [rbp+57h+var_70+8]
0x180048918  lea     r9, aCcellularsetti_8; "CCellularSettingHelperCommon::SetIntern"...
0x18004891f  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180048923  lea     r8, aSDS; "%S(%d):%s"
0x18004892a  mov     rax, [rbp+57h+var_58]
0x18004892e  sub     rdx, rcx
0x180048931  mov     [rsp+0B0h+var_88], rax
0x180048936  sar     rdx, 1; unsigned __int64
0x180048939  mov     [rsp+0B0h+var_90], 9Bh
0x180048941  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048946  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004894b  mov     ecx, [rax]
0x18004894d  cmp     ecx, 5
0x180048950  jbe     short loc_180048972
0x180048952  mov     rcx, [rbp+57h+var_70]
0x180048956  lea     rdx, word_180079236
0x18004895d  mov     qword ptr [rbp+57h+var_30], rcx
0x180048961  lea     rcx, [rbp+57h+var_30]
0x180048965  mov     qword ptr [rsp+0B0h+var_90], rcx; unsigned int
0x18004896a  mov     rcx, rax
0x18004896d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048972  lea     rcx, [rbp+57h+var_70]
0x180048976  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004897b  lea     rcx, [rbp+57h+var_58]
0x18004897f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048984  xor     edx, edx
0x180048986  mov     [rbp+57h+var_38], 0
0x18004898e  lea     r9, [rbp+57h+var_38]
0x180048992  mov     [rbp+57h+var_40], 0
0x180048999  lea     r8, [rbp+57h+var_40]
0x18004899d  lea     ecx, [rdx+1]
0x1800489a0  call    cs:__imp_WwanOpenHandle
0x1800489a6  test    eax, eax
0x1800489a8  jz      short loc_1800489C7
0x1800489aa  mov     rcx, [rbp+5Fh]; this
0x1800489ae  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800489b5  mov     r9d, eax; char *
0x1800489b8  mov     edx, 9Dh; void *
0x1800489bd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800489c2  jmp     loc_180048B08
0x1800489c7  movups  xmm1, cs:WWAN_PROFILE_SET_GUID_INTERNET_AO
0x1800489ce  mov     rcx, [rbp+57h+var_38]
0x1800489d2  lea     rax, [rbp+57h+var_28]
0x1800489d6  mov     [rsp+0B0h+var_78], 0
0x1800489df  lea     rdx, [rbx+8]
0x1800489e3  mov     r9d, 14h
0x1800489e9  mov     [rsp+0B0h+var_80], 0
0x1800489f2  xorps   xmm0, xmm0
0x1800489f5  mov     [rsp+0B0h+var_88], 0
0x1800489fe  movups  xmmword ptr [rbp+57h+var_28+4], xmm0
0x180048a02  mov     [rbp+57h+var_18], edi
0x180048a05  lea     r8d, [r9-5]
0x180048a09  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x180048a0e  movdqu  xmmword ptr [rbp+57h+var_28], xmm1
0x180048a13  call    cs:__imp_WwanSetInterface
0x180048a19  test    eax, eax
0x180048a1b  jz      short loc_180048A3C
0x180048a1d  mov     rcx, [rbp+5Fh]; this
0x180048a21  lea     r8, aOnecoreuapNetM; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180048a28  mov     r9d, eax; char *
0x180048a2b  mov     edx, 0A5h; void *
0x180048a30  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048a35  mov     ebx, eax
0x180048a37  jmp     loc_180048AFA
0x180048a3c  xorps   xmm0, xmm0
0x180048a3f  mov     [rbp+57h+var_60], 0
0x180048a47  xorps   xmm1, xmm1
0x180048a4a  mov     [rbp+57h+var_48], 0
0x180048a52  lea     rcx, [rbp+57h+var_70]
0x180048a56  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180048a5b  movdqu  xmmword ptr [rbp+57h+var_58], xmm1
0x180048a60  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048a65  lea     rcx, [rbp+57h+var_58]
0x180048a69  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180048a6e  mov     rdx, [rbp+57h+var_70+8]
0x180048a72  lea     r8, aExit; "Exit"
0x180048a79  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180048a7d  sub     rdx, rcx
0x180048a80  sar     rdx, 1; unsigned __int64
0x180048a83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048a88  mov     rdx, [rbp+57h+var_58+8]
0x180048a8c  lea     r9, aCcellularsetti_8; "CCellularSettingHelperCommon::SetIntern"...
0x180048a93  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x180048a97  lea     r8, aSDS; "%S(%d):%s"
0x180048a9e  mov     rax, [rbp+57h+var_70]
0x180048aa2  sub     rdx, rcx
0x180048aa5  mov     [rsp+0B0h+var_88], rax
0x180048aaa  sar     rdx, 1; unsigned __int64
0x180048aad  mov     [rsp+0B0h+var_90], 0A7h
0x180048ab5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048aba  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180048abf  mov     ecx, [rax]
0x180048ac1  cmp     ecx, 5
0x180048ac4  jbe     short loc_180048AE6
0x180048ac6  mov     rcx, [rbp+57h+var_58]
0x180048aca  lea     rdx, byte_180079259
0x180048ad1  mov     qword ptr [rbp+57h+var_30], rcx
0x180048ad5  lea     rcx, [rbp+57h+var_30]
0x180048ad9  mov     qword ptr [rsp+0B0h+var_90], rcx
0x180048ade  mov     rcx, rax
0x180048ae1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180048ae6  lea     rcx, [rbp+57h+var_58]
0x180048aea  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048aef  lea     rcx, [rbp+57h+var_70]
0x180048af3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180048af8  xor     ebx, ebx
0x180048afa  mov     rcx, [rbp+57h+var_38]
0x180048afe  xor     edx, edx
0x180048b00  call    cs:__imp_WwanCloseHandle
0x180048b06  mov     eax, ebx
0x180048b08  mov     rcx, [rbp+57h+var_10]
0x180048b0c  xor     rcx, rsp; StackCookie
0x180048b0f  call    __security_check_cookie
0x180048b14  lea     r11, [rsp+0B0h+var_s0]
0x180048b1c  mov     rbx, [r11+20h]
0x180048b20  mov     rdi, [r11+28h]
0x180048b24  mov     rsp, r11
0x180048b27  pop     rbp
0x180048b28  retn
```
