# GetCurrentControlSetKey

- ea: `0x180007684`
- end: `0x1800077d5`
- name: `GetCurrentControlSetKey`
- size: `337`
- prototype: `__int64 __fastcall(HKEY hKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007a58`

## callees

- `0x180007684`
- `0x1800080b0`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007797`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007797`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007745`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800077ab`

## pseudocode

```c
__int64 __fastcall GetCurrentControlSetKey(HKEY hKey, PHKEY phkResult)
{
  unsigned int v4; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = RegOpenKeyExW(hKey, L"CurrentControlSet", 0, 0xF003Fu, phkResult);
  if ( v4 )
  {
    hKeya = 0;
    v4 = RegOpenKeyExW(hKey, L"Select", 0, 0xF003Fu, &hKeya);
    if ( !v4 )
    {
      *(_DWORD *)Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKeya, L"Default", 0, &Type, Data, &cbData)
        && Type == 4
        && cbData == 4
        && *(_DWORD *)Data < 0x3E8u )
      {
        StringCchPrintfW(pszDest, 0x104u, L"ControlSet%03d");
        v4 = RegOpenKeyExW(hKey, pszDest, 0, 0xF003Fu, phkResult);
      }
      else
      {
        v4 = 1012;
      }
      RegCloseKey(hKeya);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180007684  mov     [rsp-8+arg_10], rbx
0x180007689  push    rbp
0x18000768a  push    rsi
0x18000768b  push    rdi
0x18000768c  lea     rbp, [rsp-170h]
0x180007694  sub     rsp, 270h
0x18000769b  mov     rax, cs:__security_cookie
0x1800076a2  xor     rax, rsp
0x1800076a5  mov     [rbp+180h+var_20], rax
0x1800076ac  mov     rsi, rdx
0x1800076af  mov     [rsp+280h+phkResult], rdx; phkResult
0x1800076b4  lea     rdx, aCurrentcontrol; "CurrentControlSet"
0x1800076bb  mov     r9d, 0F003Fh; samDesired
0x1800076c1  xor     r8d, r8d; ulOptions
0x1800076c4  mov     rdi, rcx
0x1800076c7  call    cs:__imp_RegOpenKeyExW
0x1800076cd  mov     ebx, eax
0x1800076cf  test    eax, eax
0x1800076d1  jz      loc_1800077B1
0x1800076d7  lea     rax, [rsp+280h+hKey]
0x1800076dc  mov     [rsp+280h+hKey], 0
0x1800076e5  mov     r9d, 0F003Fh; samDesired
0x1800076eb  mov     [rsp+280h+phkResult], rax; phkResult
0x1800076f0  xor     r8d, r8d; ulOptions
0x1800076f3  lea     rdx, aSelect; "Select"
0x1800076fa  mov     rcx, rdi; hKey
0x1800076fd  call    cs:__imp_RegOpenKeyExW
0x180007703  mov     ebx, eax
0x180007705  test    eax, eax
0x180007707  jnz     loc_1800077B1
0x18000770d  mov     rcx, [rsp+280h+hKey]; hKey
0x180007712  lea     r9, [rsp+280h+Type]; lpType
0x180007717  mov     dword ptr [rsp+280h+Data], eax
0x18000771b  lea     rdx, ValueName; "Default"
0x180007722  mov     [rsp+280h+Type], eax
0x180007726  xor     r8d, r8d; lpReserved
0x180007729  lea     rax, [rsp+280h+cbData]
0x18000772e  mov     [rsp+280h+cbData], 4
0x180007736  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000773b  lea     rax, [rsp+280h+Data]
0x180007740  mov     [rsp+280h+phkResult], rax; lpData
0x180007745  call    cs:__imp_RegQueryValueExW
0x18000774b  test    eax, eax
0x18000774d  jnz     short loc_1800077A1
0x18000774f  cmp     [rsp+280h+Type], 4
0x180007754  jnz     short loc_1800077A1
0x180007756  cmp     [rsp+280h+cbData], 4
0x18000775b  jnz     short loc_1800077A1
0x18000775d  mov     r9d, dword ptr [rsp+280h+Data]
0x180007762  cmp     r9d, 3E8h
0x180007769  jnb     short loc_1800077A1
0x18000776b  lea     r8, aControlset03d; "ControlSet%03d"
0x180007772  mov     edx, 104h; cchDest
0x180007777  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000777c  call    StringCchPrintfW
0x180007781  mov     r9d, 0F003Fh; samDesired
0x180007787  mov     [rsp+280h+phkResult], rsi; phkResult
0x18000778c  xor     r8d, r8d; ulOptions
0x18000778f  lea     rdx, [rsp+280h+pszDest]; lpSubKey
0x180007794  mov     rcx, rdi; hKey
0x180007797  call    cs:__imp_RegOpenKeyExW
0x18000779d  mov     ebx, eax
0x18000779f  jmp     short loc_1800077A6
0x1800077a1  mov     ebx, 3F4h
0x1800077a6  mov     rcx, [rsp+280h+hKey]; hKey
0x1800077ab  call    cs:__imp_RegCloseKey
0x1800077b1  mov     eax, ebx
0x1800077b3  mov     rcx, [rbp+180h+var_20]
0x1800077ba  xor     rcx, rsp; StackCookie
0x1800077bd  call    __security_check_cookie
0x1800077c2  mov     rbx, [rsp+280h+arg_10]
0x1800077ca  add     rsp, 270h
0x1800077d1  pop     rdi
0x1800077d2  pop     rsi
0x1800077d3  pop     rbp
0x1800077d4  retn
```
