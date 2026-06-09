# I_CertSetAutoUpdateCtl

- ea: `0x180038b9c`
- end: `0x180038e09`
- name: `I_CertSetAutoUpdateCtl`
- size: `621`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, unsigned int, __int64, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18001cf28`
- `0x180039430`
- `0x18003ac04`

## callees

- `0x180028d60`
- `0x1800352b8`
- `0x1800353c8`
- `0x180037114`
- `0x180038b9c`
- `0x180038e10`
- `0x1801150c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038d5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038dfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038d9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038dfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038c8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038c8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038de6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038bfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038bfa`
- `RPCRT4!RpcRevertToSelf` at `0x180038d6f`
- `RPCRT4!RpcRevertToSelf` at `0x180038d6f`
- `RPCRT4!RpcImpersonateClient` at `0x180038d1a`
- `RPCRT4!RpcImpersonateClient` at `0x180038d1a`

## pseudocode

```c
__int64 __fastcall I_CertSetAutoUpdateCtl(RPC_BINDING_HANDLE BindingHandle, unsigned int a2, __int64 a3, int *a4)
{
  int v4; // ebx
  HKEY v7; // rsi
  int v8; // edi
  const WCHAR *v9; // r15
  const WCHAR *v10; // rbx
  HKEY AutoUpdateKey; // rax
  HKEY v12; // rbp
  unsigned int v13; // r14d
  HKEY v14; // rcx
  LSTATUS v15; // eax
  RPC_STATUS v17; // eax
  DWORD LastError; // ebx
  int v19; // [rsp+30h] [rbp-58h]
  size_t Size; // [rsp+38h] [rbp-50h] BYREF
  void *Buf1; // [rsp+40h] [rbp-48h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-40h] BYREF

  SystemTimeAsFileTime = 0;
  v4 = 0;
  v19 = 0;
  Buf1 = 0;
  LODWORD(Size) = 0;
  v7 = 0;
  v8 = 0;
  switch ( a2 )
  {
    case 5u:
      v9 = L"LastSyncTime";
      v10 = L"EncodedCtl";
      break;
    case 6u:
      v9 = L"DisallowedCertLastSyncTime";
      v10 = L"DisallowedCertEncodedCtl";
      break;
    case 7u:
      v9 = L"PinRulesLastSyncTime";
      v10 = L"PinRulesEncodedCtl";
      break;
    default:
      v12 = 0;
      SetLastError(0x80070057);
      goto LABEL_21;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  AutoUpdateKey = (HKEY)CreateAutoUpdateKey(-2147483646);
  v12 = AutoUpdateKey;
  if ( !AutoUpdateKey )
  {
LABEL_25:
    v4 = 0;
    goto LABEL_21;
  }
  v13 = 1;
  if ( !(unsigned int)I_CertReadBINARYValueFromRegistry(AutoUpdateKey, v10)
    || (_DWORD)Size != *(_DWORD *)(a3 + 16)
    || memcmp_0(Buf1, *(const void **)(a3 + 8), (unsigned int)Size) )
  {
    v15 = RegSetValueExW(v12, v10, 0, 3u, *(const BYTE **)(a3 + 8), *(_DWORD *)(a3 + 16));
    if ( v15 )
    {
LABEL_30:
      SetLastError(v15);
      v4 = v19;
      goto LABEL_21;
    }
    v8 = 1;
    goto LABEL_8;
  }
  if ( !BindingHandle )
  {
LABEL_8:
    v14 = v12;
    v4 = 0;
    goto LABEL_9;
  }
  Size = 0;
  if ( !(unsigned int)GetAutoUpdateLastSyncTime(-2147483646, a2, &Size) )
  {
    v8 = 0;
    goto LABEL_8;
  }
  v17 = RpcImpersonateClient(BindingHandle);
  if ( v17 )
  {
    SetLastError(v17);
    v8 = 0;
    goto LABEL_25;
  }
  v4 = 1;
  v19 = 1;
  v7 = (HKEY)CreateAutoUpdateKey(-2147483646);
  if ( v7 || (v7 = (HKEY)CreateAutoUpdateKey(-2147483647)) != 0 )
  {
    v14 = v7;
    v8 = 0;
LABEL_9:
    v15 = RegSetValueExW(v14, v9, 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
    if ( !v15 )
      goto LABEL_10;
    goto LABEL_30;
  }
  v8 = 0;
LABEL_21:
  v13 = 0;
LABEL_10:
  if ( v4 )
  {
    LastError = GetLastError();
    CloseRegistryKey(v7);
    RpcRevertToSelf();
    SetLastError(LastError);
  }
  CloseRegistryKey(v12);
  PkiDefaultCryptFree(Buf1);
  *a4 = v8;
  return v13;
}

```

## disassembly

```asm
0x180038b9c  mov     r11, rsp
0x180038b9f  mov     [r11+8], rbx
0x180038ba3  mov     [r11+20h], r9
0x180038ba7  mov     [rsp+arg_8], edx
0x180038bab  push    rbp
0x180038bac  push    rsi
0x180038bad  push    rdi
0x180038bae  push    r12
0x180038bb0  push    r13
0x180038bb2  push    r14
0x180038bb4  push    r15
0x180038bb6  sub     rsp, 50h
0x180038bba  xor     r14d, r14d
0x180038bbd  mov     eax, edx
0x180038bbf  mov     [r11-40h], r14
0x180038bc3  mov     ebx, r14d
0x180038bc6  mov     [rsp+88h+var_58], ebx
0x180038bca  mov     r13, r8
0x180038bcd  mov     [r11-48h], r14
0x180038bd1  mov     r12, rcx
0x180038bd4  mov     [r11-50h], r14d
0x180038bd8  mov     esi, r14d
0x180038bdb  mov     edi, r14d
0x180038bde  sub     eax, 5
0x180038be1  jnz     loc_180038CDB
0x180038be7  lea     r15, aLastsynctime; "LastSyncTime"
0x180038bee  lea     rbx, aEncodedctl; "EncodedCtl"
0x180038bf5  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180038bfa  call    cs:__imp_GetSystemTimeAsFileTime
0x180038c00  mov     rcx, 0FFFFFFFF80000002h
0x180038c07  call    _CreateAutoUpdateKey
0x180038c0c  mov     rbp, rax
0x180038c0f  test    rax, rax
0x180038c12  jz      loc_180038DA6
0x180038c18  lea     r9, [rsp+88h+Size]
0x180038c1d  mov     rdx, rbx; lpValueName
0x180038c20  lea     r8, [rsp+88h+Buf1]
0x180038c25  mov     rcx, rax; hKey
0x180038c28  call    I_CertReadBINARYValueFromRegistry
0x180038c2d  mov     r14d, 1
0x180038c33  test    eax, eax
0x180038c35  jz      loc_180038DC6
0x180038c3b  mov     eax, dword ptr [rsp+88h+Size]
0x180038c3f  cmp     eax, [r13+10h]
0x180038c43  jnz     loc_180038DC6
0x180038c49  mov     rdx, [r13+8]; Buf2
0x180038c4d  mov     r8d, eax; Size
0x180038c50  mov     rcx, [rsp+88h+Buf1]; Buf1
0x180038c55  call    memcmp_0
0x180038c5a  test    eax, eax
0x180038c5c  jnz     loc_180038DC6
0x180038c62  test    r12, r12
0x180038c65  jnz     loc_180038CF3
0x180038c6b  mov     rcx, rbp; hKey
0x180038c6e  mov     ebx, esi
0x180038c70  lea     rax, [rsp+88h+SystemTimeAsFileTime]
0x180038c75  mov     [rsp+88h+cbData], 8; cbData
0x180038c7d  mov     r9d, 3; dwType
0x180038c83  mov     [rsp+88h+lpData], rax; lpData
0x180038c88  xor     r8d, r8d; Reserved
0x180038c8b  mov     rdx, r15; lpValueName
0x180038c8e  call    cs:__imp_RegSetValueExW
0x180038c94  test    eax, eax
0x180038c96  jnz     loc_180038DF8
0x180038c9c  test    ebx, ebx
0x180038c9e  jnz     loc_180038D5F
0x180038ca4  mov     rcx, rbp; hKey
0x180038ca7  call    _CloseRegistryKey
0x180038cac  mov     rcx, [rsp+88h+Buf1]; hMem
0x180038cb1  call    PkiDefaultCryptFree
0x180038cb6  mov     rax, [rsp+88h+arg_18]
0x180038cbe  mov     rbx, [rsp+88h+arg_0]
0x180038cc6  mov     [rax], edi
0x180038cc8  mov     eax, r14d
0x180038ccb  add     rsp, 50h
0x180038ccf  pop     r15
0x180038cd1  pop     r14
0x180038cd3  pop     r13
0x180038cd5  pop     r12
0x180038cd7  pop     rdi
0x180038cd8  pop     rsi
0x180038cd9  pop     rbp
0x180038cda  retn
0x180038cdb  sub     eax, 1
0x180038cde  jnz     short loc_180038D45
0x180038ce0  lea     r15, aDisallowedcert_3; "DisallowedCertLastSyncTime"
0x180038ce7  lea     rbx, aDisallowedcert_0; "DisallowedCertEncodedCtl"
0x180038cee  jmp     loc_180038BF5
0x180038cf3  mov     edx, [rsp+88h+arg_8]
0x180038cfa  lea     r8, [rsp+88h+Size]
0x180038cff  mov     rdi, 0FFFFFFFF80000002h
0x180038d06  mov     [rsp+88h+Size], rsi
0x180038d0b  mov     rcx, rdi
0x180038d0e  call    _GetAutoUpdateLastSyncTime
0x180038d13  test    eax, eax
0x180038d15  jz      short loc_180038D82
0x180038d17  mov     rcx, r12; BindingHandle
0x180038d1a  call    cs:__imp_RpcImpersonateClient
0x180038d20  test    eax, eax
0x180038d22  jnz     short loc_180038D9C
0x180038d24  mov     ebx, r14d
0x180038d27  mov     rcx, rdi
0x180038d2a  mov     [rsp+88h+var_58], ebx
0x180038d2e  call    _CreateAutoUpdateKey
0x180038d33  mov     rsi, rax
0x180038d36  test    rax, rax
0x180038d39  jz      short loc_180038DAA
0x180038d3b  mov     rcx, rsi
0x180038d3e  xor     edi, edi
0x180038d40  jmp     loc_180038C70
0x180038d45  cmp     eax, 1
0x180038d48  jz      short loc_180038D89
0x180038d4a  xor     ebp, ebp
0x180038d4c  mov     ecx, 80070057h; dwErrCode
0x180038d51  call    cs:__imp_SetLastError
0x180038d57  xor     r14d, r14d
0x180038d5a  jmp     loc_180038C9C
0x180038d5f  call    cs:__imp_GetLastError
0x180038d65  mov     rcx, rsi; hKey
0x180038d68  mov     ebx, eax
0x180038d6a  call    _CloseRegistryKey
0x180038d6f  call    cs:__imp_RpcRevertToSelf
0x180038d75  mov     ecx, ebx; dwErrCode
0x180038d77  call    cs:__imp_SetLastError
0x180038d7d  jmp     loc_180038CA4
0x180038d82  xor     edi, edi
0x180038d84  jmp     loc_180038C6B
0x180038d89  lea     r15, aPinruleslastsy; "PinRulesLastSyncTime"
0x180038d90  lea     rbx, aPinrulesencode; "PinRulesEncodedCtl"
0x180038d97  jmp     loc_180038BF5
0x180038d9c  mov     ecx, eax; dwErrCode
0x180038d9e  call    cs:__imp_SetLastError
0x180038da4  xor     edi, edi
0x180038da6  mov     ebx, esi
0x180038da8  jmp     short loc_180038D57
0x180038daa  mov     rcx, 0FFFFFFFF80000001h
0x180038db1  call    _CreateAutoUpdateKey
0x180038db6  mov     rsi, rax
0x180038db9  test    rax, rax
0x180038dbc  jnz     loc_180038D3B
0x180038dc2  xor     edi, edi
0x180038dc4  jmp     short loc_180038D57
0x180038dc6  mov     eax, [r13+10h]
0x180038dca  mov     r9d, 3; dwType
0x180038dd0  mov     [rsp+88h+cbData], eax; cbData
0x180038dd4  xor     r8d, r8d; Reserved
0x180038dd7  mov     rax, [r13+8]
0x180038ddb  mov     rdx, rbx; lpValueName
0x180038dde  mov     rcx, rbp; hKey
0x180038de1  mov     [rsp+88h+lpData], rax; lpData
0x180038de6  call    cs:__imp_RegSetValueExW
0x180038dec  test    eax, eax
0x180038dee  jnz     short loc_180038DF8
0x180038df0  mov     edi, r14d
0x180038df3  jmp     loc_180038C6B
0x180038df8  mov     ecx, eax; dwErrCode
0x180038dfa  call    cs:__imp_SetLastError
0x180038e00  mov     ebx, [rsp+88h+var_58]
0x180038e04  jmp     loc_180038D57
```
