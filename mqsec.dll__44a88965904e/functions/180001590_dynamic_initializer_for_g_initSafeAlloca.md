# _dynamic_initializer_for__g_initSafeAlloca__

- ea: `0x180001590`
- end: `0x18000160a`
- name: `_dynamic_initializer_for__g_initSafeAlloca__`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001590`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x1800015a1`
- `ntdll!RtlImageNtHeader` at `0x1800015a1`

## pseudocode

```c
void (__fastcall *dynamic_initializer_for__g_initSafeAlloca__())(void *)
{
  PIMAGE_NT_HEADERS v0; // rax
  __int64 v1; // rax
  void (__fastcall *result)(void *); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  if ( NtCurrentPeb()->BeingDebugged
    || v0 && v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
  {
    v1 = 0;
  }
  else
  {
    v1 = 0x4000;
  }
  g_ulMaxStackAllocSize = v1;
  g_pfnAllocate = (__int64)AllocaHeapAllocate;
  result = AllocaHeapFree;
  g_pfnFree = (__int64)AllocaHeapFree;
  g_ulAdditionalProbeSize = 0x4000;
  return result;
}

```

## disassembly

```asm
0x180001590  sub     rsp, 28h
0x180001594  mov     rcx, gs:60h
0x18000159d  mov     rcx, [rcx+10h]; BaseAddress
0x1800015a1  call    cs:__imp_RtlImageNtHeader
0x1800015a7  mov     rcx, gs:60h
0x1800015b0  mov     r8d, 4000h
0x1800015b6  mov     rdx, rax
0x1800015b9  cmp     byte ptr [rcx+2], 0
0x1800015bd  jnz     short loc_1800015D4
0x1800015bf  test    rax, rax
0x1800015c2  jz      short loc_1800015D8
0x1800015c4  mov     rax, [rax+60h]
0x1800015c8  sub     rax, [rdx+68h]
0x1800015cc  cmp     rax, 3000h
0x1800015d2  jnb     short loc_1800015D8
0x1800015d4  xor     eax, eax
0x1800015d6  jmp     short loc_1800015DB
0x1800015d8  mov     rax, r8
0x1800015db  mov     cs:g_ulMaxStackAllocSize, rax
0x1800015e2  lea     rax, ?AllocaHeapAllocate@@YAPEAX_K@Z; AllocaHeapAllocate(unsigned __int64)
0x1800015e9  mov     cs:g_pfnAllocate, rax
0x1800015f0  lea     rax, ?AllocaHeapFree@@YAXPEAX@Z; AllocaHeapFree(void *)
0x1800015f7  mov     cs:g_pfnFree, rax
0x1800015fe  mov     cs:g_ulAdditionalProbeSize, r8
0x180001605  add     rsp, 28h
0x180001609  retn
```
