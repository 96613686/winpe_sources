# NatCreatePortBlock

- ea: `0x180056bbc`
- end: `0x180056d6d`
- name: `NatCreatePortBlock`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180056b00`

## callees

- `0x180056bbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056cce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056bef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056cce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056bfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056bfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056cdc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056c1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056c1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056cb7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056cb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056cc4`
- `ntdll!RtlClearAllBits` at `0x180056d0d`
- `ntdll!RtlClearAllBits` at `0x180056d0d`
- `ntdll!RtlInitializeBitMap` at `0x180056d03`
- `ntdll!RtlInitializeBitMap` at `0x180056d03`
- `ntdll!NtDeviceIoControlFile` at `0x180056ca2`
- `ntdll!NtDeviceIoControlFile` at `0x180056ca2`
- `ntdll!RtlNtStatusToDosError` at `0x180056ce4`
- `ntdll!RtlNtStatusToDosError` at `0x180056ce4`

## pseudocode

```c
ULONG __fastcall NatCreatePortBlock(__int64 a1, _QWORD *a2)
{
  unsigned int v2; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v6; // rdi
  HANDLE EventW; // rbx
  HANDLE v9; // rax
  void *v10; // rcx
  int Status; // esi
  HANDLE v12; // rax
  __int64 *v13; // rbp
  __int64 *i; // rax
  __int64 **v15; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-28h] BYREF
  int OutputBuffer; // [rsp+80h] [rbp+8h] BYREF
  __int64 InputBuffer; // [rsp+90h] [rbp+18h] BYREF

  v2 = *(unsigned __int16 *)(a1 + 50);
  IoStatusBlock = 0;
  InputBuffer = 0;
  OutputBuffer = 0;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 0, v2);
  if ( !v6 )
    return 8;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v6);
    return 8;
  }
  v10 = *(void **)(a1 + 40);
  HIDWORD(InputBuffer) = *(unsigned __int16 *)(a1 + 48);
  LODWORD(InputBuffer) = 1;
  Status = NtDeviceIoControlFile(v10, EventW, 0, 0, &IoStatusBlock, 0x128024u, &InputBuffer, 8u, &OutputBuffer, 4u);
  if ( Status == 259 )
  {
    WaitForSingleObject(EventW, 0xFFFFFFFF);
    Status = IoStatusBlock.Status;
  }
  CloseHandle(EventW);
  if ( Status >= 0 )
  {
    *((_DWORD *)v6 + 4) = OutputBuffer;
    RtlInitializeBitMap((PRTL_BITMAP)(v6 + 3), (PULONG)v6 + 10, *(unsigned __int16 *)(a1 + 48));
    RtlClearAllBits((PRTL_BITMAP)(v6 + 3));
    v13 = (__int64 *)(a1 + 56);
    for ( i = (__int64 *)*v13; i != v13; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)v6 + 4) <= *((_DWORD *)i + 4) )
        break;
    }
    v15 = (__int64 **)i[1];
    if ( *v15 != i )
      __fastfail(3u);
    *v6 = i;
    v6[1] = v15;
    *v15 = v6;
    i[1] = (__int64)v6;
    if ( a2 )
      *a2 = v6;
    return 0;
  }
  else
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v6);
    return RtlNtStatusToDosError(Status);
  }
}

```

## disassembly

```asm
0x180056bbc  mov     rax, rsp
0x180056bbf  mov     [rax+10h], rbx
0x180056bc3  mov     [rax+20h], rbp
0x180056bc7  push    rsi
0x180056bc8  push    rdi
0x180056bc9  push    r14
0x180056bcb  sub     rsp, 60h
0x180056bcf  movzx   ebx, word ptr [rcx+32h]
0x180056bd3  xorps   xmm0, xmm0
0x180056bd6  movups  xmmword ptr [rax-28h], xmm0
0x180056bda  mov     r14, rdx
0x180056bdd  mov     qword ptr [rax+18h], 0
0x180056be5  mov     rbp, rcx
0x180056be8  mov     dword ptr [rax+8], 0
0x180056bef  call    cs:__imp_GetProcessHeap
0x180056bf5  mov     r8d, ebx; dwBytes
0x180056bf8  xor     edx, edx; dwFlags
0x180056bfa  mov     rcx, rax; hHeap
0x180056bfd  call    cs:__imp_HeapAlloc
0x180056c03  mov     rdi, rax
0x180056c06  test    rax, rax
0x180056c09  jnz     short loc_180056C15
0x180056c0b  mov     eax, 8
0x180056c10  jmp     loc_180056D58
0x180056c15  xor     r9d, r9d; lpName
0x180056c18  xor     r8d, r8d; bInitialState
0x180056c1b  xor     edx, edx; bManualReset
0x180056c1d  xor     ecx, ecx; lpEventAttributes
0x180056c1f  call    cs:__imp_CreateEventW
0x180056c25  mov     rbx, rax
0x180056c28  test    rax, rax
0x180056c2b  jnz     short loc_180056C43
0x180056c2d  call    cs:__imp_GetProcessHeap
0x180056c33  mov     r8, rdi; lpMem
0x180056c36  xor     edx, edx; dwFlags
0x180056c38  mov     rcx, rax; hHeap
0x180056c3b  call    cs:__imp_HeapFree
0x180056c41  jmp     short loc_180056C0B
0x180056c43  movzx   eax, word ptr [rbp+30h]
0x180056c47  xor     r9d, r9d; ApcContext
0x180056c4a  mov     rcx, [rbp+28h]; FileHandle
0x180056c4e  xor     r8d, r8d; ApcRoutine
0x180056c51  mov     [rsp+78h+OutputBufferLength], 4; OutputBufferLength
0x180056c59  mov     rdx, rbx; Event
0x180056c5c  mov     [rsp+78h+arg_14], eax
0x180056c63  lea     rax, [rsp+78h+arg_0]
0x180056c6b  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x180056c70  lea     rax, [rsp+78h+arg_10]
0x180056c78  mov     [rsp+78h+InputBufferLength], 8; InputBufferLength
0x180056c80  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x180056c85  lea     rax, [rsp+78h+var_28]
0x180056c8a  mov     [rsp+78h+IoControlCode], 128024h; IoControlCode
0x180056c92  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x180056c97  mov     [rsp+78h+arg_10], 1
0x180056ca2  call    cs:__imp_NtDeviceIoControlFile
0x180056ca8  mov     esi, eax
0x180056caa  cmp     eax, 103h
0x180056caf  jnz     short loc_180056CC1
0x180056cb1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180056cb4  mov     rcx, rbx; hHandle
0x180056cb7  call    cs:__imp_WaitForSingleObject
0x180056cbd  mov     esi, dword ptr [rsp+78h+var_28]
0x180056cc1  mov     rcx, rbx; hObject
0x180056cc4  call    cs:__imp_CloseHandle
0x180056cca  test    esi, esi
0x180056ccc  jns     short loc_180056CEC
0x180056cce  call    cs:__imp_GetProcessHeap
0x180056cd4  mov     r8, rdi; lpMem
0x180056cd7  xor     edx, edx; dwFlags
0x180056cd9  mov     rcx, rax; hHeap
0x180056cdc  call    cs:__imp_HeapFree
0x180056ce2  mov     ecx, esi; Status
0x180056ce4  call    cs:__imp_RtlNtStatusToDosError
0x180056cea  jmp     short loc_180056D58
0x180056cec  mov     eax, [rsp+78h+arg_0]
0x180056cf3  lea     rdx, [rdi+28h]; BitMapBuffer
0x180056cf7  mov     [rdi+10h], eax
0x180056cfa  lea     rcx, [rdi+18h]; BitMapHeader
0x180056cfe  movzx   r8d, word ptr [rbp+30h]; SizeOfBitMap
0x180056d03  call    cs:__imp_RtlInitializeBitMap
0x180056d09  lea     rcx, [rdi+18h]; BitMapHeader
0x180056d0d  call    cs:__imp_RtlClearAllBits
0x180056d13  add     rbp, 38h ; '8'
0x180056d17  mov     rax, [rbp+0]
0x180056d1b  cmp     rax, rbp
0x180056d1e  jz      short loc_180056D30
0x180056d20  mov     ecx, [rdi+10h]
0x180056d23  cmp     ecx, [rax+10h]
0x180056d26  jbe     short loc_180056D30
0x180056d28  mov     rax, [rax]
0x180056d2b  cmp     rax, rbp
0x180056d2e  jnz     short loc_180056D23
0x180056d30  mov     rcx, [rax+8]
0x180056d34  cmp     [rcx], rax
0x180056d37  jz      short loc_180056D40
0x180056d39  mov     ecx, 3
0x180056d3e  int     29h; Win8: RtlFailFast(ecx)
0x180056d40  mov     [rdi], rax
0x180056d43  mov     [rdi+8], rcx
0x180056d47  mov     [rcx], rdi
0x180056d4a  mov     [rax+8], rdi
0x180056d4e  test    r14, r14
0x180056d51  jz      short loc_180056D56
0x180056d53  mov     [r14], rdi
0x180056d56  xor     eax, eax
0x180056d58  lea     r11, [rsp+78h+var_18]
0x180056d5d  mov     rbx, [r11+28h]
0x180056d61  mov     rbp, [r11+38h]
0x180056d65  mov     rsp, r11
0x180056d68  pop     r14
0x180056d6a  pop     rdi
0x180056d6b  pop     rsi
0x180056d6c  retn
```
