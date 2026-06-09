# IpTlsReadProfilesUrlAndName

- ea: `0x180068494`
- end: `0x1800686aa`
- name: `IpTlsReadProfilesUrlAndName`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800613e4`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x18004b5f0`
- `0x180068494`
- `0x1800769f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800685dd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800685dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068663`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068663`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068679`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068534`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068583`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068534`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068583`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800684fd`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800684fd`

## string_xrefs

- `0x180068550`: `RegOpenKeyEx: Key = %s: Status = %d`

## pseudocode

```c
__int64 __fastcall IpTlsReadProfilesUrlAndName(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int String2; // eax
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  LPWSTR lpClassa; // [rsp+28h] [rbp-D8h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD phkResult[3]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF

  *a2 = 0;
  *a3 = 0;
  hKey = 0;
  memset(phkResult, 0, sizeof(phkResult));
  cchName = 0;
  v4 = ConvertGuidToStringW(a1, SubKey, 39);
  if ( !v4 )
  {
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Policies\\Microsoft\\Windows\\Tcpip\\v6Transition\\IPHTTPSProfiles",
           0,
           0x20019u,
           &hKey);
    v4 = v5;
    if ( v5 )
    {
      EventWrite0(
        0x10000000,
        L"RegOpenKeyEx: Key = %s: Status = %d",
        L"SOFTWARE\\Policies\\Microsoft\\Windows\\Tcpip\\v6Transition\\IPHTTPSProfiles",
        v5);
    }
    else
    {
      v4 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, (PHKEY)&phkResult[1]);
      if ( !v4 )
      {
        while ( !v4 )
        {
          cchName = 260;
          v4 = RegEnumKeyExW(*(HKEY *)&phkResult[1], 0, Name, &cchName, 0, 0, 0, 0);
          if ( !v4 )
          {
            String2 = GetString2(*(HKEY *)&phkResult[1], (__int64)phkResult, (HKEY)lpClass);
            v4 = String2;
            if ( String2 != 1168 )
            {
              if ( !String2 )
              {
                v4 = GetString2(*(HKEY *)&phkResult[1], (__int64)phkResult, (HKEY)lpClassa);
                if ( v4 )
                {
                  FREE(*a2);
                  *a2 = 0;
                }
              }
              break;
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( *(_QWORD *)&phkResult[1] )
    RegCloseKey(*(HKEY *)&phkResult[1]);
  return v4;
}

```

## disassembly

```asm
0x180068494  mov     [rsp-8+arg_18], rbx
0x180068499  push    rbp
0x18006849a  push    rsi
0x18006849b  push    rdi
0x18006849c  lea     rbp, [rsp-1D0h]
0x1800684a4  sub     rsp, 2D0h
0x1800684ab  mov     rax, cs:__security_cookie
0x1800684b2  xor     rax, rsp
0x1800684b5  mov     [rbp+1E0h+var_20], rax
0x1800684bc  mov     qword ptr [rdx], 0
0x1800684c3  mov     rsi, r8
0x1800684c6  mov     qword ptr [r8], 0
0x1800684cd  mov     rdi, rdx
0x1800684d0  mov     r8d, 27h ; '''
0x1800684d6  mov     [rsp+2E0h+hKey], 0
0x1800684df  lea     rdx, [rsp+2E0h+SubKey]
0x1800684e4  mov     dword ptr [rsp+2E0h+var_29C], 0
0x1800684ec  mov     [rsp+2E0h+cchName], 0
0x1800684f4  mov     qword ptr [rsp+2E0h+var_29C+4], 0
0x1800684fd  call    cs:__imp_ConvertGuidToStringW
0x180068504  nop     dword ptr [rax+rax+00h]
0x180068509  mov     ebx, eax
0x18006850b  test    eax, eax
0x18006850d  jnz     loc_180068659
0x180068513  lea     rax, [rsp+2E0h+hKey]
0x180068518  mov     r9d, 20019h; samDesired
0x18006851e  xor     r8d, r8d; ulOptions
0x180068521  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180068526  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18006852d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068534  call    cs:__imp_RegOpenKeyExW
0x18006853b  nop     dword ptr [rax+rax+00h]
0x180068540  mov     ebx, eax
0x180068542  test    eax, eax
0x180068544  jz      short loc_180068566
0x180068546  mov     r9d, eax
0x180068549  lea     r8, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180068550  lea     rdx, aRegopenkeyexKe; "RegOpenKeyEx: Key = %s: Status = %d"
0x180068557  mov     ecx, 10000000h
0x18006855c  call    EventWrite0
0x180068561  jmp     loc_180068659
0x180068566  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18006856b  lea     rax, [rsp+2E0h+var_29C+4]
0x180068570  mov     r9d, 20019h; samDesired
0x180068576  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18006857b  xor     r8d, r8d; ulOptions
0x18006857e  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180068583  call    cs:__imp_RegOpenKeyExW
0x18006858a  nop     dword ptr [rax+rax+00h]
0x18006858f  mov     ebx, eax
0x180068591  test    eax, eax
0x180068593  jnz     loc_180068659
0x180068599  test    ebx, ebx
0x18006859b  jnz     loc_180068659
0x1800685a1  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x1800685a6  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800685ab  mov     [rsp+2E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800685b4  lea     r8, [rbp+1E0h+Name]; lpName
0x1800685b8  mov     [rsp+2E0h+lpcchClass], 0; lpcchClass
0x1800685c1  xor     edx, edx; dwIndex
0x1800685c3  mov     [rsp+2E0h+lpClass], 0; HKEY
0x1800685cc  mov     [rsp+2E0h+phkResult], 0; lpReserved
0x1800685d5  mov     [rsp+2E0h+cchName], 104h
0x1800685dd  call    cs:__imp_RegEnumKeyExW
0x1800685e4  nop     dword ptr [rax+rax+00h]
0x1800685e9  mov     ebx, eax
0x1800685eb  test    eax, eax
0x1800685ed  jnz     short loc_180068599
0x1800685ef  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x1800685f4  lea     rax, [rsp+2E0h+var_29C]
0x1800685f9  mov     r9, rdi
0x1800685fc  mov     [rsp+2E0h+phkResult], rax; __int64
0x180068601  lea     r8, aIphttpsClientu; "IPHTTPS_ClientUrl"
0x180068608  lea     rdx, [rbp+1E0h+Name]
0x18006860c  call    GetString2
0x180068611  mov     ebx, eax
0x180068613  cmp     eax, 490h
0x180068618  jz      loc_180068599
0x18006861e  test    eax, eax
0x180068620  jnz     short loc_180068659
0x180068622  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x180068627  lea     rax, [rsp+2E0h+var_29C]
0x18006862c  mov     r9, rsi
0x18006862f  mov     [rsp+2E0h+phkResult], rax; __int64
0x180068634  lea     r8, aIphttpsProfile; "IPHTTPS_ProfileName"
0x18006863b  lea     rdx, [rbp+1E0h+Name]
0x18006863f  call    GetString2
0x180068644  mov     ebx, eax
0x180068646  test    eax, eax
0x180068648  jz      short loc_180068659
0x18006864a  mov     rcx, [rdi]
0x18006864d  call    FREE
0x180068652  mov     qword ptr [rdi], 0
0x180068659  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18006865e  test    rcx, rcx
0x180068661  jz      short loc_18006866F
0x180068663  call    cs:__imp_RegCloseKey
0x18006866a  nop     dword ptr [rax+rax+00h]
0x18006866f  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x180068674  test    rcx, rcx
0x180068677  jz      short loc_180068685
0x180068679  call    cs:__imp_RegCloseKey
0x180068680  nop     dword ptr [rax+rax+00h]
0x180068685  mov     eax, ebx
0x180068687  mov     rcx, [rbp+1E0h+var_20]
0x18006868e  xor     rcx, rsp; StackCookie
0x180068691  call    __security_check_cookie
0x180068696  mov     rbx, [rsp+2E0h+arg_18]
0x18006869e  add     rsp, 2D0h
0x1800686a5  pop     rdi
0x1800686a6  pop     rsi
0x1800686a7  pop     rbp
0x1800686a8  retn
```
