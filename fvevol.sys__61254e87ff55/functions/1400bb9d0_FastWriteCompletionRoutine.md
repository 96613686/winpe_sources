# FastWriteCompletionRoutine

- ea: `0x1400bb9d0`
- end: `0x1400bbae7`
- name: `FastWriteCompletionRoutine`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bbaf0`

## callees

- `0x140009fc0`
- `0x14002a4e4`
- `0x14002d140`
- `0x1400bb9d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bba71`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bba71`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bba3d`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bba3d`
- `ntoskrnl!KeBugCheckEx` at `0x1400bba9b`
- `ntoskrnl!KeBugCheckEx` at `0x1400bba9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbab0`

## pseudocode

```c
__int64 __fastcall FastWriteCompletionRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  __int64 v6; // rsi
  void *v7; // rbx
  int v8; // r15d
  char v9; // al
  __int64 v10; // rcx
  int v11; // ebx

  v4 = *(_QWORD *)(a1 + 64);
  *(_QWORD *)(a3 + 8) = MEMORY[0xFFFFF78000000008];
  v6 = *(_QWORD *)(a2 + 8);
  v7 = (void *)(*(_QWORD *)(v6 + 32) + *(unsigned int *)(v6 + 44));
  *(_QWORD *)(a2 + 8) = *(_QWORD *)(a3 + 56);
  FvePerfTraceDevPtr(v4, FVE_PERF_WRITE_SUBREQUEST_STOP, a2);
  FvePerfTraceDevPtr(v4, FVE_PERF_WRITE_REQUEST_STOP, a2);
  v8 = *(_DWORD *)(a3 + 40);
  if ( (*(_BYTE *)(v6 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v6 + 24), (PMDL)v6);
  v9 = *(_BYTE *)(a3 + 44);
  if ( v9 == 1 )
  {
    v10 = *(_QWORD *)(v4 + 2024);
    if ( v10 )
      PplFreeToLookasideListProcessor(v10, v7, *(_DWORD *)(a3 + 48));
    else
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v4 + 2016), v7);
  }
  else
  {
    if ( v9 != 2 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    ExFreePoolWithTag(v7, 0x70455646u);
  }
  v11 = *(_DWORD *)(v4 + 840);
  FvepInformRundownFinishedWithDisk(v4, a2, v8);
  return v11 != 0 ? 0xC0000016 : 0;
}

```

## disassembly

```asm
0x1400bb9d0  push    rbx
0x1400bb9d2  push    rbp
0x1400bb9d3  push    rsi
0x1400bb9d4  push    rdi
0x1400bb9d5  push    r14
0x1400bb9d7  push    r15
0x1400bb9d9  sub     rsp, 38h
0x1400bb9dd  mov     rax, ds:0FFFFF78000000008h
0x1400bb9e7  mov     rbp, r8
0x1400bb9ea  mov     rdi, [rcx+40h]
0x1400bb9ee  mov     r14, rdx
0x1400bb9f1  mov     [r8+8], rax
0x1400bb9f5  mov     rcx, rdi
0x1400bb9f8  mov     rsi, [rdx+8]
0x1400bb9fc  mov     rax, [r8+38h]
0x1400bba00  mov     r8, rdx
0x1400bba03  mov     ebx, [rsi+2Ch]
0x1400bba06  add     rbx, [rsi+20h]
0x1400bba0a  mov     [rdx+8], rax
0x1400bba0e  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_STOP
0x1400bba15  call    FvePerfTraceDevPtr
0x1400bba1a  mov     r8, r14
0x1400bba1d  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400bba24  mov     rcx, rdi
0x1400bba27  call    FvePerfTraceDevPtr
0x1400bba2c  test    byte ptr [rsi+0Ah], 20h
0x1400bba30  mov     r15d, [rbp+28h]
0x1400bba34  jz      short loc_1400BBA49
0x1400bba36  mov     rcx, [rsi+18h]; BaseAddress
0x1400bba3a  mov     rdx, rsi; MemoryDescriptorList
0x1400bba3d  call    cs:__imp_MmUnmapLockedPages
0x1400bba44  nop     dword ptr [rax+rax+00h]
0x1400bba49  mov     al, [rbp+2Ch]
0x1400bba4c  cmp     al, 1
0x1400bba4e  jnz     short loc_1400BBA7F
0x1400bba50  mov     rcx, [rdi+7E8h]
0x1400bba57  mov     rdx, rbx; Entry
0x1400bba5a  test    rcx, rcx
0x1400bba5d  jz      short loc_1400BBA6A
0x1400bba5f  mov     r8d, [rbp+30h]
0x1400bba63  call    PplFreeToLookasideListProcessor
0x1400bba68  jmp     short loc_1400BBABC
0x1400bba6a  mov     rcx, [rdi+7E0h]; Lookaside
0x1400bba71  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400bba78  nop     dword ptr [rax+rax+00h]
0x1400bba7d  jmp     short loc_1400BBABC
0x1400bba7f  cmp     al, 2
0x1400bba81  jz      short loc_1400BBAA8
0x1400bba83  xor     r9d, r9d; BugCheckParameter3
0x1400bba86  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x1400bba8f  xor     r8d, r8d; BugCheckParameter2
0x1400bba92  mov     ecx, 120h; BugCheckCode
0x1400bba97  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400bba9b  call    cs:__imp_KeBugCheckEx
0x1400bbaa8  mov     edx, 70455646h; Tag
0x1400bbaad  mov     rcx, rbx; P
0x1400bbab0  call    cs:__imp_ExFreePoolWithTag
0x1400bbab7  nop     dword ptr [rax+rax+00h]
0x1400bbabc  mov     ebx, [rdi+348h]
0x1400bbac2  mov     r8b, r15b
0x1400bbac5  mov     rdx, r14
0x1400bbac8  mov     rcx, rdi
0x1400bbacb  call    FvepInformRundownFinishedWithDisk
0x1400bbad0  neg     ebx
0x1400bbad2  sbb     eax, eax
0x1400bbad4  and     eax, 0C0000016h
0x1400bbad9  add     rsp, 38h
0x1400bbadd  pop     r15
0x1400bbadf  pop     r14
0x1400bbae1  pop     rdi
0x1400bbae2  pop     rsi
0x1400bbae3  pop     rbp
0x1400bbae4  pop     rbx
0x1400bbae5  retn
```
