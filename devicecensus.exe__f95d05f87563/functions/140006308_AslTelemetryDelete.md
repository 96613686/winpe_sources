# AslTelemetryDelete

- ea: `0x140006308`
- end: `0x140006457`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `char __fastcall(char *P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140002554`
- `0x1400060c0`
- `0x1400119a0`

## callees

- `0x140006308`
- `0x140006460`
- `0x140009648`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400063cb`
- `ntdll!RtlFreeHeap` at `0x1400063fe`
- `ntdll!RtlFreeHeap` at `0x140006441`
- `ntdll!RtlFreeHeap` at `0x1400063cb`
- `ntdll!RtlFreeHeap` at `0x1400063fe`
- `ntdll!RtlFreeHeap` at `0x140006441`
- `ntdll!RtlDeleteCriticalSection` at `0x140006429`
- `ntdll!RtlDeleteCriticalSection` at `0x140006429`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140006350`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140006350`

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
  v2 = _InterlockedExchangeAdd(&dword_14001C908, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_14001C000 = 0;
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
      RtlFreeHeap(*((HANDLE *)P + 22), 0, v9);
    *((_OWORD *)P + 11) = 0;
    *((_OWORD *)P + 12) = 0;
    *((_OWORD *)P + 13) = 0;
    v10 = (void *)*((_QWORD *)P + 21);
    if ( v10 )
      RtlFreeHeap(*((HANDLE *)P + 16), 0, v10);
    *((_OWORD *)P + 8) = 0;
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    AslAnsiStringFree((__int64)(P + 72));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 88));
    LOBYTE(v2) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return v2;
}

```

## disassembly

```asm
0x140006308  mov     [rsp+arg_8], rbx
0x14000630d  mov     [rsp+arg_10], rsi
0x140006312  push    rdi
0x140006313  sub     rsp, 20h
0x140006317  mov     rbx, rcx
0x14000631a  test    rcx, rcx
0x14000631d  jz      short loc_140006324
0x14000631f  call    AslTelemetryFlush
0x140006324  or      eax, 0FFFFFFFFh
0x140006327  lock xadd cs:dword_14001C908, eax
0x14000632f  cmp     eax, 1
0x140006332  jnz     short loc_140006356
0x140006334  mov     rcx, cs:RegHandle; RegHandle
0x14000633b  mov     cs:dword_14001C000, 0
0x140006345  mov     cs:RegHandle, 0
0x140006350  call    cs:__imp_EventUnregister
0x140006356  test    rbx, rbx
0x140006359  jz      loc_140006447
0x14000635f  mov     rcx, [rbx+0C0h]
0x140006366  test    rcx, rcx
0x140006369  jz      short loc_1400063B6
0x14000636b  xor     esi, esi
0x14000636d  xor     edi, edi
0x14000636f  mov     eax, esi
0x140006371  cmp     rax, rcx
0x140006374  jnb     short loc_140006394
0x140006376  mul     qword ptr [rbx+0B8h]
0x14000637d  test    rdx, rdx
0x140006380  jnz     short loc_140006392
0x140006382  mov     rcx, [rbx+0D8h]
0x140006389  lea     rdi, [rcx+rax]
0x14000638d  cmp     rdi, rcx
0x140006390  jnb     short loc_140006394
0x140006392  xor     edi, edi
0x140006394  lea     rcx, [rdi+8]
0x140006398  call    AslAnsiStringFree
0x14000639d  lea     rcx, [rdi+18h]
0x1400063a1  call    AslAnsiStringFree
0x1400063a6  mov     rcx, [rbx+0C0h]
0x1400063ad  inc     esi
0x1400063af  mov     eax, esi
0x1400063b1  cmp     rax, rcx
0x1400063b4  jb      short loc_14000636D
0x1400063b6  mov     r8, [rbx+0D8h]; P
0x1400063bd  test    r8, r8
0x1400063c0  jz      short loc_1400063D1
0x1400063c2  mov     rcx, [rbx+0B0h]; HeapHandle
0x1400063c9  xor     edx, edx; Flags
0x1400063cb  call    cs:__imp_RtlFreeHeap
0x1400063d1  xorps   xmm0, xmm0
0x1400063d4  movups  xmmword ptr [rbx+0B0h], xmm0
0x1400063db  movups  xmmword ptr [rbx+0C0h], xmm0
0x1400063e2  movups  xmmword ptr [rbx+0D0h], xmm0
0x1400063e9  mov     r8, [rbx+0A8h]; P
0x1400063f0  test    r8, r8
0x1400063f3  jz      short loc_140006404
0x1400063f5  mov     rcx, [rbx+80h]; HeapHandle
0x1400063fc  xor     edx, edx; Flags
0x1400063fe  call    cs:__imp_RtlFreeHeap
0x140006404  xorps   xmm0, xmm0
0x140006407  lea     rcx, [rbx+48h]
0x14000640b  movups  xmmword ptr [rbx+80h], xmm0
0x140006412  movups  xmmword ptr [rbx+90h], xmm0
0x140006419  movups  xmmword ptr [rbx+0A0h], xmm0
0x140006420  call    AslAnsiStringFree
0x140006425  lea     rcx, [rbx+58h]; CriticalSection
0x140006429  call    cs:__imp_RtlDeleteCriticalSection
0x14000642f  mov     rcx, gs:60h
0x140006438  mov     r8, rbx; P
0x14000643b  xor     edx, edx; Flags
0x14000643d  mov     rcx, [rcx+30h]; HeapHandle
0x140006441  call    cs:__imp_RtlFreeHeap
0x140006447  mov     rbx, [rsp+28h+arg_8]
0x14000644c  mov     rsi, [rsp+28h+arg_10]
0x140006451  add     rsp, 20h
0x140006455  pop     rdi
0x140006456  retn
```
