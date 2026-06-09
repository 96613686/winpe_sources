# RadiusProxy::getMaxRetryCount(void)

- ea: `0x18001e998`
- end: `0x18001eab2`
- name: `?getMaxRetryCount@RadiusProxy@@IEAAXXZ`
- size: `282`
- prototype: `void __fastcall(RadiusProxy *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001d908`

## callees

- `0x180009540`
- `0x18001d31c`
- `0x18001e998`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001ea82`
- `ADVAPI32!RegQueryValueExW` at `0x18001ea82`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e9d2`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e9d2`
- `ADVAPI32!RegCloseKey` at `0x18001eaa0`
- `ADVAPI32!RegCloseKey` at `0x18001eaa0`

## string_xrefs

- `0x18001ea12`: `RadiusProxy::ReadMaxRetryCount RegOpenKeyEx(%S) Failed: 0x%x\n`
- `0x18001e9c1`: `System\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
void __fastcall RadiusProxy::getMaxRetryCount(RadiusProxy *this)
{
  LSTATUS v1; // eax
  char v2; // bl
  RadiusProxy *Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  hKey = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
         0,
         0x20019u,
         &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("RadiusProxy::ReadMaxRetryCount RegOpenKeyEx(%S) Failed: 0x%x\n");
      WPP_SF_sSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_71998f247ae0370d2143b01685e48c0c_Traceguids,
        (unsigned int)"NPSRAD",
        (__int64)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
        v2);
    }
  }
  else
  {
    LODWORD(Data) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxProxyRetry", 0, 0, (LPBYTE)&Data, &cbData) )
      RadiusProxy::maxRetryCount = (unsigned int)Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001e998  mov     r11, rsp
0x18001e99b  mov     [r11+20h], rbx
0x18001e99f  mov     [r11+8], rcx
0x18001e9a3  push    rdi
0x18001e9a4  sub     rsp, 30h
0x18001e9a8  mov     qword ptr [r11+18h], 0
0x18001e9b0  lea     rax, [r11+18h]
0x18001e9b4  mov     [r11-18h], rax
0x18001e9b8  mov     r9d, 20019h; samDesired
0x18001e9be  xor     r8d, r8d; ulOptions
0x18001e9c1  lea     rdi, ?pwszRegKeyPath@RadiusProxy@@1QBGB; "System\\CurrentControlSet\\Services\\Re"...
0x18001e9c8  mov     rdx, rdi; lpSubKey
0x18001e9cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e9d2  call    cs:__imp_RegOpenKeyExW
0x18001e9d8  mov     ebx, eax
0x18001e9da  test    eax, eax
0x18001e9dc  jz      short loc_18001EA4C
0x18001e9de  lea     rax, WPP_GLOBAL_Control
0x18001e9e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9ec  cmp     rcx, rax
0x18001e9ef  jz      loc_18001EA96
0x18001e9f5  cmp     byte ptr [rcx+19h], 2
0x18001e9f9  jb      loc_18001EA96
0x18001e9ff  test    dword ptr [rcx+1Ch], 100h
0x18001ea06  jz      loc_18001EA96
0x18001ea0c  mov     r8d, ebx
0x18001ea0f  mov     rdx, rdi
0x18001ea12  lea     rcx, aRadiusproxyRea; "RadiusProxy::ReadMaxRetryCount RegOpenK"...
0x18001ea19  call    WppDbgPrint
0x18001ea1e  mov     edx, 0Ah
0x18001ea23  mov     dword ptr [rsp+38h+lpcbData], ebx
0x18001ea27  mov     [rsp+38h+lpData], rdi
0x18001ea2c  lea     r9, aNpsrad; "NPSRAD"
0x18001ea33  lea     r8, WPP_71998f247ae0370d2143b01685e48c0c_Traceguids
0x18001ea3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea41  mov     rcx, [rcx+10h]
0x18001ea45  call    WPP_SF_sSD
0x18001ea4a  jmp     short loc_18001EA96
0x18001ea4c  mov     dword ptr [rsp+38h+Data], 0
0x18001ea54  mov     [rsp+38h+cbData], 4
0x18001ea5c  lea     rax, [rsp+38h+cbData]
0x18001ea61  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001ea66  lea     rax, [rsp+38h+Data]
0x18001ea6b  mov     [rsp+38h+lpData], rax; lpData
0x18001ea70  xor     r9d, r9d; lpType
0x18001ea73  xor     r8d, r8d; lpReserved
0x18001ea76  lea     rdx, ?pwszMaxProxyRetryValueName@RadiusProxy@@1QBGB; "MaxProxyRetry"
0x18001ea7d  mov     rcx, [rsp+38h+hKey]; hKey
0x18001ea82  call    cs:__imp_RegQueryValueExW
0x18001ea88  test    eax, eax
0x18001ea8a  jnz     short loc_18001EA96
0x18001ea8c  mov     eax, dword ptr [rsp+38h+Data]
0x18001ea90  mov     cs:?maxRetryCount@RadiusProxy@@1KA, eax; ulong RadiusProxy::maxRetryCount
0x18001ea96  mov     rcx, [rsp+38h+hKey]; hKey
0x18001ea9b  test    rcx, rcx
0x18001ea9e  jz      short loc_18001EAA7
0x18001eaa0  call    cs:__imp_RegCloseKey
0x18001eaa6  nop
0x18001eaa7  mov     rbx, [rsp+38h+arg_18]
0x18001eaac  add     rsp, 30h
0x18001eab0  pop     rdi
0x18001eab1  retn
```
