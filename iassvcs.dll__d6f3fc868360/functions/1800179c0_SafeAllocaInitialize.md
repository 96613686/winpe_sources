# SafeAllocaInitialize

- ea: `0x1800179c0`
- end: `0x180017a7c`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64 (__fastcall *())()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013060`

## callees

- `0x1800179c0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x1800179d1`
- `ntdll!RtlImageNtHeader` at `0x1800179d1`

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
0x1800179c0  sub     rsp, 28h
0x1800179c4  mov     rcx, gs:60h
0x1800179cd  mov     rcx, [rcx+10h]; BaseAddress
0x1800179d1  call    cs:__imp_RtlImageNtHeader
0x1800179d7  mov     rcx, gs:60h
0x1800179e0  mov     r8d, 3000h
0x1800179e6  mov     rdx, rax
0x1800179e9  cmp     byte ptr [rcx+2], 0
0x1800179ed  jnz     short loc_180017A14
0x1800179ef  test    rax, rax
0x1800179f2  jz      short loc_180017A14
0x1800179f4  mov     rax, [rax+60h]
0x1800179f8  sub     rax, [rdx+68h]
0x1800179fc  cmp     rax, r8
0x1800179ff  jnb     short loc_180017A0E
0x180017a01  mov     cs:g_ulMaxStackAllocSize, 0
0x180017a0c  jmp     short loc_180017A22
0x180017a0e  mov     rax, [rdx+68h]
0x180017a12  jmp     short loc_180017A16
0x180017a14  xor     eax, eax
0x180017a16  mov     cs:g_ulMaxStackAllocSize, rax
0x180017a1d  test    rdx, rdx
0x180017a20  jz      short loc_180017A50
0x180017a22  mov     rax, gs:30h
0x180017a2b  mov     eax, [rax+1748h]
0x180017a31  mov     cs:g_ulAdditionalProbeSize, rax
0x180017a38  test    rax, rax
0x180017a3b  jnz     short loc_180017A46
0x180017a3d  mov     cs:g_ulAdditionalProbeSize, r8
0x180017a44  jmp     short loc_180017A5B
0x180017a46  add     rax, 8
0x180017a4a  cmp     rax, 8
0x180017a4e  jnb     short loc_180017A5B
0x180017a50  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180017a5b  lea     rax, SafeAllocaAllocateFromHeap
0x180017a62  mov     cs:g_pfnAllocate, rax
0x180017a69  lea     rax, SafeAllocaFreeToHeap
0x180017a70  mov     cs:g_pfnFree, rax
0x180017a77  add     rsp, 28h
0x180017a7b  retn
```
