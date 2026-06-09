# SavedCredsFeatureEnabledForUsernamePassword(void)

- ea: `0x18006871c`
- end: `0x18006882a`
- name: `?SavedCredsFeatureEnabledForUsernamePassword@@YAHXZ`
- size: `270`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180068e40`

## callees

- `0x180005010`
- `0x18006871c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068814`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068759`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068759`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800687ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800687ac`

## string_xrefs

- `0x180068746`: `SYSTEM\CurrentControlSet\Services\Eaphost\Configuration`

## pseudocode

```c
__int64 SavedCredsFeatureEnabledForUsernamePassword(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 v2; // r9
  struct _EAPTLS_CONTROL_BLOCK *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  cbData = 4;
  hKey = 0;
  Type = 0;
  Data = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Eaphost\\Configuration",
         0,
         0x20019u,
         &hKey);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_14;
    v4 = 10;
    goto LABEL_13;
  }
  v5 = RegQueryValueExW(hKey, L"DisableUsrPwdStoring", 0, &Type, (LPBYTE)&Data, &cbData);
  v2 = v5;
  if ( v5 )
  {
    if ( v5 == 2 )
    {
      v0 = 1;
      goto LABEL_14;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v4 = 11;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v2);
    }
  }
  else if ( Type != 4 || cbData != 4 || (v0 = 1, Data == 1) )
  {
    v0 = 0;
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18006871c  push    rbp
0x18006871e  push    rbx
0x18006871f  mov     rbp, rsp
0x180068722  sub     rsp, 38h
0x180068726  xor     ebx, ebx
0x180068728  mov     [rbp+cbData], 4
0x18006872f  lea     rax, [rbp+hKey]
0x180068733  mov     [rbp+hKey], rbx
0x180068737  mov     r9d, 20019h; samDesired
0x18006873d  mov     [rbp+Type], ebx
0x180068740  xor     r8d, r8d; ulOptions
0x180068743  mov     [rbp+Data], ebx
0x180068746  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x18006874d  mov     [rsp+38h+phkResult], rax; phkResult
0x180068752  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068759  call    cs:__imp_RegOpenKeyExW
0x180068760  nop     dword ptr [rax+rax+00h]
0x180068765  mov     r9d, eax
0x180068768  test    eax, eax
0x18006876a  jz      short loc_180068788
0x18006876c  mov     rcx, cs:WPP_GLOBAL_Control
0x180068773  lea     rax, WPP_GLOBAL_Control
0x18006877a  cmp     rcx, rax
0x18006877d  jz      loc_18006880B
0x180068783  lea     edx, [rbx+0Ah]
0x180068786  jmp     short loc_1800687FB
0x180068788  mov     rcx, [rbp+hKey]; hKey
0x18006878c  lea     rax, [rbp+cbData]
0x180068790  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180068795  lea     r9, [rbp+Type]; lpType
0x180068799  lea     rax, [rbp+Data]
0x18006879d  xor     r8d, r8d; lpReserved
0x1800687a0  lea     rdx, aDisableusrpwds; "DisableUsrPwdStoring"
0x1800687a7  mov     [rsp+38h+phkResult], rax; lpData
0x1800687ac  call    cs:__imp_RegQueryValueExW
0x1800687b3  nop     dword ptr [rax+rax+00h]
0x1800687b8  mov     r9d, eax
0x1800687bb  test    eax, eax
0x1800687bd  jnz     short loc_1800687D7
0x1800687bf  cmp     [rbp+Type], 4
0x1800687c3  jnz     short loc_1800687D3
0x1800687c5  cmp     [rbp+cbData], 4
0x1800687c9  jnz     short loc_1800687D3
0x1800687cb  lea     ebx, [rax+1]
0x1800687ce  cmp     [rbp+Data], ebx
0x1800687d1  jnz     short loc_18006880B
0x1800687d3  xor     ebx, ebx
0x1800687d5  jmp     short loc_18006880B
0x1800687d7  cmp     r9d, 2
0x1800687db  jnz     short loc_1800687E3
0x1800687dd  lea     ebx, [r9-1]
0x1800687e1  jmp     short loc_18006880B
0x1800687e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800687ea  lea     rax, WPP_GLOBAL_Control
0x1800687f1  cmp     rcx, rax
0x1800687f4  jz      short loc_18006880B
0x1800687f6  mov     edx, 0Bh
0x1800687fb  mov     rcx, [rcx+10h]
0x1800687ff  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180068806  call    WPP_SF_d
0x18006880b  mov     rcx, [rbp+hKey]; hKey
0x18006880f  test    rcx, rcx
0x180068812  jz      short loc_180068820
0x180068814  call    cs:__imp_RegCloseKey
0x18006881b  nop     dword ptr [rax+rax+00h]
0x180068820  mov     eax, ebx
0x180068822  add     rsp, 38h
0x180068826  pop     rbx
0x180068827  pop     rbp
0x180068828  retn
```
