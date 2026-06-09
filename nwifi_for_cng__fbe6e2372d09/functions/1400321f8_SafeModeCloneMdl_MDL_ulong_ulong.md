# SafeModeCloneMdl(_MDL *,ulong,ulong)

- ea: `0x1400321f8`
- end: `0x1400323b0`
- name: `?SafeModeCloneMdl@@YAPEAU_MDL@@PEAU1@KK@Z`
- size: `440`
- prototype: `struct _MDL *__fastcall(PMDL SourceMdl, ULONG Length, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400323b8`

## callees

- `0x1400321f8`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14003239c`
- `ntoskrnl!IoBuildPartialMdl` at `0x14003239c`
- `ntoskrnl!MmSizeOfMdl` at `0x14003222c`
- `ntoskrnl!MmSizeOfMdl` at `0x14003222c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003228d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003228d`
- `ntoskrnl!ExAllocatePool2` at `0x1400322a5`
- `ntoskrnl!ExAllocatePool2` at `0x1400322a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140032310`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140032310`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032336`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032336`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400322ef`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400322ef`

## pseudocode

```c
struct _MDL *__fastcall SafeModeCloneMdl(PMDL SourceMdl, ULONG Length, unsigned int a3)
{
  __int64 v3; // r15
  __int64 v5; // rbp
  __int64 ByteOffset; // r12
  char *StartVa; // r13
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  char *Pool2; // rax
  ULONG *v11; // rbx
  struct _MDL *v12; // rdi
  void *MappedSystemVa; // rax

  v3 = a3;
  v5 = Length;
  if ( Length > 0x92A )
    return 0;
  ByteOffset = SourceMdl->ByteOffset;
  StartVa = (char *)SourceMdl->StartVa;
  v8 = ((MmSizeOfMdl((PVOID)0xFFF, Length) + 7) & 0xFFFFFFF8) + 16;
  if ( v8 < 0x10 )
    return 0;
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_11:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_13;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_11;
  }
  if ( v8 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_11;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_11;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v8, 828994423);
LABEL_13:
  v11 = (ULONG *)Pool2;
  if ( !Pool2 )
    return 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  v12 = (struct _MDL *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 828994423;
  if ( (SourceMdl->MdlFlags & 5) != 0 )
    MappedSystemVa = SourceMdl->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(SourceMdl, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
  {
    if ( v12 )
    {
      if ( *(_QWORD *)v11 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v11, v11);
      else
        ExFreePoolWithTag(v11, v11[2]);
    }
    return 0;
  }
  v12->Next = 0;
  v12->ByteCount = v5;
  v12->ByteOffset = ((_WORD)v3 + (_WORD)ByteOffset + (_WORD)StartVa) & 0xFFF;
  v12->Size = 8
            * (((v5 + (unsigned __int64)(((_WORD)v3 + (_WORD)ByteOffset + (_WORD)StartVa) & 0xFFF) + 4095) >> 12) + 6);
  v12->MdlFlags = 0;
  v12->StartVa = (void *)((unsigned __int64)&StartVa[ByteOffset + v3] & 0xFFFFFFFFFFFFF000uLL);
  IoBuildPartialMdl(SourceMdl, v12, &StartVa[ByteOffset + v3], v5);
  return v12;
}

```

## disassembly

```asm
0x1400321f8  push    rbx
0x1400321fa  push    rbp
0x1400321fb  push    rsi
0x1400321fc  push    rdi
0x1400321fd  push    r12
0x1400321ff  push    r13
0x140032201  push    r14
0x140032203  push    r15
0x140032205  sub     rsp, 38h
0x140032209  mov     r15d, r8d
0x14003220c  mov     rsi, rcx
0x14003220f  mov     ebp, edx
0x140032211  cmp     edx, 92Ah
0x140032217  ja      loc_14003231C
0x14003221d  mov     r12d, [rcx+2Ch]
0x140032221  mov     edx, ebp; Length
0x140032223  mov     r13, [rcx+20h]
0x140032227  mov     ecx, 0FFFh; Base
0x14003222c  call    cs:__imp_MmSizeOfMdl
0x140032233  nop     dword ptr [rax+rax+00h]
0x140032238  add     eax, 7
0x14003223b  and     eax, 0FFFFFFF8h
0x14003223e  add     eax, 10h
0x140032241  cmp     eax, 10h
0x140032244  jb      loc_14003231C
0x14003224a  mov     ecx, 40h ; '@'
0x14003224f  cmp     eax, ecx
0x140032251  ja      short loc_14003225C
0x140032253  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003225a  jmp     short loc_14003228A
0x14003225c  cmp     eax, 100h
0x140032261  ja      short loc_14003226C
0x140032263  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003226a  jmp     short loc_14003228A
0x14003226c  cmp     eax, 400h
0x140032271  ja      short loc_14003227C
0x140032273  lea     rdi, Lookaside
0x14003227a  jmp     short loc_14003228A
0x14003227c  cmp     eax, 800h
0x140032281  ja      short loc_14003229B
0x140032283  lea     rdi, stru_1400B31C0
0x14003228a  mov     rcx, rdi; Lookaside
0x14003228d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140032294  nop     dword ptr [rax+rax+00h]
0x140032299  jmp     short loc_1400322B1
0x14003229b  xor     edi, edi
0x14003229d  mov     edx, eax
0x14003229f  mov     r8d, 31697377h
0x1400322a5  call    cs:__imp_ExAllocatePool2
0x1400322ac  nop     dword ptr [rax+rax+00h]
0x1400322b1  mov     rbx, rax
0x1400322b4  test    rax, rax
0x1400322b7  jz      short loc_14003231C
0x1400322b9  mov     [rax], rdi
0x1400322bc  lea     rdi, [rax+10h]
0x1400322c0  mov     dword ptr [rax+8], 31697377h
0x1400322c7  test    byte ptr [rsi+0Ah], 5
0x1400322cb  jz      short loc_1400322D3
0x1400322cd  mov     rax, [rsi+18h]
0x1400322d1  jmp     short loc_1400322FB
0x1400322d3  xor     r9d, r9d; RequestedAddress
0x1400322d6  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400322de  xor     edx, edx; AccessMode
0x1400322e0  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400322e8  mov     rcx, rsi; MemoryDescriptorList
0x1400322eb  lea     r8d, [r9+1]; CacheType
0x1400322ef  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400322f6  nop     dword ptr [rax+rax+00h]
0x1400322fb  test    rax, rax
0x1400322fe  jnz     short loc_140032344
0x140032300  test    rdi, rdi
0x140032303  jz      short loc_14003231C
0x140032305  mov     rcx, [rbx]; Lookaside
0x140032308  test    rcx, rcx
0x14003230b  jz      short loc_140032330
0x14003230d  mov     rdx, rbx; Entry
0x140032310  call    cs:__imp_ExFreeToNPagedLookasideList
0x140032317  nop     dword ptr [rax+rax+00h]
0x14003231c  xor     eax, eax
0x14003231e  add     rsp, 38h
0x140032322  pop     r15
0x140032324  pop     r14
0x140032326  pop     r13
0x140032328  pop     r12
0x14003232a  pop     rdi
0x14003232b  pop     rsi
0x14003232c  pop     rbp
0x14003232d  pop     rbx
0x14003232e  retn
0x140032330  mov     edx, [rbx+8]; Tag
0x140032333  mov     rcx, rbx; P
0x140032336  call    cs:__imp_ExFreePoolWithTag
0x14003233d  nop     dword ptr [rax+rax+00h]
0x140032342  jmp     short loc_14003231C
0x140032344  mov     r9d, 0FFFh
0x14003234a  mov     qword ptr [rdi], 0
0x140032351  lea     r8, [r12+r13]
0x140032355  mov     [rdi+28h], ebp
0x140032358  add     r8, r15; VirtualAddress
0x14003235b  mov     edx, r8d
0x14003235e  mov     ecx, edx
0x140032360  and     edx, r9d
0x140032363  and     rcx, r9
0x140032366  mov     [rdi+2Ch], edx
0x140032369  add     rcx, r9
0x14003236c  mov     rdx, rdi; TargetMdl
0x14003236f  add     rcx, rbp
0x140032372  mov     r9d, ebp; Length
0x140032375  shr     rcx, 0Ch
0x140032379  add     cx, 6
0x14003237d  shl     cx, 3
0x140032381  mov     [rdi+8], cx
0x140032385  xor     ecx, ecx
0x140032387  mov     [rdi+0Ah], cx
0x14003238b  mov     rcx, r8
0x14003238e  and     rcx, 0FFFFFFFFFFFFF000h
0x140032395  mov     [rdi+20h], rcx
0x140032399  mov     rcx, rsi; SourceMdl
0x14003239c  call    cs:__imp_IoBuildPartialMdl
0x1400323a3  nop     dword ptr [rax+rax+00h]
0x1400323a8  mov     rax, rdi
0x1400323ab  jmp     loc_14003231E
```
