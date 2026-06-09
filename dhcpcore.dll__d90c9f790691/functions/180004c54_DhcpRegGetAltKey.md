# DhcpRegGetAltKey

- ea: `0x180004c54`
- end: `0x180004ce2`
- name: `DhcpRegGetAltKey`
- size: `142`
- prototype: `HKEY __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180015fec`

## callees

- `0x180004c54`
- `0x180005330`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ca3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cda`

## string_xrefs

- `0x180004c77`: `System\CurrentControlSet\Services\?\Parameters\TCPIP`

## pseudocode

```c
HKEY __fastcall DhcpRegGetAltKey(void *a1)
{
  HKEY v2; // [rsp+48h] [rbp+10h]

  v2 = 0;
  if ( a1 )
    DhcpRegExpandString(L"System\\CurrentControlSet\\Services\\?\\Parameters\\TCPIP", a1);
  return v2;
}

```

## disassembly

```asm
0x180004c54  sub     rsp, 38h
0x180004c58  mov     [rsp+38h+lpMem], 0
0x180004c61  mov     [rsp+38h+arg_8], 0
0x180004c6a  test    rcx, rcx
0x180004c6d  jz      short loc_180004CA9
0x180004c6f  mov     rdx, rcx; void *
0x180004c72  lea     r8, [rsp+38h+lpMem]
0x180004c77  lea     rcx, aSystemCurrentc_19; "System\\CurrentControlSet\\Services\\?"...
0x180004c7e  call    DhcpRegExpandString
0x180004c83  test    eax, eax
0x180004c85  jz      short loc_180004CB3
0x180004c87  cmp     [rsp+38h+lpMem], 0
0x180004c8d  jz      short loc_180004CA9
0x180004c8f  mov     rcx, gs:60h
0x180004c98  xor     edx, edx; dwFlags
0x180004c9a  mov     r8, [rsp+38h+lpMem]; lpMem
0x180004c9f  mov     rcx, [rcx+30h]; hHeap
0x180004ca3  call    cs:__imp_HeapFree
0x180004ca9  mov     rax, [rsp+38h+arg_8]
0x180004cae  add     rsp, 38h
0x180004cb2  retn
0x180004cb3  cmp     [rsp+38h+lpMem], 0
0x180004cb9  jz      short loc_180004CA9
0x180004cbb  mov     rdx, [rsp+38h+lpMem]; lpSubKey
0x180004cc0  lea     rax, [rsp+38h+arg_8]
0x180004cc5  mov     r9d, 0Fh; samDesired
0x180004ccb  mov     [rsp+38h+phkResult], rax; phkResult
0x180004cd0  xor     r8d, r8d; ulOptions
0x180004cd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004cda  call    cs:__imp_RegOpenKeyExW
0x180004ce0  jmp     short loc_180004C87
```
