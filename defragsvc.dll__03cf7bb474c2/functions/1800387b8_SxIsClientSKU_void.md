# SxIsClientSKU(void)

- ea: `0x1800387b8`
- end: `0x1800388b2`
- name: `?SxIsClientSKU@@YAHXZ`
- size: `250`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029dbc`

## callees

- `0x1800387b8`
- `0x180046494`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003883d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003883d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038863`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003880f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003880f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038826`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038826`

## pseudocode

```c
_BOOL8 SxIsClientSKU(void)
{
  LSTATUS v0; // ebx
  DWORD LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-138h] BYREF
  char v5; // [rsp+15Ah] [rbp-1Eh]

  memset_0(&VersionInformation, 0, 0x11Cu);
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( !v0 )
    return 0;
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, LastError);
    }
    return 0;
  }
  return v5 == 1;
}

```

## disassembly

```asm
0x1800387b8  push    rbx
0x1800387ba  sub     rsp, 170h
0x1800387c1  mov     rax, cs:__security_cookie
0x1800387c8  xor     rax, rsp
0x1800387cb  mov     [rsp+178h+var_18], rax
0x1800387d3  xor     edx, edx; Val
0x1800387d5  lea     rcx, [rsp+178h+VersionInformation]; void *
0x1800387da  mov     r8d, 11Ch; Size
0x1800387e0  call    memset_0
0x1800387e5  lea     rax, [rsp+178h+hKey]
0x1800387ea  mov     [rsp+178h+hKey], 0
0x1800387f3  mov     r9d, 20019h; samDesired
0x1800387f9  mov     [rsp+178h+phkResult], rax; phkResult
0x1800387fe  xor     r8d, r8d; ulOptions
0x180038801  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180038808  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003880f  call    cs:__imp_RegOpenKeyExW
0x180038815  mov     rcx, [rsp+178h+hKey]; hKey
0x18003881a  mov     ebx, eax
0x18003881c  lea     rdx, [rcx-1]
0x180038820  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180038824  ja      short loc_18003882C
0x180038826  call    cs:__imp_RegCloseKey
0x18003882c  test    ebx, ebx
0x18003882e  jz      short loc_180038888
0x180038830  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x180038835  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18003883d  call    cs:__imp_GetVersionExW
0x180038843  test    eax, eax
0x180038845  jnz     short loc_1800388A3
0x180038847  mov     rax, cs:WPP_GLOBAL_Control
0x18003884e  lea     rcx, WPP_GLOBAL_Control
0x180038855  cmp     rax, rcx
0x180038858  jz      short loc_180038888
0x18003885a  test    dword ptr [rax+1Ch], 10000000h
0x180038861  jz      short loc_180038888
0x180038863  call    cs:__imp_GetLastError
0x180038869  mov     rcx, cs:WPP_GLOBAL_Control
0x180038870  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x180038877  mov     edx, 16h
0x18003887c  mov     r9d, eax
0x18003887f  mov     rcx, [rcx+10h]
0x180038883  call    WPP_SF_d
0x180038888  xor     eax, eax
0x18003888a  mov     rcx, [rsp+178h+var_18]
0x180038892  xor     rcx, rsp; StackCookie
0x180038895  call    __security_check_cookie
0x18003889a  add     rsp, 170h
0x1800388a1  pop     rbx
0x1800388a2  retn
0x1800388a3  xor     eax, eax
0x1800388a5  cmp     [rsp+178h+var_1E], 1
0x1800388ad  setz    al
0x1800388b0  jmp     short loc_18003888A
```
