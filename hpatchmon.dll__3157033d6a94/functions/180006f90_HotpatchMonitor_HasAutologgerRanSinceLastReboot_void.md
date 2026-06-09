# HotpatchMonitor::HasAutologgerRanSinceLastReboot(void)

- ea: `0x180006f90`
- end: `0x18000722b`
- name: `?HasAutologgerRanSinceLastReboot@HotpatchMonitor@@MEAA_NXZ`
- size: `667`
- prototype: `bool __fastcall(HotpatchMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800011cc`
- `0x18000132c`
- `0x180002270`
- `0x180006f90`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006fb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006fb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007036`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007036`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007053`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007053`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ff8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ff8`
- `msvcp_win!_Xtime_get_ticks` at `0x180006fc0`
- `msvcp_win!_Xtime_get_ticks` at `0x180006fc0`

## pseudocode

```c
bool __fastcall HotpatchMonitor::HasAutologgerRanSinceLastReboot(HotpatchMonitor *this)
{
  ULONGLONG TickCount64; // rsi
  __int64 ticks; // rdi
  LSTATUS v3; // eax
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  LSTATUS v7; // eax
  __int16 v8; // ax
  signed __int64 v10; // rdi
  bool v11; // bl
  bool v12; // [rsp+50h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-61h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v16; // [rsp+68h] [rbp-51h] BYREF
  __int64 v17; // [rsp+70h] [rbp-49h] BYREF
  const wchar_t *v18; // [rsp+78h] [rbp-41h] BYREF
  __int16 v19; // [rsp+80h] [rbp-39h]
  _BYTE v20[32]; // [rsp+90h] [rbp-29h] BYREF
  DWORD *p_cbData; // [rsp+B0h] [rbp-9h]
  __int64 v22; // [rsp+B8h] [rbp-1h]
  __int64 *v23; // [rsp+C0h] [rbp+7h]
  __int64 v24; // [rsp+C8h] [rbp+Fh]
  bool *v25; // [rsp+D0h] [rbp+17h]
  __int64 v26; // [rsp+D8h] [rbp+1Fh]

  *(_QWORD *)Data = 0;
  TickCount64 = GetTickCount64();
  ticks = _Xtime_get_ticks();
  hKey = 0;
  cbData = 8;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegUtil::SERVICE_KEY, 0, 0x20019u, &hKey);
  v6 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v6 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v6 = 0;
    v7 = RegQueryValueExW(hKey, L"AutologgerLastRunTime", 0, 0, Data, &cbData);
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      else
        v6 = v7;
    }
    RegCloseKey(hKey);
  }
  if ( v6 >= 0 )
  {
    v10 = ticks - 10000 * TickCount64;
    v11 = *(_QWORD *)Data > v10 / 10000;
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      v16 = *(_QWORD *)Data;
      v17 = v10 / 10000;
      v25 = &v12;
      v12 = *(_QWORD *)Data > v10 / 10000;
      v23 = &v17;
      v26 = 1;
      p_cbData = (DWORD *)&v16;
      v24 = 8;
      v22 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_180018FEB, 0, 0, 5, v20);
    }
    return v11;
  }
  else
  {
    if ( (unsigned int)dword_18001E048 > 5 )
    {
      cbData = v6;
      p_cbData = &cbData;
      v22 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_1800191AD, 0, 0, 3, v20);
    }
    if ( (unsigned int)dword_18001E080 > 5
      && (qword_18001E090 & 0x800000000000LL) != 0
      && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
    {
      cbData = v6;
      hKey = (HKEY)"GetAutologgerLastRunTime";
      if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
        v8 = -2;
      else
        v8 = 2 * TraceUtil::AutologgerStringLength;
      v19 = v8;
      v18 = L"Autologger";
      v17 = 0x80000000LL;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)L"Autologger",
        (unsigned int)&word_180018A76,
        v4,
        v5,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&hKey,
        (__int64)&cbData);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180006f90  push    rbp
0x180006f92  push    rbx
0x180006f93  push    rsi
0x180006f94  push    rdi
0x180006f95  lea     rbp, [rsp-3Fh]
0x180006f9a  sub     rsp, 0F8h
0x180006fa1  mov     rax, cs:__security_cookie
0x180006fa8  xor     rax, rsp
0x180006fab  mov     [rbp+57h+var_30], rax
0x180006faf  mov     qword ptr [rbp+57h+Data], 0
0x180006fb7  call    cs:__imp_GetTickCount64
0x180006fbd  mov     rsi, rax
0x180006fc0  call    cs:__imp__Xtime_get_ticks
0x180006fc6  mov     rdx, cs:?SERVICE_KEY@RegUtil@@0QEBGEB; lpSubKey
0x180006fcd  mov     r9d, 20019h; samDesired
0x180006fd3  mov     rdi, rax
0x180006fd6  mov     [rbp+57h+hKey], 0
0x180006fde  lea     rax, [rbp+57h+hKey]
0x180006fe2  mov     [rbp+57h+cbData], 8
0x180006fe9  xor     r8d, r8d; ulOptions
0x180006fec  mov     [rsp+110h+phkResult], rax; phkResult
0x180006ff1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006ff8  call    cs:__imp_RegOpenKeyExW
0x180006ffe  mov     ebx, eax
0x180007000  test    eax, eax
0x180007002  jz      short loc_180007011
0x180007004  jle     short loc_180007059
0x180007006  movzx   ebx, ax
0x180007009  or      ebx, 80070000h
0x18000700f  jmp     short loc_180007059
0x180007011  mov     rcx, [rbp+57h+hKey]; hKey
0x180007015  lea     rax, [rbp+57h+cbData]
0x180007019  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18000701e  lea     rdx, ValueName; "AutologgerLastRunTime"
0x180007025  lea     rax, [rbp+57h+Data]
0x180007029  xor     r9d, r9d; lpType
0x18000702c  xor     r8d, r8d; lpReserved
0x18000702f  mov     [rsp+110h+phkResult], rax; lpData
0x180007034  xor     ebx, ebx
0x180007036  call    cs:__imp_RegQueryValueExW
0x18000703c  test    eax, eax
0x18000703e  jz      short loc_18000704F
0x180007040  jg      short loc_180007046
0x180007042  mov     ebx, eax
0x180007044  jmp     short loc_18000704F
0x180007046  movzx   ebx, ax
0x180007049  or      ebx, 80070000h
0x18000704f  mov     rcx, [rbp+57h+hKey]; hKey
0x180007053  call    cs:__imp_RegCloseKey
0x180007059  test    ebx, ebx
0x18000705b  jns     loc_180007171
0x180007061  mov     eax, cs:dword_18001E048
0x180007067  cmp     eax, 5
0x18000706a  jbe     short loc_1800070A9
0x18000706c  lea     rax, [rbp+57h+cbData]
0x180007070  mov     [rbp+57h+cbData], ebx
0x180007073  mov     [rbp+57h+var_60], rax
0x180007077  lea     rdx, byte_1800191AD
0x18000707e  lea     rax, [rbp+57h+var_80]
0x180007082  mov     [rbp+57h+var_58], 4
0x18000708a  mov     [rsp+110h+lpcbData], rax
0x18000708f  lea     rcx, dword_18001E048
0x180007096  xor     r9d, r9d
0x180007099  mov     dword ptr [rsp+110h+phkResult], 3
0x1800070a1  xor     r8d, r8d
0x1800070a4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800070a9  mov     eax, cs:dword_18001E080
0x1800070af  cmp     eax, 5
0x1800070b2  jbe     loc_18000716A
0x1800070b8  mov     rcx, cs:qword_18001E098
0x1800070bf  mov     rdx, 800000000000h
0x1800070c9  mov     rax, cs:qword_18001E090
0x1800070d0  test    rdx, rax
0x1800070d3  jz      loc_18000716A
0x1800070d9  mov     rax, rcx
0x1800070dc  and     rax, rdx
0x1800070df  cmp     rax, rcx
0x1800070e2  jnz     loc_18000716A
0x1800070e8  lea     rax, aGetautologgerl; "GetAutologgerLastRunTime"
0x1800070ef  mov     [rbp+57h+cbData], ebx
0x1800070f2  mov     [rbp+57h+hKey], rax
0x1800070f6  mov     ecx, 7FFFh
0x1800070fb  movzx   eax, cs:?AutologgerStringLength@TraceUtil@@2_KA; unsigned __int64 TraceUtil::AutologgerStringLength
0x180007102  cmp     ax, cx
0x180007105  ja      short loc_18000710C
0x180007107  add     ax, ax
0x18000710a  jmp     short loc_180007111
0x18000710c  mov     eax, 0FFFEh
0x180007111  mov     [rbp+57h+var_90], ax
0x180007115  lea     rcx, aAutologger_0; "Autologger"
0x18000711c  mov     eax, 80000000h
0x180007121  mov     [rbp+57h+var_98], rcx
0x180007125  mov     [rbp+57h+var_A0], rax
0x180007129  lea     rdx, word_180018A76
0x180007130  lea     rax, [rbp+57h+cbData]
0x180007134  mov     [rbp+57h+var_A8], 1000000h
0x18000713c  mov     [rsp+110h+var_D0], rax
0x180007141  lea     rax, [rbp+57h+hKey]
0x180007145  mov     [rsp+110h+var_D8], rax
0x18000714a  lea     rax, [rbp+57h+var_98]
0x18000714e  mov     [rsp+110h+var_E0], rax
0x180007153  lea     rax, [rbp+57h+var_A8]
0x180007157  mov     [rsp+110h+lpcbData], rax
0x18000715c  lea     rax, [rbp+57h+var_A0]
0x180007160  mov     [rsp+110h+phkResult], rax
0x180007165  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000716a  xor     al, al
0x18000716c  jmp     loc_180007213
0x180007171  imul    rax, rsi, 2710h
0x180007178  sub     rdi, rax
0x18000717b  mov     rax, 346DC5D63886594Bh
0x180007185  imul    rdi
0x180007188  sar     rdx, 0Bh
0x18000718c  mov     rax, rdx
0x18000718f  shr     rax, 3Fh
0x180007193  add     rdx, rax
0x180007196  mov     eax, cs:dword_18001E048
0x18000719c  cmp     qword ptr [rbp+57h+Data], rdx
0x1800071a0  setnle  bl
0x1800071a3  cmp     eax, 5
0x1800071a6  jbe     short loc_180007211
0x1800071a8  mov     rax, qword ptr [rbp+57h+Data]
0x1800071ac  lea     rcx, dword_18001E048
0x1800071b3  mov     [rbp+57h+var_A8], rax
0x1800071b7  xor     r9d, r9d
0x1800071ba  lea     rax, [rbp+57h+var_C0]
0x1800071be  mov     [rbp+57h+var_A0], rdx
0x1800071c2  mov     [rbp+57h+var_40], rax
0x1800071c6  lea     rdx, byte_180018FEB
0x1800071cd  lea     rax, [rbp+57h+var_A0]
0x1800071d1  mov     [rbp+57h+var_C0], bl
0x1800071d4  mov     [rbp+57h+var_50], rax
0x1800071d8  xor     r8d, r8d
0x1800071db  lea     rax, [rbp+57h+var_A8]
0x1800071df  mov     [rbp+57h+var_38], 1
0x1800071e7  mov     [rbp+57h+var_60], rax
0x1800071eb  lea     rax, [rbp+57h+var_80]
0x1800071ef  mov     [rsp+110h+lpcbData], rax
0x1800071f4  mov     dword ptr [rsp+110h+phkResult], 5
0x1800071fc  mov     [rbp+57h+var_48], 8
0x180007204  mov     [rbp+57h+var_58], 8
0x18000720c  call    _tlgWriteTransfer_EventWriteTransfer
0x180007211  mov     al, bl
0x180007213  mov     rcx, [rbp+57h+var_30]
0x180007217  xor     rcx, rsp; StackCookie
0x18000721a  call    __security_check_cookie
0x18000721f  add     rsp, 0F8h
0x180007226  pop     rdi
0x180007227  pop     rsi
0x180007228  pop     rbx
0x180007229  pop     rbp
0x18000722a  retn
```
