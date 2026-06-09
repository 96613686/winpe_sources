# detail::ReadDelayReasonsForPid(HKEY__ *,ulong)

- ea: `0x1800651fc`
- end: `0x1800652e3`
- name: `?ReadDelayReasonsForPid@detail@@YA?AW4ExperienceRolloutDelayReasons@@PEAUHKEY__@@K@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800632a0`

## callees

- `0x18000bdf0`
- `0x180028b74`
- `0x18002a3d0`
- `0x1800651fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065289`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065289`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800652a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800652b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800652a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800652b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006524e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006524e`

## pseudocode

```c
__int64 __fastcall detail::ReadDelayReasonsForPid(HKEY a1)
{
  const WCHAR *v2; // rdx
  unsigned int v3; // ebx
  DWORD Type; // [rsp+30h] [rbp-40h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+48h] [rbp-28h] BYREF

  std::to_wstring(lpSubKey);
  v2 = (const WCHAR *)lpSubKey;
  hKey = 0;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v2 = lpSubKey[0];
  if ( RegOpenKeyExW(a1, v2, 0, 0x20019u, &hKey)
    || (*(_DWORD *)Data = 0, Type = 0, cbData = 4, RegQueryValueExW(hKey, L"DelayReasons", 0, &Type, Data, &cbData))
    || Type != 4 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    v3 = 0;
  }
  else
  {
    v3 = *(_DWORD *)Data;
    if ( hKey )
      RegCloseKey(hKey);
  }
  std::wstring::~wstring(lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x1800651fc  mov     [rsp-8+arg_8], rbx
0x180065201  push    rbp
0x180065202  mov     rbp, rsp
0x180065205  sub     rsp, 70h
0x180065209  mov     rax, cs:__security_cookie
0x180065210  xor     rax, rsp
0x180065213  mov     [rbp+var_8], rax
0x180065217  mov     rbx, rcx
0x18006521a  lea     rcx, [rbp+lpSubKey]
0x18006521e  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@K@Z; std::to_wstring(ulong)
0x180065223  cmp     [rbp+var_10], 7
0x180065228  lea     rax, [rbp+hKey]
0x18006522c  lea     rdx, [rbp+lpSubKey]
0x180065230  mov     [rbp+hKey], 0
0x180065238  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18006523d  mov     r9d, 20019h; samDesired
0x180065243  xor     r8d, r8d; ulOptions
0x180065246  mov     [rsp+70h+phkResult], rax; phkResult
0x18006524b  mov     rcx, rbx; hKey
0x18006524e  call    cs:__imp_RegOpenKeyExW
0x180065254  test    eax, eax
0x180065256  jnz     short loc_1800652AD
0x180065258  mov     rcx, [rbp+hKey]; hKey
0x18006525c  lea     r9, [rbp+Type]; lpType
0x180065260  mov     dword ptr [rbp+Data], eax
0x180065263  lea     rdx, aDelayreasons; "DelayReasons"
0x18006526a  mov     [rbp+Type], eax
0x18006526d  xor     r8d, r8d; lpReserved
0x180065270  lea     rax, [rbp+cbData]
0x180065274  mov     [rbp+cbData], 4
0x18006527b  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180065280  lea     rax, [rbp+Data]
0x180065284  mov     [rsp+70h+phkResult], rax; lpData
0x180065289  call    cs:__imp_RegQueryValueExW
0x18006528f  test    eax, eax
0x180065291  jnz     short loc_1800652AD
0x180065293  cmp     [rbp+Type], 4
0x180065297  jnz     short loc_1800652AD
0x180065299  mov     rcx, [rbp+hKey]; hKey
0x18006529d  mov     ebx, dword ptr [rbp+Data]
0x1800652a0  test    rcx, rcx
0x1800652a3  jz      short loc_1800652BE
0x1800652a5  call    cs:__imp_RegCloseKey
0x1800652ab  jmp     short loc_1800652BE
0x1800652ad  mov     rcx, [rbp+hKey]; hKey
0x1800652b1  test    rcx, rcx
0x1800652b4  jz      short loc_1800652BC
0x1800652b6  call    cs:__imp_RegCloseKey
0x1800652bc  xor     ebx, ebx
0x1800652be  lea     rcx, [rbp+lpSubKey]
0x1800652c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800652c7  mov     eax, ebx
0x1800652c9  mov     rcx, [rbp+var_8]
0x1800652cd  xor     rcx, rsp; StackCookie
0x1800652d0  call    __security_check_cookie
0x1800652d5  mov     rbx, [rsp+70h+arg_8]
0x1800652dd  add     rsp, 70h
0x1800652e1  pop     rbp
0x1800652e2  retn
```
