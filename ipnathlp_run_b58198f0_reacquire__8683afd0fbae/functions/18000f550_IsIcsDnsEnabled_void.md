# IsIcsDnsEnabled(void)

- ea: `0x18000f550`
- end: `0x18000f769`
- name: `?IsIcsDnsEnabled@@YAHXZ`
- size: `537`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002043c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000f550`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f70e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f70e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f653`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f653`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f671`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f671`

## string_xrefs

- `0x18000f597`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 IsIcsDnsEnabled(void)
{
  BOOL v0; // ebx
  PVOID *v1; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C0h] BYREF
  wchar_t ValueName[16]; // [rsp+40h] [rbp-B8h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
  }
  v0 = 0;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"IcsDEnabled");
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
  {
    v0 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x10) != 0 && *((_BYTE *)v1 + 25) >= 4u )
      WPP_SF_d(v1[2], 14, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x18000f550  mov     [rsp+arg_0], rbx
0x18000f555  mov     [rsp+arg_8], rsi
0x18000f55a  push    rdi
0x18000f55b  sub     rsp, 0F0h
0x18000f562  mov     rax, cs:__security_cookie
0x18000f569  xor     rax, rsp
0x18000f56c  mov     [rsp+0F8h+var_18], rax
0x18000f574  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f57b  lea     rdi, WPP_GLOBAL_Control
0x18000f582  cmp     rcx, rdi
0x18000f585  jz      short loc_18000F597
0x18000f587  test    byte ptr [rcx+1Ch], 10h
0x18000f58b  jz      short loc_18000F597
0x18000f58d  cmp     byte ptr [rcx+19h], 6
0x18000f591  jnb     loc_18000F72E
0x18000f597  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18000f59e  lea     rdx, [rsp+0F8h+SubKey]; lpSubKey
0x18000f5a3  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18000f5aa  xor     ebx, ebx
0x18000f5ac  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18000f5b2  mov     esi, 1
0x18000f5b7  movaps  xmmword ptr [rsp+0F8h+SubKey], xmm0
0x18000f5bc  mov     r9d, esi; samDesired
0x18000f5bf  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18000f5c6  xor     r8d, r8d; ulOptions
0x18000f5c9  movaps  [rsp+0F8h+var_78], xmm0
0x18000f5d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f5d8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18000f5df  movaps  [rsp+0F8h+var_88], xmm1
0x18000f5e4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x18000f5eb  movaps  [rsp+0F8h+var_58], xmm0
0x18000f5f3  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18000f5fa  movaps  [rsp+0F8h+var_68], xmm1
0x18000f602  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x18000f609  movaps  [rsp+0F8h+var_38], xmm0
0x18000f611  movups  xmm0, xmmword ptr cs:aIcsdnsenabled; "IcsDnsEnabled"
0x18000f618  mov     [rsp+0F8h+var_28], eax
0x18000f61f  lea     rax, [rsp+0F8h+hKey]
0x18000f624  movaps  [rsp+0F8h+var_48], xmm1
0x18000f62c  movups  xmm1, xmmword ptr cs:aIcsdnsenabled+0Ch; "Enabled"
0x18000f633  mov     [rsp+0F8h+hKey], rbx
0x18000f638  movups  xmmword ptr [rsp+0F8h+ValueName], xmm0
0x18000f63d  mov     [rsp+0F8h+cbData], 4
0x18000f645  movups  xmmword ptr [rsp+0F8h+ValueName+0Ch], xmm1
0x18000f64a  mov     dword ptr [rsp+0F8h+Data], ebx
0x18000f64e  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18000f653  call    cs:__imp_RegOpenKeyExW
0x18000f65a  nop     dword ptr [rax+rax+00h]
0x18000f65f  test    eax, eax
0x18000f661  jz      loc_18000F6EA
0x18000f667  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18000f66c  test    rcx, rcx
0x18000f66f  jz      short loc_18000F67D
0x18000f671  call    cs:__imp_RegCloseKey
0x18000f678  nop     dword ptr [rax+rax+00h]
0x18000f67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f684  cmp     rcx, rdi
0x18000f687  jz      short loc_18000F6C2
0x18000f689  test    byte ptr [rcx+1Ch], 10h
0x18000f68d  jz      short loc_18000F699
0x18000f68f  cmp     byte ptr [rcx+19h], 6
0x18000f693  jnb     loc_18000F748
0x18000f699  cmp     rcx, rdi
0x18000f69c  jz      short loc_18000F6C2
0x18000f69e  test    byte ptr [rcx+1Ch], 10h
0x18000f6a2  jz      short loc_18000F6C2
0x18000f6a4  cmp     byte ptr [rcx+19h], 4
0x18000f6a8  jb      short loc_18000F6C2
0x18000f6aa  mov     rcx, [rcx+10h]
0x18000f6ae  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x18000f6b5  mov     edx, 0Eh
0x18000f6ba  mov     r9d, ebx
0x18000f6bd  call    WPP_SF_d
0x18000f6c2  mov     eax, ebx
0x18000f6c4  mov     rcx, [rsp+0F8h+var_18]
0x18000f6cc  xor     rcx, rsp; StackCookie
0x18000f6cf  call    __security_check_cookie
0x18000f6d4  lea     r11, [rsp+0F8h+var_8]
0x18000f6dc  mov     rbx, [r11+10h]
0x18000f6e0  mov     rsi, [r11+18h]
0x18000f6e4  mov     rsp, r11
0x18000f6e7  pop     rdi
0x18000f6e8  retn
0x18000f6ea  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18000f6ef  lea     rax, [rsp+0F8h+cbData]
0x18000f6f4  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x18000f6f9  lea     rdx, [rsp+0F8h+ValueName]; lpValueName
0x18000f6fe  lea     rax, [rsp+0F8h+Data]
0x18000f703  xor     r9d, r9d; lpType
0x18000f706  xor     r8d, r8d; lpReserved
0x18000f709  mov     [rsp+0F8h+phkResult], rax; lpData
0x18000f70e  call    cs:__imp_RegQueryValueExW
0x18000f715  nop     dword ptr [rax+rax+00h]
0x18000f71a  test    eax, eax
0x18000f71c  jnz     loc_18000F667
0x18000f722  cmp     dword ptr [rsp+0F8h+Data], ebx
0x18000f726  cmovnz  ebx, esi
0x18000f729  jmp     loc_18000F667
0x18000f72e  mov     rcx, [rcx+10h]
0x18000f732  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x18000f739  mov     edx, 0Ch
0x18000f73e  call    WPP_SF_
0x18000f743  jmp     loc_18000F597
0x18000f748  mov     rcx, [rcx+10h]
0x18000f74c  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x18000f753  mov     edx, 0Dh
0x18000f758  call    WPP_SF_
0x18000f75d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f764  jmp     loc_18000F699
```
