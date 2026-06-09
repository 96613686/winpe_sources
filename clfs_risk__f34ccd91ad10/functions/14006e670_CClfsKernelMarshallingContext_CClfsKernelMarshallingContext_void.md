# CClfsKernelMarshallingContext::~CClfsKernelMarshallingContext(void)

- ea: `0x14006e670`
- end: `0x14006e7de`
- name: `??1CClfsKernelMarshallingContext@@QEAA@XZ`
- size: `366`
- prototype: `void __fastcall(CClfsKernelMarshallingContext *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400577c0`
- `0x14006e4b4`

## callees

- `0x14006e670`
- `0x14006e7e4`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14006e6a2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14006e6da`
- `ntoskrnl!ExDeleteResourceLite` at `0x14006e6a2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14006e6da`
- `ntoskrnl!ObfDereferenceObject` at `0x14006e7b9`
- `ntoskrnl!ObfDereferenceObject` at `0x14006e7b9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006e79f`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14006e79f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14006e71a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14006e752`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14006e71a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14006e752`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e72f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e767`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e72f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e767`

## pseudocode

```c
void __fastcall CClfsKernelMarshallingContext::~CClfsKernelMarshallingContext(
        CClfsKernelMarshallingContext *this,
        __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v7; // rcx
  int v8; // eax
  struct _PAGED_LOOKASIDE_LIST *v9; // rcx
  struct _PAGED_LOOKASIDE_LIST *v10; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v11; // rcx
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 10) + *((_QWORD *)this + 12);
  v4 = *((_QWORD *)this + 1);
  v5 = -v3;
  v12 = v5;
  if ( v4 )
  {
    if ( v5 < 0 )
      ClfsFreeReservedLogInternal(v4, a2, &v12);
    ObfDereferenceObject(*((PVOID *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  v6 = (struct _ERESOURCE *)*((_QWORD *)this + 17);
  if ( v6 )
  {
    ExDeleteResourceLite(v6);
    ExFreePoolWithTag(*((PVOID *)this + 17), 0);
    *((_QWORD *)this + 17) = 0;
  }
  v7 = (struct _ERESOURCE *)*((_QWORD *)this + 18);
  if ( v7 )
  {
    ExDeleteResourceLite(v7);
    ExFreePoolWithTag(*((PVOID *)this + 18), 0);
    *((_QWORD *)this + 18) = 0;
  }
  v8 = *((_DWORD *)this + 4);
  if ( v8 == 1 )
  {
    v9 = (struct _PAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 22);
    if ( !v9 )
      goto LABEL_10;
    ExDeletePagedLookasideList(v9);
    goto LABEL_9;
  }
  if ( v8 == 512 )
  {
    v11 = (struct _NPAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 22);
    if ( v11 )
    {
      ExDeleteNPagedLookasideList(v11);
LABEL_9:
      ExFreePoolWithTag(*((PVOID *)this + 22), 0);
      *((_QWORD *)this + 22) = 0;
    }
  }
LABEL_10:
  v10 = (struct _PAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 21);
  if ( v10 )
  {
    ExDeletePagedLookasideList(v10);
    ExFreePoolWithTag(*((PVOID *)this + 21), 0);
    *((_QWORD *)this + 21) = 0;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x14006e670  push    rbx
0x14006e672  sub     rsp, 20h
0x14006e676  mov     rax, [rcx+60h]
0x14006e67a  mov     rbx, rcx
0x14006e67d  add     rax, [rcx+50h]
0x14006e681  mov     rcx, [rcx+8]
0x14006e685  neg     rax
0x14006e688  mov     [rsp+28h+arg_0], rax
0x14006e68d  test    rcx, rcx
0x14006e690  jnz     loc_14006E7B0
0x14006e696  mov     rcx, [rbx+88h]; Resource
0x14006e69d  test    rcx, rcx
0x14006e6a0  jz      short loc_14006E6CE
0x14006e6a2  call    cs:__imp_ExDeleteResourceLite
0x14006e6a9  nop     dword ptr [rax+rax+00h]
0x14006e6ae  mov     rcx, [rbx+88h]; P
0x14006e6b5  xor     edx, edx; Tag
0x14006e6b7  call    cs:__imp_ExFreePoolWithTag
0x14006e6be  nop     dword ptr [rax+rax+00h]
0x14006e6c3  mov     qword ptr [rbx+88h], 0
0x14006e6ce  mov     rcx, [rbx+90h]; Resource
0x14006e6d5  test    rcx, rcx
0x14006e6d8  jz      short loc_14006E706
0x14006e6da  call    cs:__imp_ExDeleteResourceLite
0x14006e6e1  nop     dword ptr [rax+rax+00h]
0x14006e6e6  mov     rcx, [rbx+90h]; P
0x14006e6ed  xor     edx, edx; Tag
0x14006e6ef  call    cs:__imp_ExFreePoolWithTag
0x14006e6f6  nop     dword ptr [rax+rax+00h]
0x14006e6fb  mov     qword ptr [rbx+90h], 0
0x14006e706  mov     eax, [rbx+10h]
0x14006e709  cmp     eax, 1
0x14006e70c  jnz     short loc_14006E78C
0x14006e70e  mov     rcx, [rbx+0B0h]; Lookaside
0x14006e715  test    rcx, rcx
0x14006e718  jz      short loc_14006E746
0x14006e71a  call    cs:__imp_ExDeletePagedLookasideList
0x14006e721  nop     dword ptr [rax+rax+00h]
0x14006e726  mov     rcx, [rbx+0B0h]; P
0x14006e72d  xor     edx, edx; Tag
0x14006e72f  call    cs:__imp_ExFreePoolWithTag
0x14006e736  nop     dword ptr [rax+rax+00h]
0x14006e73b  mov     qword ptr [rbx+0B0h], 0
0x14006e746  mov     rcx, [rbx+0A8h]; Lookaside
0x14006e74d  test    rcx, rcx
0x14006e750  jz      short loc_14006E77E
0x14006e752  call    cs:__imp_ExDeletePagedLookasideList
0x14006e759  nop     dword ptr [rax+rax+00h]
0x14006e75e  mov     rcx, [rbx+0A8h]; P
0x14006e765  xor     edx, edx; Tag
0x14006e767  call    cs:__imp_ExFreePoolWithTag
0x14006e76e  nop     dword ptr [rax+rax+00h]
0x14006e773  mov     qword ptr [rbx+0A8h], 0
0x14006e77e  mov     qword ptr [rbx], 0
0x14006e785  add     rsp, 20h
0x14006e789  pop     rbx
0x14006e78a  retn
0x14006e78c  cmp     eax, 200h
0x14006e791  jnz     short loc_14006E746
0x14006e793  mov     rcx, [rbx+0B0h]; Lookaside
0x14006e79a  test    rcx, rcx
0x14006e79d  jz      short loc_14006E746
0x14006e79f  call    cs:__imp_ExDeleteNPagedLookasideList
0x14006e7a6  nop     dword ptr [rax+rax+00h]
0x14006e7ab  jmp     loc_14006E726
0x14006e7b0  test    rax, rax
0x14006e7b3  js      short loc_14006E7D2
0x14006e7b5  mov     rcx, [rbx+8]; Object
0x14006e7b9  call    cs:__imp_ObfDereferenceObject
0x14006e7c0  nop     dword ptr [rax+rax+00h]
0x14006e7c5  mov     qword ptr [rbx+8], 0
0x14006e7cd  jmp     loc_14006E696
0x14006e7d2  lea     r8, [rsp+28h+arg_0]
0x14006e7d7  call    ClfsFreeReservedLogInternal
0x14006e7dc  jmp     short loc_14006E7B5
```
