# NgcStatusStorage::GetNgcStatistics(_DSREG_NGC_STATISTICS *)

- ea: `0x180094ed8`
- end: `0x180095102`
- name: `?GetNgcStatistics@NgcStatusStorage@@SAJPEAU_DSREG_NGC_STATISTICS@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct _DSREG_NGC_STATISTICS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004aa20`

## callees

- `0x1800065d0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18001b90c`
- `0x18001c74c`
- `0x1800307c4`
- `0x180043e54`
- `0x180094ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094f83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800950b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800950cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800950b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800950cf`

## string_xrefs

- `0x180095074`: `RegReadDwordValue`
- `0x180094fb9`: `RegOpenKeyExW`
- `0x180095043`: `RegReadQwordValue`
- `0x180094f5b`: `OpenRootKey`
- `0x180094fc7`: `%s: Cannot open registry key "%s". Win32 error code: 0x%08x.`
- `0x18009502f`: `LastAttemptTime`
- `0x180094f9a`: `%s: The registry key "%s" does not exist. Noting to read.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::GetNgcStatistics(struct _DSREG_NGC_STATISTICS *a1)
{
  unsigned int v2; // esi
  int DwordValue; // ebx
  const wchar_t *v4; // rdi
  LSTATUS v5; // eax
  unsigned int *v6; // r14
  __int64 v8; // [rsp+28h] [rbp-8h]
  HKEY phkResult; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  phkResult = 0;
  hKey = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcStatusStorage::GetNgcStatistics", L"pData");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"NgcStatusStorage::GetNgcStatistics", L"pData");
    goto LABEL_21;
  }
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  DwordValue = RegOpenCurrentUserKey(0x20019u, &hKey);
  if ( DwordValue )
  {
    v4 = L"OpenRootKey";
LABEL_15:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"NgcStatusStorage::GetNgcStatistics",
      v4,
      (unsigned int)DwordValue);
LABEL_16:
    if ( DwordValue > 0 )
      v2 = (unsigned __int16)DwordValue | 0x80070000;
    else
      v2 = DwordValue;
    goto LABEL_21;
  }
  v2 = 0;
  v5 = RegOpenKeyExW(
         hKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
         0,
         0x20019u,
         &phkResult);
  DwordValue = v5;
  if ( v5 == 2 )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: The registry key \"%s\" does not exist. Noting to read.",
      L"NgcStatusStorage::GetNgcStatistics",
      L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    goto LABEL_21;
  }
  if ( v5 )
  {
    Logger::WriteRegistryFailureEvent(
      v5,
      L"RegOpenKeyExW",
      L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    Logger::TraceError(
      L"%s: Cannot open registry key \"%s\". Win32 error code: 0x%08x.",
      L"NgcStatusStorage::GetNgcStatistics",
      L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
      (unsigned int)DwordValue);
    goto LABEL_16;
  }
  DwordValue = RegReadDwordValue(
                 phkResult,
                 0,
                 L"LastError",
                 L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                 (unsigned int *)a1,
                 0);
  if ( DwordValue )
    goto LABEL_14;
  DwordValue = RegReadDwordValue(
                 phkResult,
                 0,
                 L"NumOfFailures",
                 L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                 (unsigned int *)a1 + 1,
                 0);
  if ( DwordValue )
    goto LABEL_14;
  DwordValue = RegReadQwordValue(
                 phkResult,
                 0,
                 L"LastAttemptTime",
                 L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                 (__int64 *)a1 + 1,
                 v8);
  if ( DwordValue )
  {
    v4 = L"RegReadQwordValue";
    goto LABEL_15;
  }
  v6 = (unsigned int *)((char *)a1 + 16);
  DwordValue = RegReadDwordValue(
                 phkResult,
                 0,
                 L"LastCertEnrollResult",
                 L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                 v6,
                 0);
  if ( DwordValue )
  {
LABEL_14:
    v4 = L"RegReadDwordValue";
    goto LABEL_15;
  }
  if ( !*v6 )
    *v6 = 1;
LABEL_21:
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
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcStatusStorage::GetNgcStatistics", v2);
  return v2;
}

```

## disassembly

```asm
0x180094ed8  mov     [rsp-28h+arg_10], rbx
0x180094edd  push    rbp
0x180094ede  push    rsi
0x180094edf  push    rdi
0x180094ee0  push    r12
0x180094ee2  push    r14
0x180094ee4  mov     rbp, rsp
0x180094ee7  sub     rsp, 30h
0x180094eeb  mov     [rbp+arg_0], 0
0x180094ef3  mov     r14, rcx
0x180094ef6  mov     [rbp+hKey], 0
0x180094efe  lea     r12, aNgcstatusstora_7; "NgcStatusStorage::GetNgcStatistics"
0x180094f05  test    rcx, rcx
0x180094f08  jnz     short loc_180094F39
0x180094f0a  lea     r8, aPdata; "pData"
0x180094f11  mov     rdx, r12
0x180094f14  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180094f1b  mov     esi, 80070057h
0x180094f20  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180094f25  lea     rdx, aPdata; "pData"
0x180094f2c  mov     rcx, r12; unsigned __int16 *
0x180094f2f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180094f34  jmp     loc_1800950AF
0x180094f39  xorps   xmm0, xmm0
0x180094f3c  lea     rdx, [rbp+hKey]; HKEY *
0x180094f40  movups  xmmword ptr [rcx], xmm0
0x180094f43  xor     eax, eax
0x180094f45  mov     edi, 20019h
0x180094f4a  mov     [rcx+10h], rax
0x180094f4e  mov     ecx, edi; unsigned int
0x180094f50  call    ?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z; RegOpenCurrentUserKey(ulong,HKEY__ * *)
0x180094f55  mov     ebx, eax
0x180094f57  test    eax, eax
0x180094f59  jz      short loc_180094F67
0x180094f5b  lea     rdi, aOpenrootkey; "OpenRootKey"
0x180094f62  jmp     loc_18009507B
0x180094f67  mov     rcx, [rbp+hKey]; hKey
0x180094f6b  lea     rax, [rbp+arg_0]
0x180094f6f  mov     r9d, edi; samDesired
0x180094f72  mov     [rsp+30h+phkResult], rax; phkResult
0x180094f77  xor     r8d, r8d; ulOptions
0x180094f7a  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180094f81  xor     esi, esi
0x180094f83  call    cs:__imp_RegOpenKeyExW
0x180094f89  mov     ebx, eax
0x180094f8b  cmp     eax, 2
0x180094f8e  jnz     short loc_180094FAB
0x180094f90  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x180094f97  mov     rdx, r12
0x180094f9a  lea     rcx, aSTheRegistryKe_5; "%s: The registry key \"%s\" does not ex"...
0x180094fa1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180094fa6  jmp     loc_1800950AF
0x180094fab  lea     rdi, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x180094fb2  test    ebx, ebx
0x180094fb4  jz      short loc_180094FD3
0x180094fb6  mov     r8, rdi; unsigned __int16 *
0x180094fb9  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180094fc0  mov     ecx, ebx; unsigned int
0x180094fc2  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180094fc7  lea     rcx, aSCannotOpenReg_4; "%s: Cannot open registry key \"%s\". Wi"...
0x180094fce  jmp     loc_180095082
0x180094fd3  mov     rcx, [rbp+arg_0]; HKEY
0x180094fd7  lea     r8, aLasterror; "LastError"
0x180094fde  mov     dword ptr [rsp+30h+var_8], esi; unsigned int
0x180094fe2  mov     r9, rdi; unsigned __int16 *
0x180094fe5  xor     edx, edx; unsigned __int16 *
0x180094fe7  mov     [rsp+30h+phkResult], r14; unsigned int *
0x180094fec  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x180094ff1  mov     ebx, eax
0x180094ff3  test    eax, eax
0x180094ff5  jnz     short loc_180095074
0x180094ff7  mov     rcx, [rbp+arg_0]; HKEY
0x180094ffb  lea     rax, [r14+4]
0x180094fff  mov     dword ptr [rsp+30h+var_8], esi; __int64
0x180095003  lea     r8, aNumoffailures; "NumOfFailures"
0x18009500a  mov     r9, rdi; unsigned __int16 *
0x18009500d  mov     [rsp+30h+phkResult], rax; unsigned int *
0x180095012  xor     edx, edx; unsigned __int16 *
0x180095014  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x180095019  mov     ebx, eax
0x18009501b  test    eax, eax
0x18009501d  jnz     short loc_180095074
0x18009501f  mov     rcx, [rbp+arg_0]; HKEY
0x180095023  lea     rax, [r14+8]
0x180095027  mov     r9, rdi; unsigned __int16 *
0x18009502a  mov     [rsp+30h+phkResult], rax; __int64 *
0x18009502f  lea     r8, aLastattempttim; "LastAttemptTime"
0x180095036  xor     edx, edx; unsigned __int16 *
0x180095038  call    ?RegReadQwordValue@@YAKPEAUHKEY__@@PEBG11PEA_J_J@Z; RegReadQwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,__int64 *,__int64)
0x18009503d  mov     ebx, eax
0x18009503f  test    eax, eax
0x180095041  jz      short loc_18009504C
0x180095043  lea     rdi, aRegreadqwordva; "RegReadQwordValue"
0x18009504a  jmp     short loc_18009507B
0x18009504c  mov     rcx, [rbp+arg_0]; HKEY
0x180095050  lea     r8, aLastcertenroll; "LastCertEnrollResult"
0x180095057  add     r14, 10h
0x18009505b  mov     dword ptr [rsp+30h+var_8], esi; unsigned int
0x18009505f  mov     r9, rdi; unsigned __int16 *
0x180095062  mov     [rsp+30h+phkResult], r14; unsigned int *
0x180095067  xor     edx, edx; unsigned __int16 *
0x180095069  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18009506e  mov     ebx, eax
0x180095070  test    eax, eax
0x180095072  jz      short loc_1800950A3
0x180095074  lea     rdi, aRegreaddwordva; "RegReadDwordValue"
0x18009507b  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180095082  mov     r9d, ebx
0x180095085  mov     rdx, r12
0x180095088  mov     r8, rdi
0x18009508b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095090  test    ebx, ebx
0x180095092  jg      short loc_180095098
0x180095094  mov     esi, ebx
0x180095096  jmp     short loc_1800950AF
0x180095098  movzx   esi, bx
0x18009509b  or      esi, 80070000h
0x1800950a1  jmp     short loc_1800950AF
0x1800950a3  cmp     [r14], esi
0x1800950a6  jnz     short loc_1800950AF
0x1800950a8  mov     dword ptr [r14], 1
0x1800950af  mov     rcx, [rbp+arg_0]; hKey
0x1800950b3  test    rcx, rcx
0x1800950b6  jz      short loc_1800950C6
0x1800950b8  call    cs:__imp_RegCloseKey
0x1800950be  mov     [rbp+arg_0], 0
0x1800950c6  mov     rcx, [rbp+hKey]; hKey
0x1800950ca  test    rcx, rcx
0x1800950cd  jz      short loc_1800950DD
0x1800950cf  call    cs:__imp_RegCloseKey
0x1800950d5  mov     [rbp+hKey], 0
0x1800950dd  mov     r8d, esi
0x1800950e0  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800950e7  mov     rdx, r12
0x1800950ea  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800950ef  mov     rbx, [rsp+30h+arg_10]
0x1800950f4  mov     eax, esi
0x1800950f6  add     rsp, 30h
0x1800950fa  pop     r14
0x1800950fc  pop     r12
0x1800950fe  pop     rdi
0x1800950ff  pop     rsi
0x180095100  pop     rbp
0x180095101  retn
```
