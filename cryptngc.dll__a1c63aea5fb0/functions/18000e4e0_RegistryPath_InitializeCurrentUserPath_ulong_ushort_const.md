# RegistryPath::InitializeCurrentUserPath(ulong,ushort const *)

- ea: `0x18000e4e0`
- end: `0x18000e5cc`
- name: `?InitializeCurrentUserPath@RegistryPath@@QEAAJKPEBG@Z`
- size: `236`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d770`

## callees

- `0x18000e4e0`
- `0x18000e5d4`
- `0x180026f88`
- `0x180027448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000e504`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000e504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e578`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e578`

## string_xrefs

- `0x18000e517`: `RegOpenCurrentUser`
- `0x18000e52b`: `RegOpenCurrentUserKey`
- `0x18000e535`: `%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.`
- `0x18000e5b0`: `RegistryPath::Initialize`
- `0x18000e551`: `%s: RegOpenCurrentUserKey(%lu) failed with win32 error code: 0x%08x.`
- `0x18000e544`: `RegistryPath::InitializeCurrentUserPath`
- `0x18000e5b7`: `RegistryPath::InitializeCurrentUserPath`

## pseudocode

```c
__int64 __fastcall RegistryPath::InitializeCurrentUserPath(RegistryPath *this, __int64 a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  bool v6; // sf
  int v8; // eax
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
    v6 = v5 < 0;
    if ( v5 <= 0 )
      goto LABEL_5;
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_4:
    v6 = v5 < 0;
LABEL_5:
    if ( !v6 )
      return (unsigned int)v5;
    goto LABEL_6;
  }
  v8 = RegistryPath::Initialize(
         this,
         hKey,
         L"HKEY_CURRENT_USER",
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin");
  v5 = v8;
  if ( v8 >= 0 )
    goto LABEL_4;
  v9 = v8;
  Logger::TraceError(
    L"%s: %s(%s) failed with error code: 0x%08x.",
    L"RegistryPath::InitializeCurrentUserPath",
    L"RegistryPath::Initialize",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin",
    v9);
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e4e0  mov     rax, rsp
0x18000e4e3  mov     [rax+8], rbx
0x18000e4e7  mov     [rax+18h], r8
0x18000e4eb  push    rdi
0x18000e4ec  sub     rsp, 30h
0x18000e4f0  mov     rdi, rcx
0x18000e4f3  mov     qword ptr [rax+18h], 0
0x18000e4fb  mov     ecx, 2000000h; samDesired
0x18000e500  lea     rdx, [rax+18h]; phkResult
0x18000e504  call    cs:__imp_RegOpenCurrentUser
0x18000e50a  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18000e511  mov     ebx, eax
0x18000e513  test    eax, eax
0x18000e515  jz      short loc_18000E58B
0x18000e517  lea     rdx, aRegopencurrent; "RegOpenCurrentUser"
0x18000e51e  mov     ecx, eax; unsigned int
0x18000e520  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18000e525  mov     r9d, 2000000h
0x18000e52b  lea     rdx, aRegopencurrent_0; "RegOpenCurrentUserKey"
0x18000e532  mov     r8d, ebx
0x18000e535  lea     rcx, aSRegopencurren; "%s: RegOpenCurrentUser failed with win3"...
0x18000e53c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e541  mov     r9d, ebx
0x18000e544  lea     rdx, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x18000e54b  mov     r8d, 2000000h
0x18000e551  lea     rcx, aSRegopencurren_0; "%s: RegOpenCurrentUserKey(%lu) failed w"...
0x18000e558  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e55d  test    ebx, ebx
0x18000e55f  jle     short loc_18000E56C
0x18000e561  movzx   ebx, bx
0x18000e564  or      ebx, 80070000h
0x18000e56a  test    ebx, ebx
0x18000e56c  jns     short loc_18000E57E
0x18000e56e  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e573  test    rcx, rcx
0x18000e576  jz      short loc_18000E57E
0x18000e578  call    cs:__imp_RegCloseKey
0x18000e57e  mov     eax, ebx
0x18000e580  mov     rbx, [rsp+38h+arg_0]
0x18000e585  add     rsp, 30h
0x18000e589  pop     rdi
0x18000e58a  retn
0x18000e58b  mov     rdx, [rsp+38h+hKey]; HKEY
0x18000e590  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000e597  mov     rcx, rdi; this
0x18000e59a  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18000e59f  mov     ebx, eax
0x18000e5a1  test    eax, eax
0x18000e5a3  jns     short loc_18000E56A
0x18000e5a5  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000e5ac  mov     [rsp+38h+var_18], eax
0x18000e5b0  lea     r8, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18000e5b7  lea     rdx, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x18000e5be  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x18000e5c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e5ca  jmp     short loc_18000E56E
```
