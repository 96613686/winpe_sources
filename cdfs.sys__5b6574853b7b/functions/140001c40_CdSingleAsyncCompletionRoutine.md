# CdSingleAsyncCompletionRoutine

- ea: `0x140001c40`
- end: `0x140001c98`
- name: `CdSingleAsyncCompletionRoutine`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001c40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c83`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140001c72`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140001c72`

## pseudocode

```c
__int64 __fastcall CdSingleAsyncCompletionRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // sf

  v3 = *(int *)(a2 + 48) < 0;
  *(_QWORD *)(a2 + 56) = 0;
  if ( !v3 )
    *(_QWORD *)(a2 + 56) = *(unsigned int *)(a3 + 40);
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  ExReleaseResourceForThreadLite(*(PERESOURCE *)(a3 + 24), *(_QWORD *)(a3 + 32));
  ExFreePoolWithTag((PVOID)a3, 0);
  return 0;
}

```

## disassembly

```asm
0x140001c40  push    rbx
0x140001c42  sub     rsp, 20h
0x140001c46  cmp     dword ptr [rdx+30h], 0
0x140001c4a  mov     rbx, r8
0x140001c4d  mov     qword ptr [rdx+38h], 0
0x140001c55  jl      short loc_140001C5F
0x140001c57  mov     eax, [r8+28h]
0x140001c5b  mov     [rdx+38h], rax
0x140001c5f  mov     rax, [rdx+0B8h]
0x140001c66  or      byte ptr [rax+3], 1
0x140001c6a  mov     rdx, [r8+20h]; ResourceThreadId
0x140001c6e  mov     rcx, [r8+18h]; Resource
0x140001c72  call    cs:__imp_ExReleaseResourceForThreadLite
0x140001c79  nop     dword ptr [rax+rax+00h]
0x140001c7e  xor     edx, edx; Tag
0x140001c80  mov     rcx, rbx; P
0x140001c83  call    cs:__imp_ExFreePoolWithTag
0x140001c8a  nop     dword ptr [rax+rax+00h]
0x140001c8f  xor     eax, eax
0x140001c91  add     rsp, 20h
0x140001c95  pop     rbx
0x140001c96  retn
```
