# wmain$catch$5

- ea: `0x140011b91`
- end: `0x140011cd1`
- name: `wmain$catch$5`
- size: `320`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400035b8`
- `0x14000c894`
- `0x140011b91`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011bee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011c01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011c01`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140011c76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140011c76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011cb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011cb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011c2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011c2c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x140011bcd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x140011bcd`

## string_xrefs

- `0x140011bc6`: `AdapterCacheKeyID`

## pseudocode

```c
__int64 __fastcall wmain_catch_5(__int64 a1, __int64 a2)
{
  int PersistedRegistryLocationW; // eax
  HKEY v4; // rdi
  DWORD LastError; // ebx
  LSTATUS v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  HKEY v10; // rcx

  *(_QWORD *)(a2 + 80) = 0;
  *(_BYTE *)(a2 + 64) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"AdapterCacheKeyID",
                                 L"Software\\Microsoft\\DirectX",
                                 a2 + 112,
                                 520,
                                 0);
  *(_DWORD *)(a2 + 68) = PersistedRegistryLocationW;
  *(_DWORD *)(a2 + 72) = 0;
  if ( !PersistedRegistryLocationW )
  {
    v4 = *(HKEY *)(a2 + 80);
    if ( v4 )
    {
      LastError = GetLastError();
      RegCloseKey(v4);
      SetLastError(LastError);
    }
    *(_QWORD *)(a2 + 80) = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)(a2 + 112), 0, 0x20019u, (PHKEY)(a2 + 80));
    *(_DWORD *)(a2 + 72) = v6;
    if ( !v6 )
    {
      *(_QWORD *)(a2 + 96) = 0;
      *(_DWORD *)(a2 + 88) = 8;
      if ( !RegGetValueW(*(HKEY *)(a2 + 80), 0, L"LastSeen", 0x40u, 0, (PVOID)(a2 + 96), (LPDWORD)(a2 + 88))
        && (*(_DWORD *)(a2 + 100) || *(_DWORD *)(a2 + 96)) )
      {
        *(_BYTE *)(a2 + 64) = 1;
      }
    }
  }
  DXGIAdapterCacheTelemetry::ExistingRegValueOnFailure<long &,long &,bool &>(
    (int *)(a2 + 68),
    (int *)(a2 + 72),
    (char *)(a2 + 64));
  *(_DWORD *)(a2 + 68) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 664),
                           v7,
                           v8,
                           v9);
  v10 = *(HKEY *)(a2 + 80);
  if ( v10 )
    RegCloseKey(v10);
  return 0;
}

```

## disassembly

```asm
0x140011b91  mov     [rsp+arg_8], rdx
0x140011b96  push    rbx
0x140011b97  push    rbp
0x140011b98  push    rdi
0x140011b99  sub     rsp, 40h
0x140011b9d  mov     rbp, rdx
0x140011ba0  mov     qword ptr [rbp+50h], 0
0x140011ba8  mov     byte ptr [rbp+40h], 0
0x140011bac  mov     [rsp+58h+phkResult], 0
0x140011bb5  mov     r9d, 208h
0x140011bbb  lea     r8, [rbp+70h]
0x140011bbf  lea     rdx, ?RegistryLocation@AdapterCacheUpdate@@0QBGB; "Software\\Microsoft\\DirectX"
0x140011bc6  lea     rcx, ?StateSeparationMapSourceID@AdapterCacheUpdate@@0QBGB; "AdapterCacheKeyID"
0x140011bcd  call    cs:__imp_GetPersistedRegistryLocationW
0x140011bd3  mov     [rbp+44h], eax
0x140011bd6  mov     dword ptr [rbp+48h], 0
0x140011bdd  test    eax, eax
0x140011bdf  jnz     loc_140011C8E
0x140011be5  mov     rdi, [rbp+50h]
0x140011be9  test    rdi, rdi
0x140011bec  jz      short loc_140011C07
0x140011bee  call    cs:__imp_GetLastError
0x140011bf4  mov     ebx, eax
0x140011bf6  mov     rcx, rdi; hKey
0x140011bf9  call    cs:__imp_RegCloseKey
0x140011bff  mov     ecx, ebx; dwErrCode
0x140011c01  call    cs:__imp_SetLastError
0x140011c07  mov     qword ptr [rbp+50h], 0
0x140011c0f  lea     rax, [rbp+50h]
0x140011c13  mov     [rsp+58h+phkResult], rax; phkResult
0x140011c18  mov     r9d, 20019h; samDesired
0x140011c1e  xor     r8d, r8d; ulOptions
0x140011c21  lea     rdx, [rbp+70h]; lpSubKey
0x140011c25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011c2c  call    cs:__imp_RegOpenKeyExW
0x140011c32  mov     [rbp+48h], eax
0x140011c35  test    eax, eax
0x140011c37  jnz     short loc_140011C8E
0x140011c39  mov     qword ptr [rbp+60h], 0
0x140011c41  mov     dword ptr [rbp+58h], 8
0x140011c48  lea     rax, [rbp+58h]
0x140011c4c  mov     [rsp+58h+pcbData], rax; pcbData
0x140011c51  lea     rax, [rbp+60h]
0x140011c55  mov     [rsp+58h+pvData], rax; pvData
0x140011c5a  mov     [rsp+58h+phkResult], 0; pdwType
0x140011c63  mov     r9d, 40h ; '@'; dwFlags
0x140011c69  lea     r8, aLastseen; "LastSeen"
0x140011c70  xor     edx, edx; lpSubKey
0x140011c72  mov     rcx, [rbp+50h]; hkey
0x140011c76  call    cs:__imp_RegGetValueW
0x140011c7c  test    eax, eax
0x140011c7e  jnz     short loc_140011C8E
0x140011c80  cmp     [rbp+64h], eax
0x140011c83  jnz     short loc_140011C8A
0x140011c85  cmp     [rbp+60h], eax
0x140011c88  jz      short loc_140011C8E
0x140011c8a  mov     byte ptr [rbp+40h], 1
0x140011c8e  lea     r8, [rbp+40h]
0x140011c92  lea     rdx, [rbp+48h]
0x140011c96  lea     rcx, [rbp+44h]
0x140011c9a  call    ??$ExistingRegValueOnFailure@AEAJAEAJAEA_N@DXGIAdapterCacheTelemetry@@SAXAEAJ0AEA_N@Z; DXGIAdapterCacheTelemetry::ExistingRegValueOnFailure<long &,long &,bool &>(long &,long &,bool &)
0x140011c9f  mov     rcx, [rbp+298h]; this
0x140011ca6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140011cab  mov     [rbp+44h], eax
0x140011cae  mov     rcx, [rbp+50h]; hKey
0x140011cb2  test    rcx, rcx
0x140011cb5  jz      short loc_140011CBE
0x140011cb7  call    cs:__imp_RegCloseKey
0x140011cbd  nop
0x140011cbe  mov     rax, 0
0x140011cc8  add     rsp, 40h
0x140011ccc  pop     rdi
0x140011ccd  pop     rbp
0x140011cce  pop     rbx
0x140011ccf  retn
```
