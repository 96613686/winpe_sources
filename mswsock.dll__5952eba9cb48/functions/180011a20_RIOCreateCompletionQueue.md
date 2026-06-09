# RIOCreateCompletionQueue

- ea: `0x180011a20`
- end: `0x180011cd5`
- name: `RIOCreateCompletionQueue`
- size: `693`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011a20`
- `0x1800222f0`
- `0x180022bd2`
- `0x18002819c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180011ba2`
- `ntdll!RtlFreeHeap` at `0x180011c7e`
- `ntdll!RtlFreeHeap` at `0x180011c96`
- `ntdll!RtlFreeHeap` at `0x180011ba2`
- `ntdll!RtlFreeHeap` at `0x180011c7e`
- `ntdll!RtlFreeHeap` at `0x180011c96`
- `ntdll!NtDeviceIoControlFile` at `0x180011c61`
- `ntdll!NtDeviceIoControlFile` at `0x180011c61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ad7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ca7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ad7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011ca7`

## pseudocode

```c
_DWORD *__fastcall RIOCreateCompletionQueue(int a1, __int64 a2)
{
  _DWORD *HeapRoutine; // rdi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  HANDLE RegDomain; // rax
  NTSTATUS v10; // eax
  int OutputBuffer; // [rsp+50h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-70h] BYREF
  __int128 InputBuffer; // [rsp+68h] [rbp-60h] BYREF
  __int128 v14; // [rsp+78h] [rbp-50h]
  __int128 v15; // [rsp+88h] [rbp-40h]
  __int64 v16; // [rsp+98h] [rbp-30h]

  OutputBuffer = 0;
  InputBuffer = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  IoStatusBlock = 0;
  if ( a2 )
  {
    if ( *(_DWORD *)a2 == 1 )
    {
      *(_QWORD *)&v14 = *(_QWORD *)(a2 + 8);
      v5 = *(int *)(a2 + 16);
      DWORD2(InputBuffer) = 1;
    }
    else
    {
      if ( *(_DWORD *)a2 != 2 )
        goto LABEL_3;
      v6 = *(_QWORD *)(a2 + 24);
      if ( !v6 )
        goto LABEL_3;
      *(_QWORD *)&v14 = *(_QWORD *)(a2 + 8);
      v5 = *(_QWORD *)(a2 + 16);
      *(_QWORD *)&v15 = v6;
      DWORD2(InputBuffer) = 2;
    }
    *((_QWORD *)&v14 + 1) = v5;
  }
  if ( (unsigned int)(a1 - 1) > 0x7FFFFFF )
  {
LABEL_3:
    SetLastError(0x2726u);
    return 0;
  }
  HeapRoutine = (_DWORD *)SockAllocateHeapRoutine(SockPrivateHeap, 0, 24);
  if ( !HeapRoutine )
  {
    SetLastError(0x2747u);
    return 0;
  }
  v7 = (unsigned int)(a1 + 1);
  v8 = SockAllocateHeapRoutine(SockPrivateHeap, 0, 24LL * (unsigned int)v7 + 16);
  *((_QWORD *)HeapRoutine + 2) = v8;
  if ( !v8 )
  {
    SetLastError(0x2747u);
    RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
    return 0;
  }
  *HeapRoutine = -1582119980;
  HeapRoutine[1] = v7;
  *(_BYTE *)(v8 + 8) = 0;
  **((_DWORD **)HeapRoutine + 2) = 0;
  *(_DWORD *)(*((_QWORD *)HeapRoutine + 2) + 4LL) = 0;
  memset_0((void *)(*((_QWORD *)HeapRoutine + 2) + 16LL), 0, 24 * v7);
  DWORD1(InputBuffer) = v7;
  DWORD2(v15) = 24 * v7 + 16;
  v16 = *((_QWORD *)HeapRoutine + 2);
  RegDomain = MswRioRegDomain;
  LODWORD(InputBuffer) = 0;
  if ( MswRioRegDomain == (HANDLE)-1LL )
    RegDomain = CreateRegDomain();
  v10 = NtDeviceIoControlFile(RegDomain, 0, 0, 0, &IoStatusBlock, 0x1211Bu, &InputBuffer, 0x38u, &OutputBuffer, 4u);
  if ( v10 < 0 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)HeapRoutine + 2));
    RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
    SetLastError(0x271Eu);
    return 0;
  }
  if ( v10 == 259 )
    __fastfail(0x3Eu);
  HeapRoutine[2] = OutputBuffer;
  return HeapRoutine;
}

```

## disassembly

```asm
0x180011a20  mov     r11, rsp
0x180011a23  push    rbx
0x180011a24  push    rbp
0x180011a25  sub     rsp, 0B8h
0x180011a2c  mov     rax, cs:__security_cookie
0x180011a33  xor     rax, rsp
0x180011a36  mov     [rsp+0C8h+var_28], rax
0x180011a3e  xorps   xmm1, xmm1
0x180011a41  xor     eax, eax
0x180011a43  xor     ebp, ebp
0x180011a45  xorps   xmm0, xmm0
0x180011a48  mov     [rsp+0C8h+var_78], ebp
0x180011a4c  mov     ebx, ecx
0x180011a4e  movups  [rsp+0C8h+var_60], xmm1
0x180011a53  movups  [rsp+0C8h+var_50], xmm1
0x180011a58  mov     [r11-30h], rax
0x180011a5c  movups  xmmword ptr [r11-40h], xmm1
0x180011a61  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x180011a66  test    rdx, rdx
0x180011a69  jnz     loc_180011AEF
0x180011a6f  lea     eax, [rbx-1]
0x180011a72  cmp     eax, 7FFFFFFh
0x180011a77  jbe     short loc_180011AA7
0x180011a79  mov     ecx, 2726h; dwErrCode
0x180011a7e  call    cs:__imp_SetLastError
0x180011a85  nop     dword ptr [rax+rax+00h]
0x180011a8a  xor     eax, eax
0x180011a8c  mov     rcx, [rsp+0C8h+var_28]
0x180011a94  xor     rcx, rsp; StackCookie
0x180011a97  call    __security_check_cookie
0x180011a9c  add     rsp, 0B8h
0x180011aa3  pop     rbp
0x180011aa4  pop     rbx
0x180011aa5  retn
0x180011aa7  mov     rcx, cs:SockPrivateHeap
0x180011aae  xor     edx, edx
0x180011ab0  mov     rax, cs:SockAllocateHeapRoutine
0x180011ab7  mov     r8d, 18h
0x180011abd  mov     [rsp+0C8h+var_18], rdi
0x180011ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aca  mov     rdi, rax
0x180011acd  test    rax, rax
0x180011ad0  jnz     short loc_180011B4D
0x180011ad2  mov     ecx, 2747h; dwErrCode
0x180011ad7  call    cs:__imp_SetLastError
0x180011ade  nop     dword ptr [rax+rax+00h]
0x180011ae3  xor     eax, eax
0x180011ae5  mov     rdi, [rsp+0C8h+var_18]
0x180011aed  jmp     short loc_180011A8C
0x180011aef  mov     ecx, [rdx]
0x180011af1  sub     ecx, 1
0x180011af4  jnz     short loc_180011B18
0x180011af6  mov     rax, [rdx+8]
0x180011afa  mov     qword ptr [rsp+0C8h+var_50], rax
0x180011aff  movsxd  rax, dword ptr [rdx+10h]
0x180011b03  mov     dword ptr [rsp+0C8h+var_60+8], 1
0x180011b0b  mov     qword ptr [rsp+0C8h+var_50+8], rax
0x180011b13  jmp     loc_180011A6F
0x180011b18  cmp     ecx, 1
0x180011b1b  jnz     loc_180011A79
0x180011b21  mov     rcx, [rdx+18h]
0x180011b25  test    rcx, rcx
0x180011b28  jz      loc_180011A79
0x180011b2e  mov     rax, [rdx+8]
0x180011b32  mov     qword ptr [rsp+0C8h+var_50], rax
0x180011b37  mov     rax, [rdx+10h]
0x180011b3b  mov     [rsp+0C8h+var_40], rcx
0x180011b43  mov     dword ptr [rsp+0C8h+var_60+8], 2
0x180011b4b  jmp     short loc_180011B0B
0x180011b4d  mov     rax, cs:SockAllocateHeapRoutine
0x180011b54  inc     ebx
0x180011b56  mov     [rsp+0C8h+arg_10], rsi
0x180011b5e  xor     edx, edx
0x180011b60  lea     rcx, [rbx+rbx*2]
0x180011b64  lea     rsi, ds:0[rcx*8]
0x180011b6c  mov     rcx, cs:SockPrivateHeap
0x180011b73  lea     r8, [rsi+10h]
0x180011b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7c  mov     [rdi+10h], rax
0x180011b80  test    rax, rax
0x180011b83  jnz     short loc_180011BBD
0x180011b85  mov     ecx, 2747h; dwErrCode
0x180011b8a  call    cs:__imp_SetLastError
0x180011b91  nop     dword ptr [rax+rax+00h]
0x180011b96  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180011b9d  mov     r8, rdi; P
0x180011ba0  xor     edx, edx; Flags
0x180011ba2  call    cs:__imp_RtlFreeHeap
0x180011ba9  nop     dword ptr [rax+rax+00h]
0x180011bae  xor     eax, eax
0x180011bb0  mov     rsi, [rsp+0C8h+arg_10]
0x180011bb8  jmp     loc_180011AE5
0x180011bbd  mov     dword ptr [rdi], 0A1B2C3D4h
0x180011bc3  mov     r8, rsi; Size
0x180011bc6  mov     [rdi+4], ebx
0x180011bc9  xor     edx, edx; Val
0x180011bcb  mov     [rax+8], bpl
0x180011bcf  mov     rax, [rdi+10h]
0x180011bd3  mov     [rax], ebp
0x180011bd5  mov     rax, [rdi+10h]
0x180011bd9  mov     [rax+4], ebp
0x180011bdc  mov     rcx, [rdi+10h]
0x180011be0  add     rcx, 10h; void *
0x180011be4  call    memset_0
0x180011be9  lea     eax, [rbx+rbx*2]
0x180011bec  mov     dword ptr [rsp+0C8h+var_60+4], ebx
0x180011bf0  lea     eax, ds:10h[rax*8]
0x180011bf7  mov     [rsp+0C8h+var_38], eax
0x180011bfe  mov     rax, [rdi+10h]
0x180011c02  mov     [rsp+0C8h+var_30], rax
0x180011c0a  mov     rax, cs:MswRioRegDomain
0x180011c11  mov     dword ptr [rsp+0C8h+var_60], ebp
0x180011c15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011c19  jnz     short loc_180011C20
0x180011c1b  call    CreateRegDomain
0x180011c20  mov     [rsp+0C8h+OutputBufferLength], 4; OutputBufferLength
0x180011c28  lea     rcx, [rsp+0C8h+var_78]
0x180011c2d  mov     [rsp+0C8h+OutputBuffer], rcx; OutputBuffer
0x180011c32  xor     r9d, r9d; ApcContext
0x180011c35  mov     [rsp+0C8h+InputBufferLength], 38h ; '8'; InputBufferLength
0x180011c3d  lea     rcx, [rsp+0C8h+var_60]
0x180011c42  mov     [rsp+0C8h+InputBuffer], rcx; InputBuffer
0x180011c47  xor     r8d, r8d; ApcRoutine
0x180011c4a  lea     rcx, [rsp+0C8h+var_70]
0x180011c4f  mov     [rsp+0C8h+IoControlCode], 1211Bh; IoControlCode
0x180011c57  mov     [rsp+0C8h+IoStatusBlock], rcx; IoStatusBlock
0x180011c5c  xor     edx, edx; Event
0x180011c5e  mov     rcx, rax; FileHandle
0x180011c61  call    cs:__imp_NtDeviceIoControlFile
0x180011c68  nop     dword ptr [rax+rax+00h]
0x180011c6d  test    eax, eax
0x180011c6f  jns     short loc_180011CB8
0x180011c71  mov     r8, [rdi+10h]; P
0x180011c75  xor     edx, edx; Flags
0x180011c77  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180011c7e  call    cs:__imp_RtlFreeHeap
0x180011c85  nop     dword ptr [rax+rax+00h]
0x180011c8a  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180011c91  mov     r8, rdi; P
0x180011c94  xor     edx, edx; Flags
0x180011c96  call    cs:__imp_RtlFreeHeap
0x180011c9d  nop     dword ptr [rax+rax+00h]
0x180011ca2  mov     ecx, 271Eh; dwErrCode
0x180011ca7  call    cs:__imp_SetLastError
0x180011cae  nop     dword ptr [rax+rax+00h]
0x180011cb3  jmp     loc_180011BAE
0x180011cb8  cmp     eax, 103h
0x180011cbd  jnz     short loc_180011CC6
0x180011cbf  mov     ecx, 3Eh ; '>'
0x180011cc4  int     29h; Win8: RtlFailFast(ecx)
0x180011cc6  mov     eax, [rsp+0C8h+var_78]
0x180011cca  mov     [rdi+8], eax
0x180011ccd  mov     rax, rdi
0x180011cd0  jmp     loc_180011BB0
```
