# DaSiteMgrCreateInstanceStubFromPolicyStore

- ea: `0x18003ec08`
- end: `0x18003edb6`
- name: `DaSiteMgrCreateInstanceStubFromPolicyStore`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a930`

## callees

- `0x180012dbc`
- `0x18002b46c`
- `0x18003ec08`
- `0x18003edbc`
- `0x18004c1c8`
- `0x1800769d8`
- `0x180076b38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ed9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ecc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ec7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ecc7`

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
0x18003ec08  push    rbp
0x18003ec0a  push    rbx
0x18003ec0b  push    rdi
0x18003ec0c  mov     rbp, rsp
0x18003ec0f  sub     rsp, 40h
0x18003ec13  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003ec17  mov     dword ptr [rbp+arg_0], 0
0x18003ec1e  lea     rax, [rbp+hKey]
0x18003ec22  mov     [rbp+arg_8], rdi
0x18003ec26  mov     r9d, 20019h; samDesired
0x18003ec2c  mov     [rbp+arg_10], rdi
0x18003ec30  xor     r8d, r8d; ulOptions
0x18003ec33  mov     [rbp+hKey], rdi
0x18003ec37  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18003ec3e  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ec43  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ec4a  xor     ebx, ebx
0x18003ec4c  call    cs:__imp_RegOpenKeyExW
0x18003ec53  nop     dword ptr [rax+rax+00h]
0x18003ec58  mov     rcx, [rbp+hKey]; hKey
0x18003ec5c  cmp     rcx, rdi
0x18003ec5f  jz      loc_18003ED6B
0x18003ec65  lea     rax, [rbp+arg_8]
0x18003ec69  mov     r9d, 20019h; samDesired
0x18003ec6f  xor     r8d, r8d; ulOptions
0x18003ec72  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ec77  lea     rdx, aDamultisite; "DaMultisite"
0x18003ec7e  call    cs:__imp_RegOpenKeyExW
0x18003ec85  nop     dword ptr [rax+rax+00h]
0x18003ec8a  cmp     [rbp+arg_8], rdi
0x18003ec8e  jz      loc_18003ED6B
0x18003ec94  mov     ecx, 1F0h; dwBytes
0x18003ec99  call    MALLOC
0x18003ec9e  mov     rbx, rax
0x18003eca1  test    rax, rax
0x18003eca4  jz      loc_18003ED6B
0x18003ecaa  mov     rcx, [rbp+arg_8]; hKey
0x18003ecae  lea     rax, [rbp+arg_10]
0x18003ecb2  mov     r9d, 20019h; samDesired
0x18003ecb8  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ecbd  xor     r8d, r8d; ulOptions
0x18003ecc0  lea     rdx, aSites; "Sites"
0x18003ecc7  call    cs:__imp_RegOpenKeyExW
0x18003ecce  nop     dword ptr [rax+rax+00h]
0x18003ecd3  cmp     [rbp+arg_10], rdi
0x18003ecd7  jz      loc_18003ED80
0x18003ecdd  xor     edx, edx; Val
0x18003ecdf  mov     r8d, 1F0h; Size
0x18003ece5  mov     rcx, rbx; void *
0x18003ece8  call    memset_0
0x18003eced  lea     rax, [rbx+88h]
0x18003ecf4  mov     [rax+8], rax
0x18003ecf8  mov     [rax], rax
0x18003ecfb  mov     rcx, [rbp+arg_10]; hKey
0x18003ecff  lea     rax, [rcx-1]
0x18003ed03  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ed07  ja      short loc_18003ED61
0x18003ed09  lea     r8, DaSiteMgrSiteTablePolicyReadHandler
0x18003ed10  mov     [rsp+40h+phkResult], rbx; __int64
0x18003ed15  mov     edx, 20019h; samDesired
0x18003ed1a  call    IterateOverRegistryKey
0x18003ed1f  test    eax, eax
0x18003ed21  jnz     short loc_18003ED61
0x18003ed23  mov     rcx, [rbp+arg_8]
0x18003ed27  lea     r8d, [rdi+2]
0x18003ed2b  lea     rdx, aUseroverrideal; "UserOverrideAllowed"
0x18003ed32  call    GetInteger
0x18003ed37  mov     [rbx+98h], eax
0x18003ed3d  lea     r9, [rbx+0A0h]
0x18003ed44  mov     rcx, [rbp+arg_8]; hKey
0x18003ed48  lea     rax, [rbp+arg_0]
0x18003ed4c  lea     r8, aSitefqdn; "SiteFqdn"
0x18003ed53  mov     [rsp+40h+phkResult], rax; __int64
0x18003ed58  xor     edx, edx
0x18003ed5a  call    GetString2
0x18003ed5f  jmp     short loc_18003ED6B
0x18003ed61  mov     rcx, rbx
0x18003ed64  call    DaSiteMgrDestroyInstanceStub
0x18003ed69  xor     ebx, ebx
0x18003ed6b  mov     rcx, [rbp+arg_10]; hKey
0x18003ed6f  cmp     rcx, rdi
0x18003ed72  jz      short loc_18003ED80
0x18003ed74  call    cs:__imp_RegCloseKey
0x18003ed7b  nop     dword ptr [rax+rax+00h]
0x18003ed80  mov     rcx, [rbp+arg_8]; hKey
0x18003ed84  cmp     rcx, rdi
0x18003ed87  jz      short loc_18003ED95
0x18003ed89  call    cs:__imp_RegCloseKey
0x18003ed90  nop     dword ptr [rax+rax+00h]
0x18003ed95  mov     rcx, [rbp+hKey]; hKey
0x18003ed99  cmp     rcx, rdi
0x18003ed9c  jz      short loc_18003EDAA
0x18003ed9e  call    cs:__imp_RegCloseKey
0x18003eda5  nop     dword ptr [rax+rax+00h]
0x18003edaa  mov     rax, rbx
0x18003edad  add     rsp, 40h
0x18003edb1  pop     rdi
0x18003edb2  pop     rbx
0x18003edb3  pop     rbp
0x18003edb4  retn
```
