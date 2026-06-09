# WriteUnloadTime(ushort const *)

- ea: `0x180027364`
- end: `0x1800274c3`
- name: `?WriteUnloadTime@@YAJPEBG@Z`
- size: `351`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x18000f1b0`
- `0x1800111a0`
- `0x18001fb70`
- `0x180027364`
- `0x18002d2d8`
- `0x18002e648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800273f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800273f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027429`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800274a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027429`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800274a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002743d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002743d`

## string_xrefs

- `0x1800273ba`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180027406`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180027468`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall WriteUnloadTime(LPCWCH lpString1)
{
  int ProfileListKeyNameFromSid; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+20h] BYREF

  lpSubKey = 0;
  v11 = 0;
  v12 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  v11 = -1;
  v12 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(lpString1, (unsigned __int16 **)&lpSubKey, 0);
  v3 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      phkResult);
    goto LABEL_15;
  }
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
  if ( v4 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x120,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
           (const char *)v4,
           phkResulta);
    goto LABEL_5;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = SHRegSetDWORD(hKey, 0, L"LocalProfileUnloadTimeLow", SystemTimeAsFileTime.dwLowDateTime);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 292;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)v5,
      phkResulta);
LABEL_5:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_15;
  }
  v5 = SHRegSetDWORD(hKey, 0, L"LocalProfileUnloadTimeHigh", SystemTimeAsFileTime.dwHighDateTime);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = 293;
    goto LABEL_9;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v3 = 0;
LABEL_15:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x180027364  mov     [rsp-8+arg_0], rbx
0x180027369  push    rbp
0x18002736a  mov     rbp, rsp
0x18002736d  sub     rsp, 50h
0x180027371  mov     rbx, rcx
0x180027374  mov     [rbp+lpSubKey], 0
0x18002737c  lea     rcx, [rbp+lpSubKey]
0x180027380  mov     [rbp+var_18], 0
0x180027388  mov     [rbp+var_10], 0
0x180027390  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180027395  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027399  lea     rdx, [rbp+lpSubKey]; unsigned __int16 **
0x18002739d  xor     r8d, r8d; int *
0x1800273a0  mov     [rbp+var_18], rax
0x1800273a4  mov     rcx, rbx; lpString1
0x1800273a7  mov     [rbp+var_10], rax
0x1800273ab  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x1800273b0  mov     ebx, eax
0x1800273b2  test    eax, eax
0x1800273b4  jns     short loc_1800273D3
0x1800273b6  mov     rcx, [rbp+8]; this
0x1800273ba  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800273c1  mov     r9d, eax; char *
0x1800273c4  mov     edx, 11Dh; void *
0x1800273c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800273ce  jmp     loc_1800274AD
0x1800273d3  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800273d7  lea     rax, [rbp+hKey]
0x1800273db  mov     r9d, 0F003Fh; samDesired
0x1800273e1  mov     qword ptr [rsp+50h+phkResult], rax; int
0x1800273e6  xor     r8d, r8d; ulOptions
0x1800273e9  mov     [rbp+hKey], 0
0x1800273f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800273f8  call    cs:__imp_RegOpenKeyExW
0x1800273fe  test    eax, eax
0x180027400  jz      short loc_180027431
0x180027402  mov     rcx, [rbp+8]; this
0x180027406  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002740d  mov     r9d, eax; char *
0x180027410  mov     edx, 120h; void *
0x180027415  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002741a  mov     ebx, eax
0x18002741c  mov     rcx, [rbp+hKey]; hKey
0x180027420  test    rcx, rcx
0x180027423  jz      loc_1800274AD
0x180027429  call    cs:__imp_RegCloseKey
0x18002742f  jmp     short loc_1800274AD
0x180027431  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180027435  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002743d  call    cs:__imp_GetSystemTimeAsFileTime
0x180027443  mov     r9d, [rbp+SystemTimeAsFileTime.dwLowDateTime]; unsigned int
0x180027447  lea     r8, aLocalprofileun; "LocalProfileUnloadTimeLow"
0x18002744e  mov     rcx, [rbp+hKey]; HKEY
0x180027452  xor     edx, edx; unsigned __int16 *
0x180027454  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180027459  mov     ebx, eax
0x18002745b  test    eax, eax
0x18002745d  jns     short loc_180027479
0x18002745f  mov     edx, 124h; void *
0x180027464  mov     rcx, [rbp+8]; this
0x180027468  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002746f  mov     r9d, eax; char *
0x180027472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027477  jmp     short loc_18002741C
0x180027479  mov     r9d, [rbp+SystemTimeAsFileTime.dwHighDateTime]; unsigned int
0x18002747d  lea     r8, aLocalprofileun_0; "LocalProfileUnloadTimeHigh"
0x180027484  mov     rcx, [rbp+hKey]; HKEY
0x180027488  xor     edx, edx; unsigned __int16 *
0x18002748a  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002748f  mov     ebx, eax
0x180027491  test    eax, eax
0x180027493  jns     short loc_18002749C
0x180027495  mov     edx, 125h
0x18002749a  jmp     short loc_180027464
0x18002749c  mov     rcx, [rbp+hKey]; hKey
0x1800274a0  test    rcx, rcx
0x1800274a3  jz      short loc_1800274AB
0x1800274a5  call    cs:__imp_RegCloseKey
0x1800274ab  xor     ebx, ebx
0x1800274ad  lea     rcx, [rbp+lpSubKey]
0x1800274b1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800274b6  mov     eax, ebx
0x1800274b8  mov     rbx, [rsp+50h+arg_0]
0x1800274bd  add     rsp, 50h
0x1800274c1  pop     rbp
0x1800274c2  retn
```
