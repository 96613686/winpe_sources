# IpTlsReadProfilesUrlAndName

- ea: `0x180068474`
- end: `0x18006868a`
- name: `IpTlsReadProfilesUrlAndName`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800613c4`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x18004b630`
- `0x180068474`
- `0x1800769d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800685bd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800685bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068643`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068659`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068643`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068659`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068563`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068563`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800684dd`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800684dd`

## string_xrefs

- `0x180068530`: `RegOpenKeyEx: Key = %s: Status = %d`

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
0x180068474  mov     [rsp-8+arg_18], rbx
0x180068479  push    rbp
0x18006847a  push    rsi
0x18006847b  push    rdi
0x18006847c  lea     rbp, [rsp-1D0h]
0x180068484  sub     rsp, 2D0h
0x18006848b  mov     rax, cs:__security_cookie
0x180068492  xor     rax, rsp
0x180068495  mov     [rbp+1E0h+var_20], rax
0x18006849c  mov     qword ptr [rdx], 0
0x1800684a3  mov     rsi, r8
0x1800684a6  mov     qword ptr [r8], 0
0x1800684ad  mov     rdi, rdx
0x1800684b0  mov     r8d, 27h ; '''
0x1800684b6  mov     [rsp+2E0h+hKey], 0
0x1800684bf  lea     rdx, [rsp+2E0h+SubKey]
0x1800684c4  mov     dword ptr [rsp+2E0h+var_29C], 0
0x1800684cc  mov     [rsp+2E0h+cchName], 0
0x1800684d4  mov     qword ptr [rsp+2E0h+var_29C+4], 0
0x1800684dd  call    cs:__imp_ConvertGuidToStringW
0x1800684e4  nop     dword ptr [rax+rax+00h]
0x1800684e9  mov     ebx, eax
0x1800684eb  test    eax, eax
0x1800684ed  jnz     loc_180068639
0x1800684f3  lea     rax, [rsp+2E0h+hKey]
0x1800684f8  mov     r9d, 20019h; samDesired
0x1800684fe  xor     r8d, r8d; ulOptions
0x180068501  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180068506  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18006850d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068514  call    cs:__imp_RegOpenKeyExW
0x18006851b  nop     dword ptr [rax+rax+00h]
0x180068520  mov     ebx, eax
0x180068522  test    eax, eax
0x180068524  jz      short loc_180068546
0x180068526  mov     r9d, eax
0x180068529  lea     r8, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180068530  lea     rdx, aRegopenkeyexKe; "RegOpenKeyEx: Key = %s: Status = %d"
0x180068537  mov     ecx, 10000000h
0x18006853c  call    EventWrite0
0x180068541  jmp     loc_180068639
0x180068546  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18006854b  lea     rax, [rsp+2E0h+var_29C+4]
0x180068550  mov     r9d, 20019h; samDesired
0x180068556  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18006855b  xor     r8d, r8d; ulOptions
0x18006855e  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x180068563  call    cs:__imp_RegOpenKeyExW
0x18006856a  nop     dword ptr [rax+rax+00h]
0x18006856f  mov     ebx, eax
0x180068571  test    eax, eax
0x180068573  jnz     loc_180068639
0x180068579  test    ebx, ebx
0x18006857b  jnz     loc_180068639
0x180068581  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x180068586  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x18006858b  mov     [rsp+2E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180068594  lea     r8, [rbp+1E0h+Name]; lpName
0x180068598  mov     [rsp+2E0h+lpcchClass], 0; lpcchClass
0x1800685a1  xor     edx, edx; dwIndex
0x1800685a3  mov     [rsp+2E0h+lpClass], 0; HKEY
0x1800685ac  mov     [rsp+2E0h+phkResult], 0; lpReserved
0x1800685b5  mov     [rsp+2E0h+cchName], 104h
0x1800685bd  call    cs:__imp_RegEnumKeyExW
0x1800685c4  nop     dword ptr [rax+rax+00h]
0x1800685c9  mov     ebx, eax
0x1800685cb  test    eax, eax
0x1800685cd  jnz     short loc_180068579
0x1800685cf  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x1800685d4  lea     rax, [rsp+2E0h+var_29C]
0x1800685d9  mov     r9, rdi
0x1800685dc  mov     [rsp+2E0h+phkResult], rax; __int64
0x1800685e1  lea     r8, aIphttpsClientu; "IPHTTPS_ClientUrl"
0x1800685e8  lea     rdx, [rbp+1E0h+Name]
0x1800685ec  call    GetString2
0x1800685f1  mov     ebx, eax
0x1800685f3  cmp     eax, 490h
0x1800685f8  jz      loc_180068579
0x1800685fe  test    eax, eax
0x180068600  jnz     short loc_180068639
0x180068602  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x180068607  lea     rax, [rsp+2E0h+var_29C]
0x18006860c  mov     r9, rsi
0x18006860f  mov     [rsp+2E0h+phkResult], rax; __int64
0x180068614  lea     r8, aIphttpsProfile; "IPHTTPS_ProfileName"
0x18006861b  lea     rdx, [rbp+1E0h+Name]
0x18006861f  call    GetString2
0x180068624  mov     ebx, eax
0x180068626  test    eax, eax
0x180068628  jz      short loc_180068639
0x18006862a  mov     rcx, [rdi]
0x18006862d  call    FREE
0x180068632  mov     qword ptr [rdi], 0
0x180068639  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18006863e  test    rcx, rcx
0x180068641  jz      short loc_18006864F
0x180068643  call    cs:__imp_RegCloseKey
0x18006864a  nop     dword ptr [rax+rax+00h]
0x18006864f  mov     rcx, qword ptr [rsp+2E0h+var_29C+4]; hKey
0x180068654  test    rcx, rcx
0x180068657  jz      short loc_180068665
0x180068659  call    cs:__imp_RegCloseKey
0x180068660  nop     dword ptr [rax+rax+00h]
0x180068665  mov     eax, ebx
0x180068667  mov     rcx, [rbp+1E0h+var_20]
0x18006866e  xor     rcx, rsp; StackCookie
0x180068671  call    __security_check_cookie
0x180068676  mov     rbx, [rsp+2E0h+arg_18]
0x18006867e  add     rsp, 2D0h
0x180068685  pop     rdi
0x180068686  pop     rsi
0x180068687  pop     rbp
0x180068688  retn
```
