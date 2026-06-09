# RtlDebugCreateHeap

- ea: `0x18010f94c`
- end: `0x18010fc40`
- name: `RtlDebugCreateHeap`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006a124`

## callees

- `0x180007060`
- `0x180007cd0`
- `0x18006a124`
- `0x180079980`
- `0x1800aa904`
- `0x18010f94c`
- `0x18015e730`

## string_xrefs

- `0x18010fa1f`: `Invalid CommitSize parameter - %Ix\n`

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
0x18010f94c  push    rbp
0x18010f94e  push    rsi
0x18010f94f  push    rdi
0x18010f950  push    r12
0x18010f952  push    r14
0x18010f954  push    r15
0x18010f956  sub     rsp, 78h
0x18010f95a  xorps   xmm0, xmm0
0x18010f95d  mov     rbp, r9
0x18010f960  mov     rsi, r8
0x18010f963  mov     rdi, rdx
0x18010f966  mov     r14d, ecx
0x18010f969  movups  [rsp+0A8h+var_68], xmm0
0x18010f96e  movups  [rsp+0A8h+var_58], xmm0
0x18010f973  movups  [rsp+0A8h+var_48], xmm0
0x18010f978  cmp     r8, 10h
0x18010f97c  ja      short loc_18010F9D8
0x18010f97e  mov     rax, gs:60h
0x18010f987  cmp     qword ptr [rax+18h], 0
0x18010f98c  jz      short loc_18010F9B1
0x18010f98e  mov     rax, gs:60h
0x18010f997  mov     rcx, [rax+18h]
0x18010f99b  mov     rdx, [rcx+10h]
0x18010f99f  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x18010f9a6  add     rdx, 58h ; 'X'
0x18010f9aa  call    DbgPrint
0x18010f9af  jmp     short loc_18010F9BD
0x18010f9b1  lea     rcx, aHeap; "HEAP: "
0x18010f9b8  call    DbgPrint
0x18010f9bd  mov     rdx, rsi
0x18010f9c0  lea     rcx, aInvalidReserve; "Invalid ReserveSize parameter - %Ix\n"
0x18010f9c7  call    DbgPrint
0x18010f9cc  call    RtlpBreakPointHeap
0x18010f9d1  xor     eax, eax
0x18010f9d3  jmp     loc_18010FC31
0x18010f9d8  cmp     rsi, rbp
0x18010f9db  jnb     short loc_18010FA28
0x18010f9dd  mov     rax, gs:60h
0x18010f9e6  cmp     qword ptr [rax+18h], 0
0x18010f9eb  jz      short loc_18010FA10
0x18010f9ed  mov     rax, gs:60h
0x18010f9f6  mov     rcx, [rax+18h]
0x18010f9fa  mov     rdx, [rcx+10h]
0x18010f9fe  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x18010fa05  add     rdx, 58h ; 'X'
0x18010fa09  call    DbgPrint
0x18010fa0e  jmp     short loc_18010FA1C
0x18010fa10  lea     rcx, aHeap; "HEAP: "
0x18010fa17  call    DbgPrint
0x18010fa1c  mov     rdx, rbp
0x18010fa1f  lea     rcx, aInvalidCommits; "Invalid CommitSize parameter - %Ix\n"
0x18010fa26  jmp     short loc_18010F9C7
0x18010fa28  mov     r12, [rsp+0A8h+arg_20]
0x18010fa30  test    r14b, 1
0x18010fa34  jz      short loc_18010FA8B
0x18010fa36  test    r12, r12
0x18010fa39  jz      short loc_18010FA8B
0x18010fa3b  mov     rax, gs:60h
0x18010fa44  cmp     qword ptr [rax+18h], 0
0x18010fa49  jz      short loc_18010FA6E
0x18010fa4b  mov     rax, gs:60h
0x18010fa54  mov     rcx, [rax+18h]
0x18010fa58  mov     rdx, [rcx+10h]
0x18010fa5c  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x18010fa63  add     rdx, 58h ; 'X'
0x18010fa67  call    DbgPrint
0x18010fa6c  jmp     short loc_18010FA7A
0x18010fa6e  lea     rcx, aHeap; "HEAP: "
0x18010fa75  call    DbgPrint
0x18010fa7a  lea     rcx, aMayNotSpecifyL; "May not specify Lock parameter with HEA"...
0x18010fa81  call    DbgPrint
0x18010fa86  jmp     loc_18010F9CC
0x18010fa8b  test    rdi, rdi
0x18010fa8e  jz      loc_18010FBCD
0x18010fa94  mov     [rsp+0A8h+var_80], 0
0x18010fa9d  lea     r9, [rsp+0A8h+var_68]
0x18010faa2  xor     r8d, r8d
0x18010faa5  mov     [rsp+0A8h+var_88], 30h ; '0'
0x18010faae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010fab2  call    ZwQueryVirtualMemory
0x18010fab7  mov     r15d, eax
0x18010faba  test    eax, eax
0x18010fabc  jns     short loc_18010FB14
0x18010fabe  mov     rcx, gs:60h
0x18010fac7  cmp     qword ptr [rcx+18h], 0
0x18010facc  jz      short loc_18010FAF1
0x18010face  mov     rcx, gs:60h
0x18010fad7  mov     rdx, [rcx+18h]
0x18010fadb  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x18010fae2  mov     rdx, [rdx+10h]
0x18010fae6  add     rdx, 58h ; 'X'
0x18010faea  call    DbgPrint
0x18010faef  jmp     short loc_18010FAFD
0x18010faf1  lea     rcx, aHeap; "HEAP: "
0x18010faf8  call    DbgPrint
0x18010fafd  mov     r8d, r15d
0x18010fb00  lea     rcx, aSpecifiedHeapb_0; "Specified HeapBase (%p) invalid,  Statu"...
0x18010fb07  mov     rdx, rdi
0x18010fb0a  call    DbgPrint
0x18010fb0f  jmp     loc_18010F9CC
0x18010fb14  cmp     qword ptr [rsp+0A8h+var_68], rdi
0x18010fb19  jz      short loc_18010FB73
0x18010fb1b  mov     rax, gs:60h
0x18010fb24  cmp     qword ptr [rax+18h], 0
0x18010fb29  jz      short loc_18010FB4E
0x18010fb2b  mov     rax, gs:60h
0x18010fb34  mov     rcx, [rax+18h]
0x18010fb38  mov     rdx, [rcx+10h]
0x18010fb3c  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x18010fb43  add     rdx, 58h ; 'X'
0x18010fb47  call    DbgPrint
0x18010fb4c  jmp     short loc_18010FB5A
0x18010fb4e  lea     rcx, aHeap; "HEAP: "
0x18010fb55  call    DbgPrint
0x18010fb5a  mov     r8, qword ptr [rsp+0A8h+var_68]
0x18010fb5f  lea     rcx, aSpecifiedHeapb; "Specified HeapBase (%p) != to BaseAddre"...
0x18010fb66  mov     rdx, rdi
0x18010fb69  call    DbgPrint
0x18010fb6e  jmp     loc_18010F9CC
0x18010fb73  cmp     dword ptr [rsp+0A8h+var_48], 10000h
0x18010fb7b  jnz     short loc_18010FBCD
0x18010fb7d  mov     rax, gs:60h
0x18010fb86  cmp     qword ptr [rax+18h], 0
0x18010fb8b  jz      short loc_18010FBB0
0x18010fb8d  mov     rax, gs:60h
0x18010fb96  mov     rcx, [rax+18h]
0x18010fb9a  mov     rdx, [rcx+10h]
0x18010fb9e  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x18010fba5  add     rdx, 58h ; 'X'
0x18010fba9  call    DbgPrint
0x18010fbae  jmp     short loc_18010FBBC
0x18010fbb0  lea     rcx, aHeap; "HEAP: "
0x18010fbb7  call    DbgPrint
0x18010fbbc  mov     rdx, qword ptr [rsp+0A8h+var_68]
0x18010fbc1  lea     rcx, aSpecifiedHeapb_1; "Specified HeapBase (%p) is free or not "...
0x18010fbc8  jmp     loc_18010F9C7
0x18010fbcd  mov     eax, [rsp+0A8h+arg_30]
0x18010fbd4  or      r14d, 10000060h
0x18010fbdb  mov     [rsp+0A8h+var_78], eax
0x18010fbdf  mov     r9, rbp
0x18010fbe2  mov     rax, [rsp+0A8h+arg_28]
0x18010fbea  mov     r8, rsi
0x18010fbed  mov     [rsp+0A8h+var_80], rax
0x18010fbf2  mov     rdx, rdi
0x18010fbf5  mov     ecx, r14d
0x18010fbf8  mov     [rsp+0A8h+var_88], r12
0x18010fbfd  call    RtlpCreateHeap
0x18010fc02  mov     rdi, rax
0x18010fc05  test    rax, rax
0x18010fc08  jz      short loc_18010FC2E
0x18010fc0a  test    dword ptr [rax+70h], 8000000h
0x18010fc11  jz      short loc_18010FC24
0x18010fc13  mov     ecx, 1
0x18010fc18  call    RtlLogStackBackTraceEx
0x18010fc1d  mov     [rdi+130h], ax
0x18010fc24  mov     dl, 1
0x18010fc26  mov     rcx, rdi; Src
0x18010fc29  call    RtlpValidateHeapHeaders
0x18010fc2e  mov     rax, rdi
0x18010fc31  add     rsp, 78h
0x18010fc35  pop     r15
0x18010fc37  pop     r14
0x18010fc39  pop     r12
0x18010fc3b  pop     rdi
0x18010fc3c  pop     rsi
0x18010fc3d  pop     rbp
0x18010fc3e  retn
```
