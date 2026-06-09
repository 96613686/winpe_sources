# _dynamic_initializer_for__g_initSafeAlloca__

- ea: `0x140001270`
- end: `0x1400012ea`
- name: `_dynamic_initializer_for__g_initSafeAlloca__`
- size: `122`
- prototype: `void (__fastcall *())(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140001270`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x140001281`
- `ntdll!RtlImageNtHeader` at `0x140001281`

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
0x140001270  sub     rsp, 28h
0x140001274  mov     rcx, gs:60h
0x14000127d  mov     rcx, [rcx+10h]; BaseAddress
0x140001281  call    cs:__imp_RtlImageNtHeader
0x140001287  mov     rcx, gs:60h
0x140001290  mov     r8d, 4000h
0x140001296  mov     rdx, rax
0x140001299  cmp     byte ptr [rcx+2], 0
0x14000129d  jnz     short loc_1400012B4
0x14000129f  test    rax, rax
0x1400012a2  jz      short loc_1400012B8
0x1400012a4  mov     rax, [rax+60h]
0x1400012a8  sub     rax, [rdx+68h]
0x1400012ac  cmp     rax, 3000h
0x1400012b2  jnb     short loc_1400012B8
0x1400012b4  xor     eax, eax
0x1400012b6  jmp     short loc_1400012BB
0x1400012b8  mov     rax, r8
0x1400012bb  mov     cs:g_ulMaxStackAllocSize, rax
0x1400012c2  lea     rax, ?AllocaHeapAllocate@@YAPEAX_K@Z; AllocaHeapAllocate(unsigned __int64)
0x1400012c9  mov     cs:g_pfnAllocate, rax
0x1400012d0  lea     rax, ?AllocaHeapFree@@YAXPEAX@Z; AllocaHeapFree(void *)
0x1400012d7  mov     cs:g_pfnFree, rax
0x1400012de  mov     cs:g_ulAdditionalProbeSize, r8
0x1400012e5  add     rsp, 28h
0x1400012e9  retn
```
