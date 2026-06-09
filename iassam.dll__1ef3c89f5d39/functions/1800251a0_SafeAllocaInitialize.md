# SafeAllocaInitialize

- ea: `0x1800251a0`
- end: `0x18002525c`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009fa8`

## callees

- `0x1800251a0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x1800251b1`
- `ntdll!RtlImageNtHeader` at `0x1800251b1`

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
0x1800251a0  sub     rsp, 28h
0x1800251a4  mov     rcx, gs:60h
0x1800251ad  mov     rcx, [rcx+10h]; BaseAddress
0x1800251b1  call    cs:__imp_RtlImageNtHeader
0x1800251b7  mov     rcx, gs:60h
0x1800251c0  mov     r8d, 3000h
0x1800251c6  mov     rdx, rax
0x1800251c9  cmp     byte ptr [rcx+2], 0
0x1800251cd  jnz     short loc_1800251F4
0x1800251cf  test    rax, rax
0x1800251d2  jz      short loc_1800251F4
0x1800251d4  mov     rax, [rax+60h]
0x1800251d8  sub     rax, [rdx+68h]
0x1800251dc  cmp     rax, r8
0x1800251df  jnb     short loc_1800251EE
0x1800251e1  mov     cs:g_ulMaxStackAllocSize, 0
0x1800251ec  jmp     short loc_180025202
0x1800251ee  mov     rax, [rdx+68h]
0x1800251f2  jmp     short loc_1800251F6
0x1800251f4  xor     eax, eax
0x1800251f6  mov     cs:g_ulMaxStackAllocSize, rax
0x1800251fd  test    rdx, rdx
0x180025200  jz      short loc_180025230
0x180025202  mov     rax, gs:30h
0x18002520b  mov     eax, [rax+1748h]
0x180025211  mov     cs:g_ulAdditionalProbeSize, rax
0x180025218  test    rax, rax
0x18002521b  jnz     short loc_180025226
0x18002521d  mov     cs:g_ulAdditionalProbeSize, r8
0x180025224  jmp     short loc_18002523B
0x180025226  add     rax, 8
0x18002522a  cmp     rax, 8
0x18002522e  jnb     short loc_18002523B
0x180025230  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18002523b  lea     rax, SafeAllocaAllocateFromHeap
0x180025242  mov     cs:g_pfnAllocate, rax
0x180025249  lea     rax, SafeAllocaFreeToHeap
0x180025250  mov     cs:g_pfnFree, rax
0x180025257  add     rsp, 28h
0x18002525b  retn
```
