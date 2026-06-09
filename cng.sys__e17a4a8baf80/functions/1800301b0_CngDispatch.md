# CngDispatch

- ea: `0x1800301b0`
- end: `0x1800302df`
- name: `CngDispatch`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800301b0`
- `0x1800302f0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800a7469`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800a7469`
- `ntoskrnl!IofCompleteRequest` at `0x180030244`
- `ntoskrnl!IofCompleteRequest` at `0x180030244`

## pseudocode

```c
__int64 __fastcall CngDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  DWORD LowPart; // esi
  PVOID MappedSystemVa; // r8
  unsigned int Status; // ebx
  unsigned int v8; // ecx
  int v9; // eax
  ULONG_PTR Length; // rax
  PMDL MdlAddress; // rcx
  struct _IRP *MasterIrp; // rax
  ULONG Priority; // [rsp+28h] [rbp-30h]
  ULONG ByteCount; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  switch ( CurrentStackLocation->MajorFunction )
  {
    case 0u:
    case 2u:
      a2->IoStatus.Status = 0;
LABEL_12:
      a2->IoStatus.Information = 0;
      break;
    case 3u:
      a2->IoStatus.Status = -1073741807;
      goto LABEL_12;
    case 4u:
      a2->IoStatus.Status = 0;
      Length = CurrentStackLocation->Parameters.Read.Length;
      goto LABEL_17;
    case 5u:
      if ( CurrentStackLocation->Parameters.Create.Options == 5 )
      {
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        v8 = 24;
        MasterIrp->Flags = 1;
        *((_WORD *)&MasterIrp->Flags + 2) = 0;
        *(_QWORD *)&MasterIrp->Type = 0;
        MasterIrp->MdlAddress = 0;
        goto LABEL_29;
      }
LABEL_15:
      v8 = CurrentStackLocation->Parameters.Read.Length;
      v9 = -1073741821;
LABEL_16:
      a2->IoStatus.Status = v9;
      Length = v8;
LABEL_17:
      a2->IoStatus.Information = Length;
      break;
    case 0xAu:
      if ( CurrentStackLocation->Parameters.Create.Options == 4 )
      {
        v8 = 8;
        *(_DWORD *)a2->AssociatedIrp.MasterIrp = 57;
LABEL_29:
        v9 = 0;
        goto LABEL_16;
      }
      goto LABEL_15;
    case 0xEu:
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( (LowPart & 3) == 2 && CurrentStackLocation->Parameters.Read.Length )
      {
        MdlAddress = a2->MdlAddress;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MappedSystemVa = MdlAddress->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        ByteCount = a2->MdlAddress->ByteCount;
        if ( !MappedSystemVa )
        {
          a2->IoStatus.Status = -1073741670;
          a2->IoStatus.Information = 0;
          break;
        }
      }
      else
      {
        MappedSystemVa = a2->AssociatedIrp.MasterIrp;
        ByteCount = CurrentStackLocation->Parameters.Read.Length;
      }
      LOBYTE(Priority) = a2->RequestorMode;
      a2->IoStatus.Status = CngDeviceControl(
                              a2->AssociatedIrp.MasterIrp,
                              CurrentStackLocation->Parameters.Create.Options,
                              MappedSystemVa,
                              &ByteCount,
                              LowPart,
                              Priority);
      a2->IoStatus.Information = ByteCount;
      break;
  }
  Status = a2->IoStatus.Status;
  IofCompleteRequest(a2, 0);
  return Status;
}

```

## disassembly

```asm
0x1800301b0  push    rbx
0x1800301b2  push    rbp
0x1800301b3  push    rsi
0x1800301b4  push    rdi
0x1800301b5  sub     rsp, 38h
0x1800301b9  mov     rbx, [rdx+0B8h]
0x1800301c0  xor     ebp, ebp
0x1800301c2  mov     rdi, rdx
0x1800301c5  movzx   ecx, byte ptr [rbx]
0x1800301c8  test    ecx, ecx
0x1800301ca  jz      short loc_180030235
0x1800301cc  sub     ecx, 2
0x1800301cf  jz      short loc_180030235
0x1800301d1  sub     ecx, 1
0x1800301d4  jz      loc_1800302D3
0x1800301da  sub     ecx, 1
0x1800301dd  jz      loc_1800302CB
0x1800301e3  sub     ecx, 1
0x1800301e6  jz      short loc_18003025C
0x1800301e8  sub     ecx, 5
0x1800301eb  jz      loc_180030291
0x1800301f1  cmp     ecx, 4
0x1800301f4  jnz     short loc_18003023C
0x1800301f6  mov     esi, [rbx+18h]
0x1800301f9  mov     eax, esi
0x1800301fb  and     al, 3
0x1800301fd  cmp     al, 2
0x1800301ff  jz      short loc_180030275
0x180030201  mov     eax, [rbx+8]
0x180030204  mov     r8, [rdx+18h]
0x180030208  mov     [rsp+58h+arg_8], eax
0x18003020c  mov     al, [rdi+40h]
0x18003020f  lea     r9, [rsp+58h+arg_8]
0x180030214  mov     edx, [rbx+10h]
0x180030217  mov     rcx, [rdi+18h]
0x18003021b  mov     byte ptr [rsp+58h+Priority], al
0x18003021f  mov     [rsp+58h+BugCheckOnFailure], esi
0x180030223  call    CngDeviceControl
0x180030228  mov     [rdi+30h], eax
0x18003022b  mov     eax, [rsp+58h+arg_8]
0x18003022f  mov     [rdi+38h], rax
0x180030233  jmp     short loc_18003023C
0x180030235  mov     [rdx+30h], ebp
0x180030238  mov     [rdx+38h], rbp
0x18003023c  mov     ebx, [rdi+30h]
0x18003023f  xor     edx, edx; PriorityBoost
0x180030241  mov     rcx, rdi; Irp
0x180030244  call    cs:__imp_IofCompleteRequest
0x18003024b  nop     dword ptr [rax+rax+00h]
0x180030250  mov     eax, ebx
0x180030252  add     rsp, 38h
0x180030256  pop     rdi
0x180030257  pop     rsi
0x180030258  pop     rbp
0x180030259  pop     rbx
0x18003025a  retn
0x18003025c  cmp     dword ptr [rbx+10h], 5
0x180030260  jz      short loc_1800302AB
0x180030262  mov     ecx, [rbx+8]
0x180030265  mov     eax, 0C0000003h
0x18003026a  mov     [rdx+30h], eax
0x18003026d  mov     eax, ecx
0x18003026f  mov     [rdx+38h], rax
0x180030273  jmp     short loc_18003023C
0x180030275  cmp     [rbx+8], ebp
0x180030278  jz      short loc_180030201
0x18003027a  mov     rcx, [rdx+8]; MemoryDescriptorList
0x18003027e  test    byte ptr [rcx+0Ah], 5
0x180030282  jz      loc_1800A7454
0x180030288  mov     r8, [rcx+18h]
0x18003028c  jmp     loc_1800A7478
0x180030291  cmp     dword ptr [rbx+10h], 4
0x180030295  jnz     short loc_180030262
0x180030297  mov     rax, [rdx+18h]
0x18003029b  mov     ecx, 8
0x1800302a0  mov     dword ptr [rax], 39h ; '9'
0x1800302a6  jmp     loc_1800A749C
0x1800302ab  mov     rax, [rdx+18h]
0x1800302af  mov     ecx, 18h
0x1800302b4  mov     dword ptr [rax+10h], 1
0x1800302bb  mov     [rax+14h], bp
0x1800302bf  mov     [rax], rbp
0x1800302c2  mov     [rax+8], rbp
0x1800302c6  jmp     loc_1800A749C
0x1800302cb  mov     [rdx+30h], ebp
0x1800302ce  mov     eax, [rbx+8]
0x1800302d1  jmp     short loc_18003026F
0x1800302d3  mov     dword ptr [rdx+30h], 0C0000011h
0x1800302da  jmp     loc_180030238
0x1800a7454  xor     r9d, r9d; RequestedAddress
0x1800a7457  mov     [rsp+58h+Priority], 40000010h; Priority
0x1800a745f  xor     edx, edx; AccessMode
0x1800a7461  mov     [rsp+58h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1800a7465  lea     r8d, [r9+1]; CacheType
0x1800a7469  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1800a7470  nop     dword ptr [rax+rax+00h]
0x1800a7475  mov     r8, rax
0x1800a7478  mov     rax, [rdi+8]
0x1800a747c  mov     ecx, [rax+28h]
0x1800a747f  mov     [rsp+58h+arg_8], ecx
0x1800a7483  test    r8, r8
0x1800a7486  jnz     loc_18003020C
0x1800a748c  mov     dword ptr [rdi+30h], 0C000009Ah
0x1800a7493  mov     [rdi+38h], rbp
0x1800a7497  jmp     loc_18003023C
0x1800a749c  mov     eax, ebp
0x1800a749e  jmp     loc_18003026A
```
