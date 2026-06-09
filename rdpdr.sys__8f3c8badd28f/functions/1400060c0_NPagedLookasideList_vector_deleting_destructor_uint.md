# NPagedLookasideList::`vector deleting destructor'(uint)

- ea: `0x1400060c0`
- end: `0x1400060f7`
- name: `??_ENPagedLookasideList@@UEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(PVOID P, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140006044`
- `0x1400060c0`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x1400060dc`
- `ntoskrnl!ExFreePool` at `0x1400060dc`

## pseudocode

```c
NPagedLookasideList *__fastcall NPagedLookasideList::`vector deleting destructor'(NPagedLookasideList *P, char a2)
{
  NPagedLookasideList::~NPagedLookasideList(P);
  if ( (a2 & 1) != 0 )
    ExFreePool(P);
  return P;
}

```

## disassembly

```asm
0x1400060c0  mov     [rsp+arg_0], rbx
0x1400060c5  push    rdi
0x1400060c6  sub     rsp, 20h
0x1400060ca  mov     ebx, edx
0x1400060cc  mov     rdi, rcx
0x1400060cf  call    ??1NPagedLookasideList@@UEAA@XZ; NPagedLookasideList::~NPagedLookasideList(void)
0x1400060d4  test    bl, 1
0x1400060d7  jz      short loc_1400060E8
0x1400060d9  mov     rcx, rdi; P
0x1400060dc  call    cs:__imp_ExFreePool
0x1400060e3  nop     dword ptr [rax+rax+00h]
0x1400060e8  mov     rbx, [rsp+28h+arg_0]
0x1400060ed  mov     rax, rdi
0x1400060f0  add     rsp, 20h
0x1400060f4  pop     rdi
0x1400060f5  retn
```
