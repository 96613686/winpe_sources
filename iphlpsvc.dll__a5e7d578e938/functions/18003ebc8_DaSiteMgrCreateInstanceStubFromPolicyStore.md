# DaSiteMgrCreateInstanceStubFromPolicyStore

- ea: `0x18003ebc8`
- end: `0x18003ed76`
- name: `DaSiteMgrCreateInstanceStubFromPolicyStore`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a940`

## callees

- `0x180012dcc`
- `0x18002b47c`
- `0x18003ebc8`
- `0x18003ed7c`
- `0x18004c188`
- `0x1800769f8`
- `0x180076b58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec87`

## pseudocode

```c
__int64 DaSiteMgrCreateInstanceStubFromPolicyStore()
{
  __int64 v0; // rbx
  HKEY v2; // [rsp+28h] [rbp-18h]
  __int64 v3; // [rsp+60h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+28h] BYREF
  HKEY v5; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  LODWORD(v3) = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v5 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v0 = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Tcpip\\v6Transition", 0, 0x20019u, &hKey);
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegOpenKeyExW(hKey, L"DaMultisite", 0, 0x20019u, &phkResult);
    if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v0 = MALLOC(0x1F0u);
      if ( v0 )
      {
        RegOpenKeyExW(phkResult, L"Sites", 0, 0x20019u, &v5);
        if ( v5 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          goto LABEL_11;
        memset_0((void *)v0, 0, 0x1F0u);
        *(_QWORD *)(v0 + 144) = v0 + 136;
        *(_QWORD *)(v0 + 136) = v0 + 136;
        if ( (unsigned __int64)v5 - 1 > 0xFFFFFFFFFFFFFFFDuLL || (unsigned int)IterateOverRegistryKey(v5, 0x20019u, v0) )
        {
          DaSiteMgrDestroyInstanceStub(v0);
          v0 = 0;
        }
        else
        {
          *(_DWORD *)(v0 + 152) = GetInteger(phkResult, L"UserOverrideAllowed", 1);
          GetString2(phkResult, (__int64)&v3, v2);
        }
      }
    }
  }
  if ( v5 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(v5);
LABEL_11:
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(phkResult);
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18003ebc8  push    rbp
0x18003ebca  push    rbx
0x18003ebcb  push    rdi
0x18003ebcc  mov     rbp, rsp
0x18003ebcf  sub     rsp, 40h
0x18003ebd3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003ebd7  mov     dword ptr [rbp+arg_0], 0
0x18003ebde  lea     rax, [rbp+hKey]
0x18003ebe2  mov     [rbp+arg_8], rdi
0x18003ebe6  mov     r9d, 20019h; samDesired
0x18003ebec  mov     [rbp+arg_10], rdi
0x18003ebf0  xor     r8d, r8d; ulOptions
0x18003ebf3  mov     [rbp+hKey], rdi
0x18003ebf7  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18003ebfe  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ec03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ec0a  xor     ebx, ebx
0x18003ec0c  call    cs:__imp_RegOpenKeyExW
0x18003ec13  nop     dword ptr [rax+rax+00h]
0x18003ec18  mov     rcx, [rbp+hKey]; hKey
0x18003ec1c  cmp     rcx, rdi
0x18003ec1f  jz      loc_18003ED2B
0x18003ec25  lea     rax, [rbp+arg_8]
0x18003ec29  mov     r9d, 20019h; samDesired
0x18003ec2f  xor     r8d, r8d; ulOptions
0x18003ec32  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ec37  lea     rdx, aDamultisite; "DaMultisite"
0x18003ec3e  call    cs:__imp_RegOpenKeyExW
0x18003ec45  nop     dword ptr [rax+rax+00h]
0x18003ec4a  cmp     [rbp+arg_8], rdi
0x18003ec4e  jz      loc_18003ED2B
0x18003ec54  mov     ecx, 1F0h; dwBytes
0x18003ec59  call    MALLOC
0x18003ec5e  mov     rbx, rax
0x18003ec61  test    rax, rax
0x18003ec64  jz      loc_18003ED2B
0x18003ec6a  mov     rcx, [rbp+arg_8]; hKey
0x18003ec6e  lea     rax, [rbp+arg_10]
0x18003ec72  mov     r9d, 20019h; samDesired
0x18003ec78  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ec7d  xor     r8d, r8d; ulOptions
0x18003ec80  lea     rdx, aSites; "Sites"
0x18003ec87  call    cs:__imp_RegOpenKeyExW
0x18003ec8e  nop     dword ptr [rax+rax+00h]
0x18003ec93  cmp     [rbp+arg_10], rdi
0x18003ec97  jz      loc_18003ED40
0x18003ec9d  xor     edx, edx; Val
0x18003ec9f  mov     r8d, 1F0h; Size
0x18003eca5  mov     rcx, rbx; void *
0x18003eca8  call    memset_0
0x18003ecad  lea     rax, [rbx+88h]
0x18003ecb4  mov     [rax+8], rax
0x18003ecb8  mov     [rax], rax
0x18003ecbb  mov     rcx, [rbp+arg_10]; hKey
0x18003ecbf  lea     rax, [rcx-1]
0x18003ecc3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ecc7  ja      short loc_18003ED21
0x18003ecc9  lea     r8, DaSiteMgrSiteTablePolicyReadHandler
0x18003ecd0  mov     [rsp+40h+phkResult], rbx; __int64
0x18003ecd5  mov     edx, 20019h; samDesired
0x18003ecda  call    IterateOverRegistryKey
0x18003ecdf  test    eax, eax
0x18003ece1  jnz     short loc_18003ED21
0x18003ece3  mov     rcx, [rbp+arg_8]
0x18003ece7  lea     r8d, [rdi+2]
0x18003eceb  lea     rdx, aUseroverrideal; "UserOverrideAllowed"
0x18003ecf2  call    GetInteger
0x18003ecf7  mov     [rbx+98h], eax
0x18003ecfd  lea     r9, [rbx+0A0h]
0x18003ed04  mov     rcx, [rbp+arg_8]; hKey
0x18003ed08  lea     rax, [rbp+arg_0]
0x18003ed0c  lea     r8, aSitefqdn; "SiteFqdn"
0x18003ed13  mov     [rsp+40h+phkResult], rax; __int64
0x18003ed18  xor     edx, edx
0x18003ed1a  call    GetString2
0x18003ed1f  jmp     short loc_18003ED2B
0x18003ed21  mov     rcx, rbx
0x18003ed24  call    DaSiteMgrDestroyInstanceStub
0x18003ed29  xor     ebx, ebx
0x18003ed2b  mov     rcx, [rbp+arg_10]; hKey
0x18003ed2f  cmp     rcx, rdi
0x18003ed32  jz      short loc_18003ED40
0x18003ed34  call    cs:__imp_RegCloseKey
0x18003ed3b  nop     dword ptr [rax+rax+00h]
0x18003ed40  mov     rcx, [rbp+arg_8]; hKey
0x18003ed44  cmp     rcx, rdi
0x18003ed47  jz      short loc_18003ED55
0x18003ed49  call    cs:__imp_RegCloseKey
0x18003ed50  nop     dword ptr [rax+rax+00h]
0x18003ed55  mov     rcx, [rbp+hKey]; hKey
0x18003ed59  cmp     rcx, rdi
0x18003ed5c  jz      short loc_18003ED6A
0x18003ed5e  call    cs:__imp_RegCloseKey
0x18003ed65  nop     dword ptr [rax+rax+00h]
0x18003ed6a  mov     rax, rbx
0x18003ed6d  add     rsp, 40h
0x18003ed71  pop     rdi
0x18003ed72  pop     rbx
0x18003ed73  pop     rbp
0x18003ed74  retn
```
