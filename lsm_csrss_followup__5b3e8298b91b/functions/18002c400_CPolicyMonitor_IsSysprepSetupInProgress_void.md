# CPolicyMonitor::IsSysprepSetupInProgress(void)

- ea: `0x18002c400`
- end: `0x18002c58a`
- name: `?IsSysprepSetupInProgress@CPolicyMonitor@@AEAAHXZ`
- size: `394`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180051464`

## callees

- `0x1800074c0`
- `0x18002c400`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c498`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c498`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c4ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c522`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c4ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c522`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c54e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c54e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002c46d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002c46d`

## string_xrefs

- `0x18002c558`: `Unable to open TS_SYSPREP key value 0x%x`

## pseudocode

```c
__int64 __fastcall CPolicyMonitor::IsSysprepSetupInProgress(CPolicyMonitor *this)
{
  unsigned int v1; // ebx
  int PersistedRegistryLocationW; // eax
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  int v6; // edi
  LSTATUS v7; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[512]; // [rsp+50h] [rbp-B0h] BYREF

  *(_DWORD *)Data = 0;
  hKey = 0;
  v1 = 0;
  Type = 0;
  cbData = 4;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"SystemSetup", L"SYSTEM\\Setup", v13, 512, 0);
  v3 = (const WCHAR *)v13;
  if ( PersistedRegistryLocationW )
    v3 = L"SYSTEM\\Setup";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    v6 = 0;
    _DbgPrintMessage(4, "Unable to open TS_SYSPREP key value 0x%x", v4);
    return v6 | v1;
  }
  v5 = RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, &Type, Data, &cbData);
  if ( v5 )
  {
    _DbgPrintMessage(4, "Unable to query TS_SYSPREP_INPROGRESS value 0x%x", v5);
    goto LABEL_8;
  }
  if ( !*(_DWORD *)Data )
  {
LABEL_8:
    cbData = 4;
    v7 = RegQueryValueExW(hKey, L"OOBEInProgress", 0, &Type, Data, &cbData);
    if ( v7 )
      _DbgPrintMessage(4, "Unable to query TS_OOBE_INPROGRESS value 0x%x", v7);
    else
      LOBYTE(v1) = *(_DWORD *)Data != 0;
    v6 = 0;
    goto LABEL_12;
  }
  v6 = 1;
LABEL_12:
  RegCloseKey(hKey);
  return v6 | v1;
}

```

## disassembly

```asm
0x18002c400  push    rbp
0x18002c402  push    rbx
0x18002c403  push    rdi
0x18002c404  push    r14
0x18002c406  lea     rbp, [rsp-168h]
0x18002c40e  sub     rsp, 268h
0x18002c415  mov     rax, cs:__security_cookie
0x18002c41c  xor     rax, rsp
0x18002c41f  mov     [rbp+180h+var_30], rax
0x18002c426  lea     rdi, aSystemSetup; "SYSTEM\\Setup"
0x18002c42d  mov     dword ptr [rsp+280h+Data], 0
0x18002c435  mov     r14d, 4
0x18002c43b  mov     [rsp+280h+hKey], 0
0x18002c444  xor     ebx, ebx
0x18002c446  mov     [rsp+280h+Type], 0
0x18002c44e  mov     rdx, rdi
0x18002c451  mov     [rsp+280h+cbData], r14d
0x18002c456  mov     r9d, 200h
0x18002c45c  mov     [rsp+280h+phkResult], rbx
0x18002c461  lea     r8, [rsp+280h+var_230]
0x18002c466  lea     rcx, aSystemsetup; "SystemSetup"
0x18002c46d  call    cs:__imp_GetPersistedRegistryLocationW
0x18002c473  lea     rdx, [rsp+280h+var_230]
0x18002c478  mov     r9d, 20019h; samDesired
0x18002c47e  test    eax, eax
0x18002c480  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c487  lea     rax, [rsp+280h+hKey]
0x18002c48c  cmovnz  rdx, rdi; lpSubKey
0x18002c490  mov     [rsp+280h+phkResult], rax; phkResult
0x18002c495  xor     r8d, r8d; ulOptions
0x18002c498  call    cs:__imp_RegOpenKeyExW
0x18002c49e  test    eax, eax
0x18002c4a0  jnz     loc_18002C556
0x18002c4a6  mov     rcx, [rsp+280h+hKey]; hKey
0x18002c4ab  lea     rax, [rsp+280h+cbData]
0x18002c4b0  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002c4b5  lea     r9, [rsp+280h+Type]; lpType
0x18002c4ba  lea     rax, [rsp+280h+Data]
0x18002c4bf  xor     r8d, r8d; lpReserved
0x18002c4c2  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18002c4c9  mov     [rsp+280h+phkResult], rax; lpData
0x18002c4ce  call    cs:__imp_RegQueryValueExW
0x18002c4d4  test    eax, eax
0x18002c4d6  jnz     short loc_18002C4E3
0x18002c4d8  cmp     dword ptr [rsp+280h+Data], ebx
0x18002c4dc  jz      short loc_18002C4F5
0x18002c4de  lea     edi, [rbx+1]
0x18002c4e1  jmp     short loc_18002C549
0x18002c4e3  mov     r8d, eax
0x18002c4e6  lea     rdx, aUnableToQueryT; "Unable to query TS_SYSPREP_INPROGRESS v"...
0x18002c4ed  mov     ecx, r14d; int
0x18002c4f0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c4f5  mov     rcx, [rsp+280h+hKey]; hKey
0x18002c4fa  lea     rax, [rsp+280h+cbData]
0x18002c4ff  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002c504  lea     r9, [rsp+280h+Type]; lpType
0x18002c509  lea     rax, [rsp+280h+Data]
0x18002c50e  mov     [rsp+280h+cbData], r14d
0x18002c513  xor     r8d, r8d; lpReserved
0x18002c516  mov     [rsp+280h+phkResult], rax; lpData
0x18002c51b  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x18002c522  call    cs:__imp_RegQueryValueExW
0x18002c528  test    eax, eax
0x18002c52a  jnz     short loc_18002C535
0x18002c52c  cmp     dword ptr [rsp+280h+Data], ebx
0x18002c530  setnz   bl
0x18002c533  jmp     short loc_18002C547
0x18002c535  mov     r8d, eax
0x18002c538  lea     rdx, aUnableToQueryT_0; "Unable to query TS_OOBE_INPROGRESS valu"...
0x18002c53f  mov     ecx, r14d; int
0x18002c542  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c547  xor     edi, edi
0x18002c549  mov     rcx, [rsp+280h+hKey]; hKey
0x18002c54e  call    cs:__imp_RegCloseKey
0x18002c554  jmp     short loc_18002C56A
0x18002c556  xor     edi, edi
0x18002c558  lea     rdx, aUnableToOpenTs; "Unable to open TS_SYSPREP key value 0x%"...
0x18002c55f  mov     r8d, eax
0x18002c562  mov     ecx, r14d; int
0x18002c565  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c56a  or      ebx, edi
0x18002c56c  mov     eax, ebx
0x18002c56e  mov     rcx, [rbp+180h+var_30]
0x18002c575  xor     rcx, rsp; StackCookie
0x18002c578  call    __security_check_cookie
0x18002c57d  add     rsp, 268h
0x18002c584  pop     r14
0x18002c586  pop     rdi
0x18002c587  pop     rbx
0x18002c588  pop     rbp
0x18002c589  retn
```
