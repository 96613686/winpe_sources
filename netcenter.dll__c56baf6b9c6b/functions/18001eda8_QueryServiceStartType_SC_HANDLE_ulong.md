# QueryServiceStartType(SC_HANDLE__ *,ulong *)

- ea: `0x18001eda8`
- end: `0x18001ee7a`
- name: `?QueryServiceStartType@@YAJPEAUSC_HANDLE__@@PEAK@Z`
- size: `210`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001e564`
- `0x18001ec44`

## callees

- `0x180010e9c`
- `0x18001eda8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ee4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ee4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ee03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ee03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001edf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ee3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001edf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ee3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ede6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ede6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001eddc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001ee21`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001eddc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001ee21`

## pseudocode

```c
__int64 __fastcall QueryServiceStartType(SC_HANDLE hService, unsigned int *a2)
{
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  struct _QUERY_SERVICE_CONFIGW *v6; // rax
  struct _QUERY_SERVICE_CONFIGW *v7; // rdi
  unsigned int Error; // ebx
  HANDLE v9; // rax
  DWORD pcbBytesNeeded; // [rsp+50h] [rbp+8h] BYREF

  if ( !hService || !a2 )
    return 2147942487LL;
  pcbBytesNeeded = 0;
  if ( QueryServiceConfigW(hService, 0, 0, &pcbBytesNeeded) )
  {
    return (unsigned int)-2147467259;
  }
  else if ( GetLastError() == 122 )
  {
    v4 = pcbBytesNeeded;
    ProcessHeap = GetProcessHeap();
    v6 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 0, v4);
    v7 = v6;
    if ( !v6 )
      return 2147942414LL;
    if ( QueryServiceConfigW(hService, v6, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      Error = 0;
      *a2 = v7->dwStartType;
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x18001eda8  push    rbx
0x18001edaa  push    rsi
0x18001edab  push    rdi
0x18001edac  push    r14
0x18001edae  sub     rsp, 28h
0x18001edb2  mov     r14, rdx
0x18001edb5  mov     rsi, rcx
0x18001edb8  test    rcx, rcx
0x18001edbb  jz      loc_18001EE6B
0x18001edc1  test    rdx, rdx
0x18001edc4  jz      loc_18001EE6B
0x18001edca  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18001edcf  mov     [rsp+48h+pcbBytesNeeded], 0
0x18001edd7  xor     r8d, r8d; cbBufSize
0x18001edda  xor     edx, edx; lpServiceConfig
0x18001eddc  call    cs:__imp_QueryServiceConfigW
0x18001ede2  test    eax, eax
0x18001ede4  jnz     short loc_18001EE62
0x18001ede6  call    cs:__imp_GetLastError
0x18001edec  cmp     eax, 7Ah ; 'z'
0x18001edef  jnz     short loc_18001EE59
0x18001edf1  mov     ebx, [rsp+48h+pcbBytesNeeded]
0x18001edf5  call    cs:__imp_GetProcessHeap
0x18001edfb  mov     r8d, ebx; dwBytes
0x18001edfe  xor     edx, edx; dwFlags
0x18001ee00  mov     rcx, rax; hHeap
0x18001ee03  call    cs:__imp_HeapAlloc
0x18001ee09  mov     rdi, rax
0x18001ee0c  test    rax, rax
0x18001ee0f  jz      short loc_18001EE52
0x18001ee11  mov     r8d, [rsp+48h+pcbBytesNeeded]; cbBufSize
0x18001ee16  lea     r9, [rsp+48h+pcbBytesNeeded]; pcbBytesNeeded
0x18001ee1b  mov     rdx, rax; lpServiceConfig
0x18001ee1e  mov     rcx, rsi; hService
0x18001ee21  call    cs:__imp_QueryServiceConfigW
0x18001ee27  test    eax, eax
0x18001ee29  jz      short loc_18001EE35
0x18001ee2b  mov     ecx, [rdi+4]
0x18001ee2e  xor     ebx, ebx
0x18001ee30  mov     [r14], ecx
0x18001ee33  jmp     short loc_18001EE3C
0x18001ee35  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ee3a  mov     ebx, eax
0x18001ee3c  call    cs:__imp_GetProcessHeap
0x18001ee42  mov     r8, rdi; lpMem
0x18001ee45  xor     edx, edx; dwFlags
0x18001ee47  mov     rcx, rax; hHeap
0x18001ee4a  call    cs:__imp_HeapFree
0x18001ee50  jmp     short loc_18001EE67
0x18001ee52  mov     eax, 8007000Eh
0x18001ee57  jmp     short loc_18001EE70
0x18001ee59  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ee5e  mov     ebx, eax
0x18001ee60  jmp     short loc_18001EE67
0x18001ee62  mov     ebx, 80004005h
0x18001ee67  mov     eax, ebx
0x18001ee69  jmp     short loc_18001EE70
0x18001ee6b  mov     eax, 80070057h
0x18001ee70  add     rsp, 28h
0x18001ee74  pop     r14
0x18001ee76  pop     rdi
0x18001ee77  pop     rsi
0x18001ee78  pop     rbx
0x18001ee79  retn
```
