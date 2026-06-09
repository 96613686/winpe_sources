# NgcStatusStorage::UpdateNgcCertEnrollStatistics(long)

- ea: `0x180035218`
- end: `0x18003538a`
- name: `?UpdateNgcCertEnrollStatistics@NgcStatusStorage@@SAJJ@Z`
- size: `370`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ab90`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18001c74c`
- `0x180035218`
- `0x180043e54`
- `0x18008c2d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035298`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003533a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035353`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003533a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035353`

## string_xrefs

- `0x1800352fa`: `NgcStatusStorage::UpdateNgcCertEnrollStatistics`
- `0x18003531a`: `NgcStatusStorage::UpdateNgcCertEnrollStatistics`
- `0x180035365`: `NgcStatusStorage::UpdateNgcCertEnrollStatistics`
- `0x18003524e`: `OpenRootKey`
- `0x1800352b0`: `RegCreateKeyExW`
- `0x1800352bc`: `%s: Failed to create or open registry key "%s". Error code: 0x%08x.`
- `0x180035324`: `%s: Updated NGC cert enrollment statistics. lastCertEnrollResult = 0x%08x.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::UpdateNgcCertEnrollStatistics(unsigned int a1)
{
  unsigned int v2; // ebx
  const wchar_t *v3; // rdi
  LSTATUS v4; // eax
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  phkResult = 0;
  hKey = 0;
  v2 = RegOpenCurrentUserKey(0x20006u, &hKey);
  if ( v2 )
  {
    v3 = L"OpenRootKey";
  }
  else
  {
    v4 = RegCreateKeyExW(
           hKey,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &phkResult,
           0);
    v2 = v4;
    if ( v4 )
    {
      Logger::WriteRegistryFailureEvent(
        v4,
        L"RegCreateKeyExW",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      Logger::TraceError(
        L"%s: Failed to create or open registry key \"%s\". Error code: 0x%08x.",
        L"NgcStatusStorage::UpdateNgcCertEnrollStatistics",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        v2);
      goto LABEL_8;
    }
    v2 = RegSaveDwordValue(
           phkResult,
           0,
           L"LastCertEnrollResult",
           L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           a1);
    if ( !v2 )
    {
      v2 = 0;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Updated NGC cert enrollment statistics. lastCertEnrollResult = 0x%08x.",
        L"NgcStatusStorage::UpdateNgcCertEnrollStatistics",
        a1);
      goto LABEL_11;
    }
    v3 = L"RegSaveDwordValue";
  }
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"NgcStatusStorage::UpdateNgcCertEnrollStatistics",
    v3,
    v2);
LABEL_8:
  if ( (int)v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
LABEL_11:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcStatusStorage::UpdateNgcCertEnrollStatistics", v2);
  return v2;
}

```

## disassembly

```asm
0x180035218  mov     rax, rsp
0x18003521b  mov     [rax+8], rbx
0x18003521f  mov     [rax+20h], rsi
0x180035223  push    rdi
0x180035224  sub     rsp, 50h
0x180035228  mov     esi, ecx
0x18003522a  mov     qword ptr [rax+10h], 0
0x180035232  mov     ecx, 20006h; unsigned int
0x180035237  mov     qword ptr [rax+18h], 0
0x18003523f  lea     rdx, [rax+18h]; HKEY *
0x180035243  call    ?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z; RegOpenCurrentUserKey(ulong,HKEY__ * *)
0x180035248  mov     ebx, eax
0x18003524a  test    eax, eax
0x18003524c  jz      short loc_18003525A
0x18003524e  lea     rdi, aOpenrootkey; "OpenRootKey"
0x180035255  jmp     loc_1800352F0
0x18003525a  mov     rcx, [rsp+58h+hKey]; hKey
0x18003525f  lea     rax, [rsp+58h+arg_8]
0x180035264  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18003526d  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180035274  mov     [rsp+58h+phkResult], rax; phkResult
0x180035279  xor     r9d, r9d; lpClass
0x18003527c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180035285  xor     r8d, r8d; Reserved
0x180035288  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180035290  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180035298  call    cs:__imp_RegCreateKeyExW
0x18003529e  mov     ebx, eax
0x1800352a0  test    eax, eax
0x1800352a2  jz      short loc_1800352C5
0x1800352a4  lea     rdi, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800352ab  mov     ecx, eax; unsigned int
0x1800352ad  mov     r8, rdi; unsigned __int16 *
0x1800352b0  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x1800352b7  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800352bc  lea     rcx, aSFailedToCreat_0; "%s: Failed to create or open registry k"...
0x1800352c3  jmp     short loc_1800352F7
0x1800352c5  mov     rcx, [rsp+58h+arg_8]; HKEY
0x1800352ca  lea     r9, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800352d1  lea     r8, aLastcertenroll; "LastCertEnrollResult"
0x1800352d8  mov     [rsp+58h+dwOptions], esi; unsigned int
0x1800352dc  xor     edx, edx; unsigned __int16 *
0x1800352de  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x1800352e3  mov     ebx, eax
0x1800352e5  test    eax, eax
0x1800352e7  jz      short loc_180035318
0x1800352e9  lea     rdi, aRegsavedwordva; "RegSaveDwordValue"
0x1800352f0  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800352f7  mov     r9d, ebx
0x1800352fa  lea     rdx, aNgcstatusstora_1; "NgcStatusStorage::UpdateNgcCertEnrollSt"...
0x180035301  mov     r8, rdi
0x180035304  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180035309  test    ebx, ebx
0x18003530b  jle     short loc_180035330
0x18003530d  movzx   ebx, bx
0x180035310  or      ebx, 80070000h
0x180035316  jmp     short loc_180035330
0x180035318  xor     ebx, ebx
0x18003531a  lea     rdx, aNgcstatusstora_1; "NgcStatusStorage::UpdateNgcCertEnrollSt"...
0x180035321  mov     r8d, esi
0x180035324  lea     rcx, aSUpdatedNgcCer; "%s: Updated NGC cert enrollment statist"...
0x18003532b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180035330  mov     rcx, [rsp+58h+arg_8]; hKey
0x180035335  test    rcx, rcx
0x180035338  jz      short loc_180035349
0x18003533a  call    cs:__imp_RegCloseKey
0x180035340  mov     [rsp+58h+arg_8], 0
0x180035349  mov     rcx, [rsp+58h+hKey]; hKey
0x18003534e  test    rcx, rcx
0x180035351  jz      short loc_180035362
0x180035353  call    cs:__imp_RegCloseKey
0x180035359  mov     [rsp+58h+hKey], 0
0x180035362  mov     r8d, ebx
0x180035365  lea     rdx, aNgcstatusstora_1; "NgcStatusStorage::UpdateNgcCertEnrollSt"...
0x18003536c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180035373  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180035378  mov     rsi, [rsp+58h+arg_18]
0x18003537d  mov     eax, ebx
0x18003537f  mov     rbx, [rsp+58h+arg_0]
0x180035384  add     rsp, 50h
0x180035388  pop     rdi
0x180035389  retn
```
