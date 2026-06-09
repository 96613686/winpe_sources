# AslTelemetryCreate

- ea: `0x1800171d0`
- end: `0x180017343`
- name: `AslTelemetryCreate`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180008628`

## callees

- `0x180001214`
- `0x18000b710`
- `0x18000e240`
- `0x1800156f8`
- `0x1800171d0`
- `0x18001734c`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180017280`
- `msvcrt!strcpy_s` at `0x180017280`
- `KERNEL32!GetProcessHeap` at `0x1800172de`
- `KERNEL32!GetProcessHeap` at `0x1800172de`
- `KERNEL32!HeapFree` at `0x1800172c0`
- `KERNEL32!HeapFree` at `0x1800172c0`
- `ntdll!RtlInitializeCriticalSection` at `0x18001724e`
- `ntdll!RtlInitializeCriticalSection` at `0x18001724e`
- `ntdll!RtlAllocateHeap` at `0x180017216`
- `ntdll!RtlAllocateHeap` at `0x180017216`

## string_xrefs

- `0x180017231`: `AslTelemetryCreate`

## pseudocode

```c
__int64 __fastcall AslTelemetryCreate(_QWORD *a1, const char *a2)
{
  char *Heap; // rax
  char *v5; // rbx
  int v6; // edi
  void *v7; // r8
  HANDLE ProcessHeap; // rax

  if ( _InterlockedIncrement(&dword_1800268D0) == 1 )
    TraceLoggingRegister_EventRegister_2U();
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xF8u);
  v5 = Heap;
  if ( Heap )
  {
    RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 88));
    *((_QWORD *)v5 + 28) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                          * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    strcpy_s(v5, 0x40u, a2);
    v6 = AslAnsiStringCreate((PANSI_STRING)(v5 + 72));
    if ( v6 < 0 || (v6 = RtlArray<_ASL_TELEMETRY_EVENT>::Initialize(v5 + 128), v6 < 0) )
    {
      AslTelemetryDelete(v5);
    }
    else
    {
      v7 = (void *)*((_QWORD *)v5 + 27);
      if ( v7 )
        HeapFree(*((HANDLE *)v5 + 22), 0, v7);
      *((_OWORD *)v5 + 11) = 0;
      *((_OWORD *)v5 + 12) = 0;
      *((_OWORD *)v5 + 13) = 0;
      ProcessHeap = GetProcessHeap();
      *((_QWORD *)v5 + 26) = 4;
      v6 = 0;
      *((_QWORD *)v5 + 22) = ProcessHeap;
      *((_QWORD *)v5 + 24) = 0;
      *((_QWORD *)v5 + 25) = 0;
      *((_QWORD *)v5 + 27) = 0;
      *((_QWORD *)v5 + 23) = 48;
      *a1 = v5;
    }
  }
  else
  {
    v6 = -1073741801;
    AslLogCallPrintf(1, "AslTelemetryCreate", 204, "Out of memory");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800171d0  mov     [rsp+arg_0], rbx
0x1800171d5  mov     [rsp+arg_8], rsi
0x1800171da  push    rdi
0x1800171db  sub     rsp, 20h
0x1800171df  mov     rdi, rdx
0x1800171e2  mov     rsi, rcx
0x1800171e5  mov     eax, 1
0x1800171ea  lock xadd cs:dword_1800268D0, eax
0x1800171f2  inc     eax
0x1800171f4  cmp     eax, 1
0x1800171f7  jnz     short loc_1800171FE
0x1800171f9  call    TraceLoggingRegister_EventRegister_2U
0x1800171fe  mov     rcx, gs:60h
0x180017207  mov     edx, 8; Flags
0x18001720c  mov     r8d, 0F8h; Size
0x180017212  mov     rcx, [rcx+30h]; HeapHandle
0x180017216  call    cs:__imp_RtlAllocateHeap
0x18001721c  mov     rbx, rax
0x18001721f  test    rax, rax
0x180017222  jnz     short loc_18001724A
0x180017224  lea     r9, aOutOfMemory; "Out of memory"
0x18001722b  mov     r8d, 0CCh
0x180017231  lea     rdx, aAsltelemetrycr; "AslTelemetryCreate"
0x180017238  mov     edi, 0C0000017h
0x18001723d  lea     ecx, [rax+1]
0x180017240  call    AslLogCallPrintf
0x180017245  jmp     loc_180017331
0x18001724a  lea     rcx, [rax+58h]; CriticalSection
0x18001724e  call    cs:__imp_RtlInitializeCriticalSection
0x180017254  mov     ecx, ds:7FFE0004h
0x18001725b  mov     eax, 7FFE0320h
0x180017260  shl     rcx, 20h
0x180017264  mov     r8, rdi; Source
0x180017267  mov     rax, [rax]
0x18001726a  shl     rax, 8
0x18001726e  mul     rcx
0x180017271  mov     rcx, rbx; Destination
0x180017274  mov     [rbx+0E0h], rdx
0x18001727b  mov     edx, 40h ; '@'; SizeInBytes
0x180017280  call    cs:__imp_strcpy_s
0x180017286  lea     rcx, [rbx+48h]; DestinationString
0x18001728a  call    AslAnsiStringCreate
0x18001728f  mov     edi, eax
0x180017291  test    eax, eax
0x180017293  js      loc_180017329
0x180017299  lea     rcx, [rbx+80h]
0x1800172a0  call    ?Initialize@?$RtlArray@U_ASL_TELEMETRY_EVENT@@@@QEAAJ_K0@Z; RtlArray<_ASL_TELEMETRY_EVENT>::Initialize(unsigned __int64,unsigned __int64)
0x1800172a5  mov     edi, eax
0x1800172a7  test    eax, eax
0x1800172a9  js      short loc_180017329
0x1800172ab  mov     r8, [rbx+0D8h]; lpMem
0x1800172b2  test    r8, r8
0x1800172b5  jz      short loc_1800172C6
0x1800172b7  mov     rcx, [rbx+0B0h]; hHeap
0x1800172be  xor     edx, edx; dwFlags
0x1800172c0  call    cs:__imp_HeapFree
0x1800172c6  xorps   xmm0, xmm0
0x1800172c9  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800172d0  movups  xmmword ptr [rbx+0C0h], xmm0
0x1800172d7  movups  xmmword ptr [rbx+0D0h], xmm0
0x1800172de  call    cs:__imp_GetProcessHeap
0x1800172e4  mov     qword ptr [rbx+0D0h], 4
0x1800172ef  xor     edi, edi
0x1800172f1  mov     [rbx+0B0h], rax
0x1800172f8  mov     qword ptr [rbx+0C0h], 0
0x180017303  mov     qword ptr [rbx+0C8h], 0
0x18001730e  mov     qword ptr [rbx+0D8h], 0
0x180017319  mov     qword ptr [rbx+0B8h], 30h ; '0'
0x180017324  mov     [rsi], rbx
0x180017327  jmp     short loc_180017331
0x180017329  mov     rcx, rbx; P
0x18001732c  call    AslTelemetryDelete
0x180017331  mov     rbx, [rsp+28h+arg_0]
0x180017336  mov     eax, edi
0x180017338  mov     rsi, [rsp+28h+arg_8]
0x18001733d  add     rsp, 20h
0x180017341  pop     rdi
0x180017342  retn
```
