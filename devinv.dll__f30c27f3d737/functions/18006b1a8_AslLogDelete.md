# AslLogDelete

- ea: `0x18006b1a8`
- end: `0x18006b256`
- name: `AslLogDelete`
- size: `174`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180060578`
- `0x18006a718`
- `0x180115660`

## callees

- `0x180006ec4`
- `0x18006b1a8`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18006b232`
- `ntdll!EtwEventUnregister` at `0x18006b232`
- `ntdll!RtlDeleteCriticalSection` at `0x18006b20d`
- `ntdll!RtlDeleteCriticalSection` at `0x18006b20d`
- `ntdll!RtlFreeHeap` at `0x18006b1eb`
- `ntdll!RtlFreeHeap` at `0x18006b24a`
- `ntdll!RtlFreeHeap` at `0x18006b1eb`
- `ntdll!RtlFreeHeap` at `0x18006b24a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b1c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b1c5`

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
0x18006b1a8  test    rcx, rcx
0x18006b1ab  jz      locret_18006B255
0x18006b1b1  push    rbx
0x18006b1b2  sub     rsp, 20h
0x18006b1b6  mov     rbx, rcx
0x18006b1b9  mov     rcx, [rcx+2D0h]; hLibModule
0x18006b1c0  test    rcx, rcx
0x18006b1c3  jz      short loc_18006B1D6
0x18006b1c5  call    cs:__imp_FreeLibrary
0x18006b1cb  mov     qword ptr [rbx+2D0h], 0
0x18006b1d6  mov     r8, [rbx+0B8h]; P
0x18006b1dd  test    r8, r8
0x18006b1e0  jz      short loc_18006B1F1
0x18006b1e2  mov     rcx, [rbx+90h]; HeapHandle
0x18006b1e9  xor     edx, edx; Flags
0x18006b1eb  call    cs:__imp_RtlFreeHeap
0x18006b1f1  xorps   xmm0, xmm0
0x18006b1f4  lea     rcx, [rbx+68h]; CriticalSection
0x18006b1f8  movups  xmmword ptr [rbx+90h], xmm0
0x18006b1ff  movups  xmmword ptr [rbx+0A0h], xmm0
0x18006b206  movups  xmmword ptr [rbx+0B0h], xmm0
0x18006b20d  call    cs:__imp_RtlDeleteCriticalSection
0x18006b213  mov     rcx, [rbx]; void *
0x18006b216  test    rcx, rcx
0x18006b219  jz      short loc_18006B226
0x18006b21b  xor     edx, edx; Val
0x18006b21d  lea     r8d, [rdx+5Ch]; Size
0x18006b221  call    memset_0
0x18006b226  mov     rcx, [rbx+2C8h]
0x18006b22d  test    rcx, rcx
0x18006b230  jz      short loc_18006B238
0x18006b232  call    cs:__imp_EtwEventUnregister
0x18006b238  mov     rcx, gs:60h
0x18006b241  mov     r8, rbx; P
0x18006b244  xor     edx, edx; Flags
0x18006b246  mov     rcx, [rcx+30h]; HeapHandle
0x18006b24a  call    cs:__imp_RtlFreeHeap
0x18006b250  add     rsp, 20h
0x18006b254  pop     rbx
0x18006b255  retn
```
