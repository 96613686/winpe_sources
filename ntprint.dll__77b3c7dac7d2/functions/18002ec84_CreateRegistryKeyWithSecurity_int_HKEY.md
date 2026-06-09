# CreateRegistryKeyWithSecurity(int,HKEY__ * *)

- ea: `0x18002ec84`
- end: `0x18002ee9e`
- name: `?CreateRegistryKeyWithSecurity@@YAKHPEAPEAUHKEY__@@@Z`
- size: `538`
- prototype: `unsigned int __fastcall(int, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e54c`
- `0x18002fb40`

## callees

- `0x18002ec84`
- `0x180039014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ece6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ece6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ede5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ee8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ede5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ee8b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ed3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ee44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ed3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ee44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ee55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ee68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ee55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ee68`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18002eda9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18002eda9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ecdc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ecdc`
- `ADVAPI32!GetSecurityInfo` at `0x18002ed85`
- `ADVAPI32!GetSecurityInfo` at `0x18002ed85`
- `ADVAPI32!RegDeleteKeyW` at `0x18002edfd`
- `ADVAPI32!RegDeleteKeyW` at `0x18002edfd`

## pseudocode

```c
__int64 __fastcall CreateRegistryKeyWithSecurity(int a1, HKEY *a2)
{
  DWORD LastError; // ebx
  REGSAM samDesired; // esi
  HKEY v6; // rcx
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+58h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+40h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+B8h] [rbp+48h] BYREF

  hKey = 0;
  dwDisposition = 0;
  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !a2 )
    return 87;
  *a2 = 0;
  SecurityDescriptor.nLength = 24;
  SecurityDescriptor.bInheritHandle = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;;KA;;;SY)(A;;KA;;;BA)",
          1u,
          &SecurityDescriptor.lpSecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_22;
  }
  samDesired = a1 != 0 ? 131097 : 131078;
  LastError = RegCreateKeyExW(
                HKEY_CURRENT_USER,
                L"Printers\\LegacyPointAndPrint",
                0,
                0,
                1u,
                samDesired,
                &SecurityDescriptor,
                &hKey,
                &dwDisposition);
  if ( LastError )
    goto LABEL_22;
  if ( dwDisposition != 2 )
  {
LABEL_21:
    v6 = 0;
    *a2 = hKey;
    hKey = 0;
    goto LABEL_23;
  }
  ppSecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  LastError = GetSecurityInfo(hKey, SE_REGISTRY_KEY, 4u, 0, 0, 0, 0, &ppSecurityDescriptor);
  if ( !LastError )
  {
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
           ppSecurityDescriptor,
           1u,
           4u,
           &StringSecurityDescriptor,
           0) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_16;
    }
    if ( wcscmp_0(L"D:P(A;;KA;;;SY)(A;;KA;;;BA)", StringSecurityDescriptor) )
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      LastError = RegDeleteKeyW(HKEY_CURRENT_USER, L"Printers\\LegacyPointAndPrint");
      if ( !LastError )
        LastError = RegCreateKeyExW(
                      HKEY_CURRENT_USER,
                      L"Printers\\LegacyPointAndPrint",
                      0,
                      0,
                      1u,
                      samDesired,
                      &SecurityDescriptor,
                      &hKey,
                      &dwDisposition);
    }
  }
LABEL_16:
  if ( ppSecurityDescriptor )
  {
    LocalFree(ppSecurityDescriptor);
    ppSecurityDescriptor = 0;
  }
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  if ( !LastError )
    goto LABEL_21;
LABEL_22:
  v6 = hKey;
LABEL_23:
  if ( v6 )
    RegCloseKey(v6);
  return LastError;
}

```

## disassembly

```asm
0x18002ec84  push    rbp
0x18002ec86  push    rbx
0x18002ec87  push    rsi
0x18002ec88  push    rdi
0x18002ec89  push    r14
0x18002ec8b  mov     rbp, rsp
0x18002ec8e  sub     rsp, 70h
0x18002ec92  xor     r14d, r14d
0x18002ec95  xor     eax, eax
0x18002ec97  mov     [rbp+hKey], r14
0x18002ec9b  xorps   xmm0, xmm0
0x18002ec9e  mov     [rbp+dwDisposition], r14d
0x18002eca2  mov     rdi, rdx
0x18002eca5  mov     [rbp+var_8], rax
0x18002eca9  mov     esi, ecx
0x18002ecab  movups  xmmword ptr [rbp+SecurityDescriptor], xmm0
0x18002ecaf  test    rdx, rdx
0x18002ecb2  jnz     short loc_18002ECBC
0x18002ecb4  lea     ebx, [rdx+57h]
0x18002ecb7  jmp     loc_18002EE91
0x18002ecbc  xor     r9d, r9d; SecurityDescriptorSize
0x18002ecbf  mov     [rdx], r14
0x18002ecc2  lea     r8, [rbp+SecurityDescriptor+8]; SecurityDescriptor
0x18002ecc6  mov     dword ptr [rbp+SecurityDescriptor], 18h
0x18002eccd  lea     rcx, aDPAKaSyAKaBa; "D:P(A;;KA;;;SY)(A;;KA;;;BA)"
0x18002ecd4  mov     dword ptr [rbp+var_8], r14d
0x18002ecd8  lea     edx, [r9+1]; StringSDRevision
0x18002ecdc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002ece2  test    eax, eax
0x18002ece4  jnz     short loc_18002ECF6
0x18002ece6  call    cs:__imp_GetLastError
0x18002ecec  mov     ebx, eax
0x18002ecee  test    eax, eax
0x18002ecf0  jnz     loc_18002EE82
0x18002ecf6  neg     esi
0x18002ecf8  lea     rax, [rbp+dwDisposition]
0x18002ecfc  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18002ed01  lea     rdx, aPrintersLegacy; "Printers\\LegacyPointAndPrint"
0x18002ed08  sbb     esi, esi
0x18002ed0a  lea     rax, [rbp+hKey]
0x18002ed0e  mov     [rsp+70h+phkResult], rax; phkResult
0x18002ed13  and     esi, 13h
0x18002ed16  lea     rax, [rbp+SecurityDescriptor]
0x18002ed1a  add     esi, 20006h
0x18002ed20  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002ed25  xor     r9d, r9d; lpClass
0x18002ed28  mov     [rsp+70h+samDesired], esi; samDesired
0x18002ed2c  xor     r8d, r8d; Reserved
0x18002ed2f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002ed36  mov     [rsp+70h+dwOptions], 1; dwOptions
0x18002ed3e  call    cs:__imp_RegCreateKeyExW
0x18002ed44  mov     ebx, eax
0x18002ed46  test    eax, eax
0x18002ed48  jnz     loc_18002EE82
0x18002ed4e  cmp     [rbp+dwDisposition], 2
0x18002ed52  jnz     loc_18002EE72
0x18002ed58  mov     rcx, [rbp+hKey]; handle
0x18002ed5c  lea     rax, [rbp+ppSecurityDescriptor]
0x18002ed60  mov     [rsp+70h+phkResult], rax; ppSecurityDescriptor
0x18002ed65  lea     edx, [rbx+4]; ObjectType
0x18002ed68  mov     [rsp+70h+lpSecurityAttributes], r14; ppSacl
0x18002ed6d  xor     r9d, r9d; ppsidOwner
0x18002ed70  mov     qword ptr [rsp+70h+samDesired], r14; ppDacl
0x18002ed75  mov     r8d, edx; SecurityInfo
0x18002ed78  mov     qword ptr [rsp+70h+dwOptions], r14; ppsidGroup
0x18002ed7d  mov     [rbp+ppSecurityDescriptor], r14
0x18002ed81  mov     [rbp+StringSecurityDescriptor], r14
0x18002ed85  call    cs:__imp_GetSecurityInfo
0x18002ed8b  mov     ebx, eax
0x18002ed8d  test    eax, eax
0x18002ed8f  jnz     loc_18002EE4C
0x18002ed95  mov     rcx, [rbp+ppSecurityDescriptor]; SecurityDescriptor
0x18002ed99  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002ed9d  lea     edx, [rax+1]; RequestedStringSDRevision
0x18002eda0  mov     qword ptr [rsp+70h+dwOptions], r14; StringSecurityDescriptorLen
0x18002eda5  lea     r8d, [rax+4]; SecurityInformation
0x18002eda9  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18002edaf  test    eax, eax
0x18002edb1  jz      short loc_18002EDB8
0x18002edb3  mov     ebx, r14d
0x18002edb6  jmp     short loc_18002EDC8
0x18002edb8  call    cs:__imp_GetLastError
0x18002edbe  mov     ebx, eax
0x18002edc0  test    eax, eax
0x18002edc2  jnz     loc_18002EE4C
0x18002edc8  mov     rdx, [rbp+StringSecurityDescriptor]; String2
0x18002edcc  lea     rcx, aDPAKaSyAKaBa; "D:P(A;;KA;;;SY)(A;;KA;;;BA)"
0x18002edd3  call    wcscmp_0
0x18002edd8  test    eax, eax
0x18002edda  jz      short loc_18002EE4C
0x18002eddc  mov     rcx, [rbp+hKey]; hKey
0x18002ede0  test    rcx, rcx
0x18002ede3  jz      short loc_18002EDEF
0x18002ede5  call    cs:__imp_RegCloseKey
0x18002edeb  mov     [rbp+hKey], r14
0x18002edef  lea     rdx, aPrintersLegacy; "Printers\\LegacyPointAndPrint"
0x18002edf6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002edfd  call    cs:__imp_RegDeleteKeyW
0x18002ee03  mov     ebx, eax
0x18002ee05  test    eax, eax
0x18002ee07  jnz     short loc_18002EE4C
0x18002ee09  lea     rax, [rbp+dwDisposition]
0x18002ee0d  xor     r9d, r9d; lpClass
0x18002ee10  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18002ee15  lea     rdx, aPrintersLegacy; "Printers\\LegacyPointAndPrint"
0x18002ee1c  lea     rax, [rbp+hKey]
0x18002ee20  xor     r8d, r8d; Reserved
0x18002ee23  mov     [rsp+70h+phkResult], rax; phkResult
0x18002ee28  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002ee2f  lea     rax, [rbp+SecurityDescriptor]
0x18002ee33  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002ee38  mov     [rsp+70h+samDesired], esi; samDesired
0x18002ee3c  mov     [rsp+70h+dwOptions], 1; dwOptions
0x18002ee44  call    cs:__imp_RegCreateKeyExW
0x18002ee4a  mov     ebx, eax
0x18002ee4c  mov     rcx, [rbp+ppSecurityDescriptor]; hMem
0x18002ee50  test    rcx, rcx
0x18002ee53  jz      short loc_18002EE5F
0x18002ee55  call    cs:__imp_LocalFree
0x18002ee5b  mov     [rbp+ppSecurityDescriptor], r14
0x18002ee5f  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18002ee63  test    rcx, rcx
0x18002ee66  jz      short loc_18002EE6E
0x18002ee68  call    cs:__imp_LocalFree
0x18002ee6e  test    ebx, ebx
0x18002ee70  jnz     short loc_18002EE82
0x18002ee72  mov     rax, [rbp+hKey]
0x18002ee76  mov     rcx, r14
0x18002ee79  mov     [rdi], rax
0x18002ee7c  mov     [rbp+hKey], rcx
0x18002ee80  jmp     short loc_18002EE86
0x18002ee82  mov     rcx, [rbp+hKey]; hKey
0x18002ee86  test    rcx, rcx
0x18002ee89  jz      short loc_18002EE91
0x18002ee8b  call    cs:__imp_RegCloseKey
0x18002ee91  mov     eax, ebx
0x18002ee93  add     rsp, 70h
0x18002ee97  pop     r14
0x18002ee99  pop     rdi
0x18002ee9a  pop     rsi
0x18002ee9b  pop     rbx
0x18002ee9c  pop     rbp
0x18002ee9d  retn
```
