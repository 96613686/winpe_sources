# SafeAllocaInitialize

- ea: `0x180013bd0`
- end: `0x180013c8f`
- name: `SafeAllocaInitialize`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013880`

## callees

- `0x180013bd0`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180013be1`
- `ntdll!RtlImageNtHeader` at `0x180013be1`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())(_QWORD)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(_QWORD); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged || !v0 )
  {
    SizeOfStackCommit = 0;
    goto LABEL_3;
  }
  if ( v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit >= 0x3000 )
  {
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
LABEL_3:
    g_ulMaxStackAllocSize = SizeOfStackCommit;
    if ( !v1 )
      goto LABEL_4;
    goto LABEL_8;
  }
  g_ulMaxStackAllocSize = 0;
LABEL_8:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( !GuaranteedStackBytes )
  {
    g_ulAdditionalProbeSize = 12288;
    goto LABEL_11;
  }
  if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
    goto LABEL_11;
LABEL_4:
  g_ulAdditionalProbeSize = -9;
LABEL_11:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = MSCryptFree;
  g_pfnFree = (__int64)MSCryptFree;
  return result;
}

```

## disassembly

```asm
0x180013bd0  sub     rsp, 28h
0x180013bd4  mov     rcx, gs:60h
0x180013bdd  mov     rcx, [rcx+10h]; BaseAddress
0x180013be1  call    cs:__imp_RtlImageNtHeader
0x180013be7  mov     rcx, gs:60h
0x180013bf0  mov     r8d, 3000h
0x180013bf6  mov     rdx, rax
0x180013bf9  cmp     byte ptr [rcx+2], 0
0x180013bfd  jz      short loc_180013C1A
0x180013bff  xor     eax, eax
0x180013c01  mov     cs:g_ulMaxStackAllocSize, rax
0x180013c08  test    rdx, rdx
0x180013c0b  jnz     short loc_180013C37
0x180013c0d  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180013c18  jmp     short loc_180013C65
0x180013c1a  test    rdx, rdx
0x180013c1d  jz      short loc_180013BFF
0x180013c1f  mov     rax, [rax+60h]
0x180013c23  sub     rax, [rdx+68h]
0x180013c27  cmp     rax, r8
0x180013c2a  jnb     short loc_180013C86
0x180013c2c  mov     cs:g_ulMaxStackAllocSize, 0
0x180013c37  mov     rax, gs:30h
0x180013c40  mov     eax, [rax+1748h]
0x180013c46  mov     cs:g_ulAdditionalProbeSize, rax
0x180013c4d  test    rax, rax
0x180013c50  jnz     short loc_180013C5B
0x180013c52  mov     cs:g_ulAdditionalProbeSize, r8
0x180013c59  jmp     short loc_180013C65
0x180013c5b  add     rax, 8
0x180013c5f  cmp     rax, 8
0x180013c63  jb      short loc_180013C0D
0x180013c65  lea     rax, SafeAllocaAllocateFromHeap
0x180013c6c  mov     cs:g_pfnAllocate, rax
0x180013c73  lea     rax, MSCryptFree
0x180013c7a  mov     cs:g_pfnFree, rax
0x180013c81  add     rsp, 28h
0x180013c85  retn
0x180013c86  mov     rax, [rdx+68h]
0x180013c8a  jmp     loc_180013C01
```
