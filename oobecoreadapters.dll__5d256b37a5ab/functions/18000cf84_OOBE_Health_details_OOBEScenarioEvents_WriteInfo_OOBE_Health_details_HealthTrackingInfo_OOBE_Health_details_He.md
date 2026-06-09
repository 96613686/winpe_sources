# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x18000cf84`
- end: `0x18000d0b4`
- name: `??$WriteInfo@UHealthTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthTrackingInfo@123@AEA_N2PEBG@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cc0c`
- `0x18000cc90`
- `0x18000d7f8`

## callees

- `0x180009814`
- `0x180009834`
- `0x18000b098`
- `0x18000b0c8`
- `0x18000b200`
- `0x18000b254`
- `0x18000cf84`
- `0x18000ef04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d06f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d06f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d037`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d037`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(
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
      v9 = RegSetValueExW(hKey, L"Health", 0, 3u, a2, 0xACu);
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
0x18000cf84  mov     r11, rsp
0x18000cf87  mov     [r11+10h], rbx
0x18000cf8b  mov     [r11+18h], r8
0x18000cf8f  mov     [r11+8], rcx
0x18000cf93  push    rdi
0x18000cf94  sub     rsp, 30h
0x18000cf98  mov     rbx, r9
0x18000cf9b  mov     rdi, rdx
0x18000cf9e  mov     rax, [rsp+38h+arg_20]
0x18000cfa3  cmp     byte ptr [rax], 0
0x18000cfa6  jz      loc_18000D0A9
0x18000cfac  cmp     byte ptr [r9], 0
0x18000cfb0  jz      loc_18000D0A9
0x18000cfb6  mov     qword ptr [r11+8], 0
0x18000cfbe  xor     edx, edx
0x18000cfc0  lea     rcx, [r11+8]
0x18000cfc4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000cfc9  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x18000cfce  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cfd5  lea     rcx, aOobehealth; "OOBEHealth"
0x18000cfdc  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x18000cfe1  mov     rcx, [rsp+38h]; this
0x18000cfe6  test    eax, eax
0x18000cfe8  jns     short loc_18000D003
0x18000cfea  mov     r9d, eax; char *
0x18000cfed  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000cff4  mov     edx, 42Fh; void *
0x18000cff9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000cffe  jmp     loc_18000D09C
0x18000d003  mov     [rsp+38h+hKey], 0
0x18000d00c  xor     edx, edx
0x18000d00e  lea     rcx, [rsp+38h+hKey]
0x18000d013  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000d018  lea     rax, [rsp+38h+hKey]
0x18000d01d  mov     [rsp+38h+phkResult], rax; phkResult
0x18000d022  mov     r9d, 0F003Fh; samDesired
0x18000d028  xor     r8d, r8d; ulOptions
0x18000d02b  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x18000d030  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d037  call    cs:__imp_RegOpenKeyExW
0x18000d03d  mov     rcx, [rsp+38h]
0x18000d042  test    eax, eax
0x18000d044  jz      short loc_18000D04D
0x18000d046  mov     edx, 432h
0x18000d04b  jmp     short loc_18000D083
0x18000d04d  mov     [rsp+38h+cbData], 0ACh; cbData
0x18000d055  mov     [rsp+38h+phkResult], rdi; unsigned int
0x18000d05a  mov     r9d, 3; dwType
0x18000d060  xor     r8d, r8d; Reserved
0x18000d063  lea     rdx, aHealth; "Health"
0x18000d06a  mov     rcx, [rsp+38h+hKey]; hKey
0x18000d06f  call    cs:__imp_RegSetValueExW
0x18000d075  mov     rcx, [rsp+38h]; this
0x18000d07a  test    eax, eax
0x18000d07c  jz      short loc_18000D092
0x18000d07e  mov     edx, 435h; void *
0x18000d083  mov     r9d, eax; char *
0x18000d086  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x18000d08d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000d092  lea     rcx, [rsp+38h+hKey]
0x18000d097  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000d09c  mov     byte ptr [rbx], 0
0x18000d09f  lea     rcx, [rsp+38h+lpSubKey]
0x18000d0a4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000d0a9  mov     rbx, [rsp+38h+arg_8]
0x18000d0ae  add     rsp, 30h
0x18000d0b2  pop     rdi
0x18000d0b3  retn
```
