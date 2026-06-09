# EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)

- ea: `0x18000e994`
- end: `0x18000eb47`
- name: `?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z`
- size: `435`
- prototype: `int __fastcall(HKEY hKey, wchar_t *String1, int, HKEY *, unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000df4c`
- `0x18000eb50`
- `0x18000eccc`

## callees

- `0x180001a70`
- `0x1800040a4`
- `0x180005aec`
- `0x18000e994`
- `0x180011704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ead3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ead3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e9f0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e9f0`

## pseudocode

```c
int __fastcall EEDBManager::OpenEnrollmentHKEY(
        HKEY hKey,
        wchar_t *String1,
        int a3,
        HKEY *a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  int result; // eax
  LSTATUS v11; // eax
  signed int v12; // ebx
  LSTATUS v13; // eax
  signed int v14; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a4 )
    return -2147467261;
  *a4 = 0;
  if ( hKey != HKEY_LOCAL_MACHINE || !(unsigned __int8)RtlIsStateSeparationEnabled() )
    goto LABEL_12;
  result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", String1);
  if ( result < 0 )
    return result;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, a3 | 0x100, a4);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( (v12 >= 0 || wcsncmp_0(String1, L"Status", 6u) && wcsncmp_0(String1, L"Context", 7u))
    && (unsigned int)(v12 + 2147024894) <= 1 )
  {
LABEL_12:
    result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Enrollments", String1);
    if ( result < 0 )
      return result;
    v13 = RegOpenKeyExW(hKey, SubKey, 0, a3 | 0x100, a4);
    v12 = v13;
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( a5 )
  {
    v14 = StringCchCopyW(a5, a6, SubKey);
    if ( v12 < 0 )
      goto LABEL_19;
    v12 = v14;
  }
  if ( v12 >= 0 )
    return 0;
LABEL_19:
  if ( *a4 )
  {
    RegCloseKey(*a4);
    *a4 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x18000e994  push    rbx
0x18000e996  push    rbp
0x18000e997  push    rsi
0x18000e998  push    rdi
0x18000e999  push    r14
0x18000e99b  push    r15
0x18000e99d  sub     rsp, 258h
0x18000e9a4  mov     rax, cs:__security_cookie
0x18000e9ab  xor     rax, rsp
0x18000e9ae  mov     [rsp+288h+var_48], rax
0x18000e9b6  mov     r14, [rsp+288h+arg_20]
0x18000e9be  mov     rdi, r9
0x18000e9c1  mov     esi, r8d
0x18000e9c4  mov     rbp, rdx
0x18000e9c7  mov     r15, rcx
0x18000e9ca  test    r9, r9
0x18000e9cd  jnz     short loc_18000E9D9
0x18000e9cf  mov     eax, 80004003h
0x18000e9d4  jmp     loc_18000EB27
0x18000e9d9  mov     rbx, 0FFFFFFFF80000002h
0x18000e9e0  mov     qword ptr [r9], 0
0x18000e9e7  cmp     r15, rbx
0x18000e9ea  jnz     loc_18000EA96
0x18000e9f0  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000e9f6  test    al, al
0x18000e9f8  jz      loc_18000EA96
0x18000e9fe  lea     r9, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Enrollment"...
0x18000ea05  mov     [rsp+288h+phkResult], rbp
0x18000ea0a  lea     r8, aSS; "%s\\%s"
0x18000ea11  mov     edx, 104h; unsigned __int64
0x18000ea16  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x18000ea1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ea20  test    eax, eax
0x18000ea22  js      loc_18000EB27
0x18000ea28  mov     r9d, esi
0x18000ea2b  mov     [rsp+288h+phkResult], rdi; phkResult
0x18000ea30  bts     r9d, 8; samDesired
0x18000ea35  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18000ea3a  xor     r8d, r8d; ulOptions
0x18000ea3d  mov     rcx, rbx; hKey
0x18000ea40  call    cs:__imp_RegOpenKeyExW
0x18000ea46  mov     ebx, eax
0x18000ea48  test    eax, eax
0x18000ea4a  jle     short loc_18000EA55
0x18000ea4c  movzx   ebx, ax
0x18000ea4f  or      ebx, 80070000h
0x18000ea55  test    ebx, ebx
0x18000ea57  jns     short loc_18000EA8B
0x18000ea59  mov     r8d, 6; MaxCount
0x18000ea5f  lea     rdx, aStatus; "Status"
0x18000ea66  mov     rcx, rbp; String1
0x18000ea69  call    wcsncmp_0
0x18000ea6e  test    eax, eax
0x18000ea70  jz      short loc_18000EAE8
0x18000ea72  mov     r8d, 7; MaxCount
0x18000ea78  lea     rdx, aContext; "Context"
0x18000ea7f  mov     rcx, rbp; String1
0x18000ea82  call    wcsncmp_0
0x18000ea87  test    eax, eax
0x18000ea89  jz      short loc_18000EAE8
0x18000ea8b  lea     eax, [rbx+7FF8FFFEh]
0x18000ea91  cmp     eax, 1
0x18000ea94  ja      short loc_18000EAE8
0x18000ea96  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\Enrollments"
0x18000ea9d  mov     [rsp+288h+phkResult], rbp
0x18000eaa2  lea     r8, aSS; "%s\\%s"
0x18000eaa9  mov     edx, 104h; unsigned __int64
0x18000eaae  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x18000eab3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eab8  test    eax, eax
0x18000eaba  js      short loc_18000EB27
0x18000eabc  bts     esi, 8
0x18000eac0  mov     [rsp+288h+phkResult], rdi; phkResult
0x18000eac5  mov     r9d, esi; samDesired
0x18000eac8  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18000eacd  xor     r8d, r8d; ulOptions
0x18000ead0  mov     rcx, r15; hKey
0x18000ead3  call    cs:__imp_RegOpenKeyExW
0x18000ead9  mov     ebx, eax
0x18000eadb  test    eax, eax
0x18000eadd  jle     short loc_18000EAE8
0x18000eadf  movzx   ebx, ax
0x18000eae2  or      ebx, 80070000h
0x18000eae8  test    r14, r14
0x18000eaeb  jz      short loc_18000EB08
0x18000eaed  mov     rdx, [rsp+288h+arg_28]; unsigned __int64
0x18000eaf5  lea     r8, [rsp+288h+SubKey]; unsigned __int16 *
0x18000eafa  mov     rcx, r14; unsigned __int16 *
0x18000eafd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eb02  test    ebx, ebx
0x18000eb04  js      short loc_18000EB0C
0x18000eb06  mov     ebx, eax
0x18000eb08  test    ebx, ebx
0x18000eb0a  jns     short loc_18000EB25
0x18000eb0c  mov     rcx, [rdi]; hKey
0x18000eb0f  test    rcx, rcx
0x18000eb12  jz      short loc_18000EB21
0x18000eb14  call    cs:__imp_RegCloseKey
0x18000eb1a  mov     qword ptr [rdi], 0
0x18000eb21  mov     eax, ebx
0x18000eb23  jmp     short loc_18000EB27
0x18000eb25  xor     eax, eax
0x18000eb27  mov     rcx, [rsp+288h+var_48]
0x18000eb2f  xor     rcx, rsp; StackCookie
0x18000eb32  call    __security_check_cookie
0x18000eb37  add     rsp, 258h
0x18000eb3e  pop     r15
0x18000eb40  pop     r14
0x18000eb42  pop     rdi
0x18000eb43  pop     rsi
0x18000eb44  pop     rbp
0x18000eb45  pop     rbx
0x18000eb46  retn
```
