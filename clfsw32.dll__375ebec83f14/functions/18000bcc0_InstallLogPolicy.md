# InstallLogPolicy

- ea: `0x18000bcc0`
- end: `0x18000bd2c`
- name: `InstallLogPolicy`
- size: `108`
- prototype: `BOOL __stdcall(HANDLE hLog, PCLFS_MGMT_POLICY pPolicy)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bcc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd18`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bd05`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bd05`

## pseudocode

```c
BOOL __stdcall InstallLogPolicy(HANDLE hLog, PCLFS_MGMT_POLICY pPolicy)
{
  DWORD v2; // ecx
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  if ( (char *)hLog - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v2 = 6;
  }
  else
  {
    if ( pPolicy )
      return DeviceIoControl(hLog, 0x8007B010, pPolicy, pPolicy->LengthInBytes, 0, 0, &BytesReturned, 0);
    v2 = 87;
  }
  SetLastError(v2);
  return 0;
}

```

## disassembly

```asm
0x18000bcc0  sub     rsp, 48h
0x18000bcc4  xor     r8d, r8d
0x18000bcc7  lea     rax, [rcx-1]
0x18000bccb  mov     [rsp+48h+BytesReturned], r8d
0x18000bcd0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bcd4  ja      short loc_18000BD13
0x18000bcd6  test    rdx, rdx
0x18000bcd9  jnz     short loc_18000BCE0
0x18000bcdb  lea     ecx, [rdx+57h]; hDevice
0x18000bcde  jmp     short loc_18000BD18
0x18000bce0  mov     r9d, [rdx+4]; nInBufferSize
0x18000bce4  lea     rax, [rsp+48h+BytesReturned]
0x18000bce9  mov     [rsp+48h+lpOverlapped], r8; lpOverlapped
0x18000bcee  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000bcf3  mov     [rsp+48h+nOutBufferSize], r8d; nOutBufferSize
0x18000bcf8  mov     [rsp+48h+lpOutBuffer], r8; lpOutBuffer
0x18000bcfd  mov     r8, rdx; lpInBuffer
0x18000bd00  mov     edx, 8007B010h; dwIoControlCode
0x18000bd05  call    cs:__imp_DeviceIoControl
0x18000bd0c  nop     dword ptr [rax+rax+00h]
0x18000bd11  jmp     short loc_18000BD26
0x18000bd13  mov     ecx, 6; dwErrCode
0x18000bd18  call    cs:__imp_SetLastError
0x18000bd1f  nop     dword ptr [rax+rax+00h]
0x18000bd24  xor     eax, eax
0x18000bd26  add     rsp, 48h
0x18000bd2a  retn
```
