# AslLogDelete

- ea: `0x180013ad0`
- end: `0x180013b7d`
- name: `AslLogDelete`
- size: `173`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007808`
- `0x18001304c`
- `0x1800d0920`

## callees

- `0x1800038b8`
- `0x180003ad0`
- `0x180013ad0`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180013b59`
- `ntdll!EtwEventUnregister` at `0x180013b59`
- `ntdll!RtlFreeHeap` at `0x180013b12`
- `ntdll!RtlFreeHeap` at `0x180013b71`
- `ntdll!RtlFreeHeap` at `0x180013b12`
- `ntdll!RtlFreeHeap` at `0x180013b71`
- `ntdll!RtlDeleteCriticalSection` at `0x180013b34`
- `ntdll!RtlDeleteCriticalSection` at `0x180013b34`

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
0x180013ad0  test    rcx, rcx
0x180013ad3  jz      locret_180013B7C
0x180013ad9  push    rbx
0x180013ada  sub     rsp, 20h
0x180013ade  mov     rbx, rcx
0x180013ae1  mov     rcx, [rcx+2D0h]; hLibModule
0x180013ae8  test    rcx, rcx
0x180013aeb  jz      short loc_180013AFD
0x180013aed  call    FreeLibrary_0
0x180013af2  mov     qword ptr [rbx+2D0h], 0
0x180013afd  mov     r8, [rbx+0B8h]; P
0x180013b04  test    r8, r8
0x180013b07  jz      short loc_180013B18
0x180013b09  mov     rcx, [rbx+90h]; HeapHandle
0x180013b10  xor     edx, edx; Flags
0x180013b12  call    cs:__imp_RtlFreeHeap
0x180013b18  xorps   xmm0, xmm0
0x180013b1b  lea     rcx, [rbx+68h]; CriticalSection
0x180013b1f  movups  xmmword ptr [rbx+90h], xmm0
0x180013b26  movups  xmmword ptr [rbx+0A0h], xmm0
0x180013b2d  movups  xmmword ptr [rbx+0B0h], xmm0
0x180013b34  call    cs:__imp_RtlDeleteCriticalSection
0x180013b3a  mov     rcx, [rbx]; void *
0x180013b3d  test    rcx, rcx
0x180013b40  jz      short loc_180013B4D
0x180013b42  xor     edx, edx; Val
0x180013b44  lea     r8d, [rdx+5Ch]; Size
0x180013b48  call    memset_0
0x180013b4d  mov     rcx, [rbx+2C8h]
0x180013b54  test    rcx, rcx
0x180013b57  jz      short loc_180013B5F
0x180013b59  call    cs:__imp_EtwEventUnregister
0x180013b5f  mov     rcx, gs:60h
0x180013b68  mov     r8, rbx; P
0x180013b6b  xor     edx, edx; Flags
0x180013b6d  mov     rcx, [rcx+30h]; HeapHandle
0x180013b71  call    cs:__imp_RtlFreeHeap
0x180013b77  add     rsp, 20h
0x180013b7b  pop     rbx
0x180013b7c  retn
```
