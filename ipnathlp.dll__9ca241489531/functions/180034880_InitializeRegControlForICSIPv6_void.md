# InitializeRegControlForICSIPv6(void)

- ea: `0x180034880`
- end: `0x1800349c9`
- name: `?InitializeRegControlForICSIPv6@@YAKXZ`
- size: `329`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180033a64`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180034880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003493d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003493d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800348ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800348ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003498b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003498b`

## string_xrefs

- `0x1800348de`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
0x180034880  push    rdi
0x180034882  sub     rsp, 30h
0x180034886  mov     rcx, cs:WPP_GLOBAL_Control
0x18003488d  lea     rdi, WPP_GLOBAL_Control
0x180034894  cmp     rcx, rdi
0x180034897  jz      short loc_1800348BA
0x180034899  test    byte ptr [rcx+1Ch], 80h
0x18003489d  jz      short loc_1800348BA
0x18003489f  cmp     byte ptr [rcx+19h], 6
0x1800348a3  jb      short loc_1800348BA
0x1800348a5  mov     rcx, [rcx+10h]
0x1800348a9  lea     r8, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids
0x1800348b0  mov     edx, 2Dh ; '-'
0x1800348b5  call    WPP_SF_
0x1800348ba  lea     rax, [rsp+38h+hKey]
0x1800348bf  mov     [rsp+38h+hKey], 0
0x1800348c8  mov     r9d, 1; samDesired
0x1800348ce  mov     [rsp+38h+phkResult], rax; phkResult
0x1800348d3  xor     r8d, r8d; ulOptions
0x1800348d6  mov     [rsp+38h+cbData], 4
0x1800348de  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x1800348e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800348ec  call    cs:__imp_RegOpenKeyExW
0x1800348f2  test    eax, eax
0x1800348f4  jz      short loc_180034915
0x1800348f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348fd  cmp     rcx, rdi
0x180034900  jz      short loc_18003497E
0x180034902  test    byte ptr [rcx+1Ch], 80h
0x180034906  jz      short loc_18003497E
0x180034908  cmp     byte ptr [rcx+19h], 2
0x18003490c  jb      short loc_18003497E
0x18003490e  mov     edx, 2Eh ; '.'
0x180034913  jmp     short loc_180034964
0x180034915  mov     rcx, [rsp+38h+hKey]; hKey
0x18003491a  lea     rax, [rsp+38h+cbData]
0x18003491f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180034924  lea     rdx, aEnableicsipv6; "EnableICSIPv6"
0x18003492b  lea     rax, ?gEnabledICSIPv6@@3KA; ulong gEnabledICSIPv6
0x180034932  xor     r9d, r9d; lpType
0x180034935  xor     r8d, r8d; lpReserved
0x180034938  mov     [rsp+38h+phkResult], rax; lpData
0x18003493d  call    cs:__imp_RegQueryValueExW
0x180034943  test    eax, eax
0x180034945  jz      short loc_180034977
0x180034947  mov     rcx, cs:WPP_GLOBAL_Control
0x18003494e  cmp     rcx, rdi
0x180034951  jz      short loc_18003497E
0x180034953  test    byte ptr [rcx+1Ch], 80h
0x180034957  jz      short loc_18003497E
0x180034959  cmp     byte ptr [rcx+19h], 3
0x18003495d  jb      short loc_18003497E
0x18003495f  mov     edx, 2Fh ; '/'
0x180034964  mov     rcx, [rcx+10h]
0x180034968  lea     r8, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids
0x18003496f  mov     r9d, eax
0x180034972  call    WPP_SF_d
0x180034977  mov     rcx, cs:WPP_GLOBAL_Control
0x18003497e  mov     rax, [rsp+38h+hKey]
0x180034983  test    rax, rax
0x180034986  jz      short loc_180034998
0x180034988  mov     rcx, rax; hKey
0x18003498b  call    cs:__imp_RegCloseKey
0x180034991  mov     rcx, cs:WPP_GLOBAL_Control
0x180034998  cmp     rcx, rdi
0x18003499b  jz      short loc_1800349C1
0x18003499d  test    byte ptr [rcx+1Ch], 80h
0x1800349a1  jz      short loc_1800349C1
0x1800349a3  cmp     byte ptr [rcx+19h], 6
0x1800349a7  jb      short loc_1800349C1
0x1800349a9  mov     rcx, [rcx+10h]
0x1800349ad  lea     r8, WPP_1ad2f3a6fe2d3e3af4fbc552326e8bb7_Traceguids
0x1800349b4  mov     edx, 30h ; '0'
0x1800349b9  xor     r9d, r9d
0x1800349bc  call    WPP_SF_d
0x1800349c1  xor     eax, eax
0x1800349c3  add     rsp, 30h
0x1800349c7  pop     rdi
0x1800349c8  retn
```
