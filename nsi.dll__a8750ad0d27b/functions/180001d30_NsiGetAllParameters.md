# NsiGetAllParameters

- ea: `0x180001d30`
- end: `0x180001f27`
- name: `NsiGetAllParameters`
- size: `503`
- prototype: `DWORD __fastcall(unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001d30`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180001e2f`
- `ntdll!NtDeviceIoControlFile` at `0x180001e2f`
- `ntdll!NtWaitForSingleObject` at `0x180001f14`
- `ntdll!NtWaitForSingleObject` at `0x180001f14`
- `ntdll!RtlNtStatusToDosError` at `0x180001e59`
- `ntdll!RtlNtStatusToDosError` at `0x180001e59`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001ebe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001e45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ee3`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001dda`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180001dda`

## pseudocode

```c
DWORD __fastcall NsiGetAllParameters(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10,
        unsigned int a11)
{
  HANDLE EventA; // rax
  void *v12; // rbx
  int Status; // edi
  DWORD result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-61h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-51h] BYREF
  __int64 v18; // [rsp+70h] [rbp-41h]
  __int64 v19; // [rsp+78h] [rbp-39h]
  __int64 v20; // [rsp+80h] [rbp-31h]
  __int64 v21; // [rsp+88h] [rbp-29h]
  __int64 v22; // [rsp+90h] [rbp-21h]
  __int64 v23; // [rsp+98h] [rbp-19h]
  __int64 v24; // [rsp+A0h] [rbp-11h]
  __int64 v25; // [rsp+A8h] [rbp-9h]
  __int64 v26; // [rsp+B0h] [rbp-1h]
  __int64 v27; // [rsp+B8h] [rbp+7h]
  __int64 v28; // [rsp+C0h] [rbp+Fh]

  v21 = a4;
  v22 = a5;
  v23 = a6;
  v25 = a8;
  v26 = a9;
  v27 = a10;
  v28 = a11;
  InputBuffer = 0;
  v18 = a2;
  v19 = a3;
  v24 = a7;
  v20 = a1;
  IoStatusBlock = 0;
  if ( g_NsiAsyncDeviceHandle == (HANDLE)-1LL )
  {
    FileW = CreateFileW(L"\\\\.\\Nsi", 0, 3u, 0, 3u, 0x40000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result )
        return result;
    }
    else if ( _InterlockedCompareExchange64(
                (volatile signed __int64 *)&g_NsiAsyncDeviceHandle,
                (signed __int64)FileW,
                -1) != -1 )
    {
      CloseHandle(FileW);
    }
  }
  EventA = CreateEventA(0, 0, 0, 0);
  v12 = EventA;
  if ( !EventA )
  {
    result = GetLastError();
LABEL_7:
    if ( result )
      return result;
    goto LABEL_10;
  }
  Status = NtDeviceIoControlFile(
             g_NsiAsyncDeviceHandle,
             EventA,
             0,
             0,
             &IoStatusBlock,
             0x12000Fu,
             &InputBuffer,
             0x68u,
             &InputBuffer,
             0x68u);
  if ( Status == 259 )
  {
    Status = NtWaitForSingleObject(v12, 0, 0);
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
  }
  CloseHandle(v12);
  if ( Status < 0 || Status == 261 )
  {
    result = RtlNtStatusToDosError(Status);
    goto LABEL_7;
  }
  result = 0;
LABEL_10:
  if ( (unsigned int)v24 < a7 )
    return -1073741811;
  return result;
}

```

## disassembly

```asm
0x180001d30  mov     [rsp-8+arg_10], rsi
0x180001d35  mov     [rsp-8+arg_18], r14
0x180001d3a  push    rbp
0x180001d3b  lea     rbp, [rsp-1Fh]
0x180001d40  sub     rsp, 0D0h
0x180001d47  mov     esi, [rbp+1Fh+arg_30]
0x180001d4a  xor     eax, eax
0x180001d4c  xorps   xmm0, xmm0
0x180001d4f  mov     [rbp+1Fh+var_10], rax
0x180001d53  mov     eax, [rbp+1Fh+arg_20]
0x180001d56  xor     r14d, r14d
0x180001d59  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x180001d61  movups  [rbp+1Fh+var_50], xmm0
0x180001d65  mov     qword ptr [rbp+1Fh+var_50+8], r9
0x180001d69  movups  [rbp+1Fh+var_40], xmm0
0x180001d6d  mov     dword ptr [rbp+1Fh+var_40], eax
0x180001d70  mov     rax, [rbp+1Fh+arg_28]
0x180001d74  mov     qword ptr [rbp+1Fh+var_40+8], rax
0x180001d78  mov     rax, [rbp+1Fh+arg_38]
0x180001d7c  movups  [rbp+1Fh+var_30], xmm0
0x180001d80  mov     qword ptr [rbp+1Fh+var_30+8], rax
0x180001d84  mov     eax, [rbp+1Fh+arg_40]
0x180001d87  movups  [rbp+1Fh+var_20], xmm0
0x180001d8b  mov     dword ptr [rbp+1Fh+var_20], eax
0x180001d8e  mov     rax, [rbp+1Fh+arg_48]
0x180001d92  movups  [rbp+1Fh+var_60], xmm0
0x180001d96  mov     qword ptr [rbp+1Fh+var_20+8], rax
0x180001d9a  mov     eax, [rbp+1Fh+arg_50]
0x180001d9d  mov     dword ptr [rbp+1Fh+var_10], eax
0x180001da0  movups  [rbp+1Fh+var_70], xmm0
0x180001da4  mov     qword ptr [rbp+1Fh+var_60], rdx
0x180001da8  mov     dword ptr [rbp+1Fh+var_60+8], r8d
0x180001dac  mov     dword ptr [rbp+1Fh+var_30], esi
0x180001daf  mov     dword ptr [rbp+1Fh+var_50], ecx
0x180001db2  mov     dword ptr [rbp+1Fh+var_50+4], r14d
0x180001db6  movups  xmmword ptr [rbp+1Fh+var_80], xmm0
0x180001dba  jz      loc_180001E97
0x180001dc0  mov     [rsp+0D0h+arg_0], rbx
0x180001dc8  xor     r9d, r9d; lpName
0x180001dcb  xor     r8d, r8d; bInitialState
0x180001dce  mov     [rsp+0D0h+arg_8], rdi
0x180001dd6  xor     edx, edx; bManualReset
0x180001dd8  xor     ecx, ecx; lpEventAttributes
0x180001dda  call    cs:__imp_CreateEventA
0x180001de0  mov     rbx, rax
0x180001de3  test    rax, rax
0x180001de6  jz      loc_180001F01
0x180001dec  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x180001df3  lea     rax, [rbp+1Fh+var_70]
0x180001df7  mov     [rsp+0D0h+OutputBufferLength], 68h ; 'h'; OutputBufferLength
0x180001dff  xor     r9d, r9d; ApcContext
0x180001e02  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x180001e07  xor     r8d, r8d; ApcRoutine
0x180001e0a  mov     [rsp+0D0h+InputBufferLength], 68h ; 'h'; InputBufferLength
0x180001e12  lea     rax, [rbp+1Fh+var_70]
0x180001e16  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x180001e1b  mov     rdx, rbx; Event
0x180001e1e  lea     rax, [rbp+1Fh+var_80]
0x180001e22  mov     [rsp+0D0h+IoControlCode], 12000Fh; IoControlCode
0x180001e2a  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x180001e2f  call    cs:__imp_NtDeviceIoControlFile
0x180001e35  mov     edi, eax
0x180001e37  cmp     eax, 103h
0x180001e3c  jz      loc_180001F0C
0x180001e42  mov     rcx, rbx; hObject
0x180001e45  call    cs:__imp_CloseHandle
0x180001e4b  test    edi, edi
0x180001e4d  js      short loc_180001E57
0x180001e4f  cmp     edi, 105h
0x180001e55  jnz     short loc_180001E88
0x180001e57  mov     ecx, edi; Status
0x180001e59  call    cs:__imp_RtlNtStatusToDosError
0x180001e5f  test    eax, eax
0x180001e61  jz      short loc_180001E8B
0x180001e63  mov     rbx, [rsp+0D0h+arg_0]
0x180001e6b  mov     rdi, [rsp+0D0h+arg_8]
0x180001e73  lea     r11, [rsp+0D0h+var_s0]
0x180001e7b  mov     rsi, [r11+20h]
0x180001e7f  mov     r14, [r11+28h]
0x180001e83  mov     rsp, r11
0x180001e86  pop     rbp
0x180001e87  retn
0x180001e88  mov     eax, r14d
0x180001e8b  cmp     dword ptr [rbp+1Fh+var_30], esi
0x180001e8e  jnb     short loc_180001E63
0x180001e90  mov     eax, 0C000000Dh
0x180001e95  jmp     short loc_180001E63
0x180001e97  mov     [rsp+0D0h+InputBuffer], r14; hTemplateFile
0x180001e9c  lea     rcx, FileName; "\\\\.\\Nsi"
0x180001ea3  mov     [rsp+0D0h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x180001eab  xor     r9d, r9d; lpSecurityAttributes
0x180001eae  xor     edx, edx; dwDesiredAccess
0x180001eb0  mov     dword ptr [rsp+0D0h+IoStatusBlock], 3; dwCreationDisposition
0x180001eb8  mov     r8d, 3; dwShareMode
0x180001ebe  call    cs:__imp_CreateFileW
0x180001ec4  mov     rcx, rax; hObject
0x180001ec7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001ecb  jz      short loc_180001EEE
0x180001ecd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001ed4  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x180001edd  jz      loc_180001DC0
0x180001ee3  call    cs:__imp_CloseHandle
0x180001ee9  jmp     loc_180001DC0
0x180001eee  call    cs:__imp_GetLastError
0x180001ef4  test    eax, eax
0x180001ef6  jz      loc_180001DC0
0x180001efc  jmp     loc_180001E73
0x180001f01  call    cs:__imp_GetLastError
0x180001f07  jmp     loc_180001E5F
0x180001f0c  xor     r8d, r8d; Timeout
0x180001f0f  xor     edx, edx; Alertable
0x180001f11  mov     rcx, rbx; Handle
0x180001f14  call    cs:__imp_NtWaitForSingleObject
0x180001f1a  test    eax, eax
0x180001f1c  mov     edi, eax
0x180001f1e  cmovns  edi, dword ptr [rbp+1Fh+var_80]
0x180001f22  jmp     loc_180001E42
```
