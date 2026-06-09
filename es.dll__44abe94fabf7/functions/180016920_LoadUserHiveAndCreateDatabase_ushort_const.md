# LoadUserHiveAndCreateDatabase(ushort const *)

- ea: `0x180016920`
- end: `0x180016a8c`
- name: `?LoadUserHiveAndCreateDatabase@@YAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180016548`

## callees

- `0x180007e6c`
- `0x18000c910`
- `0x180016920`
- `0x180033a9c`
- `0x180033b78`
- `0x180033f2c`
- `0x1800434c6`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016971`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016a0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016971`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016a0a`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180016a32`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180016a32`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800169ca`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800169ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a68`

## pseudocode

```c
__int64 __fastcall LoadUserHiveAndCreateDatabase(const unsigned __int16 *a1)
{
  unsigned int v2; // esi
  LPCWSTR v3; // rcx
  LSTATUS ProfilePath; // eax
  unsigned int EventSystemKey; // ebx
  __int64 v6; // rcx
  bool v7; // cc
  LSTATUS KeyW; // eax
  __int64 v9; // rcx
  HKEY hKey[2]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR File[264]; // [rsp+40h] [rbp-248h] BYREF

  hKey[0] = 0;
  v2 = safe_lstrlenW(a1);
  ProfilePath = RegOpenKeyExW(HKEY_USERS, v3, 0, 0x20019u, hKey);
  EventSystemKey = ProfilePath;
  if ( ProfilePath == 2 )
  {
    memset_0(File, 0, 0x20Au);
    ProfilePath = GetProfilePath(v2, a1, File);
    EventSystemKey = ProfilePath;
    v7 = ProfilePath <= 0;
    if ( !ProfilePath )
    {
      ProfilePath = SetPrivilege(v6, 1);
      EventSystemKey = ProfilePath;
      v7 = ProfilePath <= 0;
      if ( !ProfilePath )
      {
        KeyW = RegLoadKeyW(HKEY_USERS, a1, File);
        EventSystemKey = KeyW;
        if ( KeyW )
        {
          if ( KeyW > 0 )
            EventSystemKey = (unsigned __int16)KeyW | 0x80070000;
        }
        else
        {
          EventSystemKey = AddToUnLoadOnLogOff(a1);
          if ( (EventSystemKey & 0x80000000) != 0 )
          {
            RegUnLoadKeyW(HKEY_USERS, a1);
          }
          else if ( !RegOpenKeyExW(HKEY_USERS, a1, 0, 0x20006u, hKey) )
          {
            EventSystemKey = CreateEventSystemKey(hKey[0], v2, a1);
            RegCloseKey(hKey[0]);
          }
        }
        SetPrivilege(v9, 0);
        return EventSystemKey;
      }
    }
  }
  else
  {
    v7 = ProfilePath <= 0;
    if ( !ProfilePath )
    {
      EventSystemKey = CreateEventSystemKey(hKey[0], v2, a1);
      RegCloseKey(hKey[0]);
      return EventSystemKey;
    }
  }
  if ( !v7 )
    return (unsigned __int16)ProfilePath | 0x80070000;
  return EventSystemKey;
}

```

## disassembly

```asm
0x180016920  push    rbx
0x180016922  push    rbp
0x180016923  push    rsi
0x180016924  push    rdi
0x180016925  sub     rsp, 268h
0x18001692c  mov     rax, cs:__security_cookie
0x180016933  xor     rax, rsp
0x180016936  mov     [rsp+288h+var_38], rax
0x18001693e  mov     rdi, rcx
0x180016941  mov     [rsp+288h+hKey], 0
0x18001694a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18001694f  mov     esi, eax
0x180016951  mov     rdx, rcx; lpSubKey
0x180016954  lea     rax, [rsp+288h+hKey]
0x180016959  mov     rbp, 0FFFFFFFF80000003h
0x180016960  mov     r9d, 20019h; samDesired
0x180016966  mov     [rsp+288h+phkResult], rax; phkResult
0x18001696b  xor     r8d, r8d; ulOptions
0x18001696e  mov     rcx, rbp; hKey
0x180016971  call    cs:__imp_RegOpenKeyExW
0x180016977  mov     ebx, eax
0x180016979  cmp     eax, 2
0x18001697c  jnz     loc_180016A41
0x180016982  xor     edx, edx; Val
0x180016984  lea     rcx, [rsp+288h+File]; void *
0x180016989  mov     r8d, 20Ah; Size
0x18001698f  call    memset_0
0x180016994  lea     r8, [rsp+288h+File]
0x180016999  mov     rdx, rdi
0x18001699c  mov     ecx, esi
0x18001699e  call    GetProfilePath
0x1800169a3  mov     ebx, eax
0x1800169a5  test    eax, eax
0x1800169a7  jnz     loc_180016A45
0x1800169ad  lea     edx, [rax+1]
0x1800169b0  call    SetPrivilege
0x1800169b5  mov     ebx, eax
0x1800169b7  test    eax, eax
0x1800169b9  jnz     loc_180016A45
0x1800169bf  lea     r8, [rsp+288h+File]; lpFile
0x1800169c4  mov     rdx, rdi; lpSubKey
0x1800169c7  mov     rcx, rbp; hKey
0x1800169ca  call    cs:__imp_RegLoadKeyW
0x1800169d0  mov     ebx, eax
0x1800169d2  test    eax, eax
0x1800169d4  jz      short loc_1800169E3
0x1800169d6  jle     short loc_180016A38
0x1800169d8  movzx   ebx, ax
0x1800169db  or      ebx, 80070000h
0x1800169e1  jmp     short loc_180016A38
0x1800169e3  mov     rcx, rdi; unsigned __int16 *
0x1800169e6  call    ?AddToUnLoadOnLogOff@@YAJPEBG@Z; AddToUnLoadOnLogOff(ushort const *)
0x1800169eb  mov     ebx, eax
0x1800169ed  mov     rdx, rdi; lpSubKey
0x1800169f0  mov     rcx, rbp; hKey
0x1800169f3  test    eax, eax
0x1800169f5  js      short loc_180016A32
0x1800169f7  lea     rax, [rsp+288h+hKey]
0x1800169fc  mov     r9d, 20006h; samDesired
0x180016a02  xor     r8d, r8d; ulOptions
0x180016a05  mov     [rsp+288h+phkResult], rax; phkResult
0x180016a0a  call    cs:__imp_RegOpenKeyExW
0x180016a10  test    eax, eax
0x180016a12  jnz     short loc_180016A38
0x180016a14  mov     rcx, [rsp+288h+hKey]; hKey
0x180016a19  mov     r8, rdi; unsigned __int16 *
0x180016a1c  mov     edx, esi; unsigned int
0x180016a1e  call    ?CreateEventSystemKey@@YAJPEAUHKEY__@@KPEBG@Z; CreateEventSystemKey(HKEY__ *,ulong,ushort const *)
0x180016a23  mov     rcx, [rsp+288h+hKey]; hKey
0x180016a28  mov     ebx, eax
0x180016a2a  call    cs:__imp_RegCloseKey
0x180016a30  jmp     short loc_180016A38
0x180016a32  call    cs:__imp_RegUnLoadKeyW
0x180016a38  xor     edx, edx
0x180016a3a  call    SetPrivilege
0x180016a3f  jmp     short loc_180016A6E
0x180016a41  test    eax, eax
0x180016a43  jz      short loc_180016A52
0x180016a45  jle     short loc_180016A6E
0x180016a47  movzx   ebx, ax
0x180016a4a  or      ebx, 80070000h
0x180016a50  jmp     short loc_180016A6E
0x180016a52  mov     rcx, [rsp+288h+hKey]; hKey
0x180016a57  mov     r8, rdi; unsigned __int16 *
0x180016a5a  mov     edx, esi; unsigned int
0x180016a5c  call    ?CreateEventSystemKey@@YAJPEAUHKEY__@@KPEBG@Z; CreateEventSystemKey(HKEY__ *,ulong,ushort const *)
0x180016a61  mov     rcx, [rsp+288h+hKey]; hKey
0x180016a66  mov     ebx, eax
0x180016a68  call    cs:__imp_RegCloseKey
0x180016a6e  mov     eax, ebx
0x180016a70  mov     rcx, [rsp+288h+var_38]
0x180016a78  xor     rcx, rsp; StackCookie
0x180016a7b  call    __security_check_cookie
0x180016a80  add     rsp, 268h
0x180016a87  pop     rdi
0x180016a88  pop     rsi
0x180016a89  pop     rbp
0x180016a8a  pop     rbx
0x180016a8b  retn
```
