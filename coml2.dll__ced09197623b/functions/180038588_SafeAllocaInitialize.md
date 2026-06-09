# SafeAllocaInitialize

- ea: `0x180038588`
- end: `0x180038647`
- name: `SafeAllocaInitialize`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180047ef0`

## callees

- `0x180038588`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180038599`
- `ntdll!RtlImageNtHeader` at `0x180038599`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())()
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 v2; // rax
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(); // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged )
  {
    v2 = 0;
  }
  else
  {
    if ( v0 && v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_4;
    }
    v2 = 526;
  }
  g_ulMaxStackAllocSize = v2;
  if ( !v1 )
    goto LABEL_12;
LABEL_4:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_10;
LABEL_12:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_10;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_10:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = SafeAllocaFreeToHeap;
  g_pfnFree = (__int64)SafeAllocaFreeToHeap;
  return result;
}

```

## disassembly

```asm
0x180038588  sub     rsp, 28h
0x18003858c  mov     rcx, gs:60h
0x180038595  mov     rcx, [rcx+10h]; BaseAddress
0x180038599  call    cs:__imp_RtlImageNtHeader
0x18003859f  mov     rcx, gs:60h
0x1800385a8  mov     r8d, 3000h
0x1800385ae  mov     rdx, rax
0x1800385b1  cmp     byte ptr [rcx+2], 0
0x1800385b5  jz      short loc_1800385E9
0x1800385b7  xor     eax, eax
0x1800385b9  mov     cs:g_ulMaxStackAllocSize, rax
0x1800385c0  test    rdx, rdx
0x1800385c3  jz      short loc_18003863A
0x1800385c5  mov     rax, gs:30h
0x1800385ce  mov     eax, [rax+1748h]
0x1800385d4  mov     cs:g_ulAdditionalProbeSize, rax
0x1800385db  test    rax, rax
0x1800385de  jnz     short loc_180038602
0x1800385e0  mov     cs:g_ulAdditionalProbeSize, r8
0x1800385e7  jmp     short loc_18003860C
0x1800385e9  test    rdx, rdx
0x1800385ec  jz      short loc_1800385FB
0x1800385ee  mov     rax, [rax+60h]
0x1800385f2  sub     rax, [rdx+68h]
0x1800385f6  cmp     rax, r8
0x1800385f9  jb      short loc_18003862D
0x1800385fb  mov     eax, 20Eh
0x180038600  jmp     short loc_1800385B9
0x180038602  add     rax, 8
0x180038606  cmp     rax, 8
0x18003860a  jb      short loc_18003863A
0x18003860c  lea     rax, SafeAllocaAllocateFromHeap
0x180038613  mov     cs:g_pfnAllocate, rax
0x18003861a  lea     rax, SafeAllocaFreeToHeap
0x180038621  mov     cs:g_pfnFree, rax
0x180038628  add     rsp, 28h
0x18003862c  retn
0x18003862d  mov     cs:g_ulMaxStackAllocSize, 0
0x180038638  jmp     short loc_1800385C5
0x18003863a  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180038645  jmp     short loc_18003860C
```
