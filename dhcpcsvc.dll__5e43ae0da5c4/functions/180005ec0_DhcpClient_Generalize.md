# DhcpClient_Generalize

- ea: `0x180005ec0`
- end: `0x180005ff7`
- name: `DhcpClient_Generalize`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002760`
- `0x180005ec0`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005ee8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005fc6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005ee8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180005fc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005f33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005f33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005f69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f92`

## string_xrefs

- `0x180005f25`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 DhcpClient_Generalize()
{
  LPWSTR CommandLineW; // rax
  unsigned int v1; // ebx
  unsigned int v2; // eax
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 217, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v1 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 218, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else
  {
    v1 = 0;
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
           0,
           0xF003Fu,
           &hKey);
    v3 = v2;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_d(1028, 219, WPP_e15037783097355a5233924022d92169_Traceguids, v2);
    if ( !v3 )
    {
      v4 = RegDeleteValueW(hKey, L"Dhcpv6DUID");
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
        WPP_SF_d(1028, 220, WPP_e15037783097355a5233924022d92169_Traceguids, v4);
    }
    RegCloseKey(hKey);
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v5 = (unsigned int)GetCommandLineW();
    WPP_SF_SD(1028, 221, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v5, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_8], rbx
0x180005ec5  mov     [rsp+arg_10], rsi
0x180005eca  push    rdi
0x180005ecb  sub     rsp, 30h
0x180005ecf  mov     [rsp+38h+hKey], 0
0x180005ed8  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005edf  lea     rsi, WPP_e15037783097355a5233924022d92169_Traceguids
0x180005ee6  jz      short loc_180005F03
0x180005ee8  call    cs:__imp_GetCommandLineW
0x180005eee  mov     edx, 0D9h
0x180005ef3  mov     ecx, 404h
0x180005ef8  mov     r9, rax
0x180005efb  mov     r8, rsi
0x180005efe  call    WPP_SF_S
0x180005f03  call    DhcpIsFSEGuestSystem
0x180005f08  test    eax, eax
0x180005f0a  jnz     loc_180005F9A
0x180005f10  lea     rax, [rsp+38h+hKey]
0x180005f15  xor     ebx, ebx
0x180005f17  mov     r9d, 0F003Fh; samDesired
0x180005f1d  mov     [rsp+38h+phkResult], rax; phkResult
0x180005f22  xor     r8d, r8d; ulOptions
0x180005f25  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x180005f2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005f33  call    cs:__imp_RegOpenKeyExW
0x180005f39  mov     edi, eax
0x180005f3b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005f42  jz      short loc_180005F59
0x180005f44  mov     edx, 0DBh
0x180005f49  mov     ecx, 404h
0x180005f4e  mov     r9d, eax
0x180005f51  mov     r8, rsi
0x180005f54  call    WPP_SF_d
0x180005f59  test    edi, edi
0x180005f5b  jnz     short loc_180005F8D
0x180005f5d  mov     rcx, [rsp+38h+hKey]; hKey
0x180005f62  lea     rdx, aDhcpv6duid; "Dhcpv6DUID"
0x180005f69  call    cs:__imp_RegDeleteValueW
0x180005f6f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005f76  jz      short loc_180005F8D
0x180005f78  mov     edx, 0DCh
0x180005f7d  mov     ecx, 404h
0x180005f82  mov     r9d, eax
0x180005f85  mov     r8, rsi
0x180005f88  call    WPP_SF_d
0x180005f8d  mov     rcx, [rsp+38h+hKey]; hKey
0x180005f92  call    cs:__imp_RegCloseKey
0x180005f98  jmp     short loc_180005FBD
0x180005f9a  mov     ebx, 32h ; '2'
0x180005f9f  test    byte ptr cs:xmmword_18001E1E0, 2
0x180005fa6  jz      short loc_180005FBD
0x180005fa8  mov     edx, 0DAh
0x180005fad  mov     ecx, 401h
0x180005fb2  mov     r9d, ebx
0x180005fb5  mov     r8, rsi
0x180005fb8  call    WPP_SF_d
0x180005fbd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180005fc4  jz      short loc_180005FE5
0x180005fc6  call    cs:__imp_GetCommandLineW
0x180005fcc  mov     edx, 0DDh
0x180005fd1  mov     dword ptr [rsp+38h+phkResult], ebx
0x180005fd5  mov     r9, rax
0x180005fd8  mov     ecx, 404h
0x180005fdd  mov     r8, rsi
0x180005fe0  call    WPP_SF_SD
0x180005fe5  mov     rsi, [rsp+38h+arg_10]
0x180005fea  mov     eax, ebx
0x180005fec  mov     rbx, [rsp+38h+arg_8]
0x180005ff1  add     rsp, 30h
0x180005ff5  pop     rdi
0x180005ff6  retn
```
