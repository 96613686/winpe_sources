# CMapiSupport::IsOutlookInstalled(int *)

- ea: `0x1800303ac`
- end: `0x1800304cb`
- name: `?IsOutlookInstalled@CMapiSupport@@SAJPEAH@Z`
- size: `287`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18001ed10`

## callees

- `0x1800303ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800303e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003045f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003048d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800303e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003045f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003048d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800303fa`

## pseudocode

```c
__int64 __fastcall CMapiSupport::IsOutlookInstalled(int *a1)
{
  LSTATUS v2; // eax
  int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( !v2 )
    goto LABEL_2;
  if ( v2 == 2 )
  {
    v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.12", 0, 0x20019u, &hKey);
    v3 = v4;
    if ( !v4 )
      goto LABEL_2;
    if ( v4 == 2 )
    {
      v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.11", 0, 0x20019u, &hKey);
      v3 = v5;
      if ( !v5 )
        goto LABEL_2;
      if ( v5 == 2 )
      {
        v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Outlook.Application.10", 0, 0x20019u, &hKey);
        v3 = v6;
        if ( v6 )
        {
          if ( v6 == 2 )
          {
            *a1 = 0;
            return 0;
          }
          goto LABEL_11;
        }
LABEL_2:
        RegCloseKey(hKey);
        *a1 = 1;
        return (unsigned int)v3;
      }
    }
  }
LABEL_11:
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800303ac  mov     r11, rsp
0x1800303af  mov     [r11+8], rbx
0x1800303b3  mov     [r11+18h], rbp
0x1800303b7  push    rdi
0x1800303b8  sub     rsp, 30h
0x1800303bc  mov     rdi, rcx
0x1800303bf  mov     qword ptr [r11+10h], 0
0x1800303c7  lea     rax, [r11+10h]
0x1800303cb  mov     rbp, 0FFFFFFFF80000000h
0x1800303d2  mov     rcx, rbp; hKey
0x1800303d5  mov     [r11-18h], rax
0x1800303d9  mov     r9d, 20019h; samDesired
0x1800303df  lea     rdx, aOutlookApplica_3; "Outlook.Application"
0x1800303e6  xor     r8d, r8d; ulOptions
0x1800303e9  call    cs:__imp_RegOpenKeyExW
0x1800303ef  mov     ebx, eax
0x1800303f1  test    eax, eax
0x1800303f3  jnz     short loc_18003040B
0x1800303f5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800303fa  call    cs:__imp_RegCloseKey
0x180030400  mov     dword ptr [rdi], 1
0x180030406  jmp     loc_1800304B9
0x18003040b  cmp     eax, 2
0x18003040e  jnz     loc_1800304AC
0x180030414  lea     rax, [rsp+38h+hKey]
0x180030419  mov     r9d, 20019h; samDesired
0x18003041f  xor     r8d, r8d; ulOptions
0x180030422  mov     [rsp+38h+phkResult], rax; phkResult
0x180030427  lea     rdx, aOutlookApplica_1; "Outlook.Application.12"
0x18003042e  mov     rcx, rbp; hKey
0x180030431  call    cs:__imp_RegOpenKeyExW
0x180030437  mov     ebx, eax
0x180030439  test    eax, eax
0x18003043b  jz      short loc_1800303F5
0x18003043d  cmp     eax, 2
0x180030440  jnz     short loc_1800304AC
0x180030442  lea     rax, [rsp+38h+hKey]
0x180030447  mov     r9d, 20019h; samDesired
0x18003044d  xor     r8d, r8d; ulOptions
0x180030450  mov     [rsp+38h+phkResult], rax; phkResult
0x180030455  lea     rdx, aOutlookApplica_0; "Outlook.Application.11"
0x18003045c  mov     rcx, rbp; hKey
0x18003045f  call    cs:__imp_RegOpenKeyExW
0x180030465  mov     ebx, eax
0x180030467  test    eax, eax
0x180030469  jz      short loc_1800303F5
0x18003046b  cmp     eax, 2
0x18003046e  jnz     short loc_1800304AC
0x180030470  lea     rax, [rsp+38h+hKey]
0x180030475  mov     r9d, 20019h; samDesired
0x18003047b  xor     r8d, r8d; ulOptions
0x18003047e  mov     [rsp+38h+phkResult], rax; phkResult
0x180030483  lea     rdx, aOutlookApplica_2; "Outlook.Application.10"
0x18003048a  mov     rcx, rbp; hKey
0x18003048d  call    cs:__imp_RegOpenKeyExW
0x180030493  mov     ebx, eax
0x180030495  test    eax, eax
0x180030497  jz      loc_1800303F5
0x18003049d  cmp     eax, 2
0x1800304a0  jnz     short loc_1800304AC
0x1800304a2  mov     dword ptr [rdi], 0
0x1800304a8  xor     ebx, ebx
0x1800304aa  jmp     short loc_1800304B9
0x1800304ac  test    ebx, ebx
0x1800304ae  jle     short loc_1800304B9
0x1800304b0  movzx   ebx, bx
0x1800304b3  or      ebx, 80070000h
0x1800304b9  mov     rbp, [rsp+38h+arg_10]
0x1800304be  mov     eax, ebx
0x1800304c0  mov     rbx, [rsp+38h+arg_0]
0x1800304c5  add     rsp, 30h
0x1800304c9  pop     rdi
0x1800304ca  retn
```
