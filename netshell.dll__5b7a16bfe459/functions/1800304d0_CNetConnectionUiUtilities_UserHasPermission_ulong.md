# CNetConnectionUiUtilities::UserHasPermission(ulong)

- ea: `0x1800304d0`
- end: `0x18003058a`
- name: `?UserHasPermission@CNetConnectionUiUtilities@@UEAAHK@Z`
- size: `186`
- prototype: `int(CNetConnectionUiUtilities *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007de0`
- `0x18000ac14`
- `0x1800304d0`
- `0x180065010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800304f0`
- `USER32!GetSystemMetrics` at `0x1800304f0`
- `ole32!CoCreateInstance` at `0x180030544`
- `ole32!CoCreateInstance` at `0x180030544`
- `policymanager!PolicyManager_GetWiFiPolicy_AllowInternetSharing` at `0x180030508`
- `policymanager!PolicyManager_GetWiFiPolicy_AllowInternetSharing` at `0x180030508`

## pseudocode

```c
__int64 __fastcall CNetConnectionUiUtilities::UserHasPermission(CNetConnectionUiUtilities *this, unsigned int a2)
{
  unsigned int v4; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  if ( a2 >= 0x32 )
  {
    if ( a2 == 50 )
    {
      if ( GetSystemMetrics(88) )
        return v4;
      if ( !IsHomenetICSOSType() || (int)PolicyManager_GetWiFiPolicy_AllowInternetSharing(&v4) >= 0 && !v4 )
        return 0;
    }
    ppv = 0;
    if ( CoCreateInstance(&CLSID_NetGroupPolicies, 0, 0x15u, &IID_INetMachinePolicies, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD, unsigned int *))(*(_QWORD *)ppv + 24LL))(ppv, a2, &v4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    return v4;
  }
  return FHasPermission(a2);
}

```

## disassembly

```asm
0x1800304d0  push    rbx
0x1800304d2  sub     rsp, 30h
0x1800304d6  mov     [rsp+38h+arg_8], 0
0x1800304de  mov     ebx, edx
0x1800304e0  cmp     edx, 32h ; '2'
0x1800304e3  jb      loc_18003057D
0x1800304e9  jnz     short loc_18003051D
0x1800304eb  mov     ecx, 58h ; 'X'; nIndex
0x1800304f0  call    cs:__imp_GetSystemMetrics
0x1800304f6  test    eax, eax
0x1800304f8  jnz     short loc_180030577
0x1800304fa  call    ?IsHomenetICSOSType@@YAHXZ; IsHomenetICSOSType(void)
0x1800304ff  test    eax, eax
0x180030501  jz      short loc_180030519
0x180030503  lea     rcx, [rsp+38h+arg_8]
0x180030508  call    cs:__imp_PolicyManager_GetWiFiPolicy_AllowInternetSharing
0x18003050e  test    eax, eax
0x180030510  js      short loc_18003051D
0x180030512  cmp     [rsp+38h+arg_8], 0
0x180030517  jnz     short loc_18003051D
0x180030519  xor     eax, eax
0x18003051b  jmp     short loc_180030584
0x18003051d  xor     edx, edx; pUnkOuter
0x18003051f  mov     [rsp+38h+arg_10], 0
0x180030528  lea     rax, [rsp+38h+arg_10]
0x18003052d  lea     r9, IID_INetMachinePolicies; riid
0x180030534  mov     [rsp+38h+ppv], rax; ppv
0x180030539  lea     rcx, CLSID_NetGroupPolicies; rclsid
0x180030540  lea     r8d, [rdx+15h]; dwClsContext
0x180030544  call    cs:__imp_CoCreateInstance
0x18003054a  test    eax, eax
0x18003054c  js      short loc_180030577
0x18003054e  mov     rcx, [rsp+38h+arg_10]
0x180030553  lea     r8, [rsp+38h+arg_8]
0x180030558  mov     edx, ebx
0x18003055a  mov     rax, [rcx]
0x18003055d  mov     rax, [rax+18h]
0x180030561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030566  mov     rcx, [rsp+38h+arg_10]
0x18003056b  mov     rax, [rcx]
0x18003056e  mov     rax, [rax+10h]
0x180030572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030577  mov     eax, [rsp+38h+arg_8]
0x18003057b  jmp     short loc_180030584
0x18003057d  mov     ecx, ebx; unsigned int
0x18003057f  call    ?FHasPermission@@YAHK@Z; FHasPermission(ulong)
0x180030584  add     rsp, 30h
0x180030588  pop     rbx
0x180030589  retn
```
