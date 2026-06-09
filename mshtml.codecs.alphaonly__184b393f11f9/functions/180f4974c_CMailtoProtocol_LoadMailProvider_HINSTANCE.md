# CMailtoProtocol::LoadMailProvider(HINSTANCE__ * *)

- ea: `0x180f4974c`
- end: `0x180f49990`
- name: `?LoadMailProvider@CMailtoProtocol@@QEAAJPEAPEAUHINSTANCE__@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(CMailtoProtocol *__hidden this, HINSTANCE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180f49ad0`

## callees

- `0x1802e5024`
- `0x18073d694`
- `0x180f4974c`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180f4995f`
- `KERNEL32!LoadLibraryExW` at `0x180f4995f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180f4993f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180f4993f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f497f0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f49865`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f49919`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f497f0`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f49865`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x180f49919`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f497c1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f49831`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f498e4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f497c1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f49831`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x180f498e4`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f497fd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f49872`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f49926`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f497fd`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f49872`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x180f49926`

## string_xrefs

- `0x180f498fd`: `DLLPath`

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
0x180f4974c  mov     rax, rsp
0x180f4974f  mov     [rax+18h], rbx
0x180f49753  mov     [rax+10h], rdx
0x180f49757  mov     [rax+8], rcx
0x180f4975b  push    rbp
0x180f4975c  push    rsi
0x180f4975d  push    rdi
0x180f4975e  push    r12
0x180f49760  push    r14
0x180f49762  lea     rbp, [rax-3A8h]
0x180f49769  sub     rsp, 480h
0x180f49770  mov     rax, cs:__security_cookie
0x180f49777  xor     rax, rsp
0x180f4977a  mov     [rbp+3A0h+var_30], rax
0x180f49781  mov     r14, [rbp+3A0h+arg_8]
0x180f49788  lea     rax, [rsp+4A0h+hKey]
0x180f4978d  xor     edi, edi
0x180f4978f  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180f49794  mov     r12d, 104h
0x180f4979a  mov     [rsp+4A0h+var_460], rdi
0x180f4979f  xor     r8d, r8d; ulOptions
0x180f497a2  mov     [rsp+4A0h+cbData], r12d
0x180f497a7  lea     rdx, aSoftwareClient_0; "Software\\Clients\\Mail"
0x180f497ae  mov     [rsp+4A0h+hKey], rdi
0x180f497b3  lea     r9d, [rdi+1]; samDesired
0x180f497b7  mov     [r14], rdi
0x180f497ba  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180f497c1  call    cs:__imp_RegOpenKeyExW
0x180f497c7  test    eax, eax
0x180f497c9  jnz     loc_180F49968
0x180f497cf  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f497d4  lea     rax, [rsp+4A0h+cbData]
0x180f497d9  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180f497de  xor     r9d, r9d; lpType
0x180f497e1  lea     rax, [rsp+4A0h+Data]
0x180f497e6  xor     r8d, r8d; lpReserved
0x180f497e9  xor     edx, edx; lpValueName
0x180f497eb  mov     [rsp+4A0h+phkResult], rax; lpData
0x180f497f0  call    cs:__imp_RegQueryValueExW
0x180f497f6  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f497fb  mov     ebx, eax
0x180f497fd  call    cs:__imp_RegCloseKey
0x180f49803  test    ebx, ebx
0x180f49805  jnz     short loc_180F49810
0x180f49807  xor     esi, esi
0x180f49809  cmp     [rsp+4A0h+cbData], 2
0x180f4980e  ja      short loc_180F49885
0x180f49810  lea     rax, [rsp+4A0h+hKey]
0x180f49815  mov     r9d, 1; samDesired
0x180f4981b  xor     r8d, r8d; ulOptions
0x180f4981e  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180f49823  lea     rdx, aSoftwareClient_0; "Software\\Clients\\Mail"
0x180f4982a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180f49831  call    cs:__imp_RegOpenKeyExW
0x180f49837  test    eax, eax
0x180f49839  jnz     loc_180F49968
0x180f4983f  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f49844  lea     rax, [rsp+4A0h+cbData]
0x180f49849  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180f4984e  xor     r9d, r9d; lpType
0x180f49851  lea     rax, [rsp+4A0h+Data]
0x180f49856  mov     [rsp+4A0h+cbData], r12d
0x180f4985b  xor     r8d, r8d; lpReserved
0x180f4985e  mov     [rsp+4A0h+phkResult], rax; lpData
0x180f49863  xor     edx, edx; lpValueName
0x180f49865  call    cs:__imp_RegQueryValueExW
0x180f4986b  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180f49870  mov     ebx, eax
0x180f49872  call    cs:__imp_RegCloseKey
0x180f49878  mov     esi, 1
0x180f4987d  test    ebx, ebx
0x180f4987f  jnz     loc_180F49968
0x180f49885  lea     r8, aSoftwareClient; "Software\\Clients\\Mail\\"
0x180f4988c  mov     rdx, r12; unsigned __int64
0x180f4988f  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x180f49896  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180f4989b  mov     edi, eax
0x180f4989d  test    eax, eax
0x180f4989f  js      loc_180F49968
0x180f498a5  lea     r8, [rsp+4A0h+Data]; unsigned __int16 *
0x180f498aa  mov     rdx, r12; unsigned __int64
0x180f498ad  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x180f498b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180f498b9  mov     edi, eax
0x180f498bb  test    eax, eax
0x180f498bd  js      loc_180F49968
0x180f498c3  lea     rax, [rsp+4A0h+var_460]
0x180f498c8  mov     r9d, 1; samDesired
0x180f498ce  lea     rcx, [rsi-7FFFFFFFh]; hKey
0x180f498d5  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180f498da  xor     r8d, r8d; ulOptions
0x180f498dd  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x180f498e4  call    cs:__imp_RegOpenKeyExW
0x180f498ea  test    eax, eax
0x180f498ec  jnz     short loc_180F49968
0x180f498ee  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180f498f3  lea     rax, [rsp+4A0h+cbData]
0x180f498f8  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180f498fd  lea     rdx, aDllpath; "DLLPath"
0x180f49904  lea     rax, [rsp+4A0h+Data]
0x180f49909  mov     [rsp+4A0h+cbData], r12d
0x180f4990e  xor     r9d, r9d; lpType
0x180f49911  mov     [rsp+4A0h+phkResult], rax; lpData
0x180f49916  xor     r8d, r8d; lpReserved
0x180f49919  call    cs:__imp_RegQueryValueExW
0x180f4991f  mov     rcx, [rsp+4A0h+var_460]; hKey
0x180f49924  mov     ebx, eax
0x180f49926  call    cs:__imp_RegCloseKey
0x180f4992c  test    ebx, ebx
0x180f4992e  jnz     short loc_180F49968
0x180f49930  mov     r8d, r12d; nSize
0x180f49933  lea     rdx, [rbp+3A0h+SubKey]; lpDst
0x180f4993a  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x180f4993f  call    cs:__imp_ExpandEnvironmentStringsW
0x180f49945  mov     [rsp+4A0h+cbData], eax
0x180f49949  dec     eax
0x180f4994b  cmp     eax, 103h
0x180f49950  ja      short loc_180F49968
0x180f49952  xor     edx, edx; hFile
0x180f49954  lea     r8d, [rbx+8]; dwFlags
0x180f49958  lea     rcx, [rbp+3A0h+SubKey]; lpLibFileName
0x180f4995f  call    cs:__imp_LoadLibraryExW
0x180f49965  mov     [r14], rax
0x180f49968  mov     eax, edi
0x180f4996a  mov     rcx, [rbp+3A0h+var_30]
0x180f49971  xor     rcx, rsp; StackCookie
0x180f49974  call    __security_check_cookie
0x180f49979  mov     rbx, [rsp+4A0h+arg_10]
0x180f49981  add     rsp, 480h
0x180f49988  pop     r14
0x180f4998a  pop     r12
0x180f4998c  pop     rdi
0x180f4998d  pop     rsi
0x180f4998e  pop     rbp
0x180f4998f  retn
```
