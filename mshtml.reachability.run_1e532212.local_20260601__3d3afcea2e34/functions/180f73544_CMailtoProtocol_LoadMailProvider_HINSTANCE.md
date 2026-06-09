# CMailtoProtocol::LoadMailProvider(HINSTANCE__ * *)

- ea: `0x180f73544`
- end: `0x180f737d3`
- name: `?LoadMailProvider@CMailtoProtocol@@QEAAJPEAPEAUHINSTANCE__@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(CMailtoProtocol *__hidden this, HINSTANCE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180f73920`

## callees

- `0x18040ac58`
- `0x180745a1c`
- `0x180f73544`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180f7379b`
- `KERNEL32!LoadLibraryExW` at `0x180f7379b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180f73775`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180f73775`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f735ee`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f73679`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f73743`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f735ee`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f73679`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f73743`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f735b9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f7363f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f73704`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f735b9`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f7363f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f73704`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f73601`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f7368c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f73756`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f73601`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f7368c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f73756`

## string_xrefs

- `0x180f73727`: `DLLPath`

## pseudocode

```c
__int64 __fastcall CMailtoProtocol::LoadMailProvider(CMailtoProtocol *this, HINSTANCE *a2)
{
  int v3; // edi
  LSTATUS v4; // ebx
  __int64 v5; // rsi
  LSTATUS v6; // ebx
  LSTATUS Value; // ebx
  DWORD cbData[2]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Data[264]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+268h] [rbp+160h] BYREF

  v3 = 0;
  phkResult = 0;
  cbData[0] = 260;
  hKey = 0;
  *a2 = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Clients\\Mail", 0, 1u, &hKey) )
  {
    if ( (v4 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, cbData), RegCloseKey(hKey), !v4) && (v5 = 0, cbData[0] > 2)
      || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Clients\\Mail", 0, 1u, &hKey)
      && (cbData[0] = 260, v6 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, cbData), RegCloseKey(hKey), v5 = 1, !v6) )
    {
      v3 = StringCchCopyW(SubKey, 0x104u, L"Software\\Clients\\Mail\\");
      if ( v3 >= 0 )
      {
        v3 = StringCchCatW(SubKey, 0x104u, Data);
        if ( v3 >= 0 && !RegOpenKeyExW((HKEY)(v5 - 0x7FFFFFFF), SubKey, 0, 1u, &phkResult) )
        {
          cbData[0] = 260;
          Value = RegQueryValueExW(phkResult, L"DLLPath", 0, 0, (LPBYTE)Data, cbData);
          RegCloseKey(phkResult);
          if ( !Value )
          {
            cbData[0] = ExpandEnvironmentStringsW(Data, SubKey, 0x104u);
            if ( cbData[0] - 1 <= 0x103 )
              *a2 = LoadLibraryExW(SubKey, 0, 8u);
          }
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180f73544  mov     rax, rsp
0x180f73547  mov     [rax+18h], rbx
0x180f7354b  mov     [rax+10h], rdx
0x180f7354f  mov     [rax+8], rcx
0x180f73553  push    rbp
0x180f73554  push    rsi
0x180f73555  push    rdi
0x180f73556  push    r12
0x180f73558  push    r14
0x180f7355a  lea     rbp, [rax-3A8h]
0x180f73561  sub     rsp, 480h
0x180f73568  mov     rax, cs:__security_cookie
0x180f7356f  xor     rax, rsp
0x180f73572  mov     [rbp+3A0h+var_30], rax
0x180f73579  mov     r14, [rbp+3A0h+arg_8]
0x180f73580  lea     rax, [rsp+4A0h+hKey]
0x180f73585  xor     edi, edi
0x180f73587  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180f7358c  mov     r12d, 104h
0x180f73592  mov     [rsp+4A0h+var_460], rdi
0x180f73597  xor     r8d, r8d; ulOptions
0x180f7359a  mov     [rsp+4A0h+cbData], r12d
0x180f7359f  lea     rdx, aSoftwareClient_0; "Software\\Clients\\Mail"
0x180f735a6  mov     [rsp+4A0h+hKey], rdi
0x180f735ab  lea     r9d, [rdi+1]; samDesired
0x180f735af  mov     [r14], rdi
0x180f735b2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180f735b9  call    cs:__imp_RegOpenKeyExW
0x180f735c0  nop     dword ptr [rax+rax+00h]
0x180f735c5  test    eax, eax
0x180f735c7  jnz     loc_180F737AA
0x180f735cd  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f735d2  lea     rax, [rsp+4A0h+cbData]
0x180f735d7  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180f735dc  xor     r9d, r9d; lpType
0x180f735df  lea     rax, [rsp+4A0h+Data]
0x180f735e4  xor     r8d, r8d; lpReserved
0x180f735e7  xor     edx, edx; lpValueName
0x180f735e9  mov     [rsp+4A0h+phkResult], rax; lpData
0x180f735ee  call    cs:__imp_RegQueryValueExW
0x180f735f5  nop     dword ptr [rax+rax+00h]
0x180f735fa  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f735ff  mov     ebx, eax
0x180f73601  call    cs:__imp_RegCloseKey
0x180f73608  nop     dword ptr [rax+rax+00h]
0x180f7360d  test    ebx, ebx
0x180f7360f  jnz     short loc_180F7361E
0x180f73611  xor     esi, esi
0x180f73613  cmp     [rsp+4A0h+cbData], 2
0x180f73618  ja      loc_180F736A5
0x180f7361e  lea     rax, [rsp+4A0h+hKey]
0x180f73623  mov     r9d, 1; samDesired
0x180f73629  xor     r8d, r8d; ulOptions
0x180f7362c  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180f73631  lea     rdx, aSoftwareClient_0; "Software\\Clients\\Mail"
0x180f73638  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180f7363f  call    cs:__imp_RegOpenKeyExW
0x180f73646  nop     dword ptr [rax+rax+00h]
0x180f7364b  test    eax, eax
0x180f7364d  jnz     loc_180F737AA
0x180f73653  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f73658  lea     rax, [rsp+4A0h+cbData]
0x180f7365d  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180f73662  xor     r9d, r9d; lpType
0x180f73665  lea     rax, [rsp+4A0h+Data]
0x180f7366a  mov     [rsp+4A0h+cbData], r12d
0x180f7366f  xor     r8d, r8d; lpReserved
0x180f73672  mov     [rsp+4A0h+phkResult], rax; lpData
0x180f73677  xor     edx, edx; lpValueName
0x180f73679  call    cs:__imp_RegQueryValueExW
0x180f73680  nop     dword ptr [rax+rax+00h]
0x180f73685  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f7368a  mov     ebx, eax
0x180f7368c  call    cs:__imp_RegCloseKey
0x180f73693  nop     dword ptr [rax+rax+00h]
0x180f73698  mov     esi, 1
0x180f7369d  test    ebx, ebx
0x180f7369f  jnz     loc_180F737AA
0x180f736a5  lea     r8, aSoftwareClient; "Software\\Clients\\Mail\\"
0x180f736ac  mov     rdx, r12; unsigned __int64
0x180f736af  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x180f736b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180f736bb  mov     edi, eax
0x180f736bd  test    eax, eax
0x180f736bf  js      loc_180F737AA
0x180f736c5  lea     r8, [rsp+4A0h+Data]; unsigned __int16 *
0x180f736ca  mov     rdx, r12; unsigned __int64
0x180f736cd  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x180f736d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180f736d9  mov     edi, eax
0x180f736db  test    eax, eax
0x180f736dd  js      loc_180F737AA
0x180f736e3  lea     rax, [rsp+4A0h+var_460]
0x180f736e8  mov     r9d, 1; samDesired
0x180f736ee  lea     rcx, [rsi-7FFFFFFFh]; hKey
0x180f736f5  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180f736fa  xor     r8d, r8d; ulOptions
0x180f736fd  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x180f73704  call    cs:__imp_RegOpenKeyExW
0x180f7370b  nop     dword ptr [rax+rax+00h]
0x180f73710  test    eax, eax
0x180f73712  jnz     loc_180F737AA
0x180f73718  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180f7371d  lea     rax, [rsp+4A0h+cbData]
0x180f73722  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180f73727  lea     rdx, aDllpath; "DLLPath"
0x180f7372e  lea     rax, [rsp+4A0h+Data]
0x180f73733  mov     [rsp+4A0h+cbData], r12d
0x180f73738  xor     r9d, r9d; lpType
0x180f7373b  mov     [rsp+4A0h+phkResult], rax; lpData
0x180f73740  xor     r8d, r8d; lpReserved
0x180f73743  call    cs:__imp_RegQueryValueExW
0x180f7374a  nop     dword ptr [rax+rax+00h]
0x180f7374f  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180f73754  mov     ebx, eax
0x180f73756  call    cs:__imp_RegCloseKey
0x180f7375d  nop     dword ptr [rax+rax+00h]
0x180f73762  test    ebx, ebx
0x180f73764  jnz     short loc_180F737AA
0x180f73766  mov     r8d, r12d; nSize
0x180f73769  lea     rdx, [rbp+3A0h+SubKey]; lpDst
0x180f73770  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x180f73775  call    cs:__imp_ExpandEnvironmentStringsW
0x180f7377c  nop     dword ptr [rax+rax+00h]
0x180f73781  mov     [rsp+4A0h+cbData], eax
0x180f73785  dec     eax
0x180f73787  cmp     eax, 103h
0x180f7378c  ja      short loc_180F737AA
0x180f7378e  xor     edx, edx; hFile
0x180f73790  lea     r8d, [rbx+8]; dwFlags
0x180f73794  lea     rcx, [rbp+3A0h+SubKey]; lpLibFileName
0x180f7379b  call    cs:__imp_LoadLibraryExW
0x180f737a2  nop     dword ptr [rax+rax+00h]
0x180f737a7  mov     [r14], rax
0x180f737aa  mov     eax, edi
0x180f737ac  mov     rcx, [rbp+3A0h+var_30]
0x180f737b3  xor     rcx, rsp; StackCookie
0x180f737b6  call    __security_check_cookie
0x180f737bb  mov     rbx, [rsp+4A0h+arg_10]
0x180f737c3  add     rsp, 480h
0x180f737ca  pop     r14
0x180f737cc  pop     r12
0x180f737ce  pop     rdi
0x180f737cf  pop     rsi
0x180f737d0  pop     rbp
0x180f737d1  retn
```
