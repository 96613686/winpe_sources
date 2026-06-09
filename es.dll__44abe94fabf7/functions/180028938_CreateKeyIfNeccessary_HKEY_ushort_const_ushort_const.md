# CreateKeyIfNeccessary(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180028938`
- end: `0x180028a76`
- name: `?CreateKeyIfNeccessary@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `318`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003b550`

## callees

- `0x180028938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028985`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800289f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800289f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028a27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028a27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a42`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002897b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002897b`

## pseudocode

```c
__int64 __fastcall CreateKeyIfNeccessary(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR StringSecurityDescriptor)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+28h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v7 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, &SecurityAttributes, &hKeya, &dwDisposition);
    v6 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      if ( dwDisposition == 1 )
      {
        *(_DWORD *)Data = 0;
        v8 = RegSetValueExW(hKeya, L"Active", 0, 4u, Data, 4u);
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
      }
      RegCloseKey(hKeya);
    }
    LocalFree(SecurityDescriptor);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180028938  mov     [rsp-8+arg_0], rbx
0x18002893d  mov     [rsp-8+arg_8], rdi
0x180028942  push    rbp
0x180028943  mov     rbp, rsp
0x180028946  sub     rsp, 80h
0x18002894d  mov     rax, r8
0x180028950  mov     [rbp+hKey], 0
0x180028958  xor     r9d, r9d; SecurityDescriptorSize
0x18002895b  mov     [rbp+dwDisposition], 0
0x180028962  mov     rbx, rdx
0x180028965  mov     [rbp+SecurityDescriptor], 0
0x18002896d  mov     rdi, rcx
0x180028970  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180028974  mov     rcx, rax; StringSecurityDescriptor
0x180028977  lea     edx, [r9+1]; StringSDRevision
0x18002897b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180028981  test    eax, eax
0x180028983  jnz     short loc_1800289A3
0x180028985  call    cs:__imp_GetLastError
0x18002898b  mov     ebx, eax
0x18002898d  test    eax, eax
0x18002898f  jle     loc_180028A5F
0x180028995  movzx   ebx, ax
0x180028998  or      ebx, 80070000h
0x18002899e  jmp     loc_180028A5F
0x1800289a3  mov     rax, [rbp+SecurityDescriptor]
0x1800289a7  xor     r9d, r9d; lpClass
0x1800289aa  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x1800289ae  xor     r8d, r8d; Reserved
0x1800289b1  lea     rax, [rbp+dwDisposition]
0x1800289b5  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x1800289bd  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x1800289c2  mov     rdx, rbx; lpSubKey
0x1800289c5  lea     rax, [rbp+hKey]
0x1800289c9  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x1800289d1  mov     [rsp+80h+phkResult], rax; phkResult
0x1800289d6  mov     rcx, rdi; hKey
0x1800289d9  lea     rax, [rbp+SecurityAttributes]
0x1800289dd  mov     [rsp+80h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800289e2  mov     [rsp+80h+samDesired], 20006h; samDesired
0x1800289ea  mov     [rsp+80h+dwOptions], 0; dwOptions
0x1800289f2  call    cs:__imp_RegCreateKeyExW
0x1800289f8  mov     ebx, eax
0x1800289fa  test    eax, eax
0x1800289fc  jnz     short loc_180028A4A
0x1800289fe  cmp     [rbp+dwDisposition], 1
0x180028a02  jnz     short loc_180028A3E
0x180028a04  mov     rcx, [rbp+hKey]; hKey
0x180028a08  lea     r9d, [rax+4]; dwType
0x180028a0c  mov     dword ptr [rbp+Data], eax
0x180028a0f  lea     rdx, Value; "Active"
0x180028a16  lea     rax, [rbp+Data]
0x180028a1a  mov     [rsp+80h+samDesired], r9d; cbData
0x180028a1f  xor     r8d, r8d; Reserved
0x180028a22  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x180028a27  call    cs:__imp_RegSetValueExW
0x180028a2d  mov     ebx, eax
0x180028a2f  test    eax, eax
0x180028a31  jz      short loc_180028A3E
0x180028a33  jle     short loc_180028A3E
0x180028a35  movzx   ebx, ax
0x180028a38  or      ebx, 80070000h
0x180028a3e  mov     rcx, [rbp+hKey]; hKey
0x180028a42  call    cs:__imp_RegCloseKey
0x180028a48  jmp     short loc_180028A55
0x180028a4a  jle     short loc_180028A55
0x180028a4c  movzx   ebx, ax
0x180028a4f  or      ebx, 80070000h
0x180028a55  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180028a59  call    cs:__imp_LocalFree
0x180028a5f  lea     r11, [rsp+80h+var_s0]
0x180028a67  mov     eax, ebx
0x180028a69  mov     rbx, [r11+10h]
0x180028a6d  mov     rdi, [r11+18h]
0x180028a71  mov     rsp, r11
0x180028a74  pop     rbp
0x180028a75  retn
```
