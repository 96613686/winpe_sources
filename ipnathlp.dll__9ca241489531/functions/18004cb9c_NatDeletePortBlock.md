# NatDeletePortBlock

- ea: `0x18004cb9c`
- end: `0x18004cc9d`
- name: `NatDeletePortBlock`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18004cb40`
- `0x180056ef0`

## callees

- `0x18004cb9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cc69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cc69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cc77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004cc77`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004cbcb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004cbcb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004cc4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004cc4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cc80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004cc80`
- `ntdll!NtDeviceIoControlFile` at `0x18004cc37`
- `ntdll!NtDeviceIoControlFile` at `0x18004cc37`

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
0x18004cb9c  mov     rax, rsp
0x18004cb9f  mov     [rax+8], rbx
0x18004cba3  mov     [rax+10h], rsi
0x18004cba7  push    rdi
0x18004cba8  sub     rsp, 60h
0x18004cbac  mov     rbx, rdx
0x18004cbaf  mov     qword ptr [rax+18h], 0
0x18004cbb7  mov     rsi, rcx
0x18004cbba  xorps   xmm0, xmm0
0x18004cbbd  xor     edx, edx; bManualReset
0x18004cbbf  xor     ecx, ecx; lpEventAttributes
0x18004cbc1  xor     r9d, r9d; lpName
0x18004cbc4  xor     r8d, r8d; bInitialState
0x18004cbc7  movups  xmmword ptr [rax-18h], xmm0
0x18004cbcb  call    cs:__imp_CreateEventW
0x18004cbd1  mov     rdi, rax
0x18004cbd4  test    rax, rax
0x18004cbd7  jz      loc_18004CC86
0x18004cbdd  mov     ecx, [rbx+10h]
0x18004cbe0  lea     rax, [rsp+68h+arg_10]
0x18004cbe8  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x18004cbf0  xor     r9d, r9d; ApcContext
0x18004cbf3  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x18004cbfc  xor     r8d, r8d; ApcRoutine
0x18004cbff  mov     [rsp+68h+InputBufferLength], 8; InputBufferLength
0x18004cc07  mov     rdx, rdi; Event
0x18004cc0a  mov     [rsp+68h+InputBuffer], rax; InputBuffer
0x18004cc0f  lea     rax, [rsp+68h+var_18]
0x18004cc14  mov     [rsp+68h+arg_14], ecx
0x18004cc1b  mov     rcx, [rsi+28h]; FileHandle
0x18004cc1f  mov     [rsp+68h+IoControlCode], 128024h; IoControlCode
0x18004cc27  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18004cc2c  mov     [rsp+68h+arg_10], 0
0x18004cc37  call    cs:__imp_NtDeviceIoControlFile
0x18004cc3d  cmp     eax, 103h
0x18004cc42  jnz     short loc_18004CC50
0x18004cc44  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004cc47  mov     rcx, rdi; hHandle
0x18004cc4a  call    cs:__imp_WaitForSingleObject
0x18004cc50  mov     rax, [rbx]
0x18004cc53  cmp     [rax+8], rbx
0x18004cc57  jnz     short loc_18004CC96
0x18004cc59  mov     rcx, [rbx+8]
0x18004cc5d  cmp     [rcx], rbx
0x18004cc60  jnz     short loc_18004CC96
0x18004cc62  mov     [rcx], rax
0x18004cc65  mov     [rax+8], rcx
0x18004cc69  call    cs:__imp_GetProcessHeap
0x18004cc6f  mov     r8, rbx; lpMem
0x18004cc72  xor     edx, edx; dwFlags
0x18004cc74  mov     rcx, rax; hHeap
0x18004cc77  call    cs:__imp_HeapFree
0x18004cc7d  mov     rcx, rdi; hObject
0x18004cc80  call    cs:__imp_CloseHandle
0x18004cc86  mov     rbx, [rsp+68h+arg_0]
0x18004cc8b  mov     rsi, [rsp+68h+arg_8]
0x18004cc90  add     rsp, 60h
0x18004cc94  pop     rdi
0x18004cc95  retn
0x18004cc96  mov     ecx, 3
0x18004cc9b  int     29h; Win8: RtlFailFast(ecx)
```
