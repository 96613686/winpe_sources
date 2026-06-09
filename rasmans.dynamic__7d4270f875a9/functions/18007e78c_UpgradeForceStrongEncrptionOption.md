# UpgradeForceStrongEncrptionOption

- ea: `0x18007e78c`
- end: `0x18007e947`
- name: `UpgradeForceStrongEncrptionOption`
- size: `443`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18007e950`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18007e78c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e80c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e80c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e8fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e8fa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007e8db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007e8db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007e883`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007e883`

## string_xrefs

- `0x18007e7e6`: `System\CurrentControlSet\Services\Rasman\PPP`

## pseudocode

```c
__int64 __fastcall UpgradeForceStrongEncrptionOption(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 869, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  hKeya = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  v4 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\Rasman\\PPP", 0, 0x20019u, &hKeya);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v7 = 870;
LABEL_10:
      WPP_SF_d(v6[1].Flink, v7, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v4);
LABEL_20:
      v6 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v4 = RegQueryValueExW(hKeya, L"ForceStrongEncryption", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v4;
    if ( !v4 )
    {
      if ( Data && *(_DWORD *)(a2 + 172) == 256 )
        *(_DWORD *)(a2 + 172) = 512;
      RegDeleteValueW(hKeya, L"ForceStrongEncryption");
      goto LABEL_20;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v7 = 871;
      goto LABEL_10;
    }
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v6[1].Blink) < 0 && BYTE1(v6[1].Blink) >= 6u )
    WPP_SF_d(v6[1].Flink, 872, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18007e78c  mov     [rsp-18h+arg_0], rbx
0x18007e791  push    rbp
0x18007e792  push    rdi
0x18007e793  push    r14
0x18007e795  mov     rbp, rsp
0x18007e798  sub     rsp, 40h
0x18007e79c  mov     rdi, rdx
0x18007e79f  mov     rbx, rcx
0x18007e7a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e7a9  lea     r14, WPP_GLOBAL_Control
0x18007e7b0  cmp     rcx, r14
0x18007e7b3  jz      short loc_18007E7D6
0x18007e7b5  test    byte ptr [rcx+1Ch], 80h
0x18007e7b9  jz      short loc_18007E7D6
0x18007e7bb  cmp     byte ptr [rcx+19h], 6
0x18007e7bf  jb      short loc_18007E7D6
0x18007e7c1  mov     rcx, [rcx+10h]
0x18007e7c5  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007e7cc  mov     edx, 365h
0x18007e7d1  call    WPP_SF_
0x18007e7d6  mov     eax, 4
0x18007e7db  mov     [rbp+hKey], 0
0x18007e7e3  mov     [rbp+Type], eax
0x18007e7e6  lea     rdx, c_pszRegKeySecureVpn; "System\\CurrentControlSet\\Services\\Ra"...
0x18007e7ed  mov     [rbp+cbData], eax
0x18007e7f0  mov     r9d, 20019h; samDesired
0x18007e7f6  lea     rax, [rbp+hKey]
0x18007e7fa  mov     [rbp+Data], 0
0x18007e801  xor     r8d, r8d; ulOptions
0x18007e804  mov     [rsp+40h+phkResult], rax; phkResult
0x18007e809  mov     rcx, rbx; hKey
0x18007e80c  call    cs:__imp_RegOpenKeyExW
0x18007e813  nop     dword ptr [rax+rax+00h]
0x18007e818  mov     ebx, eax
0x18007e81a  test    eax, eax
0x18007e81c  jz      short loc_18007E85F
0x18007e81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e825  cmp     rcx, r14
0x18007e828  jz      loc_18007E8EE
0x18007e82e  test    byte ptr [rcx+1Ch], 80h
0x18007e832  jz      loc_18007E8EE
0x18007e838  cmp     byte ptr [rcx+19h], 2
0x18007e83c  jb      loc_18007E8EE
0x18007e842  mov     edx, 366h
0x18007e847  mov     rcx, [rcx+10h]
0x18007e84b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007e852  mov     r9d, eax
0x18007e855  call    WPP_SF_d
0x18007e85a  jmp     loc_18007E8E7
0x18007e85f  mov     rcx, [rbp+hKey]; hKey
0x18007e863  lea     rax, [rbp+cbData]
0x18007e867  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18007e86c  lea     r9, [rbp+Type]; lpType
0x18007e870  lea     rax, [rbp+Data]
0x18007e874  xor     r8d, r8d; lpReserved
0x18007e877  lea     rdx, c_pszRegValForceStrongEncryption; "ForceStrongEncryption"
0x18007e87e  mov     [rsp+40h+phkResult], rax; lpData
0x18007e883  call    cs:__imp_RegQueryValueExW
0x18007e88a  nop     dword ptr [rax+rax+00h]
0x18007e88f  mov     ebx, eax
0x18007e891  test    eax, eax
0x18007e893  jz      short loc_18007E8B4
0x18007e895  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e89c  cmp     rcx, r14
0x18007e89f  jz      short loc_18007E8EE
0x18007e8a1  test    byte ptr [rcx+1Ch], 80h
0x18007e8a5  jz      short loc_18007E8EE
0x18007e8a7  cmp     byte ptr [rcx+19h], 2
0x18007e8ab  jb      short loc_18007E8EE
0x18007e8ad  mov     edx, 367h
0x18007e8b2  jmp     short loc_18007E847
0x18007e8b4  cmp     [rbp+Data], 0
0x18007e8b8  jz      short loc_18007E8D0
0x18007e8ba  cmp     dword ptr [rdi+0ACh], 100h
0x18007e8c4  jnz     short loc_18007E8D0
0x18007e8c6  mov     dword ptr [rdi+0ACh], 200h
0x18007e8d0  mov     rcx, [rbp+hKey]; hKey
0x18007e8d4  lea     rdx, c_pszRegValForceStrongEncryption; "ForceStrongEncryption"
0x18007e8db  call    cs:__imp_RegDeleteValueW
0x18007e8e2  nop     dword ptr [rax+rax+00h]
0x18007e8e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e8ee  mov     rax, [rbp+hKey]
0x18007e8f2  test    rax, rax
0x18007e8f5  jz      short loc_18007E90D
0x18007e8f7  mov     rcx, rax; hKey
0x18007e8fa  call    cs:__imp_RegCloseKey
0x18007e901  nop     dword ptr [rax+rax+00h]
0x18007e906  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e90d  cmp     rcx, r14
0x18007e910  jz      short loc_18007E936
0x18007e912  test    byte ptr [rcx+1Ch], 80h
0x18007e916  jz      short loc_18007E936
0x18007e918  cmp     byte ptr [rcx+19h], 6
0x18007e91c  jb      short loc_18007E936
0x18007e91e  mov     rcx, [rcx+10h]
0x18007e922  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007e929  mov     edx, 368h
0x18007e92e  mov     r9d, ebx
0x18007e931  call    WPP_SF_d
0x18007e936  mov     eax, ebx
0x18007e938  mov     rbx, [rsp+40h+arg_0]
0x18007e93d  add     rsp, 40h
0x18007e941  pop     r14
0x18007e943  pop     rdi
0x18007e944  pop     rbp
0x18007e945  retn
```
