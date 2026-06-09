# DaSiteMgrDfsDcSetOrResetSiteName

- ea: `0x180073868`
- end: `0x1800739ba`
- name: `DaSiteMgrDfsDcSetOrResetSiteName`
- size: `338`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18004315c`
- `0x180070f5c`

## callees

- `0x180073868`
- `0x180076d64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800738f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007399e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800738f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007399e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007397c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007397c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007398a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007398a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800738b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073938`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800738b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073938`

## string_xrefs

- `0x180073880`: `System\CurrentControlSet\Services\Netlogon\Parameters`
- `0x180073913`: `System\CurrentControlSet\Services\DfsC\Parameters`

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
0x180073868  mov     r11, rsp
0x18007386b  mov     [r11+8], rbx
0x18007386f  push    rbp
0x180073870  push    rsi
0x180073871  push    rdi
0x180073872  sub     rsp, 50h
0x180073876  xor     ebp, ebp
0x180073878  lea     rax, [r11+18h]
0x18007387c  mov     [r11-28h], rbp
0x180073880  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Services\\Ne"...
0x180073887  mov     [r11-30h], rax
0x18007388b  mov     rsi, rcx
0x18007388e  mov     [r11-38h], rbp
0x180073892  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180073896  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18007389e  xor     r9d, r9d; lpClass
0x1800738a1  xor     r8d, r8d; Reserved
0x1800738a4  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x1800738a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800738af  mov     [r11+18h], rbx
0x1800738b3  call    cs:__imp_RegCreateKeyExW
0x1800738ba  nop     dword ptr [rax+rax+00h]
0x1800738bf  mov     edi, eax
0x1800738c1  test    eax, eax
0x1800738c3  jnz     loc_1800739AA
0x1800738c9  inc     rbx
0x1800738cc  cmp     [rsi+rbx*2], bp
0x1800738d0  jnz     short loc_1800738C9
0x1800738d2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800738da  lea     r9d, [rbx+1]
0x1800738de  mov     r8, rsi; lpData
0x1800738e1  lea     rdx, aSitename; "SiteName"
0x1800738e8  call    SetOrDeleteString
0x1800738ed  mov     rcx, [rsp+68h+hKey]; hKey
0x1800738f5  call    cs:__imp_RegCloseKey
0x1800738fc  nop     dword ptr [rax+rax+00h]
0x180073901  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x180073906  lea     rax, [rsp+68h+hKey]
0x18007390e  mov     [rsp+68h+phkResult], rax; phkResult
0x180073913  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Df"...
0x18007391a  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18007391f  xor     r9d, r9d; lpClass
0x180073922  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18007392a  xor     r8d, r8d; Reserved
0x18007392d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073934  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x180073938  call    cs:__imp_RegCreateKeyExW
0x18007393f  nop     dword ptr [rax+rax+00h]
0x180073944  mov     edi, eax
0x180073946  test    eax, eax
0x180073948  jnz     short loc_1800739AA
0x18007394a  lea     rdx, aUsedclocatorsi; "UseDcLocatorSiteName"
0x180073951  mov     rcx, [rsp+68h+hKey]; hKey
0x180073959  cmp     [rsi], bp
0x18007395c  jz      short loc_18007398A
0x18007395e  lea     r9d, [rax+4]; dwType
0x180073962  mov     [rsp+68h+Data], 1
0x18007396a  lea     rax, [rsp+68h+Data]
0x18007396f  mov     [rsp+68h+samDesired], r9d; cbData
0x180073974  xor     r8d, r8d; Reserved
0x180073977  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18007397c  call    cs:__imp_RegSetValueExW
0x180073983  nop     dword ptr [rax+rax+00h]
0x180073988  jmp     short loc_180073996
0x18007398a  call    cs:__imp_RegDeleteValueW
0x180073991  nop     dword ptr [rax+rax+00h]
0x180073996  mov     rcx, [rsp+68h+hKey]; hKey
0x18007399e  call    cs:__imp_RegCloseKey
0x1800739a5  nop     dword ptr [rax+rax+00h]
0x1800739aa  mov     rbx, [rsp+68h+arg_0]
0x1800739af  mov     eax, edi
0x1800739b1  add     rsp, 50h
0x1800739b5  pop     rdi
0x1800739b6  pop     rsi
0x1800739b7  pop     rbp
0x1800739b8  retn
```
