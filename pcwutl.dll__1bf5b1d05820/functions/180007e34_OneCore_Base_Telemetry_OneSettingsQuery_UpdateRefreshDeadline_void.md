# OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(void)

- ea: `0x180007e34`
- end: `0x180007f86`
- name: `?UpdateRefreshDeadline@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800055f4`
- `0x180007504`

## callees

- `0x180007b54`
- `0x180007e34`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180007f5e`
- `ADVAPI32!RegCloseKey` at `0x180007f5e`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f08`
- `ADVAPI32!RegOpenKeyExW` at `0x180007f08`
- `ADVAPI32!RegSetValueExW` at `0x180007f48`
- `ADVAPI32!RegSetValueExW` at `0x180007f48`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180007e7d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180007e7d`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::UpdateRefreshDeadline(struct _FILETIME *this)
{
  __int64 v2; // rdx
  signed int v3; // ebx
  LSTATUS v4; // eax
  bool v5; // cc
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  SystemTimeAsFileTime = 0;
  *(_QWORD *)Data = 0;
  hKey = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = *(_QWORD *)&SystemTimeAsFileTime + 600000000LL * this[3].dwLowDateTime;
  this[200] = SystemTimeAsFileTime;
  v3 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", &this[135], &this[5], &this[70], v2);
  if ( v3 >= 0 )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
    v3 = v4;
    v5 = v4 <= 0;
    if ( v4 || (v4 = RegSetValueExW(hKey, L"RefreshAfter", 0, 0xBu, Data, 8u), v3 = v4, v5 = v4 <= 0, v4) )
    {
      if ( !v5 )
        v3 = (unsigned __int16)v4 | 0x80070000;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007e34  mov     [rsp-8+arg_8], rbx
0x180007e39  push    rbp
0x180007e3a  lea     rbp, [rsp-170h]
0x180007e42  sub     rsp, 270h
0x180007e49  mov     rax, cs:__security_cookie
0x180007e50  xor     rax, rsp
0x180007e53  mov     [rbp+170h+var_10], rax
0x180007e5a  mov     rbx, rcx
0x180007e5d  mov     qword ptr [rsp+270h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180007e66  lea     rcx, [rsp+270h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007e6b  mov     qword ptr [rsp+270h+Data], 0
0x180007e74  mov     [rsp+270h+hKey], 0
0x180007e7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180007e83  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwHighDateTime]
0x180007e87  lea     r9, [rbx+438h]
0x180007e8e  mov     ecx, [rbx+18h]
0x180007e91  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180007e98  mov     dword ptr [rsp+270h+Data+4], eax
0x180007e9c  mov     eax, [rsp+270h+SystemTimeAsFileTime.dwLowDateTime]
0x180007ea0  imul    rdx, rcx, 23C34600h
0x180007ea7  mov     dword ptr [rsp+270h+Data], eax
0x180007eab  lea     rcx, [rbx+28h]
0x180007eaf  mov     rax, qword ptr [rsp+270h+Data]
0x180007eb4  add     rdx, rax
0x180007eb7  mov     [rbx+640h], rax
0x180007ebe  lea     rax, [rbx+230h]
0x180007ec5  mov     qword ptr [rsp+270h+Data], rdx
0x180007eca  mov     qword ptr [rsp+270h+cbData], rax
0x180007ecf  mov     edx, 104h; unsigned __int64
0x180007ed4  mov     [rsp+270h+phkResult], rcx
0x180007ed9  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x180007ede  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007ee3  mov     ebx, eax
0x180007ee5  test    eax, eax
0x180007ee7  js      short loc_180007F54
0x180007ee9  lea     rax, [rsp+270h+hKey]
0x180007eee  mov     r9d, 0F003Fh; samDesired
0x180007ef4  xor     r8d, r8d; ulOptions
0x180007ef7  mov     [rsp+270h+phkResult], rax; phkResult
0x180007efc  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180007f01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007f08  call    cs:__imp_RegOpenKeyExW
0x180007f0e  mov     ebx, eax
0x180007f10  test    eax, eax
0x180007f12  jz      short loc_180007F21
0x180007f14  jle     short loc_180007F54
0x180007f16  movzx   ebx, ax
0x180007f19  or      ebx, 80070000h
0x180007f1f  jmp     short loc_180007F54
0x180007f21  mov     rcx, [rsp+270h+hKey]; hKey
0x180007f26  lea     rax, [rsp+270h+Data]
0x180007f2b  mov     [rsp+270h+cbData], 8; cbData
0x180007f33  lea     rdx, Value; "RefreshAfter"
0x180007f3a  mov     r9d, 0Bh; dwType
0x180007f40  mov     [rsp+270h+phkResult], rax; lpData
0x180007f45  xor     r8d, r8d; Reserved
0x180007f48  call    cs:__imp_RegSetValueExW
0x180007f4e  mov     ebx, eax
0x180007f50  test    eax, eax
0x180007f52  jnz     short loc_180007F14
0x180007f54  mov     rcx, [rsp+270h+hKey]; hKey
0x180007f59  test    rcx, rcx
0x180007f5c  jz      short loc_180007F64
0x180007f5e  call    cs:__imp_RegCloseKey
0x180007f64  mov     eax, ebx
0x180007f66  mov     rcx, [rbp+170h+var_10]
0x180007f6d  xor     rcx, rsp; StackCookie
0x180007f70  call    __security_check_cookie
0x180007f75  mov     rbx, [rsp+270h+arg_8]
0x180007f7d  add     rsp, 270h
0x180007f84  pop     rbp
0x180007f85  retn
```
