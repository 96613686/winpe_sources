# SafeAllocaInitialize

- ea: `0x18006b4b8`
- end: `0x18006b574`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180020160`
- `0x180048050`

## callees

- `0x18006b4b8`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18006b4c9`
- `ntdll!RtlImageNtHeader` at `0x18006b4c9`

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
  g_pfnAllocate = (__int64)NtLmAllocate;
  result = NtLmFree;
  g_pfnFree = (__int64)NtLmFree;
  return result;
}

```

## disassembly

```asm
0x18006b4b8  sub     rsp, 28h
0x18006b4bc  mov     rcx, gs:60h
0x18006b4c5  mov     rcx, [rcx+10h]; BaseAddress
0x18006b4c9  call    cs:__imp_RtlImageNtHeader
0x18006b4cf  mov     rcx, gs:60h
0x18006b4d8  mov     r8d, 3000h
0x18006b4de  mov     rdx, rax
0x18006b4e1  cmp     byte ptr [rcx+2], 0
0x18006b4e5  jnz     short loc_18006B50C
0x18006b4e7  test    rax, rax
0x18006b4ea  jz      short loc_18006B50C
0x18006b4ec  mov     rax, [rax+60h]
0x18006b4f0  sub     rax, [rdx+68h]
0x18006b4f4  cmp     rax, r8
0x18006b4f7  jnb     short loc_18006B506
0x18006b4f9  mov     cs:g_ulMaxStackAllocSize, 0
0x18006b504  jmp     short loc_18006B51A
0x18006b506  mov     rax, [rdx+68h]
0x18006b50a  jmp     short loc_18006B50E
0x18006b50c  xor     eax, eax
0x18006b50e  mov     cs:g_ulMaxStackAllocSize, rax
0x18006b515  test    rdx, rdx
0x18006b518  jz      short loc_18006B548
0x18006b51a  mov     rax, gs:30h
0x18006b523  mov     eax, [rax+1748h]
0x18006b529  mov     cs:g_ulAdditionalProbeSize, rax
0x18006b530  test    rax, rax
0x18006b533  jnz     short loc_18006B53E
0x18006b535  mov     cs:g_ulAdditionalProbeSize, r8
0x18006b53c  jmp     short loc_18006B553
0x18006b53e  add     rax, 8
0x18006b542  cmp     rax, 8
0x18006b546  jnb     short loc_18006B553
0x18006b548  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18006b553  lea     rax, NtLmAllocate
0x18006b55a  mov     cs:g_pfnAllocate, rax
0x18006b561  lea     rax, NtLmFree
0x18006b568  mov     cs:g_pfnFree, rax
0x18006b56f  add     rsp, 28h
0x18006b573  retn
```
