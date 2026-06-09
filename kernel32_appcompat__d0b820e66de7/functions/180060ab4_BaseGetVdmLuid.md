# BaseGetVdmLuid

- ea: `0x180060ab4`
- end: `0x180060ba5`
- name: `BaseGetVdmLuid`
- size: `241`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800296bc`

## callees

- `0x180060ab4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180060ae4`
- `ntdll!NtQueryInformationToken` at `0x180060b56`
- `ntdll!NtQueryInformationToken` at `0x180060ae4`
- `ntdll!NtQueryInformationToken` at `0x180060b56`
- `ntdll!RtlFreeHeap` at `0x180060b86`
- `ntdll!RtlFreeHeap` at `0x180060b86`
- `ntdll!RtlAllocateHeap` at `0x180060b21`
- `ntdll!RtlAllocateHeap` at `0x180060b21`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180060afb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180060afb`

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
0x180060ab4  mov     rax, rsp
0x180060ab7  mov     [rax+8], rbx
0x180060abb  mov     [rax+10h], rsi
0x180060abf  push    rdi
0x180060ac0  sub     rsp, 30h
0x180060ac4  xor     r9d, r9d; TokenInformationLength
0x180060ac7  mov     dword ptr [rax+18h], 0
0x180060ace  mov     rdi, rdx
0x180060ad1  lea     rax, [rax+18h]
0x180060ad5  xor     r8d, r8d; TokenInformation
0x180060ad8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180060add  mov     rsi, rcx
0x180060ae0  lea     edx, [r9+0Ah]; TokenInformationClass
0x180060ae4  call    cs:__imp_NtQueryInformationToken
0x180060aeb  nop     dword ptr [rax+rax+00h]
0x180060af0  cmp     eax, 0C0000023h
0x180060af5  jnz     loc_180060B94
0x180060afb  call    cs:__imp_KernelBaseGetGlobalData
0x180060b02  nop     dword ptr [rax+rax+00h]
0x180060b07  mov     rcx, gs:60h
0x180060b10  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180060b15  mov     edx, [rax]
0x180060b17  mov     rcx, [rcx+30h]; HeapHandle
0x180060b1b  add     edx, 200000h; Flags
0x180060b21  call    cs:__imp_RtlAllocateHeap
0x180060b28  nop     dword ptr [rax+rax+00h]
0x180060b2d  mov     rbx, rax
0x180060b30  test    rax, rax
0x180060b33  jnz     short loc_180060B3C
0x180060b35  mov     eax, 0C0000023h
0x180060b3a  jmp     short loc_180060B94
0x180060b3c  mov     r9d, dword ptr [rsp+38h+Size]; TokenInformationLength
0x180060b41  lea     rax, [rsp+38h+Size]
0x180060b46  mov     r8, rbx; TokenInformation
0x180060b49  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180060b4e  mov     edx, 0Ah; TokenInformationClass
0x180060b53  mov     rcx, rsi; TokenHandle
0x180060b56  call    cs:__imp_NtQueryInformationToken
0x180060b5d  nop     dword ptr [rax+rax+00h]
0x180060b62  mov     esi, eax
0x180060b64  test    eax, eax
0x180060b66  js      short loc_180060B74
0x180060b68  test    rdi, rdi
0x180060b6b  jz      short loc_180060B74
0x180060b6d  mov     rcx, [rbx+8]
0x180060b71  mov     [rdi], rcx
0x180060b74  mov     rcx, gs:60h
0x180060b7d  mov     r8, rbx; P
0x180060b80  xor     edx, edx; Flags
0x180060b82  mov     rcx, [rcx+30h]; HeapHandle
0x180060b86  call    cs:__imp_RtlFreeHeap
0x180060b8d  nop     dword ptr [rax+rax+00h]
0x180060b92  mov     eax, esi
0x180060b94  mov     rbx, [rsp+38h+arg_0]
0x180060b99  mov     rsi, [rsp+38h+arg_8]
0x180060b9e  add     rsp, 30h
0x180060ba2  pop     rdi
0x180060ba3  retn
```
