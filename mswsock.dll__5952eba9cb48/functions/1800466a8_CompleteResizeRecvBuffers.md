# CompleteResizeRecvBuffers

- ea: `0x1800466a8`
- end: `0x18004677b`
- name: `CompleteResizeRecvBuffers`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180049eac`

## callees

- `0x180038118`
- `0x18003dae8`
- `0x1800466a8`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004670b`
- `ntdll!RtlFreeHeap` at `0x180046727`
- `ntdll!RtlFreeHeap` at `0x18004670b`
- `ntdll!RtlFreeHeap` at `0x180046727`

## pseudocode

```c
__int64 __fastcall CompleteResizeRecvBuffers(__int64 a1)
{
  int v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  if ( (BYTE3(xmmword_180063D60) & 1) != 0 )
    WPP_SF_q(1048, 59, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, a1);
  (*(void (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)(a1 + 16) + 312LL))(
    *(_QWORD *)(a1 + 104),
    *(_QWORD *)(a1 + 856),
    &v3);
  RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(a1 + 864));
  RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(a1 + 872));
  *(_QWORD *)(a1 + 864) = 0;
  *(_QWORD *)(a1 + 872) = 0;
  return SendControlMessage((PVOID)a1, 0, 0);
}

```

## disassembly

```asm
0x1800466a8  push    rbx
0x1800466aa  sub     rsp, 30h
0x1800466ae  mov     rbx, rcx
0x1800466b1  mov     [rsp+38h+arg_0], 0
0x1800466b9  test    byte ptr cs:xmmword_180063D60+3, 1
0x1800466c0  jz      short loc_1800466DB
0x1800466c2  mov     edx, 3Bh ; ';'
0x1800466c7  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800466ce  mov     ecx, 418h
0x1800466d3  mov     r9, rbx
0x1800466d6  call    WPP_SF_q
0x1800466db  mov     rax, [rbx+10h]
0x1800466df  lea     r8, [rsp+38h+arg_0]
0x1800466e4  mov     rdx, [rbx+358h]
0x1800466eb  mov     rcx, [rbx+68h]
0x1800466ef  mov     rax, [rax+138h]
0x1800466f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800466fb  mov     r8, [rbx+360h]; P
0x180046702  xor     edx, edx; Flags
0x180046704  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004670b  call    cs:__imp_RtlFreeHeap
0x180046712  nop     dword ptr [rax+rax+00h]
0x180046717  mov     r8, [rbx+368h]; P
0x18004671e  xor     edx, edx; Flags
0x180046720  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180046727  call    cs:__imp_RtlFreeHeap
0x18004672e  nop     dword ptr [rax+rax+00h]
0x180046733  movzx   r8d, word ptr [rbx+348h]
0x18004673b  xor     r9d, r9d
0x18004673e  add     r8, 28h ; '('
0x180046742  mov     [rsp+38h+var_10], 0
0x18004674b  mov     dl, 12h
0x18004674d  mov     qword ptr [rbx+360h], 0
0x180046758  mov     rcx, rbx
0x18004675b  mov     qword ptr [rbx+368h], 0
0x180046766  mov     [rsp+38h+var_18], 0
0x18004676f  call    SendControlMessage
0x180046774  add     rsp, 30h
0x180046778  pop     rbx
0x180046779  retn
```
