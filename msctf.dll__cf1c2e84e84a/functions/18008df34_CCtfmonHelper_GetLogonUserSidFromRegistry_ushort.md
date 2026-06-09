# CCtfmonHelper::GetLogonUserSidFromRegistry(ushort * *)

- ea: `0x18008df34`
- end: `0x18008e0ba`
- name: `?GetLogonUserSidFromRegistry@CCtfmonHelper@@SAXPEAPEAG@Z`
- size: `390`
- prototype: `void __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180053ba0`

## callees

- `0x1800341b4`
- `0x180053c74`
- `0x18005fa4c`
- `0x180074b68`
- `0x18008df34`
- `0x18008e0c0`
- `0x18008e14c`
- `0x1800a5d3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008df9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008df9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008dfd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008dfd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e014`

## string_xrefs

- `0x18008e04d`: `SelectedUserSID`
- `0x18008e000`: `LoggedOnUserSID`
- `0x18008e028`: `LastLoggedOnUserSID`
- `0x18008dfbd`: `UserSID`

## pseudocode

```c
void __fastcall CCtfmonHelper::GetLogonUserSidFromRegistry(
        unsigned __int16 **a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  _WORD *v4; // rbx
  __int64 v6; // rdx
  HKEY *v7; // r9
  LSTATUS v8; // eax
  bool v9; // sf
  __int64 v10; // rdx
  _QWORD v11[3]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v12; // [rsp+48h] [rbp-20h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]
  __int64 v14; // [rsp+58h] [rbp-10h]
  HKEY hKey; // [rsp+90h] [rbp+28h] BYREF

  v4 = 0;
  memset(v11, 0, sizeof(v11));
  LODWORD(hKey) = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(
              (HKEY)a1,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
              L"Enabled",
              a4,
              (int *)&hKey) >= 0
    && (_DWORD)hKey )
  {
    hKey = 0;
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserSwitch",
           0,
           0x20019u,
           &hKey);
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
    if ( !v9 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        v11,
        hKey,
        L"UserSID");
      RegCloseKey(hKey);
LABEL_14:
      v4 = (_WORD *)v11[0];
    }
  }
  else
  {
    hKey = 0;
    if ( (int)input_profile_settings::RegOpenSessionDataKey(
                (input_profile_settings *)NtCurrentPeb()->SessionId,
                v6,
                &hKey,
                v7) < 0
      || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
            v11,
            hKey,
            L"LoggedOnUserSID"),
          RegCloseKey(hKey),
          (v4 = (_WORD *)v11[0]) == 0)
      || !*(_WORD *)v11[0] )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        v11,
        v10,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
        L"LastLoggedOnUserSID");
      v4 = (_WORD *)v11[0];
    }
    if ( !v4 || !*v4 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        v11,
        v10,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
        L"SelectedUserSID");
      goto LABEL_14;
    }
  }
  *a1 = 0;
  if ( v4 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(&v12, v11) >= 0 )
    {
      *a1 = v12;
      v12 = 0;
      v14 = 0;
      v13 = 0;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v12);
    Internal_CoTaskMemFree(v4);
  }
}

```

## disassembly

```asm
0x18008df34  push    rbp
0x18008df36  push    rbx
0x18008df37  push    rsi
0x18008df38  push    rdi
0x18008df39  mov     rbp, rsp
0x18008df3c  sub     rsp, 68h
0x18008df40  xor     esi, esi
0x18008df42  lea     rax, [rbp+hKey]
0x18008df46  mov     ebx, esi
0x18008df48  mov     [rbp+var_30], rsi
0x18008df4c  lea     r8, aEnabled; "Enabled"
0x18008df53  mov     [rbp+var_38], rbx
0x18008df57  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008df5e  mov     [rbp+var_28], rsi
0x18008df62  mov     rdi, rcx
0x18008df65  mov     dword ptr [rbp+hKey], esi
0x18008df68  mov     [rsp+68h+phkResult], rax; int *
0x18008df6d  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18008df72  test    eax, eax
0x18008df74  js      short loc_18008DFDC
0x18008df76  cmp     dword ptr [rbp+hKey], esi
0x18008df79  jz      short loc_18008DFDC
0x18008df7b  lea     rax, [rbp+hKey]
0x18008df7f  mov     [rbp+hKey], rsi
0x18008df83  mov     r9d, 20019h; samDesired
0x18008df89  mov     [rsp+68h+phkResult], rax; phkResult
0x18008df8e  xor     r8d, r8d; ulOptions
0x18008df91  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008df98  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008df9f  call    cs:__imp_RegOpenKeyExW
0x18008dfa5  test    eax, eax
0x18008dfa7  jle     short loc_18008DFB3
0x18008dfa9  movzx   eax, ax
0x18008dfac  or      eax, 80070000h
0x18008dfb1  test    eax, eax
0x18008dfb3  js      loc_18008E068
0x18008dfb9  mov     rdx, [rbp+hKey]
0x18008dfbd  lea     r8, aUsersid; "UserSID"
0x18008dfc4  lea     rcx, [rbp+var_38]
0x18008dfc8  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18008dfcd  mov     rcx, [rbp+hKey]; hKey
0x18008dfd1  call    cs:__imp_RegCloseKey
0x18008dfd7  jmp     loc_18008E064
0x18008dfdc  mov     [rbp+hKey], rsi
0x18008dfe0  lea     r8, [rbp+hKey]; unsigned int
0x18008dfe4  mov     rcx, gs:60h
0x18008dfed  mov     ecx, [rcx+2C0h]; this
0x18008dff3  call    ?RegOpenSessionDataKey@input_profile_settings@@YAJKKPEAPEAUHKEY__@@@Z; input_profile_settings::RegOpenSessionDataKey(ulong,ulong,HKEY__ * *)
0x18008dff8  test    eax, eax
0x18008dffa  js      short loc_18008E028
0x18008dffc  mov     rdx, [rbp+hKey]
0x18008e000  lea     r8, aLoggedonusersi; "LoggedOnUserSID"
0x18008e007  lea     rcx, [rbp+var_38]
0x18008e00b  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18008e010  mov     rcx, [rbp+hKey]; hKey
0x18008e014  call    cs:__imp_RegCloseKey
0x18008e01a  mov     rbx, [rbp+var_38]
0x18008e01e  test    rbx, rbx
0x18008e021  jz      short loc_18008E028
0x18008e023  cmp     [rbx], si
0x18008e026  jnz     short loc_18008E043
0x18008e028  lea     r9, aLastloggedonus; "LastLoggedOnUserSID"
0x18008e02f  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008e036  lea     rcx, [rbp+var_38]
0x18008e03a  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18008e03f  mov     rbx, [rbp+var_38]
0x18008e043  test    rbx, rbx
0x18008e046  jz      short loc_18008E04D
0x18008e048  cmp     [rbx], si
0x18008e04b  jnz     short loc_18008E068
0x18008e04d  lea     r9, aSelectedusersi; "SelectedUserSID"
0x18008e054  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008e05b  lea     rcx, [rbp+var_38]
0x18008e05f  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18008e064  mov     rbx, [rbp+var_38]
0x18008e068  mov     [rdi], rsi
0x18008e06b  test    rbx, rbx
0x18008e06e  jz      short loc_18008E0B1
0x18008e070  lea     rdx, [rbp+var_38]
0x18008e074  mov     [rbp+var_20], rsi
0x18008e078  lea     rcx, [rbp+var_20]
0x18008e07c  mov     [rbp+var_18], rsi
0x18008e080  mov     [rbp+var_10], rsi
0x18008e084  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18008e089  test    eax, eax
0x18008e08b  js      short loc_18008E0A0
0x18008e08d  mov     rax, [rbp+var_20]
0x18008e091  mov     [rdi], rax
0x18008e094  mov     [rbp+var_20], rsi
0x18008e098  mov     [rbp+var_10], rsi
0x18008e09c  mov     [rbp+var_18], rsi
0x18008e0a0  lea     rcx, [rbp+var_20]
0x18008e0a4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008e0a9  mov     rcx, rbx; void *
0x18008e0ac  call    ?Internal_CoTaskMemFree@@YAXPEAX@Z; Internal_CoTaskMemFree(void *)
0x18008e0b1  add     rsp, 68h
0x18008e0b5  pop     rdi
0x18008e0b6  pop     rsi
0x18008e0b7  pop     rbx
0x18008e0b8  pop     rbp
0x18008e0b9  retn
```
