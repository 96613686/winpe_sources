# NatCreatePortBlock

- ea: `0x18005afc8`
- end: `0x18005b1c8`
- name: `NatCreatePortBlock`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005aef0`

## callees

- `0x18005afc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005affb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b04b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b10a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005affb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b04b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b10a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b00f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b00f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b05f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b11e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b05f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b11e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b037`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b037`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b0e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005b0e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b0fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b0fa`
- `ntdll!RtlClearAllBits` at `0x18005b161`
- `ntdll!RtlClearAllBits` at `0x18005b161`
- `ntdll!RtlInitializeBitMap` at `0x18005b151`
- `ntdll!RtlInitializeBitMap` at `0x18005b151`
- `ntdll!NtDeviceIoControlFile` at `0x18005b0cc`
- `ntdll!NtDeviceIoControlFile` at `0x18005b0cc`
- `ntdll!RtlNtStatusToDosError` at `0x18005b12c`
- `ntdll!RtlNtStatusToDosError` at `0x18005b12c`

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
0x18005afc8  mov     rax, rsp
0x18005afcb  mov     [rax+10h], rbx
0x18005afcf  mov     [rax+20h], rbp
0x18005afd3  push    rsi
0x18005afd4  push    rdi
0x18005afd5  push    r14
0x18005afd7  sub     rsp, 60h
0x18005afdb  movzx   ebx, word ptr [rcx+32h]
0x18005afdf  xorps   xmm0, xmm0
0x18005afe2  movups  xmmword ptr [rax-28h], xmm0
0x18005afe6  mov     r14, rdx
0x18005afe9  mov     qword ptr [rax+18h], 0
0x18005aff1  mov     rbp, rcx
0x18005aff4  mov     dword ptr [rax+8], 0
0x18005affb  call    cs:__imp_GetProcessHeap
0x18005b002  nop     dword ptr [rax+rax+00h]
0x18005b007  mov     r8d, ebx; dwBytes
0x18005b00a  xor     edx, edx; dwFlags
0x18005b00c  mov     rcx, rax; hHeap
0x18005b00f  call    cs:__imp_HeapAlloc
0x18005b016  nop     dword ptr [rax+rax+00h]
0x18005b01b  mov     rdi, rax
0x18005b01e  test    rax, rax
0x18005b021  jnz     short loc_18005B02D
0x18005b023  mov     eax, 8
0x18005b028  jmp     loc_18005B1B2
0x18005b02d  xor     r9d, r9d; lpName
0x18005b030  xor     r8d, r8d; bInitialState
0x18005b033  xor     edx, edx; bManualReset
0x18005b035  xor     ecx, ecx; lpEventAttributes
0x18005b037  call    cs:__imp_CreateEventW
0x18005b03e  nop     dword ptr [rax+rax+00h]
0x18005b043  mov     rbx, rax
0x18005b046  test    rax, rax
0x18005b049  jnz     short loc_18005B06D
0x18005b04b  call    cs:__imp_GetProcessHeap
0x18005b052  nop     dword ptr [rax+rax+00h]
0x18005b057  mov     r8, rdi; lpMem
0x18005b05a  xor     edx, edx; dwFlags
0x18005b05c  mov     rcx, rax; hHeap
0x18005b05f  call    cs:__imp_HeapFree
0x18005b066  nop     dword ptr [rax+rax+00h]
0x18005b06b  jmp     short loc_18005B023
0x18005b06d  movzx   eax, word ptr [rbp+30h]
0x18005b071  xor     r9d, r9d; ApcContext
0x18005b074  mov     rcx, [rbp+28h]; FileHandle
0x18005b078  xor     r8d, r8d; ApcRoutine
0x18005b07b  mov     [rsp+78h+OutputBufferLength], 4; OutputBufferLength
0x18005b083  mov     rdx, rbx; Event
0x18005b086  mov     [rsp+78h+arg_14], eax
0x18005b08d  lea     rax, [rsp+78h+arg_0]
0x18005b095  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x18005b09a  lea     rax, [rsp+78h+arg_10]
0x18005b0a2  mov     [rsp+78h+InputBufferLength], 8; InputBufferLength
0x18005b0aa  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x18005b0af  lea     rax, [rsp+78h+var_28]
0x18005b0b4  mov     [rsp+78h+IoControlCode], 128024h; IoControlCode
0x18005b0bc  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x18005b0c1  mov     [rsp+78h+arg_10], 1
0x18005b0cc  call    cs:__imp_NtDeviceIoControlFile
0x18005b0d3  nop     dword ptr [rax+rax+00h]
0x18005b0d8  mov     esi, eax
0x18005b0da  cmp     eax, 103h
0x18005b0df  jnz     short loc_18005B0F7
0x18005b0e1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005b0e4  mov     rcx, rbx; hHandle
0x18005b0e7  call    cs:__imp_WaitForSingleObject
0x18005b0ee  nop     dword ptr [rax+rax+00h]
0x18005b0f3  mov     esi, dword ptr [rsp+78h+var_28]
0x18005b0f7  mov     rcx, rbx; hObject
0x18005b0fa  call    cs:__imp_CloseHandle
0x18005b101  nop     dword ptr [rax+rax+00h]
0x18005b106  test    esi, esi
0x18005b108  jns     short loc_18005B13A
0x18005b10a  call    cs:__imp_GetProcessHeap
0x18005b111  nop     dword ptr [rax+rax+00h]
0x18005b116  mov     r8, rdi; lpMem
0x18005b119  xor     edx, edx; dwFlags
0x18005b11b  mov     rcx, rax; hHeap
0x18005b11e  call    cs:__imp_HeapFree
0x18005b125  nop     dword ptr [rax+rax+00h]
0x18005b12a  mov     ecx, esi; Status
0x18005b12c  call    cs:__imp_RtlNtStatusToDosError
0x18005b133  nop     dword ptr [rax+rax+00h]
0x18005b138  jmp     short loc_18005B1B2
0x18005b13a  mov     eax, [rsp+78h+arg_0]
0x18005b141  lea     rdx, [rdi+28h]; BitMapBuffer
0x18005b145  mov     [rdi+10h], eax
0x18005b148  lea     rcx, [rdi+18h]; BitMapHeader
0x18005b14c  movzx   r8d, word ptr [rbp+30h]; SizeOfBitMap
0x18005b151  call    cs:__imp_RtlInitializeBitMap
0x18005b158  nop     dword ptr [rax+rax+00h]
0x18005b15d  lea     rcx, [rdi+18h]; BitMapHeader
0x18005b161  call    cs:__imp_RtlClearAllBits
0x18005b168  nop     dword ptr [rax+rax+00h]
0x18005b16d  add     rbp, 38h ; '8'
0x18005b171  mov     rax, [rbp+0]
0x18005b175  cmp     rax, rbp
0x18005b178  jz      short loc_18005B18A
0x18005b17a  mov     ecx, [rdi+10h]
0x18005b17d  cmp     ecx, [rax+10h]
0x18005b180  jbe     short loc_18005B18A
0x18005b182  mov     rax, [rax]
0x18005b185  cmp     rax, rbp
0x18005b188  jnz     short loc_18005B17D
0x18005b18a  mov     rcx, [rax+8]
0x18005b18e  cmp     [rcx], rax
0x18005b191  jz      short loc_18005B19A
0x18005b193  mov     ecx, 3
0x18005b198  int     29h; Win8: RtlFailFast(ecx)
0x18005b19a  mov     [rdi], rax
0x18005b19d  mov     [rdi+8], rcx
0x18005b1a1  mov     [rcx], rdi
0x18005b1a4  mov     [rax+8], rdi
0x18005b1a8  test    r14, r14
0x18005b1ab  jz      short loc_18005B1B0
0x18005b1ad  mov     [r14], rdi
0x18005b1b0  xor     eax, eax
0x18005b1b2  lea     r11, [rsp+78h+var_18]
0x18005b1b7  mov     rbx, [r11+28h]
0x18005b1bb  mov     rbp, [r11+38h]
0x18005b1bf  mov     rsp, r11
0x18005b1c2  pop     r14
0x18005b1c4  pop     rdi
0x18005b1c5  pop     rsi
0x18005b1c6  retn
```
