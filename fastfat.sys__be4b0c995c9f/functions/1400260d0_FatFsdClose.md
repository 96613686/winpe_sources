# FatFsdClose

- ea: `0x1400260d0`
- end: `0x140026388`
- name: `FatFsdClose`
- size: `696`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140005288`
- `0x140025bb8`
- `0x1400260d0`
- `0x140038eb4`
- `0x140039550`
- `0x14003960c`
- `0x14003d880`
- `0x140048104`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002636a`
- `ntoskrnl!IofCompleteRequest` at `0x14002636a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026122`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026122`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140026338`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140026338`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026344`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026344`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140026203`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140026203`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002618b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002618b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140026228`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140026228`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400262f9`

## pseudocode

```c
__int64 __fastcall FatFsdClose(__int64 a1, IRP *a2)
{
  char IsIrpTopLevel; // si
  PFILE_OBJECT FileObject; // rdi
  __int64 v5; // rdx
  int v6; // r12d
  __int64 v7; // r13
  char v8; // si
  __int64 v9; // r15
  PSLIST_ENTRY v10; // rdi
  int v12[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 Wait; // [rsp+90h] [rbp+8h] BYREF
  PIRP Irp; // [rsp+98h] [rbp+10h]
  char v15; // [rsp+A0h] [rbp+18h]
  __int64 v16; // [rsp+A8h] [rbp+20h] BYREF

  Irp = a2;
  *(_QWORD *)v12 = 0;
  v16 = 0;
  Wait = 0;
  if ( a1 == qword_140017CC8 || a1 == qword_140017CD0 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  else
  {
    KeEnterCriticalRegion();
    IsIrpTopLevel = FatIsIrpTopLevel(a2);
    v15 = IsIrpTopLevel;
    FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
    v6 = FatDecodeFileObject(FileObject, v12, &v16, &Wait);
    v7 = Wait;
    if ( Wait && !*(_WORD *)&FileObject->WriteAccess )
      *(_DWORD *)(Wait + 4) |= 0x80u;
    if ( !IsIrpTopLevel || IoGetCurrentProcess() == (PEPROCESS)qword_140017D40 )
    {
      LOBYTE(Wait) = 0;
      v8 = 1;
    }
    else
    {
      v8 = 1;
      LOBYTE(Wait) = 1;
    }
    v9 = v16;
    if ( v16 && (FileObject->Flags & 0x4000) == 0 && (unsigned __int16)(*(_WORD *)v16 - 1282) <= 2u )
      FsRtlCheckOplockEx((POPLOCK)(v16 + 88), a2, 0, 0, 0, 0);
    if ( (unsigned int)(v6 - 5) <= 3 || (v10 = 0, v6 == 9) )
    {
      v10 = ExpInterlockedPopEntrySList(&FatCloseContextSList);
      BYTE4(v10[3].Next) = 1;
    }
    if ( (unsigned int)(v6 - 2) <= 1 && (*(_DWORD *)(v9 + 192) & 0x800) != 0 && (byte_140017D4C & 8) == 0
      || (unsigned int)FatCommonClose(*(__int64 *)v12, v9, v7, v6, Wait, v15, &v16) == 259 )
    {
      if ( !v10 )
      {
        FatDeallocateCcbStrings(v7);
        v10 = (PSLIST_ENTRY)(v7 + 24);
        *(_BYTE *)(v7 + 76) = 0;
        *(_DWORD *)(v7 + 4) |= 0x8000u;
      }
      v10[2].Next = *(struct _SLIST_ENTRY **)v12;
      *((_QWORD *)&v10[2].Next + 1) = v9;
      LODWORD(v10[3].Next) = v6;
      if ( !v9 || (*(_DWORD *)(v9 + 192) & 0x800) == 0 )
        v8 = 0;
      LOBYTE(v5) = v8;
      FatQueueClose(v10, v5);
    }
    else if ( (unsigned int)(v6 - 5) <= 4 && v10 )
    {
      ExFreePoolWithTag(v10, 0);
    }
    FatCompleteRequest_Real(0, a2);
    if ( v15 )
      IoSetTopLevelIrp(0);
    KeLeaveCriticalRegion();
    return 0;
  }
}

```

## disassembly

```asm
0x1400260d0  mov     rax, rsp
0x1400260d3  mov     [rax+10h], rdx
0x1400260d7  push    rsi
0x1400260d8  push    rdi
0x1400260d9  push    r12
0x1400260db  push    r13
0x1400260dd  push    r14
0x1400260df  push    r15
0x1400260e1  sub     rsp, 58h
0x1400260e5  mov     r14, rdx
0x1400260e8  mov     qword ptr [rax-40h], 0
0x1400260f0  mov     qword ptr [rax+20h], 0
0x1400260f8  mov     qword ptr [rax+8], 0
0x140026100  cmp     rcx, cs:qword_140017CC8
0x140026107  jz      loc_140026354
0x14002610d  cmp     rcx, cs:qword_140017CD0
0x140026114  jz      loc_140026354
0x14002611a  mov     [rsp+88h+var_48], 0
0x140026122  call    cs:__imp_KeEnterCriticalRegion
0x140026129  nop     dword ptr [rax+rax+00h]
0x14002612e  mov     rcx, r14; Irp
0x140026131  call    FatIsIrpTopLevel
0x140026136  mov     sil, al
0x140026139  mov     [rsp+88h+arg_10], al
0x140026140  mov     rax, [r14+0B8h]
0x140026147  mov     rdi, [rax+30h]
0x14002614b  lea     r9, [rsp+88h+Wait]
0x140026153  lea     r8, [rsp+88h+arg_18]
0x14002615b  lea     rdx, [rsp+88h+var_40]
0x140026160  mov     rcx, rdi
0x140026163  call    FatDecodeFileObject
0x140026168  mov     r12d, eax
0x14002616b  mov     r13, [rsp+88h+Wait]
0x140026173  test    r13, r13
0x140026176  jz      short loc_140026186
0x140026178  mov     al, [rdi+4Ch]
0x14002617b  or      al, [rdi+4Bh]
0x14002617e  jnz     short loc_140026186
0x140026180  bts     dword ptr [r13+4], 7
0x140026186  test    sil, sil
0x140026189  jz      short loc_1400261AF
0x14002618b  call    cs:__imp_IoGetCurrentProcess
0x140026192  nop     dword ptr [rax+rax+00h]
0x140026197  cmp     rax, cs:qword_140017D40
0x14002619e  jz      short loc_1400261AF
0x1400261a0  mov     esi, 1
0x1400261a5  mov     byte ptr [rsp+88h+Wait], sil
0x1400261ad  jmp     short loc_1400261BC
0x1400261af  mov     byte ptr [rsp+88h+Wait], 0
0x1400261b7  mov     esi, 1
0x1400261bc  mov     r15, [rsp+88h+arg_18]
0x1400261c4  test    r15, r15
0x1400261c7  jz      short loc_14002620F
0x1400261c9  mov     eax, [rdi+50h]
0x1400261cc  bt      eax, 0Eh
0x1400261d0  jb      short loc_14002620F
0x1400261d2  mov     ecx, 502h
0x1400261d7  movzx   eax, word ptr [r15]
0x1400261db  sub     ax, cx
0x1400261de  cmp     ax, 2
0x1400261e2  ja      short loc_14002620F
0x1400261e4  lea     rcx, [r15+58h]; Oplock
0x1400261e8  mov     [rsp+88h+PostIrpRoutine], 0; PostIrpRoutine
0x1400261f1  mov     [rsp+88h+CompletionRoutine], 0; CompletionRoutine
0x1400261fa  xor     r9d, r9d; Context
0x1400261fd  xor     r8d, r8d; Flags
0x140026200  mov     rdx, r14; Irp
0x140026203  call    cs:__imp_FsRtlCheckOplockEx
0x14002620a  nop     dword ptr [rax+rax+00h]
0x14002620f  lea     eax, [r12-5]
0x140026214  cmp     eax, 3
0x140026217  jbe     short loc_140026221
0x140026219  xor     edi, edi
0x14002621b  cmp     r12d, 9
0x14002621f  jnz     short loc_14002623B
0x140026221  lea     rcx, FatCloseContextSList; ListHead
0x140026228  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002622f  nop     dword ptr [rax+rax+00h]
0x140026234  mov     rdi, rax
0x140026237  mov     [rax+34h], sil
0x14002623b  lea     eax, [r12-2]
0x140026240  cmp     eax, esi
0x140026242  ja      short loc_14002625A
0x140026244  test    dword ptr [r15+0C0h], 800h
0x14002624f  jz      short loc_14002625A
0x140026251  test    cs:byte_140017D4C, 8
0x140026258  jz      short loc_140026297
0x14002625a  lea     rax, [rsp+88h+arg_18]
0x140026262  mov     [rsp+88h+var_58], rax; __int64
0x140026267  mov     al, [rsp+88h+arg_10]
0x14002626e  mov     byte ptr [rsp+88h+PostIrpRoutine], al; char
0x140026272  mov     al, byte ptr [rsp+88h+Wait]
0x140026279  mov     byte ptr [rsp+88h+CompletionRoutine], al; Wait
0x14002627d  mov     r9d, r12d; int
0x140026280  mov     r8, r13; int
0x140026283  mov     rdx, r15; int
0x140026286  mov     rcx, qword ptr [rsp+88h+var_40]; int
0x14002628b  call    FatCommonClose
0x140026290  cmp     eax, 103h
0x140026295  jnz     short loc_1400262E5
0x140026297  test    rdi, rdi
0x14002629a  jnz     short loc_1400262B2
0x14002629c  mov     rcx, r13
0x14002629f  call    FatDeallocateCcbStrings
0x1400262a4  lea     rdi, [r13+18h]
0x1400262a8  mov     byte ptr [rdi+34h], 0
0x1400262ac  bts     dword ptr [r13+4], 0Fh
0x1400262b2  mov     rax, qword ptr [rsp+88h+var_40]
0x1400262b7  mov     [rdi+20h], rax
0x1400262bb  mov     [rdi+28h], r15
0x1400262bf  mov     [rdi+30h], r12d
0x1400262c3  test    r15, r15
0x1400262c6  jz      short loc_1400262D5
0x1400262c8  test    dword ptr [r15+0C0h], 800h
0x1400262d3  jnz     short loc_1400262D8
0x1400262d5  xor     sil, sil
0x1400262d8  mov     dl, sil
0x1400262db  mov     rcx, rdi
0x1400262de  call    FatQueueClose
0x1400262e3  jmp     short loc_140026305
0x1400262e5  lea     eax, [r12-5]
0x1400262ea  cmp     eax, 4
0x1400262ed  ja      short loc_140026305
0x1400262ef  test    rdi, rdi
0x1400262f2  jz      short loc_140026305
0x1400262f4  xor     edx, edx; Tag
0x1400262f6  mov     rcx, rdi; P
0x1400262f9  call    cs:__imp_ExFreePoolWithTag
0x140026300  nop     dword ptr [rax+rax+00h]
0x140026305  xor     r8d, r8d
0x140026308  mov     rdx, r14; Irp
0x14002630b  xor     ecx, ecx; Entry
0x14002630d  call    FatCompleteRequest_Real
0x140026312  mov     edi, [rsp+88h+var_48]
0x140026316  jmp     short loc_14002632C
0x140026318  mov     r8d, eax
0x14002631b  mov     rdx, [rsp+88h+Irp]; Irp
0x140026323  xor     ecx, ecx; Entry
0x140026325  call    FatProcessException
0x14002632a  mov     edi, eax
0x14002632c  cmp     [rsp+88h+arg_10], 0
0x140026334  jz      short loc_140026344
0x140026336  xor     ecx, ecx; Irp
0x140026338  call    cs:__imp_IoSetTopLevelIrp
0x14002633f  nop     dword ptr [rax+rax+00h]
0x140026344  call    cs:__imp_KeLeaveCriticalRegion
0x14002634b  nop     dword ptr [rax+rax+00h]
0x140026350  mov     eax, edi
0x140026352  jmp     short loc_140026378
0x140026354  mov     dword ptr [rdx+30h], 0
0x14002635b  mov     esi, 1
0x140026360  mov     [rdx+38h], rsi
0x140026364  mov     dl, sil; PriorityBoost
0x140026367  mov     rcx, r14; Irp
0x14002636a  call    cs:__imp_IofCompleteRequest
0x140026371  nop     dword ptr [rax+rax+00h]
0x140026376  xor     eax, eax
0x140026378  add     rsp, 58h
0x14002637c  pop     r15
0x14002637e  pop     r14
0x140026380  pop     r13
0x140026382  pop     r12
0x140026384  pop     rdi
0x140026385  pop     rsi
0x140026386  retn
0x14005bafc  push    rbp
0x14005bafe  sub     rsp, 40h
0x14005bb02  mov     rbp, rdx
0x14005bb05  mov     rdx, rcx
0x14005bb08  xor     ecx, ecx
0x14005bb0a  call    FatExceptionFilter
0x14005bb0f  nop
0x14005bb10  add     rsp, 40h
0x14005bb14  pop     rbp
0x14005bb15  retn
```
