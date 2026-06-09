# SafeAllocaInitialize

- ea: `0x180024010`
- end: `0x1800240cc`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017d90`

## callees

- `0x180024010`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180024021`
- `ntdll!RtlImageNtHeader` at `0x180024021`

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
  g_pfnAllocate = (__int64)AllocH;
  result = FreeH;
  g_pfnFree = (__int64)FreeH;
  return result;
}

```

## disassembly

```asm
0x180024010  sub     rsp, 28h
0x180024014  mov     rcx, gs:60h
0x18002401d  mov     rcx, [rcx+10h]; BaseAddress
0x180024021  call    cs:__imp_RtlImageNtHeader
0x180024027  mov     rcx, gs:60h
0x180024030  mov     r8d, 3000h
0x180024036  mov     rdx, rax
0x180024039  cmp     byte ptr [rcx+2], 0
0x18002403d  jnz     short loc_180024064
0x18002403f  test    rax, rax
0x180024042  jz      short loc_180024064
0x180024044  mov     rax, [rax+60h]
0x180024048  sub     rax, [rdx+68h]
0x18002404c  cmp     rax, r8
0x18002404f  jnb     short loc_18002405E
0x180024051  mov     cs:g_ulMaxStackAllocSize, 0
0x18002405c  jmp     short loc_180024072
0x18002405e  mov     rax, [rdx+68h]
0x180024062  jmp     short loc_180024066
0x180024064  xor     eax, eax
0x180024066  mov     cs:g_ulMaxStackAllocSize, rax
0x18002406d  test    rdx, rdx
0x180024070  jz      short loc_1800240A0
0x180024072  mov     rax, gs:30h
0x18002407b  mov     eax, [rax+1748h]
0x180024081  mov     cs:g_ulAdditionalProbeSize, rax
0x180024088  test    rax, rax
0x18002408b  jnz     short loc_180024096
0x18002408d  mov     cs:g_ulAdditionalProbeSize, r8
0x180024094  jmp     short loc_1800240AB
0x180024096  add     rax, 8
0x18002409a  cmp     rax, 8
0x18002409e  jnb     short loc_1800240AB
0x1800240a0  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x1800240ab  lea     rax, AllocH
0x1800240b2  mov     cs:g_pfnAllocate, rax
0x1800240b9  lea     rax, FreeH
0x1800240c0  mov     cs:g_pfnFree, rax
0x1800240c7  add     rsp, 28h
0x1800240cb  retn
```
