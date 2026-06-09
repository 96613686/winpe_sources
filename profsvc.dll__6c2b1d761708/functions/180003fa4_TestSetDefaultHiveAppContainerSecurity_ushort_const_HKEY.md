# TestSetDefaultHiveAppContainerSecurity(ushort const *,HKEY__ *)

- ea: `0x180003fa4`
- end: `0x180004320`
- name: `?TestSetDefaultHiveAppContainerSecurity@@YAJPEBGPEAUHKEY__@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038798`

## callees

- `0x180003754`
- `0x180003850`
- `0x180003fa4`
- `0x180005370`
- `0x180039ce0`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000405a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800041b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000405a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800041b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000403d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000419c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000403d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000419c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003fe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003fe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800041e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004155`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004155`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004300`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800040c6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000412a`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000421b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000427f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800040c6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000412a`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000421b`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000427f`

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
0x180003fa4  mov     [rsp-40h+cbSecurityDescriptor], rdx
0x180003fa9  mov     [rsp-40h+arg_0], rcx
0x180003fae  push    rbp
0x180003faf  push    rbx
0x180003fb0  push    rsi
0x180003fb1  push    rdi
0x180003fb2  push    r12
0x180003fb4  push    r13
0x180003fb6  push    r14
0x180003fb8  push    r15
0x180003fba  mov     rbp, rsp
0x180003fbd  sub     rsp, 68h
0x180003fc1  mov     rdx, rcx; lpSubKey
0x180003fc4  mov     [rbp+hKey], 0
0x180003fcc  lea     rcx, [rbp+hKey]
0x180003fd0  mov     r9d, 60019h; samDesired
0x180003fd6  mov     [rsp+68h+phkResult], rcx; phkResult
0x180003fdb  xor     r8d, r8d; ulOptions
0x180003fde  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180003fe5  call    cs:__imp_RegOpenKeyExW
0x180003fec  nop     dword ptr [rax+rax+00h]
0x180003ff1  mov     edi, eax
0x180003ff3  test    eax, eax
0x180003ff5  jle     short loc_180004000
0x180003ff7  movzx   edi, ax
0x180003ffa  or      edi, 80070000h
0x180004000  test    edi, edi
0x180004002  js      loc_18000430C
0x180004008  mov     r12, [rbp+hKey]
0x18000400c  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\Internet Explorer"
0x180004013  mov     [rbp+lpSubKey], rax
0x180004017  lea     rax, aSoftwareMicros_30; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000401e  mov     [rbp+var_28], rax
0x180004022  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Speech_OneCore"
0x180004029  mov     [rbp+var_18], rax
0x18000402d  mov     [rbp+var_20], 0
0x180004035  mov     [rbp+arg_18], 0
0x18000403d  call    cs:__imp_GetProcessHeap
0x180004044  nop     dword ptr [rax+rax+00h]
0x180004049  mov     r13d, 100h
0x18000404f  mov     edx, 8; dwFlags
0x180004054  mov     rcx, rax; hHeap
0x180004057  mov     r8d, r13d; dwBytes
0x18000405a  call    cs:__imp_HeapAlloc
0x180004061  nop     dword ptr [rax+rax+00h]
0x180004066  mov     rsi, rax
0x180004069  test    rax, rax
0x18000406c  jz      loc_1800042E1
0x180004072  mov     r15d, r13d
0x180004075  xor     r14d, r14d
0x180004078  mov     rdx, [rbp+r14*8+lpSubKey]; lpSubKey
0x18000407d  lea     rax, [rbp+arg_18]
0x180004081  mov     r9d, 20000h; samDesired
0x180004087  mov     [rsp+68h+phkResult], rax; phkResult
0x18000408c  xor     r8d, r8d; ulOptions
0x18000408f  mov     rcx, r12; hKey
0x180004092  call    cs:__imp_RegOpenKeyExW
0x180004099  nop     dword ptr [rax+rax+00h]
0x18000409e  test    eax, eax
0x1800040a0  jle     short loc_1800040AC
0x1800040a2  movzx   eax, ax
0x1800040a5  or      eax, 80070000h
0x1800040aa  test    eax, eax
0x1800040ac  js      loc_18000417E
0x1800040b2  mov     rcx, [rbp+arg_18]; hKey
0x1800040b6  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800040ba  mov     r8, rsi; pSecurityDescriptor
0x1800040bd  mov     dword ptr [rbp+cbSecurityDescriptor], r15d
0x1800040c1  mov     edx, 4; SecurityInformation
0x1800040c6  call    cs:__imp_RegGetKeySecurity
0x1800040cd  nop     dword ptr [rax+rax+00h]
0x1800040d2  mov     ebx, eax
0x1800040d4  test    eax, eax
0x1800040d6  jle     short loc_1800040E1
0x1800040d8  movzx   ebx, ax
0x1800040db  or      ebx, 80070000h
0x1800040e1  cmp     ebx, 8007007Ah
0x1800040e7  jnz     short loc_18000414C
0x1800040e9  mov     eax, dword ptr [rbp+cbSecurityDescriptor]
0x1800040ec  lea     ecx, [rax+rax]
0x1800040ef  cmp     ecx, eax
0x1800040f1  jbe     short loc_180004147
0x1800040f3  mov     dword ptr [rbp+cbSecurityDescriptor], ecx
0x1800040f6  lea     r8, [rbp+pSecurityDescriptor]; void **
0x1800040fa  mov     edx, ecx; dwBytes
0x1800040fc  mov     rcx, rsi; lpMem
0x1800040ff  mov     [rbp+pSecurityDescriptor], 0
0x180004107  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x18000410c  mov     ebx, eax
0x18000410e  test    eax, eax
0x180004110  js      short loc_18000414C
0x180004112  mov     rsi, [rbp+pSecurityDescriptor]
0x180004116  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000411a  mov     rcx, [rbp+arg_18]; hKey
0x18000411e  mov     r8, rsi; pSecurityDescriptor
0x180004121  mov     r15d, dword ptr [rbp+cbSecurityDescriptor]
0x180004125  mov     edx, 4; SecurityInformation
0x18000412a  call    cs:__imp_RegGetKeySecurity
0x180004131  nop     dword ptr [rax+rax+00h]
0x180004136  mov     ebx, eax
0x180004138  test    eax, eax
0x18000413a  jle     short loc_18000414C
0x18000413c  movzx   ebx, ax
0x18000413f  or      ebx, 80070000h
0x180004145  jmp     short loc_18000414C
0x180004147  mov     ebx, 80070216h
0x18000414c  mov     rcx, [rbp+arg_18]; hKey
0x180004150  cmp     rcx, r12
0x180004153  jz      short loc_180004161
0x180004155  call    cs:__imp_RegCloseKey
0x18000415c  nop     dword ptr [rax+rax+00h]
0x180004161  test    ebx, ebx
0x180004163  js      short loc_18000417E
0x180004165  mov     rcx, rsi; void *
0x180004168  call    ?DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z; DaclContainsPackageAndLpacCapabilitySid_(void *)
0x18000416d  test    eax, eax
0x18000416f  jz      short loc_18000417E
0x180004171  inc     r14d
0x180004174  cmp     r14d, 2
0x180004178  jb      loc_180004078
0x18000417e  mov     rcx, rsi; lpMem
0x180004181  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004186  cmp     r14d, 2
0x18000418a  jnz     loc_1800042E1
0x180004190  mov     r15, [rbp+hKey]
0x180004194  mov     [rbp+arg_18], 0
0x18000419c  call    cs:__imp_GetProcessHeap
0x1800041a3  nop     dword ptr [rax+rax+00h]
0x1800041a8  mov     r8, r13; dwBytes
0x1800041ab  lea     edx, [r14+6]; dwFlags
0x1800041af  mov     rcx, rax; hHeap
0x1800041b2  call    cs:__imp_HeapAlloc
0x1800041b9  nop     dword ptr [rax+rax+00h]
0x1800041be  mov     rsi, rax
0x1800041c1  test    rax, rax
0x1800041c4  jz      loc_1800042E1
0x1800041ca  xor     r14d, r14d
0x1800041cd  mov     rdx, [rbp+r14*8+var_20]; lpSubKey
0x1800041d2  lea     rax, [rbp+arg_18]
0x1800041d6  mov     r9d, 20000h; samDesired
0x1800041dc  mov     [rsp+68h+phkResult], rax; phkResult
0x1800041e1  xor     r8d, r8d; ulOptions
0x1800041e4  mov     rcx, r15; hKey
0x1800041e7  call    cs:__imp_RegOpenKeyExW
0x1800041ee  nop     dword ptr [rax+rax+00h]
0x1800041f3  test    eax, eax
0x1800041f5  jle     short loc_180004201
0x1800041f7  movzx   eax, ax
0x1800041fa  or      eax, 80070000h
0x1800041ff  test    eax, eax
0x180004201  js      loc_1800042D3
0x180004207  mov     rcx, [rbp+arg_18]; hKey
0x18000420b  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000420f  mov     r8, rsi; pSecurityDescriptor
0x180004212  mov     dword ptr [rbp+cbSecurityDescriptor], r13d
0x180004216  mov     edx, 4; SecurityInformation
0x18000421b  call    cs:__imp_RegGetKeySecurity
0x180004222  nop     dword ptr [rax+rax+00h]
0x180004227  mov     ebx, eax
0x180004229  test    eax, eax
0x18000422b  jle     short loc_180004236
0x18000422d  movzx   ebx, ax
0x180004230  or      ebx, 80070000h
0x180004236  cmp     ebx, 8007007Ah
0x18000423c  jnz     short loc_1800042A1
0x18000423e  mov     eax, dword ptr [rbp+cbSecurityDescriptor]
0x180004241  lea     ecx, [rax+rax]
0x180004244  cmp     ecx, eax
0x180004246  jbe     short loc_18000429C
0x180004248  mov     dword ptr [rbp+cbSecurityDescriptor], ecx
0x18000424b  lea     r8, [rbp+pSecurityDescriptor]; void **
0x18000424f  mov     edx, ecx; dwBytes
0x180004251  mov     rcx, rsi; lpMem
0x180004254  mov     [rbp+pSecurityDescriptor], 0
0x18000425c  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180004261  mov     ebx, eax
0x180004263  test    eax, eax
0x180004265  js      short loc_1800042A1
0x180004267  mov     rsi, [rbp+pSecurityDescriptor]
0x18000426b  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000426f  mov     rcx, [rbp+arg_18]; hKey
0x180004273  mov     r8, rsi; pSecurityDescriptor
0x180004276  mov     r13d, dword ptr [rbp+cbSecurityDescriptor]
0x18000427a  mov     edx, 4; SecurityInformation
0x18000427f  call    cs:__imp_RegGetKeySecurity
0x180004286  nop     dword ptr [rax+rax+00h]
0x18000428b  mov     ebx, eax
0x18000428d  test    eax, eax
0x18000428f  jle     short loc_1800042A1
0x180004291  movzx   ebx, ax
0x180004294  or      ebx, 80070000h
0x18000429a  jmp     short loc_1800042A1
0x18000429c  mov     ebx, 80070216h
0x1800042a1  mov     rcx, [rbp+arg_18]; hKey
0x1800042a5  cmp     rcx, r15
0x1800042a8  jz      short loc_1800042B6
0x1800042aa  call    cs:__imp_RegCloseKey
0x1800042b1  nop     dword ptr [rax+rax+00h]
0x1800042b6  test    ebx, ebx
0x1800042b8  js      short loc_1800042D3
0x1800042ba  mov     rcx, rsi; void *
0x1800042bd  call    ?DaclContainsPackageSid_@@YAHPEAX@Z; DaclContainsPackageSid_(void *)
0x1800042c2  test    eax, eax
0x1800042c4  jz      short loc_1800042D3
0x1800042c6  inc     r14d
0x1800042c9  cmp     r14d, 2
0x1800042cd  jb      loc_1800041CD
0x1800042d3  mov     rcx, rsi; lpMem
0x1800042d6  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800042db  cmp     r14d, 2
0x1800042df  jz      short loc_1800042F7
0x1800042e1  mov     rdx, [rbp+hKey]; hKey
0x1800042e5  lea     r8, ?ApplySecurityToRegistryKey_@@YAJPEAUHKEY__@@PEAX1HH@Z; int (*)(HKEY, void *, void *, int, int)
0x1800042ec  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x1800042f0  call    ?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x1800042f5  mov     edi, eax
0x1800042f7  mov     rcx, [rbp+hKey]; hKey
0x1800042fb  test    rcx, rcx
0x1800042fe  jz      short loc_18000430C
0x180004300  call    cs:__imp_RegCloseKey
0x180004307  nop     dword ptr [rax+rax+00h]
0x18000430c  mov     eax, edi
0x18000430e  add     rsp, 68h
0x180004312  pop     r15
0x180004314  pop     r14
0x180004316  pop     r13
0x180004318  pop     r12
0x18000431a  pop     rdi
0x18000431b  pop     rsi
0x18000431c  pop     rbx
0x18000431d  pop     rbp
0x18000431e  retn
```
