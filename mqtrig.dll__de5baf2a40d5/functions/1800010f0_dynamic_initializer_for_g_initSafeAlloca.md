# _dynamic_initializer_for__g_initSafeAlloca__

- ea: `0x1800010f0`
- end: `0x18000116a`
- name: `_dynamic_initializer_for__g_initSafeAlloca__`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800010f0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180001101`
- `ntdll!RtlImageNtHeader` at `0x180001101`

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
0x1800010f0  sub     rsp, 28h
0x1800010f4  mov     rcx, gs:60h
0x1800010fd  mov     rcx, [rcx+10h]; BaseAddress
0x180001101  call    cs:__imp_RtlImageNtHeader
0x180001107  mov     rcx, gs:60h
0x180001110  mov     r8d, 4000h
0x180001116  mov     rdx, rax
0x180001119  cmp     byte ptr [rcx+2], 0
0x18000111d  jnz     short loc_180001134
0x18000111f  test    rax, rax
0x180001122  jz      short loc_180001138
0x180001124  mov     rax, [rax+60h]
0x180001128  sub     rax, [rdx+68h]
0x18000112c  cmp     rax, 3000h
0x180001132  jnb     short loc_180001138
0x180001134  xor     eax, eax
0x180001136  jmp     short loc_18000113B
0x180001138  mov     rax, r8
0x18000113b  mov     cs:g_ulMaxStackAllocSize, rax
0x180001142  lea     rax, ?AllocaHeapAllocate@@YAPEAX_K@Z; AllocaHeapAllocate(unsigned __int64)
0x180001149  mov     cs:g_pfnAllocate, rax
0x180001150  lea     rax, ?AllocaHeapFree@@YAXPEAX@Z; AllocaHeapFree(void *)
0x180001157  mov     cs:g_pfnFree, rax
0x18000115e  mov     cs:g_ulAdditionalProbeSize, r8
0x180001165  add     rsp, 28h
0x180001169  retn
```
