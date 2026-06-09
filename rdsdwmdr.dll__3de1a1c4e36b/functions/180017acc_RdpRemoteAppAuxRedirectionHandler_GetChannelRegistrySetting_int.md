# RdpRemoteAppAuxRedirectionHandler::GetChannelRegistrySetting(int *)

- ea: `0x180017acc`
- end: `0x180017b78`
- name: `?GetChannelRegistrySetting@RdpRemoteAppAuxRedirectionHandler@@SAJPEAH@Z`
- size: `172`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180017c98`

## callees

- `0x180017acc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017b49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017b49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b07`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppAuxRedirectionHandler::GetChannelRegistrySetting(int *a1)
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
    if ( !RegQueryValueExW(hKey, L"RemoteAppAuxRedirectionEnabled", 0, &Type, (LPBYTE)&Data, &cbData) )
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
0x180017acc  mov     r11, rsp
0x180017acf  mov     [r11+8], rbx
0x180017ad3  push    rdi
0x180017ad4  sub     rsp, 40h
0x180017ad8  mov     rdi, rcx
0x180017adb  mov     qword ptr [r11-18h], 0
0x180017ae3  lea     rax, [r11-18h]
0x180017ae7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017aee  mov     r9d, 20019h; samDesired
0x180017af4  mov     [r11-28h], rax
0x180017af8  xor     r8d, r8d; ulOptions
0x180017afb  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180017b02  mov     ebx, 80070490h
0x180017b07  call    cs:__imp_RegOpenKeyExW
0x180017b0d  test    eax, eax
0x180017b0f  jnz     short loc_180017B6B
0x180017b11  mov     rcx, [rsp+48h+hKey]; hKey
0x180017b16  lea     r9, [rsp+48h+Type]; lpType
0x180017b1b  mov     [rsp+48h+Data], eax
0x180017b1f  lea     rdx, aRemoteappauxre; "RemoteAppAuxRedirectionEnabled"
0x180017b26  mov     [rsp+48h+Type], eax
0x180017b2a  xor     r8d, r8d; lpReserved
0x180017b2d  lea     rax, [rsp+48h+cbData]
0x180017b32  mov     [rsp+48h+cbData], 4
0x180017b3a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180017b3f  lea     rax, [rsp+48h+Data]
0x180017b44  mov     [rsp+48h+lpData], rax; lpData
0x180017b49  call    cs:__imp_RegQueryValueExW
0x180017b4f  test    eax, eax
0x180017b51  jnz     short loc_180017B60
0x180017b53  xor     ecx, ecx
0x180017b55  xor     ebx, ebx
0x180017b57  cmp     [rsp+48h+Data], ecx
0x180017b5b  setnz   cl
0x180017b5e  mov     [rdi], ecx
0x180017b60  mov     rcx, [rsp+48h+hKey]; hKey
0x180017b65  call    cs:__imp_RegCloseKey
0x180017b6b  mov     eax, ebx
0x180017b6d  mov     rbx, [rsp+48h+arg_0]
0x180017b72  add     rsp, 40h
0x180017b76  pop     rdi
0x180017b77  retn
```
