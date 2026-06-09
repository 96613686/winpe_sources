# MapSDToRpcSD

- ea: `0x18001d28c`
- end: `0x18001d323`
- name: `MapSDToRpcSD`
- size: `151`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ca9c`

## callees

- `0x18001d28c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001d2f6`
- `ntdll!RtlNtStatusToDosError` at `0x18001d2f6`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001d2ae`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001d2ae`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001d2ee`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001d2ee`
- `ntdll!RtlValidSecurityDescriptor` at `0x18001d2a1`
- `ntdll!RtlValidSecurityDescriptor` at `0x18001d2a1`
- `ntdll!RtlAllocateHeap` at `0x18001d2d0`
- `ntdll!RtlAllocateHeap` at `0x18001d2d0`

## pseudocode

```c
ULONG __fastcall MapSDToRpcSD(PSECURITY_DESCRIPTOR AbsoluteSD, __int64 a2)
{
  ULONG v4; // edi
  PVOID Heap; // rax
  ULONG *v6; // r8
  NTSTATUS SelfRelativeSD; // eax

  if ( !RtlValidSecurityDescriptor(AbsoluteSD) )
    return 87;
  v4 = RtlLengthSecurityDescriptor(AbsoluteSD);
  Heap = *(PVOID *)a2;
  if ( *(_QWORD *)a2 )
  {
    v6 = (ULONG *)(a2 + 8);
    if ( *(_DWORD *)(a2 + 8) >= v4 )
      goto LABEL_5;
  }
  else
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    *(_QWORD *)a2 = Heap;
    if ( Heap )
    {
      v6 = (ULONG *)(a2 + 8);
      *(_DWORD *)(a2 + 8) = v4;
LABEL_5:
      *(_DWORD *)(a2 + 12) = v4;
      SelfRelativeSD = RtlMakeSelfRelativeSD(AbsoluteSD, Heap, v6);
      return RtlNtStatusToDosError(SelfRelativeSD);
    }
  }
  return 14;
}

```

## disassembly

```asm
0x18001d28c  mov     [rsp+arg_0], rbx
0x18001d291  mov     [rsp+arg_8], rsi
0x18001d296  push    rdi
0x18001d297  sub     rsp, 20h
0x18001d29b  mov     rbx, rdx
0x18001d29e  mov     rsi, rcx
0x18001d2a1  call    cs:__imp_RtlValidSecurityDescriptor
0x18001d2a7  test    al, al
0x18001d2a9  jz      short loc_18001D30E
0x18001d2ab  mov     rcx, rsi; SecurityDescriptor
0x18001d2ae  call    cs:__imp_RtlLengthSecurityDescriptor
0x18001d2b4  mov     edi, eax
0x18001d2b6  mov     rax, [rbx]
0x18001d2b9  test    rax, rax
0x18001d2bc  jnz     short loc_18001D2FE
0x18001d2be  mov     rcx, gs:60h
0x18001d2c7  mov     r8d, edi; Size
0x18001d2ca  xor     edx, edx; Flags
0x18001d2cc  mov     rcx, [rcx+30h]; HeapHandle
0x18001d2d0  call    cs:__imp_RtlAllocateHeap
0x18001d2d6  mov     [rbx], rax
0x18001d2d9  test    rax, rax
0x18001d2dc  jz      short loc_18001D307
0x18001d2de  lea     r8, [rbx+8]; BufferLength
0x18001d2e2  mov     [r8], edi
0x18001d2e5  mov     rdx, rax; SelfRelativeSD
0x18001d2e8  mov     [rbx+0Ch], edi
0x18001d2eb  mov     rcx, rsi; AbsoluteSD
0x18001d2ee  call    cs:__imp_RtlMakeSelfRelativeSD
0x18001d2f4  mov     ecx, eax; Status
0x18001d2f6  call    cs:__imp_RtlNtStatusToDosError
0x18001d2fc  jmp     short loc_18001D313
0x18001d2fe  lea     r8, [rbx+8]
0x18001d302  cmp     [r8], edi
0x18001d305  jnb     short loc_18001D2E5
0x18001d307  mov     eax, 0Eh
0x18001d30c  jmp     short loc_18001D313
0x18001d30e  mov     eax, 57h ; 'W'
0x18001d313  mov     rbx, [rsp+28h+arg_0]
0x18001d318  mov     rsi, [rsp+28h+arg_8]
0x18001d31d  add     rsp, 20h
0x18001d321  pop     rdi
0x18001d322  retn
```
