# SafeAllocaInitialize

- ea: `0x18000c0c8`
- end: `0x18000c184`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f60c`

## callees

- `0x18000c0c8`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18000c0d9`
- `ntdll!RtlImageNtHeader` at `0x18000c0d9`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())()
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged || !v0 )
  {
    SizeOfStackCommit = 0;
  }
  else
  {
    if ( v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_8;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
    goto LABEL_11;
LABEL_8:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_12;
LABEL_11:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_12;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_12:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = SafeAllocaFreeToHeap;
  g_pfnFree = (__int64)SafeAllocaFreeToHeap;
  return result;
}

```

## disassembly

```asm
0x18000c0c8  sub     rsp, 28h
0x18000c0cc  mov     rcx, gs:60h
0x18000c0d5  mov     rcx, [rcx+10h]; BaseAddress
0x18000c0d9  call    cs:__imp_RtlImageNtHeader
0x18000c0df  mov     rcx, gs:60h
0x18000c0e8  mov     r8d, 3000h
0x18000c0ee  mov     rdx, rax
0x18000c0f1  cmp     byte ptr [rcx+2], 0
0x18000c0f5  jnz     short loc_18000C11C
0x18000c0f7  test    rax, rax
0x18000c0fa  jz      short loc_18000C11C
0x18000c0fc  mov     rax, [rax+60h]
0x18000c100  sub     rax, [rdx+68h]
0x18000c104  cmp     rax, r8
0x18000c107  jnb     short loc_18000C116
0x18000c109  mov     cs:g_ulMaxStackAllocSize, 0
0x18000c114  jmp     short loc_18000C12A
0x18000c116  mov     rax, [rdx+68h]
0x18000c11a  jmp     short loc_18000C11E
0x18000c11c  xor     eax, eax
0x18000c11e  mov     cs:g_ulMaxStackAllocSize, rax
0x18000c125  test    rdx, rdx
0x18000c128  jz      short loc_18000C158
0x18000c12a  mov     rax, gs:30h
0x18000c133  mov     eax, [rax+1748h]
0x18000c139  mov     cs:g_ulAdditionalProbeSize, rax
0x18000c140  test    rax, rax
0x18000c143  jnz     short loc_18000C14E
0x18000c145  mov     cs:g_ulAdditionalProbeSize, r8
0x18000c14c  jmp     short loc_18000C163
0x18000c14e  add     rax, 8
0x18000c152  cmp     rax, 8
0x18000c156  jnb     short loc_18000C163
0x18000c158  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18000c163  lea     rax, SafeAllocaAllocateFromHeap
0x18000c16a  mov     cs:g_pfnAllocate, rax
0x18000c171  lea     rax, SafeAllocaFreeToHeap
0x18000c178  mov     cs:g_pfnFree, rax
0x18000c17f  add     rsp, 28h
0x18000c183  retn
```
