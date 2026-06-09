# RemoveLogPolicy

- ea: `0x18000cf80`
- end: `0x18000cfe4`
- name: `RemoveLogPolicy`
- size: `100`
- prototype: `BOOL __stdcall(HANDLE hLog, CLFS_MGMT_POLICY_TYPE ePolicyType)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000cf80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfd0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000cfbd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000cfbd`

## pseudocode

```c
BOOL __stdcall RemoveLogPolicy(HANDLE hLog, CLFS_MGMT_POLICY_TYPE ePolicyType)
{
  DWORD v3; // [rsp+50h] [rbp+8h] BYREF
  CLFS_MGMT_POLICY_TYPE v4; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  if ( (char *)hLog - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    SetLastError(6u);
    return 0;
  }
  else
  {
    v4 = ePolicyType;
    return DeviceIoControl(hLog, 0x8007B014, &v4, 4u, 0, 0, &v3, 0);
  }
}

```

## disassembly

```asm
0x18000cf80  mov     r11, rsp
0x18000cf83  sub     rsp, 48h
0x18000cf87  xor     r8d, r8d
0x18000cf8a  lea     rax, [rcx-1]
0x18000cf8e  mov     [r11+8], r8d
0x18000cf92  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cf96  ja      short loc_18000CFCB
0x18000cf98  mov     [r11-10h], r8
0x18000cf9c  lea     rax, [r11+8]
0x18000cfa0  mov     [r11-18h], rax
0x18000cfa4  lea     r9d, [r8+4]; nInBufferSize
0x18000cfa8  mov     [r11-20h], r8d
0x18000cfac  mov     [r11-28h], r8
0x18000cfb0  lea     r8, [r11+18h]; lpInBuffer
0x18000cfb4  mov     [rsp+48h+arg_10], edx
0x18000cfb8  mov     edx, 8007B014h; dwIoControlCode
0x18000cfbd  call    cs:__imp_DeviceIoControl
0x18000cfc4  nop     dword ptr [rax+rax+00h]
0x18000cfc9  jmp     short loc_18000CFDE
0x18000cfcb  mov     ecx, 6; dwErrCode
0x18000cfd0  call    cs:__imp_SetLastError
0x18000cfd7  nop     dword ptr [rax+rax+00h]
0x18000cfdc  xor     eax, eax
0x18000cfde  add     rsp, 48h
0x18000cfe2  retn
```
