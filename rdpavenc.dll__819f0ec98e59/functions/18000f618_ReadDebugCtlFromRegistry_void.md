# ReadDebugCtlFromRegistry(void)

- ea: `0x18000f618`
- end: `0x18000f6c5`
- name: `?ReadDebugCtlFromRegistry@@YAXXZ`
- size: `173`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000fa84`

## callees

- `0x18000f618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f67f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f67f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f6ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f6ba`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000f638`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000f638`

## pseudocode

```c
void ReadDebugCtlFromRegistry(void)
{
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  phkResult = 0;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\RdpAvenc", &phkResult) )
  {
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(phkResult, 0, L"DebugCtrl", 0x10u, 0, &pvData, &pcbData) )
    {
      gDebugCtrl = pvData & 1;
      byte_1800C20BD = (pvData & 2) != 0;
      byte_1800C20BE = (pvData & 4) != 0;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x18000f618  sub     rsp, 48h
0x18000f61c  lea     r8, [rsp+48h+phkResult]; phkResult
0x18000f621  mov     [rsp+48h+phkResult], 0
0x18000f62a  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18000f631  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f638  call    cs:__imp_RegOpenKeyW
0x18000f63e  test    eax, eax
0x18000f640  jnz     short loc_18000F6B0
0x18000f642  mov     rcx, [rsp+48h+phkResult]; hkey
0x18000f647  lea     r8, Value; "DebugCtrl"
0x18000f64e  mov     [rsp+48h+arg_0], eax
0x18000f652  mov     r9d, 10h; dwFlags
0x18000f658  lea     rax, [rsp+48h+arg_8]
0x18000f65d  mov     [rsp+48h+arg_8], 4
0x18000f665  mov     [rsp+48h+pcbData], rax; pcbData
0x18000f66a  xor     edx, edx; lpSubKey
0x18000f66c  lea     rax, [rsp+48h+arg_0]
0x18000f671  mov     [rsp+48h+pvData], rax; pvData
0x18000f676  mov     [rsp+48h+pdwType], 0; pdwType
0x18000f67f  call    cs:__imp_RegGetValueW
0x18000f685  test    eax, eax
0x18000f687  jnz     short loc_18000F6B0
0x18000f689  mov     ecx, [rsp+48h+arg_0]
0x18000f68d  mov     dl, 1
0x18000f68f  mov     al, cl
0x18000f691  and     al, dl
0x18000f693  mov     cs:?gDebugCtrl@@3URDPAVENC_DEBUG_CTRL@@A, al; RDPAVENC_DEBUG_CTRL gDebugCtrl
0x18000f699  mov     al, cl
0x18000f69b  shr     al, 1
0x18000f69d  and     al, dl
0x18000f69f  shr     cl, 2
0x18000f6a2  and     cl, dl
0x18000f6a4  mov     cs:byte_1800C20BD, al
0x18000f6aa  mov     cs:byte_1800C20BE, cl
0x18000f6b0  mov     rcx, [rsp+48h+phkResult]; hKey
0x18000f6b5  test    rcx, rcx
0x18000f6b8  jz      short loc_18000F6C0
0x18000f6ba  call    cs:__imp_RegCloseKey
0x18000f6c0  add     rsp, 48h
0x18000f6c4  retn
```
