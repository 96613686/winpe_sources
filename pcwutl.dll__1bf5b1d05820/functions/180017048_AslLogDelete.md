# AslLogDelete

- ea: `0x180017048`
- end: `0x1800170f6`
- name: `AslLogDelete`
- size: `174`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016590`
- `0x180019850`

## callees

- `0x180017048`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001708b`
- `KERNEL32!HeapFree` at `0x18001708b`
- `KERNEL32!FreeLibrary` at `0x180017065`
- `KERNEL32!FreeLibrary` at `0x180017065`
- `ntdll!EtwEventUnregister` at `0x1800170d2`
- `ntdll!EtwEventUnregister` at `0x1800170d2`
- `ntdll!RtlDeleteCriticalSection` at `0x1800170ad`
- `ntdll!RtlDeleteCriticalSection` at `0x1800170ad`
- `ntdll!RtlFreeHeap` at `0x1800170ea`
- `ntdll!RtlFreeHeap` at `0x1800170ea`

## pseudocode

```c
BOOLEAN __fastcall AslLogDelete(char *P)
{
  HMODULE v2; // rcx
  void *v3; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v2 = (HMODULE)*((_QWORD *)P + 90);
    if ( v2 )
    {
      FreeLibrary(v2);
      *((_QWORD *)P + 90) = 0;
    }
    v3 = (void *)*((_QWORD *)P + 23);
    if ( v3 )
      HeapFree(*((HANDLE *)P + 18), 0, v3);
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    *((_OWORD *)P + 11) = 0;
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 104));
    if ( *(_QWORD *)P )
      memset_0(*(void **)P, 0, 0x5Cu);
    if ( *((_QWORD *)P + 89) )
      EtwEventUnregister();
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x180017048  test    rcx, rcx
0x18001704b  jz      locret_1800170F5
0x180017051  push    rbx
0x180017052  sub     rsp, 20h
0x180017056  mov     rbx, rcx
0x180017059  mov     rcx, [rcx+2D0h]; hLibModule
0x180017060  test    rcx, rcx
0x180017063  jz      short loc_180017076
0x180017065  call    cs:__imp_FreeLibrary
0x18001706b  mov     qword ptr [rbx+2D0h], 0
0x180017076  mov     r8, [rbx+0B8h]; lpMem
0x18001707d  test    r8, r8
0x180017080  jz      short loc_180017091
0x180017082  mov     rcx, [rbx+90h]; hHeap
0x180017089  xor     edx, edx; dwFlags
0x18001708b  call    cs:__imp_HeapFree
0x180017091  xorps   xmm0, xmm0
0x180017094  lea     rcx, [rbx+68h]; CriticalSection
0x180017098  movups  xmmword ptr [rbx+90h], xmm0
0x18001709f  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800170a6  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800170ad  call    cs:__imp_RtlDeleteCriticalSection
0x1800170b3  mov     rcx, [rbx]; void *
0x1800170b6  test    rcx, rcx
0x1800170b9  jz      short loc_1800170C6
0x1800170bb  xor     edx, edx; Val
0x1800170bd  lea     r8d, [rdx+5Ch]; Size
0x1800170c1  call    memset_0
0x1800170c6  mov     rcx, [rbx+2C8h]
0x1800170cd  test    rcx, rcx
0x1800170d0  jz      short loc_1800170D8
0x1800170d2  call    cs:__imp_EtwEventUnregister
0x1800170d8  mov     rcx, gs:60h
0x1800170e1  mov     r8, rbx; P
0x1800170e4  xor     edx, edx; Flags
0x1800170e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800170ea  call    cs:__imp_RtlFreeHeap
0x1800170f0  add     rsp, 20h
0x1800170f4  pop     rbx
0x1800170f5  retn
```
