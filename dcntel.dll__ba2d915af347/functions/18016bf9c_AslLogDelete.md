# AslLogDelete

- ea: `0x18016bf9c`
- end: `0x18016c049`
- name: `AslLogDelete`
- size: `173`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800a2728`
- `0x18016b51c`
- `0x18018cef0`

## callees

- `0x180009f14`
- `0x18000a1d0`
- `0x18016bf9c`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18016c025`
- `ntdll!EtwEventUnregister` at `0x18016c025`
- `ntdll!RtlDeleteCriticalSection` at `0x18016c000`
- `ntdll!RtlDeleteCriticalSection` at `0x18016c000`
- `ntdll!RtlFreeHeap` at `0x18016bfde`
- `ntdll!RtlFreeHeap` at `0x18016c03d`
- `ntdll!RtlFreeHeap` at `0x18016bfde`
- `ntdll!RtlFreeHeap` at `0x18016c03d`

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
      FreeLibrary_0(v2);
      *((_QWORD *)P + 90) = 0;
    }
    v3 = (void *)*((_QWORD *)P + 23);
    if ( v3 )
      RtlFreeHeap(*((HANDLE *)P + 18), 0, v3);
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
0x18016bf9c  test    rcx, rcx
0x18016bf9f  jz      locret_18016C048
0x18016bfa5  push    rbx
0x18016bfa6  sub     rsp, 20h
0x18016bfaa  mov     rbx, rcx
0x18016bfad  mov     rcx, [rcx+2D0h]; hLibModule
0x18016bfb4  test    rcx, rcx
0x18016bfb7  jz      short loc_18016BFC9
0x18016bfb9  call    FreeLibrary_0
0x18016bfbe  mov     qword ptr [rbx+2D0h], 0
0x18016bfc9  mov     r8, [rbx+0B8h]; P
0x18016bfd0  test    r8, r8
0x18016bfd3  jz      short loc_18016BFE4
0x18016bfd5  mov     rcx, [rbx+90h]; HeapHandle
0x18016bfdc  xor     edx, edx; Flags
0x18016bfde  call    cs:__imp_RtlFreeHeap
0x18016bfe4  xorps   xmm0, xmm0
0x18016bfe7  lea     rcx, [rbx+68h]; CriticalSection
0x18016bfeb  movups  xmmword ptr [rbx+90h], xmm0
0x18016bff2  movups  xmmword ptr [rbx+0A0h], xmm0
0x18016bff9  movups  xmmword ptr [rbx+0B0h], xmm0
0x18016c000  call    cs:__imp_RtlDeleteCriticalSection
0x18016c006  mov     rcx, [rbx]; void *
0x18016c009  test    rcx, rcx
0x18016c00c  jz      short loc_18016C019
0x18016c00e  xor     edx, edx; Val
0x18016c010  lea     r8d, [rdx+5Ch]; Size
0x18016c014  call    memset_0
0x18016c019  mov     rcx, [rbx+2C8h]
0x18016c020  test    rcx, rcx
0x18016c023  jz      short loc_18016C02B
0x18016c025  call    cs:__imp_EtwEventUnregister
0x18016c02b  mov     rcx, gs:60h
0x18016c034  mov     r8, rbx; P
0x18016c037  xor     edx, edx; Flags
0x18016c039  mov     rcx, [rcx+30h]; HeapHandle
0x18016c03d  call    cs:__imp_RtlFreeHeap
0x18016c043  add     rsp, 20h
0x18016c047  pop     rbx
0x18016c048  retn
```
