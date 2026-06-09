# ndisAllocateMdlInternal(ulong *)

- ea: `0x14004fbb0`
- end: `0x14004fc9f`
- name: `?ndisAllocateMdlInternal@@YAPEAU_MDL@@PEAK@Z`
- size: `239`
- prototype: `PMDL __stdcall(PULONG BufferSize)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140030bc0`

## callees

- `0x14004fbb0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14004fbcb`
- `ntoskrnl!MmSizeOfMdl` at `0x14004fbea`
- `ntoskrnl!MmSizeOfMdl` at `0x14004fbcb`
- `ntoskrnl!MmSizeOfMdl` at `0x14004fbea`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004fc7b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14004fc7b`
- `ntoskrnl!ExAllocatePool2` at `0x14004fc12`
- `ntoskrnl!ExAllocatePool2` at `0x14004fc12`

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
0x14004fbb0  mov     [rsp+arg_0], rbx
0x14004fbb5  mov     [rsp+arg_8], rsi
0x14004fbba  push    rdi
0x14004fbbb  sub     rsp, 20h
0x14004fbbf  mov     edi, [rcx]
0x14004fbc1  mov     rsi, rcx
0x14004fbc4  mov     edx, edi; Length
0x14004fbc6  mov     ecx, 0FFFh; Base
0x14004fbcb  call    cs:__imp_MmSizeOfMdl
0x14004fbd2  nop     dword ptr [rax+rax+00h]
0x14004fbd7  mov     ebx, 7
0x14004fbdc  mov     edx, edi; Length
0x14004fbde  dec     eax
0x14004fbe0  mov     ecx, 0FFFh; Base
0x14004fbe5  and     eax, 7
0x14004fbe8  sub     ebx, eax
0x14004fbea  call    cs:__imp_MmSizeOfMdl
0x14004fbf1  nop     dword ptr [rax+rax+00h]
0x14004fbf6  mov     ecx, [rsi]
0x14004fbf8  lea     edi, [rax+rbx]
0x14004fbfb  add     ecx, edi
0x14004fbfd  cmp     ecx, edi
0x14004fbff  jb      loc_14004FC9B
0x14004fc05  mov     edx, ecx
0x14004fc07  mov     r8d, 646E444Eh
0x14004fc0d  mov     ecx, 42h ; 'B'
0x14004fc12  call    cs:__imp_ExAllocatePool2
0x14004fc19  nop     dword ptr [rax+rax+00h]
0x14004fc1e  mov     rbx, rax
0x14004fc21  test    rax, rax
0x14004fc24  jz      short loc_14004FC9B
0x14004fc26  mov     r9d, [rsi]
0x14004fc29  mov     qword ptr [rax], 0
0x14004fc30  mov     r8d, edi
0x14004fc33  add     r8, rax
0x14004fc36  mov     [rbx+28h], r9d
0x14004fc3a  mov     edx, r8d
0x14004fc3d  lea     rcx, [r9+0FFFh]
0x14004fc44  mov     eax, edx
0x14004fc46  and     r8, 0FFFFFFFFFFFFF000h
0x14004fc4d  and     eax, 0FFFh
0x14004fc52  mov     [rbx+20h], r8
0x14004fc56  add     rcx, rax
0x14004fc59  and     edx, 0FFFh
0x14004fc5f  shr     rcx, 0Ch
0x14004fc63  xor     eax, eax
0x14004fc65  add     cx, 6
0x14004fc69  mov     [rbx+0Ah], ax
0x14004fc6d  shl     cx, 3
0x14004fc71  mov     [rbx+8], cx
0x14004fc75  mov     rcx, rbx; MemoryDescriptorList
0x14004fc78  mov     [rbx+2Ch], edx
0x14004fc7b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14004fc82  nop     dword ptr [rax+rax+00h]
0x14004fc87  mov     rax, rbx
0x14004fc8a  mov     rbx, [rsp+28h+arg_0]
0x14004fc8f  mov     rsi, [rsp+28h+arg_8]
0x14004fc94  add     rsp, 20h
0x14004fc98  pop     rdi
0x14004fc99  retn
0x14004fc9b  xor     eax, eax
0x14004fc9d  jmp     short loc_14004FC8A
```
