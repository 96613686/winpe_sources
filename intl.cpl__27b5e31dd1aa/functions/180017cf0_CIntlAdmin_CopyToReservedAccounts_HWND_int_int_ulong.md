# CIntlAdmin::CopyToReservedAccounts(HWND__ *,int,int,ulong *)

- ea: `0x180017cf0`
- end: `0x180017e4d`
- name: `?CopyToReservedAccounts@CIntlAdmin@@UEAAJPEAUHWND__@@HHPEAK@Z`
- size: `349`
- prototype: `int(CIntlAdmin *__hidden this, HWND, int, int, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x18001319c`
- `0x180016e00`
- `0x180017c90`
- `0x180017cbc`
- `0x180017cf0`
- `0x180017fdc`
- `0x18001809c`
- `0x180026038`
- `0x1800261f0`
- `0x180026234`
- `0x180026304`
- `0x180026994`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e1d`

## string_xrefs

- `0x180017dad`: `CopySettingsToNewUserAccounts`
- `0x180017d42`: `CopySettingsToSystemAccounts`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIntlAdmin::CopyToReservedAccounts(CIntlAdmin *this, HWND a2, int a3, int a4, unsigned int *a5)
{
  HKEY v8; // rbx
  signed int v9; // eax
  int v10; // eax
  _QWORD v12[42]; // [rsp+20h] [rbp-178h] BYREF

  if ( a3 || a4 )
  {
    v8 = Intl_RegOpenCurrentUser();
    if ( a3 )
    {
      wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v12,
        "CopySettingsToSystemAccounts");
      v12[0] = &IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::`vftable';
      IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::StartActivity((IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts *)v12);
      v9 = Intl_SaveSystemAcctSettings(v8, a2, 1);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12, v9);
      Intl_SetUILanguageForSystemAccts(v8, a5);
      IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::~CopySettingsToSystemAccounts((IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts *)v12);
    }
    if ( a4 )
    {
      wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v12,
        "CopySettingsToNewUserAccounts");
      v12[0] = &IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::`vftable';
      IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::StartActivity((IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts *)v12);
      v10 = Intl_SaveDefaultUserSettings(v8, a2, 1);
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12, v10);
      Intl_SaveUISettingsToNtUserFile(v8);
      IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::~CopySettingsToNewUserAccounts((IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts *)v12);
    }
    if ( v8 != HKEY_CURRENT_USER )
      RegCloseKey(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180017cf0  mov     [rsp+arg_0], rbx
0x180017cf5  mov     [rsp+arg_10], rbp
0x180017cfa  push    rsi
0x180017cfb  push    rdi
0x180017cfc  push    r14
0x180017cfe  sub     rsp, 180h
0x180017d05  mov     rax, cs:__security_cookie
0x180017d0c  xor     rax, rsp
0x180017d0f  mov     [rsp+198h+var_28], rax
0x180017d17  mov     edi, r9d
0x180017d1a  mov     esi, r8d
0x180017d1d  mov     rbp, rdx
0x180017d20  mov     r14, [rsp+198h+arg_20]
0x180017d28  test    r8d, r8d
0x180017d2b  jnz     short loc_180017D36
0x180017d2d  test    r9d, r9d
0x180017d30  jz      loc_180017E23
0x180017d36  call    ?Intl_RegOpenCurrentUser@@YAPEAUHKEY__@@XZ; Intl_RegOpenCurrentUser(void)
0x180017d3b  mov     rbx, rax
0x180017d3e  test    esi, esi
0x180017d40  jz      short loc_180017DA9
0x180017d42  lea     rdx, aCopysettingsto_0; "CopySettingsToSystemAccounts"
0x180017d49  lea     rcx, [rsp+198h+var_178]
0x180017d4e  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017d53  lea     rax, ??_7CopySettingsToSystemAccounts@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::`vftable'
0x180017d5a  mov     [rsp+198h+var_178], rax
0x180017d5f  lea     rcx, [rsp+198h+var_178]; this
0x180017d64  call    ?StartActivity@CopySettingsToSystemAccounts@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::StartActivity(void)
0x180017d69  nop
0x180017d6a  mov     r8d, 1; int
0x180017d70  mov     rdx, rbp; HWND
0x180017d73  mov     rcx, rbx; HKEY
0x180017d76  call    ?Intl_SaveSystemAcctSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z; Intl_SaveSystemAcctSettings(HKEY__ *,HWND__ *,int)
0x180017d7b  test    eax, eax
0x180017d7d  jle     short loc_180017D87
0x180017d7f  movzx   eax, ax
0x180017d82  or      eax, 80070000h
0x180017d87  mov     edx, eax
0x180017d89  lea     rcx, [rsp+198h+var_178]
0x180017d8e  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180017d93  mov     rdx, r14; unsigned int *
0x180017d96  mov     rcx, rbx; hKey
0x180017d99  call    ?Intl_SetUILanguageForSystemAccts@@YAXPEAUHKEY__@@PEAK@Z; Intl_SetUILanguageForSystemAccts(HKEY__ *,ulong *)
0x180017d9e  nop
0x180017d9f  lea     rcx, [rsp+198h+var_178]; this
0x180017da4  call    ??1CopySettingsToSystemAccounts@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::CopySettingsToSystemAccounts::~CopySettingsToSystemAccounts(void)
0x180017da9  test    edi, edi
0x180017dab  jz      short loc_180017E11
0x180017dad  lea     rdx, aCopysettingsto; "CopySettingsToNewUserAccounts"
0x180017db4  lea     rcx, [rsp+198h+var_178]
0x180017db9  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017dbe  lea     rax, ??_7CopySettingsToNewUserAccounts@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::`vftable'
0x180017dc5  mov     [rsp+198h+var_178], rax
0x180017dca  lea     rcx, [rsp+198h+var_178]; this
0x180017dcf  call    ?StartActivity@CopySettingsToNewUserAccounts@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::StartActivity(void)
0x180017dd4  nop
0x180017dd5  mov     r8d, 1; int
0x180017ddb  mov     rdx, rbp; HWND
0x180017dde  mov     rcx, rbx; HKEY
0x180017de1  call    ?Intl_SaveDefaultUserSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z; Intl_SaveDefaultUserSettings(HKEY__ *,HWND__ *,int)
0x180017de6  test    eax, eax
0x180017de8  jle     short loc_180017DF2
0x180017dea  movzx   eax, ax
0x180017ded  or      eax, 80070000h
0x180017df2  mov     edx, eax
0x180017df4  lea     rcx, [rsp+198h+var_178]
0x180017df9  call    ?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180017dfe  mov     rcx, rbx; hKey
0x180017e01  call    ?Intl_SaveUISettingsToNtUserFile@@YAXPEAUHKEY__@@@Z; Intl_SaveUISettingsToNtUserFile(HKEY__ *)
0x180017e06  nop
0x180017e07  lea     rcx, [rsp+198h+var_178]; this
0x180017e0c  call    ??1CopySettingsToNewUserAccounts@IntlCplTraceLoggingTelemetry@@QEAA@XZ; IntlCplTraceLoggingTelemetry::CopySettingsToNewUserAccounts::~CopySettingsToNewUserAccounts(void)
0x180017e11  cmp     rbx, 0FFFFFFFF80000001h
0x180017e18  jz      short loc_180017E23
0x180017e1a  mov     rcx, rbx; hKey
0x180017e1d  call    cs:__imp_RegCloseKey
0x180017e23  xor     eax, eax
0x180017e25  mov     rcx, [rsp+198h+var_28]
0x180017e2d  xor     rcx, rsp; StackCookie
0x180017e30  call    __security_check_cookie
0x180017e35  lea     r11, [rsp+198h+var_18]
0x180017e3d  mov     rbx, [r11+20h]
0x180017e41  mov     rbp, [r11+30h]
0x180017e45  mov     rsp, r11
0x180017e48  pop     r14
0x180017e4a  pop     rdi
0x180017e4b  pop     rsi
0x180017e4c  retn
```
