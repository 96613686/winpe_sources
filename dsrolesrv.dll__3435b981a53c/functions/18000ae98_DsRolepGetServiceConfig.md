# DsRolepGetServiceConfig

- ea: `0x18000ae98`
- end: `0x18000af90`
- name: `DsRolepGetServiceConfig`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000af98`

## callees

- `0x18000ae98`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af47`
- `ntdll!RtlAllocateHeap` at `0x18000af1d`
- `ntdll!RtlAllocateHeap` at `0x18000af1d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000aec6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000aec6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000af5e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000af5e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000aef9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000af3d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000aef9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000af3d`

## string_xrefs

- `0x18000af6b`: `DsRolepGetServiceConfig on %ws failed with %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepGetServiceConfig(__int64 a1, __int64 a2, SC_HANDLE a3, struct _QUERY_SERVICE_CONFIGW **a4)
{
  SC_HANDLE v6; // rdi
  DWORD LastError; // ebx
  struct _QUERY_SERVICE_CONFIGW *Heap; // rax
  DWORD pcbBytesNeeded; // [rsp+38h] [rbp+10h] BYREF
  int v11; // [rsp+3Ch] [rbp+14h]

  v11 = HIDWORD(a2);
  pcbBytesNeeded = 0;
  if ( a3 )
  {
    v6 = a3;
  }
  else
  {
    v6 = OpenServiceW(0, 0, 1u);
    if ( !v6 )
    {
      LastError = GetLastError();
      goto LABEL_13;
    }
  }
  pcbBytesNeeded = 0;
  if ( !QueryServiceConfigW(v6, 0, 0, &pcbBytesNeeded) )
    GetLastError();
  Heap = (struct _QUERY_SERVICE_CONFIGW *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, pcbBytesNeeded);
  *a4 = Heap;
  if ( Heap )
  {
    LastError = 0;
    if ( !QueryServiceConfigW(v6, Heap, pcbBytesNeeded, &pcbBytesNeeded) )
      LastError = GetLastError();
  }
  else
  {
    LastError = 8;
  }
  if ( !a3 )
    CloseServiceHandle(v6);
LABEL_13:
  if ( LastError )
    DsRolepLogPrintRoutine(4, "DsRolepGetServiceConfig on %ws failed with %lu\n", 0, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000ae98  mov     rax, rsp
0x18000ae9b  mov     [rax+8], rbx
0x18000ae9f  mov     [rax+18h], rsi
0x18000aea3  mov     [rax+10h], rdx
0x18000aea7  push    rdi
0x18000aea8  sub     rsp, 20h
0x18000aeac  mov     dword ptr [rax+10h], 0
0x18000aeb3  mov     rbx, r9
0x18000aeb6  mov     rsi, r8
0x18000aeb9  test    r8, r8
0x18000aebc  jnz     short loc_18000AEE1
0x18000aebe  xor     edx, edx; lpServiceName
0x18000aec0  lea     r8d, [rsi+1]; dwDesiredAccess
0x18000aec4  xor     ecx, ecx; hSCManager
0x18000aec6  call    cs:__imp_OpenServiceW
0x18000aecc  mov     rdi, rax
0x18000aecf  test    rax, rax
0x18000aed2  jnz     short loc_18000AEE4
0x18000aed4  call    cs:__imp_GetLastError
0x18000aeda  mov     ebx, eax
0x18000aedc  jmp     loc_18000AF64
0x18000aee1  mov     rdi, rsi
0x18000aee4  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18000aee9  mov     [rsp+28h+pcbBytesNeeded], 0
0x18000aef1  xor     r8d, r8d; cbBufSize
0x18000aef4  xor     edx, edx; lpServiceConfig
0x18000aef6  mov     rcx, rdi; hService
0x18000aef9  call    cs:__imp_QueryServiceConfigW
0x18000aeff  test    eax, eax
0x18000af01  jnz     short loc_18000AF09
0x18000af03  call    cs:__imp_GetLastError
0x18000af09  mov     rcx, gs:60h
0x18000af12  xor     edx, edx; Flags
0x18000af14  mov     r8d, [rsp+28h+pcbBytesNeeded]; Size
0x18000af19  mov     rcx, [rcx+30h]; HeapHandle
0x18000af1d  call    cs:__imp_RtlAllocateHeap
0x18000af23  mov     [rbx], rax
0x18000af26  test    rax, rax
0x18000af29  jz      short loc_18000AF51
0x18000af2b  mov     r8d, [rsp+28h+pcbBytesNeeded]; cbBufSize
0x18000af30  lea     r9, [rsp+28h+pcbBytesNeeded]; pcbBytesNeeded
0x18000af35  mov     rdx, rax; lpServiceConfig
0x18000af38  mov     rcx, rdi; hService
0x18000af3b  xor     ebx, ebx
0x18000af3d  call    cs:__imp_QueryServiceConfigW
0x18000af43  test    eax, eax
0x18000af45  jnz     short loc_18000AF56
0x18000af47  call    cs:__imp_GetLastError
0x18000af4d  mov     ebx, eax
0x18000af4f  jmp     short loc_18000AF56
0x18000af51  mov     ebx, 8
0x18000af56  test    rsi, rsi
0x18000af59  jnz     short loc_18000AF64
0x18000af5b  mov     rcx, rdi; hSCObject
0x18000af5e  call    cs:__imp_CloseServiceHandle
0x18000af64  test    ebx, ebx
0x18000af66  jz      short loc_18000AF7E
0x18000af68  xor     r8d, r8d
0x18000af6b  lea     rdx, aDsrolepgetserv; "DsRolepGetServiceConfig on %ws failed w"...
0x18000af72  mov     r9d, ebx
0x18000af75  lea     ecx, [r8+4]
0x18000af79  call    DsRolepLogPrintRoutine
0x18000af7e  mov     rsi, [rsp+28h+arg_10]
0x18000af83  mov     eax, ebx
0x18000af85  mov     rbx, [rsp+28h+arg_0]
0x18000af8a  add     rsp, 20h
0x18000af8e  pop     rdi
0x18000af8f  retn
```
