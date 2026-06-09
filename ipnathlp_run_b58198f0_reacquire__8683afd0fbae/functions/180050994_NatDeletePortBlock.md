# NatDeletePortBlock

- ea: `0x180050994`
- end: `0x180050aba`
- name: `NatDeletePortBlock`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180050920`
- `0x18005b370`

## callees

- `0x180050994`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050a73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050a73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050a87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050a87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800509c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800509c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050a4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050a4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050a96`
- `ntdll!NtDeviceIoControlFile` at `0x180050a35`
- `ntdll!NtDeviceIoControlFile` at `0x180050a35`

## pseudocode

```c
int __fastcall NatDeletePortBlock(__int64 a1, void ***a2)
{
  HANDLE EventW; // rax
  void *v5; // rdi
  void *v6; // rcx
  void **v7; // rax
  void **v8; // rcx
  HANDLE ProcessHeap; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  __int64 InputBuffer; // [rsp+80h] [rbp+18h] BYREF

  InputBuffer = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v5 = EventW;
  if ( EventW )
  {
    HIDWORD(InputBuffer) = *((_DWORD *)a2 + 4);
    v6 = *(void **)(a1 + 40);
    LODWORD(InputBuffer) = 0;
    if ( NtDeviceIoControlFile(v6, EventW, 0, 0, &IoStatusBlock, 0x128024u, &InputBuffer, 8u, 0, 0) == 259 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    v7 = *a2;
    if ( (*a2)[1] != a2 || (v8 = a2[1], *v8 != a2) )
      __fastfail(3u);
    *v8 = v7;
    v7[1] = v8;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a2);
    LODWORD(EventW) = CloseHandle(v5);
  }
  return (int)EventW;
}

```

## disassembly

```asm
0x180050994  mov     rax, rsp
0x180050997  mov     [rax+8], rbx
0x18005099b  mov     [rax+10h], rsi
0x18005099f  push    rdi
0x1800509a0  sub     rsp, 60h
0x1800509a4  mov     rbx, rdx
0x1800509a7  mov     qword ptr [rax+18h], 0
0x1800509af  mov     rsi, rcx
0x1800509b2  xorps   xmm0, xmm0
0x1800509b5  xor     edx, edx; bManualReset
0x1800509b7  xor     ecx, ecx; lpEventAttributes
0x1800509b9  xor     r9d, r9d; lpName
0x1800509bc  xor     r8d, r8d; bInitialState
0x1800509bf  movups  xmmword ptr [rax-18h], xmm0
0x1800509c3  call    cs:__imp_CreateEventW
0x1800509ca  nop     dword ptr [rax+rax+00h]
0x1800509cf  mov     rdi, rax
0x1800509d2  test    rax, rax
0x1800509d5  jz      loc_180050AA2
0x1800509db  mov     ecx, [rbx+10h]
0x1800509de  lea     rax, [rsp+68h+arg_10]
0x1800509e6  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x1800509ee  xor     r9d, r9d; ApcContext
0x1800509f1  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x1800509fa  xor     r8d, r8d; ApcRoutine
0x1800509fd  mov     [rsp+68h+InputBufferLength], 8; InputBufferLength
0x180050a05  mov     rdx, rdi; Event
0x180050a08  mov     [rsp+68h+InputBuffer], rax; InputBuffer
0x180050a0d  lea     rax, [rsp+68h+var_18]
0x180050a12  mov     [rsp+68h+arg_14], ecx
0x180050a19  mov     rcx, [rsi+28h]; FileHandle
0x180050a1d  mov     [rsp+68h+IoControlCode], 128024h; IoControlCode
0x180050a25  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180050a2a  mov     [rsp+68h+arg_10], 0
0x180050a35  call    cs:__imp_NtDeviceIoControlFile
0x180050a3c  nop     dword ptr [rax+rax+00h]
0x180050a41  cmp     eax, 103h
0x180050a46  jnz     short loc_180050A5A
0x180050a48  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180050a4b  mov     rcx, rdi; hHandle
0x180050a4e  call    cs:__imp_WaitForSingleObject
0x180050a55  nop     dword ptr [rax+rax+00h]
0x180050a5a  mov     rax, [rbx]
0x180050a5d  cmp     [rax+8], rbx
0x180050a61  jnz     short loc_180050AB3
0x180050a63  mov     rcx, [rbx+8]
0x180050a67  cmp     [rcx], rbx
0x180050a6a  jnz     short loc_180050AB3
0x180050a6c  mov     [rcx], rax
0x180050a6f  mov     [rax+8], rcx
0x180050a73  call    cs:__imp_GetProcessHeap
0x180050a7a  nop     dword ptr [rax+rax+00h]
0x180050a7f  mov     r8, rbx; lpMem
0x180050a82  xor     edx, edx; dwFlags
0x180050a84  mov     rcx, rax; hHeap
0x180050a87  call    cs:__imp_HeapFree
0x180050a8e  nop     dword ptr [rax+rax+00h]
0x180050a93  mov     rcx, rdi; hObject
0x180050a96  call    cs:__imp_CloseHandle
0x180050a9d  nop     dword ptr [rax+rax+00h]
0x180050aa2  mov     rbx, [rsp+68h+arg_0]
0x180050aa7  mov     rsi, [rsp+68h+arg_8]
0x180050aac  add     rsp, 60h
0x180050ab0  pop     rdi
0x180050ab1  retn
0x180050ab3  mov     ecx, 3
0x180050ab8  int     29h; Win8: RtlFailFast(ecx)
```
