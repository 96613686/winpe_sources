# FatIsVolumeDirty

- ea: `0x1400400d8`
- end: `0x140040208`
- name: `FatIsVolumeDirty`
- size: `304`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x140038eb4`
- `0x14003d880`
- `0x1400400d8`
- `0x14004a37c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140040146`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140040146`

## pseudocode

```c
__int64 __fastcall FatIsVolumeDirty(_DWORD *Entry, PIRP Irp, __int64 a3, __int64 a4)
{
  struct _IRP *MasterIrp; // rsi
  PIRP v5; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  PMDL MdlAddress; // rcx
  unsigned int v9; // esi
  __int64 v10; // rbp
  PVOID v11; // rcx
  __int64 v12; // r9
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v5 = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  if ( !MasterIrp )
  {
    MdlAddress = Irp->MdlAddress;
    if ( !MdlAddress )
    {
      v9 = -1073741592;
      goto LABEL_18;
    }
    MasterIrp = (struct _IRP *)((MdlAddress->MdlFlags & 5) != 0
                              ? MdlAddress->MappedSystemVa
                              : MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u));
    if ( !MasterIrp )
    {
      v9 = -1073741670;
LABEL_8:
      Irp = v5;
LABEL_18:
      v11 = Entry;
      goto LABEL_19;
    }
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 4
    || (*(_DWORD *)&MasterIrp->Type = 0,
        (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v14, &v16, &v15) != 4) )
  {
    v9 = -1073741811;
    goto LABEL_8;
  }
  v10 = v14;
  v11 = Entry;
  if ( *(_DWORD *)(v14 + 204) != 1 )
  {
    v9 = -1073741202;
    Irp = v5;
LABEL_19:
    FatCompleteRequest_Real(v11, Irp, v9, a4);
    return v9;
  }
  Entry[17] |= 0x20u;
  FatVerifyVcb(Entry, v10);
  if ( (*(_DWORD *)(v10 + 200) & 0x10) != 0 )
    *(_DWORD *)&MasterIrp->Type |= 1u;
  v5->IoStatus.Information = 4;
  FatCompleteRequest_Real(Entry, v5, 0, v12);
  return 0;
}

```

## disassembly

```asm
0x1400400d8  mov     rax, rsp
0x1400400db  mov     [rax+8], rbx
0x1400400df  push    rbp
0x1400400e0  push    rsi
0x1400400e1  push    rdi
0x1400400e2  sub     rsp, 30h
0x1400400e6  mov     rsi, [rdx+18h]
0x1400400ea  mov     rbx, rdx
0x1400400ed  mov     rbp, [rdx+0B8h]
0x1400400f4  mov     rdi, rcx
0x1400400f7  mov     qword ptr [rax+10h], 0
0x1400400ff  mov     qword ptr [rax+20h], 0
0x140040107  mov     qword ptr [rax+18h], 0
0x14004010f  test    rsi, rsi
0x140040112  jnz     short loc_140040167
0x140040114  mov     rcx, [rdx+8]; MemoryDescriptorList
0x140040118  test    rcx, rcx
0x14004011b  jz      loc_1400401E8
0x140040121  test    byte ptr [rcx+0Ah], 5
0x140040125  jz      short loc_14004012D
0x140040127  mov     rsi, [rcx+18h]
0x14004012b  jmp     short loc_140040155
0x14004012d  xor     r9d, r9d; RequestedAddress
0x140040130  mov     [rsp+48h+Priority], 40000000h; Priority
0x140040138  xor     edx, edx; AccessMode
0x14004013a  mov     [rsp+48h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140040142  lea     r8d, [r9+1]; CacheType
0x140040146  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004014d  nop     dword ptr [rax+rax+00h]
0x140040152  mov     rsi, rax
0x140040155  test    rsi, rsi
0x140040158  jnz     short loc_140040167
0x14004015a  mov     esi, 0C000009Ah
0x14004015f  mov     rdx, rbx
0x140040162  jmp     loc_1400401ED
0x140040167  cmp     dword ptr [rbp+8], 4
0x14004016b  jb      short loc_1400401DE
0x14004016d  mov     dword ptr [rsi], 0
0x140040173  lea     r9, [rsp+48h+arg_10]
0x140040178  mov     rcx, [rbp+30h]
0x14004017c  lea     r8, [rsp+48h+arg_18]
0x140040181  lea     rdx, [rsp+48h+arg_8]
0x140040186  call    FatDecodeFileObject
0x14004018b  cmp     eax, 4
0x14004018e  jnz     short loc_1400401DE
0x140040190  mov     rbp, [rsp+48h+arg_8]
0x140040195  mov     rcx, rdi
0x140040198  cmp     dword ptr [rbp+0CCh], 1
0x14004019f  jz      short loc_1400401AB
0x1400401a1  mov     esi, 0C000026Eh
0x1400401a6  mov     rdx, rbx
0x1400401a9  jmp     short loc_1400401F0
0x1400401ab  or      dword ptr [rdi+44h], 20h
0x1400401af  mov     rdx, rbp
0x1400401b2  call    FatVerifyVcb
0x1400401b7  mov     eax, [rbp+0C8h]
0x1400401bd  test    al, 10h
0x1400401bf  jz      short loc_1400401C4
0x1400401c1  or      dword ptr [rsi], 1
0x1400401c4  xor     r8d, r8d
0x1400401c7  mov     qword ptr [rbx+38h], 4
0x1400401cf  mov     rdx, rbx; Irp
0x1400401d2  mov     rcx, rdi; Entry
0x1400401d5  call    FatCompleteRequest_Real
0x1400401da  xor     eax, eax
0x1400401dc  jmp     short loc_1400401FA
0x1400401de  mov     esi, 0C000000Dh
0x1400401e3  jmp     loc_14004015F
0x1400401e8  mov     esi, 0C00000E8h
0x1400401ed  mov     rcx, rdi; Entry
0x1400401f0  mov     r8d, esi
0x1400401f3  call    FatCompleteRequest_Real
0x1400401f8  mov     eax, esi
0x1400401fa  mov     rbx, [rsp+48h+arg_0]
0x1400401ff  add     rsp, 30h
0x140040203  pop     rdi
0x140040204  pop     rsi
0x140040205  pop     rbp
0x140040206  retn
```
