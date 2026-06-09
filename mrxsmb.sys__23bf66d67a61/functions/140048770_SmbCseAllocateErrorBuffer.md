# SmbCseAllocateErrorBuffer

- ea: `0x140048770`
- end: `0x140048849`
- name: `SmbCseAllocateErrorBuffer`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140048770`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048826`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048826`
- `ntoskrnl!MmSizeOfMdl` at `0x1400487a2`
- `ntoskrnl!MmSizeOfMdl` at `0x1400487a2`
- `ntoskrnl!ExAllocatePool2` at `0x1400487c2`
- `ntoskrnl!ExAllocatePool2` at `0x1400487c2`

## pseudocode

```c
__int64 __fastcall SmbCseAllocateErrorBuffer(__int64 a1, unsigned int a2)
{
  __int64 v3; // rbp
  __int64 result; // rax
  unsigned int v5; // edi
  struct _MDL *Pool2; // rax
  struct _MDL *v7; // rbx

  v3 = a2;
  if ( *(_QWORD *)(a1 + 752) )
    return 3221225701LL;
  v5 = (MmSizeOfMdl((PVOID)0xFFF, a2) + 7) & 0xFFFFFFF8;
  Pool2 = (struct _MDL *)ExAllocatePool2(66, v5 + (unsigned int)v3, 1834185285);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Pool2->Next = 0;
  Pool2->ByteCount = v3;
  Pool2->StartVa = (PVOID)(((unsigned __int64)Pool2 + v5) & 0xFFFFFFFFFFFFF000uLL);
  Pool2->ByteOffset = ((_DWORD)Pool2 + v5) & 0xFFF;
  Pool2->Size = 8 * (((v3 + (((unsigned int)Pool2 + v5) & 0xFFFuLL) + 4095) >> 12) + 6);
  Pool2->MdlFlags = 0;
  MmBuildMdlForNonPagedPool(Pool2);
  result = 0;
  *(_QWORD *)(a1 + 752) = v7;
  return result;
}

```

## disassembly

```asm
0x140048770  push    rbx
0x140048772  push    rbp
0x140048773  push    rsi
0x140048774  push    rdi
0x140048775  push    r14
0x140048777  push    r15
0x140048779  sub     rsp, 28h
0x14004877d  cmp     qword ptr [rcx+2F0h], 0
0x140048785  mov     rsi, rcx
0x140048788  mov     ebp, edx
0x14004878a  jz      short loc_140048796
0x14004878c  mov     eax, 0C00000E5h
0x140048791  jmp     loc_14004883B
0x140048796  mov     r15d, 0FFFh
0x14004879c  mov     rdx, rbp; Length
0x14004879f  mov     ecx, r15d; Base
0x1400487a2  call    cs:__imp_MmSizeOfMdl
0x1400487a9  nop     dword ptr [rax+rax+00h]
0x1400487ae  mov     ecx, 42h ; 'B'
0x1400487b3  mov     r8d, 6D537245h
0x1400487b9  lea     edi, [rax+7]
0x1400487bc  and     edi, 0FFFFFFF8h
0x1400487bf  lea     edx, [rdi+rbp]
0x1400487c2  call    cs:__imp_ExAllocatePool2
0x1400487c9  nop     dword ptr [rax+rax+00h]
0x1400487ce  mov     rbx, rax
0x1400487d1  test    rax, rax
0x1400487d4  jnz     short loc_1400487DD
0x1400487d6  mov     eax, 0C000009Ah
0x1400487db  jmp     short loc_14004883B
0x1400487dd  mov     qword ptr [rax], 0
0x1400487e4  mov     edx, edi
0x1400487e6  add     rdx, rbx
0x1400487e9  mov     [rbx+28h], ebp
0x1400487ec  mov     r8d, edx
0x1400487ef  and     rdx, 0FFFFFFFFFFFFF000h
0x1400487f6  mov     ecx, r8d
0x1400487f9  mov     [rbx+20h], rdx
0x1400487fd  and     rcx, r15
0x140048800  and     r8d, r15d
0x140048803  add     rcx, r15
0x140048806  mov     [rbx+2Ch], r8d
0x14004880a  add     rcx, rbp
0x14004880d  shr     rcx, 0Ch
0x140048811  add     cx, 6
0x140048815  shl     cx, 3
0x140048819  mov     [rax+8], cx
0x14004881d  xor     eax, eax
0x14004881f  mov     rcx, rbx; MemoryDescriptorList
0x140048822  mov     [rbx+0Ah], ax
0x140048826  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14004882d  nop     dword ptr [rax+rax+00h]
0x140048832  xor     eax, eax
0x140048834  mov     [rsi+2F0h], rbx
0x14004883b  add     rsp, 28h
0x14004883f  pop     r15
0x140048841  pop     r14
0x140048843  pop     rdi
0x140048844  pop     rsi
0x140048845  pop     rbp
0x140048846  pop     rbx
0x140048847  retn
```
