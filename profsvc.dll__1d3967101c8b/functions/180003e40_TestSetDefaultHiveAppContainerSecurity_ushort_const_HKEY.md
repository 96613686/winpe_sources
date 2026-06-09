# TestSetDefaultHiveAppContainerSecurity(ushort const *,HKEY__ *)

- ea: `0x180003e40`
- end: `0x180004167`
- name: `?TestSetDefaultHiveAppContainerSecurity@@YAJPEBGPEAUHKEY__@@@Z`
- size: `807`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003735c`

## callees

- `0x180003e40`
- `0x180004170`
- `0x180004530`
- `0x180004690`
- `0x180037f78`
- `0x18003e8fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003eea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000401e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003eea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000401e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ed3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000400e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ed3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000400e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003f1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000404d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003e81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003f1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000404d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000414e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003fcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000414e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180003f4a`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180003fa8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000407b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800040d9`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180003f4a`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180003fa8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000407b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800040d9`

## pseudocode

```c
__int64 __fastcall TestSetDefaultHiveAppContainerSecurity(LPCWSTR lpSubKey, HKEY a2)
{
  LSTATUS v2; // eax
  signed int v3; // edi
  HKEY v4; // r12
  HANDLE ProcessHeap; // rax
  int v6; // r13d
  void *v7; // rsi
  int v8; // r15d
  __int64 v9; // r14
  LSTATUS v10; // eax
  bool v11; // sf
  LSTATUS KeySecurity; // eax
  signed int v13; // ebx
  unsigned int v14; // ecx
  LSTATUS v15; // eax
  HKEY v16; // r15
  HANDLE v17; // rax
  void *v18; // rsi
  __int64 v19; // r14
  LSTATUS v20; // eax
  bool v21; // sf
  LSTATUS v22; // eax
  signed int v23; // ebx
  unsigned int v24; // ecx
  LSTATUS v25; // eax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpSubKeya[2]; // [rsp+38h] [rbp-30h]
  LPCWSTR v29[4]; // [rsp+48h] [rbp-20h]
  HKEY cbSecurityDescriptor; // [rsp+B8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+58h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp+60h] BYREF

  cbSecurityDescriptor = a2;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x60019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v4 = hKey;
    lpSubKeya[0] = L"Software\\Microsoft\\Internet Explorer";
    lpSubKeya[1] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings";
    v29[1] = L"Software\\Microsoft\\Speech_OneCore";
    v29[0] = 0;
    phkResult = 0;
    ProcessHeap = GetProcessHeap();
    v6 = 256;
    v7 = HeapAlloc(ProcessHeap, 8u, 0x100u);
    if ( !v7 )
      goto LABEL_42;
    v8 = 256;
    v9 = 0;
    do
    {
      v10 = RegOpenKeyExW(v4, lpSubKeya[v9], 0, 0x20000u, &phkResult);
      v11 = v10 < 0;
      if ( v10 > 0 )
        v11 = 1;
      if ( v11 )
        break;
      LODWORD(cbSecurityDescriptor) = v8;
      KeySecurity = RegGetKeySecurity(phkResult, 4u, v7, (LPDWORD)&cbSecurityDescriptor);
      v13 = KeySecurity;
      if ( KeySecurity > 0 )
        v13 = (unsigned __int16)KeySecurity | 0x80070000;
      if ( v13 == -2147024774 )
      {
        v14 = 2 * (_DWORD)cbSecurityDescriptor;
        if ( 2 * (int)cbSecurityDescriptor <= (unsigned int)cbSecurityDescriptor )
        {
          v13 = -2147024362;
        }
        else
        {
          LODWORD(cbSecurityDescriptor) = 2 * (_DWORD)cbSecurityDescriptor;
          pSecurityDescriptor = 0;
          v13 = ResultFromHeapReAlloc(v7, v14, &pSecurityDescriptor);
          if ( v13 >= 0 )
          {
            v7 = pSecurityDescriptor;
            v8 = (int)cbSecurityDescriptor;
            v15 = RegGetKeySecurity(phkResult, 4u, pSecurityDescriptor, (LPDWORD)&cbSecurityDescriptor);
            v13 = v15;
            if ( v15 > 0 )
              v13 = (unsigned __int16)v15 | 0x80070000;
          }
        }
      }
      if ( phkResult != v4 )
        RegCloseKey(phkResult);
      if ( v13 < 0 )
        break;
      if ( !(unsigned int)DaclContainsPackageAndLpacCapabilitySid_(v7) )
        break;
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (unsigned int)v9 < 2 );
    ResultFromHeapFree(v7);
    if ( (_DWORD)v9 != 2 )
      goto LABEL_42;
    v16 = hKey;
    phkResult = 0;
    v17 = GetProcessHeap();
    v18 = HeapAlloc(v17, 8u, 0x100u);
    if ( !v18 )
      goto LABEL_42;
    v19 = 0;
    do
    {
      v20 = RegOpenKeyExW(v16, v29[v19], 0, 0x20000u, &phkResult);
      v21 = v20 < 0;
      if ( v20 > 0 )
        v21 = 1;
      if ( v21 )
        break;
      LODWORD(cbSecurityDescriptor) = v6;
      v22 = RegGetKeySecurity(phkResult, 4u, v18, (LPDWORD)&cbSecurityDescriptor);
      v23 = v22;
      if ( v22 > 0 )
        v23 = (unsigned __int16)v22 | 0x80070000;
      if ( v23 == -2147024774 )
      {
        v24 = 2 * (_DWORD)cbSecurityDescriptor;
        if ( 2 * (int)cbSecurityDescriptor <= (unsigned int)cbSecurityDescriptor )
        {
          v23 = -2147024362;
        }
        else
        {
          LODWORD(cbSecurityDescriptor) = 2 * (_DWORD)cbSecurityDescriptor;
          pSecurityDescriptor = 0;
          v23 = ResultFromHeapReAlloc(v18, v24, &pSecurityDescriptor);
          if ( v23 >= 0 )
          {
            v18 = pSecurityDescriptor;
            v6 = (int)cbSecurityDescriptor;
            v25 = RegGetKeySecurity(phkResult, 4u, pSecurityDescriptor, (LPDWORD)&cbSecurityDescriptor);
            v23 = v25;
            if ( v25 > 0 )
              v23 = (unsigned __int16)v25 | 0x80070000;
          }
        }
      }
      if ( phkResult != v16 )
        RegCloseKey(phkResult);
      if ( v23 < 0 )
        break;
      if ( !(unsigned int)DaclContainsPackageSid_(v18) )
        break;
      v19 = (unsigned int)(v19 + 1);
    }
    while ( (unsigned int)v19 < 2 );
    ResultFromHeapFree(v18);
    if ( (_DWORD)v19 != 2 )
LABEL_42:
      v3 = SetDefaultHiveAppContainerSecurity_(
             lpSubKey,
             hKey,
             (int (*)(HKEY, void *, void *, int, int))ApplySecurityToRegistryKey_);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003e40  mov     [rsp-40h+cbSecurityDescriptor], rdx
0x180003e45  mov     [rsp-40h+arg_0], rcx
0x180003e4a  push    rbp
0x180003e4b  push    rbx
0x180003e4c  push    rsi
0x180003e4d  push    rdi
0x180003e4e  push    r12
0x180003e50  push    r13
0x180003e52  push    r14
0x180003e54  push    r15
0x180003e56  mov     rbp, rsp
0x180003e59  sub     rsp, 68h
0x180003e5d  mov     rdx, rcx; lpSubKey
0x180003e60  mov     [rbp+hKey], 0
0x180003e68  lea     rcx, [rbp+hKey]
0x180003e6c  mov     r9d, 60019h; samDesired
0x180003e72  mov     [rsp+68h+phkResult], rcx; phkResult
0x180003e77  xor     r8d, r8d; ulOptions
0x180003e7a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180003e81  call    cs:__imp_RegOpenKeyExW
0x180003e87  mov     edi, eax
0x180003e89  test    eax, eax
0x180003e8b  jle     short loc_180003E96
0x180003e8d  movzx   edi, ax
0x180003e90  or      edi, 80070000h
0x180003e96  test    edi, edi
0x180003e98  js      loc_180004154
0x180003e9e  mov     r12, [rbp+hKey]
0x180003ea2  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\Internet Explorer"
0x180003ea9  mov     [rbp+lpSubKey], rax
0x180003ead  lea     rax, aSoftwareMicros_30; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003eb4  mov     [rbp+var_28], rax
0x180003eb8  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Speech_OneCore"
0x180003ebf  mov     [rbp+var_18], rax
0x180003ec3  mov     [rbp+var_20], 0
0x180003ecb  mov     [rbp+arg_18], 0
0x180003ed3  call    cs:__imp_GetProcessHeap
0x180003ed9  mov     r13d, 100h
0x180003edf  mov     edx, 8; dwFlags
0x180003ee4  mov     rcx, rax; hHeap
0x180003ee7  mov     r8d, r13d; dwBytes
0x180003eea  call    cs:__imp_HeapAlloc
0x180003ef0  mov     rsi, rax
0x180003ef3  test    rax, rax
0x180003ef6  jz      loc_18000412F
0x180003efc  mov     r15d, r13d
0x180003eff  xor     r14d, r14d
0x180003f02  mov     rdx, [rbp+r14*8+lpSubKey]; lpSubKey
0x180003f07  lea     rax, [rbp+arg_18]
0x180003f0b  mov     r9d, 20000h; samDesired
0x180003f11  mov     [rsp+68h+phkResult], rax; phkResult
0x180003f16  xor     r8d, r8d; ulOptions
0x180003f19  mov     rcx, r12; hKey
0x180003f1c  call    cs:__imp_RegOpenKeyExW
0x180003f22  test    eax, eax
0x180003f24  jle     short loc_180003F30
0x180003f26  movzx   eax, ax
0x180003f29  or      eax, 80070000h
0x180003f2e  test    eax, eax
0x180003f30  js      loc_180003FF0
0x180003f36  mov     rcx, [rbp+arg_18]; hKey
0x180003f3a  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180003f3e  mov     r8, rsi; pSecurityDescriptor
0x180003f41  mov     dword ptr [rbp+cbSecurityDescriptor], r15d
0x180003f45  mov     edx, 4; SecurityInformation
0x180003f4a  call    cs:__imp_RegGetKeySecurity
0x180003f50  mov     ebx, eax
0x180003f52  test    eax, eax
0x180003f54  jle     short loc_180003F5F
0x180003f56  movzx   ebx, ax
0x180003f59  or      ebx, 80070000h
0x180003f5f  cmp     ebx, 8007007Ah
0x180003f65  jnz     short loc_180003FC4
0x180003f67  mov     eax, dword ptr [rbp+cbSecurityDescriptor]
0x180003f6a  lea     ecx, [rax+rax]
0x180003f6d  cmp     ecx, eax
0x180003f6f  jbe     short loc_180003FBF
0x180003f71  mov     dword ptr [rbp+cbSecurityDescriptor], ecx
0x180003f74  lea     r8, [rbp+pSecurityDescriptor]; void **
0x180003f78  mov     edx, ecx; dwBytes
0x180003f7a  mov     rcx, rsi; lpMem
0x180003f7d  mov     [rbp+pSecurityDescriptor], 0
0x180003f85  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180003f8a  mov     ebx, eax
0x180003f8c  test    eax, eax
0x180003f8e  js      short loc_180003FC4
0x180003f90  mov     rsi, [rbp+pSecurityDescriptor]
0x180003f94  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180003f98  mov     rcx, [rbp+arg_18]; hKey
0x180003f9c  mov     r8, rsi; pSecurityDescriptor
0x180003f9f  mov     r15d, dword ptr [rbp+cbSecurityDescriptor]
0x180003fa3  mov     edx, 4; SecurityInformation
0x180003fa8  call    cs:__imp_RegGetKeySecurity
0x180003fae  mov     ebx, eax
0x180003fb0  test    eax, eax
0x180003fb2  jle     short loc_180003FC4
0x180003fb4  movzx   ebx, ax
0x180003fb7  or      ebx, 80070000h
0x180003fbd  jmp     short loc_180003FC4
0x180003fbf  mov     ebx, 80070216h
0x180003fc4  mov     rcx, [rbp+arg_18]; hKey
0x180003fc8  cmp     rcx, r12
0x180003fcb  jz      short loc_180003FD3
0x180003fcd  call    cs:__imp_RegCloseKey
0x180003fd3  test    ebx, ebx
0x180003fd5  js      short loc_180003FF0
0x180003fd7  mov     rcx, rsi; void *
0x180003fda  call    ?DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z; DaclContainsPackageAndLpacCapabilitySid_(void *)
0x180003fdf  test    eax, eax
0x180003fe1  jz      short loc_180003FF0
0x180003fe3  inc     r14d
0x180003fe6  cmp     r14d, 2
0x180003fea  jb      loc_180003F02
0x180003ff0  mov     rcx, rsi; lpMem
0x180003ff3  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180003ff8  cmp     r14d, 2
0x180003ffc  jnz     loc_18000412F
0x180004002  mov     r15, [rbp+hKey]
0x180004006  mov     [rbp+arg_18], 0
0x18000400e  call    cs:__imp_GetProcessHeap
0x180004014  mov     r8, r13; dwBytes
0x180004017  lea     edx, [r14+6]; dwFlags
0x18000401b  mov     rcx, rax; hHeap
0x18000401e  call    cs:__imp_HeapAlloc
0x180004024  mov     rsi, rax
0x180004027  test    rax, rax
0x18000402a  jz      loc_18000412F
0x180004030  xor     r14d, r14d
0x180004033  mov     rdx, [rbp+r14*8+var_20]; lpSubKey
0x180004038  lea     rax, [rbp+arg_18]
0x18000403c  mov     r9d, 20000h; samDesired
0x180004042  mov     [rsp+68h+phkResult], rax; phkResult
0x180004047  xor     r8d, r8d; ulOptions
0x18000404a  mov     rcx, r15; hKey
0x18000404d  call    cs:__imp_RegOpenKeyExW
0x180004053  test    eax, eax
0x180004055  jle     short loc_180004061
0x180004057  movzx   eax, ax
0x18000405a  or      eax, 80070000h
0x18000405f  test    eax, eax
0x180004061  js      loc_180004121
0x180004067  mov     rcx, [rbp+arg_18]; hKey
0x18000406b  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000406f  mov     r8, rsi; pSecurityDescriptor
0x180004072  mov     dword ptr [rbp+cbSecurityDescriptor], r13d
0x180004076  mov     edx, 4; SecurityInformation
0x18000407b  call    cs:__imp_RegGetKeySecurity
0x180004081  mov     ebx, eax
0x180004083  test    eax, eax
0x180004085  jle     short loc_180004090
0x180004087  movzx   ebx, ax
0x18000408a  or      ebx, 80070000h
0x180004090  cmp     ebx, 8007007Ah
0x180004096  jnz     short loc_1800040F5
0x180004098  mov     eax, dword ptr [rbp+cbSecurityDescriptor]
0x18000409b  lea     ecx, [rax+rax]
0x18000409e  cmp     ecx, eax
0x1800040a0  jbe     short loc_1800040F0
0x1800040a2  mov     dword ptr [rbp+cbSecurityDescriptor], ecx
0x1800040a5  lea     r8, [rbp+pSecurityDescriptor]; void **
0x1800040a9  mov     edx, ecx; dwBytes
0x1800040ab  mov     rcx, rsi; lpMem
0x1800040ae  mov     [rbp+pSecurityDescriptor], 0
0x1800040b6  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800040bb  mov     ebx, eax
0x1800040bd  test    eax, eax
0x1800040bf  js      short loc_1800040F5
0x1800040c1  mov     rsi, [rbp+pSecurityDescriptor]
0x1800040c5  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800040c9  mov     rcx, [rbp+arg_18]; hKey
0x1800040cd  mov     r8, rsi; pSecurityDescriptor
0x1800040d0  mov     r13d, dword ptr [rbp+cbSecurityDescriptor]
0x1800040d4  mov     edx, 4; SecurityInformation
0x1800040d9  call    cs:__imp_RegGetKeySecurity
0x1800040df  mov     ebx, eax
0x1800040e1  test    eax, eax
0x1800040e3  jle     short loc_1800040F5
0x1800040e5  movzx   ebx, ax
0x1800040e8  or      ebx, 80070000h
0x1800040ee  jmp     short loc_1800040F5
0x1800040f0  mov     ebx, 80070216h
0x1800040f5  mov     rcx, [rbp+arg_18]; hKey
0x1800040f9  cmp     rcx, r15
0x1800040fc  jz      short loc_180004104
0x1800040fe  call    cs:__imp_RegCloseKey
0x180004104  test    ebx, ebx
0x180004106  js      short loc_180004121
0x180004108  mov     rcx, rsi; void *
0x18000410b  call    ?DaclContainsPackageSid_@@YAHPEAX@Z; DaclContainsPackageSid_(void *)
0x180004110  test    eax, eax
0x180004112  jz      short loc_180004121
0x180004114  inc     r14d
0x180004117  cmp     r14d, 2
0x18000411b  jb      loc_180004033
0x180004121  mov     rcx, rsi; lpMem
0x180004124  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004129  cmp     r14d, 2
0x18000412d  jz      short loc_180004145
0x18000412f  mov     rdx, [rbp+hKey]; hKey
0x180004133  lea     r8, ?ApplySecurityToRegistryKey_@@YAJPEAUHKEY__@@PEAX1HH@Z; int (*)(HKEY, void *, void *, int, int)
0x18000413a  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x18000413e  call    ?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x180004143  mov     edi, eax
0x180004145  mov     rcx, [rbp+hKey]; hKey
0x180004149  test    rcx, rcx
0x18000414c  jz      short loc_180004154
0x18000414e  call    cs:__imp_RegCloseKey
0x180004154  mov     eax, edi
0x180004156  add     rsp, 68h
0x18000415a  pop     r15
0x18000415c  pop     r14
0x18000415e  pop     r13
0x180004160  pop     r12
0x180004162  pop     rdi
0x180004163  pop     rsi
0x180004164  pop     rbx
0x180004165  pop     rbp
0x180004166  retn
```
