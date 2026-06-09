# PowerState::GetConnectedStandbyState(void)

- ea: `0x18001de74`
- end: `0x18001e157`
- name: `?GetConnectedStandbyState@PowerState@@AEAAJXZ`
- size: `739`
- prototype: `__int64 __fastcall(PowerState *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001fa38`

## callees

- `0x1800031b0`
- `0x180011b78`
- `0x180013cf8`
- `0x18001de74`
- `0x18001e208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e07d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e05e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dfd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e0c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dfd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e0c3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e02d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e02d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dec9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001def2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001def2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001df4e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001df7b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e06f`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e0e0`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e119`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e135`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001df4e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001df7b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e06f`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e0e0`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e119`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001e135`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001dfae`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001e0a2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001dfae`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18001e0a2`

## pseudocode

```c
__int64 __fastcall PowerState::GetConnectedStandbyState(PowerState *this)
{
  HANDLE EventW; // rax
  void *v3; // r14
  HANDLE v4; // rbx
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  DWORD v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  DWORD v13; // ebx
  DWORD v14; // eax
  signed int v15; // eax
  void *v16; // rcx
  const char *v17; // r9
  HPOWERNOTIFY v18; // rsi
  DWORD v19; // ebx
  HPOWERNOTIFY RegistrationHandle; // [rsp+20h] [rbp-30h] BYREF
  _QWORD Recipient[2]; // [rsp+28h] [rbp-28h] BYREF
  GUID SettingGuid; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  Recipient[1] = this;
  RegistrationHandle = 0;
  Recipient[0] = HandlePowerStatusChangeCallback;
  SettingGuid = GUID_LOW_POWER_EPOCH;
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 1);
  v4 = EventW;
  if ( v3 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v3) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
  {
    v8 = GetLastError();
    if ( v8 )
    {
      v9 = 85;
LABEL_7:
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v9,
              (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\powerstate.cpp",
              (const char *)v8,
              (unsigned int)RegistrationHandle);
LABEL_8:
      v11 = v10;
LABEL_9:
      if ( RegistrationHandle )
        PowerSettingUnregisterNotification(RegistrationHandle);
      return v11;
    }
  }
  if ( RegistrationHandle )
  {
    v13 = GetLastError();
    PowerSettingUnregisterNotification(RegistrationHandle);
    SetLastError(v13);
  }
  RegistrationHandle = 0;
  v8 = PowerSettingRegisterNotification(&SettingGuid, 2u, Recipient, &RegistrationHandle);
  if ( v8 )
  {
    v9 = 91;
    goto LABEL_7;
  }
  v14 = WaitForSingleObject(*((HANDLE *)this + 1), 0xC8u);
  if ( v14 )
    goto LABEL_17;
  v16 = (void *)*((_QWORD *)this + 1);
  SettingGuid = GUID_ACDC_POWER_SOURCE;
  if ( !ResetEvent(v16) )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x6D,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\powerstate.cpp",
            v17);
    goto LABEL_8;
  }
  v18 = RegistrationHandle;
  if ( RegistrationHandle )
  {
    v19 = GetLastError();
    PowerSettingUnregisterNotification(v18);
    SetLastError(v19);
  }
  RegistrationHandle = 0;
  v8 = PowerSettingRegisterNotification(&SettingGuid, 2u, Recipient, &RegistrationHandle);
  if ( v8 )
  {
    v9 = 111;
    goto LABEL_7;
  }
  v14 = WaitForSingleObject(*((HANDLE *)this + 1), 0xC8u);
  if ( v14 )
  {
LABEL_17:
    if ( v14 == 258 )
    {
      if ( RegistrationHandle )
        PowerSettingUnregisterNotification(RegistrationHandle);
      return 2147943860LL;
    }
    else
    {
      if ( v14 == -1 )
      {
        v15 = GetLastError();
        v11 = v15;
        if ( v15 > 0 )
          v11 = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_9;
      }
      if ( RegistrationHandle )
        PowerSettingUnregisterNotification(RegistrationHandle);
      return 2147549183LL;
    }
  }
  else
  {
    if ( RegistrationHandle )
      PowerSettingUnregisterNotification(RegistrationHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x18001de74  mov     [rsp-18h+arg_8], rbx
0x18001de79  mov     [rsp-18h+arg_10], rsi
0x18001de7e  push    rbp
0x18001de7f  push    rdi
0x18001de80  push    r14
0x18001de82  mov     rbp, rsp
0x18001de85  sub     rsp, 50h
0x18001de89  mov     rax, cs:__security_cookie
0x18001de90  xor     rax, rsp
0x18001de93  mov     [rbp+var_8], rax
0x18001de97  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18001de9e  xor     r9d, r9d; lpName
0x18001dea1  mov     [rbp+var_20], rcx
0x18001dea5  mov     rdi, rcx
0x18001dea8  mov     [rbp+RegistrationHandle], 0
0x18001deb0  lea     rax, ?HandlePowerStatusChangeCallback@@YAKPEAXK0@Z; HandlePowerStatusChangeCallback(void *,ulong,void *)
0x18001deb7  xor     r8d, r8d; bInitialState
0x18001deba  xor     ecx, ecx; lpEventAttributes
0x18001debc  mov     [rbp+Recipient], rax
0x18001dec0  lea     edx, [r9+1]; bManualReset
0x18001dec4  movdqu  xmmword ptr [rbp+SettingGuid.Data1], xmm0
0x18001dec9  call    cs:__imp_CreateEventW
0x18001ded0  nop     dword ptr [rax+rax+00h]
0x18001ded5  mov     r14, [rdi+8]
0x18001ded9  mov     rbx, rax
0x18001dedc  test    r14, r14
0x18001dedf  jz      short loc_18001DF14
0x18001dee1  call    cs:__imp_GetLastError
0x18001dee8  nop     dword ptr [rax+rax+00h]
0x18001deed  mov     rcx, r14; hObject
0x18001def0  mov     esi, eax
0x18001def2  call    cs:__imp_CloseHandle
0x18001def9  nop     dword ptr [rax+rax+00h]
0x18001defe  test    eax, eax
0x18001df00  jz      loc_18001E148
0x18001df06  mov     ecx, esi; dwErrCode
0x18001df08  call    cs:__imp_SetLastError
0x18001df0f  nop     dword ptr [rax+rax+00h]
0x18001df14  mov     [rdi+8], rbx
0x18001df18  test    rbx, rbx
0x18001df1b  jnz     short loc_18001DF61
0x18001df1d  call    cs:__imp_GetLastError
0x18001df24  nop     dword ptr [rax+rax+00h]
0x18001df29  test    eax, eax
0x18001df2b  jz      short loc_18001DF61
0x18001df2d  lea     edx, [rbx+55h]; void *
0x18001df30  mov     rcx, [rbp+18h]; this
0x18001df34  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001df3b  mov     r9d, eax; char *
0x18001df3e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001df43  mov     ebx, eax
0x18001df45  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x18001df49  test    rcx, rcx
0x18001df4c  jz      short loc_18001DF5A
0x18001df4e  call    cs:__imp_PowerSettingUnregisterNotification
0x18001df55  nop     dword ptr [rax+rax+00h]
0x18001df5a  mov     eax, ebx
0x18001df5c  jmp     loc_18001E0EE
0x18001df61  mov     rsi, [rbp+RegistrationHandle]
0x18001df65  test    rsi, rsi
0x18001df68  jz      short loc_18001DF95
0x18001df6a  call    cs:__imp_GetLastError
0x18001df71  nop     dword ptr [rax+rax+00h]
0x18001df76  mov     rcx, rsi; RegistrationHandle
0x18001df79  mov     ebx, eax
0x18001df7b  call    cs:__imp_PowerSettingUnregisterNotification
0x18001df82  nop     dword ptr [rax+rax+00h]
0x18001df87  mov     ecx, ebx; dwErrCode
0x18001df89  call    cs:__imp_SetLastError
0x18001df90  nop     dword ptr [rax+rax+00h]
0x18001df95  lea     r9, [rbp+RegistrationHandle]; RegistrationHandle
0x18001df99  mov     [rbp+RegistrationHandle], 0
0x18001dfa1  lea     r8, [rbp+Recipient]; Recipient
0x18001dfa5  mov     edx, 2; Flags
0x18001dfaa  lea     rcx, [rbp+SettingGuid]; SettingGuid
0x18001dfae  call    cs:__imp_PowerSettingRegisterNotification
0x18001dfb5  nop     dword ptr [rax+rax+00h]
0x18001dfba  test    eax, eax
0x18001dfbc  jz      short loc_18001DFC8
0x18001dfbe  mov     edx, 5Bh ; '['
0x18001dfc3  jmp     loc_18001DF30
0x18001dfc8  mov     rcx, [rdi+8]; hHandle
0x18001dfcc  mov     r14d, 0C8h
0x18001dfd2  mov     edx, r14d; dwMilliseconds
0x18001dfd5  call    cs:__imp_WaitForSingleObject
0x18001dfdc  nop     dword ptr [rax+rax+00h]
0x18001dfe1  test    eax, eax
0x18001dfe3  jz      short loc_18001E01D
0x18001dfe5  cmp     eax, 102h
0x18001dfea  jz      loc_18001E12C
0x18001dff0  cmp     eax, 0FFFFFFFFh
0x18001dff3  jnz     loc_18001E110
0x18001dff9  call    cs:__imp_GetLastError
0x18001e000  nop     dword ptr [rax+rax+00h]
0x18001e005  mov     ebx, eax
0x18001e007  test    eax, eax
0x18001e009  jle     loc_18001DF45
0x18001e00f  movzx   ebx, ax
0x18001e012  or      ebx, 80070000h
0x18001e018  jmp     loc_18001DF45
0x18001e01d  movups  xmm0, xmmword ptr cs:GUID_ACDC_POWER_SOURCE.Data1
0x18001e024  mov     rcx, [rdi+8]; hEvent
0x18001e028  movdqu  xmmword ptr [rbp+SettingGuid.Data1], xmm0
0x18001e02d  call    cs:__imp_ResetEvent
0x18001e034  nop     dword ptr [rax+rax+00h]
0x18001e039  test    eax, eax
0x18001e03b  jnz     short loc_18001E055
0x18001e03d  mov     rcx, [rbp+18h]; this
0x18001e041  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001e048  lea     edx, [rax+6Dh]; void *
0x18001e04b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e050  jmp     loc_18001DF43
0x18001e055  mov     rsi, [rbp+RegistrationHandle]
0x18001e059  test    rsi, rsi
0x18001e05c  jz      short loc_18001E089
0x18001e05e  call    cs:__imp_GetLastError
0x18001e065  nop     dword ptr [rax+rax+00h]
0x18001e06a  mov     rcx, rsi; RegistrationHandle
0x18001e06d  mov     ebx, eax
0x18001e06f  call    cs:__imp_PowerSettingUnregisterNotification
0x18001e076  nop     dword ptr [rax+rax+00h]
0x18001e07b  mov     ecx, ebx; dwErrCode
0x18001e07d  call    cs:__imp_SetLastError
0x18001e084  nop     dword ptr [rax+rax+00h]
0x18001e089  lea     r9, [rbp+RegistrationHandle]; RegistrationHandle
0x18001e08d  mov     [rbp+RegistrationHandle], 0
0x18001e095  lea     r8, [rbp+Recipient]; Recipient
0x18001e099  mov     edx, 2; Flags
0x18001e09e  lea     rcx, [rbp+SettingGuid]; SettingGuid
0x18001e0a2  call    cs:__imp_PowerSettingRegisterNotification
0x18001e0a9  nop     dword ptr [rax+rax+00h]
0x18001e0ae  test    eax, eax
0x18001e0b0  jz      short loc_18001E0BC
0x18001e0b2  mov     edx, 6Fh ; 'o'
0x18001e0b7  jmp     loc_18001DF30
0x18001e0bc  mov     rcx, [rdi+8]; hHandle
0x18001e0c0  mov     edx, r14d; dwMilliseconds
0x18001e0c3  call    cs:__imp_WaitForSingleObject
0x18001e0ca  nop     dword ptr [rax+rax+00h]
0x18001e0cf  test    eax, eax
0x18001e0d1  jnz     loc_18001DFE5
0x18001e0d7  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x18001e0db  test    rcx, rcx
0x18001e0de  jz      short loc_18001E0EC
0x18001e0e0  call    cs:__imp_PowerSettingUnregisterNotification
0x18001e0e7  nop     dword ptr [rax+rax+00h]
0x18001e0ec  xor     eax, eax
0x18001e0ee  mov     rcx, [rbp+var_8]
0x18001e0f2  xor     rcx, rsp; StackCookie
0x18001e0f5  call    __security_check_cookie
0x18001e0fa  lea     r11, [rsp+50h+var_s0]
0x18001e0ff  mov     rbx, [r11+28h]
0x18001e103  mov     rsi, [r11+30h]
0x18001e107  mov     rsp, r11
0x18001e10a  pop     r14
0x18001e10c  pop     rdi
0x18001e10d  pop     rbp
0x18001e10e  retn
0x18001e110  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x18001e114  test    rcx, rcx
0x18001e117  jz      short loc_18001E125
0x18001e119  call    cs:__imp_PowerSettingUnregisterNotification
0x18001e120  nop     dword ptr [rax+rax+00h]
0x18001e125  mov     eax, 8000FFFFh
0x18001e12a  jmp     short loc_18001E0EE
0x18001e12c  mov     rcx, [rbp+RegistrationHandle]; RegistrationHandle
0x18001e130  test    rcx, rcx
0x18001e133  jz      short loc_18001E141
0x18001e135  call    cs:__imp_PowerSettingUnregisterNotification
0x18001e13c  nop     dword ptr [rax+rax+00h]
0x18001e141  mov     eax, 800705B4h
0x18001e146  jmp     short loc_18001E0EE
0x18001e148  mov     rcx, [rbp+18h]; this
0x18001e14c  mov     edx, 0A0Bh; void *
0x18001e151  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
