# lrGetSetMaxEndPoints

- ea: `0x18009dc30`
- end: `0x18009dcf4`
- name: `lrGetSetMaxEndPoints`
- size: `196`
- prototype: `__int64 __fastcall(BYTE *lpData, BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c940`

## callees

- `0x18009dc30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dc69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dc69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009dc99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009dcc9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009dc99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009dcc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dcda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dcda`

## string_xrefs

- `0x18009dc8a`: `LimitSimultaneousIncomingCalls`
- `0x18009dc4e`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
__int64 __fastcall lrGetSetMaxEndPoints(BYTE *lpData, BYTE *a2)
{
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Rasman\\Parameters",
          0,
          0x20007u,
          &hKey) )
  {
    if ( !RegSetValueExW(hKey, L"LimitSimultaneousIncomingCalls", 0, 4u, a2, 4u) )
      RegSetValueExW(hKey, L"LimitSimultaneousOutgoingCalls", 0, 4u, lpData, 4u);
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x18009dc30  mov     r11, rsp
0x18009dc33  mov     [r11+8], rbx
0x18009dc37  push    rdi
0x18009dc38  sub     rsp, 30h
0x18009dc3c  mov     rdi, rdx
0x18009dc3f  mov     qword ptr [r11+20h], 0
0x18009dc47  mov     rbx, rcx
0x18009dc4a  lea     rax, [r11+20h]
0x18009dc4e  lea     rdx, aSystemCurrentc_31; "System\\CurrentControlSet\\Services\\Ra"...
0x18009dc55  mov     [r11-18h], rax
0x18009dc59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009dc60  mov     r9d, 20007h; samDesired
0x18009dc66  xor     r8d, r8d; ulOptions
0x18009dc69  call    cs:__imp_RegOpenKeyExW
0x18009dc70  nop     dword ptr [rax+rax+00h]
0x18009dc75  test    eax, eax
0x18009dc77  jnz     short loc_18009DCE6
0x18009dc79  mov     rcx, [rsp+38h+hKey]; hKey
0x18009dc7e  lea     r9d, [rax+4]; dwType
0x18009dc82  mov     [rsp+38h+cbData], 4; cbData
0x18009dc8a  lea     rdx, aLimitsimultane; "LimitSimultaneousIncomingCalls"
0x18009dc91  xor     r8d, r8d; Reserved
0x18009dc94  mov     [rsp+38h+lpData], rdi; lpData
0x18009dc99  call    cs:__imp_RegSetValueExW
0x18009dca0  nop     dword ptr [rax+rax+00h]
0x18009dca5  test    eax, eax
0x18009dca7  jnz     short loc_18009DCD5
0x18009dca9  mov     rcx, [rsp+38h+hKey]; hKey
0x18009dcae  lea     r9d, [rax+4]; dwType
0x18009dcb2  mov     [rsp+38h+cbData], 4; cbData
0x18009dcba  lea     rdx, aLimitsimultane_0; "LimitSimultaneousOutgoingCalls"
0x18009dcc1  xor     r8d, r8d; Reserved
0x18009dcc4  mov     [rsp+38h+lpData], rbx; lpData
0x18009dcc9  call    cs:__imp_RegSetValueExW
0x18009dcd0  nop     dword ptr [rax+rax+00h]
0x18009dcd5  mov     rcx, [rsp+38h+hKey]; hKey
0x18009dcda  call    cs:__imp_RegCloseKey
0x18009dce1  nop     dword ptr [rax+rax+00h]
0x18009dce6  mov     rbx, [rsp+38h+arg_0]
0x18009dceb  xor     eax, eax
0x18009dced  add     rsp, 30h
0x18009dcf1  pop     rdi
0x18009dcf2  retn
```
