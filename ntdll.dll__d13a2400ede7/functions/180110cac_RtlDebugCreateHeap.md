# RtlDebugCreateHeap

- ea: `0x180110cac`
- end: `0x180110fa0`
- name: `RtlDebugCreateHeap`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180086bd4`

## callees

- `0x180007060`
- `0x180007cd0`
- `0x180059320`
- `0x180086bd4`
- `0x1800b32d4`
- `0x180110cac`
- `0x18015ef40`

## string_xrefs

- `0x180110d7f`: `Invalid CommitSize parameter - %Ix\n`

## pseudocode

```c
void *__fastcall RtlDebugCreateHeap(
        int a1,
        void *a2,
        unsigned __int64 a3,
        char *a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  int VirtualMemory; // r15d
  __int64 Heap; // rax
  void *v14; // rdi
  _OWORD v15[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v16; // [rsp+60h] [rbp-48h]

  memset(v15, 0, sizeof(v15));
  v16 = 0;
  if ( a3 <= 0x10 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("Invalid ReserveSize parameter - %Ix\n", a3);
LABEL_6:
    RtlpBreakPointHeap();
    return 0;
  }
  if ( a3 < (unsigned __int64)a4 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("Invalid CommitSize parameter - %Ix\n", a4);
    goto LABEL_6;
  }
  if ( (a1 & 1) != 0 && a5 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("May not specify Lock parameter with HEAP_NO_SERIALIZE\n");
    goto LABEL_6;
  }
  if ( a2 )
  {
    VirtualMemory = ZwQueryVirtualMemory(-1, a2, 0, v15, 48, 0);
    if ( VirtualMemory < 0 )
    {
      if ( NtCurrentPeb()->Ldr )
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
      else
        DbgPrint("HEAP: ");
      DbgPrint("Specified HeapBase (%p) invalid,  Status = %lx\n", a2, VirtualMemory);
      goto LABEL_6;
    }
    if ( *(void **)&v15[0] != a2 )
    {
      if ( NtCurrentPeb()->Ldr )
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
      else
        DbgPrint("HEAP: ");
      DbgPrint("Specified HeapBase (%p) != to BaseAddress (%p)\n", a2, *(const void **)&v15[0]);
      goto LABEL_6;
    }
    if ( (_DWORD)v16 == 0x10000 )
    {
      if ( NtCurrentPeb()->Ldr )
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
      else
        DbgPrint("HEAP: ");
      DbgPrint("Specified HeapBase (%p) is free or not writable\n", *(_QWORD *)&v15[0]);
      goto LABEL_6;
    }
  }
  Heap = RtlpCreateHeap(a1 | 0x10000060u, a2, a3, a4, a5, a6, a7);
  v14 = (void *)Heap;
  if ( Heap )
  {
    if ( (*(_DWORD *)(Heap + 112) & 0x8000000) != 0 )
      *(_WORD *)(Heap + 304) = RtlLogStackBackTraceEx(1);
    RtlpValidateHeapHeaders(v14);
  }
  return v14;
}

```

## disassembly

```asm
0x180110cac  push    rbp
0x180110cae  push    rsi
0x180110caf  push    rdi
0x180110cb0  push    r12
0x180110cb2  push    r14
0x180110cb4  push    r15
0x180110cb6  sub     rsp, 78h
0x180110cba  xorps   xmm0, xmm0
0x180110cbd  mov     rbp, r9
0x180110cc0  mov     rsi, r8
0x180110cc3  mov     rdi, rdx
0x180110cc6  mov     r14d, ecx
0x180110cc9  movups  [rsp+0A8h+var_68], xmm0
0x180110cce  movups  [rsp+0A8h+var_58], xmm0
0x180110cd3  movups  [rsp+0A8h+var_48], xmm0
0x180110cd8  cmp     r8, 10h
0x180110cdc  ja      short loc_180110D38
0x180110cde  mov     rax, gs:60h
0x180110ce7  cmp     qword ptr [rax+18h], 0
0x180110cec  jz      short loc_180110D11
0x180110cee  mov     rax, gs:60h
0x180110cf7  mov     rcx, [rax+18h]
0x180110cfb  mov     rdx, [rcx+10h]
0x180110cff  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180110d06  add     rdx, 58h ; 'X'
0x180110d0a  call    DbgPrint
0x180110d0f  jmp     short loc_180110D1D
0x180110d11  lea     rcx, aHeap; "HEAP: "
0x180110d18  call    DbgPrint
0x180110d1d  mov     rdx, rsi
0x180110d20  lea     rcx, aInvalidReserve; "Invalid ReserveSize parameter - %Ix\n"
0x180110d27  call    DbgPrint
0x180110d2c  call    RtlpBreakPointHeap
0x180110d31  xor     eax, eax
0x180110d33  jmp     loc_180110F91
0x180110d38  cmp     rsi, rbp
0x180110d3b  jnb     short loc_180110D88
0x180110d3d  mov     rax, gs:60h
0x180110d46  cmp     qword ptr [rax+18h], 0
0x180110d4b  jz      short loc_180110D70
0x180110d4d  mov     rax, gs:60h
0x180110d56  mov     rcx, [rax+18h]
0x180110d5a  mov     rdx, [rcx+10h]
0x180110d5e  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180110d65  add     rdx, 58h ; 'X'
0x180110d69  call    DbgPrint
0x180110d6e  jmp     short loc_180110D7C
0x180110d70  lea     rcx, aHeap; "HEAP: "
0x180110d77  call    DbgPrint
0x180110d7c  mov     rdx, rbp
0x180110d7f  lea     rcx, aInvalidCommits; "Invalid CommitSize parameter - %Ix\n"
0x180110d86  jmp     short loc_180110D27
0x180110d88  mov     r12, [rsp+0A8h+arg_20]
0x180110d90  test    r14b, 1
0x180110d94  jz      short loc_180110DEB
0x180110d96  test    r12, r12
0x180110d99  jz      short loc_180110DEB
0x180110d9b  mov     rax, gs:60h
0x180110da4  cmp     qword ptr [rax+18h], 0
0x180110da9  jz      short loc_180110DCE
0x180110dab  mov     rax, gs:60h
0x180110db4  mov     rcx, [rax+18h]
0x180110db8  mov     rdx, [rcx+10h]
0x180110dbc  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180110dc3  add     rdx, 58h ; 'X'
0x180110dc7  call    DbgPrint
0x180110dcc  jmp     short loc_180110DDA
0x180110dce  lea     rcx, aHeap; "HEAP: "
0x180110dd5  call    DbgPrint
0x180110dda  lea     rcx, aMayNotSpecifyL; "May not specify Lock parameter with HEA"...
0x180110de1  call    DbgPrint
0x180110de6  jmp     loc_180110D2C
0x180110deb  test    rdi, rdi
0x180110dee  jz      loc_180110F2D
0x180110df4  mov     [rsp+0A8h+var_80], 0
0x180110dfd  lea     r9, [rsp+0A8h+var_68]
0x180110e02  xor     r8d, r8d
0x180110e05  mov     [rsp+0A8h+var_88], 30h ; '0'
0x180110e0e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180110e12  call    ZwQueryVirtualMemory
0x180110e17  mov     r15d, eax
0x180110e1a  test    eax, eax
0x180110e1c  jns     short loc_180110E74
0x180110e1e  mov     rcx, gs:60h
0x180110e27  cmp     qword ptr [rcx+18h], 0
0x180110e2c  jz      short loc_180110E51
0x180110e2e  mov     rcx, gs:60h
0x180110e37  mov     rdx, [rcx+18h]
0x180110e3b  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180110e42  mov     rdx, [rdx+10h]
0x180110e46  add     rdx, 58h ; 'X'
0x180110e4a  call    DbgPrint
0x180110e4f  jmp     short loc_180110E5D
0x180110e51  lea     rcx, aHeap; "HEAP: "
0x180110e58  call    DbgPrint
0x180110e5d  mov     r8d, r15d
0x180110e60  lea     rcx, aSpecifiedHeapb_0; "Specified HeapBase (%p) invalid,  Statu"...
0x180110e67  mov     rdx, rdi
0x180110e6a  call    DbgPrint
0x180110e6f  jmp     loc_180110D2C
0x180110e74  cmp     qword ptr [rsp+0A8h+var_68], rdi
0x180110e79  jz      short loc_180110ED3
0x180110e7b  mov     rax, gs:60h
0x180110e84  cmp     qword ptr [rax+18h], 0
0x180110e89  jz      short loc_180110EAE
0x180110e8b  mov     rax, gs:60h
0x180110e94  mov     rcx, [rax+18h]
0x180110e98  mov     rdx, [rcx+10h]
0x180110e9c  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180110ea3  add     rdx, 58h ; 'X'
0x180110ea7  call    DbgPrint
0x180110eac  jmp     short loc_180110EBA
0x180110eae  lea     rcx, aHeap; "HEAP: "
0x180110eb5  call    DbgPrint
0x180110eba  mov     r8, qword ptr [rsp+0A8h+var_68]
0x180110ebf  lea     rcx, aSpecifiedHeapb; "Specified HeapBase (%p) != to BaseAddre"...
0x180110ec6  mov     rdx, rdi
0x180110ec9  call    DbgPrint
0x180110ece  jmp     loc_180110D2C
0x180110ed3  cmp     dword ptr [rsp+0A8h+var_48], 10000h
0x180110edb  jnz     short loc_180110F2D
0x180110edd  mov     rax, gs:60h
0x180110ee6  cmp     qword ptr [rax+18h], 0
0x180110eeb  jz      short loc_180110F10
0x180110eed  mov     rax, gs:60h
0x180110ef6  mov     rcx, [rax+18h]
0x180110efa  mov     rdx, [rcx+10h]
0x180110efe  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180110f05  add     rdx, 58h ; 'X'
0x180110f09  call    DbgPrint
0x180110f0e  jmp     short loc_180110F1C
0x180110f10  lea     rcx, aHeap; "HEAP: "
0x180110f17  call    DbgPrint
0x180110f1c  mov     rdx, qword ptr [rsp+0A8h+var_68]
0x180110f21  lea     rcx, aSpecifiedHeapb_1; "Specified HeapBase (%p) is free or not "...
0x180110f28  jmp     loc_180110D27
0x180110f2d  mov     eax, [rsp+0A8h+arg_30]
0x180110f34  or      r14d, 10000060h
0x180110f3b  mov     [rsp+0A8h+var_78], eax
0x180110f3f  mov     r9, rbp
0x180110f42  mov     rax, [rsp+0A8h+arg_28]
0x180110f4a  mov     r8, rsi
0x180110f4d  mov     [rsp+0A8h+var_80], rax
0x180110f52  mov     rdx, rdi
0x180110f55  mov     ecx, r14d
0x180110f58  mov     [rsp+0A8h+var_88], r12
0x180110f5d  call    RtlpCreateHeap
0x180110f62  mov     rdi, rax
0x180110f65  test    rax, rax
0x180110f68  jz      short loc_180110F8E
0x180110f6a  test    dword ptr [rax+70h], 8000000h
0x180110f71  jz      short loc_180110F84
0x180110f73  mov     ecx, 1
0x180110f78  call    RtlLogStackBackTraceEx
0x180110f7d  mov     [rdi+130h], ax
0x180110f84  mov     dl, 1
0x180110f86  mov     rcx, rdi; Src
0x180110f89  call    RtlpValidateHeapHeaders
0x180110f8e  mov     rax, rdi
0x180110f91  add     rsp, 78h
0x180110f95  pop     r15
0x180110f97  pop     r14
0x180110f99  pop     r12
0x180110f9b  pop     rdi
0x180110f9c  pop     rsi
0x180110f9d  pop     rbp
0x180110f9e  retn
```
