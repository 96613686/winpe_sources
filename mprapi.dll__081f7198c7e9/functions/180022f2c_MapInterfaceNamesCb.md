# MapInterfaceNamesCb

- ea: `0x180022f2c`
- end: `0x18002302c`
- name: `MapInterfaceNamesCb`
- size: `256`
- prototype: `__int64 __fastcall(HANDLE hMprConfig, HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017f30`

## callees

- `0x180022f2c`
- `0x180023130`
- `0x1800231a0`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023002`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023002`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022f95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022f95`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180022fd4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180022fd4`

## pseudocode

```c
__int64 __fastcall MapInterfaceNamesCb(HANDLE hMprConfig, HKEY hKey, int a3)
{
  DWORD FriendlyName; // eax
  int v7; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR pszBuffer[512]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Data[512]; // [rsp+440h] [rbp+340h] BYREF
  __int16 v13; // [rsp+840h] [rbp+740h]

  Type[0] = 0;
  cbData = 1024;
  if ( !RegQueryValueExW(hKey, L"InterfaceName", 0, Type, (LPBYTE)Data, &cbData) )
  {
    v13 = 0;
    if ( a3 )
      FriendlyName = MprConfigGetFriendlyName(hMprConfig, Data, pszBuffer, 0x400u);
    else
      FriendlyName = MprConfigGetGuidName(hMprConfig, Data, pszBuffer, 0x400u);
    if ( !FriendlyName )
    {
      v7 = lstrlenW(pszBuffer);
      RegSetValueExW(hKey, L"InterfaceName", 0, 1u, (const BYTE *)pszBuffer, 2 * v7 + 2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180022f2c  mov     [rsp-8+arg_10], rbx
0x180022f31  push    rbp
0x180022f32  push    rsi
0x180022f33  push    rdi
0x180022f34  lea     rbp, [rsp-760h]
0x180022f3c  sub     rsp, 860h
0x180022f43  mov     rax, cs:__security_cookie
0x180022f4a  xor     rax, rsp
0x180022f4d  mov     [rbp+770h+var_20], rax
0x180022f54  mov     rsi, rdx
0x180022f57  mov     [rsp+870h+Type], 0
0x180022f5f  lea     rax, [rsp+870h+cbData]
0x180022f64  mov     [rsp+870h+cbData], 400h
0x180022f6c  mov     [rsp+870h+lpcbData], rax; lpcbData
0x180022f71  lea     r9, [rsp+870h+Type]; lpType
0x180022f76  lea     rax, [rbp+770h+Data]
0x180022f7d  mov     edi, r8d
0x180022f80  mov     rbx, rcx
0x180022f83  mov     [rsp+870h+lpData], rax; lpData
0x180022f88  xor     r8d, r8d; lpReserved
0x180022f8b  lea     rdx, c_szInterfaceName; "InterfaceName"
0x180022f92  mov     rcx, rsi; hKey
0x180022f95  call    cs:__imp_RegQueryValueExW
0x180022f9b  test    eax, eax
0x180022f9d  jnz     short loc_180023008
0x180022f9f  mov     [rbp+770h+var_30], ax
0x180022fa6  mov     r9d, 400h; dwBufferSize
0x180022fac  lea     r8, [rsp+870h+pszBuffer]; pszBuffer
0x180022fb1  mov     rcx, rbx; hMprConfig
0x180022fb4  lea     rdx, [rbp+770h+Data]; pszFriendlyName
0x180022fbb  test    edi, edi
0x180022fbd  jz      short loc_180022FC6
0x180022fbf  call    MprConfigGetFriendlyName
0x180022fc4  jmp     short loc_180022FCB
0x180022fc6  call    MprConfigGetGuidName
0x180022fcb  test    eax, eax
0x180022fcd  jnz     short loc_180023008
0x180022fcf  lea     rcx, [rsp+870h+pszBuffer]; lpString
0x180022fd4  call    cs:__imp_lstrlenW
0x180022fda  mov     r9d, 1; dwType
0x180022fe0  lea     rdx, c_szInterfaceName; "InterfaceName"
0x180022fe7  xor     r8d, r8d; Reserved
0x180022fea  mov     rcx, rsi; hKey
0x180022fed  lea     eax, ds:2[rax*2]
0x180022ff4  mov     dword ptr [rsp+870h+lpcbData], eax; cbData
0x180022ff8  lea     rax, [rsp+870h+pszBuffer]
0x180022ffd  mov     [rsp+870h+lpData], rax; lpData
0x180023002  call    cs:__imp_RegSetValueExW
0x180023008  xor     eax, eax
0x18002300a  mov     rcx, [rbp+770h+var_20]
0x180023011  xor     rcx, rsp; StackCookie
0x180023014  call    __security_check_cookie
0x180023019  mov     rbx, [rsp+870h+arg_10]
0x180023021  add     rsp, 860h
0x180023028  pop     rdi
0x180023029  pop     rsi
0x18002302a  pop     rbp
0x18002302b  retn
```
