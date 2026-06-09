# NsiEnumerateObjectsAllParameters

- ea: `0x180002110`
- end: `0x1800022ff`
- name: `NsiEnumerateObjectsAllParameters`
- size: `495`
- prototype: `DWORD __fastcall(unsigned int, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, int, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002110`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180002211`
- `ntdll!NtDeviceIoControlFile` at `0x180002211`
- `ntdll!NtWaitForSingleObject` at `0x1800022ec`
- `ntdll!NtWaitForSingleObject` at `0x1800022ec`
- `ntdll!RtlNtStatusToDosError` at `0x180002263`
- `ntdll!RtlNtStatusToDosError` at `0x180002263`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002296`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800021b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800021b4`

## pseudocode

```c
DWORD __fastcall NsiEnumerateObjectsAllParameters(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        unsigned int a10,
        __int64 a11,
        int a12,
        _DWORD *a13)
{
  HANDLE EventA; // rax
  void *v14; // rbx
  int Status; // edi
  DWORD result; // eax
  HANDLE FileW; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-71h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-61h] BYREF
  __int64 v20; // [rsp+70h] [rbp-51h]
  __int64 v21; // [rsp+78h] [rbp-49h]
  unsigned __int64 v22; // [rsp+80h] [rbp-41h]
  __int64 v23; // [rsp+88h] [rbp-39h]
  __int64 v24; // [rsp+90h] [rbp-31h]
  __int64 v25; // [rsp+98h] [rbp-29h]
  __int64 v26; // [rsp+A0h] [rbp-21h]
  __int64 v27; // [rsp+A8h] [rbp-19h]
  __int64 v28; // [rsp+B0h] [rbp-11h]
  __int64 v29; // [rsp+B8h] [rbp-9h]
  __int128 v30; // [rsp+C0h] [rbp-1h]

  v22 = 0;
  v23 = a5;
  v24 = a6;
  v25 = a7;
  v26 = a8;
  v27 = a9;
  v28 = a10;
  v29 = a11;
  v30 = 0;
  LODWORD(v30) = a12;
  DWORD2(v30) = *a13;
  InputBuffer = 0;
  v20 = a3;
  v21 = a4;
  v22 = __PAIR64__(a2, a1);
  IoStatusBlock = 0;
  if ( g_NsiAsyncDeviceHandle == (HANDLE)-1LL )
  {
    FileW = CreateFileW(L"\\\\.\\Nsi", 0, 3u, 0, 3u, 0x40000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result )
        goto LABEL_7;
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
  v14 = EventA;
  if ( EventA )
  {
    Status = NtDeviceIoControlFile(
               g_NsiAsyncDeviceHandle,
               EventA,
               0,
               0,
               &IoStatusBlock,
               0x12001Bu,
               &InputBuffer,
               0x70u,
               &InputBuffer,
               0x70u);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(v14, 0, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
    }
    CloseHandle(v14);
    if ( Status < 0 || Status == 261 )
      result = RtlNtStatusToDosError(Status);
    else
      result = 0;
  }
  else
  {
    result = GetLastError();
  }
LABEL_7:
  *a13 = DWORD2(v30);
  return result;
}

```

## disassembly

```asm
0x180002110  mov     [rsp-8+arg_10], rsi
0x180002115  push    rbp
0x180002116  lea     rbp, [rsp-0Fh]
0x18000211b  sub     rsp, 0D0h
0x180002122  cmp     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x18000212a  xorps   xmm0, xmm0
0x18000212d  mov     rax, [rbp+0Fh+arg_20]
0x180002131  mov     rsi, [rbp+0Fh+arg_60]
0x180002135  movups  [rbp+0Fh+var_50], xmm0
0x180002139  mov     qword ptr [rbp+0Fh+var_50+8], rax
0x18000213d  mov     eax, [rbp+0Fh+arg_28]
0x180002140  movups  [rbp+0Fh+var_40], xmm0
0x180002144  mov     dword ptr [rbp+0Fh+var_40], eax
0x180002147  mov     rax, [rbp+0Fh+arg_30]
0x18000214b  mov     qword ptr [rbp+0Fh+var_40+8], rax
0x18000214f  mov     eax, [rbp+0Fh+arg_38]
0x180002152  movups  [rbp+0Fh+var_30], xmm0
0x180002156  mov     dword ptr [rbp+0Fh+var_30], eax
0x180002159  mov     rax, [rbp+0Fh+arg_40]
0x18000215d  mov     qword ptr [rbp+0Fh+var_30+8], rax
0x180002161  mov     eax, [rbp+0Fh+arg_48]
0x180002164  movups  [rbp+0Fh+var_20], xmm0
0x180002168  mov     dword ptr [rbp+0Fh+var_20], eax
0x18000216b  mov     rax, [rbp+0Fh+arg_50]
0x18000216f  mov     qword ptr [rbp+0Fh+var_20+8], rax
0x180002173  mov     eax, [rbp+0Fh+arg_58]
0x180002176  movups  [rbp+0Fh+var_10], xmm0
0x18000217a  mov     dword ptr [rbp+0Fh+var_10], eax
0x18000217d  mov     eax, [rsi]
0x18000217f  movups  [rbp+0Fh+var_60], xmm0
0x180002183  mov     dword ptr [rbp+0Fh+var_10+8], eax
0x180002186  movups  [rbp+0Fh+var_70], xmm0
0x18000218a  mov     qword ptr [rbp+0Fh+var_60], r8
0x18000218e  mov     dword ptr [rbp+0Fh+var_60+8], r9d
0x180002192  mov     dword ptr [rbp+0Fh+var_50], ecx
0x180002195  mov     dword ptr [rbp+0Fh+var_50+4], edx
0x180002198  movups  xmmword ptr [rbp+0Fh+var_80], xmm0
0x18000219c  jz      loc_18000226B
0x1800021a2  xor     r9d, r9d; lpName
0x1800021a5  mov     [rsp+0D0h+arg_0], rbx
0x1800021ad  xor     r8d, r8d; bInitialState
0x1800021b0  xor     edx, edx; bManualReset
0x1800021b2  xor     ecx, ecx; lpEventAttributes
0x1800021b4  call    cs:__imp_CreateEventA
0x1800021ba  mov     rbx, rax
0x1800021bd  test    rax, rax
0x1800021c0  jz      loc_1800022D9
0x1800021c6  mov     rcx, cs:g_NsiAsyncDeviceHandle; FileHandle
0x1800021cd  lea     rax, [rbp+0Fh+var_70]
0x1800021d1  mov     [rsp+0D0h+OutputBufferLength], 70h ; 'p'; OutputBufferLength
0x1800021d9  xor     r9d, r9d; ApcContext
0x1800021dc  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x1800021e1  xor     r8d, r8d; ApcRoutine
0x1800021e4  mov     [rsp+0D0h+InputBufferLength], 70h ; 'p'; InputBufferLength
0x1800021ec  lea     rax, [rbp+0Fh+var_70]
0x1800021f0  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x1800021f5  mov     rdx, rbx; Event
0x1800021f8  lea     rax, [rbp+0Fh+var_80]
0x1800021fc  mov     [rsp+0D0h+IoControlCode], 12001Bh; IoControlCode
0x180002204  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x180002209  mov     [rsp+0D0h+arg_8], rdi
0x180002211  call    cs:__imp_NtDeviceIoControlFile
0x180002217  mov     edi, eax
0x180002219  cmp     eax, 103h
0x18000221e  jz      loc_1800022E4
0x180002224  mov     rcx, rbx; hObject
0x180002227  call    cs:__imp_CloseHandle
0x18000222d  test    edi, edi
0x18000222f  js      short loc_180002261
0x180002231  cmp     edi, 105h
0x180002237  jz      short loc_180002261
0x180002239  xor     eax, eax
0x18000223b  mov     rdi, [rsp+0D0h+arg_8]
0x180002243  mov     rbx, [rsp+0D0h+arg_0]
0x18000224b  mov     ecx, dword ptr [rbp+0Fh+var_10+8]
0x18000224e  mov     [rsi], ecx
0x180002250  mov     rsi, [rsp+0D0h+arg_10]
0x180002258  add     rsp, 0D0h
0x18000225f  pop     rbp
0x180002260  retn
0x180002261  mov     ecx, edi; Status
0x180002263  call    cs:__imp_RtlNtStatusToDosError
0x180002269  jmp     short loc_18000223B
0x18000226b  mov     [rsp+0D0h+InputBuffer], 0; hTemplateFile
0x180002274  lea     rcx, FileName; "\\\\.\\Nsi"
0x18000227b  mov     [rsp+0D0h+IoControlCode], 40000000h; dwFlagsAndAttributes
0x180002283  xor     r9d, r9d; lpSecurityAttributes
0x180002286  xor     edx, edx; dwDesiredAccess
0x180002288  mov     dword ptr [rsp+0D0h+IoStatusBlock], 3; dwCreationDisposition
0x180002290  mov     r8d, 3; dwShareMode
0x180002296  call    cs:__imp_CreateFileW
0x18000229c  mov     rcx, rax; hObject
0x18000229f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800022a3  jz      short loc_1800022C6
0x1800022a5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800022ac  lock cmpxchg cs:g_NsiAsyncDeviceHandle, rcx
0x1800022b5  jz      loc_1800021A2
0x1800022bb  call    cs:__imp_CloseHandle
0x1800022c1  jmp     loc_1800021A2
0x1800022c6  call    cs:__imp_GetLastError
0x1800022cc  test    eax, eax
0x1800022ce  jz      loc_1800021A2
0x1800022d4  jmp     loc_18000224B
0x1800022d9  call    cs:__imp_GetLastError
0x1800022df  jmp     loc_180002243
0x1800022e4  xor     r8d, r8d; Timeout
0x1800022e7  xor     edx, edx; Alertable
0x1800022e9  mov     rcx, rbx; Handle
0x1800022ec  call    cs:__imp_NtWaitForSingleObject
0x1800022f2  test    eax, eax
0x1800022f4  mov     edi, eax
0x1800022f6  cmovns  edi, dword ptr [rbp+0Fh+var_80]
0x1800022fa  jmp     loc_180002224
```
