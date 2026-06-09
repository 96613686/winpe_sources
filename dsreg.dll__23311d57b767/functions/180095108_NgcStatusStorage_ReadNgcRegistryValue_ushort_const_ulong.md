# NgcStatusStorage::ReadNgcRegistryValue(ushort const *,ulong *)

- ea: `0x180095108`
- end: `0x180095259`
- name: `?ReadNgcRegistryValue@NgcStatusStorage@@SAJPEBGPEAK@Z`
- size: `337`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004aac0`

## callees

- `0x1800065d0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18001c74c`
- `0x180043e54`
- `0x180095108`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009516d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009516d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009521b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095234`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009521b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095234`

## string_xrefs

- `0x1800951ac`: `RegOpenKeyExW`
- `0x180095142`: `OpenRootKey`
- `0x1800951c2`: `%s: Cannot open registry key "%s". Win32 error code: 0x%08x.`
- `0x18009518a`: `%s: The registry key "%s" does not exist. Noting to read.`
- `0x180095183`: `NgcStatusStorage::ReadNgcRegistryValue`
- `0x180095205`: `NgcStatusStorage::ReadNgcRegistryValue`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::ReadNgcRegistryValue(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int DwordValue; // eax
  int v5; // ebx
  const wchar_t *v6; // r8
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  DwordValue = RegOpenCurrentUserKey(0x20019u, &hKey);
  v5 = DwordValue;
  if ( DwordValue )
  {
    v6 = L"OpenRootKey";
LABEL_10:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"NgcStatusStorage::ReadNgcRegistryValue",
      v6,
      DwordValue);
    goto LABEL_11;
  }
  v7 = RegOpenKeyExW(
         hKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
         0,
         0x20019u,
         &phkResult);
  v5 = v7;
  if ( v7 == 2 )
  {
    v5 = 0;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: The registry key \"%s\" does not exist. Noting to read.",
      L"NgcStatusStorage::ReadNgcRegistryValue",
      L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    if ( a2 )
      *a2 = 0;
  }
  else
  {
    if ( v7 )
    {
      Logger::WriteRegistryFailureEvent(
        v7,
        L"RegOpenKeyExW",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
      Logger::TraceError(
        L"%s: Cannot open registry key \"%s\". Win32 error code: 0x%08x.",
        L"NgcStatusStorage::ReadNgcRegistryValue",
        L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
        (unsigned int)v5);
      goto LABEL_11;
    }
    DwordValue = RegReadDwordValue(
                   phkResult,
                   0,
                   a1,
                   L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
                   a2,
                   0);
    v5 = DwordValue;
    if ( DwordValue )
    {
      v6 = L"RegSaveDwordValue";
      goto LABEL_10;
    }
  }
LABEL_11:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180095108  mov     rax, rsp
0x18009510b  mov     [rax+8], rbx
0x18009510f  mov     [rax+10h], rsi
0x180095113  push    rdi
0x180095114  sub     rsp, 30h
0x180095118  mov     rdi, rdx
0x18009511b  mov     qword ptr [rax+18h], 0
0x180095123  mov     rsi, rcx
0x180095126  mov     qword ptr [rax+20h], 0
0x18009512e  lea     rdx, [rax+18h]; HKEY *
0x180095132  mov     ecx, 20019h; unsigned int
0x180095137  call    ?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z; RegOpenCurrentUserKey(ulong,HKEY__ * *)
0x18009513c  mov     ebx, eax
0x18009513e  test    eax, eax
0x180095140  jz      short loc_18009514E
0x180095142  lea     r8, aOpenrootkey; "OpenRootKey"
0x180095149  jmp     loc_1800951FB
0x18009514e  mov     rcx, [rsp+38h+hKey]; hKey
0x180095153  lea     rax, [rsp+38h+arg_18]
0x180095158  mov     r9d, 20019h; samDesired
0x18009515e  mov     [rsp+38h+phkResult], rax; phkResult
0x180095163  xor     r8d, r8d; ulOptions
0x180095166  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18009516d  call    cs:__imp_RegOpenKeyExW
0x180095173  mov     ebx, eax
0x180095175  cmp     eax, 2
0x180095178  jnz     short loc_18009519F
0x18009517a  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x180095181  xor     ebx, ebx
0x180095183  lea     rdx, aNgcstatusstora_6; "NgcStatusStorage::ReadNgcRegistryValue"
0x18009518a  lea     rcx, aSTheRegistryKe_5; "%s: The registry key \"%s\" does not ex"...
0x180095191  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180095196  test    rdi, rdi
0x180095199  jz      short loc_180095211
0x18009519b  mov     [rdi], ebx
0x18009519d  jmp     short loc_180095211
0x18009519f  test    ebx, ebx
0x1800951a1  jz      short loc_1800951CB
0x1800951a3  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800951aa  mov     ecx, ebx; unsigned int
0x1800951ac  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800951b3  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800951b8  mov     r9d, ebx
0x1800951bb  lea     r8, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800951c2  lea     rcx, aSCannotOpenReg_4; "%s: Cannot open registry key \"%s\". Wi"...
0x1800951c9  jmp     short loc_180095205
0x1800951cb  mov     rcx, [rsp+38h+arg_18]; HKEY
0x1800951d0  lea     r9, aHkeyCurrentUse_0; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x1800951d7  mov     [rsp+38h+var_10], 0; unsigned int
0x1800951df  mov     r8, rsi; unsigned __int16 *
0x1800951e2  xor     edx, edx; unsigned __int16 *
0x1800951e4  mov     [rsp+38h+phkResult], rdi; unsigned int *
0x1800951e9  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x1800951ee  mov     ebx, eax
0x1800951f0  test    eax, eax
0x1800951f2  jz      short loc_180095211
0x1800951f4  lea     r8, aRegsavedwordva; "RegSaveDwordValue"
0x1800951fb  mov     r9d, eax
0x1800951fe  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180095205  lea     rdx, aNgcstatusstora_6; "NgcStatusStorage::ReadNgcRegistryValue"
0x18009520c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095211  mov     rcx, [rsp+38h+hKey]; hKey
0x180095216  test    rcx, rcx
0x180095219  jz      short loc_18009522A
0x18009521b  call    cs:__imp_RegCloseKey
0x180095221  mov     [rsp+38h+hKey], 0
0x18009522a  mov     rcx, [rsp+38h+arg_18]; hKey
0x18009522f  test    rcx, rcx
0x180095232  jz      short loc_18009523A
0x180095234  call    cs:__imp_RegCloseKey
0x18009523a  test    ebx, ebx
0x18009523c  jle     short loc_180095247
0x18009523e  movzx   ebx, bx
0x180095241  or      ebx, 80070000h
0x180095247  mov     rsi, [rsp+38h+arg_8]
0x18009524c  mov     eax, ebx
0x18009524e  mov     rbx, [rsp+38h+arg_0]
0x180095253  add     rsp, 30h
0x180095257  pop     rdi
0x180095258  retn
```
