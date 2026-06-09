# NatCancelRedirect

- ea: `0x1800427d0`
- end: `0x1800428f7`
- name: `NatCancelRedirect`
- size: `295`
- prototype: `ULONG __fastcall(HANDLE FileHandle, char, int, __int16, int, __int16, int, __int16, int, __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180081ba0`

## callees

- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042814`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042814`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800428c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800428c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800428d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800428d1`
- `ntdll!NtDeviceIoControlFile` at `0x1800428b0`
- `ntdll!NtDeviceIoControlFile` at `0x1800428b0`
- `ntdll!RtlNtStatusToDosError` at `0x1800428e1`
- `ntdll!RtlNtStatusToDosError` at `0x1800428e1`

## pseudocode

```c
ULONG __fastcall NatCancelRedirect(
        HANDLE FileHandle,
        char a2,
        int a3,
        __int16 a4,
        int a5,
        __int16 a6,
        int a7,
        __int16 a8,
        int a9,
        __int16 a10)
{
  HANDLE EventW; // rax
  void *v15; // rdi
  int Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-51h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-41h] BYREF
  __int128 v20; // [rsp+70h] [rbp-31h]
  __int128 v21; // [rsp+80h] [rbp-21h]
  int v22; // [rsp+90h] [rbp-11h]

  v22 = 0;
  InputBuffer = 0;
  v20 = 0;
  v21 = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v15 = EventW;
  if ( !EventW )
    return 8;
  DWORD1(v20) = a5;
  WORD4(v20) = a6;
  HIDWORD(v21) = a7;
  LOWORD(v22) = a8;
  DWORD1(v21) = a9;
  WORD4(v21) = a10;
  LODWORD(InputBuffer) = 0;
  *((_QWORD *)&InputBuffer + 1) = 0;
  LOBYTE(v20) = a2;
  HIDWORD(v20) = a3;
  LOWORD(v21) = a4;
  Status = NtDeviceIoControlFile(FileHandle, EventW, 0, 0, &IoStatusBlock, 0x128034u, &InputBuffer, 0x38u, 0, 0);
  if ( Status == 259 )
  {
    WaitForSingleObject(v15, 0xFFFFFFFF);
    Status = IoStatusBlock.Status;
  }
  CloseHandle(v15);
  if ( Status < 0 )
    return RtlNtStatusToDosError(Status);
  else
    return 0;
}

```

## disassembly

```asm
0x1800427d0  push    rbp
0x1800427d2  push    rbx
0x1800427d3  push    rsi
0x1800427d4  push    rdi
0x1800427d5  push    r14
0x1800427d7  push    r15
0x1800427d9  lea     rbp, [rsp-7]
0x1800427de  sub     rsp, 0A8h
0x1800427e5  xorps   xmm0, xmm0
0x1800427e8  movzx   ebx, r9w
0x1800427ec  mov     esi, r8d
0x1800427ef  mov     r14b, dl
0x1800427f2  mov     r15, rcx
0x1800427f5  xor     eax, eax
0x1800427f7  xor     r9d, r9d; lpName
0x1800427fa  mov     [rbp+2Fh+var_40], eax
0x1800427fd  xor     r8d, r8d; bInitialState
0x180042800  xor     edx, edx; bManualReset
0x180042802  xor     ecx, ecx; lpEventAttributes
0x180042804  movups  [rbp+2Fh+var_70], xmm0
0x180042808  movups  [rbp+2Fh+var_60], xmm0
0x18004280c  movups  [rbp+2Fh+var_50], xmm0
0x180042810  movups  xmmword ptr [rbp+2Fh+var_80], xmm0
0x180042814  call    cs:__imp_CreateEventW
0x18004281a  mov     rdi, rax
0x18004281d  test    rax, rax
0x180042820  jnz     short loc_18004282A
0x180042822  lea     eax, [rdi+8]
0x180042825  jmp     loc_1800428E7
0x18004282a  mov     eax, [rbp+2Fh+arg_20]
0x18004282d  xor     r9d, r9d; ApcContext
0x180042830  mov     dword ptr [rbp+2Fh+var_60+4], eax
0x180042833  xor     r8d, r8d; ApcRoutine
0x180042836  movzx   eax, [rbp+2Fh+arg_28]
0x18004283a  mov     rdx, rdi; Event
0x18004283d  mov     word ptr [rbp+2Fh+var_60+8], ax
0x180042841  mov     rcx, r15; FileHandle
0x180042844  mov     eax, [rbp+2Fh+arg_30]
0x180042847  mov     dword ptr [rbp+2Fh+var_50+0Ch], eax
0x18004284a  movzx   eax, [rbp+2Fh+arg_38]
0x18004284e  mov     word ptr [rbp+2Fh+var_40], ax
0x180042852  mov     eax, [rbp+2Fh+arg_40]
0x180042855  mov     [rsp+0D0h+OutputBufferLength], 0; OutputBufferLength
0x18004285d  mov     dword ptr [rbp+2Fh+var_50+4], eax
0x180042860  movzx   eax, [rbp+2Fh+arg_48]
0x180042867  mov     [rsp+0D0h+OutputBuffer], 0; OutputBuffer
0x180042870  mov     word ptr [rbp+2Fh+var_50+8], ax
0x180042874  lea     rax, [rbp+2Fh+var_70]
0x180042878  mov     [rsp+0D0h+InputBufferLength], 38h ; '8'; InputBufferLength
0x180042880  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x180042885  lea     rax, [rbp+2Fh+var_80]
0x180042889  mov     [rsp+0D0h+IoControlCode], 128034h; IoControlCode
0x180042891  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x180042896  mov     dword ptr [rbp+2Fh+var_70], 0
0x18004289d  mov     qword ptr [rbp+2Fh+var_70+8], 0
0x1800428a5  mov     byte ptr [rbp+2Fh+var_60], r14b
0x1800428a9  mov     dword ptr [rbp+2Fh+var_60+0Ch], esi
0x1800428ac  mov     word ptr [rbp+2Fh+var_50], bx
0x1800428b0  call    cs:__imp_NtDeviceIoControlFile
0x1800428b6  mov     ebx, eax
0x1800428b8  cmp     eax, 103h
0x1800428bd  jnz     short loc_1800428CE
0x1800428bf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800428c2  mov     rcx, rdi; hHandle
0x1800428c5  call    cs:__imp_WaitForSingleObject
0x1800428cb  mov     ebx, dword ptr [rbp+2Fh+var_80]
0x1800428ce  mov     rcx, rdi; hObject
0x1800428d1  call    cs:__imp_CloseHandle
0x1800428d7  test    ebx, ebx
0x1800428d9  js      short loc_1800428DF
0x1800428db  xor     eax, eax
0x1800428dd  jmp     short loc_1800428E7
0x1800428df  mov     ecx, ebx; Status
0x1800428e1  call    cs:__imp_RtlNtStatusToDosError
0x1800428e7  add     rsp, 0A8h
0x1800428ee  pop     r15
0x1800428f0  pop     r14
0x1800428f2  pop     rdi
0x1800428f3  pop     rsi
0x1800428f4  pop     rbx
0x1800428f5  pop     rbp
0x1800428f6  retn
```
