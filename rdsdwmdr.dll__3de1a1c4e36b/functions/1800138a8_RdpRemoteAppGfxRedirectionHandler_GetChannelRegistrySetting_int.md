# RdpRemoteAppGfxRedirectionHandler::GetChannelRegistrySetting(int *)

- ea: `0x1800138a8`
- end: `0x180013954`
- name: `?GetChannelRegistrySetting@RdpRemoteAppGfxRedirectionHandler@@SAJPEAH@Z`
- size: `172`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180012238`
- `0x1800141d0`

## callees

- `0x1800138a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013925`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013925`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013941`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013941`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800138e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800138e3`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::GetChannelRegistrySetting(int *a1)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v2 = -2147023728;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"RemoteAppGfxRedirectionEnabled", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v2 = 0;
      *a1 = Data != 0;
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800138a8  mov     r11, rsp
0x1800138ab  mov     [r11+8], rbx
0x1800138af  push    rdi
0x1800138b0  sub     rsp, 40h
0x1800138b4  mov     rdi, rcx
0x1800138b7  mov     qword ptr [r11-18h], 0
0x1800138bf  lea     rax, [r11-18h]
0x1800138c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800138ca  mov     r9d, 20019h; samDesired
0x1800138d0  mov     [r11-28h], rax
0x1800138d4  xor     r8d, r8d; ulOptions
0x1800138d7  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800138de  mov     ebx, 80070490h
0x1800138e3  call    cs:__imp_RegOpenKeyExW
0x1800138e9  test    eax, eax
0x1800138eb  jnz     short loc_180013947
0x1800138ed  mov     rcx, [rsp+48h+hKey]; hKey
0x1800138f2  lea     r9, [rsp+48h+Type]; lpType
0x1800138f7  mov     [rsp+48h+Data], eax
0x1800138fb  lea     rdx, aRemoteappgfxre; "RemoteAppGfxRedirectionEnabled"
0x180013902  mov     [rsp+48h+Type], eax
0x180013906  xor     r8d, r8d; lpReserved
0x180013909  lea     rax, [rsp+48h+cbData]
0x18001390e  mov     [rsp+48h+cbData], 4
0x180013916  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001391b  lea     rax, [rsp+48h+Data]
0x180013920  mov     [rsp+48h+lpData], rax; lpData
0x180013925  call    cs:__imp_RegQueryValueExW
0x18001392b  test    eax, eax
0x18001392d  jnz     short loc_18001393C
0x18001392f  xor     ecx, ecx
0x180013931  xor     ebx, ebx
0x180013933  cmp     [rsp+48h+Data], ecx
0x180013937  setnz   cl
0x18001393a  mov     [rdi], ecx
0x18001393c  mov     rcx, [rsp+48h+hKey]; hKey
0x180013941  call    cs:__imp_RegCloseKey
0x180013947  mov     eax, ebx
0x180013949  mov     rbx, [rsp+48h+arg_0]
0x18001394e  add     rsp, 40h
0x180013952  pop     rdi
0x180013953  retn
```
