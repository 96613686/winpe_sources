# RegistryPath::InitializeCurrentUserPath(ulong,ushort const *)

- ea: `0x180005894`
- end: `0x18000598d`
- name: `?InitializeCurrentUserPath@RegistryPath@@QEAAJKPEBG@Z`
- size: `249`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800053d0`
- `0x180005bbc`

## callees

- `0x18000554c`
- `0x180005894`
- `0x1800084f4`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800058b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800058b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005982`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005982`

## string_xrefs

- `0x18000595a`: `RegistryPath::Initialize`
- `0x180005934`: `%s: RegOpenCurrentUserKey(%lu) failed with win32 error code: 0x%08x.`
- `0x180005927`: `RegistryPath::InitializeCurrentUserPath`
- `0x180005961`: `RegistryPath::InitializeCurrentUserPath`
- `0x1800058fa`: `RegOpenCurrentUser`
- `0x18000590e`: `RegOpenCurrentUserKey`
- `0x180005918`: `%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.`

## pseudocode

```c
__int64 __fastcall RegistryPath::InitializeCurrentUserPath(RegistryPath *this, __int64 a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  int v6; // eax
  bool v7; // sf
  int v9; // [rsp+20h] [rbp-18h]
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v4 = RegOpenCurrentUser(0x2000000u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    Logger::WriteRegistryFailureEvent(v4, L"RegOpenCurrentUser", L"HKEY_CURRENT_USER");
    Logger::TraceError(
      L"%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.",
      L"RegOpenCurrentUserKey",
      (unsigned int)v5,
      0x2000000);
    Logger::TraceError(
      L"%s: RegOpenCurrentUserKey(%lu) failed with win32 error code: 0x%08x.",
      L"RegistryPath::InitializeCurrentUserPath",
      0x2000000,
      (unsigned int)v5);
    v7 = v5 < 0;
    if ( v5 <= 0 )
    {
LABEL_4:
      if ( !v7 )
        return (unsigned int)v5;
      goto LABEL_9;
    }
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_3:
    v7 = v5 < 0;
    goto LABEL_4;
  }
  v6 = RegistryPath::Initialize(
         this,
         hKey,
         (wchar_t *)L"HKEY_CURRENT_USER",
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin");
  v5 = v6;
  if ( v6 >= 0 )
    goto LABEL_3;
  v9 = v6;
  Logger::TraceError(
    L"%s: %s(%s) failed with error code: 0x%08x.",
    L"RegistryPath::InitializeCurrentUserPath",
    L"RegistryPath::Initialize",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin",
    v9);
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005894  mov     rax, rsp
0x180005897  mov     [rax+8], rbx
0x18000589b  mov     [rax+18h], r8
0x18000589f  push    rdi
0x1800058a0  sub     rsp, 30h
0x1800058a4  mov     rdi, rcx
0x1800058a7  mov     qword ptr [rax+18h], 0
0x1800058af  mov     ecx, 2000000h; samDesired
0x1800058b4  lea     rdx, [rax+18h]; phkResult
0x1800058b8  call    cs:__imp_RegOpenCurrentUser
0x1800058be  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800058c5  mov     ebx, eax
0x1800058c7  test    eax, eax
0x1800058c9  jnz     short loc_1800058FA
0x1800058cb  mov     rdx, [rsp+38h+hKey]; HKEY
0x1800058d0  lea     r9, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800058d7  mov     rcx, rdi; this
0x1800058da  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800058df  mov     ebx, eax
0x1800058e1  test    eax, eax
0x1800058e3  js      short loc_18000594F
0x1800058e5  test    ebx, ebx
0x1800058e7  js      loc_180005974
0x1800058ed  mov     eax, ebx
0x1800058ef  mov     rbx, [rsp+38h+arg_0]
0x1800058f4  add     rsp, 30h
0x1800058f8  pop     rdi
0x1800058f9  retn
0x1800058fa  lea     rdx, aRegopencurrent; "RegOpenCurrentUser"
0x180005901  mov     ecx, ebx; unsigned int
0x180005903  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180005908  mov     r9d, 2000000h
0x18000590e  lea     rdx, aRegopencurrent_0; "RegOpenCurrentUserKey"
0x180005915  mov     r8d, ebx
0x180005918  lea     rcx, aSRegopencurren; "%s: RegOpenCurrentUser failed with win3"...
0x18000591f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005924  mov     r9d, ebx
0x180005927  lea     rdx, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x18000592e  mov     r8d, 2000000h
0x180005934  lea     rcx, aSRegopencurren_0; "%s: RegOpenCurrentUserKey(%lu) failed w"...
0x18000593b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005940  test    ebx, ebx
0x180005942  jle     short loc_1800058E7
0x180005944  movzx   ebx, bx
0x180005947  or      ebx, 80070000h
0x18000594d  jmp     short loc_1800058E5
0x18000594f  lea     r9, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180005956  mov     [rsp+38h+var_18], eax
0x18000595a  lea     r8, aRegistrypathIn_0; "RegistryPath::Initialize"
0x180005961  lea     rdx, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x180005968  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x18000596f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005974  mov     rcx, [rsp+38h+hKey]; hKey
0x180005979  test    rcx, rcx
0x18000597c  jz      loc_1800058ED
0x180005982  call    cs:__imp_RegCloseKey
0x180005988  jmp     loc_1800058ED
```
