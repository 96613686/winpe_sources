# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::CensusTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x18000cd14`
- end: `0x18000ce44`
- name: `??$WriteInfo@UCensusTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUCensusTrackingInfo@123@AEA_N2PEBG@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d7f8`

## callees

- `0x180009814`
- `0x180009834`
- `0x18000b098`
- `0x18000b0c8`
- `0x18000b200`
- `0x18000b254`
- `0x18000cd14`
- `0x18000ef04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cdff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cdff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cdc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cdc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(
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
      v9 = RegSetValueExW(hKey, L"Census", 0, 3u, a2, 0x10u);
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
0x18000cd14  mov     r11, rsp
0x18000cd17  mov     [r11+10h], rbx
0x18000cd1b  mov     [r11+18h], r8
0x18000cd1f  mov     [r11+8], rcx
0x18000cd23  push    rdi
0x18000cd24  sub     rsp, 30h
0x18000cd28  mov     rbx, r9
0x18000cd2b  mov     rdi, rdx
0x18000cd2e  mov     rax, [rsp+38h+arg_20]
0x18000cd33  cmp     byte ptr [rax], 0
0x18000cd36  jz      loc_18000CE39
0x18000cd3c  cmp     byte ptr [r9], 0
0x18000cd40  jz      loc_18000CE39
0x18000cd46  mov     qword ptr [r11+8], 0
0x18000cd4e  xor     edx, edx
0x18000cd50  lea     rcx, [r11+8]
0x18000cd54  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000cd59  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x18000cd5e  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cd65  lea     rcx, aOobehealth; "OOBEHealth"
0x18000cd6c  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x18000cd71  mov     rcx, [rsp+38h]; this
0x18000cd76  test    eax, eax
0x18000cd78  jns     short loc_18000CD93
0x18000cd7a  mov     r9d, eax; char *
0x18000cd7d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000cd84  mov     edx, 42Fh; void *
0x18000cd89  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cd8e  jmp     loc_18000CE2C
0x18000cd93  mov     [rsp+38h+hKey], 0
0x18000cd9c  xor     edx, edx
0x18000cd9e  lea     rcx, [rsp+38h+hKey]
0x18000cda3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000cda8  lea     rax, [rsp+38h+hKey]
0x18000cdad  mov     [rsp+38h+phkResult], rax; phkResult
0x18000cdb2  mov     r9d, 0F003Fh; samDesired
0x18000cdb8  xor     r8d, r8d; ulOptions
0x18000cdbb  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x18000cdc0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cdc7  call    cs:__imp_RegOpenKeyExW
0x18000cdcd  mov     rcx, [rsp+38h]
0x18000cdd2  test    eax, eax
0x18000cdd4  jz      short loc_18000CDDD
0x18000cdd6  mov     edx, 432h
0x18000cddb  jmp     short loc_18000CE13
0x18000cddd  mov     [rsp+38h+cbData], 10h; cbData
0x18000cde5  mov     [rsp+38h+phkResult], rdi; unsigned int
0x18000cdea  mov     r9d, 3; dwType
0x18000cdf0  xor     r8d, r8d; Reserved
0x18000cdf3  lea     rdx, ValueName; "Census"
0x18000cdfa  mov     rcx, [rsp+38h+hKey]; hKey
0x18000cdff  call    cs:__imp_RegSetValueExW
0x18000ce05  mov     rcx, [rsp+38h]; this
0x18000ce0a  test    eax, eax
0x18000ce0c  jz      short loc_18000CE22
0x18000ce0e  mov     edx, 435h; void *
0x18000ce13  mov     r9d, eax; char *
0x18000ce16  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000ce1d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000ce22  lea     rcx, [rsp+38h+hKey]
0x18000ce27  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ce2c  mov     byte ptr [rbx], 0
0x18000ce2f  lea     rcx, [rsp+38h+lpSubKey]
0x18000ce34  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ce39  mov     rbx, [rsp+38h+arg_8]
0x18000ce3e  add     rsp, 30h
0x18000ce42  pop     rdi
0x18000ce43  retn
```
