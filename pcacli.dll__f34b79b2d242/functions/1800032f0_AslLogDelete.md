# AslLogDelete

- ea: `0x1800032f0`
- end: `0x1800033ba`
- name: `AslLogDelete`
- size: `202`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003290`
- `0x180004790`

## callees

- `0x1800032f0`
- `0x180008286`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180003339`
- `ntdll!RtlDeleteCriticalSection` at `0x180003339`
- `ntdll!EtwEventUnregister` at `0x18000336d`
- `ntdll!EtwEventUnregister` at `0x18000336d`
- `ntdll!RtlFreeHeap` at `0x180003385`
- `ntdll!RtlFreeHeap` at `0x180003385`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000339a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000339a`

## pseudocode

```c
void __fastcall AslLogDelete(char *P)
{
  HMODULE v2; // rcx
  void *v3; // r8
  _OWORD *v4; // rax

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
      HeapFree(*((HANDLE *)P + 18), 0, v3);
    *((_OWORD *)P + 9) = 0;
    *((_OWORD *)P + 10) = 0;
    *((_OWORD *)P + 11) = 0;
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 104));
    v4 = *(_OWORD **)P;
    if ( *(_QWORD *)P )
    {
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = 0;
      *(_OWORD *)((char *)v4 + 76) = 0;
    }
    if ( *((_QWORD *)P + 89) )
      EtwEventUnregister();
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
}

```

## disassembly

```asm
0x1800032f0  test    rcx, rcx
0x1800032f3  jz      locret_180003390
0x1800032f9  push    rbx
0x1800032fa  sub     rsp, 20h
0x1800032fe  mov     rbx, rcx
0x180003301  mov     rcx, [rcx+2D0h]; hLibModule
0x180003308  test    rcx, rcx
0x18000330b  jnz     loc_1800033A5
0x180003311  mov     r8, [rbx+0B8h]; lpMem
0x180003318  test    r8, r8
0x18000331b  jnz     short loc_180003391
0x18000331d  xorps   xmm0, xmm0
0x180003320  lea     rcx, [rbx+68h]; CriticalSection
0x180003324  movups  xmmword ptr [rbx+90h], xmm0
0x18000332b  movups  xmmword ptr [rbx+0A0h], xmm0
0x180003332  movups  xmmword ptr [rbx+0B0h], xmm0
0x180003339  call    cs:__imp_RtlDeleteCriticalSection
0x18000333f  mov     rax, [rbx]
0x180003342  test    rax, rax
0x180003345  jz      short loc_180003361
0x180003347  xorps   xmm0, xmm0
0x18000334a  movups  xmmword ptr [rax], xmm0
0x18000334d  movups  xmmword ptr [rax+10h], xmm0
0x180003351  movups  xmmword ptr [rax+20h], xmm0
0x180003355  movups  xmmword ptr [rax+30h], xmm0
0x180003359  movups  xmmword ptr [rax+40h], xmm0
0x18000335d  movups  xmmword ptr [rax+4Ch], xmm0
0x180003361  mov     rcx, [rbx+2C8h]
0x180003368  test    rcx, rcx
0x18000336b  jz      short loc_180003373
0x18000336d  call    cs:__imp_EtwEventUnregister
0x180003373  mov     rcx, gs:60h
0x18000337c  mov     r8, rbx; P
0x18000337f  xor     edx, edx; Flags
0x180003381  mov     rcx, [rcx+30h]; HeapHandle
0x180003385  call    cs:__imp_RtlFreeHeap
0x18000338b  add     rsp, 20h
0x18000338f  pop     rbx
0x180003390  retn
0x180003391  mov     rcx, [rbx+90h]; hHeap
0x180003398  xor     edx, edx; dwFlags
0x18000339a  call    cs:__imp_HeapFree
0x1800033a0  jmp     loc_18000331D
0x1800033a5  call    FreeLibrary_0
0x1800033aa  mov     qword ptr [rbx+2D0h], 0
0x1800033b5  jmp     loc_180003311
```
