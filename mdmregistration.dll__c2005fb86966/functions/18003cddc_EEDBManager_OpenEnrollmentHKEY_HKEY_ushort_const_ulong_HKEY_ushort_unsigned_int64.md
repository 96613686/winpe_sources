# EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)

- ea: `0x18003cddc`
- end: `0x18003cfa8`
- name: `?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z`
- size: `460`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, wchar_t *String1@<rdx>, unsigned int@<r8d>, HKEY *@<r9>, unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003bf04`
- `0x18003cfb0`
- `0x18003d1b4`

## callees

- `0x1800026d0`
- `0x18000bd08`
- `0x18000bd7c`
- `0x18003cddc`
- `0x18004b970`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18003ce38`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18003ce38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003cf6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ce8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cf27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ce8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cf27`

## pseudocode

```c
__int64 __fastcall EEDBManager::OpenEnrollmentHKEY(
        HKEY hKey,
        wchar_t *String1,
        int a3,
        HKEY *a4,
        unsigned __int16 *a5,
        unsigned __int64 a6)
{
  __int64 result; // rax
  LSTATUS v11; // eax
  signed int v12; // ebx
  LSTATUS v13; // eax
  signed int v14; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( hKey != HKEY_LOCAL_MACHINE || !(unsigned __int8)RtlIsStateSeparationEnabled() )
    goto LABEL_12;
  result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", String1);
  if ( (int)result < 0 )
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
    if ( (int)result < 0 )
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
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003cddc  push    rbx
0x18003cdde  push    rbp
0x18003cddf  push    rsi
0x18003cde0  push    rdi
0x18003cde1  push    r14
0x18003cde3  push    r15
0x18003cde5  sub     rsp, 258h
0x18003cdec  mov     rax, cs:__security_cookie
0x18003cdf3  xor     rax, rsp
0x18003cdf6  mov     [rsp+288h+var_48], rax
0x18003cdfe  mov     r14, [rsp+288h+arg_20]
0x18003ce06  mov     rdi, r9
0x18003ce09  mov     esi, r8d
0x18003ce0c  mov     rbp, rdx
0x18003ce0f  mov     r15, rcx
0x18003ce12  test    r9, r9
0x18003ce15  jnz     short loc_18003CE21
0x18003ce17  mov     eax, 80004003h
0x18003ce1c  jmp     loc_18003CF87
0x18003ce21  mov     rbx, 0FFFFFFFF80000002h
0x18003ce28  mov     qword ptr [r9], 0
0x18003ce2f  cmp     r15, rbx
0x18003ce32  jnz     loc_18003CEEA
0x18003ce38  call    cs:__imp_RtlIsStateSeparationEnabled
0x18003ce3f  nop     dword ptr [rax+rax+00h]
0x18003ce44  test    al, al
0x18003ce46  jz      loc_18003CEEA
0x18003ce4c  lea     r9, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Enrollment"...
0x18003ce53  mov     [rsp+288h+phkResult], rbp
0x18003ce58  lea     r8, aSS; "%s\\%s"
0x18003ce5f  mov     edx, 104h; unsigned __int64
0x18003ce64  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x18003ce69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ce6e  test    eax, eax
0x18003ce70  js      loc_18003CF87
0x18003ce76  mov     r9d, esi
0x18003ce79  mov     [rsp+288h+phkResult], rdi; phkResult
0x18003ce7e  bts     r9d, 8; samDesired
0x18003ce83  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18003ce88  xor     r8d, r8d; ulOptions
0x18003ce8b  mov     rcx, rbx; hKey
0x18003ce8e  call    cs:__imp_RegOpenKeyExW
0x18003ce95  nop     dword ptr [rax+rax+00h]
0x18003ce9a  mov     ebx, eax
0x18003ce9c  test    eax, eax
0x18003ce9e  jle     short loc_18003CEA9
0x18003cea0  movzx   ebx, ax
0x18003cea3  or      ebx, 80070000h
0x18003cea9  test    ebx, ebx
0x18003ceab  jns     short loc_18003CEDF
0x18003cead  mov     r8d, 6; MaxCount
0x18003ceb3  lea     rdx, aStatus; "Status"
0x18003ceba  mov     rcx, rbp; String1
0x18003cebd  call    wcsncmp_0
0x18003cec2  test    eax, eax
0x18003cec4  jz      short loc_18003CF42
0x18003cec6  mov     r8d, 7; MaxCount
0x18003cecc  lea     rdx, aContext_0; "Context"
0x18003ced3  mov     rcx, rbp; String1
0x18003ced6  call    wcsncmp_0
0x18003cedb  test    eax, eax
0x18003cedd  jz      short loc_18003CF42
0x18003cedf  lea     eax, [rbx+7FF8FFFEh]
0x18003cee5  cmp     eax, 1
0x18003cee8  ja      short loc_18003CF42
0x18003ceea  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Enrollments"
0x18003cef1  mov     [rsp+288h+phkResult], rbp
0x18003cef6  lea     r8, aSS; "%s\\%s"
0x18003cefd  mov     edx, 104h; unsigned __int64
0x18003cf02  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x18003cf07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003cf0c  test    eax, eax
0x18003cf0e  js      short loc_18003CF87
0x18003cf10  bts     esi, 8
0x18003cf14  mov     [rsp+288h+phkResult], rdi; phkResult
0x18003cf19  mov     r9d, esi; samDesired
0x18003cf1c  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18003cf21  xor     r8d, r8d; ulOptions
0x18003cf24  mov     rcx, r15; hKey
0x18003cf27  call    cs:__imp_RegOpenKeyExW
0x18003cf2e  nop     dword ptr [rax+rax+00h]
0x18003cf33  mov     ebx, eax
0x18003cf35  test    eax, eax
0x18003cf37  jle     short loc_18003CF42
0x18003cf39  movzx   ebx, ax
0x18003cf3c  or      ebx, 80070000h
0x18003cf42  test    r14, r14
0x18003cf45  jz      short loc_18003CF62
0x18003cf47  mov     rdx, [rsp+288h+arg_28]; unsigned __int64
0x18003cf4f  lea     r8, [rsp+288h+SubKey]; unsigned __int16 *
0x18003cf54  mov     rcx, r14; unsigned __int16 *
0x18003cf57  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003cf5c  test    ebx, ebx
0x18003cf5e  js      short loc_18003CF66
0x18003cf60  mov     ebx, eax
0x18003cf62  test    ebx, ebx
0x18003cf64  jns     short loc_18003CF85
0x18003cf66  mov     rcx, [rdi]; hKey
0x18003cf69  test    rcx, rcx
0x18003cf6c  jz      short loc_18003CF81
0x18003cf6e  call    cs:__imp_RegCloseKey
0x18003cf75  nop     dword ptr [rax+rax+00h]
0x18003cf7a  mov     qword ptr [rdi], 0
0x18003cf81  mov     eax, ebx
0x18003cf83  jmp     short loc_18003CF87
0x18003cf85  xor     eax, eax
0x18003cf87  mov     rcx, [rsp+288h+var_48]
0x18003cf8f  xor     rcx, rsp; StackCookie
0x18003cf92  call    __security_check_cookie
0x18003cf97  add     rsp, 258h
0x18003cf9e  pop     r15
0x18003cfa0  pop     r14
0x18003cfa2  pop     rdi
0x18003cfa3  pop     rsi
0x18003cfa4  pop     rbp
0x18003cfa5  pop     rbx
0x18003cfa6  retn
```
