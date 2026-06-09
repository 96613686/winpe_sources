# NgcStatusStorage::UpdateNgcStatistics(long)

- ea: `0x18003ae14`
- end: `0x18003b030`
- name: `?UpdateNgcStatistics@NgcStatusStorage@@SAJJ@Z`
- size: `540`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004aba0`
- `0x1800813fc`

## callees

- `0x1800065d0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18001c74c`
- `0x18003ae14`
- `0x180043e54`
- `0x18005b3f4`
- `0x18008c2d4`
- `0x18008c364`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ae98`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ae98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aff6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aff6`

## string_xrefs

- `0x18003af54`: `NgcStatusStorage::UpdateNgcStatistics`
- `0x18003af98`: `NgcStatusStorage::UpdateNgcStatistics`
- `0x18003afc0`: `NgcStatusStorage::UpdateNgcStatistics`
- `0x18003b007`: `NgcStatusStorage::UpdateNgcStatistics`
- `0x18003ae5c`: `OpenRootKey`
- `0x18003aeae`: `RegCreateKeyExW`
- `0x18003aebc`: `%s: Failed to create or open registry key "%s". Error code: 0x%08x.`
- `0x18003af6b`: `LastAttemptTime`
- `0x18003afca`: `%s: Updated NGC statistics. lastError = %lu, numberOfFailures = %lu, lastAttemptTime = %lld.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::UpdateNgcStatistics(int a1)
{
  unsigned int v1; // r15d
  unsigned int v3; // esi
  unsigned int v4; // ebx
  const wchar_t *v5; // rdi
  LSTATUS v6; // eax
  time_t v7; // r14
  unsigned int v9; // [rsp+80h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v1 = 0;
  phkResult = 0;
  hKey = 0;
  if ( a1 < 0 )
    v1 = a1;
  v3 = 0;
  v9 = 0;
  v4 = RegOpenCurrentUserKey(0x20006u, &hKey);
  if ( v4 )
  {
    v5 = L"OpenRootKey";
  }
  else
  {
    v6 = RegCreateKeyExW(
           hKey,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &phkResult,
           0);
    v4 = v6;
    if ( v6 )
    {
      Logger::WriteRegistryFailureEvent(
        v6,
        L"RegCreateKeyExW",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      Logger::TraceError(
        L"%s: Failed to create or open registry key \"%s\". Error code: 0x%08x.",
        L"NgcStatusStorage::UpdateNgcStatistics",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        v4);
      goto LABEL_17;
    }
    v4 = RegSaveDwordValue(
           phkResult,
           0,
           L"LastError",
           L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
           v1);
    if ( v4
      || a1 < 0
      && ((v4 = RegReadDwordValue(
                  phkResult,
                  0,
                  L"NumOfFailures",
                  L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                  &v9,
                  0)) != 0
       || (v3 = v9 + 1,
           (v4 = RegSaveDwordValue(
                   phkResult,
                   0,
                   L"NumOfFailures",
                   L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                   v9 + 1)) != 0)) )
    {
      v5 = L"RegSaveDwordValue";
    }
    else
    {
      v7 = time(0);
      if ( v7 < 0 )
        Logger::TraceError(L"%s: Cannot get system time. time() returned -1.", L"NgcStatusStorage::UpdateNgcStatistics");
      v4 = RegSaveQwordValue(
             phkResult,
             0,
             L"LastAttemptTime",
             L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
             v7);
      if ( !v4 )
      {
        v4 = 0;
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Updated NGC statistics. lastError = %lu, numberOfFailures = %lu, lastAttemptTime = %lld.",
          L"NgcStatusStorage::UpdateNgcStatistics",
          v1,
          v3,
          v7);
        goto LABEL_20;
      }
      v5 = L"RegSaveQwordValue";
    }
  }
  Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::UpdateNgcStatistics", v5, v4);
LABEL_17:
  if ( (int)v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_20:
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
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcStatusStorage::UpdateNgcStatistics", v4);
  return v4;
}

```

## disassembly

```asm
0x18003ae14  mov     [rsp-28h+arg_18], rbx
0x18003ae19  push    rbp
0x18003ae1a  push    rsi
0x18003ae1b  push    rdi
0x18003ae1c  push    r14
0x18003ae1e  push    r15
0x18003ae20  mov     rbp, rsp
0x18003ae23  sub     rsp, 50h
0x18003ae27  xor     r15d, r15d
0x18003ae2a  mov     [rbp+arg_8], 0
0x18003ae32  test    ecx, ecx
0x18003ae34  mov     [rbp+hKey], 0
0x18003ae3c  mov     r14d, ecx
0x18003ae3f  lea     rdx, [rbp+hKey]; HKEY *
0x18003ae43  cmovs   r15d, ecx
0x18003ae47  xor     esi, esi
0x18003ae49  mov     ecx, 20006h; unsigned int
0x18003ae4e  mov     [rbp+arg_0], esi
0x18003ae51  call    ?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z; RegOpenCurrentUserKey(ulong,HKEY__ * *)
0x18003ae56  mov     ebx, eax
0x18003ae58  test    eax, eax
0x18003ae5a  jz      short loc_18003AE68
0x18003ae5c  lea     rdi, aOpenrootkey; "OpenRootKey"
0x18003ae63  jmp     loc_18003AF8E
0x18003ae68  mov     rcx, [rbp+hKey]; hKey
0x18003ae6c  lea     rax, [rbp+arg_8]
0x18003ae70  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x18003ae75  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003ae7c  mov     [rsp+50h+phkResult], rax; phkResult
0x18003ae81  xor     r9d, r9d; lpClass
0x18003ae84  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18003ae89  xor     r8d, r8d; Reserved
0x18003ae8c  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18003ae94  mov     [rsp+50h+dwOptions], esi; dwOptions
0x18003ae98  call    cs:__imp_RegCreateKeyExW
0x18003ae9e  lea     rdi, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x18003aea5  mov     ebx, eax
0x18003aea7  test    eax, eax
0x18003aea9  jz      short loc_18003AEC8
0x18003aeab  mov     r8, rdi; unsigned __int16 *
0x18003aeae  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18003aeb5  mov     ecx, eax; unsigned int
0x18003aeb7  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18003aebc  lea     rcx, aSFailedToCreat_0; "%s: Failed to create or open registry k"...
0x18003aec3  jmp     loc_18003AF95
0x18003aec8  mov     rcx, [rbp+arg_8]; HKEY
0x18003aecc  lea     r8, aLasterror; "LastError"
0x18003aed3  mov     r9, rdi; unsigned __int16 *
0x18003aed6  mov     [rsp+50h+dwOptions], r15d; unsigned int
0x18003aedb  xor     edx, edx; unsigned __int16 *
0x18003aedd  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18003aee2  mov     ebx, eax
0x18003aee4  test    eax, eax
0x18003aee6  jz      short loc_18003AEF4
0x18003aee8  lea     rdi, aRegsavedwordva; "RegSaveDwordValue"
0x18003aeef  jmp     loc_18003AF8E
0x18003aef4  test    r14d, r14d
0x18003aef7  jns     short loc_18003AF45
0x18003aef9  mov     rcx, [rbp+arg_8]; HKEY
0x18003aefd  lea     rax, [rbp+arg_0]
0x18003af01  mov     [rsp+50h+samDesired], esi; unsigned int
0x18003af05  lea     r8, aNumoffailures; "NumOfFailures"
0x18003af0c  mov     r9, rdi; unsigned __int16 *
0x18003af0f  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned int *
0x18003af14  xor     edx, edx; unsigned __int16 *
0x18003af16  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18003af1b  mov     ebx, eax
0x18003af1d  test    eax, eax
0x18003af1f  jnz     short loc_18003AEE8
0x18003af21  mov     esi, [rbp+arg_0]
0x18003af24  lea     r8, aNumoffailures; "NumOfFailures"
0x18003af2b  mov     rcx, [rbp+arg_8]; HKEY
0x18003af2f  inc     esi
0x18003af31  mov     r9, rdi; unsigned __int16 *
0x18003af34  mov     [rsp+50h+dwOptions], esi; unsigned int
0x18003af38  xor     edx, edx; unsigned __int16 *
0x18003af3a  call    ?RegSaveDwordValue@@YAKPEAUHKEY__@@PEBG11K@Z; RegSaveDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x18003af3f  mov     ebx, eax
0x18003af41  test    eax, eax
0x18003af43  jnz     short loc_18003AEE8
0x18003af45  xor     ecx, ecx; Time
0x18003af47  call    time
0x18003af4c  mov     r14, rax
0x18003af4f  test    rax, rax
0x18003af52  jns     short loc_18003AF67
0x18003af54  lea     rdx, aNgcstatusstora_11; "NgcStatusStorage::UpdateNgcStatistics"
0x18003af5b  lea     rcx, aSCannotGetSyst; "%s: Cannot get system time. time() retu"...
0x18003af62  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003af67  mov     rcx, [rbp+arg_8]; HKEY
0x18003af6b  lea     r8, aLastattempttim; "LastAttemptTime"
0x18003af72  mov     r9, rdi; unsigned __int16 *
0x18003af75  mov     qword ptr [rsp+50h+dwOptions], r14; __int64
0x18003af7a  xor     edx, edx; unsigned __int16 *
0x18003af7c  call    ?RegSaveQwordValue@@YAKPEAUHKEY__@@PEBG11_J@Z; RegSaveQwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,__int64)
0x18003af81  mov     ebx, eax
0x18003af83  test    eax, eax
0x18003af85  jz      short loc_18003AFB6
0x18003af87  lea     rdi, aRegsaveqwordva; "RegSaveQwordValue"
0x18003af8e  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18003af95  mov     r9d, ebx
0x18003af98  lea     rdx, aNgcstatusstora_11; "NgcStatusStorage::UpdateNgcStatistics"
0x18003af9f  mov     r8, rdi
0x18003afa2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003afa7  test    ebx, ebx
0x18003afa9  jle     short loc_18003AFD6
0x18003afab  movzx   ebx, bx
0x18003afae  or      ebx, 80070000h
0x18003afb4  jmp     short loc_18003AFD6
0x18003afb6  xor     ebx, ebx
0x18003afb8  mov     qword ptr [rsp+50h+dwOptions], r14
0x18003afbd  mov     r9d, esi
0x18003afc0  lea     rdx, aNgcstatusstora_11; "NgcStatusStorage::UpdateNgcStatistics"
0x18003afc7  mov     r8d, r15d
0x18003afca  lea     rcx, aSUpdatedNgcSta; "%s: Updated NGC statistics. lastError ="...
0x18003afd1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003afd6  mov     rcx, [rbp+arg_8]; hKey
0x18003afda  test    rcx, rcx
0x18003afdd  jz      short loc_18003AFED
0x18003afdf  call    cs:__imp_RegCloseKey
0x18003afe5  mov     [rbp+arg_8], 0
0x18003afed  mov     rcx, [rbp+hKey]; hKey
0x18003aff1  test    rcx, rcx
0x18003aff4  jz      short loc_18003B004
0x18003aff6  call    cs:__imp_RegCloseKey
0x18003affc  mov     [rbp+hKey], 0
0x18003b004  mov     r8d, ebx
0x18003b007  lea     rdx, aNgcstatusstora_11; "NgcStatusStorage::UpdateNgcStatistics"
0x18003b00e  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18003b015  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003b01a  mov     eax, ebx
0x18003b01c  mov     rbx, [rsp+50h+arg_18]
0x18003b024  add     rsp, 50h
0x18003b028  pop     r15
0x18003b02a  pop     r14
0x18003b02c  pop     rdi
0x18003b02d  pop     rsi
0x18003b02e  pop     rbp
0x18003b02f  retn
```
