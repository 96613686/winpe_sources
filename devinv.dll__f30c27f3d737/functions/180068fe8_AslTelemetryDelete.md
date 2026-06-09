# AslTelemetryDelete

- ea: `0x180068fe8`
- end: `0x180069137`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006059c`
- `0x180068e60`
- `0x180115660`

## callees

- `0x180067e64`
- `0x180068fe8`
- `0x180069140`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180069109`
- `ntdll!RtlDeleteCriticalSection` at `0x180069109`
- `ntdll!RtlFreeHeap` at `0x180069121`
- `ntdll!RtlFreeHeap` at `0x180069121`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800690ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800690de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800690ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800690de`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180069030`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180069030`

## pseudocode

```c
char __fastcall AslTelemetryDelete(char *P)
{
  signed __int32 v2; // eax
  REGHANDLE v3; // rcx
  unsigned __int64 v4; // rcx
  unsigned int i; // esi
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  void *v9; // r8
  void *v10; // r8

  if ( P )
    AslTelemetryFlush();
  v2 = _InterlockedExchangeAdd(&dword_180157A80, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_180155160 = 0;
    RegHandle = 0;
    LOBYTE(v2) = EventUnregister(v3);
  }
  if ( P )
  {
    v4 = *((_QWORD *)P + 24);
    if ( v4 )
    {
      for ( i = 0; i < v4; ++i )
      {
        v6 = 0;
        if ( i < v4 )
        {
          v7 = *((_QWORD *)P + 23) * i;
          if ( !is_mul_ok(*((_QWORD *)P + 23), i) || (v8 = *((_QWORD *)P + 27), v6 = v8 + v7, v8 + v7 < v8) )
            v6 = 0;
        }
        AslAnsiStringFree(v6 + 8);
        AslAnsiStringFree(v6 + 24);
        v4 = *((_QWORD *)P + 24);
      }
    }
    v9 = (void *)*((_QWORD *)P + 27);
    if ( v9 )
      HeapFree(*((HANDLE *)P + 22), 0, v9);
    *((_OWORD *)P + 11) = 0;
    *((_OWORD *)P + 12) = 0;
    *((_OWORD *)P + 13) = 0;
    v10 = (void *)*((_QWORD *)P + 21);
    if ( v10 )
      HeapFree(*((HANDLE *)P + 16), 0, v10);
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
0x180068fe8  mov     [rsp+arg_8], rbx
0x180068fed  mov     [rsp+arg_10], rsi
0x180068ff2  push    rdi
0x180068ff3  sub     rsp, 20h
0x180068ff7  mov     rbx, rcx
0x180068ffa  test    rcx, rcx
0x180068ffd  jz      short loc_180069004
0x180068fff  call    AslTelemetryFlush
0x180069004  or      eax, 0FFFFFFFFh
0x180069007  lock xadd cs:dword_180157A80, eax
0x18006900f  cmp     eax, 1
0x180069012  jnz     short loc_180069036
0x180069014  mov     rcx, cs:RegHandle; RegHandle
0x18006901b  mov     cs:dword_180155160, 0
0x180069025  mov     cs:RegHandle, 0
0x180069030  call    cs:__imp_EventUnregister
0x180069036  test    rbx, rbx
0x180069039  jz      loc_180069127
0x18006903f  mov     rcx, [rbx+0C0h]
0x180069046  test    rcx, rcx
0x180069049  jz      short loc_180069096
0x18006904b  xor     esi, esi
0x18006904d  xor     edi, edi
0x18006904f  mov     eax, esi
0x180069051  cmp     rax, rcx
0x180069054  jnb     short loc_180069074
0x180069056  mul     qword ptr [rbx+0B8h]
0x18006905d  test    rdx, rdx
0x180069060  jnz     short loc_180069072
0x180069062  mov     rcx, [rbx+0D8h]
0x180069069  lea     rdi, [rcx+rax]
0x18006906d  cmp     rdi, rcx
0x180069070  jnb     short loc_180069074
0x180069072  xor     edi, edi
0x180069074  lea     rcx, [rdi+8]
0x180069078  call    AslAnsiStringFree
0x18006907d  lea     rcx, [rdi+18h]
0x180069081  call    AslAnsiStringFree
0x180069086  mov     rcx, [rbx+0C0h]
0x18006908d  inc     esi
0x18006908f  mov     eax, esi
0x180069091  cmp     rax, rcx
0x180069094  jb      short loc_18006904D
0x180069096  mov     r8, [rbx+0D8h]; lpMem
0x18006909d  test    r8, r8
0x1800690a0  jz      short loc_1800690B1
0x1800690a2  mov     rcx, [rbx+0B0h]; hHeap
0x1800690a9  xor     edx, edx; dwFlags
0x1800690ab  call    cs:__imp_HeapFree
0x1800690b1  xorps   xmm0, xmm0
0x1800690b4  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800690bb  movups  xmmword ptr [rbx+0C0h], xmm0
0x1800690c2  movups  xmmword ptr [rbx+0D0h], xmm0
0x1800690c9  mov     r8, [rbx+0A8h]; lpMem
0x1800690d0  test    r8, r8
0x1800690d3  jz      short loc_1800690E4
0x1800690d5  mov     rcx, [rbx+80h]; hHeap
0x1800690dc  xor     edx, edx; dwFlags
0x1800690de  call    cs:__imp_HeapFree
0x1800690e4  xorps   xmm0, xmm0
0x1800690e7  lea     rcx, [rbx+48h]
0x1800690eb  movups  xmmword ptr [rbx+80h], xmm0
0x1800690f2  movups  xmmword ptr [rbx+90h], xmm0
0x1800690f9  movups  xmmword ptr [rbx+0A0h], xmm0
0x180069100  call    AslAnsiStringFree
0x180069105  lea     rcx, [rbx+58h]; CriticalSection
0x180069109  call    cs:__imp_RtlDeleteCriticalSection
0x18006910f  mov     rcx, gs:60h
0x180069118  mov     r8, rbx; P
0x18006911b  xor     edx, edx; Flags
0x18006911d  mov     rcx, [rcx+30h]; HeapHandle
0x180069121  call    cs:__imp_RtlFreeHeap
0x180069127  mov     rbx, [rsp+28h+arg_8]
0x18006912c  mov     rsi, [rsp+28h+arg_10]
0x180069131  add     rsp, 20h
0x180069135  pop     rdi
0x180069136  retn
```
