# DhcpSaveInterfaceConfiguration

- ea: `0x1800368d0`
- end: `0x180036b14`
- name: `DhcpSaveInterfaceConfiguration`
- size: `580`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180021128`
- `0x180024488`

## callees

- `0x180005178`
- `0x1800057f0`
- `0x180008084`
- `0x180013b60`
- `0x1800368d0`
- `0x18004d1e0`
- `0x18004d200`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ae5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036990`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036990`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036ab1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036ab1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036a2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036a2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180036940`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180036940`

## string_xrefs

- `0x180036a6d`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces\Tcpip_?\DhcpNameServerList`

## pseudocode

```c
__int64 __fastcall DhcpSaveInterfaceConfiguration(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  BYTE *lpData[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+20h] BYREF
  DWORD dwType; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  dwDisposition = 0;
  lpData[0] = 0;
  dwType = 0;
  cbData = 0;
  if ( a1
    && *(_QWORD *)(a1 + 1888)
    && *(_DWORD *)(a1 + 120)
    && *(_DWORD *)(a1 + 792)
    && !*(_DWORD *)(a1 + 796)
    && GetTickCount64() / 0x3E8 <= *(_QWORD *)(a1 + 472) )
  {
    v2 = RegOpenKeyExW(*(HKEY *)(a1 + 728), *(LPCWSTR *)(a1 + 1888), 0, 0xFu, &hKey);
    if ( v2 )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_S(1028, 91, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, *(_QWORD *)(a1 + 1888));
      v2 = DhcpCacheScavanger(a1, 1);
      if ( v2 )
      {
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          v3 = 92;
LABEL_21:
          WPP_SF_(1028, v3, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
          goto LABEL_22;
        }
        goto LABEL_22;
      }
      v2 = RegCreateKeyExW(*(HKEY *)(a1 + 728), *(LPCWSTR *)(a1 + 1888), 0, 0, 0, 0xFu, 0, &hKey, &dwDisposition);
      if ( v2 )
        goto LABEL_22;
    }
    if ( !hKey )
      return v2;
    DhcpRegCopyInterfaceSettings(*(HKEY *)(a1 + 728), hKey);
    v2 = DhcpRegReadFromLocation(
           L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList",
           *(void **)(a1 + 56),
           lpData,
           &dwType,
           &cbData);
    if ( !v2 )
    {
      v2 = RegSetValueExW(hKey, L"DhcpNameServerList", 0, dwType, lpData[0], cbData);
      if ( !v2 || (xmmword_1800616A0 & 0x10) == 0 )
        goto LABEL_22;
      v3 = 94;
      goto LABEL_21;
    }
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      v3 = 93;
      goto LABEL_21;
    }
LABEL_22:
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( lpData[0] )
      DhcpPunycodeFree((LPVOID *)lpData);
    return v2;
  }
  return 87;
}

```

## disassembly

```asm
0x1800368d0  push    rbp
0x1800368d2  push    rbx
0x1800368d3  push    rdi
0x1800368d4  mov     rbp, rsp
0x1800368d7  sub     rsp, 60h
0x1800368db  mov     [rbp+hKey], 0
0x1800368e3  mov     rbx, rcx
0x1800368e6  mov     [rbp+dwDisposition], 0
0x1800368ed  mov     [rbp+lpData], 0
0x1800368f5  mov     [rbp+dwType], 0
0x1800368fc  mov     [rbp+cbData], 0
0x180036903  test    rcx, rcx
0x180036906  jz      loc_180036B07
0x18003690c  cmp     qword ptr [rcx+760h], 0
0x180036914  jz      loc_180036B07
0x18003691a  cmp     dword ptr [rcx+78h], 0
0x18003691e  jz      loc_180036B07
0x180036924  mov     eax, [rcx+318h]
0x18003692a  test    eax, eax
0x18003692c  jz      loc_180036B07
0x180036932  mov     eax, [rcx+31Ch]
0x180036938  test    eax, eax
0x18003693a  jnz     loc_180036B07
0x180036940  call    cs:__imp_GetTickCount64
0x180036946  mov     rcx, rax
0x180036949  mov     rax, 624DD2F1A9FBE77h
0x180036953  mul     rcx
0x180036956  sub     rcx, rdx
0x180036959  shr     rcx, 1
0x18003695c  add     rcx, rdx
0x18003695f  shr     rcx, 9
0x180036963  cmp     rcx, [rbx+1D8h]
0x18003696a  ja      loc_180036B07
0x180036970  mov     rdx, [rbx+760h]; lpSubKey
0x180036977  lea     rax, [rbp+hKey]
0x18003697b  mov     rcx, [rbx+2D8h]; hKey
0x180036982  mov     r9d, 0Fh; samDesired
0x180036988  xor     r8d, r8d; ulOptions
0x18003698b  mov     [rsp+60h+phkResult], rax; phkResult
0x180036990  call    cs:__imp_RegOpenKeyExW
0x180036996  mov     edi, eax
0x180036998  test    eax, eax
0x18003699a  jz      loc_180036A3F
0x1800369a0  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800369a7  jz      short loc_1800369C6
0x1800369a9  mov     r9, [rbx+760h]
0x1800369b0  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800369b7  mov     edx, 5Bh ; '['
0x1800369bc  mov     ecx, 404h
0x1800369c1  call    WPP_SF_S
0x1800369c6  mov     edx, 1
0x1800369cb  mov     rcx, rbx
0x1800369ce  call    DhcpCacheScavanger
0x1800369d3  mov     edi, eax
0x1800369d5  test    eax, eax
0x1800369d7  jz      short loc_1800369F0
0x1800369d9  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800369e0  jz      loc_180036ADC
0x1800369e6  mov     edx, 5Ch ; '\'
0x1800369eb  jmp     loc_180036ACB
0x1800369f0  mov     rdx, [rbx+760h]; lpSubKey
0x1800369f7  lea     rax, [rbp+dwDisposition]
0x1800369fb  mov     rcx, [rbx+2D8h]; hKey
0x180036a02  xor     r9d, r9d; lpClass
0x180036a05  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180036a0a  xor     r8d, r8d; Reserved
0x180036a0d  lea     rax, [rbp+hKey]
0x180036a11  mov     [rsp+60h+var_28], rax; phkResult
0x180036a16  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036a1f  mov     [rsp+60h+samDesired], 0Fh; samDesired
0x180036a27  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180036a2f  call    cs:__imp_RegCreateKeyExW
0x180036a35  mov     edi, eax
0x180036a37  test    eax, eax
0x180036a39  jnz     loc_180036ADC
0x180036a3f  mov     rdx, [rbp+hKey]; HKEY
0x180036a43  test    rdx, rdx
0x180036a46  jz      loc_180036B03
0x180036a4c  mov     rcx, [rbx+2D8h]; hKey
0x180036a53  call    DhcpRegCopyInterfaceSettings
0x180036a58  mov     rdx, [rbx+38h]; void *
0x180036a5c  lea     rax, [rbp+cbData]
0x180036a60  lea     r9, [rbp+dwType]
0x180036a64  mov     [rsp+60h+phkResult], rax; LPDWORD
0x180036a69  lea     r8, [rbp+lpData]
0x180036a6d  lea     rcx, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\Ne"...
0x180036a74  call    DhcpRegReadFromLocation
0x180036a79  mov     edi, eax
0x180036a7b  test    eax, eax
0x180036a7d  jz      short loc_180036A8F
0x180036a7f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036a86  jz      short loc_180036ADC
0x180036a88  mov     edx, 5Dh ; ']'
0x180036a8d  jmp     short loc_180036ACB
0x180036a8f  mov     eax, [rbp+cbData]
0x180036a92  lea     rdx, aDhcpnameserver_0; "DhcpNameServerList"
0x180036a99  mov     r9d, [rbp+dwType]; dwType
0x180036a9d  xor     r8d, r8d; Reserved
0x180036aa0  mov     rcx, [rbp+hKey]; hKey
0x180036aa4  mov     [rsp+60h+samDesired], eax; cbData
0x180036aa8  mov     rax, [rbp+lpData]
0x180036aac  mov     [rsp+60h+phkResult], rax; lpData
0x180036ab1  call    cs:__imp_RegSetValueExW
0x180036ab7  mov     edi, eax
0x180036ab9  test    eax, eax
0x180036abb  jz      short loc_180036ADC
0x180036abd  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036ac4  jz      short loc_180036ADC
0x180036ac6  mov     edx, 5Eh ; '^'
0x180036acb  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180036ad2  mov     ecx, 404h
0x180036ad7  call    WPP_SF_
0x180036adc  mov     rcx, [rbp+hKey]; hKey
0x180036ae0  test    rcx, rcx
0x180036ae3  jz      short loc_180036AF3
0x180036ae5  call    cs:__imp_RegCloseKey
0x180036aeb  mov     [rbp+hKey], 0
0x180036af3  cmp     [rbp+lpData], 0
0x180036af8  jz      short loc_180036B03
0x180036afa  lea     rcx, [rbp+lpData]
0x180036afe  call    DhcpPunycodeFree
0x180036b03  mov     eax, edi
0x180036b05  jmp     short loc_180036B0C
0x180036b07  mov     eax, 57h ; 'W'
0x180036b0c  add     rsp, 60h
0x180036b10  pop     rdi
0x180036b11  pop     rbx
0x180036b12  pop     rbp
0x180036b13  retn
```
