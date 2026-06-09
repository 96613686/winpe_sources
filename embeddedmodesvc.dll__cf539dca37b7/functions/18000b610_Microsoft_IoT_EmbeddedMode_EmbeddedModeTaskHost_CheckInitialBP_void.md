# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::CheckInitialBP(void)

- ea: `0x18000b610`
- end: `0x18000b66d`
- name: `?CheckInitialBP@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@MEAAXXZ`
- size: `93`
- prototype: `void __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b610`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b65a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b65a`

## string_xrefs

- `0x18000b63e`: `Software\Microsoft\Windows NT\CurrentVersion\Winlogon\IoTShellExtension`

## pseudocode

```c
void __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::CheckInitialBP(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this)
{
  int v1; // [rsp+58h] [rbp+10h] BYREF
  DWORD v2; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\IoTShellExtension",
    L"debug",
    0x20000018u,
    0,
    &v1,
    &v2);
  if ( v1 )
    __debugbreak();
}

```

## disassembly

```asm
0x18000b610  mov     r11, rsp
0x18000b613  sub     rsp, 48h
0x18000b617  lea     rax, [r11+18h]
0x18000b61b  mov     [rsp+48h+arg_8], 0
0x18000b623  mov     [r11-18h], rax
0x18000b627  lea     r8, Value; "debug"
0x18000b62e  lea     rax, [r11+10h]
0x18000b632  mov     [rsp+48h+arg_10], 4
0x18000b63a  mov     [r11-20h], rax
0x18000b63e  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000b645  mov     r9d, 20000018h; dwFlags
0x18000b64b  mov     qword ptr [r11-28h], 0
0x18000b653  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b65a  call    cs:__imp_RegGetValueW
0x18000b660  cmp     [rsp+48h+arg_8], 0
0x18000b665  jz      short loc_18000B668
0x18000b667  int     3; Trap to Debugger
0x18000b668  add     rsp, 48h
0x18000b66c  retn
```
