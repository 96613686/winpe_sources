# TelemetryProvider::UseOneSettingsPpe(void)

- ea: `0x140004210`
- end: `0x1400042b7`
- name: `?UseOneSettingsPpe@TelemetryProvider@@CA_NXZ`
- size: `167`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003cd8`

## callees

- `0x140004210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000425a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400042a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000425a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400042a4`

## string_xrefs

- `0x14000423e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Wosc\Client\Persistent\ClientState\COMPATPROVIDEREOS`
- `0x14000428d`: `OSDATA\SOFTWARE\Microsoft\Windows\CurrentVersion\Wosc\Client\Persistent\ClientState\COMPATPROVIDEREOS`

## pseudocode

```c
bool TelemetryProvider::UseOneSettingsPpe(void)
{
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF

  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Wosc\\Client\\Persistent\\ClientState\\COMPATPROVIDEREOS",
         L"Environment",
         0x10u,
         0,
         &pvData,
         &pcbData) )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"OSDATA\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Wosc\\Client\\Persistent\\ClientState\\COMPATPROVIDEREOS",
      L"Environment",
      0x10u,
      0,
      &pvData,
      &pcbData);
  }
  return pvData == 1;
}

```

## disassembly

```asm
0x140004210  mov     r11, rsp
0x140004213  sub     rsp, 48h
0x140004217  lea     rax, [r11+8]
0x14000421b  mov     [rsp+48h+arg_8], 0
0x140004223  mov     [r11-18h], rax
0x140004227  lea     r8, aEnvironment; "Environment"
0x14000422e  lea     rax, [r11+10h]
0x140004232  mov     [rsp+48h+arg_0], 4
0x14000423a  mov     [r11-20h], rax
0x14000423e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140004245  mov     r9d, 10h; dwFlags
0x14000424b  mov     qword ptr [r11-28h], 0
0x140004253  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000425a  call    cs:__imp_RegGetValueW
0x140004260  test    eax, eax
0x140004262  jz      short loc_1400042AA
0x140004264  lea     rax, [rsp+48h+arg_0]
0x140004269  mov     [rsp+48h+arg_0], 4
0x140004271  mov     [rsp+48h+pcbData], rax; pcbData
0x140004276  lea     r8, aEnvironment; "Environment"
0x14000427d  lea     rax, [rsp+48h+arg_8]
0x140004282  mov     r9d, 10h; dwFlags
0x140004288  mov     [rsp+48h+pvData], rax; pvData
0x14000428d  lea     rdx, aOsdataSoftware_0; "OSDATA\\SOFTWARE\\Microsoft\\Windows\\C"...
0x140004294  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14000429b  mov     [rsp+48h+pdwType], 0; pdwType
0x1400042a4  call    cs:__imp_RegGetValueW
0x1400042aa  cmp     [rsp+48h+arg_8], 1
0x1400042af  setz    al
0x1400042b2  add     rsp, 48h
0x1400042b6  retn
```
