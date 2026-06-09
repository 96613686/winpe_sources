# RdsDWMDirectDriverIO::GetRDPDriverDeviceName(void)

- ea: `0x180009a4c`
- end: `0x180009bbd`
- name: `?GetRDPDriverDeviceName@RdsDWMDirectDriverIO@@IEAAJXZ`
- size: `369`
- prototype: `__int64 __fastcall(RdsDWMDirectDriverIO *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a140`

## callees

- `0x180001724`
- `0x180009a4c`
- `0x18000c4ec`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `USER32!EnumDisplayDevicesW` at `0x180009adf`
- `USER32!EnumDisplayDevicesW` at `0x180009adf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009a9c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180009a9c`

## string_xrefs

- `0x180009afd`: `EnumDisplayDevices failed! Driver not installed!`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::GetRDPDriverDeviceName(RdsDWMDirectDriverIO *this)
{
  DWORD v2; // ebx
  DWORD i; // edx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  int v9; // [rsp+50h] [rbp-B0h] BYREF
  int v10; // [rsp+54h] [rbp-ACh] BYREF
  const char *v11; // [rsp+58h] [rbp-A8h] BYREF
  const char *v12; // [rsp+60h] [rbp-A0h] BYREF
  const char *v13; // [rsp+68h] [rbp-98h] BYREF
  const char *v14; // [rsp+70h] [rbp-90h] BYREF
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+80h] [rbp-80h] BYREF

  v2 = 0;
  memset_0(DisplayDevice.DeviceName, 0, 0x344u);
  for ( i = 0; ; i = v2 )
  {
    DisplayDevice.cb = 840;
    if ( !EnumDisplayDevicesW(0, i, &DisplayDevice, 0) )
      break;
    if ( !lstrcmpW(L"RDPUDD Chained DD", DisplayDevice.DeviceString) || (DisplayDevice.StateFlags & 0x1000000) != 0 )
      return (unsigned int)StringCchCopyW((unsigned __int16 *)this + 28, 0x104u, DisplayDevice.DeviceName);
    ++v2;
    memset_0(DisplayDevice.DeviceName, 0, 0x344u);
  }
  v7 = -2147418113;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v9 = 478;
    v11 = "EnumDisplayDevices failed! Driver not installed!";
    v10 = -2147418113;
    v12 = "GetRDPDriverDeviceName";
    v13 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
    v14 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v4,
      (__int64)byte_180038799,
      v5,
      v6,
      (const unsigned __int16 **)&v14,
      (__int64)&v10,
      (const unsigned __int16 **)&v13,
      (__int64)&v9,
      (const unsigned __int16 **)&v12,
      (const unsigned __int16 **)&v11);
  }
  return v7;
}

```

## disassembly

```asm
0x180009a4c  mov     [rsp-8+arg_8], rbx
0x180009a51  mov     [rsp-8+arg_10], rdi
0x180009a56  push    rbp
0x180009a57  lea     rbp, [rsp-2E0h]
0x180009a5f  sub     rsp, 3E0h
0x180009a66  mov     rax, cs:__security_cookie
0x180009a6d  xor     rax, rsp
0x180009a70  mov     [rbp+2E0h+var_10], rax
0x180009a77  mov     rdi, rcx
0x180009a7a  xor     edx, edx; Val
0x180009a7c  lea     rcx, [rbp+2E0h+DisplayDevice.DeviceName]; void *
0x180009a80  mov     r8d, 344h; Size
0x180009a86  xor     ebx, ebx
0x180009a88  call    memset_0
0x180009a8d  xor     edx, edx
0x180009a8f  jmp     short loc_180009ACF
0x180009a91  lea     rdx, [rbp+2E0h+DisplayDevice.DeviceString]; lpString2
0x180009a95  lea     rcx, String1; "RDPUDD Chained DD"
0x180009a9c  call    cs:__imp_lstrcmpW
0x180009aa2  test    eax, eax
0x180009aa4  jz      loc_180009BA7
0x180009aaa  test    [rbp+2E0h+DisplayDevice.StateFlags], 1000000h
0x180009ab4  jnz     loc_180009BA7
0x180009aba  inc     ebx
0x180009abc  lea     rcx, [rbp+2E0h+DisplayDevice.DeviceName]; void *
0x180009ac0  xor     edx, edx; Val
0x180009ac2  mov     r8d, 344h; Size
0x180009ac8  call    memset_0
0x180009acd  mov     edx, ebx; iDevNum
0x180009acf  xor     r9d, r9d; dwFlags
0x180009ad2  mov     [rbp+2E0h+DisplayDevice.cb], 348h
0x180009ad9  lea     r8, [rbp+2E0h+DisplayDevice]; lpDisplayDevice
0x180009add  xor     ecx, ecx; lpDevice
0x180009adf  call    cs:__imp_EnumDisplayDevicesW
0x180009ae5  test    eax, eax
0x180009ae7  jnz     short loc_180009A91
0x180009ae9  mov     eax, cs:dword_180044008
0x180009aef  mov     ebx, 8000FFFFh
0x180009af4  cmp     eax, 2
0x180009af7  jbe     loc_180009B81
0x180009afd  lea     rax, aEnumdisplaydev; "EnumDisplayDevices failed! Driver not i"...
0x180009b04  mov     [rsp+3E0h+var_390], 1DEh
0x180009b0c  mov     [rsp+3E0h+var_388], rax
0x180009b11  lea     rdx, byte_180038799
0x180009b18  lea     rax, aGetrdpdriverde; "GetRDPDriverDeviceName"
0x180009b1f  mov     [rsp+3E0h+var_38C], ebx
0x180009b23  mov     [rsp+3E0h+var_380], rax
0x180009b28  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180009b2f  mov     [rsp+3E0h+var_378], rax
0x180009b34  lea     rax, aErrorCondition; "Error condition failed"
0x180009b3b  mov     [rsp+3E0h+var_370], rax
0x180009b40  lea     rax, [rsp+3E0h+var_388]
0x180009b45  mov     [rsp+3E0h+var_398], rax
0x180009b4a  lea     rax, [rsp+3E0h+var_380]
0x180009b4f  mov     [rsp+3E0h+var_3A0], rax
0x180009b54  lea     rax, [rsp+3E0h+var_390]
0x180009b59  mov     [rsp+3E0h+var_3A8], rax
0x180009b5e  lea     rax, [rsp+3E0h+var_378]
0x180009b63  mov     [rsp+3E0h+var_3B0], rax
0x180009b68  lea     rax, [rsp+3E0h+var_38C]
0x180009b6d  mov     [rsp+3E0h+var_3B8], rax
0x180009b72  lea     rax, [rsp+3E0h+var_370]
0x180009b77  mov     [rsp+3E0h+var_3C0], rax
0x180009b7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180009b81  mov     eax, ebx
0x180009b83  mov     rcx, [rbp+2E0h+var_10]
0x180009b8a  xor     rcx, rsp; StackCookie
0x180009b8d  call    __security_check_cookie
0x180009b92  lea     r11, [rsp+3E0h+var_s0]
0x180009b9a  mov     rbx, [r11+18h]
0x180009b9e  mov     rdi, [r11+20h]
0x180009ba2  mov     rsp, r11
0x180009ba5  pop     rbp
0x180009ba6  retn
0x180009ba7  lea     rcx, [rdi+38h]; unsigned __int16 *
0x180009bab  mov     edx, 104h; unsigned __int64
0x180009bb0  lea     r8, [rbp+2E0h+DisplayDevice.DeviceName]; unsigned __int16 *
0x180009bb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009bb9  mov     ebx, eax
0x180009bbb  jmp     short loc_180009B81
```
