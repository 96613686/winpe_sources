# AslTelemetryDelete

- ea: `0x180169e60`
- end: `0x180169faf`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800a274c`
- `0x180169ce0`
- `0x18018cef0`

## callees

- `0x180168e94`
- `0x180169e60`
- `0x180169fb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180169f23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180169f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180169f23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180169f56`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180169ea8`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180169ea8`
- `ntdll!RtlDeleteCriticalSection` at `0x180169f81`
- `ntdll!RtlDeleteCriticalSection` at `0x180169f81`
- `ntdll!RtlFreeHeap` at `0x180169f99`
- `ntdll!RtlFreeHeap` at `0x180169f99`

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
  v2 = _InterlockedExchangeAdd(&dword_180200710, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = qword_1801FE450;
    dword_1801FE430 = 0;
    qword_1801FE450 = 0;
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
0x180169e60  mov     [rsp+arg_8], rbx
0x180169e65  mov     [rsp+arg_10], rsi
0x180169e6a  push    rdi
0x180169e6b  sub     rsp, 20h
0x180169e6f  mov     rbx, rcx
0x180169e72  test    rcx, rcx
0x180169e75  jz      short loc_180169E7C
0x180169e77  call    AslTelemetryFlush
0x180169e7c  or      eax, 0FFFFFFFFh
0x180169e7f  lock xadd cs:dword_180200710, eax
0x180169e87  cmp     eax, 1
0x180169e8a  jnz     short loc_180169EAE
0x180169e8c  mov     rcx, cs:qword_1801FE450; RegHandle
0x180169e93  mov     cs:dword_1801FE430, 0
0x180169e9d  mov     cs:qword_1801FE450, 0
0x180169ea8  call    cs:__imp_EventUnregister
0x180169eae  test    rbx, rbx
0x180169eb1  jz      loc_180169F9F
0x180169eb7  mov     rcx, [rbx+0C0h]
0x180169ebe  test    rcx, rcx
0x180169ec1  jz      short loc_180169F0E
0x180169ec3  xor     esi, esi
0x180169ec5  xor     edi, edi
0x180169ec7  mov     eax, esi
0x180169ec9  cmp     rax, rcx
0x180169ecc  jnb     short loc_180169EEC
0x180169ece  mul     qword ptr [rbx+0B8h]
0x180169ed5  test    rdx, rdx
0x180169ed8  jnz     short loc_180169EEA
0x180169eda  mov     rcx, [rbx+0D8h]
0x180169ee1  lea     rdi, [rcx+rax]
0x180169ee5  cmp     rdi, rcx
0x180169ee8  jnb     short loc_180169EEC
0x180169eea  xor     edi, edi
0x180169eec  lea     rcx, [rdi+8]
0x180169ef0  call    AslAnsiStringFree
0x180169ef5  lea     rcx, [rdi+18h]
0x180169ef9  call    AslAnsiStringFree
0x180169efe  mov     rcx, [rbx+0C0h]
0x180169f05  inc     esi
0x180169f07  mov     eax, esi
0x180169f09  cmp     rax, rcx
0x180169f0c  jb      short loc_180169EC5
0x180169f0e  mov     r8, [rbx+0D8h]; lpMem
0x180169f15  test    r8, r8
0x180169f18  jz      short loc_180169F29
0x180169f1a  mov     rcx, [rbx+0B0h]; hHeap
0x180169f21  xor     edx, edx; dwFlags
0x180169f23  call    cs:__imp_HeapFree
0x180169f29  xorps   xmm0, xmm0
0x180169f2c  movups  xmmword ptr [rbx+0B0h], xmm0
0x180169f33  movups  xmmword ptr [rbx+0C0h], xmm0
0x180169f3a  movups  xmmword ptr [rbx+0D0h], xmm0
0x180169f41  mov     r8, [rbx+0A8h]; lpMem
0x180169f48  test    r8, r8
0x180169f4b  jz      short loc_180169F5C
0x180169f4d  mov     rcx, [rbx+80h]; hHeap
0x180169f54  xor     edx, edx; dwFlags
0x180169f56  call    cs:__imp_HeapFree
0x180169f5c  xorps   xmm0, xmm0
0x180169f5f  lea     rcx, [rbx+48h]
0x180169f63  movups  xmmword ptr [rbx+80h], xmm0
0x180169f6a  movups  xmmword ptr [rbx+90h], xmm0
0x180169f71  movups  xmmword ptr [rbx+0A0h], xmm0
0x180169f78  call    AslAnsiStringFree
0x180169f7d  lea     rcx, [rbx+58h]; CriticalSection
0x180169f81  call    cs:__imp_RtlDeleteCriticalSection
0x180169f87  mov     rcx, gs:60h
0x180169f90  mov     r8, rbx; P
0x180169f93  xor     edx, edx; Flags
0x180169f95  mov     rcx, [rcx+30h]; HeapHandle
0x180169f99  call    cs:__imp_RtlFreeHeap
0x180169f9f  mov     rbx, [rsp+28h+arg_8]
0x180169fa4  mov     rsi, [rsp+28h+arg_10]
0x180169fa9  add     rsp, 20h
0x180169fad  pop     rdi
0x180169fae  retn
```
