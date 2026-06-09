# StRegisterCredProviders(void)

- ea: `0x18001d47c`
- end: `0x18001d6c4`
- name: `?StRegisterCredProviders@@YAKXZ`
- size: `584`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d920`
- `0x18001c080`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001d47c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d51f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d5a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d61f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d51f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d5a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d61f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d663`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d672`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d663`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d672`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d681`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d556`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d5d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d652`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d556`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d5d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d652`

## pseudocode

```c
__int64 StRegisterCredProviders(void)
{
  unsigned int v0; // ebx
  DWORD dwDisposition; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+38h] BYREF
  HKEY v5; // [rsp+98h] [rbp+40h] BYREF

  hKey = 0;
  phkResult = 0;
  v5 = 0;
  dwDisposition = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 58, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{07AA0886-CC8D-4e19-A410-1C75AF686E62}",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         &dwDisposition);
  if ( !v0 && (dwDisposition != 1 || (v0 = RegSetValueExW(hKey, 0, 0, 1u, L"OnexCredentialProvider", 0x2Cu)) == 0) )
  {
    v0 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{33c86cd6-705f-4ba1-9adb-67070b837775}",
           0,
           0,
           0,
           0x20006u,
           0,
           &phkResult,
           &dwDisposition);
    if ( !v0
      && (dwDisposition != 1
       || (v0 = RegSetValueExW(phkResult, 0, 0, 1u, L"OnexPlapSmartcardCredentialProvider", 0x46u)) == 0) )
    {
      v0 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provider Filters\\{edd749de-2ef1-4"
              "a80-98d1-81f20e6df58e}",
             0,
             0,
             0,
             0x20006u,
             0,
             &v5,
             &dwDisposition);
      if ( !v0 && dwDisposition == 1 )
        v0 = RegSetValueExW(v5, 0, 0, 1u, L"PlapLogonProviderFilter", 0x2Eu);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    RegCloseKey(v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 59, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x18001d47c  push    rbp
0x18001d47e  push    rbx
0x18001d47f  push    r12
0x18001d481  push    r14
0x18001d483  mov     rbp, rsp
0x18001d486  sub     rsp, 58h
0x18001d48a  mov     [rbp+hKey], 0
0x18001d492  mov     [rbp+arg_10], 0
0x18001d49a  mov     [rbp+arg_18], 0
0x18001d4a2  mov     [rbp+dwDisposition], 0
0x18001d4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4b0  lea     r14, WPP_GLOBAL_Control
0x18001d4b7  cmp     rcx, r14
0x18001d4ba  jz      short loc_18001D4DD
0x18001d4bc  cmp     byte ptr [rcx+19h], 4
0x18001d4c0  jb      short loc_18001D4DD
0x18001d4c2  test    byte ptr [rcx+1Ch], 1
0x18001d4c6  jz      short loc_18001D4DD
0x18001d4c8  mov     rcx, [rcx+10h]
0x18001d4cc  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d4d3  mov     edx, 3Ah ; ':'
0x18001d4d8  call    WPP_SF_
0x18001d4dd  lea     rax, [rbp+dwDisposition]
0x18001d4e1  mov     r12, 0FFFFFFFF80000002h
0x18001d4e8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18001d4ed  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d4f4  lea     rax, [rbp+hKey]
0x18001d4f8  xor     r9d, r9d; lpClass
0x18001d4fb  mov     [rsp+58h+phkResult], rax; phkResult
0x18001d500  xor     r8d, r8d; Reserved
0x18001d503  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d50c  mov     rcx, r12; hKey
0x18001d50f  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18001d517  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001d51f  call    cs:__imp_RegCreateKeyExW
0x18001d525  mov     ebx, eax
0x18001d527  test    eax, eax
0x18001d529  jnz     loc_18001D65A
0x18001d52f  cmp     [rbp+dwDisposition], 1
0x18001d533  jnz     short loc_18001D566
0x18001d535  mov     rcx, [rbp+hKey]; hKey
0x18001d539  lea     rax, aOnexcredential; "OnexCredentialProvider"
0x18001d540  mov     [rsp+58h+samDesired], 2Ch ; ','; cbData
0x18001d548  lea     r9d, [rbx+1]; dwType
0x18001d54c  xor     r8d, r8d; Reserved
0x18001d54f  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001d554  xor     edx, edx; lpValueName
0x18001d556  call    cs:__imp_RegSetValueExW
0x18001d55c  mov     ebx, eax
0x18001d55e  test    eax, eax
0x18001d560  jnz     loc_18001D65A
0x18001d566  lea     rax, [rbp+dwDisposition]
0x18001d56a  xor     r9d, r9d; lpClass
0x18001d56d  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18001d572  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d579  lea     rax, [rbp+arg_10]
0x18001d57d  xor     r8d, r8d; Reserved
0x18001d580  mov     [rsp+58h+phkResult], rax; phkResult
0x18001d585  mov     rcx, r12; hKey
0x18001d588  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d591  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18001d599  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001d5a1  call    cs:__imp_RegCreateKeyExW
0x18001d5a7  mov     ebx, eax
0x18001d5a9  test    eax, eax
0x18001d5ab  jnz     loc_18001D65A
0x18001d5b1  cmp     [rbp+dwDisposition], 1
0x18001d5b5  jnz     short loc_18001D5E4
0x18001d5b7  mov     rcx, [rbp+arg_10]; hKey
0x18001d5bb  lea     rax, aOnexplapsmartc; "OnexPlapSmartcardCredentialProvider"
0x18001d5c2  mov     [rsp+58h+samDesired], 46h ; 'F'; cbData
0x18001d5ca  lea     r9d, [rbx+1]; dwType
0x18001d5ce  xor     r8d, r8d; Reserved
0x18001d5d1  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001d5d6  xor     edx, edx; lpValueName
0x18001d5d8  call    cs:__imp_RegSetValueExW
0x18001d5de  mov     ebx, eax
0x18001d5e0  test    eax, eax
0x18001d5e2  jnz     short loc_18001D65A
0x18001d5e4  lea     rax, [rbp+dwDisposition]
0x18001d5e8  xor     r9d, r9d; lpClass
0x18001d5eb  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18001d5f0  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d5f7  lea     rax, [rbp+arg_18]
0x18001d5fb  xor     r8d, r8d; Reserved
0x18001d5fe  mov     [rsp+58h+phkResult], rax; phkResult
0x18001d603  mov     rcx, r12; hKey
0x18001d606  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d60f  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18001d617  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001d61f  call    cs:__imp_RegCreateKeyExW
0x18001d625  mov     ebx, eax
0x18001d627  test    eax, eax
0x18001d629  jnz     short loc_18001D65A
0x18001d62b  cmp     [rbp+dwDisposition], 1
0x18001d62f  jnz     short loc_18001D65A
0x18001d631  mov     rcx, [rbp+arg_18]; hKey
0x18001d635  lea     rax, aPlaplogonprovi; "PlapLogonProviderFilter"
0x18001d63c  mov     [rsp+58h+samDesired], 2Eh ; '.'; cbData
0x18001d644  lea     r9d, [rbx+1]; dwType
0x18001d648  xor     r8d, r8d; Reserved
0x18001d64b  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001d650  xor     edx, edx; lpValueName
0x18001d652  call    cs:__imp_RegSetValueExW
0x18001d658  mov     ebx, eax
0x18001d65a  mov     rcx, [rbp+hKey]; hKey
0x18001d65e  test    rcx, rcx
0x18001d661  jz      short loc_18001D669
0x18001d663  call    cs:__imp_RegCloseKey
0x18001d669  mov     rcx, [rbp+arg_10]; hKey
0x18001d66d  test    rcx, rcx
0x18001d670  jz      short loc_18001D678
0x18001d672  call    cs:__imp_RegCloseKey
0x18001d678  mov     rcx, [rbp+arg_18]; hKey
0x18001d67c  test    rcx, rcx
0x18001d67f  jz      short loc_18001D687
0x18001d681  call    cs:__imp_RegCloseKey
0x18001d687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d68e  cmp     rcx, r14
0x18001d691  jz      short loc_18001D6B7
0x18001d693  cmp     byte ptr [rcx+19h], 4
0x18001d697  jb      short loc_18001D6B7
0x18001d699  test    byte ptr [rcx+1Ch], 1
0x18001d69d  jz      short loc_18001D6B7
0x18001d69f  mov     rcx, [rcx+10h]
0x18001d6a3  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d6aa  mov     edx, 3Bh ; ';'
0x18001d6af  mov     r9d, ebx
0x18001d6b2  call    WPP_SF_d
0x18001d6b7  mov     eax, ebx
0x18001d6b9  add     rsp, 58h
0x18001d6bd  pop     r14
0x18001d6bf  pop     r12
0x18001d6c1  pop     rbx
0x18001d6c2  pop     rbp
0x18001d6c3  retn
```
