# FsbAllocateAtDpcLevel

- ea: `0x14002c034`
- end: `0x14002c1db`
- name: `FsbAllocateAtDpcLevel`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002bfe0`

## callees

- `0x14002c034`
- `0x14002c1e4`
- `0x14002c29c`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002c095`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002c095`
- `ntoskrnl!ExQueryDepthSList` at `0x14002c0c7`
- `ntoskrnl!ExQueryDepthSList` at `0x14002c0c7`
- `ntoskrnl!InitializeSListHead` at `0x14002c17e`
- `ntoskrnl!InitializeSListHead` at `0x14002c17e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002c048`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002c048`
- `ntoskrnl!ExAllocatePool3` at `0x14002c156`
- `ntoskrnl!ExAllocatePool3` at `0x14002c156`

## pseudocode

```c
__int64 __fastcall FsbAllocateAtDpcLevel(unsigned int *a1)
{
  ULONGLONG **v2; // rbx
  ULONGLONG *v3; // rax
  union _SLIST_HEADER *v4; // rbp
  PSLIST_ENTRY v5; // rdi
  __int64 Block; // rdi
  ULONGLONG *v7; // rax
  ULONGLONG *v8; // rcx
  ULONGLONG *v9; // rbx
  ULONGLONG **v10; // rcx
  __int64 v11; // r8
  union _SLIST_HEADER *Pool3; // rax
  union _SLIST_HEADER *v13; // r15
  ULONGLONG v14; // rcx
  _QWORD v16[9]; // [rsp+30h] [rbp-48h] BYREF

  v2 = (ULONGLONG **)&a1[16 * KeGetCurrentProcessorNumberEx(0) + 16];
  if ( MEMORY[0xFFFFF78000000320] > (__int64)v2[4] )
    FsbpScavengePool(v2);
  v3 = *v2;
  if ( *v2 != (ULONGLONG *)v2 )
  {
    v4 = (union _SLIST_HEADER *)(v3 - 1);
    v5 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v3 + 3));
    if ( v5 )
      Block = (__int64)v5 - *((unsigned __int16 *)a1 + 5);
    else
      Block = FsbpBuildNextBlock(a1, v4);
    if ( ExQueryDepthSList(v4 + 2) || *((_WORD *)&v4[1].HeaderX64 + 4) != *((_WORD *)a1 + 4) )
      goto LABEL_18;
    v7 = *v2;
    if ( (ULONGLONG **)(*v2)[1] == v2 )
    {
      v8 = (ULONGLONG *)*v7;
      if ( *(ULONGLONG **)(*v7 + 8) == v7 )
      {
        *v2 = v8;
        v8[1] = (ULONGLONG)v2;
        v9 = (ULONGLONG *)(v2 + 2);
        v10 = (ULONGLONG **)v9[1];
        if ( *v10 == v9 )
        {
          *v7 = (ULONGLONG)v9;
          v7[1] = (ULONGLONG)v10;
          *v10 = v7;
          v9[1] = (ULONGLONG)v7;
          *((_WORD *)&v4[1].HeaderX64 + 5) = 1;
LABEL_18:
          *(_QWORD *)(*((unsigned __int16 *)a1 + 5) + Block) = 0;
          return Block;
        }
      }
    }
LABEL_15:
    __fastfail(3u);
  }
  v11 = *a1;
  v16[0] = 1;
  v16[1] = 0;
  Block = 0;
  Pool3 = (union _SLIST_HEADER *)ExAllocatePool3(64, 4096, v11, v16, 1);
  v13 = Pool3;
  if ( Pool3 )
  {
    memset(Pool3, 0, 0x40u);
    v13->Alignment = (ULONGLONG)v2;
    InitializeSListHead(v13 + 2);
    v14 = (ULONGLONG)*v2;
    if ( (ULONGLONG **)(*v2)[1] != v2 )
      goto LABEL_15;
    v13->Region = v14;
    v13[1].Alignment = (ULONGLONG)v2;
    *(_QWORD *)(v14 + 8) = &v13->Region;
    *v2 = &v13->Region;
    Block = FsbpBuildNextBlock(a1, v13);
  }
  if ( Block )
    goto LABEL_18;
  return Block;
}

```

## disassembly

```asm
0x14002c034  push    rbx
0x14002c036  push    rbp
0x14002c037  push    rsi
0x14002c038  push    rdi
0x14002c039  push    r12
0x14002c03b  push    r14
0x14002c03d  push    r15
0x14002c03f  sub     rsp, 40h
0x14002c043  mov     r14, rcx
0x14002c046  xor     ecx, ecx; ProcNumber
0x14002c048  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002c04f  nop     dword ptr [rax+rax+00h]
0x14002c054  mov     ebx, eax
0x14002c056  mov     r12d, 1
0x14002c05c  add     rbx, r12
0x14002c05f  mov     rax, 0FFFFF78000000320h
0x14002c069  shl     rbx, 6
0x14002c06d  add     rbx, r14
0x14002c070  mov     rax, [rax]
0x14002c073  cmp     rax, [rbx+20h]
0x14002c077  jle     short loc_14002C081
0x14002c079  mov     rcx, rbx
0x14002c07c  call    FsbpScavengePool
0x14002c081  mov     rax, [rbx]
0x14002c084  cmp     rax, rbx
0x14002c087  jz      loc_14002C131
0x14002c08d  lea     rbp, [rax-8]
0x14002c091  lea     rcx, [rbp+20h]; ListHead
0x14002c095  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002c09c  nop     dword ptr [rax+rax+00h]
0x14002c0a1  xor     esi, esi
0x14002c0a3  mov     rdi, rax
0x14002c0a6  test    rax, rax
0x14002c0a9  jz      short loc_14002C0B5
0x14002c0ab  movzx   eax, word ptr [r14+0Ah]
0x14002c0b0  sub     rdi, rax
0x14002c0b3  jmp     short loc_14002C0C3
0x14002c0b5  mov     rdx, rbp
0x14002c0b8  mov     rcx, r14
0x14002c0bb  call    FsbpBuildNextBlock
0x14002c0c0  mov     rdi, rax
0x14002c0c3  lea     rcx, [rbp+20h]; SListHead
0x14002c0c7  call    cs:__imp_ExQueryDepthSList
0x14002c0ce  nop     dword ptr [rax+rax+00h]
0x14002c0d3  cmp     si, ax
0x14002c0d6  jnz     loc_14002C1BF
0x14002c0dc  movzx   ecx, word ptr [r14+8]
0x14002c0e1  cmp     [rbp+18h], cx
0x14002c0e5  jnz     loc_14002C1BF
0x14002c0eb  mov     rax, [rbx]
0x14002c0ee  cmp     [rax+8], rbx
0x14002c0f2  jnz     loc_14002C193
0x14002c0f8  mov     rcx, [rax]
0x14002c0fb  cmp     [rcx+8], rax
0x14002c0ff  jnz     loc_14002C193
0x14002c105  mov     [rbx], rcx
0x14002c108  mov     [rcx+8], rbx
0x14002c10c  add     rbx, 10h
0x14002c110  mov     rcx, [rbx+8]
0x14002c114  cmp     [rcx], rbx
0x14002c117  jnz     short loc_14002C193
0x14002c119  mov     [rax], rbx
0x14002c11c  mov     [rax+8], rcx
0x14002c120  mov     [rcx], rax
0x14002c123  mov     [rbx+8], rax
0x14002c127  mov     [rbp+1Ah], r12w
0x14002c12c  jmp     loc_14002C1BF
0x14002c131  mov     r8d, [r14]
0x14002c134  lea     r9, [rsp+78h+var_48]
0x14002c139  xor     esi, esi
0x14002c13b  mov     [rsp+78h+var_48], r12
0x14002c140  mov     edx, 1000h
0x14002c145  mov     [rsp+78h+var_40], rsi
0x14002c14a  mov     edi, esi
0x14002c14c  mov     [rsp+78h+var_58], r12d
0x14002c151  lea     ebp, [rsi+40h]
0x14002c154  mov     ecx, ebp
0x14002c156  call    cs:__imp_ExAllocatePool3
0x14002c15d  nop     dword ptr [rax+rax+00h]
0x14002c162  mov     r15, rax
0x14002c165  test    rax, rax
0x14002c168  jz      short loc_14002C1BA
0x14002c16a  mov     r8d, ebp; Size
0x14002c16d  xor     edx, edx; Val
0x14002c16f  mov     rcx, rax; void *
0x14002c172  call    memset
0x14002c177  lea     rcx, [r15+20h]; SListHead
0x14002c17b  mov     [r15], rbx
0x14002c17e  call    cs:__imp_InitializeSListHead
0x14002c185  nop     dword ptr [rax+rax+00h]
0x14002c18a  mov     rcx, [rbx]
0x14002c18d  cmp     [rcx+8], rbx
0x14002c191  jz      short loc_14002C19A
0x14002c193  mov     ecx, 3
0x14002c198  int     29h; Win8: RtlFailFast(ecx)
0x14002c19a  lea     rax, [r15+8]
0x14002c19e  mov     rdx, r15
0x14002c1a1  mov     [rax], rcx
0x14002c1a4  mov     [rax+8], rbx
0x14002c1a8  mov     [rcx+8], rax
0x14002c1ac  mov     rcx, r14
0x14002c1af  mov     [rbx], rax
0x14002c1b2  call    FsbpBuildNextBlock
0x14002c1b7  mov     rdi, rax
0x14002c1ba  test    rdi, rdi
0x14002c1bd  jz      short loc_14002C1C8
0x14002c1bf  movzx   eax, word ptr [r14+0Ah]
0x14002c1c4  mov     [rax+rdi], rsi
0x14002c1c8  mov     rax, rdi
0x14002c1cb  add     rsp, 40h
0x14002c1cf  pop     r15
0x14002c1d1  pop     r14
0x14002c1d3  pop     r12
0x14002c1d5  pop     rdi
0x14002c1d6  pop     rsi
0x14002c1d7  pop     rbp
0x14002c1d8  pop     rbx
0x14002c1d9  retn
```
