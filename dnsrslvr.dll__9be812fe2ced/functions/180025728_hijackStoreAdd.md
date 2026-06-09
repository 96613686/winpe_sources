# hijackStoreAdd

- ea: `0x180025728`
- end: `0x18002594f`
- name: `hijackStoreAdd`
- size: `551`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180025360`
- `0x180034eb0`

## callees

- `0x180008b00`
- `0x18002039c`
- `0x180025728`
- `0x1800277c0`
- `0x180027900`
- `0x180046ec0`
- `0x180047818`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002590d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002591d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002590d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002591d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800258c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800258f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800258c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800258f7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025838`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025891`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025838`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025891`

## string_xrefs

- `0x1800257e4`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x1800257eb`: `Dnscache`

## pseudocode

```c
_BOOL8 __fastcall hijackStoreAdd(__int64 a1, int a2, int a3)
{
  BOOL v6; // ebx
  int PersistedRegistryLocation; // eax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v12[12]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR v13[80]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  phkResult = 0;
  memset_0(v13, 0, sizeof(v13));
  *(_DWORD *)Data = 0;
  *(_DWORD *)v12 = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( !a1 || a3 == 2 || g_HijackSystemState != 1 )
    return 0;
  v6 = 0;
  hijackStoreRemove(a1);
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                L"Dnscache",
                                L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                L"Parameters\\Probe",
                                SubKey,
                                520);
  if ( PersistedRegistryLocation >= 0 )
  {
    if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    {
      if ( (unsigned int)Dns_GuidToString(a1, v13) )
      {
        v13[79] = 0;
        if ( !RegCreateKeyExW(hKey, v13, 0, 0, 0, 0x20006u, 0, &phkResult, 0) )
        {
          *(_DWORD *)Data = a2;
          if ( !RegSetValueExW(phkResult, L"LastProbeTime", 0, 4u, Data, 4u) )
          {
            *(_DWORD *)v12 = a3 == 1;
            v6 = RegSetValueExW(phkResult, L"NetworkPerformsHijacking", 0, 4u, v12, 4u) == 0;
          }
        }
      }
    }
  }
  else
  {
    WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180025728  mov     [rsp-8+arg_10], rbx
0x18002572d  push    rbp
0x18002572e  push    rsi
0x18002572f  push    rdi
0x180025730  push    r12
0x180025732  push    r14
0x180025734  lea     rbp, [rsp-230h]
0x18002573c  sub     rsp, 330h
0x180025743  mov     rax, cs:__security_cookie
0x18002574a  xor     rax, rsp
0x18002574d  mov     [rbp+250h+var_30], rax
0x180025754  mov     esi, r8d
0x180025757  mov     [rsp+350h+hKey], 0
0x180025760  mov     r14d, edx
0x180025763  mov     [rsp+350h+var_300], 0
0x18002576c  mov     rdi, rcx
0x18002576f  xor     edx, edx; Val
0x180025771  mov     r8d, 0A0h; Size
0x180025777  lea     rcx, [rsp+350h+var_2E0]; void *
0x18002577c  call    memset_0
0x180025781  xor     edx, edx; Val
0x180025783  mov     dword ptr [rsp+350h+Data], 0
0x18002578b  mov     r8d, 208h; Size
0x180025791  mov     dword ptr [rsp+350h+var_2EC], 0
0x180025799  lea     rcx, [rbp+250h+SubKey]; void *
0x18002579d  call    memset_0
0x1800257a2  test    rdi, rdi
0x1800257a5  jz      loc_180025927
0x1800257ab  cmp     esi, 2
0x1800257ae  jz      loc_180025927
0x1800257b4  mov     r12d, 1
0x1800257ba  cmp     cs:g_HijackSystemState, r12d
0x1800257c1  jnz     loc_180025927
0x1800257c7  mov     rcx, rdi
0x1800257ca  xor     ebx, ebx
0x1800257cc  call    hijackStoreRemove
0x1800257d1  lea     r9, [rbp+250h+SubKey]
0x1800257d5  mov     [rsp+350h+dwOptions], 208h
0x1800257dd  lea     r8, aParametersProb; "Parameters\\Probe"
0x1800257e4  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800257eb  lea     rcx, aDnscache_0; "Dnscache"
0x1800257f2  call    WxGetPersistedRegistryLocation
0x1800257f7  test    eax, eax
0x1800257f9  jns     short loc_180025807
0x1800257fb  mov     ecx, eax
0x1800257fd  call    WX_WIN32_FROM_HR
0x180025802  jmp     loc_180025903
0x180025807  mov     [rsp+350h+lpdwDisposition], rbx; lpdwDisposition
0x18002580c  lea     rax, [rsp+350h+hKey]
0x180025811  mov     [rsp+350h+phkResult], rax; phkResult
0x180025816  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x18002581a  mov     [rsp+350h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18002581f  xor     r9d, r9d; lpClass
0x180025822  mov     [rsp+350h+samDesired], 20006h; samDesired
0x18002582a  xor     r8d, r8d; Reserved
0x18002582d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025834  mov     [rsp+350h+dwOptions], ebx; dwOptions
0x180025838  call    cs:__imp_RegCreateKeyExW
0x18002583e  test    eax, eax
0x180025840  jnz     loc_180025903
0x180025846  lea     rdx, [rsp+350h+var_2E0]
0x18002584b  mov     rcx, rdi
0x18002584e  call    Dns_GuidToString
0x180025853  test    eax, eax
0x180025855  jz      loc_180025903
0x18002585b  mov     rcx, [rsp+350h+hKey]; hKey
0x180025860  lea     rdx, [rsp+350h+var_2E0]; lpSubKey
0x180025865  xor     eax, eax
0x180025867  xor     r9d, r9d; lpClass
0x18002586a  mov     [rsp+350h+lpdwDisposition], rax; lpdwDisposition
0x18002586f  xor     r8d, r8d; Reserved
0x180025872  mov     [rbp+250h+var_242], ax
0x180025876  lea     rax, [rsp+350h+var_300]
0x18002587b  mov     [rsp+350h+phkResult], rax; phkResult
0x180025880  mov     [rsp+350h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180025885  mov     [rsp+350h+samDesired], 20006h; samDesired
0x18002588d  mov     [rsp+350h+dwOptions], ebx; dwOptions
0x180025891  call    cs:__imp_RegCreateKeyExW
0x180025897  test    eax, eax
0x180025899  jnz     short loc_180025903
0x18002589b  mov     rcx, [rsp+350h+var_300]; hKey
0x1800258a0  lea     edi, [rax+4]
0x1800258a3  lea     rax, [rsp+350h+Data]
0x1800258a8  mov     [rsp+350h+samDesired], edi; cbData
0x1800258ac  mov     r9d, edi; dwType
0x1800258af  mov     qword ptr [rsp+350h+dwOptions], rax; lpData
0x1800258b4  xor     r8d, r8d; Reserved
0x1800258b7  mov     dword ptr [rsp+350h+Data], r14d
0x1800258bc  lea     rdx, aLastprobetime; "LastProbeTime"
0x1800258c3  call    cs:__imp_RegSetValueExW
0x1800258c9  test    eax, eax
0x1800258cb  jnz     short loc_180025903
0x1800258cd  mov     rcx, [rsp+350h+var_300]; hKey
0x1800258d2  lea     rdx, aNetworkperform; "NetworkPerformsHijacking"
0x1800258d9  cmp     esi, r12d
0x1800258dc  mov     [rsp+350h+samDesired], edi; cbData
0x1800258e0  mov     r9d, edi; dwType
0x1800258e3  setz    al
0x1800258e6  xor     r8d, r8d; Reserved
0x1800258e9  mov     dword ptr [rsp+350h+var_2EC], eax
0x1800258ed  lea     rax, [rsp+350h+var_2EC]
0x1800258f2  mov     qword ptr [rsp+350h+dwOptions], rax; lpData
0x1800258f7  call    cs:__imp_RegSetValueExW
0x1800258fd  test    eax, eax
0x1800258ff  cmovz   ebx, r12d
0x180025903  mov     rcx, [rsp+350h+var_300]; hKey
0x180025908  test    rcx, rcx
0x18002590b  jz      short loc_180025913
0x18002590d  call    cs:__imp_RegCloseKey
0x180025913  mov     rcx, [rsp+350h+hKey]; hKey
0x180025918  test    rcx, rcx
0x18002591b  jz      short loc_180025923
0x18002591d  call    cs:__imp_RegCloseKey
0x180025923  mov     eax, ebx
0x180025925  jmp     short loc_180025929
0x180025927  xor     eax, eax
0x180025929  mov     rcx, [rbp+250h+var_30]
0x180025930  xor     rcx, rsp; StackCookie
0x180025933  call    __security_check_cookie
0x180025938  mov     rbx, [rsp+350h+arg_10]
0x180025940  add     rsp, 330h
0x180025947  pop     r14
0x180025949  pop     r12
0x18002594b  pop     rdi
0x18002594c  pop     rsi
0x18002594d  pop     rbp
0x18002594e  retn
```
