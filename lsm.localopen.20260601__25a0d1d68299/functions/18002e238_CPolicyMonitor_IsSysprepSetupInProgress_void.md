# CPolicyMonitor::IsSysprepSetupInProgress(void)

- ea: `0x18002e238`
- end: `0x18002e3e1`
- name: `?IsSysprepSetupInProgress@CPolicyMonitor@@AEAAHXZ`
- size: `425`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180054be4`

## callees

- `0x1800077a0`
- `0x18002e238`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e2d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e2d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e312`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e36c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e312`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e36c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e39e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e39e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002e2a5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002e2a5`

## string_xrefs

- `0x18002e3ae`: `Unable to open TS_SYSPREP key value 0x%x`

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
0x18002e238  push    rbp
0x18002e23a  push    rbx
0x18002e23b  push    rdi
0x18002e23c  push    r14
0x18002e23e  lea     rbp, [rsp-168h]
0x18002e246  sub     rsp, 268h
0x18002e24d  mov     rax, cs:__security_cookie
0x18002e254  xor     rax, rsp
0x18002e257  mov     [rbp+180h+var_30], rax
0x18002e25e  lea     rdi, aSystemSetup; "SYSTEM\\Setup"
0x18002e265  mov     dword ptr [rsp+280h+Data], 0
0x18002e26d  mov     r14d, 4
0x18002e273  mov     [rsp+280h+hKey], 0
0x18002e27c  xor     ebx, ebx
0x18002e27e  mov     [rsp+280h+Type], 0
0x18002e286  mov     rdx, rdi
0x18002e289  mov     [rsp+280h+cbData], r14d
0x18002e28e  mov     r9d, 200h
0x18002e294  mov     [rsp+280h+phkResult], rbx
0x18002e299  lea     r8, [rsp+280h+var_230]
0x18002e29e  lea     rcx, aSystemsetup; "SystemSetup"
0x18002e2a5  call    cs:__imp_GetPersistedRegistryLocationW
0x18002e2ac  nop     dword ptr [rax+rax+00h]
0x18002e2b1  lea     rdx, [rsp+280h+var_230]
0x18002e2b6  mov     r9d, 20019h; samDesired
0x18002e2bc  test    eax, eax
0x18002e2be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e2c5  lea     rax, [rsp+280h+hKey]
0x18002e2ca  cmovnz  rdx, rdi; lpSubKey
0x18002e2ce  mov     [rsp+280h+phkResult], rax; phkResult
0x18002e2d3  xor     r8d, r8d; ulOptions
0x18002e2d6  call    cs:__imp_RegOpenKeyExW
0x18002e2dd  nop     dword ptr [rax+rax+00h]
0x18002e2e2  test    eax, eax
0x18002e2e4  jnz     loc_18002E3AC
0x18002e2ea  mov     rcx, [rsp+280h+hKey]; hKey
0x18002e2ef  lea     rax, [rsp+280h+cbData]
0x18002e2f4  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002e2f9  lea     r9, [rsp+280h+Type]; lpType
0x18002e2fe  lea     rax, [rsp+280h+Data]
0x18002e303  xor     r8d, r8d; lpReserved
0x18002e306  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18002e30d  mov     [rsp+280h+phkResult], rax; lpData
0x18002e312  call    cs:__imp_RegQueryValueExW
0x18002e319  nop     dword ptr [rax+rax+00h]
0x18002e31e  test    eax, eax
0x18002e320  jnz     short loc_18002E32D
0x18002e322  cmp     dword ptr [rsp+280h+Data], ebx
0x18002e326  jz      short loc_18002E33F
0x18002e328  lea     edi, [rbx+1]
0x18002e32b  jmp     short loc_18002E399
0x18002e32d  mov     r8d, eax
0x18002e330  lea     rdx, aUnableToQueryT; "Unable to query TS_SYSPREP_INPROGRESS v"...
0x18002e337  mov     ecx, r14d; int
0x18002e33a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e33f  mov     rcx, [rsp+280h+hKey]; hKey
0x18002e344  lea     rax, [rsp+280h+cbData]
0x18002e349  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002e34e  lea     r9, [rsp+280h+Type]; lpType
0x18002e353  lea     rax, [rsp+280h+Data]
0x18002e358  mov     [rsp+280h+cbData], r14d
0x18002e35d  xor     r8d, r8d; lpReserved
0x18002e360  mov     [rsp+280h+phkResult], rax; lpData
0x18002e365  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x18002e36c  call    cs:__imp_RegQueryValueExW
0x18002e373  nop     dword ptr [rax+rax+00h]
0x18002e378  test    eax, eax
0x18002e37a  jnz     short loc_18002E385
0x18002e37c  cmp     dword ptr [rsp+280h+Data], ebx
0x18002e380  setnz   bl
0x18002e383  jmp     short loc_18002E397
0x18002e385  mov     r8d, eax
0x18002e388  lea     rdx, aUnableToQueryT_0; "Unable to query TS_OOBE_INPROGRESS valu"...
0x18002e38f  mov     ecx, r14d; int
0x18002e392  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e397  xor     edi, edi
0x18002e399  mov     rcx, [rsp+280h+hKey]; hKey
0x18002e39e  call    cs:__imp_RegCloseKey
0x18002e3a5  nop     dword ptr [rax+rax+00h]
0x18002e3aa  jmp     short loc_18002E3C0
0x18002e3ac  xor     edi, edi
0x18002e3ae  lea     rdx, aUnableToOpenTs; "Unable to open TS_SYSPREP key value 0x%"...
0x18002e3b5  mov     r8d, eax
0x18002e3b8  mov     ecx, r14d; int
0x18002e3bb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e3c0  or      ebx, edi
0x18002e3c2  mov     eax, ebx
0x18002e3c4  mov     rcx, [rbp+180h+var_30]
0x18002e3cb  xor     rcx, rsp; StackCookie
0x18002e3ce  call    __security_check_cookie
0x18002e3d3  add     rsp, 268h
0x18002e3da  pop     r14
0x18002e3dc  pop     rdi
0x18002e3dd  pop     rbx
0x18002e3de  pop     rbp
0x18002e3df  retn
```
