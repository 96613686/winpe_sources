# CngDispatch

- ea: `0x180023140`
- end: `0x18002326f`
- name: `CngDispatch`
- size: `303`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180023140`
- `0x180023280`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800a2281`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800a2281`
- `ntoskrnl!IofCompleteRequest` at `0x1800231d4`
- `ntoskrnl!IofCompleteRequest` at `0x1800231d4`

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
0x180023140  push    rbx
0x180023142  push    rbp
0x180023143  push    rsi
0x180023144  push    rdi
0x180023145  sub     rsp, 38h
0x180023149  mov     rbx, [rdx+0B8h]
0x180023150  xor     ebp, ebp
0x180023152  mov     rdi, rdx
0x180023155  movzx   ecx, byte ptr [rbx]
0x180023158  test    ecx, ecx
0x18002315a  jz      short loc_1800231C5
0x18002315c  sub     ecx, 2
0x18002315f  jz      short loc_1800231C5
0x180023161  sub     ecx, 1
0x180023164  jz      loc_180023263
0x18002316a  sub     ecx, 1
0x18002316d  jz      loc_18002325B
0x180023173  sub     ecx, 1
0x180023176  jz      short loc_1800231EC
0x180023178  sub     ecx, 5
0x18002317b  jz      loc_180023221
0x180023181  cmp     ecx, 4
0x180023184  jnz     short loc_1800231CC
0x180023186  mov     esi, [rbx+18h]
0x180023189  mov     eax, esi
0x18002318b  and     al, 3
0x18002318d  cmp     al, 2
0x18002318f  jz      short loc_180023205
0x180023191  mov     eax, [rbx+8]
0x180023194  mov     r8, [rdx+18h]
0x180023198  mov     [rsp+58h+arg_8], eax
0x18002319c  mov     al, [rdi+40h]
0x18002319f  lea     r9, [rsp+58h+arg_8]
0x1800231a4  mov     edx, [rbx+10h]
0x1800231a7  mov     rcx, [rdi+18h]
0x1800231ab  mov     byte ptr [rsp+58h+Priority], al
0x1800231af  mov     [rsp+58h+BugCheckOnFailure], esi
0x1800231b3  call    CngDeviceControl
0x1800231b8  mov     [rdi+30h], eax
0x1800231bb  mov     eax, [rsp+58h+arg_8]
0x1800231bf  mov     [rdi+38h], rax
0x1800231c3  jmp     short loc_1800231CC
0x1800231c5  mov     [rdx+30h], ebp
0x1800231c8  mov     [rdx+38h], rbp
0x1800231cc  mov     ebx, [rdi+30h]
0x1800231cf  xor     edx, edx; PriorityBoost
0x1800231d1  mov     rcx, rdi; Irp
0x1800231d4  call    cs:__imp_IofCompleteRequest
0x1800231db  nop     dword ptr [rax+rax+00h]
0x1800231e0  mov     eax, ebx
0x1800231e2  add     rsp, 38h
0x1800231e6  pop     rdi
0x1800231e7  pop     rsi
0x1800231e8  pop     rbp
0x1800231e9  pop     rbx
0x1800231ea  retn
0x1800231ec  cmp     dword ptr [rbx+10h], 5
0x1800231f0  jz      short loc_18002323B
0x1800231f2  mov     ecx, [rbx+8]
0x1800231f5  mov     eax, 0C0000003h
0x1800231fa  mov     [rdx+30h], eax
0x1800231fd  mov     eax, ecx
0x1800231ff  mov     [rdx+38h], rax
0x180023203  jmp     short loc_1800231CC
0x180023205  cmp     [rbx+8], ebp
0x180023208  jz      short loc_180023191
0x18002320a  mov     rcx, [rdx+8]; MemoryDescriptorList
0x18002320e  test    byte ptr [rcx+0Ah], 5
0x180023212  jz      loc_1800A226C
0x180023218  mov     r8, [rcx+18h]
0x18002321c  jmp     loc_1800A2290
0x180023221  cmp     dword ptr [rbx+10h], 4
0x180023225  jnz     short loc_1800231F2
0x180023227  mov     rax, [rdx+18h]
0x18002322b  mov     ecx, 8
0x180023230  mov     dword ptr [rax], 39h ; '9'
0x180023236  jmp     loc_1800A22B4
0x18002323b  mov     rax, [rdx+18h]
0x18002323f  mov     ecx, 18h
0x180023244  mov     dword ptr [rax+10h], 1
0x18002324b  mov     [rax+14h], bp
0x18002324f  mov     [rax], rbp
0x180023252  mov     [rax+8], rbp
0x180023256  jmp     loc_1800A22B4
0x18002325b  mov     [rdx+30h], ebp
0x18002325e  mov     eax, [rbx+8]
0x180023261  jmp     short loc_1800231FF
0x180023263  mov     dword ptr [rdx+30h], 0C0000011h
0x18002326a  jmp     loc_1800231C8
0x1800a226c  xor     r9d, r9d; RequestedAddress
0x1800a226f  mov     [rsp+58h+Priority], 40000010h; Priority
0x1800a2277  xor     edx, edx; AccessMode
0x1800a2279  mov     [rsp+58h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1800a227d  lea     r8d, [r9+1]; CacheType
0x1800a2281  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1800a2288  nop     dword ptr [rax+rax+00h]
0x1800a228d  mov     r8, rax
0x1800a2290  mov     rax, [rdi+8]
0x1800a2294  mov     ecx, [rax+28h]
0x1800a2297  mov     [rsp+58h+arg_8], ecx
0x1800a229b  test    r8, r8
0x1800a229e  jnz     loc_18002319C
0x1800a22a4  mov     dword ptr [rdi+30h], 0C000009Ah
0x1800a22ab  mov     [rdi+38h], rbp
0x1800a22af  jmp     loc_1800231CC
0x1800a22b4  mov     eax, ebp
0x1800a22b6  jmp     loc_1800231FA
```
