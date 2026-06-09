# InitializeRegControlForICSIPv6(void)

- ea: `0x18003726c`
- end: `0x1800373cc`
- name: `?InitializeRegControlForICSIPv6@@YAKXZ`
- size: `352`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180036364`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003726c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037333`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037333`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800372d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800372d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037387`

## string_xrefs

- `0x1800372ca`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 InitializeRegControlForICSIPv6(void)
{
  unsigned int v0; // eax
  PVOID *v1; // rcx
  __int64 v2; // rdx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids);
  }
  hKey = 0;
  cbData = 4;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters", 0, 1u, &hKey);
  if ( v0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 46;
LABEL_15:
      WPP_SF_d(v1[2], v2, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids, v0);
      goto LABEL_16;
    }
  }
  else
  {
    v0 = RegQueryValueExW(hKey, L"EnableICSIPv6", 0, 0, &gEnabledICSIPv6, &cbData);
    if ( !v0 )
    {
LABEL_16:
      v1 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v2 = 47;
      goto LABEL_15;
    }
  }
LABEL_17:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control && *((char *)v1 + 28) < 0 && *((_BYTE *)v1 + 25) >= 6u )
    WPP_SF_d(v1[2], 48, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18003726c  push    rdi
0x18003726e  sub     rsp, 30h
0x180037272  mov     rcx, cs:WPP_GLOBAL_Control
0x180037279  lea     rdi, WPP_GLOBAL_Control
0x180037280  cmp     rcx, rdi
0x180037283  jz      short loc_1800372A6
0x180037285  test    byte ptr [rcx+1Ch], 80h
0x180037289  jz      short loc_1800372A6
0x18003728b  cmp     byte ptr [rcx+19h], 6
0x18003728f  jb      short loc_1800372A6
0x180037291  mov     rcx, [rcx+10h]
0x180037295  lea     r8, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids
0x18003729c  mov     edx, 2Dh ; '-'
0x1800372a1  call    WPP_SF_
0x1800372a6  lea     rax, [rsp+38h+hKey]
0x1800372ab  mov     [rsp+38h+hKey], 0
0x1800372b4  mov     r9d, 1; samDesired
0x1800372ba  mov     [rsp+38h+phkResult], rax; phkResult
0x1800372bf  xor     r8d, r8d; ulOptions
0x1800372c2  mov     [rsp+38h+cbData], 4
0x1800372ca  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x1800372d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800372d8  call    cs:__imp_RegOpenKeyExW
0x1800372df  nop     dword ptr [rax+rax+00h]
0x1800372e4  test    eax, eax
0x1800372e6  jz      short loc_18003730B
0x1800372e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372ef  cmp     rcx, rdi
0x1800372f2  jz      loc_18003737A
0x1800372f8  test    byte ptr [rcx+1Ch], 80h
0x1800372fc  jz      short loc_18003737A
0x1800372fe  cmp     byte ptr [rcx+19h], 2
0x180037302  jb      short loc_18003737A
0x180037304  mov     edx, 2Eh ; '.'
0x180037309  jmp     short loc_180037360
0x18003730b  mov     rcx, [rsp+38h+hKey]; hKey
0x180037310  lea     rax, [rsp+38h+cbData]
0x180037315  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003731a  lea     rdx, aEnableicsipv6; "EnableICSIPv6"
0x180037321  lea     rax, ?gEnabledICSIPv6@@3KA; ulong gEnabledICSIPv6
0x180037328  xor     r9d, r9d; lpType
0x18003732b  xor     r8d, r8d; lpReserved
0x18003732e  mov     [rsp+38h+phkResult], rax; lpData
0x180037333  call    cs:__imp_RegQueryValueExW
0x18003733a  nop     dword ptr [rax+rax+00h]
0x18003733f  test    eax, eax
0x180037341  jz      short loc_180037373
0x180037343  mov     rcx, cs:WPP_GLOBAL_Control
0x18003734a  cmp     rcx, rdi
0x18003734d  jz      short loc_18003737A
0x18003734f  test    byte ptr [rcx+1Ch], 80h
0x180037353  jz      short loc_18003737A
0x180037355  cmp     byte ptr [rcx+19h], 3
0x180037359  jb      short loc_18003737A
0x18003735b  mov     edx, 2Fh ; '/'
0x180037360  mov     rcx, [rcx+10h]
0x180037364  lea     r8, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids
0x18003736b  mov     r9d, eax
0x18003736e  call    WPP_SF_d
0x180037373  mov     rcx, cs:WPP_GLOBAL_Control
0x18003737a  mov     rax, [rsp+38h+hKey]
0x18003737f  test    rax, rax
0x180037382  jz      short loc_18003739A
0x180037384  mov     rcx, rax; hKey
0x180037387  call    cs:__imp_RegCloseKey
0x18003738e  nop     dword ptr [rax+rax+00h]
0x180037393  mov     rcx, cs:WPP_GLOBAL_Control
0x18003739a  cmp     rcx, rdi
0x18003739d  jz      short loc_1800373C3
0x18003739f  test    byte ptr [rcx+1Ch], 80h
0x1800373a3  jz      short loc_1800373C3
0x1800373a5  cmp     byte ptr [rcx+19h], 6
0x1800373a9  jb      short loc_1800373C3
0x1800373ab  mov     rcx, [rcx+10h]
0x1800373af  lea     r8, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids
0x1800373b6  mov     edx, 30h ; '0'
0x1800373bb  xor     r9d, r9d
0x1800373be  call    WPP_SF_d
0x1800373c3  xor     eax, eax
0x1800373c5  add     rsp, 30h
0x1800373c9  pop     rdi
0x1800373ca  retn
```
