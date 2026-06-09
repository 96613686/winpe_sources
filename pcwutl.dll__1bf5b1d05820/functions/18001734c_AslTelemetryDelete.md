# AslTelemetryDelete

- ea: `0x18001734c`
- end: `0x18001749b`
- name: `AslTelemetryDelete`
- size: `335`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800171d0`
- `0x180019850`

## callees

- `0x18000b854`
- `0x18001734c`
- `0x1800174a4`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x180017394`
- `ADVAPI32!EventUnregister` at `0x180017394`
- `KERNEL32!HeapFree` at `0x18001740f`
- `KERNEL32!HeapFree` at `0x180017442`
- `KERNEL32!HeapFree` at `0x18001740f`
- `KERNEL32!HeapFree` at `0x180017442`
- `ntdll!RtlDeleteCriticalSection` at `0x18001746d`
- `ntdll!RtlDeleteCriticalSection` at `0x18001746d`
- `ntdll!RtlFreeHeap` at `0x180017485`
- `ntdll!RtlFreeHeap` at `0x180017485`

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
  v2 = _InterlockedExchangeAdd(&dword_1800268D0, 0xFFFFFFFF);
  if ( v2 == 1 )
  {
    v3 = RegHandle;
    dword_180026100 = 0;
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
0x18001734c  mov     [rsp+arg_8], rbx
0x180017351  mov     [rsp+arg_10], rsi
0x180017356  push    rdi
0x180017357  sub     rsp, 20h
0x18001735b  mov     rbx, rcx
0x18001735e  test    rcx, rcx
0x180017361  jz      short loc_180017368
0x180017363  call    AslTelemetryFlush
0x180017368  or      eax, 0FFFFFFFFh
0x18001736b  lock xadd cs:dword_1800268D0, eax
0x180017373  cmp     eax, 1
0x180017376  jnz     short loc_18001739A
0x180017378  mov     rcx, cs:RegHandle; RegHandle
0x18001737f  mov     cs:dword_180026100, 0
0x180017389  mov     cs:RegHandle, 0
0x180017394  call    cs:__imp_EventUnregister
0x18001739a  test    rbx, rbx
0x18001739d  jz      loc_18001748B
0x1800173a3  mov     rcx, [rbx+0C0h]
0x1800173aa  test    rcx, rcx
0x1800173ad  jz      short loc_1800173FA
0x1800173af  xor     esi, esi
0x1800173b1  xor     edi, edi
0x1800173b3  mov     eax, esi
0x1800173b5  cmp     rax, rcx
0x1800173b8  jnb     short loc_1800173D8
0x1800173ba  mul     qword ptr [rbx+0B8h]
0x1800173c1  test    rdx, rdx
0x1800173c4  jnz     short loc_1800173D6
0x1800173c6  mov     rcx, [rbx+0D8h]
0x1800173cd  lea     rdi, [rcx+rax]
0x1800173d1  cmp     rdi, rcx
0x1800173d4  jnb     short loc_1800173D8
0x1800173d6  xor     edi, edi
0x1800173d8  lea     rcx, [rdi+8]
0x1800173dc  call    AslAnsiStringFree
0x1800173e1  lea     rcx, [rdi+18h]
0x1800173e5  call    AslAnsiStringFree
0x1800173ea  mov     rcx, [rbx+0C0h]
0x1800173f1  inc     esi
0x1800173f3  mov     eax, esi
0x1800173f5  cmp     rax, rcx
0x1800173f8  jb      short loc_1800173B1
0x1800173fa  mov     r8, [rbx+0D8h]; lpMem
0x180017401  test    r8, r8
0x180017404  jz      short loc_180017415
0x180017406  mov     rcx, [rbx+0B0h]; hHeap
0x18001740d  xor     edx, edx; dwFlags
0x18001740f  call    cs:__imp_HeapFree
0x180017415  xorps   xmm0, xmm0
0x180017418  movups  xmmword ptr [rbx+0B0h], xmm0
0x18001741f  movups  xmmword ptr [rbx+0C0h], xmm0
0x180017426  movups  xmmword ptr [rbx+0D0h], xmm0
0x18001742d  mov     r8, [rbx+0A8h]; lpMem
0x180017434  test    r8, r8
0x180017437  jz      short loc_180017448
0x180017439  mov     rcx, [rbx+80h]; hHeap
0x180017440  xor     edx, edx; dwFlags
0x180017442  call    cs:__imp_HeapFree
0x180017448  xorps   xmm0, xmm0
0x18001744b  lea     rcx, [rbx+48h]
0x18001744f  movups  xmmword ptr [rbx+80h], xmm0
0x180017456  movups  xmmword ptr [rbx+90h], xmm0
0x18001745d  movups  xmmword ptr [rbx+0A0h], xmm0
0x180017464  call    AslAnsiStringFree
0x180017469  lea     rcx, [rbx+58h]; CriticalSection
0x18001746d  call    cs:__imp_RtlDeleteCriticalSection
0x180017473  mov     rcx, gs:60h
0x18001747c  mov     r8, rbx; P
0x18001747f  xor     edx, edx; Flags
0x180017481  mov     rcx, [rcx+30h]; HeapHandle
0x180017485  call    cs:__imp_RtlFreeHeap
0x18001748b  mov     rbx, [rsp+28h+arg_8]
0x180017490  mov     rsi, [rsp+28h+arg_10]
0x180017495  add     rsp, 20h
0x180017499  pop     rdi
0x18001749a  retn
```
