# MapSDToRpcSD

- ea: `0x18009fc5c`
- end: `0x18009fd17`
- name: `MapSDToRpcSD`
- size: `187`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180064130`
- `0x180064e00`

## callees

- `0x18009fc5c`

## import_xrefs

- `ntdll!RtlValidSecurityDescriptor` at `0x18009fc6b`
- `ntdll!RtlValidSecurityDescriptor` at `0x18009fc6b`
- `ntdll!RtlAllocateHeap` at `0x18009fc9e`
- `ntdll!RtlAllocateHeap` at `0x18009fc9e`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18009fcd5`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18009fcd5`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18009fc7c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18009fc7c`
- `ntdll!RtlNtStatusToDosError` at `0x18009fcdd`
- `ntdll!RtlNtStatusToDosError` at `0x18009fcdd`
- `ntdll!RtlFreeHeap` at `0x18009fcff`
- `ntdll!RtlFreeHeap` at `0x18009fcff`

## pseudocode

```c
__int64 __fastcall MapSDToRpcSD(PSECURITY_DESCRIPTOR AbsoluteSD, __int64 a2)
{
  ULONG v4; // edi
  PVOID Heap; // rax
  ULONG *v6; // r8
  int v7; // esi
  NTSTATUS SelfRelativeSD; // eax
  ULONG v10; // edi

  if ( !RtlValidSecurityDescriptor(AbsoluteSD) )
    return 87;
  v4 = RtlLengthSecurityDescriptor(AbsoluteSD);
  Heap = *(PVOID *)a2;
  if ( *(_QWORD *)a2 )
  {
    v6 = (ULONG *)(a2 + 8);
    if ( *(_DWORD *)(a2 + 8) >= v4 )
    {
      v7 = 0;
      goto LABEL_8;
    }
    return 14;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  *(_QWORD *)a2 = Heap;
  if ( !Heap )
    return 14;
  v6 = (ULONG *)(a2 + 8);
  v7 = 1;
  *(_DWORD *)(a2 + 8) = v4;
LABEL_8:
  *(_DWORD *)(a2 + 12) = v4;
  SelfRelativeSD = RtlMakeSelfRelativeSD(AbsoluteSD, Heap, v6);
  v10 = RtlNtStatusToDosError(SelfRelativeSD);
  if ( v10 )
  {
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)a2);
  }
  return v10;
}

```

## disassembly

```asm
0x18009fc5c  push    rbx
0x18009fc5e  push    rbp
0x18009fc5f  push    rsi
0x18009fc60  push    rdi
0x18009fc61  sub     rsp, 28h
0x18009fc65  mov     rbx, rdx
0x18009fc68  mov     rbp, rcx
0x18009fc6b  call    cs:__imp_RtlValidSecurityDescriptor
0x18009fc71  test    al, al
0x18009fc73  jz      loc_18009FD09
0x18009fc79  mov     rcx, rbp; SecurityDescriptor
0x18009fc7c  call    cs:__imp_RtlLengthSecurityDescriptor
0x18009fc82  mov     edi, eax
0x18009fc84  mov     rax, [rbx]
0x18009fc87  test    rax, rax
0x18009fc8a  jnz     short loc_18009FCBA
0x18009fc8c  mov     rcx, gs:60h
0x18009fc95  mov     r8d, edi; Size
0x18009fc98  xor     edx, edx; Flags
0x18009fc9a  mov     rcx, [rcx+30h]; HeapHandle
0x18009fc9e  call    cs:__imp_RtlAllocateHeap
0x18009fca4  mov     [rbx], rax
0x18009fca7  test    rax, rax
0x18009fcaa  jz      short loc_18009FCC3
0x18009fcac  lea     r8, [rbx+8]
0x18009fcb0  mov     esi, 1
0x18009fcb5  mov     [r8], edi
0x18009fcb8  jmp     short loc_18009FCCC
0x18009fcba  lea     r8, [rbx+8]; BufferLength
0x18009fcbe  cmp     [r8], edi
0x18009fcc1  jnb     short loc_18009FCCA
0x18009fcc3  mov     eax, 0Eh
0x18009fcc8  jmp     short loc_18009FD0E
0x18009fcca  xor     esi, esi
0x18009fccc  mov     rdx, rax; SelfRelativeSD
0x18009fccf  mov     [rbx+0Ch], edi
0x18009fcd2  mov     rcx, rbp; AbsoluteSD
0x18009fcd5  call    cs:__imp_RtlMakeSelfRelativeSD
0x18009fcdb  mov     ecx, eax; Status
0x18009fcdd  call    cs:__imp_RtlNtStatusToDosError
0x18009fce3  mov     edi, eax
0x18009fce5  test    eax, eax
0x18009fce7  jz      short loc_18009FD05
0x18009fce9  test    esi, esi
0x18009fceb  jz      short loc_18009FD05
0x18009fced  mov     rcx, gs:60h
0x18009fcf6  xor     edx, edx; Flags
0x18009fcf8  mov     r8, [rbx]; P
0x18009fcfb  mov     rcx, [rcx+30h]; HeapHandle
0x18009fcff  call    cs:__imp_RtlFreeHeap
0x18009fd05  mov     eax, edi
0x18009fd07  jmp     short loc_18009FD0E
0x18009fd09  mov     eax, 57h ; 'W'
0x18009fd0e  add     rsp, 28h
0x18009fd12  pop     rdi
0x18009fd13  pop     rsi
0x18009fd14  pop     rbp
0x18009fd15  pop     rbx
0x18009fd16  retn
```
