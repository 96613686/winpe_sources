# SafeModeCloneMdl(_MDL *,ulong,ulong)

- ea: `0x140031fd8`
- end: `0x140032190`
- name: `?SafeModeCloneMdl@@YAPEAU_MDL@@PEAU1@KK@Z`
- size: `440`
- prototype: `struct _MDL *__fastcall(PMDL SourceMdl, ULONG Length, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140032198`

## callees

- `0x140031fd8`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14003217c`
- `ntoskrnl!IoBuildPartialMdl` at `0x14003217c`
- `ntoskrnl!MmSizeOfMdl` at `0x14003200c`
- `ntoskrnl!MmSizeOfMdl` at `0x14003200c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003206d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003206d`
- `ntoskrnl!ExAllocatePool2` at `0x140032085`
- `ntoskrnl!ExAllocatePool2` at `0x140032085`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400320f0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400320f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032116`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032116`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400320cf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400320cf`

## pseudocode

```c
struct _MDL *__fastcall SafeModeCloneMdl(PMDL SourceMdl, ULONG Length, unsigned int a3)
{
  __int64 v3; // r15
  __int64 v5; // rbp
  __int64 ByteOffset; // r12
  char *StartVa; // r13
  unsigned int v8; // eax
  __int64 v9; // r9
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  char *Pool2; // rax
  ULONG *v12; // rbx
  struct _MDL *v13; // rdi
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
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_11;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v8, 828994423, v9);
LABEL_13:
  v12 = (ULONG *)Pool2;
  if ( !Pool2 )
    return 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  v13 = (struct _MDL *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 828994423;
  if ( (SourceMdl->MdlFlags & 5) != 0 )
    MappedSystemVa = SourceMdl->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(SourceMdl, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
  {
    if ( v13 )
    {
      if ( *(_QWORD *)v12 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, v12);
      else
        ExFreePoolWithTag(v12, v12[2]);
    }
    return 0;
  }
  v13->Next = 0;
  v13->ByteCount = v5;
  v13->ByteOffset = ((_WORD)v3 + (_WORD)ByteOffset + (_WORD)StartVa) & 0xFFF;
  v13->Size = 8
            * (((v5 + (unsigned __int64)(((_WORD)v3 + (_WORD)ByteOffset + (_WORD)StartVa) & 0xFFF) + 4095) >> 12) + 6);
  v13->MdlFlags = 0;
  v13->StartVa = (void *)((unsigned __int64)&StartVa[ByteOffset + v3] & 0xFFFFFFFFFFFFF000uLL);
  IoBuildPartialMdl(SourceMdl, v13, &StartVa[ByteOffset + v3], v5);
  return v13;
}

```

## disassembly

```asm
0x140031fd8  push    rbx
0x140031fda  push    rbp
0x140031fdb  push    rsi
0x140031fdc  push    rdi
0x140031fdd  push    r12
0x140031fdf  push    r13
0x140031fe1  push    r14
0x140031fe3  push    r15
0x140031fe5  sub     rsp, 38h
0x140031fe9  mov     r15d, r8d
0x140031fec  mov     rsi, rcx
0x140031fef  mov     ebp, edx
0x140031ff1  cmp     edx, 92Ah
0x140031ff7  ja      loc_1400320FC
0x140031ffd  mov     r12d, [rcx+2Ch]
0x140032001  mov     edx, ebp; Length
0x140032003  mov     r13, [rcx+20h]
0x140032007  mov     ecx, 0FFFh; Base
0x14003200c  call    cs:__imp_MmSizeOfMdl
0x140032013  nop     dword ptr [rax+rax+00h]
0x140032018  add     eax, 7
0x14003201b  and     eax, 0FFFFFFF8h
0x14003201e  add     eax, 10h
0x140032021  cmp     eax, 10h
0x140032024  jb      loc_1400320FC
0x14003202a  mov     ecx, 40h ; '@'
0x14003202f  cmp     eax, ecx
0x140032031  ja      short loc_14003203C
0x140032033  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003203a  jmp     short loc_14003206A
0x14003203c  cmp     eax, 100h
0x140032041  ja      short loc_14003204C
0x140032043  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003204a  jmp     short loc_14003206A
0x14003204c  cmp     eax, 400h
0x140032051  ja      short loc_14003205C
0x140032053  lea     rdi, Lookaside
0x14003205a  jmp     short loc_14003206A
0x14003205c  cmp     eax, 800h
0x140032061  ja      short loc_14003207B
0x140032063  lea     rdi, stru_1400B0180
0x14003206a  mov     rcx, rdi; Lookaside
0x14003206d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140032074  nop     dword ptr [rax+rax+00h]
0x140032079  jmp     short loc_140032091
0x14003207b  xor     edi, edi
0x14003207d  mov     edx, eax
0x14003207f  mov     r8d, 31697377h
0x140032085  call    cs:__imp_ExAllocatePool2
0x14003208c  nop     dword ptr [rax+rax+00h]
0x140032091  mov     rbx, rax
0x140032094  test    rax, rax
0x140032097  jz      short loc_1400320FC
0x140032099  mov     [rax], rdi
0x14003209c  lea     rdi, [rax+10h]
0x1400320a0  mov     dword ptr [rax+8], 31697377h
0x1400320a7  test    byte ptr [rsi+0Ah], 5
0x1400320ab  jz      short loc_1400320B3
0x1400320ad  mov     rax, [rsi+18h]
0x1400320b1  jmp     short loc_1400320DB
0x1400320b3  xor     r9d, r9d; RequestedAddress
0x1400320b6  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400320be  xor     edx, edx; AccessMode
0x1400320c0  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400320c8  mov     rcx, rsi; MemoryDescriptorList
0x1400320cb  lea     r8d, [r9+1]; CacheType
0x1400320cf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400320d6  nop     dword ptr [rax+rax+00h]
0x1400320db  test    rax, rax
0x1400320de  jnz     short loc_140032124
0x1400320e0  test    rdi, rdi
0x1400320e3  jz      short loc_1400320FC
0x1400320e5  mov     rcx, [rbx]; Lookaside
0x1400320e8  test    rcx, rcx
0x1400320eb  jz      short loc_140032110
0x1400320ed  mov     rdx, rbx; Entry
0x1400320f0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400320f7  nop     dword ptr [rax+rax+00h]
0x1400320fc  xor     eax, eax
0x1400320fe  add     rsp, 38h
0x140032102  pop     r15
0x140032104  pop     r14
0x140032106  pop     r13
0x140032108  pop     r12
0x14003210a  pop     rdi
0x14003210b  pop     rsi
0x14003210c  pop     rbp
0x14003210d  pop     rbx
0x14003210e  retn
0x140032110  mov     edx, [rbx+8]; Tag
0x140032113  mov     rcx, rbx; P
0x140032116  call    cs:__imp_ExFreePoolWithTag
0x14003211d  nop     dword ptr [rax+rax+00h]
0x140032122  jmp     short loc_1400320FC
0x140032124  mov     r9d, 0FFFh
0x14003212a  mov     qword ptr [rdi], 0
0x140032131  lea     r8, [r12+r13]
0x140032135  mov     [rdi+28h], ebp
0x140032138  add     r8, r15; VirtualAddress
0x14003213b  mov     edx, r8d
0x14003213e  mov     ecx, edx
0x140032140  and     edx, r9d
0x140032143  and     rcx, r9
0x140032146  mov     [rdi+2Ch], edx
0x140032149  add     rcx, r9
0x14003214c  mov     rdx, rdi; TargetMdl
0x14003214f  add     rcx, rbp
0x140032152  mov     r9d, ebp; Length
0x140032155  shr     rcx, 0Ch
0x140032159  add     cx, 6
0x14003215d  shl     cx, 3
0x140032161  mov     [rdi+8], cx
0x140032165  xor     ecx, ecx
0x140032167  mov     [rdi+0Ah], cx
0x14003216b  mov     rcx, r8
0x14003216e  and     rcx, 0FFFFFFFFFFFFF000h
0x140032175  mov     [rdi+20h], rcx
0x140032179  mov     rcx, rsi; SourceMdl
0x14003217c  call    cs:__imp_IoBuildPartialMdl
0x140032183  nop     dword ptr [rax+rax+00h]
0x140032188  mov     rax, rdi
0x14003218b  jmp     loc_1400320FE
```
