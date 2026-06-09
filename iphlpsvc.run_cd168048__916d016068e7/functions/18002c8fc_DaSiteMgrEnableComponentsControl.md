# DaSiteMgrEnableComponentsControl

- ea: `0x18002c8fc`
- end: `0x18002cb14`
- name: `DaSiteMgrEnableComponentsControl`
- size: `536`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004319c`
- `0x180070f3c`

## callees

- `0x18002c8fc`
- `0x18002cb1c`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cacf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cacf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c9ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c9ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ca64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ca8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002caa2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002cab9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ca8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002caa2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002cab9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c97f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c97f`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18002c9f0`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18002c9f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c93f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c93f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cae2`

## string_xrefs

- `0x18002c959`: `System\CurrentControlSet\Services\iphlpsvc\DaMultisite`

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
0x18002c8fc  mov     [rsp-8+arg_0], rbx
0x18002c901  push    rbp
0x18002c902  push    rsi
0x18002c903  push    rdi
0x18002c904  push    r14
0x18002c906  push    r15
0x18002c908  lea     rbp, [rsp-37h]
0x18002c90d  sub     rsp, 0C0h
0x18002c914  mov     rax, cs:__security_cookie
0x18002c91b  xor     rax, rsp
0x18002c91e  mov     [rbp+57h+var_30], rax
0x18002c922  mov     edi, ecx
0x18002c924  mov     [rbp+57h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002c92c  xor     r15d, r15d
0x18002c92f  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18002c936  mov     ebx, r15d
0x18002c939  mov     r14d, r8d
0x18002c93c  mov     rsi, rdx
0x18002c93f  call    cs:__imp_EnterCriticalSection
0x18002c946  nop     dword ptr [rax+rax+00h]
0x18002c94b  mov     [rsp+0E0h+lpdwDisposition], r15; lpdwDisposition
0x18002c950  lea     rax, [rbp+57h+hKey]
0x18002c954  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002c959  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\ip"...
0x18002c960  mov     [rsp+0E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002c965  xor     r9d, r9d; lpClass
0x18002c968  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x18002c970  xor     r8d, r8d; Reserved
0x18002c973  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c97a  mov     [rsp+0E0h+dwOptions], r15d; dwOptions
0x18002c97f  call    cs:__imp_RegCreateKeyExW
0x18002c986  nop     dword ptr [rax+rax+00h]
0x18002c98b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c98f  lea     rax, [rcx-1]
0x18002c993  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c997  ja      loc_18002CADB
0x18002c99d  xor     r8d, r8d; Reserved
0x18002c9a0  lea     rdx, aSitemanageract; "SiteManagerActive"
0x18002c9a7  test    edi, edi
0x18002c9a9  jz      loc_18002CA72
0x18002c9af  lea     edi, [r15+4]
0x18002c9b3  mov     dword ptr [rbp+57h+Data], 1
0x18002c9ba  lea     rax, [rbp+57h+Data]
0x18002c9be  mov     [rsp+0E0h+samDesired], edi; cbData
0x18002c9c2  mov     r9d, edi; dwType
0x18002c9c5  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002c9ca  call    cs:__imp_RegSetValueExW
0x18002c9d1  nop     dword ptr [rax+rax+00h]
0x18002c9d6  xor     edx, edx; Val
0x18002c9d8  lea     r8d, [r15+4Eh]; Size
0x18002c9dc  lea     rcx, [rbp+57h+var_80]; void *
0x18002c9e0  call    memset_0
0x18002c9e5  lea     r8d, [r15+27h]
0x18002c9e9  mov     rcx, rsi
0x18002c9ec  lea     rdx, [rbp+57h+var_80]
0x18002c9f0  call    cs:__imp_ConvertGuidToStringW
0x18002c9f7  nop     dword ptr [rax+rax+00h]
0x18002c9fc  lea     rcx, [rbp+57h+var_80]
0x18002ca00  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ca04  inc     rax
0x18002ca07  cmp     [rcx+rax*2], r15w
0x18002ca0c  jnz     short loc_18002CA04
0x18002ca0e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca12  lea     eax, ds:2[rax*2]
0x18002ca19  mov     [rsp+0E0h+samDesired], eax; cbData
0x18002ca1d  lea     rdx, aSelectedsite; "SelectedSite"
0x18002ca24  lea     rax, [rbp+57h+var_80]
0x18002ca28  mov     r9d, 1; dwType
0x18002ca2e  xor     r8d, r8d; Reserved
0x18002ca31  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002ca36  call    cs:__imp_RegSetValueExW
0x18002ca3d  nop     dword ptr [rax+rax+00h]
0x18002ca42  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca46  lea     rax, [rbp+57h+Data]
0x18002ca4a  mov     [rsp+0E0h+samDesired], edi; cbData
0x18002ca4e  lea     rdx, aSelectionmetho; "SelectionMethod"
0x18002ca55  mov     r9d, edi; dwType
0x18002ca58  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x18002ca5d  xor     r8d, r8d; Reserved
0x18002ca60  mov     dword ptr [rbp+57h+Data], r14d
0x18002ca64  call    cs:__imp_RegSetValueExW
0x18002ca6b  nop     dword ptr [rax+rax+00h]
0x18002ca70  jmp     short loc_18002CAC5
0x18002ca72  call    GetInteger2
0x18002ca77  test    eax, eax
0x18002ca79  jz      short loc_18002CA97
0x18002ca7b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca7f  lea     rdx, aSitemanageract; "SiteManagerActive"
0x18002ca86  mov     ebx, 1
0x18002ca8b  call    cs:__imp_RegDeleteValueW
0x18002ca92  nop     dword ptr [rax+rax+00h]
0x18002ca97  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ca9b  lea     rdx, aSelectedsite; "SelectedSite"
0x18002caa2  call    cs:__imp_RegDeleteValueW
0x18002caa9  nop     dword ptr [rax+rax+00h]
0x18002caae  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cab2  lea     rdx, aSelectionmetho; "SelectionMethod"
0x18002cab9  call    cs:__imp_RegDeleteValueW
0x18002cac0  nop     dword ptr [rax+rax+00h]
0x18002cac5  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cac9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cacd  jz      short loc_18002CADB
0x18002cacf  call    cs:__imp_RegCloseKey
0x18002cad6  nop     dword ptr [rax+rax+00h]
0x18002cadb  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18002cae2  call    cs:__imp_LeaveCriticalSection
0x18002cae9  nop     dword ptr [rax+rax+00h]
0x18002caee  mov     eax, ebx
0x18002caf0  mov     rcx, [rbp+57h+var_30]
0x18002caf4  xor     rcx, rsp; StackCookie
0x18002caf7  call    __security_check_cookie
0x18002cafc  mov     rbx, [rsp+0E0h+arg_0]
0x18002cb04  add     rsp, 0C0h
0x18002cb0b  pop     r15
0x18002cb0d  pop     r14
0x18002cb0f  pop     rdi
0x18002cb10  pop     rsi
0x18002cb11  pop     rbp
0x18002cb12  retn
```
