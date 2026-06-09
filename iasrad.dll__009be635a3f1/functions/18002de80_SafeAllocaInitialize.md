# SafeAllocaInitialize

- ea: `0x18002de80`
- end: `0x18002df3c`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800013e0`

## callees

- `0x18002de80`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18002de91`
- `ntdll!RtlImageNtHeader` at `0x18002de91`

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
0x18002de80  sub     rsp, 28h
0x18002de84  mov     rcx, gs:60h
0x18002de8d  mov     rcx, [rcx+10h]; BaseAddress
0x18002de91  call    cs:__imp_RtlImageNtHeader
0x18002de97  mov     rcx, gs:60h
0x18002dea0  mov     r8d, 3000h
0x18002dea6  mov     rdx, rax
0x18002dea9  cmp     byte ptr [rcx+2], 0
0x18002dead  jnz     short loc_18002DED4
0x18002deaf  test    rax, rax
0x18002deb2  jz      short loc_18002DED4
0x18002deb4  mov     rax, [rax+60h]
0x18002deb8  sub     rax, [rdx+68h]
0x18002debc  cmp     rax, r8
0x18002debf  jnb     short loc_18002DECE
0x18002dec1  mov     cs:g_ulMaxStackAllocSize, 0
0x18002decc  jmp     short loc_18002DEE2
0x18002dece  mov     rax, [rdx+68h]
0x18002ded2  jmp     short loc_18002DED6
0x18002ded4  xor     eax, eax
0x18002ded6  mov     cs:g_ulMaxStackAllocSize, rax
0x18002dedd  test    rdx, rdx
0x18002dee0  jz      short loc_18002DF10
0x18002dee2  mov     rax, gs:30h
0x18002deeb  mov     eax, [rax+1748h]
0x18002def1  mov     cs:g_ulAdditionalProbeSize, rax
0x18002def8  test    rax, rax
0x18002defb  jnz     short loc_18002DF06
0x18002defd  mov     cs:g_ulAdditionalProbeSize, r8
0x18002df04  jmp     short loc_18002DF1B
0x18002df06  add     rax, 8
0x18002df0a  cmp     rax, 8
0x18002df0e  jnb     short loc_18002DF1B
0x18002df10  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18002df1b  lea     rax, SafeAllocaAllocateFromHeap
0x18002df22  mov     cs:g_pfnAllocate, rax
0x18002df29  lea     rax, SafeAllocaFreeToHeap
0x18002df30  mov     cs:g_pfnFree, rax
0x18002df37  add     rsp, 28h
0x18002df3b  retn
```
