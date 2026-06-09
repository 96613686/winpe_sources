# FastWriteCompletionRoutine

- ea: `0x1400b9900`
- end: `0x1400b9a17`
- name: `FastWriteCompletionRoutine`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b9a20`

## callees

- `0x140009f00`
- `0x1400294e4`
- `0x14002c140`
- `0x1400b9900`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b99a1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b99a1`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400b996d`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400b996d`
- `ntoskrnl!KeBugCheckEx` at `0x1400b99cb`
- `ntoskrnl!KeBugCheckEx` at `0x1400b99cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b99e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b99e0`

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
0x1400b9900  push    rbx
0x1400b9902  push    rbp
0x1400b9903  push    rsi
0x1400b9904  push    rdi
0x1400b9905  push    r14
0x1400b9907  push    r15
0x1400b9909  sub     rsp, 38h
0x1400b990d  mov     rax, ds:0FFFFF78000000008h
0x1400b9917  mov     rbp, r8
0x1400b991a  mov     rdi, [rcx+40h]
0x1400b991e  mov     r14, rdx
0x1400b9921  mov     [r8+8], rax
0x1400b9925  mov     rcx, rdi
0x1400b9928  mov     rsi, [rdx+8]
0x1400b992c  mov     rax, [r8+38h]
0x1400b9930  mov     r8, rdx
0x1400b9933  mov     ebx, [rsi+2Ch]
0x1400b9936  add     rbx, [rsi+20h]
0x1400b993a  mov     [rdx+8], rax
0x1400b993e  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_STOP
0x1400b9945  call    FvePerfTraceDevPtr
0x1400b994a  mov     r8, r14
0x1400b994d  lea     rdx, FVE_PERF_WRITE_REQUEST_STOP
0x1400b9954  mov     rcx, rdi
0x1400b9957  call    FvePerfTraceDevPtr
0x1400b995c  test    byte ptr [rsi+0Ah], 20h
0x1400b9960  mov     r15d, [rbp+28h]
0x1400b9964  jz      short loc_1400B9979
0x1400b9966  mov     rcx, [rsi+18h]; BaseAddress
0x1400b996a  mov     rdx, rsi; MemoryDescriptorList
0x1400b996d  call    cs:__imp_MmUnmapLockedPages
0x1400b9974  nop     dword ptr [rax+rax+00h]
0x1400b9979  mov     al, [rbp+2Ch]
0x1400b997c  cmp     al, 1
0x1400b997e  jnz     short loc_1400B99AF
0x1400b9980  mov     rcx, [rdi+7E8h]
0x1400b9987  mov     rdx, rbx; Entry
0x1400b998a  test    rcx, rcx
0x1400b998d  jz      short loc_1400B999A
0x1400b998f  mov     r8d, [rbp+30h]
0x1400b9993  call    PplFreeToLookasideListProcessor
0x1400b9998  jmp     short loc_1400B99EC
0x1400b999a  mov     rcx, [rdi+7E0h]; Lookaside
0x1400b99a1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b99a8  nop     dword ptr [rax+rax+00h]
0x1400b99ad  jmp     short loc_1400B99EC
0x1400b99af  cmp     al, 2
0x1400b99b1  jz      short loc_1400B99D8
0x1400b99b3  xor     r9d, r9d; BugCheckParameter3
0x1400b99b6  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x1400b99bf  xor     r8d, r8d; BugCheckParameter2
0x1400b99c2  mov     ecx, 120h; BugCheckCode
0x1400b99c7  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400b99cb  call    cs:__imp_KeBugCheckEx
0x1400b99d8  mov     edx, 70455646h; Tag
0x1400b99dd  mov     rcx, rbx; P
0x1400b99e0  call    cs:__imp_ExFreePoolWithTag
0x1400b99e7  nop     dword ptr [rax+rax+00h]
0x1400b99ec  mov     ebx, [rdi+348h]
0x1400b99f2  mov     r8b, r15b
0x1400b99f5  mov     rdx, r14
0x1400b99f8  mov     rcx, rdi
0x1400b99fb  call    FvepInformRundownFinishedWithDisk
0x1400b9a00  neg     ebx
0x1400b9a02  sbb     eax, eax
0x1400b9a04  and     eax, 0C0000016h
0x1400b9a09  add     rsp, 38h
0x1400b9a0d  pop     r15
0x1400b9a0f  pop     r14
0x1400b9a11  pop     rdi
0x1400b9a12  pop     rsi
0x1400b9a13  pop     rbp
0x1400b9a14  pop     rbx
0x1400b9a15  retn
```
