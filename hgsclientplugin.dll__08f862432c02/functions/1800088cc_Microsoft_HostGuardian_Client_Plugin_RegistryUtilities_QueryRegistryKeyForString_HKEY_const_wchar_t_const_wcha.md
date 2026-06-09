# Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(HKEY__ * const,wchar_t const *,wchar_t const *)

- ea: `0x1800088cc`
- end: `0x180008a88`
- name: `?QueryRegistryKeyForString@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAUHKEY__@@PEB_W1@Z`
- size: `444`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006060`
- `0x1800065c0`

## callees

- `0x180001520`
- `0x1800018f0`
- `0x180001970`
- `0x180001f9e`
- `0x180005f34`
- `0x180006260`
- `0x18000642c`
- `0x180006b00`
- `0x1800088cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008951`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008951`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000899c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a00`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000899c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a5a`

## string_xrefs

- `0x180008961`: `Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4)
{
  unsigned int v6; // eax
  unsigned int ValueW; // eax
  DWORD v8; // ebx
  void *pvData; // rsi
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  DWORD pcbData; // [rsp+40h] [rbp-9h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-1h] BYREF
  int v15; // [rsp+50h] [rbp+7h]
  DWORD pdwType; // [rsp+54h] [rbp+Bh] BYREF
  __int64 v17; // [rsp+58h] [rbp+Fh]
  void *v18; // [rsp+60h] [rbp+17h]
  _BYTE v19[32]; // [rsp+68h] [rbp+1Fh] BYREF

  v17 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v15 = 1;
  pcbData = 0;
  hkey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\HgsClient", 0, 0x20019u, &hkey);
  if ( v6 )
  {
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
      (wchar_t *)L"Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X",
      L"SOFTWARE\\Microsoft\\HgsClient",
      v6);
  }
  else
  {
    ValueW = RegGetValueW(hkey, 0, a4, 6u, 0, 0, &pcbData);
    if ( ValueW || !pcbData )
    {
      Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
        (wchar_t *)L"Failed to call RegGetValue or bufferSize is 0. subKey: %ws. valueName: %ws. Error code:0X%08X",
        L"SOFTWARE\\Microsoft\\HgsClient",
        a4,
        ValueW);
    }
    else
    {
      pdwType = 0;
      v8 = pcbData;
      pvData = operator new[](pcbData);
      memset_0(pvData, 0, v8);
      v18 = pvData;
      v15 = 3;
      if ( !RegGetValueW(hkey, 0, a4, 6u, &pdwType, pvData, &pcbData) && pdwType == 1 )
      {
        v11 = std::wstring::wstring(v19);
        std::wstring::operator=(a1, v11);
        std::wstring::~wstring(v19);
      }
      operator delete(pvData, v10);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return a1;
}

```

## disassembly

```asm
0x1800088cc  mov     [rsp-8+arg_8], rbx
0x1800088d1  mov     [rsp-8+arg_10], rsi
0x1800088d6  push    rbp
0x1800088d7  push    rdi
0x1800088d8  push    r14
0x1800088da  lea     rbp, [rsp-47h]
0x1800088df  sub     rsp, 90h
0x1800088e6  mov     rax, cs:__security_cookie
0x1800088ed  xor     rax, rsp
0x1800088f0  mov     [rbp+57h+var_18], rax
0x1800088f4  mov     r14, r9
0x1800088f7  mov     rdi, rcx
0x1800088fa  mov     [rbp+57h+var_48], rcx
0x1800088fe  mov     [rbp+57h+var_50], 1
0x180008905  xorps   xmm0, xmm0
0x180008908  movups  xmmword ptr [rcx], xmm0
0x18000890b  mov     qword ptr [rcx+10h], 0
0x180008913  mov     qword ptr [rcx+18h], 7
0x18000891b  xor     eax, eax
0x18000891d  mov     [rcx], ax
0x180008920  mov     [rbp+57h+var_50], 1
0x180008927  mov     [rbp+57h+var_60], eax
0x18000892a  mov     [rbp+57h+hkey], rax
0x18000892e  lea     rax, [rbp+57h+hkey]
0x180008932  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180008937  mov     r9d, 20019h; samDesired
0x18000893d  xor     r8d, r8d; ulOptions
0x180008940  lea     rbx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x180008947  mov     rdx, rbx; lpSubKey
0x18000894a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008951  call    cs:__imp_RegOpenKeyExW
0x180008957  test    eax, eax
0x180008959  jz      short loc_180008972
0x18000895b  mov     r8d, eax
0x18000895e  mov     rdx, rbx; wchar_t *
0x180008961  lea     rcx, aFailedToCallRe; "Failed to call RegOpenKeyEx. subKey: %w"...
0x180008968  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x18000896d  jmp     loc_180008A51
0x180008972  lea     rax, [rbp+57h+var_60]
0x180008976  mov     [rsp+0A0h+pcbData], rax; pcbData
0x18000897b  mov     [rsp+0A0h+pvData], 0; pvData
0x180008984  mov     [rsp+0A0h+phkResult], 0; pdwType
0x18000898d  mov     r9d, 6; dwFlags
0x180008993  mov     r8, r14; lpValue
0x180008996  xor     edx, edx; lpSubKey
0x180008998  mov     rcx, [rbp+57h+hkey]; hkey
0x18000899c  call    cs:__imp_RegGetValueW
0x1800089a2  test    eax, eax
0x1800089a4  jnz     loc_180008A3B
0x1800089aa  mov     ecx, [rbp+57h+var_60]; unsigned __int64
0x1800089ad  test    ecx, ecx
0x1800089af  jz      loc_180008A3B
0x1800089b5  mov     [rbp+57h+pdwType], eax
0x1800089b8  mov     ebx, ecx
0x1800089ba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800089bf  mov     rsi, rax
0x1800089c2  mov     r8d, ebx; Size
0x1800089c5  xor     edx, edx; Val
0x1800089c7  mov     rcx, rax; void *
0x1800089ca  call    memset_0
0x1800089cf  mov     [rbp+57h+var_40], rsi
0x1800089d3  mov     [rbp+57h+var_50], 3
0x1800089da  lea     rax, [rbp+57h+var_60]
0x1800089de  mov     [rsp+0A0h+pcbData], rax; pcbData
0x1800089e3  mov     [rsp+0A0h+pvData], rsi; pvData
0x1800089e8  lea     rax, [rbp+57h+pdwType]
0x1800089ec  mov     [rsp+0A0h+phkResult], rax; pdwType
0x1800089f1  mov     r9d, 6; dwFlags
0x1800089f7  mov     r8, r14; lpValue
0x1800089fa  xor     edx, edx; lpSubKey
0x1800089fc  mov     rcx, [rbp+57h+hkey]; hkey
0x180008a00  call    cs:__imp_RegGetValueW
0x180008a06  test    eax, eax
0x180008a08  jnz     short loc_180008A31
0x180008a0a  cmp     [rbp+57h+pdwType], 1
0x180008a0e  jnz     short loc_180008A31
0x180008a10  mov     rdx, rsi
0x180008a13  lea     rcx, [rbp+57h+var_38]
0x180008a17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180008a1c  mov     rdx, rax
0x180008a1f  mov     rcx, rdi
0x180008a22  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008a27  lea     rcx, [rbp+57h+var_38]
0x180008a2b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a30  nop
0x180008a31  mov     rcx, rsi; void *
0x180008a34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008a39  jmp     short loc_180008A51
0x180008a3b  mov     r9d, eax
0x180008a3e  mov     r8, r14
0x180008a41  mov     rdx, rbx; wchar_t *
0x180008a44  lea     rcx, aFailedToCallRe_3; "Failed to call RegGetValue or bufferSiz"...
0x180008a4b  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x180008a50  nop
0x180008a51  mov     rcx, [rbp+57h+hkey]; hKey
0x180008a55  test    rcx, rcx
0x180008a58  jz      short loc_180008A61
0x180008a5a  call    cs:__imp_RegCloseKey
0x180008a60  nop
0x180008a61  mov     rax, rdi
0x180008a64  mov     rcx, [rbp+57h+var_18]
0x180008a68  xor     rcx, rsp; StackCookie
0x180008a6b  call    __security_check_cookie
0x180008a70  lea     r11, [rsp+0A0h+var_10]
0x180008a78  mov     rbx, [r11+28h]
0x180008a7c  mov     rsi, [r11+30h]
0x180008a80  mov     rsp, r11
0x180008a83  pop     r14
0x180008a85  pop     rdi
0x180008a86  pop     rbp
0x180008a87  retn
```
