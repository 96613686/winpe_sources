# Microsoft::Windows::Autopilot::AutopilotDevicePreparationHelpers::GetAndEnforceAutopilotDevicePrepHintIsInOobe(AUTOPILOT_DEVICE_PREP_HINT &)

- ea: `0x140055cdc`
- end: `0x140055e5f`
- name: `?GetAndEnforceAutopilotDevicePrepHintIsInOobe@AutopilotDevicePreparationHelpers@Autopilot@Windows@Microsoft@@SAJAEAW4AUTOPILOT_DEVICE_PREP_HINT@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(enum AUTOPILOT_DEVICE_PREP_HINT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004f290`

## callees

- `0x140003450`
- `0x14000d71c`
- `0x140055cdc`
- `0x140055e68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055d4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055d4e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140055dc5`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140055dc5`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x140055d99`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x140055d99`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotDevicePreparationHelpers::GetAndEnforceAutopilotDevicePrepHintIsInOobe(
        enum AUTOPILOT_DEVICE_PREP_HINT *a1)
{
  LSTATUS ValueW; // eax
  const char *v3; // r9
  bool v4; // sf
  DWORD v5; // ebx
  __int64 v6; // r8
  int v7; // eax
  __int64 *v8; // rdx
  __int64 result; // rax
  DWORD v10; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v11; // [rsp+48h] [rbp-40h] BYREF
  DWORD v12; // [rsp+4Ch] [rbp-3Ch] BYREF
  DWORD *v13; // [rsp+60h] [rbp-28h]
  __int64 v14; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_DWORD *)a1 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Provisioning\\AutopilotSettings",
             L"AutopilotDevicePrepHint",
             0x10u,
             &v10,
             &v11,
             &v12);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
    v4 = 1;
  if ( !v4 )
  {
    v5 = v11;
    if ( v11 <= 4 )
    {
      if ( v11 )
      {
        v11 = 0;
        if ( (unsigned int)Microsoft::Windows::Autopilot::AutopilotDevicePreparationHelpers::IsPostOobeProvisioningAllowed()
          || (unsigned int)OOBEComplete(&v11) && !v11 )
        {
          *(_DWORD *)a1 = v5;
          if ( (byte_140084F42 & 1) != 0 )
          {
            v10 = v5;
            v8 = AutopilotDevicePreparationHint;
            goto LABEL_15;
          }
        }
        else
        {
          v7 = RegDeleteKeyValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Provisioning\\AutopilotSettings",
                 L"AutopilotDevicePrepHint");
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          if ( (byte_140084F42 & 4) != 0 )
          {
            v10 = v7;
            v8 = AutopilotDevicePreparationHintCleared;
LABEL_15:
            v13 = &v10;
            v14 = 4;
            McGenEventWrite_EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, v8, v6, 2);
          }
        }
      }
    }
  }
  result = 0;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v10 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x37,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\autopilotdevicepreparationhelpers.cpp",
              v3);
      result = v10;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x140055cdc  mov     r11, rsp
0x140055cdf  mov     [r11+10h], rbx
0x140055ce3  push    rdi
0x140055ce4  sub     rsp, 80h
0x140055ceb  mov     rax, cs:__security_cookie
0x140055cf2  xor     rax, rsp
0x140055cf5  mov     [rsp+88h+var_18], rax
0x140055cfa  mov     rdi, rcx
0x140055cfd  mov     dword ptr [rcx], 0
0x140055d03  mov     [rsp+88h+var_48], 0
0x140055d0b  mov     [rsp+88h+var_40], 0
0x140055d13  mov     [rsp+88h+var_3C], 4
0x140055d1b  lea     rax, [r11-3Ch]
0x140055d1f  mov     [r11-58h], rax
0x140055d23  lea     rax, [r11-40h]
0x140055d27  mov     [r11-60h], rax
0x140055d2b  lea     rax, [r11-48h]
0x140055d2f  mov     [r11-68h], rax
0x140055d33  mov     r9d, 10h; dwFlags
0x140055d39  lea     r8, aAutopilotdevic; "AutopilotDevicePrepHint"
0x140055d40  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Provisioning\\Auto"...
0x140055d47  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140055d4e  call    cs:__imp_RegGetValueW
0x140055d55  nop     dword ptr [rax+rax+00h]
0x140055d5a  test    eax, eax
0x140055d5c  jle     short loc_140055D68
0x140055d5e  movzx   eax, ax
0x140055d61  or      eax, 80070000h
0x140055d66  test    eax, eax
0x140055d68  js      loc_140055E38
0x140055d6e  mov     ebx, [rsp+88h+var_40]
0x140055d72  cmp     ebx, 4
0x140055d75  ja      loc_140055E38
0x140055d7b  test    ebx, ebx
0x140055d7d  jz      loc_140055E38
0x140055d83  mov     [rsp+88h+var_40], 0
0x140055d8b  call    ?IsPostOobeProvisioningAllowed@AutopilotDevicePreparationHelpers@Autopilot@Windows@Microsoft@@SAHXZ; Microsoft::Windows::Autopilot::AutopilotDevicePreparationHelpers::IsPostOobeProvisioningAllowed(void)
0x140055d90  test    eax, eax
0x140055d92  jnz     short loc_140055DF3
0x140055d94  lea     rcx, [rsp+88h+var_40]
0x140055d99  call    cs:__imp_OOBEComplete
0x140055da0  nop     dword ptr [rax+rax+00h]
0x140055da5  test    eax, eax
0x140055da7  jz      short loc_140055DB0
0x140055da9  cmp     [rsp+88h+var_40], 0
0x140055dae  jz      short loc_140055DF3
0x140055db0  lea     r8, aAutopilotdevic; "AutopilotDevicePrepHint"
0x140055db7  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Provisioning\\Auto"...
0x140055dbe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140055dc5  call    cs:__imp_RegDeleteKeyValueW
0x140055dcc  nop     dword ptr [rax+rax+00h]
0x140055dd1  test    eax, eax
0x140055dd3  jle     short loc_140055DDD
0x140055dd5  movzx   eax, ax
0x140055dd8  or      eax, 80070000h
0x140055ddd  test    cs:byte_140084F42, 4
0x140055de4  jz      short loc_140055E38
0x140055de6  mov     [rsp+88h+var_48], eax
0x140055dea  lea     rdx, AutopilotDevicePreparationHintCleared
0x140055df1  jmp     short loc_140055E09
0x140055df3  mov     [rdi], ebx
0x140055df5  test    cs:byte_140084F42, 1
0x140055dfc  jz      short loc_140055E38
0x140055dfe  mov     [rsp+88h+var_48], ebx
0x140055e02  lea     rdx, AutopilotDevicePreparationHint
0x140055e09  lea     rax, [rsp+88h+var_48]
0x140055e0e  mov     [rsp+88h+var_28], rax
0x140055e13  lea     rax, [rsp+88h+var_38]
0x140055e18  mov     [rsp+88h+var_68], rax
0x140055e1d  mov     [rsp+88h+var_20], 4
0x140055e26  mov     r9d, 2
0x140055e2c  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x140055e33  call    McGenEventWrite_EventWriteTransfer
0x140055e38  xor     eax, eax
0x140055e3a  jmp     short loc_140055E40
0x140055e3c  mov     eax, [rsp+88h+var_48]
0x140055e40  mov     rcx, [rsp+88h+var_18]
0x140055e45  xor     rcx, rsp; StackCookie
0x140055e48  call    __security_check_cookie
0x140055e4d  mov     rbx, [rsp+88h+arg_8]
0x140055e55  add     rsp, 80h
0x140055e5c  pop     rdi
0x140055e5d  retn
```
