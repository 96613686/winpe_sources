# DaSiteMgrEnableComponentsControl

- ea: `0x18002c90c`
- end: `0x18002cb24`
- name: `DaSiteMgrEnableComponentsControl`
- size: `536`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004315c`
- `0x180070f5c`

## callees

- `0x18002c90c`
- `0x18002cb2c`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cadf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cadf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c9da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c9da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca74`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ca9b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002cab2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002cac9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ca9b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002cab2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002cac9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c98f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c98f`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18002ca00`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18002ca00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c94f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c94f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002caf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002caf2`

## string_xrefs

- `0x18002c969`: `System\CurrentControlSet\Services\iphlpsvc\DaMultisite`

## pseudocode

```c
__int64 __fastcall DaSiteMgrEnableComponentsControl(int a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx
  __int64 v7; // rax
  HKEY hKey; // [rsp+50h] [rbp-39h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-31h] BYREF
  _WORD v11[40]; // [rsp+60h] [rbp-29h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = 0;
  EnterCriticalSection(&g_DaSiteMgrConfigLock);
  RegCreateKeyExW(
    HKEY_LOCAL_MACHINE,
    L"System\\CurrentControlSet\\Services\\iphlpsvc\\DaMultisite",
    0,
    0,
    0,
    0x2001Fu,
    0,
    &hKey,
    0);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( a1 )
    {
      *(_DWORD *)Data = 1;
      RegSetValueExW(hKey, L"SiteManagerActive", 0, 4u, Data, 4u);
      memset_0(v11, 0, 0x4Eu);
      ConvertGuidToStringW(a2, v11, 39);
      v7 = -1;
      do
        ++v7;
      while ( v11[v7] );
      RegSetValueExW(hKey, L"SelectedSite", 0, 1u, (const BYTE *)v11, 2 * v7 + 2);
      *(_DWORD *)Data = a3;
      RegSetValueExW(hKey, L"SelectionMethod", 0, 4u, Data, 4u);
    }
    else
    {
      if ( (unsigned int)GetInteger2(hKey, L"SiteManagerActive", 0) )
      {
        v4 = 1;
        RegDeleteValueW(hKey, L"SiteManagerActive");
      }
      RegDeleteValueW(hKey, L"SelectedSite");
      RegDeleteValueW(hKey, L"SelectionMethod");
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  LeaveCriticalSection(&g_DaSiteMgrConfigLock);
  return v4;
}

```

## disassembly

```asm
0x18002c90c  mov     [rsp-8+arg_0], rbx
0x18002c911  push    rbp
0x18002c912  push    rsi
0x18002c913  push    rdi
0x18002c914  push    r14
0x18002c916  push    r15
0x18002c918  lea     rbp, [rsp-37h]
0x18002c91d  sub     rsp, 0C0h
0x18002c924  mov     rax, cs:__security_cookie
0x18002c92b  xor     rax, rsp
0x18002c92e  mov     [rbp+57h+var_30], rax
0x18002c932  mov     edi, ecx
0x18002c934  mov     [rbp+57h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002c93c  xor     r15d, r15d
0x18002c93f  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18002c946  mov     ebx, r15d
0x18002c949  mov     r14d, r8d
0x18002c94c  mov     rsi, rdx
0x18002c94f  call    cs:__imp_EnterCriticalSection
0x18002c956  nop     dword ptr [rax+rax+00h]
0x18002c95b  mov     [rsp+0E0h+lpdwDisposition], r15; lpdwDisposition
0x18002c960  lea     rax, [rbp+57h+hKey]
0x18002c964  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002c969  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\ip"...
0x18002c970  mov     [rsp+0E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002c975  xor     r9d, r9d; lpClass
0x18002c978  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x18002c980  xor     r8d, r8d; Reserved
0x18002c983  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c98a  mov     [rsp+0E0h+dwOptions], r15d; dwOptions
0x18002c98f  call    cs:__imp_RegCreateKeyExW
0x18002c996  nop     dword ptr [rax+rax+00h]
0x18002c99b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c99f  lea     rax, [rcx-1]
0x18002c9a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c9a7  ja      loc_18002CAEB
0x18002c9ad  xor     r8d, r8d; Reserved
0x18002c9b0  lea     rdx, aSitemanageract; "SiteManagerActive"
0x18002c9b7  test    edi, edi
0x18002c9b9  jz      loc_18002CA82
0x18002c9bf  lea     edi, [r15+4]
0x18002c9c3  mov     dword ptr [rbp+57h+Data], 1
0x18002c9ca  lea     rax, [rbp+57h+Data]
0x18002c9ce  mov     [rsp+0E0h+samDesired], edi; cbData
0x18002c9d2  mov     r9d, edi; dwType
0x18002c9d5  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002c9da  call    cs:__imp_RegSetValueExW
0x18002c9e1  nop     dword ptr [rax+rax+00h]
0x18002c9e6  xor     edx, edx; Val
0x18002c9e8  lea     r8d, [r15+4Eh]; Size
0x18002c9ec  lea     rcx, [rbp+57h+var_80]; void *
0x18002c9f0  call    memset_0
0x18002c9f5  lea     r8d, [r15+27h]
0x18002c9f9  mov     rcx, rsi
0x18002c9fc  lea     rdx, [rbp+57h+var_80]
0x18002ca00  call    cs:__imp_ConvertGuidToStringW
0x18002ca07  nop     dword ptr [rax+rax+00h]
0x18002ca0c  lea     rcx, [rbp+57h+var_80]
0x18002ca10  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ca14  inc     rax
0x18002ca17  cmp     [rcx+rax*2], r15w
0x18002ca1c  jnz     short loc_18002CA14
0x18002ca1e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca22  lea     eax, ds:2[rax*2]
0x18002ca29  mov     [rsp+0E0h+samDesired], eax; cbData
0x18002ca2d  lea     rdx, aSelectedsite; "SelectedSite"
0x18002ca34  lea     rax, [rbp+57h+var_80]
0x18002ca38  mov     r9d, 1; dwType
0x18002ca3e  xor     r8d, r8d; Reserved
0x18002ca41  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002ca46  call    cs:__imp_RegSetValueExW
0x18002ca4d  nop     dword ptr [rax+rax+00h]
0x18002ca52  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca56  lea     rax, [rbp+57h+Data]
0x18002ca5a  mov     [rsp+0E0h+samDesired], edi; cbData
0x18002ca5e  lea     rdx, aSelectionmetho; "SelectionMethod"
0x18002ca65  mov     r9d, edi; dwType
0x18002ca68  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002ca6d  xor     r8d, r8d; Reserved
0x18002ca70  mov     dword ptr [rbp+57h+Data], r14d
0x18002ca74  call    cs:__imp_RegSetValueExW
0x18002ca7b  nop     dword ptr [rax+rax+00h]
0x18002ca80  jmp     short loc_18002CAD5
0x18002ca82  call    GetInteger2
0x18002ca87  test    eax, eax
0x18002ca89  jz      short loc_18002CAA7
0x18002ca8b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca8f  lea     rdx, aSitemanageract; "SiteManagerActive"
0x18002ca96  mov     ebx, 1
0x18002ca9b  call    cs:__imp_RegDeleteValueW
0x18002caa2  nop     dword ptr [rax+rax+00h]
0x18002caa7  mov     rcx, [rbp+57h+hKey]; hKey
0x18002caab  lea     rdx, aSelectedsite; "SelectedSite"
0x18002cab2  call    cs:__imp_RegDeleteValueW
0x18002cab9  nop     dword ptr [rax+rax+00h]
0x18002cabe  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cac2  lea     rdx, aSelectionmetho; "SelectionMethod"
0x18002cac9  call    cs:__imp_RegDeleteValueW
0x18002cad0  nop     dword ptr [rax+rax+00h]
0x18002cad5  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cad9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cadd  jz      short loc_18002CAEB
0x18002cadf  call    cs:__imp_RegCloseKey
0x18002cae6  nop     dword ptr [rax+rax+00h]
0x18002caeb  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18002caf2  call    cs:__imp_LeaveCriticalSection
0x18002caf9  nop     dword ptr [rax+rax+00h]
0x18002cafe  mov     eax, ebx
0x18002cb00  mov     rcx, [rbp+57h+var_30]
0x18002cb04  xor     rcx, rsp; StackCookie
0x18002cb07  call    __security_check_cookie
0x18002cb0c  mov     rbx, [rsp+0E0h+arg_0]
0x18002cb14  add     rsp, 0C0h
0x18002cb1b  pop     r15
0x18002cb1d  pop     r14
0x18002cb1f  pop     rdi
0x18002cb20  pop     rsi
0x18002cb21  pop     rbp
0x18002cb22  retn
```
