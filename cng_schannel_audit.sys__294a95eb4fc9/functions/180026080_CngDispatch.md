# CngDispatch

- ea: `0x180026080`
- end: `0x1800261af`
- name: `CngDispatch`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180026080`
- `0x1800261c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800a06cb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800a06cb`
- `ntoskrnl!IofCompleteRequest` at `0x180026114`
- `ntoskrnl!IofCompleteRequest` at `0x180026114`

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
0x180026080  push    rbx
0x180026082  push    rbp
0x180026083  push    rsi
0x180026084  push    rdi
0x180026085  sub     rsp, 38h
0x180026089  mov     rbx, [rdx+0B8h]
0x180026090  xor     ebp, ebp
0x180026092  mov     rdi, rdx
0x180026095  movzx   ecx, byte ptr [rbx]
0x180026098  test    ecx, ecx
0x18002609a  jz      short loc_180026105
0x18002609c  sub     ecx, 2
0x18002609f  jz      short loc_180026105
0x1800260a1  sub     ecx, 1
0x1800260a4  jz      loc_1800261A3
0x1800260aa  sub     ecx, 1
0x1800260ad  jz      loc_18002619B
0x1800260b3  sub     ecx, 1
0x1800260b6  jz      short loc_18002612C
0x1800260b8  sub     ecx, 5
0x1800260bb  jz      loc_180026161
0x1800260c1  cmp     ecx, 4
0x1800260c4  jnz     short loc_18002610C
0x1800260c6  mov     esi, [rbx+18h]
0x1800260c9  mov     eax, esi
0x1800260cb  and     al, 3
0x1800260cd  cmp     al, 2
0x1800260cf  jz      short loc_180026145
0x1800260d1  mov     eax, [rbx+8]
0x1800260d4  mov     r8, [rdx+18h]
0x1800260d8  mov     [rsp+58h+arg_8], eax
0x1800260dc  mov     al, [rdi+40h]
0x1800260df  lea     r9, [rsp+58h+arg_8]
0x1800260e4  mov     edx, [rbx+10h]
0x1800260e7  mov     rcx, [rdi+18h]
0x1800260eb  mov     byte ptr [rsp+58h+Priority], al
0x1800260ef  mov     [rsp+58h+BugCheckOnFailure], esi
0x1800260f3  call    CngDeviceControl
0x1800260f8  mov     [rdi+30h], eax
0x1800260fb  mov     eax, [rsp+58h+arg_8]
0x1800260ff  mov     [rdi+38h], rax
0x180026103  jmp     short loc_18002610C
0x180026105  mov     [rdx+30h], ebp
0x180026108  mov     [rdx+38h], rbp
0x18002610c  mov     ebx, [rdi+30h]
0x18002610f  xor     edx, edx; PriorityBoost
0x180026111  mov     rcx, rdi; Irp
0x180026114  call    cs:__imp_IofCompleteRequest
0x18002611b  nop     dword ptr [rax+rax+00h]
0x180026120  mov     eax, ebx
0x180026122  add     rsp, 38h
0x180026126  pop     rdi
0x180026127  pop     rsi
0x180026128  pop     rbp
0x180026129  pop     rbx
0x18002612a  retn
0x18002612c  cmp     dword ptr [rbx+10h], 5
0x180026130  jz      short loc_18002617B
0x180026132  mov     ecx, [rbx+8]
0x180026135  mov     eax, 0C0000003h
0x18002613a  mov     [rdx+30h], eax
0x18002613d  mov     eax, ecx
0x18002613f  mov     [rdx+38h], rax
0x180026143  jmp     short loc_18002610C
0x180026145  cmp     [rbx+8], ebp
0x180026148  jz      short loc_1800260D1
0x18002614a  mov     rcx, [rdx+8]; MemoryDescriptorList
0x18002614e  test    byte ptr [rcx+0Ah], 5
0x180026152  jz      loc_1800A06B6
0x180026158  mov     r8, [rcx+18h]
0x18002615c  jmp     loc_1800A06DA
0x180026161  cmp     dword ptr [rbx+10h], 4
0x180026165  jnz     short loc_180026132
0x180026167  mov     rax, [rdx+18h]
0x18002616b  mov     ecx, 8
0x180026170  mov     dword ptr [rax], 39h ; '9'
0x180026176  jmp     loc_1800A06FE
0x18002617b  mov     rax, [rdx+18h]
0x18002617f  mov     ecx, 18h
0x180026184  mov     dword ptr [rax+10h], 1
0x18002618b  mov     [rax+14h], bp
0x18002618f  mov     [rax], rbp
0x180026192  mov     [rax+8], rbp
0x180026196  jmp     loc_1800A06FE
0x18002619b  mov     [rdx+30h], ebp
0x18002619e  mov     eax, [rbx+8]
0x1800261a1  jmp     short loc_18002613F
0x1800261a3  mov     dword ptr [rdx+30h], 0C0000011h
0x1800261aa  jmp     loc_180026108
0x1800a06b6  xor     r9d, r9d; RequestedAddress
0x1800a06b9  mov     [rsp+58h+Priority], 40000010h; Priority
0x1800a06c1  xor     edx, edx; AccessMode
0x1800a06c3  mov     [rsp+58h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1800a06c7  lea     r8d, [r9+1]; CacheType
0x1800a06cb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1800a06d2  nop     dword ptr [rax+rax+00h]
0x1800a06d7  mov     r8, rax
0x1800a06da  mov     rax, [rdi+8]
0x1800a06de  mov     ecx, [rax+28h]
0x1800a06e1  mov     [rsp+58h+arg_8], ecx
0x1800a06e5  test    r8, r8
0x1800a06e8  jnz     loc_1800260DC
0x1800a06ee  mov     dword ptr [rdi+30h], 0C000009Ah
0x1800a06f5  mov     [rdi+38h], rbp
0x1800a06f9  jmp     loc_18002610C
0x1800a06fe  mov     eax, ebp
0x1800a0700  jmp     loc_18002613A
```
