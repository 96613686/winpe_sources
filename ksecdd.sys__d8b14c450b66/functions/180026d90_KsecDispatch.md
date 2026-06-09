# KsecDispatch

- ea: `0x180026d90`
- end: `0x180026f60`
- name: `KsecDispatch`
- size: `464`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007bd8`
- `0x18000b79c`
- `0x180026d90`
- `0x180026f68`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180026e58`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180026e58`
- `ntoskrnl!IofCompleteRequest` at `0x180026e96`
- `ntoskrnl!IofCompleteRequest` at `0x180026e96`

## pseudocode

```c
__int64 __fastcall KsecDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int LowPart; // ebx
  _DWORD *MappedSystemVa; // r8
  unsigned int v6; // ebx
  PMDL MdlAddress; // rcx
  ULONG_PTR Length; // rax
  struct _IRP *MasterIrp; // rax
  int ByteCount; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  switch ( CurrentStackLocation->MajorFunction )
  {
    case 0u:
    case 2u:
      a2->IoStatus.Information = 0;
LABEL_19:
      v6 = 0;
      goto LABEL_20;
    case 3u:
      v6 = -1073741807;
      a2->IoStatus.Information = 0;
      goto LABEL_20;
    case 4u:
      a2->IoStatus.Information = CurrentStackLocation->Parameters.Read.Length;
      goto LABEL_19;
    case 5u:
      if ( CurrentStackLocation->Parameters.Create.Options == 5 )
      {
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        MasterIrp->Flags = 1;
        *((_WORD *)&MasterIrp->Flags + 2) = 0;
        *(_QWORD *)&MasterIrp->Type = 0;
        MasterIrp->MdlAddress = 0;
        Length = 24;
        goto LABEL_34;
      }
LABEL_22:
      Length = CurrentStackLocation->Parameters.Read.Length;
      v6 = -1073741821;
LABEL_23:
      a2->IoStatus.Information = Length;
      goto LABEL_20;
    case 0xAu:
      if ( CurrentStackLocation->Parameters.Create.Options == 4 )
      {
        *(_DWORD *)a2->AssociatedIrp.MasterIrp = 57;
        Length = 8;
LABEL_34:
        v6 = 0;
        goto LABEL_23;
      }
      goto LABEL_22;
  }
  if ( CurrentStackLocation->MajorFunction != 14 )
  {
    if ( CurrentStackLocation->MajorFunction != 16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          30,
          WPP_47798432cc4f3443573e38da5669f213_Traceguids,
          CurrentStackLocation->MajorFunction);
      v6 = -1073741811;
      goto LABEL_20;
    }
    KsecShutdown();
    a2->IoStatus.Information = 0;
    goto LABEL_19;
  }
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
      v6 = -1073741670;
      a2->IoStatus.Information = 0;
LABEL_20:
      a2->IoStatus.Status = v6;
      IofCompleteRequest(a2, 0);
      return v6;
    }
  }
  else
  {
    MappedSystemVa = &a2->AssociatedIrp.MasterIrp->Type;
    ByteCount = CurrentStackLocation->Parameters.Read.Length;
  }
  v6 = KsecDeviceControl(
         (unsigned int *)a2->AssociatedIrp.MasterIrp,
         CurrentStackLocation->Parameters.Create.Options,
         MappedSystemVa,
         (unsigned int *)&ByteCount,
         LowPart,
         a2);
  if ( v6 != 259 )
  {
    a2->IoStatus.Information = (unsigned int)ByteCount;
    goto LABEL_20;
  }
  return v6;
}

```

## disassembly

```asm
0x180026d90  push    rbx
0x180026d92  push    rbp
0x180026d93  push    rsi
0x180026d94  push    rdi
0x180026d95  sub     rsp, 38h
0x180026d99  mov     rsi, [rdx+0B8h]
0x180026da0  xor     ebp, ebp
0x180026da2  mov     rdi, rdx
0x180026da5  movzx   r9d, byte ptr [rsi]
0x180026da9  mov     ecx, r9d
0x180026dac  test    r9d, r9d
0x180026daf  jz      loc_180026E88
0x180026db5  sub     ecx, 2
0x180026db8  jz      loc_180026E88
0x180026dbe  sub     ecx, 1
0x180026dc1  jz      loc_180026F52
0x180026dc7  sub     ecx, 1
0x180026dca  jz      loc_180026F46
0x180026dd0  sub     ecx, 1
0x180026dd3  jz      loc_180026EA4
0x180026dd9  sub     ecx, 5
0x180026ddc  jz      loc_180026F0D
0x180026de2  sub     ecx, 4
0x180026de5  jnz     loc_180026EBD
0x180026deb  mov     ebx, [rsi+18h]
0x180026dee  mov     eax, ebx
0x180026df0  and     al, 3
0x180026df2  cmp     al, 2
0x180026df4  jz      short loc_180026E34
0x180026df6  mov     eax, [rsi+8]
0x180026df9  mov     r8, [rdx+18h]; int
0x180026dfd  mov     [rsp+58h+arg_8], eax
0x180026e01  mov     edx, [rsi+10h]; int
0x180026e04  lea     r9, [rsp+58h+arg_8]; int
0x180026e09  mov     rcx, [rdi+18h]; int
0x180026e0d  mov     qword ptr [rsp+58h+Priority], rdi; Irp
0x180026e12  mov     [rsp+58h+BugCheckOnFailure], ebx; int
0x180026e16  call    KsecDeviceControl
0x180026e1b  mov     ebx, eax
0x180026e1d  cmp     eax, 103h
0x180026e22  jnz     loc_180026F03
0x180026e28  mov     eax, ebx
0x180026e2a  add     rsp, 38h
0x180026e2e  pop     rdi
0x180026e2f  pop     rsi
0x180026e30  pop     rbp
0x180026e31  pop     rbx
0x180026e32  retn
0x180026e34  cmp     [rsi+8], ebp
0x180026e37  jz      short loc_180026DF6
0x180026e39  mov     rcx, [rdx+8]; MemoryDescriptorList
0x180026e3d  test    byte ptr [rcx+0Ah], 5
0x180026e41  jnz     short loc_180026E82
0x180026e43  xor     r9d, r9d; RequestedAddress
0x180026e46  mov     [rsp+58h+Priority], 40000010h; Priority
0x180026e4e  xor     edx, edx; AccessMode
0x180026e50  mov     [rsp+58h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x180026e54  lea     r8d, [r9+1]; CacheType
0x180026e58  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180026e5f  nop     dword ptr [rax+rax+00h]
0x180026e64  mov     r8, rax
0x180026e67  mov     rax, [rdi+8]
0x180026e6b  mov     ecx, [rax+28h]
0x180026e6e  mov     [rsp+58h+arg_8], ecx
0x180026e72  test    r8, r8
0x180026e75  jnz     short loc_180026E01
0x180026e77  mov     ebx, 0C000009Ah
0x180026e7c  mov     [rdi+38h], rbp
0x180026e80  jmp     short loc_180026E8E
0x180026e82  mov     r8, [rcx+18h]
0x180026e86  jmp     short loc_180026E67
0x180026e88  mov     [rdx+38h], rbp
0x180026e8c  mov     ebx, ebp
0x180026e8e  xor     edx, edx; PriorityBoost
0x180026e90  mov     [rdi+30h], ebx
0x180026e93  mov     rcx, rdi; Irp
0x180026e96  call    cs:__imp_IofCompleteRequest
0x180026e9d  nop     dword ptr [rax+rax+00h]
0x180026ea2  jmp     short loc_180026E28
0x180026ea4  cmp     dword ptr [rsi+10h], 5
0x180026ea8  jz      short loc_180026F24
0x180026eaa  mov     eax, [rsi+8]
0x180026ead  mov     ebx, 0C0000003h
0x180026eb2  mov     ecx, 38h ; '8'
0x180026eb7  mov     [rdx+rcx], rax
0x180026ebb  jmp     short loc_180026E8E
0x180026ebd  cmp     ecx, 2
0x180026ec0  jz      short loc_180026EF8
0x180026ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ec9  lea     rax, WPP_GLOBAL_Control
0x180026ed0  cmp     rcx, rax
0x180026ed3  jz      short loc_180026EF1
0x180026ed5  mov     eax, [rcx+2Ch]
0x180026ed8  test    al, 1
0x180026eda  jz      short loc_180026EF1
0x180026edc  mov     rcx, [rcx+18h]
0x180026ee0  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x180026ee7  mov     edx, 1Eh
0x180026eec  call    WPP_SF_D
0x180026ef1  mov     ebx, 0C000000Dh
0x180026ef6  jmp     short loc_180026E8E
0x180026ef8  call    KsecShutdown
0x180026efd  mov     [rdi+38h], rbp
0x180026f01  jmp     short loc_180026E8C
0x180026f03  mov     ecx, [rsp+58h+arg_8]
0x180026f07  mov     [rdi+38h], rcx
0x180026f0b  jmp     short loc_180026E8E
0x180026f0d  cmp     dword ptr [rsi+10h], 4
0x180026f11  jnz     short loc_180026EAA
0x180026f13  mov     rax, [rdx+18h]
0x180026f17  mov     dword ptr [rax], 39h ; '9'
0x180026f1d  mov     eax, 8
0x180026f22  jmp     short loc_180026F3F
0x180026f24  mov     rax, [rdx+18h]
0x180026f28  mov     dword ptr [rax+10h], 1
0x180026f2f  mov     [rax+14h], bp
0x180026f33  mov     [rax], rbp
0x180026f36  mov     [rax+8], rbp
0x180026f3a  mov     eax, 18h
0x180026f3f  mov     ebx, ebp
0x180026f41  jmp     loc_180026EB2
0x180026f46  mov     eax, [rsi+8]
0x180026f49  mov     [rdx+38h], rax
0x180026f4d  jmp     loc_180026E8C
0x180026f52  mov     ebx, 0C0000011h
0x180026f57  mov     [rdx+38h], rbp
0x180026f5b  jmp     loc_180026E8E
```
