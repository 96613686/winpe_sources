# SafeAllocaInitialize

- ea: `0x180027c80`
- end: `0x180027d3c`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009afc`

## callees

- `0x180027c80`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180027c91`
- `ntdll!RtlImageNtHeader` at `0x180027c91`

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
  g_pfnAllocate = (__int64)DsRoleSrvSafeAllocaAllocate;
  result = DsRoleSrvSafeAllocaFree;
  g_pfnFree = (__int64)DsRoleSrvSafeAllocaFree;
  return result;
}

```

## disassembly

```asm
0x180027c80  sub     rsp, 28h
0x180027c84  mov     rcx, gs:60h
0x180027c8d  mov     rcx, [rcx+10h]; BaseAddress
0x180027c91  call    cs:__imp_RtlImageNtHeader
0x180027c97  mov     rcx, gs:60h
0x180027ca0  mov     r8d, 3000h
0x180027ca6  mov     rdx, rax
0x180027ca9  cmp     byte ptr [rcx+2], 0
0x180027cad  jnz     short loc_180027CD4
0x180027caf  test    rax, rax
0x180027cb2  jz      short loc_180027CD4
0x180027cb4  mov     rax, [rax+60h]
0x180027cb8  sub     rax, [rdx+68h]
0x180027cbc  cmp     rax, r8
0x180027cbf  jnb     short loc_180027CCE
0x180027cc1  mov     cs:g_ulMaxStackAllocSize, 0
0x180027ccc  jmp     short loc_180027CE2
0x180027cce  mov     rax, [rdx+68h]
0x180027cd2  jmp     short loc_180027CD6
0x180027cd4  xor     eax, eax
0x180027cd6  mov     cs:g_ulMaxStackAllocSize, rax
0x180027cdd  test    rdx, rdx
0x180027ce0  jz      short loc_180027D10
0x180027ce2  mov     rax, gs:30h
0x180027ceb  mov     eax, [rax+1748h]
0x180027cf1  mov     cs:g_ulAdditionalProbeSize, rax
0x180027cf8  test    rax, rax
0x180027cfb  jnz     short loc_180027D06
0x180027cfd  mov     cs:g_ulAdditionalProbeSize, r8
0x180027d04  jmp     short loc_180027D1B
0x180027d06  add     rax, 8
0x180027d0a  cmp     rax, 8
0x180027d0e  jnb     short loc_180027D1B
0x180027d10  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180027d1b  lea     rax, DsRoleSrvSafeAllocaAllocate
0x180027d22  mov     cs:g_pfnAllocate, rax
0x180027d29  lea     rax, DsRoleSrvSafeAllocaFree
0x180027d30  mov     cs:g_pfnFree, rax
0x180027d37  add     rsp, 28h
0x180027d3b  retn
```
