# FatCreateIrpContext

- ea: `0x140047d24`
- end: `0x140047e2b`
- name: `FatCreateIrpContext`
- size: `263`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001f80`
- `0x140002900`
- `0x140006030`
- `0x140007530`
- `0x140025a90`
- `0x14002a4b0`
- `0x14002d3f0`
- `0x14002ea00`
- `0x1400345b0`
- `0x14003816c`
- `0x14003a550`
- `0x14003a610`
- `0x14003e9d0`
- `0x14003f2c0`
- `0x140044460`
- `0x140045130`
- `0x140046fb0`
- `0x14004a8f0`
- `0x14004a9b0`

## callees

- `0x14000c680`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140047e07`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140047e07`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047d7c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140047d7c`
- `ntoskrnl!ExRaiseStatus` at `0x140047d68`
- `ntoskrnl!ExRaiseStatus` at `0x140047d68`

## pseudocode

```c
_DWORD *__fastcall FatCreateIrpContext(IRP *a1, char a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PDEVICE_OBJECT DeviceObject; // rax
  _DWORD *v6; // rbx
  UCHAR MajorFunction; // al
  PFILE_OBJECT FileObject; // rcx

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  if ( (DeviceObject == (PDEVICE_OBJECT)qword_140017CC8 || DeviceObject == (PDEVICE_OBJECT)qword_140017CD0)
    && CurrentStackLocation->FileObject
    && ((CurrentStackLocation->MajorFunction & 0xED) != 0 || CurrentStackLocation->MajorFunction == 16) )
  {
    ExRaiseStatus(-1073741808);
  }
  v6 = ExAllocateFromNPagedLookasideList(&FatIrpContextLookasideList);
  memset(v6, 0, 0x90u);
  *v6 = 9438472;
  *((_QWORD *)v6 + 5) = a1;
  MajorFunction = CurrentStackLocation->MajorFunction;
  *((_BYTE *)v6 + 64) = CurrentStackLocation->MajorFunction;
  *((_BYTE *)v6 + 65) = CurrentStackLocation->MinorFunction;
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject )
  {
    *((_QWORD *)v6 + 6) = FileObject->DeviceObject;
    *((_QWORD *)v6 + 7) = (char *)CurrentStackLocation->DeviceObject + 416;
    if ( (FileObject->Flags & 0x10) != 0
      || CurrentStackLocation->MajorFunction == 4 && (a1->Flags & 1) != 0 && (CurrentStackLocation->Flags & 4) != 0 )
    {
      v6[17] |= 4u;
    }
  }
  else if ( MajorFunction == 13 )
  {
    *((_QWORD *)v6 + 6) = *(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  }
  if ( a2 )
    v6[17] |= 2u;
  if ( IoGetTopLevelIrp() != a1 )
    v6[17] |= 0x10u;
  return v6;
}

```

## disassembly

```asm
0x140047d24  push    rbx
0x140047d26  push    rbp
0x140047d27  push    rsi
0x140047d28  push    rdi
0x140047d29  push    r14
0x140047d2b  sub     rsp, 20h
0x140047d2f  mov     rdi, [rcx+0B8h]
0x140047d36  mov     bpl, dl
0x140047d39  mov     rsi, rcx
0x140047d3c  mov     rax, [rdi+28h]
0x140047d40  cmp     rax, cs:qword_140017CC8
0x140047d47  jz      short loc_140047D52
0x140047d49  cmp     rax, cs:qword_140017CD0
0x140047d50  jnz     short loc_140047D75
0x140047d52  cmp     qword ptr [rdi+30h], 0
0x140047d57  jz      short loc_140047D75
0x140047d59  mov     al, [rdi]
0x140047d5b  test    al, 0EDh
0x140047d5d  jnz     short loc_140047D63
0x140047d5f  cmp     al, 10h
0x140047d61  jnz     short loc_140047D75
0x140047d63  mov     ecx, 0C0000010h; Status
0x140047d68  call    cs:__imp_ExRaiseStatus
0x140047d75  lea     rcx, FatIrpContextLookasideList; Lookaside
0x140047d7c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140047d83  nop     dword ptr [rax+rax+00h]
0x140047d88  xor     edx, edx; Val
0x140047d8a  mov     r8d, 90h; Size
0x140047d90  mov     rcx, rax; void *
0x140047d93  mov     rbx, rax
0x140047d96  call    memset
0x140047d9b  mov     dword ptr [rbx], 900508h
0x140047da1  mov     [rbx+28h], rsi
0x140047da5  mov     al, [rdi]
0x140047da7  mov     [rbx+40h], al
0x140047daa  mov     cl, [rdi+1]
0x140047dad  mov     [rbx+41h], cl
0x140047db0  mov     rcx, [rdi+30h]
0x140047db4  test    rcx, rcx
0x140047db7  jz      short loc_140047DEE
0x140047db9  mov     rax, [rcx+8]
0x140047dbd  mov     [rbx+30h], rax
0x140047dc1  mov     rax, [rdi+28h]
0x140047dc5  add     rax, 1A0h
0x140047dcb  mov     [rbx+38h], rax
0x140047dcf  mov     eax, [rcx+50h]
0x140047dd2  test    al, 10h
0x140047dd4  jnz     short loc_140047DE8
0x140047dd6  cmp     byte ptr [rdi], 4
0x140047dd9  jnz     short loc_140047DFE
0x140047ddb  mov     eax, [rsi+10h]
0x140047dde  test    al, 1
0x140047de0  jz      short loc_140047DFE
0x140047de2  test    byte ptr [rdi+2], 4
0x140047de6  jz      short loc_140047DFE
0x140047de8  or      dword ptr [rbx+44h], 4
0x140047dec  jmp     short loc_140047DFE
0x140047dee  cmp     al, 0Dh
0x140047df0  jnz     short loc_140047DFE
0x140047df2  mov     rax, [rdi+8]
0x140047df6  mov     rcx, [rax+10h]
0x140047dfa  mov     [rbx+30h], rcx
0x140047dfe  test    bpl, bpl
0x140047e01  jz      short loc_140047E07
0x140047e03  or      dword ptr [rbx+44h], 2
0x140047e07  call    cs:__imp_IoGetTopLevelIrp
0x140047e0e  nop     dword ptr [rax+rax+00h]
0x140047e13  cmp     rax, rsi
0x140047e16  jz      short loc_140047E1C
0x140047e18  or      dword ptr [rbx+44h], 10h
0x140047e1c  mov     rax, rbx
0x140047e1f  add     rsp, 20h
0x140047e23  pop     r14
0x140047e25  pop     rdi
0x140047e26  pop     rsi
0x140047e27  pop     rbp
0x140047e28  pop     rbx
0x140047e29  retn
```
