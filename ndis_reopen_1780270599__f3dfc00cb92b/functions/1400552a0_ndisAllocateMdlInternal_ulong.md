# ndisAllocateMdlInternal(ulong *)

- ea: `0x1400552a0`
- end: `0x14005538f`
- name: `?ndisAllocateMdlInternal@@YAPEAU_MDL@@PEAK@Z`
- size: `239`
- prototype: `PMDL __stdcall(PULONG BufferSize)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140030860`

## callees

- `0x1400552a0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400552bb`
- `ntoskrnl!MmSizeOfMdl` at `0x1400552da`
- `ntoskrnl!MmSizeOfMdl` at `0x1400552bb`
- `ntoskrnl!MmSizeOfMdl` at `0x1400552da`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005536b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005536b`
- `ntoskrnl!ExAllocatePool2` at `0x140055302`
- `ntoskrnl!ExAllocatePool2` at `0x140055302`

## pseudocode

```c
PMDL __fastcall ndisAllocateMdlInternal(unsigned int *BufferSize)
{
  unsigned int v1; // edi
  int v3; // ebx
  ULONG v4; // edi
  ULONG v5; // ecx
  struct _MDL *Pool2; // rax
  struct _MDL *v7; // rbx
  __int64 v8; // r9

  v1 = *BufferSize;
  v3 = 7 - (((unsigned __int8)MmSizeOfMdl((PVOID)0xFFF, *BufferSize) - 1) & 7);
  v4 = MmSizeOfMdl((PVOID)0xFFF, v1) + v3;
  v5 = v4 + *BufferSize;
  if ( v5 < v4 )
    return 0;
  Pool2 = (struct _MDL *)ExAllocatePool2(66, v5, 1684948046);
  v7 = Pool2;
  if ( !Pool2 )
    return 0;
  v8 = *BufferSize;
  Pool2->Next = 0;
  Pool2->ByteCount = v8;
  Pool2->StartVa = (PVOID)(((unsigned __int64)Pool2 + v4) & 0xFFFFFFFFFFFFF000uLL);
  Pool2->MdlFlags = 0;
  Pool2->Size = 8 * ((((unsigned __int64)(((_WORD)Pool2 + (_WORD)v4) & 0xFFF) + v8 + 4095) >> 12) + 6);
  Pool2->ByteOffset = ((_WORD)Pool2 + (_WORD)v4) & 0xFFF;
  MmBuildMdlForNonPagedPool(Pool2);
  return v7;
}

```

## disassembly

```asm
0x1400552a0  mov     [rsp+arg_0], rbx
0x1400552a5  mov     [rsp+arg_8], rsi
0x1400552aa  push    rdi
0x1400552ab  sub     rsp, 20h
0x1400552af  mov     edi, [rcx]
0x1400552b1  mov     rsi, rcx
0x1400552b4  mov     edx, edi; Length
0x1400552b6  mov     ecx, 0FFFh; Base
0x1400552bb  call    cs:__imp_MmSizeOfMdl
0x1400552c2  nop     dword ptr [rax+rax+00h]
0x1400552c7  mov     ebx, 7
0x1400552cc  mov     edx, edi; Length
0x1400552ce  dec     eax
0x1400552d0  mov     ecx, 0FFFh; Base
0x1400552d5  and     eax, 7
0x1400552d8  sub     ebx, eax
0x1400552da  call    cs:__imp_MmSizeOfMdl
0x1400552e1  nop     dword ptr [rax+rax+00h]
0x1400552e6  mov     ecx, [rsi]
0x1400552e8  lea     edi, [rax+rbx]
0x1400552eb  add     ecx, edi
0x1400552ed  cmp     ecx, edi
0x1400552ef  jb      loc_14005538B
0x1400552f5  mov     edx, ecx
0x1400552f7  mov     r8d, 646E444Eh
0x1400552fd  mov     ecx, 42h ; 'B'
0x140055302  call    cs:__imp_ExAllocatePool2
0x140055309  nop     dword ptr [rax+rax+00h]
0x14005530e  mov     rbx, rax
0x140055311  test    rax, rax
0x140055314  jz      short loc_14005538B
0x140055316  mov     r9d, [rsi]
0x140055319  mov     qword ptr [rax], 0
0x140055320  mov     r8d, edi
0x140055323  add     r8, rax
0x140055326  mov     [rbx+28h], r9d
0x14005532a  mov     edx, r8d
0x14005532d  lea     rcx, [r9+0FFFh]
0x140055334  mov     eax, edx
0x140055336  and     r8, 0FFFFFFFFFFFFF000h
0x14005533d  and     eax, 0FFFh
0x140055342  mov     [rbx+20h], r8
0x140055346  add     rcx, rax
0x140055349  and     edx, 0FFFh
0x14005534f  shr     rcx, 0Ch
0x140055353  xor     eax, eax
0x140055355  add     cx, 6
0x140055359  mov     [rbx+0Ah], ax
0x14005535d  shl     cx, 3
0x140055361  mov     [rbx+8], cx
0x140055365  mov     rcx, rbx; MemoryDescriptorList
0x140055368  mov     [rbx+2Ch], edx
0x14005536b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140055372  nop     dword ptr [rax+rax+00h]
0x140055377  mov     rax, rbx
0x14005537a  mov     rbx, [rsp+28h+arg_0]
0x14005537f  mov     rsi, [rsp+28h+arg_8]
0x140055384  add     rsp, 20h
0x140055388  pop     rdi
0x140055389  retn
0x14005538b  xor     eax, eax
0x14005538d  jmp     short loc_14005537A
```
