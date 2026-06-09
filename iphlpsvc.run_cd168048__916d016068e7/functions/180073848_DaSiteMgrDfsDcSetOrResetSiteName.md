# DaSiteMgrDfsDcSetOrResetSiteName

- ea: `0x180073848`
- end: `0x18007399a`
- name: `DaSiteMgrDfsDcSetOrResetSiteName`
- size: `338`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18004319c`
- `0x180070f3c`

## callees

- `0x180073848`
- `0x180076d44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800738d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007397e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800738d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007397e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007395c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007395c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007396a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007396a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073893`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073918`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073893`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073918`

## string_xrefs

- `0x180073860`: `System\CurrentControlSet\Services\Netlogon\Parameters`
- `0x1800738f3`: `System\CurrentControlSet\Services\DfsC\Parameters`

## pseudocode

```c
__int64 __fastcall DaSiteMgrDfsDcSetOrResetSiteName(BYTE *lpData)
{
  __int64 v2; // rbx
  unsigned int v3; // edi
  int Data; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  v2 = -1;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Netlogon\\Parameters",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         0);
  if ( !v3 )
  {
    do
      ++v2;
    while ( *(_WORD *)&lpData[2 * v2] );
    SetOrDeleteString(hKey, L"SiteName", lpData);
    RegCloseKey(hKey);
    v3 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\DfsC\\Parameters",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hKey,
           0);
    if ( !v3 )
    {
      if ( *(_WORD *)lpData )
      {
        Data = 1;
        RegSetValueExW(hKey, L"UseDcLocatorSiteName", 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        RegDeleteValueW(hKey, L"UseDcLocatorSiteName");
      }
      RegCloseKey(hKey);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180073848  mov     r11, rsp
0x18007384b  mov     [r11+8], rbx
0x18007384f  push    rbp
0x180073850  push    rsi
0x180073851  push    rdi
0x180073852  sub     rsp, 50h
0x180073856  xor     ebp, ebp
0x180073858  lea     rax, [r11+18h]
0x18007385c  mov     [r11-28h], rbp
0x180073860  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Services\\Ne"...
0x180073867  mov     [r11-30h], rax
0x18007386b  mov     rsi, rcx
0x18007386e  mov     [r11-38h], rbp
0x180073872  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180073876  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18007387e  xor     r9d, r9d; lpClass
0x180073881  xor     r8d, r8d; Reserved
0x180073884  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x180073888  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007388f  mov     [r11+18h], rbx
0x180073893  call    cs:__imp_RegCreateKeyExW
0x18007389a  nop     dword ptr [rax+rax+00h]
0x18007389f  mov     edi, eax
0x1800738a1  test    eax, eax
0x1800738a3  jnz     loc_18007398A
0x1800738a9  inc     rbx
0x1800738ac  cmp     [rsi+rbx*2], bp
0x1800738b0  jnz     short loc_1800738A9
0x1800738b2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800738ba  lea     r9d, [rbx+1]
0x1800738be  mov     r8, rsi; lpData
0x1800738c1  lea     rdx, aSitename; "SiteName"
0x1800738c8  call    SetOrDeleteString
0x1800738cd  mov     rcx, [rsp+68h+hKey]; hKey
0x1800738d5  call    cs:__imp_RegCloseKey
0x1800738dc  nop     dword ptr [rax+rax+00h]
0x1800738e1  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x1800738e6  lea     rax, [rsp+68h+hKey]
0x1800738ee  mov     [rsp+68h+phkResult], rax; phkResult
0x1800738f3  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Df"...
0x1800738fa  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1800738ff  xor     r9d, r9d; lpClass
0x180073902  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18007390a  xor     r8d, r8d; Reserved
0x18007390d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073914  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x180073918  call    cs:__imp_RegCreateKeyExW
0x18007391f  nop     dword ptr [rax+rax+00h]
0x180073924  mov     edi, eax
0x180073926  test    eax, eax
0x180073928  jnz     short loc_18007398A
0x18007392a  lea     rdx, aUsedclocatorsi; "UseDcLocatorSiteName"
0x180073931  mov     rcx, [rsp+68h+hKey]; hKey
0x180073939  cmp     [rsi], bp
0x18007393c  jz      short loc_18007396A
0x18007393e  lea     r9d, [rax+4]; dwType
0x180073942  mov     [rsp+68h+Data], 1
0x18007394a  lea     rax, [rsp+68h+Data]
0x18007394f  mov     [rsp+68h+samDesired], r9d; cbData
0x180073954  xor     r8d, r8d; Reserved
0x180073957  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18007395c  call    cs:__imp_RegSetValueExW
0x180073963  nop     dword ptr [rax+rax+00h]
0x180073968  jmp     short loc_180073976
0x18007396a  call    cs:__imp_RegDeleteValueW
0x180073971  nop     dword ptr [rax+rax+00h]
0x180073976  mov     rcx, [rsp+68h+hKey]; hKey
0x18007397e  call    cs:__imp_RegCloseKey
0x180073985  nop     dword ptr [rax+rax+00h]
0x18007398a  mov     rbx, [rsp+68h+arg_0]
0x18007398f  mov     eax, edi
0x180073991  add     rsp, 50h
0x180073995  pop     rdi
0x180073996  pop     rsi
0x180073997  pop     rbp
0x180073998  retn
```
