# RdpDisplayControlHandler::IsDisplayControlChannelDisabled(void)

- ea: `0x14000eec8`
- end: `0x14000ef63`
- name: `?IsDisplayControlChannelDisabled@RdpDisplayControlHandler@@AEAAHXZ`
- size: `155`
- prototype: `__int64 __fastcall(RdpDisplayControlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ea80`

## callees

- `0x14000eec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ef55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ef55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000eefd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000eefd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ef3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ef3f`

## pseudocode

```c
__int64 __fastcall RdpDisplayControlHandler::IsDisplayControlChannelDisabled(RdpDisplayControlHandler *this)
{
  unsigned int v1; // ebx
  RdpDisplayControlHandler *Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = this;
  hKey = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(Data) = 0;
    cbData = 4;
    Type = 0;
    if ( !RegQueryValueExW(hKey, L"DisplayControlEnabled", 0, &Type, (LPBYTE)&Data, &cbData) )
      LOBYTE(v1) = (_DWORD)Data == 0;
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x14000eec8  mov     r11, rsp
0x14000eecb  mov     [r11+8], rcx
0x14000eecf  push    rbx
0x14000eed0  sub     rsp, 30h
0x14000eed4  lea     rax, [r11+20h]
0x14000eed8  mov     qword ptr [r11+20h], 0
0x14000eee0  mov     r9d, 20019h; samDesired
0x14000eee6  mov     [r11-18h], rax
0x14000eeea  xor     r8d, r8d; ulOptions
0x14000eeed  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x14000eef4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000eefb  xor     ebx, ebx
0x14000eefd  call    cs:__imp_RegOpenKeyExW
0x14000ef03  test    eax, eax
0x14000ef05  jnz     short loc_14000EF5B
0x14000ef07  mov     rcx, [rsp+38h+hKey]; hKey
0x14000ef0c  lea     rax, [rsp+38h+cbData]
0x14000ef11  mov     [rsp+38h+lpcbData], rax; lpcbData
0x14000ef16  lea     r9, [rsp+38h+Type]; lpType
0x14000ef1b  lea     rax, [rsp+38h+Data]
0x14000ef20  mov     dword ptr [rsp+38h+Data], ebx
0x14000ef24  xor     r8d, r8d; lpReserved
0x14000ef27  mov     [rsp+38h+lpData], rax; lpData
0x14000ef2c  lea     rdx, ValueName; "DisplayControlEnabled"
0x14000ef33  mov     [rsp+38h+cbData], 4
0x14000ef3b  mov     [rsp+38h+Type], ebx
0x14000ef3f  call    cs:__imp_RegQueryValueExW
0x14000ef45  test    eax, eax
0x14000ef47  jnz     short loc_14000EF50
0x14000ef49  cmp     dword ptr [rsp+38h+Data], ebx
0x14000ef4d  setz    bl
0x14000ef50  mov     rcx, [rsp+38h+hKey]; hKey
0x14000ef55  call    cs:__imp_RegCloseKey
0x14000ef5b  mov     eax, ebx
0x14000ef5d  add     rsp, 30h
0x14000ef61  pop     rbx
0x14000ef62  retn
```
