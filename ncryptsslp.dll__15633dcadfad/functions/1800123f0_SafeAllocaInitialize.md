# SafeAllocaInitialize

- ea: `0x1800123f0`
- end: `0x1800124af`
- name: `SafeAllocaInitialize`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012220`

## callees

- `0x1800123f0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180012401`
- `ntdll!RtlImageNtHeader` at `0x180012401`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())(_QWORD)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 (__fastcall *result)(_QWORD); // rax
  __int64 GuaranteedStackBytes; // rax

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
      goto LABEL_10;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
  {
LABEL_4:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_6;
  }
LABEL_10:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( !GuaranteedStackBytes )
  {
    g_ulAdditionalProbeSize = 12288;
    goto LABEL_6;
  }
  if ( (unsigned __int64)(GuaranteedStackBytes + 8) < 8 )
    goto LABEL_4;
LABEL_6:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = MSCryptFree;
  g_pfnFree = (__int64)MSCryptFree;
  return result;
}

```

## disassembly

```asm
0x1800123f0  sub     rsp, 28h
0x1800123f4  mov     rcx, gs:60h
0x1800123fd  mov     rcx, [rcx+10h]; BaseAddress
0x180012401  call    cs:__imp_RtlImageNtHeader
0x180012407  mov     rcx, gs:60h
0x180012410  mov     r8d, 3000h
0x180012416  mov     rdx, rax
0x180012419  cmp     byte ptr [rcx+2], 0
0x18001241d  jz      short loc_180012465
0x18001241f  xor     eax, eax
0x180012421  mov     cs:g_ulMaxStackAllocSize, rax
0x180012428  test    rdx, rdx
0x18001242b  jnz     short loc_180012482
0x18001242d  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180012438  jmp     short loc_180012444
0x18001243a  add     rax, 8
0x18001243e  cmp     rax, 8
0x180012442  jb      short loc_18001242D
0x180012444  lea     rax, SafeAllocaAllocateFromHeap
0x18001244b  mov     cs:g_pfnAllocate, rax
0x180012452  lea     rax, MSCryptFree
0x180012459  mov     cs:g_pfnFree, rax
0x180012460  add     rsp, 28h
0x180012464  retn
0x180012465  test    rdx, rdx
0x180012468  jz      short loc_18001241F
0x18001246a  mov     rax, [rax+60h]
0x18001246e  sub     rax, [rdx+68h]
0x180012472  cmp     rax, r8
0x180012475  jnb     short loc_1800124A6
0x180012477  mov     cs:g_ulMaxStackAllocSize, 0
0x180012482  mov     rax, gs:30h
0x18001248b  mov     eax, [rax+1748h]
0x180012491  mov     cs:g_ulAdditionalProbeSize, rax
0x180012498  test    rax, rax
0x18001249b  jnz     short loc_18001243A
0x18001249d  mov     cs:g_ulAdditionalProbeSize, r8
0x1800124a4  jmp     short loc_180012444
0x1800124a6  mov     rax, [rdx+68h]
0x1800124aa  jmp     loc_180012421
```
