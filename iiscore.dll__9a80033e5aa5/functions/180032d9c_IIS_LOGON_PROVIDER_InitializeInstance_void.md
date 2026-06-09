# IIS_LOGON_PROVIDER::InitializeInstance(void)

- ea: `0x180032d9c`
- end: `0x180032e66`
- name: `?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180013690`

## callees

- `0x1800323cc`
- `0x180032d9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032e37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032de9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032de9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032e17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032e17`

## string_xrefs

- `0x180032de2`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::InitializeInstance(wchar_t *Destination)
{
  LSTATUS v2; // eax
  __int64 result; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = RegQueryValueExW(hKey, L"LastPriorityUPNLogon", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data != 0;
      *((_DWORD *)Destination + 641) = v2;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  result = IIS_LOGON_PROVIDER::GetDefaultDomainName(Destination);
  if ( (int)result >= 0 )
    *((_DWORD *)Destination + 642) = 1;
  return result;
}

```

## disassembly

```asm
0x180032d9c  mov     [rsp-8+arg_0], rbx
0x180032da1  push    rbp
0x180032da2  mov     rbp, rsp
0x180032da5  sub     rsp, 40h
0x180032da9  mov     rbx, rcx
0x180032dac  mov     [rbp+hKey], 0
0x180032db4  lea     rax, [rbp+hKey]
0x180032db8  mov     [rbp+Data], 0
0x180032dbf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032dc6  mov     [rsp+40h+phkResult], rax; phkResult
0x180032dcb  mov     r9d, 20019h; samDesired
0x180032dd1  mov     [rbp+Type], 0
0x180032dd8  xor     r8d, r8d; ulOptions
0x180032ddb  mov     [rbp+cbData], 4
0x180032de2  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\in"...
0x180032de9  call    cs:__imp_RegOpenKeyExW
0x180032def  test    eax, eax
0x180032df1  jnz     short loc_180032E45
0x180032df3  mov     rcx, [rbp+hKey]; hKey
0x180032df7  lea     rax, [rbp+cbData]
0x180032dfb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180032e00  lea     r9, [rbp+Type]; lpType
0x180032e04  lea     rax, [rbp+Data]
0x180032e08  xor     r8d, r8d; lpReserved
0x180032e0b  lea     rdx, aLastpriorityup; "LastPriorityUPNLogon"
0x180032e12  mov     [rsp+40h+phkResult], rax; lpData
0x180032e17  call    cs:__imp_RegQueryValueExW
0x180032e1d  test    eax, eax
0x180032e1f  jnz     short loc_180032E33
0x180032e21  cmp     [rbp+Type], 4
0x180032e25  jnz     short loc_180032E33
0x180032e27  cmp     [rbp+Data], eax
0x180032e2a  setnz   al
0x180032e2d  mov     [rbx+0A04h], eax
0x180032e33  mov     rcx, [rbp+hKey]; hKey
0x180032e37  call    cs:__imp_RegCloseKey
0x180032e3d  mov     [rbp+hKey], 0
0x180032e45  mov     rcx, rbx; Destination
0x180032e48  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x180032e4d  test    eax, eax
0x180032e4f  js      short loc_180032E5B
0x180032e51  mov     dword ptr [rbx+0A08h], 1
0x180032e5b  mov     rbx, [rsp+40h+arg_0]
0x180032e60  add     rsp, 40h
0x180032e64  pop     rbp
0x180032e65  retn
```
