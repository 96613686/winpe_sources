# _dynamic_initializer_for__g_initSafeAlloca__

- ea: `0x1800017e0`
- end: `0x18000185a`
- name: `_dynamic_initializer_for__g_initSafeAlloca__`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800017e0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x1800017f1`
- `ntdll!RtlImageNtHeader` at `0x1800017f1`

## pseudocode

```c
void (__stdcall *dynamic_initializer_for__g_initSafeAlloca__())(PVOID pvMemory)
{
  PIMAGE_NT_HEADERS v0; // rax
  __int64 v1; // rax
  void (__stdcall *result)(PVOID); // rax

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
  result = MQFreeMemory;
  g_pfnFree = (__int64)MQFreeMemory;
  g_ulAdditionalProbeSize = 0x4000;
  return result;
}

```

## disassembly

```asm
0x1800017e0  sub     rsp, 28h
0x1800017e4  mov     rcx, gs:60h
0x1800017ed  mov     rcx, [rcx+10h]; BaseAddress
0x1800017f1  call    cs:__imp_RtlImageNtHeader
0x1800017f7  mov     rcx, gs:60h
0x180001800  mov     r8d, 4000h
0x180001806  mov     rdx, rax
0x180001809  cmp     byte ptr [rcx+2], 0
0x18000180d  jnz     short loc_180001824
0x18000180f  test    rax, rax
0x180001812  jz      short loc_180001828
0x180001814  mov     rax, [rax+60h]
0x180001818  sub     rax, [rdx+68h]
0x18000181c  cmp     rax, 3000h
0x180001822  jnb     short loc_180001828
0x180001824  xor     eax, eax
0x180001826  jmp     short loc_18000182B
0x180001828  mov     rax, r8
0x18000182b  mov     cs:g_ulMaxStackAllocSize, rax
0x180001832  lea     rax, ?AllocaHeapAllocate@@YAPEAX_K@Z; AllocaHeapAllocate(unsigned __int64)
0x180001839  mov     cs:g_pfnAllocate, rax
0x180001840  lea     rax, MQFreeMemory
0x180001847  mov     cs:g_pfnFree, rax
0x18000184e  mov     cs:g_ulAdditionalProbeSize, r8
0x180001855  add     rsp, 28h
0x180001859  retn
```
