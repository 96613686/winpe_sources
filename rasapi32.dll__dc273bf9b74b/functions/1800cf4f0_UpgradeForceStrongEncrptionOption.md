# UpgradeForceStrongEncrptionOption

- ea: `0x1800cf4f0`
- end: `0x1800cf68f`
- name: `UpgradeForceStrongEncrptionOption`
- size: `415`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800cf698`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800cf4f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800cf630`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800cf630`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf570`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf649`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800cf5de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800cf5de`

## string_xrefs

- `0x1800cf54a`: `System\CurrentControlSet\Services\Rasman\PPP`

## pseudocode

```c
__int64 __fastcall UpgradeForceStrongEncrptionOption(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  char *v6; // rcx
  __int64 v7; // rdx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 869, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  hKeya = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  v4 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\Rasman\\PPP", 0, 0x20019u, &hKeya);
  v5 = v4;
  if ( v4 )
  {
    v6 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 870;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v4);
LABEL_20:
      v6 = (char *)WPP_GLOBAL_Control;
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
    v6 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 871;
      goto LABEL_10;
    }
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v6 = (char *)WPP_GLOBAL_Control;
  }
  if ( v6 != (char *)&WPP_GLOBAL_Control && v6[28] < 0 && (unsigned __int8)v6[25] >= 6u )
    WPP_SF_d(*((_QWORD *)v6 + 2), 872, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800cf4f0  mov     [rsp-18h+arg_0], rbx
0x1800cf4f5  push    rbp
0x1800cf4f6  push    rdi
0x1800cf4f7  push    r14
0x1800cf4f9  mov     rbp, rsp
0x1800cf4fc  sub     rsp, 40h
0x1800cf500  mov     rdi, rdx
0x1800cf503  mov     rbx, rcx
0x1800cf506  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf50d  lea     r14, WPP_GLOBAL_Control
0x1800cf514  cmp     rcx, r14
0x1800cf517  jz      short loc_1800CF53A
0x1800cf519  test    byte ptr [rcx+1Ch], 80h
0x1800cf51d  jz      short loc_1800CF53A
0x1800cf51f  cmp     byte ptr [rcx+19h], 6
0x1800cf523  jb      short loc_1800CF53A
0x1800cf525  mov     rcx, [rcx+10h]
0x1800cf529  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cf530  mov     edx, 365h
0x1800cf535  call    WPP_SF_
0x1800cf53a  mov     eax, 4
0x1800cf53f  mov     [rbp+hKey], 0
0x1800cf547  mov     [rbp+Type], eax
0x1800cf54a  lea     rdx, c_pszRegKeySecureVpn; "System\\CurrentControlSet\\Services\\Ra"...
0x1800cf551  mov     [rbp+cbData], eax
0x1800cf554  mov     r9d, 20019h; samDesired
0x1800cf55a  lea     rax, [rbp+hKey]
0x1800cf55e  mov     [rbp+Data], 0
0x1800cf565  xor     r8d, r8d; ulOptions
0x1800cf568  mov     [rsp+40h+phkResult], rax; phkResult
0x1800cf56d  mov     rcx, rbx; hKey
0x1800cf570  call    cs:__imp_RegOpenKeyExW
0x1800cf576  mov     ebx, eax
0x1800cf578  test    eax, eax
0x1800cf57a  jz      short loc_1800CF5BA
0x1800cf57c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf583  cmp     rcx, r14
0x1800cf586  jz      loc_1800CF63D
0x1800cf58c  test    byte ptr [rcx+1Ch], 80h
0x1800cf590  jz      loc_1800CF63D
0x1800cf596  cmp     byte ptr [rcx+19h], 2
0x1800cf59a  jb      loc_1800CF63D
0x1800cf5a0  mov     edx, 366h
0x1800cf5a5  mov     rcx, [rcx+10h]
0x1800cf5a9  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cf5b0  mov     r9d, eax
0x1800cf5b3  call    WPP_SF_d
0x1800cf5b8  jmp     short loc_1800CF636
0x1800cf5ba  mov     rcx, [rbp+hKey]; hKey
0x1800cf5be  lea     rax, [rbp+cbData]
0x1800cf5c2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800cf5c7  lea     r9, [rbp+Type]; lpType
0x1800cf5cb  lea     rax, [rbp+Data]
0x1800cf5cf  xor     r8d, r8d; lpReserved
0x1800cf5d2  lea     rdx, c_pszRegValForceStrongEncryption; "ForceStrongEncryption"
0x1800cf5d9  mov     [rsp+40h+phkResult], rax; lpData
0x1800cf5de  call    cs:__imp_RegQueryValueExW
0x1800cf5e4  mov     ebx, eax
0x1800cf5e6  test    eax, eax
0x1800cf5e8  jz      short loc_1800CF609
0x1800cf5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf5f1  cmp     rcx, r14
0x1800cf5f4  jz      short loc_1800CF63D
0x1800cf5f6  test    byte ptr [rcx+1Ch], 80h
0x1800cf5fa  jz      short loc_1800CF63D
0x1800cf5fc  cmp     byte ptr [rcx+19h], 2
0x1800cf600  jb      short loc_1800CF63D
0x1800cf602  mov     edx, 367h
0x1800cf607  jmp     short loc_1800CF5A5
0x1800cf609  cmp     [rbp+Data], 0
0x1800cf60d  jz      short loc_1800CF625
0x1800cf60f  cmp     dword ptr [rdi+0ACh], 100h
0x1800cf619  jnz     short loc_1800CF625
0x1800cf61b  mov     dword ptr [rdi+0ACh], 200h
0x1800cf625  mov     rcx, [rbp+hKey]; hKey
0x1800cf629  lea     rdx, c_pszRegValForceStrongEncryption; "ForceStrongEncryption"
0x1800cf630  call    cs:__imp_RegDeleteValueW
0x1800cf636  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf63d  mov     rax, [rbp+hKey]
0x1800cf641  test    rax, rax
0x1800cf644  jz      short loc_1800CF656
0x1800cf646  mov     rcx, rax; hKey
0x1800cf649  call    cs:__imp_RegCloseKey
0x1800cf64f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf656  cmp     rcx, r14
0x1800cf659  jz      short loc_1800CF67F
0x1800cf65b  test    byte ptr [rcx+1Ch], 80h
0x1800cf65f  jz      short loc_1800CF67F
0x1800cf661  cmp     byte ptr [rcx+19h], 6
0x1800cf665  jb      short loc_1800CF67F
0x1800cf667  mov     rcx, [rcx+10h]
0x1800cf66b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cf672  mov     edx, 368h
0x1800cf677  mov     r9d, ebx
0x1800cf67a  call    WPP_SF_d
0x1800cf67f  mov     eax, ebx
0x1800cf681  mov     rbx, [rsp+40h+arg_0]
0x1800cf686  add     rsp, 40h
0x1800cf68a  pop     r14
0x1800cf68c  pop     rdi
0x1800cf68d  pop     rbp
0x1800cf68e  retn
```
