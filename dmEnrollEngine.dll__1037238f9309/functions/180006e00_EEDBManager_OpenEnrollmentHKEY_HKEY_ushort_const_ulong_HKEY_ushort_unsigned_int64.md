# EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)

- ea: `0x180006e00`
- end: `0x18000702f`
- name: `?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z`
- size: `559`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, wchar_t *String1@<rdx>, unsigned int@<r8d>, HKEY *@<r9>, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d580`
- `0x180040508`

## callees

- `0x1800067a0`
- `0x180006e00`
- `0x18002e1a0`
- `0x180078040`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180006e5f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006e5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006eaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006eaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006f4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ff5`

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
  unsigned __int16 *v6; // rbx
  __int64 result; // rax
  LSTATUS v12; // eax
  signed int v13; // r15d
  LSTATUS v14; // eax
  unsigned __int64 v15; // r8
  int v16; // ecx
  __int64 v17; // rax
  WCHAR *v18; // rdx
  unsigned __int16 *v19; // rcx
  WCHAR SubKey[264]; // [rsp+30h] [rbp-258h] BYREF

  v6 = a5;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( hKey != HKEY_LOCAL_MACHINE || !(unsigned __int8)RtlIsStateSeparationEnabled(-2147483646, String1) )
    goto LABEL_12;
  result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", String1);
  if ( (int)result < 0 )
    return result;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, a3 | 0x100, a4);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( (v13 >= 0 || wcsncmp_0(String1, L"Status", 6u) && wcsncmp_0(String1, L"Context", 7u))
    && (unsigned int)(v13 + 2147024894) <= 1 )
  {
LABEL_12:
    result = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Enrollments", String1);
    if ( (int)result < 0 )
      return result;
    v14 = RegOpenKeyExW(hKey, SubKey, 0, a3 | 0x100, a4);
    v13 = v14;
    if ( v14 > 0 )
      v13 = (unsigned __int16)v14 | 0x80070000;
  }
  if ( a5 )
  {
    v15 = a6;
    if ( a6 )
    {
      if ( a6 <= 0x7FFFFFFF )
      {
        v17 = 2147483646;
        v18 = SubKey;
        do
        {
          if ( !v17 )
            break;
          if ( !*v18 )
            break;
          *v6++ = *v18++;
          --v17;
          --v15;
        }
        while ( v15 );
        v19 = v6 - 1;
        if ( v15 )
          v19 = v6;
        *v19 = 0;
        v16 = -2147024774;
        if ( v15 )
          v16 = 0;
      }
      else
      {
        v16 = -2147024809;
        *a5 = 0;
      }
    }
    else
    {
      v16 = -2147024809;
    }
    if ( v13 < 0 )
      goto LABEL_32;
    v13 = v16;
  }
  if ( v13 >= 0 )
    return 0;
LABEL_32:
  if ( *a4 )
  {
    RegCloseKey(*a4);
    *a4 = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180006e00  push    rbx
0x180006e02  push    rbp
0x180006e03  push    rsi
0x180006e04  push    rdi
0x180006e05  push    r14
0x180006e07  sub     rsp, 260h
0x180006e0e  mov     rax, cs:__security_cookie
0x180006e15  xor     rax, rsp
0x180006e18  mov     [rsp+288h+var_48], rax
0x180006e20  mov     rbx, [rsp+288h+arg_20]
0x180006e28  mov     r14, r9
0x180006e2b  mov     esi, r8d
0x180006e2e  mov     rbp, rdx
0x180006e31  mov     rdi, rcx
0x180006e34  test    r9, r9
0x180006e37  jnz     short loc_180006E43
0x180006e39  mov     eax, 80004003h
0x180006e3e  jmp     loc_180007011
0x180006e43  mov     [rsp+288h+var_30], r15
0x180006e4b  mov     qword ptr [r9], 0
0x180006e52  cmp     rdi, 0FFFFFFFF80000002h
0x180006e59  jnz     loc_180006F0A
0x180006e5f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006e65  test    al, al
0x180006e67  jz      loc_180006F0A
0x180006e6d  lea     r9, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x180006e74  mov     [rsp+288h+phkResult], rbp
0x180006e79  lea     r8, aSS_0; "%s\\%s"
0x180006e80  mov     edx, 104h; unsigned __int64
0x180006e85  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x180006e8a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006e8f  test    eax, eax
0x180006e91  js      loc_180007009
0x180006e97  mov     r9d, esi
0x180006e9a  mov     [rsp+288h+phkResult], r14; phkResult
0x180006e9f  bts     r9d, 8; samDesired
0x180006ea4  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180006ea9  xor     r8d, r8d; ulOptions
0x180006eac  mov     rcx, rdi; hKey
0x180006eaf  call    cs:__imp_RegOpenKeyExW
0x180006eb5  mov     r15d, eax
0x180006eb8  test    eax, eax
0x180006eba  jle     short loc_180006EC7
0x180006ebc  movzx   r15d, ax
0x180006ec0  or      r15d, 80070000h
0x180006ec7  test    r15d, r15d
0x180006eca  jns     short loc_180006EFE
0x180006ecc  mov     r8d, 6; MaxCount
0x180006ed2  lea     rdx, aStatus; "Status"
0x180006ed9  mov     rcx, rbp; String1
0x180006edc  call    wcsncmp_0
0x180006ee1  test    eax, eax
0x180006ee3  jz      short loc_180006F63
0x180006ee5  mov     r8d, 7; MaxCount
0x180006eeb  lea     rdx, aContext_0; "Context"
0x180006ef2  mov     rcx, rbp; String1
0x180006ef5  call    wcsncmp_0
0x180006efa  test    eax, eax
0x180006efc  jz      short loc_180006F63
0x180006efe  lea     eax, [r15+7FF8FFFEh]
0x180006f05  cmp     eax, 1
0x180006f08  ja      short loc_180006F63
0x180006f0a  lea     r9, SubKey; "Software\\Microsoft\\Enrollments"
0x180006f11  mov     [rsp+288h+phkResult], rbp
0x180006f16  lea     r8, aSS_0; "%s\\%s"
0x180006f1d  mov     edx, 104h; unsigned __int64
0x180006f22  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x180006f27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f2c  test    eax, eax
0x180006f2e  js      loc_180007009
0x180006f34  bts     esi, 8
0x180006f38  mov     [rsp+288h+phkResult], r14; phkResult
0x180006f3d  mov     r9d, esi; samDesired
0x180006f40  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180006f45  xor     r8d, r8d; ulOptions
0x180006f48  mov     rcx, rdi; hKey
0x180006f4b  call    cs:__imp_RegOpenKeyExW
0x180006f51  mov     r15d, eax
0x180006f54  test    eax, eax
0x180006f56  jle     short loc_180006F63
0x180006f58  movzx   r15d, ax
0x180006f5c  or      r15d, 80070000h
0x180006f63  test    rbx, rbx
0x180006f66  jz      loc_180006FE8
0x180006f6c  mov     r8, [rsp+288h+arg_28]
0x180006f74  test    r8, r8
0x180006f77  jz      short loc_180006FD1
0x180006f79  cmp     r8, 7FFFFFFFh
0x180006f80  jbe     short loc_180006F89
0x180006f82  mov     ecx, 80070057h
0x180006f87  jmp     short loc_180006FDB
0x180006f89  mov     eax, 7FFFFFFEh
0x180006f8e  lea     rdx, [rsp+288h+SubKey]
0x180006f93  test    rax, rax
0x180006f96  jz      short loc_180006FB4
0x180006f98  movzx   ecx, word ptr [rdx]
0x180006f9b  test    cx, cx
0x180006f9e  jz      short loc_180006FB4
0x180006fa0  mov     [rbx], cx
0x180006fa3  add     rdx, 2
0x180006fa7  add     rbx, 2
0x180006fab  dec     rax
0x180006fae  sub     r8, 1
0x180006fb2  jnz     short loc_180006F93
0x180006fb4  test    r8, r8
0x180006fb7  lea     rcx, [rbx-2]
0x180006fbb  cmovnz  rcx, rbx
0x180006fbf  xor     eax, eax
0x180006fc1  test    r8, r8
0x180006fc4  mov     [rcx], ax
0x180006fc7  mov     ecx, 8007007Ah
0x180006fcc  cmovnz  ecx, eax
0x180006fcf  jmp     short loc_180006FE0
0x180006fd1  mov     ecx, 80070057h
0x180006fd6  test    r8, r8
0x180006fd9  jz      short loc_180006FE0
0x180006fdb  xor     eax, eax
0x180006fdd  mov     [rbx], ax
0x180006fe0  test    r15d, r15d
0x180006fe3  js      short loc_180006FED
0x180006fe5  mov     r15d, ecx
0x180006fe8  test    r15d, r15d
0x180006feb  jns     short loc_180007007
0x180006fed  mov     rcx, [r14]; hKey
0x180006ff0  test    rcx, rcx
0x180006ff3  jz      short loc_180007002
0x180006ff5  call    cs:__imp_RegCloseKey
0x180006ffb  mov     qword ptr [r14], 0
0x180007002  mov     eax, r15d
0x180007005  jmp     short loc_180007009
0x180007007  xor     eax, eax
0x180007009  mov     r15, [rsp+288h+var_30]
0x180007011  mov     rcx, [rsp+288h+var_48]
0x180007019  xor     rcx, rsp; StackCookie
0x18000701c  call    __security_check_cookie
0x180007021  add     rsp, 260h
0x180007028  pop     r14
0x18000702a  pop     rdi
0x18000702b  pop     rsi
0x18000702c  pop     rbp
0x18000702d  pop     rbx
0x18000702e  retn
```
