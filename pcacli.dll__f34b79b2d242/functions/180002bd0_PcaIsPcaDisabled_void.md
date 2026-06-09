# PcaIsPcaDisabled(void)

- ea: `0x180002bd0`
- end: `0x180002c94`
- name: `?PcaIsPcaDisabled@@YAHXZ`
- size: `196`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012c0`
- `0x180002210`
- `0x180007040`
- `0x1800082c0`

## callees

- `0x180002bd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002c18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002c62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002c18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002c62`

## string_xrefs

- `0x180002bfb`: `Software\Policies\Microsoft\Windows\AppCompat`
- `0x180002c49`: `Software\Policies\Microsoft\Windows\AppCompat`

## pseudocode

```c
__int64 PcaIsPcaDisabled(void)
{
  __int64 result; // rax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF

  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Policies\\Microsoft\\Windows\\AppCompat",
          L"DisablePca",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData == 1 )
  {
    return 1;
  }
  pcbData = 4;
  pvData = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\AppCompat",
         L"DisablePca",
         0x18u,
         0,
         &pvData,
         &pcbData) )
  {
    return 0;
  }
  result = 1;
  if ( pvData != 1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180002bd0  push    rbx
0x180002bd2  sub     rsp, 40h
0x180002bd6  lea     rax, [rsp+48h+arg_8]
0x180002bdb  mov     [rsp+48h+arg_8], 4
0x180002be3  mov     [rsp+48h+pcbData], rax; pcbData
0x180002be8  lea     r8, Value; "DisablePca"
0x180002bef  lea     rax, [rsp+48h+arg_0]
0x180002bf4  xor     ebx, ebx
0x180002bf6  mov     [rsp+48h+pvData], rax; pvData
0x180002bfb  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180002c02  mov     r9d, 18h; dwFlags
0x180002c08  mov     [rsp+48h+pdwType], rbx; pdwType
0x180002c0d  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180002c14  mov     [rsp+48h+arg_0], ebx
0x180002c18  call    cs:__imp_RegGetValueW
0x180002c1e  test    eax, eax
0x180002c20  jz      short loc_180002C74
0x180002c22  lea     rax, [rsp+48h+arg_8]
0x180002c27  mov     [rsp+48h+arg_8], 4
0x180002c2f  mov     [rsp+48h+pcbData], rax; pcbData
0x180002c34  lea     r8, Value; "DisablePca"
0x180002c3b  lea     rax, [rsp+48h+arg_0]
0x180002c40  mov     [rsp+48h+arg_0], ebx
0x180002c44  mov     [rsp+48h+pvData], rax; pvData
0x180002c49  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180002c50  mov     r9d, 18h; dwFlags
0x180002c56  mov     [rsp+48h+pdwType], rbx; pdwType
0x180002c5b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002c62  call    cs:__imp_RegGetValueW
0x180002c68  test    eax, eax
0x180002c6a  jz      short loc_180002C86
0x180002c6c  mov     eax, ebx
0x180002c6e  add     rsp, 40h
0x180002c72  pop     rbx
0x180002c73  retn
0x180002c74  cmp     [rsp+48h+arg_0], 1
0x180002c79  jnz     short loc_180002C22
0x180002c7b  mov     eax, 1
0x180002c80  add     rsp, 40h
0x180002c84  pop     rbx
0x180002c85  retn
0x180002c86  cmp     [rsp+48h+arg_0], 1
0x180002c8b  mov     eax, 1
0x180002c90  jz      short loc_180002C6E
0x180002c92  jmp     short loc_180002C6C
```
