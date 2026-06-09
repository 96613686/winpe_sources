# IsServiceAutoStart(SC_HANDLE__ *)

- ea: `0x180007c34`
- end: `0x180007ce3`
- name: `?IsServiceAutoStart@@YA_NPEAUSC_HANDLE__@@@Z`
- size: `175`
- prototype: `bool __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180007b34`

## callees

- `0x180007c34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007cbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007cca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007c84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c64`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007c5a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007ca2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007c5a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007ca2`

## pseudocode

```c
bool __fastcall IsServiceAutoStart(SC_HANDLE hService)
{
  bool v2; // di
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  struct _QUERY_SERVICE_CONFIGW *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rbx
  HANDLE v7; // rax
  SIZE_T dwBytes; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  v2 = 0;
  if ( QueryServiceConfigW(hService, 0, 0, (LPDWORD)&dwBytes) || GetLastError() == 122 )
  {
    v3 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v5 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 8u, v3);
    v6 = v5;
    if ( v5 )
    {
      if ( QueryServiceConfigW(hService, v5, dwBytes, (LPDWORD)&dwBytes) )
        v2 = v6->dwStartType == 2;
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180007c34  mov     rax, rsp
0x180007c37  mov     [rax+8], rbx
0x180007c3b  mov     [rax+18h], rsi
0x180007c3f  push    rdi
0x180007c40  sub     rsp, 20h
0x180007c44  lea     r9, [rax+10h]; pcbBytesNeeded
0x180007c48  mov     dword ptr [rax+10h], 0
0x180007c4f  xor     r8d, r8d; cbBufSize
0x180007c52  xor     edx, edx; lpServiceConfig
0x180007c54  mov     rsi, rcx
0x180007c57  xor     dil, dil
0x180007c5a  call    cs:__imp_QueryServiceConfigW
0x180007c60  test    eax, eax
0x180007c62  jnz     short loc_180007C6F
0x180007c64  call    cs:__imp_GetLastError
0x180007c6a  cmp     eax, 7Ah ; 'z'
0x180007c6d  jnz     short loc_180007CD0
0x180007c6f  mov     ebx, dword ptr [rsp+28h+dwBytes]
0x180007c73  call    cs:__imp_GetProcessHeap
0x180007c79  mov     r8d, ebx; dwBytes
0x180007c7c  mov     edx, 8; dwFlags
0x180007c81  mov     rcx, rax; hHeap
0x180007c84  call    cs:__imp_HeapAlloc
0x180007c8a  mov     rbx, rax
0x180007c8d  test    rax, rax
0x180007c90  jz      short loc_180007CD0
0x180007c92  mov     r8d, dword ptr [rsp+28h+dwBytes]; cbBufSize
0x180007c97  lea     r9, [rsp+28h+dwBytes]; pcbBytesNeeded
0x180007c9c  mov     rdx, rax; lpServiceConfig
0x180007c9f  mov     rcx, rsi; hService
0x180007ca2  call    cs:__imp_QueryServiceConfigW
0x180007ca8  test    eax, eax
0x180007caa  jz      short loc_180007CBC
0x180007cac  cmp     dword ptr [rbx+4], 2
0x180007cb0  mov     eax, 1
0x180007cb5  movzx   edi, dil
0x180007cb9  cmovz   edi, eax
0x180007cbc  call    cs:__imp_GetProcessHeap
0x180007cc2  mov     r8, rbx; lpMem
0x180007cc5  xor     edx, edx; dwFlags
0x180007cc7  mov     rcx, rax; hHeap
0x180007cca  call    cs:__imp_HeapFree
0x180007cd0  mov     rbx, [rsp+28h+arg_0]
0x180007cd5  mov     al, dil
0x180007cd8  mov     rsi, [rsp+28h+arg_10]
0x180007cdd  add     rsp, 20h
0x180007ce1  pop     rdi
0x180007ce2  retn
```
