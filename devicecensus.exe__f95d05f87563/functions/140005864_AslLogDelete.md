# AslLogDelete

- ea: `0x140005864`
- end: `0x140005912`
- name: `AslLogDelete`
- size: `174`
- prototype: `BOOLEAN __fastcall(char *P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002524`
- `0x140004dd4`
- `0x1400119a0`

## callees

- `0x14000233f`
- `0x140005864`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x1400058ee`
- `ntdll!EtwEventUnregister` at `0x1400058ee`
- `ntdll!RtlFreeHeap` at `0x1400058a7`
- `ntdll!RtlFreeHeap` at `0x140005906`
- `ntdll!RtlFreeHeap` at `0x1400058a7`
- `ntdll!RtlFreeHeap` at `0x140005906`
- `ntdll!RtlDeleteCriticalSection` at `0x1400058c9`
- `ntdll!RtlDeleteCriticalSection` at `0x1400058c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005881`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140005881`

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
0x140005864  test    rcx, rcx
0x140005867  jz      locret_140005911
0x14000586d  push    rbx
0x14000586e  sub     rsp, 20h
0x140005872  mov     rbx, rcx
0x140005875  mov     rcx, [rcx+2D0h]; hLibModule
0x14000587c  test    rcx, rcx
0x14000587f  jz      short loc_140005892
0x140005881  call    cs:__imp_FreeLibrary
0x140005887  mov     qword ptr [rbx+2D0h], 0
0x140005892  mov     r8, [rbx+0B8h]; P
0x140005899  test    r8, r8
0x14000589c  jz      short loc_1400058AD
0x14000589e  mov     rcx, [rbx+90h]; HeapHandle
0x1400058a5  xor     edx, edx; Flags
0x1400058a7  call    cs:__imp_RtlFreeHeap
0x1400058ad  xorps   xmm0, xmm0
0x1400058b0  lea     rcx, [rbx+68h]; CriticalSection
0x1400058b4  movups  xmmword ptr [rbx+90h], xmm0
0x1400058bb  movups  xmmword ptr [rbx+0A0h], xmm0
0x1400058c2  movups  xmmword ptr [rbx+0B0h], xmm0
0x1400058c9  call    cs:__imp_RtlDeleteCriticalSection
0x1400058cf  mov     rcx, [rbx]; void *
0x1400058d2  test    rcx, rcx
0x1400058d5  jz      short loc_1400058E2
0x1400058d7  xor     edx, edx; Val
0x1400058d9  lea     r8d, [rdx+5Ch]; Size
0x1400058dd  call    memset_0
0x1400058e2  mov     rcx, [rbx+2C8h]
0x1400058e9  test    rcx, rcx
0x1400058ec  jz      short loc_1400058F4
0x1400058ee  call    cs:__imp_EtwEventUnregister
0x1400058f4  mov     rcx, gs:60h
0x1400058fd  mov     r8, rbx; P
0x140005900  xor     edx, edx; Flags
0x140005902  mov     rcx, [rcx+30h]; HeapHandle
0x140005906  call    cs:__imp_RtlFreeHeap
0x14000590c  add     rsp, 20h
0x140005910  pop     rbx
0x140005911  retn
```
