# AslTelemetryCreate

- ea: `0x1400060c0`
- end: `0x140006302`
- name: `AslTelemetryCreate`
- size: `578`
- prototype: `__int64 __fastcall(_QWORD *, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140002844`

## callees

- `0x140001214`
- `0x14000233f`
- `0x1400060c0`
- `0x140006308`
- `0x140007074`
- `0x140009504`

## import_xrefs

- `msvcrt!strcpy_s` at `0x140006175`
- `msvcrt!strcpy_s` at `0x140006175`
- `ntdll!RtlFreeHeap` at `0x1400061a3`
- `ntdll!RtlFreeHeap` at `0x14000625f`
- `ntdll!RtlFreeHeap` at `0x140006296`
- `ntdll!RtlFreeHeap` at `0x1400061a3`
- `ntdll!RtlFreeHeap` at `0x14000625f`
- `ntdll!RtlFreeHeap` at `0x140006296`
- `ntdll!RtlInitializeCriticalSection` at `0x140006141`
- `ntdll!RtlInitializeCriticalSection` at `0x140006141`
- `ntdll!RtlAllocateHeap` at `0x14000610a`
- `ntdll!RtlAllocateHeap` at `0x140006213`
- `ntdll!RtlAllocateHeap` at `0x14000610a`
- `ntdll!RtlAllocateHeap` at `0x140006213`

## string_xrefs

- `0x140006125`: `AslTelemetryCreate`

## pseudocode

```c
__int64 __fastcall AslTelemetryCreate(_QWORD *a1, const char *a2)
{
  char *Heap; // rax
  char *v5; // rbx
  unsigned int v6; // edi
  void *v7; // r8
  PVOID ProcessHeap; // r9
  PVOID v9; // rax
  PVOID v10; // rdi
  void *v11; // r8
  void *v12; // r8

  if ( _InterlockedIncrement(&dword_14001C908) == 1 )
    TraceLoggingRegister_EventRegister_2U();
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xF8u);
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    AslLogCallPrintf(1, "AslTelemetryCreate", 204, "Out of memory");
    return v6;
  }
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 88));
  *((_QWORD *)v5 + 28) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                        * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  strcpy_s(v5, 0x40u, a2);
  v6 = AslAnsiStringCreate((PANSI_STRING)(v5 + 72));
  if ( (v6 & 0x80000000) != 0 )
  {
LABEL_20:
    AslTelemetryDelete(v5);
    return v6;
  }
  v7 = (void *)*((_QWORD *)v5 + 21);
  if ( v7 )
    RtlFreeHeap(*((HANDLE *)v5 + 16), 0, v7);
  *((_OWORD *)v5 + 8) = 0;
  *((_OWORD *)v5 + 9) = 0;
  *((_OWORD *)v5 + 10) = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v5 + 16) = ProcessHeap;
  *((_QWORD *)v5 + 20) = 64;
  *((_QWORD *)v5 + 17) = 72;
  if ( !is_mul_ok(0, 0x48u) || !is_mul_ok(0x40u, 0x48u) )
  {
    v6 = -1073741675;
    goto LABEL_14;
  }
  v9 = RtlAllocateHeap(ProcessHeap, (0x40 * (unsigned __int128)0x48u) >> 64, 0x1200u);
  v10 = v9;
  if ( !v9 )
  {
    v6 = -1073741801;
LABEL_14:
    v11 = (void *)*((_QWORD *)v5 + 21);
    if ( v11 )
      RtlFreeHeap(*((HANDLE *)v5 + 16), 0, v11);
    *((_OWORD *)v5 + 8) = 0;
    *((_OWORD *)v5 + 9) = 0;
    *((_OWORD *)v5 + 10) = 0;
    goto LABEL_20;
  }
  memset_0(v9, 0, 0x1200u);
  *((_QWORD *)v5 + 21) = v10;
  *((_QWORD *)v5 + 19) = 64;
  v12 = (void *)*((_QWORD *)v5 + 27);
  if ( v12 )
    RtlFreeHeap(*((HANDLE *)v5 + 22), 0, v12);
  v6 = 0;
  *((_OWORD *)v5 + 11) = 0;
  *((_OWORD *)v5 + 12) = 0;
  *((_OWORD *)v5 + 13) = 0;
  *((_QWORD *)v5 + 22) = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v5 + 26) = 4;
  *((_QWORD *)v5 + 23) = 48;
  *a1 = v5;
  return v6;
}

```

## disassembly

```asm
0x1400060c0  mov     [rsp+arg_0], rbx
0x1400060c5  mov     [rsp+arg_8], rbp
0x1400060ca  push    rsi
0x1400060cb  push    rdi
0x1400060cc  push    r14
0x1400060ce  sub     rsp, 20h
0x1400060d2  mov     esi, 1
0x1400060d7  mov     rdi, rdx
0x1400060da  mov     eax, esi
0x1400060dc  mov     r14, rcx
0x1400060df  lock xadd cs:dword_14001C908, eax
0x1400060e7  add     eax, esi
0x1400060e9  cmp     eax, esi
0x1400060eb  jnz     short loc_1400060F2
0x1400060ed  call    TraceLoggingRegister_EventRegister_2U
0x1400060f2  mov     rcx, gs:60h
0x1400060fb  mov     edx, 8; Flags
0x140006100  mov     r8d, 0F8h; Size
0x140006106  mov     rcx, [rcx+30h]; HeapHandle
0x14000610a  call    cs:__imp_RtlAllocateHeap
0x140006110  mov     rbx, rax
0x140006113  test    rax, rax
0x140006116  jnz     short loc_14000613D
0x140006118  lea     r9, aOutOfMemory; "Out of memory"
0x14000611f  mov     r8d, 0CCh
0x140006125  lea     rdx, aAsltelemetrycr; "AslTelemetryCreate"
0x14000612c  mov     ecx, esi
0x14000612e  mov     edi, 0C0000017h
0x140006133  call    AslLogCallPrintf
0x140006138  jmp     loc_1400062ED
0x14000613d  lea     rcx, [rax+58h]; CriticalSection
0x140006141  call    cs:__imp_RtlInitializeCriticalSection
0x140006147  mov     ecx, ds:7FFE0004h
0x14000614e  mov     eax, 7FFE0320h
0x140006153  shl     rcx, 20h
0x140006157  mov     ebp, 40h ; '@'
0x14000615c  mov     r8, rdi; Source
0x14000615f  mov     rax, [rax]
0x140006162  shl     rax, 8
0x140006166  mul     rcx
0x140006169  mov     rcx, rbx; Destination
0x14000616c  mov     [rbx+0E0h], rdx
0x140006173  mov     edx, ebp; SizeInBytes
0x140006175  call    cs:__imp_strcpy_s
0x14000617b  lea     rcx, [rbx+48h]; DestinationString
0x14000617f  call    AslAnsiStringCreate
0x140006184  mov     edi, eax
0x140006186  test    eax, eax
0x140006188  js      loc_1400062E5
0x14000618e  mov     r8, [rbx+0A8h]; P
0x140006195  test    r8, r8
0x140006198  jz      short loc_1400061A9
0x14000619a  mov     rcx, [rbx+80h]; HeapHandle
0x1400061a1  xor     edx, edx; Flags
0x1400061a3  call    cs:__imp_RtlFreeHeap
0x1400061a9  xorps   xmm0, xmm0
0x1400061ac  mov     [rsp+38h+arg_10], 0
0x1400061b5  movups  xmmword ptr [rbx+80h], xmm0
0x1400061bc  mov     r8d, 48h ; 'H'
0x1400061c2  xor     ecx, ecx
0x1400061c4  movups  xmmword ptr [rbx+90h], xmm0
0x1400061cb  movups  xmmword ptr [rbx+0A0h], xmm0
0x1400061d2  mov     rax, gs:60h
0x1400061db  mov     r9, [rax+30h]
0x1400061df  mov     eax, r8d
0x1400061e2  mul     rcx
0x1400061e5  mov     [rbx+80h], r9
0x1400061ec  mov     [rbx+0A0h], rbp
0x1400061f3  mov     [rbx+88h], r8
0x1400061fa  test    rdx, rdx
0x1400061fd  jnz     short loc_140006245
0x1400061ff  mov     eax, r8d
0x140006202  mul     rbp
0x140006205  mov     rsi, rax
0x140006208  test    rdx, rdx
0x14000620b  jnz     short loc_140006245
0x14000620d  mov     r8, rax; Size
0x140006210  mov     rcx, r9; HeapHandle
0x140006213  call    cs:__imp_RtlAllocateHeap
0x140006219  mov     rdi, rax
0x14000621c  test    rax, rax
0x14000621f  jz      short loc_14000623E
0x140006221  mov     r8, rsi; Size
0x140006224  xor     edx, edx; Val
0x140006226  mov     rcx, rax; void *
0x140006229  call    memset_0
0x14000622e  mov     [rbx+0A8h], rdi
0x140006235  mov     [rbx+98h], rbp
0x14000623c  jmp     short loc_140006281
0x14000623e  mov     edi, 0C0000017h
0x140006243  jmp     short loc_14000624A
0x140006245  mov     edi, 0C0000095h
0x14000624a  mov     r8, [rbx+0A8h]; P
0x140006251  test    r8, r8
0x140006254  jz      short loc_140006265
0x140006256  mov     rcx, [rbx+80h]; HeapHandle
0x14000625d  xor     edx, edx; Flags
0x14000625f  call    cs:__imp_RtlFreeHeap
0x140006265  xorps   xmm0, xmm0
0x140006268  movups  xmmword ptr [rbx+80h], xmm0
0x14000626f  movups  xmmword ptr [rbx+90h], xmm0
0x140006276  movups  xmmword ptr [rbx+0A0h], xmm0
0x14000627d  test    edi, edi
0x14000627f  js      short loc_1400062E5
0x140006281  mov     r8, [rbx+0D8h]; P
0x140006288  test    r8, r8
0x14000628b  jz      short loc_14000629C
0x14000628d  mov     rcx, [rbx+0B0h]; HeapHandle
0x140006294  xor     edx, edx; Flags
0x140006296  call    cs:__imp_RtlFreeHeap
0x14000629c  xorps   xmm0, xmm0
0x14000629f  xor     edi, edi
0x1400062a1  movups  xmmword ptr [rbx+0B0h], xmm0
0x1400062a8  movups  xmmword ptr [rbx+0C0h], xmm0
0x1400062af  movups  xmmword ptr [rbx+0D0h], xmm0
0x1400062b6  mov     rax, gs:60h
0x1400062bf  mov     rcx, [rax+30h]
0x1400062c3  mov     [rbx+0B0h], rcx
0x1400062ca  mov     qword ptr [rbx+0D0h], 4
0x1400062d5  mov     qword ptr [rbx+0B8h], 30h ; '0'
0x1400062e0  mov     [r14], rbx
0x1400062e3  jmp     short loc_1400062ED
0x1400062e5  mov     rcx, rbx; P
0x1400062e8  call    AslTelemetryDelete
0x1400062ed  mov     rbx, [rsp+38h+arg_0]
0x1400062f2  mov     eax, edi
0x1400062f4  mov     rbp, [rsp+38h+arg_8]
0x1400062f9  add     rsp, 20h
0x1400062fd  pop     r14
0x1400062ff  pop     rdi
0x140006300  pop     rsi
0x140006301  retn
```
