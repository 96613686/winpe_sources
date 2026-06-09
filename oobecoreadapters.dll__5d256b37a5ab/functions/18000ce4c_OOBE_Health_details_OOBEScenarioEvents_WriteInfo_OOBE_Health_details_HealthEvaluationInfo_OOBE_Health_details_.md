# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthEvaluationInfo &,bool &,bool &,ushort const *)

- ea: `0x18000ce4c`
- end: `0x18000cf7c`
- name: `??$WriteInfo@UHealthEvaluationInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthEvaluationInfo@123@AEA_N2PEBG@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d7f8`
- `0x18000e870`

## callees

- `0x180009814`
- `0x180009834`
- `0x18000b098`
- `0x18000b0c8`
- `0x18000b200`
- `0x18000b254`
- `0x18000ce4c`
- `0x18000ef04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cf37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cf37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ceff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ceff`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(
        const WCHAR *a1,
        const BYTE *a2,
        HKEY a3,
        _BYTE *a4,
        _BYTE *a5)
{
  __int64 result; // rax
  int RedirectionKeyPath; // eax
  unsigned int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = a3;
  lpSubKey = a1;
  result = (__int64)a5;
  if ( *a5 && *a4 )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    RedirectionKeyPath = GetRedirectionKeyPath(
                           L"OOBEHealth",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
                           (unsigned __int16 **)&lpSubKey);
    if ( RedirectionKeyPath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)RedirectionKeyPath,
        phkResult);
LABEL_11:
      *a4 = 0;
      return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    v10 = retaddr;
    if ( v9 )
    {
      v11 = 1074;
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"HealthEvaluation", 0, 3u, a2, 0xCu);
      v10 = retaddr;
      if ( !v9 )
      {
LABEL_10:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_11;
      }
      v11 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(
      v10,
      (void *)v11,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v9,
      phkResulta);
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x18000ce4c  mov     r11, rsp
0x18000ce4f  mov     [r11+10h], rbx
0x18000ce53  mov     [r11+18h], r8
0x18000ce57  mov     [r11+8], rcx
0x18000ce5b  push    rdi
0x18000ce5c  sub     rsp, 30h
0x18000ce60  mov     rbx, r9
0x18000ce63  mov     rdi, rdx
0x18000ce66  mov     rax, [rsp+38h+arg_20]
0x18000ce6b  cmp     byte ptr [rax], 0
0x18000ce6e  jz      loc_18000CF71
0x18000ce74  cmp     byte ptr [r9], 0
0x18000ce78  jz      loc_18000CF71
0x18000ce7e  mov     qword ptr [r11+8], 0
0x18000ce86  xor     edx, edx
0x18000ce88  lea     rcx, [r11+8]
0x18000ce8c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000ce91  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x18000ce96  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ce9d  lea     rcx, aOobehealth; "OOBEHealth"
0x18000cea4  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x18000cea9  mov     rcx, [rsp+38h]; this
0x18000ceae  test    eax, eax
0x18000ceb0  jns     short loc_18000CECB
0x18000ceb2  mov     r9d, eax; char *
0x18000ceb5  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000cebc  mov     edx, 42Fh; void *
0x18000cec1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cec6  jmp     loc_18000CF64
0x18000cecb  mov     [rsp+38h+hKey], 0
0x18000ced4  xor     edx, edx
0x18000ced6  lea     rcx, [rsp+38h+hKey]
0x18000cedb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000cee0  lea     rax, [rsp+38h+hKey]
0x18000cee5  mov     [rsp+38h+phkResult], rax; phkResult
0x18000ceea  mov     r9d, 0F003Fh; samDesired
0x18000cef0  xor     r8d, r8d; ulOptions
0x18000cef3  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x18000cef8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ceff  call    cs:__imp_RegOpenKeyExW
0x18000cf05  mov     rcx, [rsp+38h]
0x18000cf0a  test    eax, eax
0x18000cf0c  jz      short loc_18000CF15
0x18000cf0e  mov     edx, 432h
0x18000cf13  jmp     short loc_18000CF4B
0x18000cf15  mov     [rsp+38h+cbData], 0Ch; cbData
0x18000cf1d  mov     [rsp+38h+phkResult], rdi; unsigned int
0x18000cf22  mov     r9d, 3; dwType
0x18000cf28  xor     r8d, r8d; Reserved
0x18000cf2b  lea     rdx, aHealthevaluati; "HealthEvaluation"
0x18000cf32  mov     rcx, [rsp+38h+hKey]; hKey
0x18000cf37  call    cs:__imp_RegSetValueExW
0x18000cf3d  mov     rcx, [rsp+38h]; this
0x18000cf42  test    eax, eax
0x18000cf44  jz      short loc_18000CF5A
0x18000cf46  mov     edx, 435h; void *
0x18000cf4b  mov     r9d, eax; char *
0x18000cf4e  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000cf55  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000cf5a  lea     rcx, [rsp+38h+hKey]
0x18000cf5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000cf64  mov     byte ptr [rbx], 0
0x18000cf67  lea     rcx, [rsp+38h+lpSubKey]
0x18000cf6c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000cf71  mov     rbx, [rsp+38h+arg_8]
0x18000cf76  add     rsp, 30h
0x18000cf7a  pop     rdi
0x18000cf7b  retn
```
