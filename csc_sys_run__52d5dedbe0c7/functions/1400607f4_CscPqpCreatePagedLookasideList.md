# CscPqpCreatePagedLookasideList

- ea: `0x1400607f4`
- end: `0x140060867`
- name: `CscPqpCreatePagedLookasideList`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004635c`

## callees

- `0x1400607f4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140060812`
- `ntoskrnl!ExAllocatePool2` at `0x140060812`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140060852`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140060852`

## pseudocode

```c
__int64 __fastcall CscPqpCreatePagedLookasideList(
        struct _PAGED_LOOKASIDE_LIST **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  struct _PAGED_LOOKASIDE_LIST *Pool2; // rax
  unsigned int v6; // ebx

  *a1 = 0;
  Pool2 = (struct _PAGED_LOOKASIDE_LIST *)ExAllocatePool2(66, 128, 608203587, a4);
  *a1 = Pool2;
  if ( Pool2 )
  {
    v6 = 0;
    ExInitializePagedLookasideList(Pool2, 0, 0, 0, 0xD0u, 0x24407343u, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v6;
}

```

## disassembly

```asm
0x1400607f4  push    rbx
0x1400607f6  sub     rsp, 40h
0x1400607fa  mov     edx, 80h
0x1400607ff  mov     qword ptr [rcx], 0
0x140060806  mov     rbx, rcx
0x140060809  mov     r8d, 24407343h
0x14006080f  lea     ecx, [rdx-3Eh]
0x140060812  call    cs:__imp_ExAllocatePool2
0x140060819  nop     dword ptr [rax+rax+00h]
0x14006081e  mov     [rbx], rax
0x140060821  test    rax, rax
0x140060824  jnz     short loc_14006082D
0x140060826  mov     ebx, 0C000009Ah
0x14006082b  jmp     short loc_14006085E
0x14006082d  xor     ecx, ecx
0x14006082f  xor     ebx, ebx
0x140060831  mov     [rsp+48h+Depth], cx; Depth
0x140060836  xor     r9d, r9d; Flags
0x140060839  mov     [rsp+48h+Tag], 24407343h; Tag
0x140060841  mov     rcx, rax; Lookaside
0x140060844  xor     r8d, r8d; Free
0x140060847  mov     [rsp+48h+Size], 0D0h; Size
0x140060850  xor     edx, edx; Allocate
0x140060852  call    cs:__imp_ExInitializePagedLookasideList
0x140060859  nop     dword ptr [rax+rax+00h]
0x14006085e  mov     eax, ebx
0x140060860  add     rsp, 40h
0x140060864  pop     rbx
0x140060865  retn
```
