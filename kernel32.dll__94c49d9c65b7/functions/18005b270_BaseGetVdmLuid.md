# BaseGetVdmLuid

- ea: `0x18005b270`
- end: `0x18005b342`
- name: `BaseGetVdmLuid`
- size: `210`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a6d8`

## callees

- `0x18005b270`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18005b2a0`
- `ntdll!NtQueryInformationToken` at `0x18005b300`
- `ntdll!NtQueryInformationToken` at `0x18005b2a0`
- `ntdll!NtQueryInformationToken` at `0x18005b300`
- `ntdll!RtlFreeHeap` at `0x18005b32a`
- `ntdll!RtlFreeHeap` at `0x18005b32a`
- `ntdll!RtlAllocateHeap` at `0x18005b2d1`
- `ntdll!RtlAllocateHeap` at `0x18005b2d1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005b2b1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005b2b1`

## pseudocode

```c
NTSTATUS __fastcall BaseGetVdmLuid(HANDLE TokenHandle, _QWORD *a2)
{
  NTSTATUS result; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _DWORD *GlobalData; // rax
  _QWORD *Heap; // rbx
  NTSTATUS InformationToken; // esi
  SIZE_T Size; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(Size) = 0;
  result = NtQueryInformationToken(TokenHandle, TokenStatistics, 0, 0, (PULONG)&Size);
  if ( result == -1073741789 )
  {
    GlobalData = (_DWORD *)KernelBaseGetGlobalData(v6, v5, v7, v8);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData + 0x200000, (unsigned int)Size);
    if ( Heap )
    {
      InformationToken = NtQueryInformationToken(TokenHandle, TokenStatistics, Heap, Size, (PULONG)&Size);
      if ( InformationToken >= 0 )
      {
        if ( a2 )
          *a2 = Heap[1];
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return InformationToken;
    }
    else
    {
      return -1073741789;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005b270  mov     rax, rsp
0x18005b273  mov     [rax+8], rbx
0x18005b277  mov     [rax+10h], rsi
0x18005b27b  push    rdi
0x18005b27c  sub     rsp, 30h
0x18005b280  xor     r9d, r9d; TokenInformationLength
0x18005b283  mov     dword ptr [rax+18h], 0
0x18005b28a  mov     rdi, rdx
0x18005b28d  lea     rax, [rax+18h]
0x18005b291  xor     r8d, r8d; TokenInformation
0x18005b294  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005b299  mov     rsi, rcx
0x18005b29c  lea     edx, [r9+0Ah]; TokenInformationClass
0x18005b2a0  call    cs:__imp_NtQueryInformationToken
0x18005b2a6  cmp     eax, 0C0000023h
0x18005b2ab  jnz     loc_18005B332
0x18005b2b1  call    cs:__imp_KernelBaseGetGlobalData
0x18005b2b7  mov     rcx, gs:60h
0x18005b2c0  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x18005b2c5  mov     edx, [rax]
0x18005b2c7  mov     rcx, [rcx+30h]; HeapHandle
0x18005b2cb  add     edx, 200000h; Flags
0x18005b2d1  call    cs:__imp_RtlAllocateHeap
0x18005b2d7  mov     rbx, rax
0x18005b2da  test    rax, rax
0x18005b2dd  jnz     short loc_18005B2E6
0x18005b2df  mov     eax, 0C0000023h
0x18005b2e4  jmp     short loc_18005B332
0x18005b2e6  mov     r9d, dword ptr [rsp+38h+Size]; TokenInformationLength
0x18005b2eb  lea     rax, [rsp+38h+Size]
0x18005b2f0  mov     r8, rbx; TokenInformation
0x18005b2f3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18005b2f8  mov     edx, 0Ah; TokenInformationClass
0x18005b2fd  mov     rcx, rsi; TokenHandle
0x18005b300  call    cs:__imp_NtQueryInformationToken
0x18005b306  mov     esi, eax
0x18005b308  test    eax, eax
0x18005b30a  js      short loc_18005B318
0x18005b30c  test    rdi, rdi
0x18005b30f  jz      short loc_18005B318
0x18005b311  mov     rcx, [rbx+8]
0x18005b315  mov     [rdi], rcx
0x18005b318  mov     rcx, gs:60h
0x18005b321  mov     r8, rbx; P
0x18005b324  xor     edx, edx; Flags
0x18005b326  mov     rcx, [rcx+30h]; HeapHandle
0x18005b32a  call    cs:__imp_RtlFreeHeap
0x18005b330  mov     eax, esi
0x18005b332  mov     rbx, [rsp+38h+arg_0]
0x18005b337  mov     rsi, [rsp+38h+arg_8]
0x18005b33c  add     rsp, 30h
0x18005b340  pop     rdi
0x18005b341  retn
```
