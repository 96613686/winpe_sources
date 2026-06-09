# ServiceLoadAllPolicyModule

- ea: `0x180031408`
- end: `0x1800315bd`
- name: `ServiceLoadAllPolicyModule`
- size: `437`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020790`

## callees

- `0x180005665`
- `0x180030d54`
- `0x180030d84`
- `0x180030e60`
- `0x180031408`
- `0x1800a0fb0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180031486`
- `ADVAPI32!RegOpenKeyExW` at `0x1800314dd`
- `ADVAPI32!RegOpenKeyExW` at `0x18003154f`
- `ADVAPI32!RegOpenKeyExW` at `0x180031486`
- `ADVAPI32!RegOpenKeyExW` at `0x1800314dd`
- `ADVAPI32!RegOpenKeyExW` at `0x18003154f`
- `ADVAPI32!RegCloseKey` at `0x18003157a`
- `ADVAPI32!RegCloseKey` at `0x18003157a`

## pseudocode

```c
unsigned int ServiceLoadAllPolicyModule()
{
  LSTATUS v0; // eax
  LSTATUS v1; // eax
  const unsigned __int16 *v2; // r9
  const unsigned __int16 *v3; // r9
  unsigned int v5; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v6; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v10[256]; // [rsp+260h] [rbp+160h] BYREF

  *(_OWORD *)hKey = 0;
  *(_OWORD *)phkResult = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  memset_0(v10, 0, sizeof(v10));
  v5 = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TermServLicensing\\Policy", 0, 0x20019u, &hKey[1]);
  LODWORD(hKey[0]) = 0;
  while ( !v0 )
  {
    v5 = 256;
    if ( RegEnumNext((struct _RegEnumHandle *)hKey, SubKey, &v5) )
      break;
    v1 = RegOpenKeyExW(hKey[1], SubKey, 0, 0x20019u, &phkResult[1]);
    LODWORD(phkResult[0]) = 0;
    if ( !v1 )
    {
      ServiceLoadPolicyModule(phkResult[1], SubKey, 0, v2);
      while ( 1 )
      {
        v5 = 256;
        if ( RegEnumNext((struct _RegEnumHandle *)phkResult, v10, &v5) )
          break;
        v6 = 0;
        if ( RegOpenKeyExW(phkResult[1], v10, 0, 0x20019u, &v6) )
          break;
        ServiceLoadPolicyModule(v6, SubKey, v10, v3);
        RegCloseKey(v6);
      }
    }
    v0 = RegEnumEnd((struct _RegEnumHandle *)phkResult);
  }
  return RegEnumEnd((struct _RegEnumHandle *)hKey);
}

```

## disassembly

```asm
0x180031408  push    rbp
0x18003140a  lea     rbp, [rsp-370h]
0x180031412  sub     rsp, 470h
0x180031419  mov     rax, cs:__security_cookie
0x180031420  xor     rax, rsp
0x180031423  mov     [rbp+370h+var_10], rax
0x18003142a  xorps   xmm0, xmm0
0x18003142d  lea     rcx, [rsp+470h+SubKey]; void *
0x180031432  xorps   xmm1, xmm1
0x180031435  xor     edx, edx; Val
0x180031437  mov     r8d, 200h; Size
0x18003143d  movups  xmmword ptr [rsp+470h+hKey], xmm0
0x180031442  movups  xmmword ptr [rsp+470h+var_430], xmm1
0x180031447  call    memset_0
0x18003144c  xor     edx, edx; Val
0x18003144e  lea     rcx, [rbp+370h+var_210]; void *
0x180031455  mov     r8d, 200h; Size
0x18003145b  call    memset_0
0x180031460  and     [rsp+470h+var_440], 0
0x180031465  lea     rax, [rsp+470h+hKey+8]
0x18003146a  mov     r9d, 20019h; samDesired
0x180031470  mov     [rsp+470h+phkResult], rax; phkResult
0x180031475  xor     r8d, r8d; ulOptions
0x180031478  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x18003147f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031486  call    cs:__imp_RegOpenKeyExW
0x18003148d  nop     dword ptr [rax+rax+00h]
0x180031492  and     dword ptr [rsp+470h+hKey], 0
0x180031497  jmp     loc_180031592
0x18003149c  lea     r8, [rsp+470h+var_440]; unsigned int *
0x1800314a1  mov     [rsp+470h+var_440], 100h
0x1800314a9  lea     rdx, [rsp+470h+SubKey]; unsigned __int16 *
0x1800314ae  lea     rcx, [rsp+470h+hKey]; struct _RegEnumHandle *
0x1800314b3  call    ?RegEnumNext@@YAKPEAU_RegEnumHandle@@PEAGPEAK@Z; RegEnumNext(_RegEnumHandle *,ushort *,ulong *)
0x1800314b8  test    eax, eax
0x1800314ba  jnz     loc_18003159A
0x1800314c0  mov     rcx, [rsp+470h+hKey+8]; hKey
0x1800314c5  lea     rax, [rsp+470h+var_430+8]
0x1800314ca  mov     r9d, 20019h; samDesired
0x1800314d0  mov     [rsp+470h+phkResult], rax; unsigned __int16 *
0x1800314d5  xor     r8d, r8d; ulOptions
0x1800314d8  lea     rdx, [rsp+470h+SubKey]; lpSubKey
0x1800314dd  call    cs:__imp_RegOpenKeyExW
0x1800314e4  nop     dword ptr [rax+rax+00h]
0x1800314e9  and     dword ptr [rsp+470h+var_430], 0
0x1800314ee  test    eax, eax
0x1800314f0  jnz     loc_180031588
0x1800314f6  mov     rcx, [rsp+470h+var_430+8]; HKEY
0x1800314fb  lea     rdx, [rsp+470h+SubKey]; unsigned __int16 *
0x180031500  xor     r8d, r8d; unsigned __int16 *
0x180031503  call    ?ServiceLoadPolicyModule@@YAKPEAUHKEY__@@PEBG111@Z; ServiceLoadPolicyModule(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180031508  lea     r8, [rsp+470h+var_440]; unsigned int *
0x18003150d  mov     [rsp+470h+var_440], 100h
0x180031515  lea     rdx, [rbp+370h+var_210]; unsigned __int16 *
0x18003151c  lea     rcx, [rsp+470h+var_430]; struct _RegEnumHandle *
0x180031521  call    ?RegEnumNext@@YAKPEAU_RegEnumHandle@@PEAGPEAK@Z; RegEnumNext(_RegEnumHandle *,ushort *,ulong *)
0x180031526  test    eax, eax
0x180031528  jnz     short loc_180031588
0x18003152a  mov     rcx, [rsp+470h+var_430+8]; hKey
0x18003152f  lea     rax, [rsp+470h+var_438]
0x180031534  and     [rsp+470h+var_438], 0
0x18003153a  lea     rdx, [rbp+370h+var_210]; lpSubKey
0x180031541  mov     r9d, 20019h; samDesired
0x180031547  mov     [rsp+470h+phkResult], rax; unsigned __int16 *
0x18003154c  xor     r8d, r8d; ulOptions
0x18003154f  call    cs:__imp_RegOpenKeyExW
0x180031556  nop     dword ptr [rax+rax+00h]
0x18003155b  test    eax, eax
0x18003155d  jnz     short loc_180031588
0x18003155f  mov     rcx, [rsp+470h+var_438]; HKEY
0x180031564  lea     r8, [rbp+370h+var_210]; unsigned __int16 *
0x18003156b  lea     rdx, [rsp+470h+SubKey]; unsigned __int16 *
0x180031570  call    ?ServiceLoadPolicyModule@@YAKPEAUHKEY__@@PEBG111@Z; ServiceLoadPolicyModule(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180031575  mov     rcx, [rsp+470h+var_438]; hKey
0x18003157a  call    cs:__imp_RegCloseKey
0x180031581  nop     dword ptr [rax+rax+00h]
0x180031586  jmp     short loc_180031508
0x180031588  lea     rcx, [rsp+470h+var_430]; struct _RegEnumHandle *
0x18003158d  call    ?RegEnumEnd@@YAKPEAU_RegEnumHandle@@@Z; RegEnumEnd(_RegEnumHandle *)
0x180031592  test    eax, eax
0x180031594  jz      loc_18003149C
0x18003159a  lea     rcx, [rsp+470h+hKey]; struct _RegEnumHandle *
0x18003159f  call    ?RegEnumEnd@@YAKPEAU_RegEnumHandle@@@Z; RegEnumEnd(_RegEnumHandle *)
0x1800315a4  mov     rcx, [rbp+370h+var_10]
0x1800315ab  xor     rcx, rsp; StackCookie
0x1800315ae  call    __security_check_cookie
0x1800315b3  add     rsp, 470h
0x1800315ba  pop     rbp
0x1800315bb  retn
```
