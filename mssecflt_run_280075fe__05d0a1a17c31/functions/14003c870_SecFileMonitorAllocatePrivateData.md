# SecFileMonitorAllocatePrivateData

- ea: `0x14003c870`
- end: `0x14003c910`
- name: `SecFileMonitorAllocatePrivateData`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14003c828`

## callees

- `0x140011610`
- `0x1400119c0`
- `0x14003c870`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003c8ef`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003c8ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c8a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c8a3`

## pseudocode

```c
__int64 SecFileMonitorAllocatePrivateData()
{
  unsigned int v0; // ebx
  struct _PAGED_LOOKASIDE_LIST *PoolWithTag; // rax
  struct _PAGED_LOOKASIDE_LIST *v2; // rdi

  v0 = 0;
  if ( qword_140020008 )
    PoolWithTag = (struct _PAGED_LOOKASIDE_LIST *)qword_140020008(64, 128, 1833329491);
  else
    PoolWithTag = (struct _PAGED_LOOKASIDE_LIST *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x80u, 0x6D466353u);
  v2 = PoolWithTag;
  if ( PoolWithTag )
  {
    memset(PoolWithTag, 0, sizeof(struct _PAGED_LOOKASIDE_LIST));
    ExInitializePagedLookasideList(v2, 0, 0, 0, 0x28u, 0x6D466353u, 0);
    SecFileMonDataPrivate = v2;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v0;
}

```

## disassembly

```asm
0x14003c870  mov     [rsp+arg_0], rbx
0x14003c875  push    rdi
0x14003c876  sub     rsp, 40h
0x14003c87a  mov     rax, cs:qword_140020008
0x14003c881  xor     ebx, ebx
0x14003c883  mov     edx, 80h; NumberOfBytes
0x14003c888  mov     r8d, 6D466353h; Tag
0x14003c88e  test    rax, rax
0x14003c891  jz      short loc_14003C89E
0x14003c893  lea     ecx, [rbx+40h]
0x14003c896  call    cs:__guard_dispatch_icall_fptr
0x14003c89c  jmp     short loc_14003C8AF
0x14003c89e  mov     ecx, 200h; PoolType
0x14003c8a3  call    cs:__imp_ExAllocatePoolWithTag
0x14003c8aa  nop     dword ptr [rax+rax+00h]
0x14003c8af  mov     rdi, rax
0x14003c8b2  test    rax, rax
0x14003c8b5  jnz     short loc_14003C8BE
0x14003c8b7  mov     ebx, 0C000009Ah
0x14003c8bc  jmp     short loc_14003C902
0x14003c8be  xor     edx, edx; Val
0x14003c8c0  mov     r8d, 80h; Size
0x14003c8c6  mov     rcx, rdi; void *
0x14003c8c9  call    memset
0x14003c8ce  mov     [rsp+48h+Depth], bx; Depth
0x14003c8d3  xor     r9d, r9d; Flags
0x14003c8d6  mov     [rsp+48h+Tag], 6D466353h; Tag
0x14003c8de  xor     r8d, r8d; Free
0x14003c8e1  xor     edx, edx; Allocate
0x14003c8e3  mov     [rsp+48h+Size], 28h ; '('; Size
0x14003c8ec  mov     rcx, rdi; Lookaside
0x14003c8ef  call    cs:__imp_ExInitializePagedLookasideList
0x14003c8f6  nop     dword ptr [rax+rax+00h]
0x14003c8fb  mov     cs:SecFileMonDataPrivate, rdi
0x14003c902  mov     eax, ebx
0x14003c904  mov     rbx, [rsp+48h+arg_0]
0x14003c909  add     rsp, 40h
0x14003c90d  pop     rdi
0x14003c90e  retn
```
