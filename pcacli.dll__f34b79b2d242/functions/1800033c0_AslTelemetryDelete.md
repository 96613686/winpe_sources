# AslTelemetryDelete

- ea: `0x1800033c0`
- end: `0x180003527`
- name: `AslTelemetryDelete`
- size: `359`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003290`
- `0x1800050e0`

## callees

- `0x1800033c0`
- `0x180003530`
- `0x180003560`
- `0x180005334`
- `0x180007010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180003464`
- `ntdll!RtlDeleteCriticalSection` at `0x180003464`
- `ntdll!RtlFreeHeap` at `0x18000347c`
- `ntdll!RtlFreeHeap` at `0x18000347c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003508`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000351c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003508`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000351c`

## pseudocode

```c
char __fastcall AslTelemetryDelete(char *P)
{
  signed __int32 v2; // eax
  unsigned __int64 v3; // rcx
  void *v4; // r8
  void *v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned int i; // esi
  unsigned __int64 v9; // rcx
  unsigned __int64 v11; // [rsp+30h] [rbp+8h] BYREF

  if ( P )
    AslTelemetryFlush();
  v2 = _InterlockedExchangeAdd(&dword_180014828, 0xFFFFFFFF);
  if ( v2 == 1 )
    LOBYTE(v2) = TraceLoggingUnregister_EventUnregister();
  if ( P )
  {
    v3 = *((_QWORD *)P + 24);
    if ( v3 )
    {
      for ( i = 0; i < v3; ++i )
      {
        v7 = 0;
        if ( i < v3 )
        {
          v9 = *((_QWORD *)P + 23);
          v11 = 0;
          if ( (int)ULongLongMult(v9, i, &v11) < 0 || (v6 = *((_QWORD *)P + 27), v7 = v6 + v11, v6 + v11 < v6) )
            v7 = 0;
        }
        AslAnsiStringFree(v7 + 8);
        AslAnsiStringFree(v7 + 24);
        v3 = *((_QWORD *)P + 24);
      }
    }
    v4 = (void *)*((_QWORD *)P + 27);
    if ( v4 )
      HeapFree(*((HANDLE *)P + 22), 0, v4);
    *((_OWORD *)P + 11) = 0;
    *((_OWORD *)P + 12) = 0;
    *((_OWORD *)P + 13) = 0;
    v5 = (void *)*((_QWORD *)P + 21);
    if ( v5 )
      HeapFree(*((HANDLE *)P + 16), 0, v5);
    *((_OWORD *)P + 8) = 0;
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    AslAnsiStringFree(P + 72);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 88));
    LOBYTE(v2) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return v2;
}

```

## disassembly

```asm
0x1800033c0  push    rbx
0x1800033c2  sub     rsp, 20h
0x1800033c6  mov     rbx, rcx
0x1800033c9  test    rcx, rcx
0x1800033cc  jnz     short loc_1800033F0
0x1800033ce  mov     eax, 0FFFFFFFFh
0x1800033d3  lock xadd cs:dword_180014828, eax
0x1800033db  cmp     eax, 1
0x1800033de  jnz     short loc_1800033E5
0x1800033e0  call    TraceLoggingUnregister_EventUnregister
0x1800033e5  test    rbx, rbx
0x1800033e8  jnz     short loc_1800033F7
0x1800033ea  add     rsp, 20h
0x1800033ee  pop     rbx
0x1800033ef  retn
0x1800033f0  call    AslTelemetryFlush
0x1800033f5  jmp     short loc_1800033CE
0x1800033f7  mov     rcx, [rbx+0C0h]
0x1800033fe  test    rcx, rcx
0x180003401  jnz     loc_1800034CE
0x180003407  mov     r8, [rbx+0D8h]; lpMem
0x18000340e  test    r8, r8
0x180003411  jnz     loc_1800034FF
0x180003417  xorps   xmm0, xmm0
0x18000341a  movups  xmmword ptr [rbx+0B0h], xmm0
0x180003421  movups  xmmword ptr [rbx+0C0h], xmm0
0x180003428  movups  xmmword ptr [rbx+0D0h], xmm0
0x18000342f  mov     r8, [rbx+0A8h]; lpMem
0x180003436  test    r8, r8
0x180003439  jnz     loc_180003513
0x18000343f  xorps   xmm0, xmm0
0x180003442  lea     rcx, [rbx+48h]
0x180003446  movups  xmmword ptr [rbx+80h], xmm0
0x18000344d  movups  xmmword ptr [rbx+90h], xmm0
0x180003454  movups  xmmword ptr [rbx+0A0h], xmm0
0x18000345b  call    AslAnsiStringFree
0x180003460  lea     rcx, [rbx+58h]; CriticalSection
0x180003464  call    cs:__imp_RtlDeleteCriticalSection
0x18000346a  mov     rcx, gs:60h
0x180003473  mov     r8, rbx; P
0x180003476  xor     edx, edx; Flags
0x180003478  mov     rcx, [rcx+30h]; HeapHandle
0x18000347c  call    cs:__imp_RtlFreeHeap
0x180003482  jmp     loc_1800033EA
0x180003487  mov     rcx, [rbx+0D8h]
0x18000348e  mov     rdi, [rsp+28h+arg_0]
0x180003493  add     rdi, rcx
0x180003496  cmp     rdi, rcx
0x180003499  jnb     short loc_18000349D
0x18000349b  xor     edi, edi
0x18000349d  lea     rcx, [rdi+8]
0x1800034a1  call    AslAnsiStringFree
0x1800034a6  lea     rcx, [rdi+18h]
0x1800034aa  call    AslAnsiStringFree
0x1800034af  mov     rcx, [rbx+0C0h]
0x1800034b6  inc     esi
0x1800034b8  mov     eax, esi
0x1800034ba  cmp     rax, rcx
0x1800034bd  jb      short loc_1800034DA
0x1800034bf  mov     rdi, [rsp+28h+arg_10]
0x1800034c4  mov     rsi, [rsp+28h+arg_8]
0x1800034c9  jmp     loc_180003407
0x1800034ce  mov     [rsp+28h+arg_8], rsi
0x1800034d3  xor     esi, esi
0x1800034d5  mov     [rsp+28h+arg_10], rdi
0x1800034da  xor     edi, edi
0x1800034dc  mov     edx, esi; unsigned __int64
0x1800034de  cmp     rdx, rcx
0x1800034e1  jnb     short loc_18000349D
0x1800034e3  mov     rcx, [rbx+0B8h]; unsigned __int64
0x1800034ea  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x1800034ef  mov     [rsp+28h+arg_0], rdi
0x1800034f4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800034f9  test    eax, eax
0x1800034fb  js      short loc_18000349B
0x1800034fd  jmp     short loc_180003487
0x1800034ff  mov     rcx, [rbx+0B0h]; hHeap
0x180003506  xor     edx, edx; dwFlags
0x180003508  call    cs:__imp_HeapFree
0x18000350e  jmp     loc_180003417
0x180003513  mov     rcx, [rbx+80h]; hHeap
0x18000351a  xor     edx, edx; dwFlags
0x18000351c  call    cs:__imp_HeapFree
0x180003522  jmp     loc_18000343F
```
