# LuafvPostDirectoryControl

- ea: `0x140003140`
- end: `0x140003223`
- name: `LuafvPostDirectoryControl`
- size: `227`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, const struct _FLT_RELATED_OBJECTS *, void *, FLT_POST_OPERATION_FLAGS)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400028e0`
- `0x140003140`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400031a5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400031a5`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400031e1`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400031e1`

## pseudocode

```c
__int64 __fastcall LuafvPostDirectoryControl(
        PFLT_CALLBACK_DATA Data,
        const struct _FLT_RELATED_OBJECTS *a2,
        void *a3,
        FLT_POST_OPERATION_FLAGS a4)
{
  NTSTATUS Status; // ecx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdi
  LARGE_INTEGER AllocationSize; // rcx
  PVOID v8; // rax
  PVOID EaBuffer; // rcx
  NTSTATUS v10; // eax
  _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+40h] [rbp+8h] BYREF

  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  Status = Data->IoStatus.Status;
  if ( (int)(Status + 0x80000000) >= 0 && Status != -2147483643 )
    return (unsigned int)RetPostOperationStatus;
  Iopb = Data->Iopb;
  AllocationSize = Iopb->Parameters.Create.AllocationSize;
  if ( AllocationSize.QuadPart )
  {
    if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
      v8 = *(PVOID *)(AllocationSize.QuadPart + 24);
    else
      v8 = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v8 )
    {
      v10 = -1073741670;
      goto LABEL_15;
    }
    EaBuffer = v8;
LABEL_14:
    v10 = LuafvMarkVirtualDirectoryEntries(EaBuffer, Iopb->Parameters.Read.Length);
LABEL_15:
    if ( v10 < 0 )
      goto LABEL_16;
    return (unsigned int)RetPostOperationStatus;
  }
  if ( (Data->Flags & 0xA) != 0 )
  {
    EaBuffer = Iopb->Parameters.Create.EaBuffer;
    goto LABEL_14;
  }
  if ( !FltDoCompletionProcessingWhenSafe(Data, a2, a3, a4, LuafvPostDirectoryControlSafe, &RetPostOperationStatus) )
  {
    v10 = -1073741823;
LABEL_16:
    Data->IoStatus.Status = v10;
    Data->IoStatus.Information = 0;
  }
  return (unsigned int)RetPostOperationStatus;
}

```

## disassembly

```asm
0x140003140  mov     [rsp+arg_8], rbx
0x140003145  push    rdi
0x140003146  sub     rsp, 30h
0x14000314a  mov     r10d, 80000000h
0x140003150  mov     [rsp+38h+RetPostOperationStatus], 0
0x140003158  mov     rbx, rcx
0x14000315b  mov     ecx, [rcx+18h]
0x14000315e  lea     eax, [rcx+r10]
0x140003162  test    r10d, eax
0x140003165  jnz     short loc_140003173
0x140003167  cmp     ecx, 80000005h
0x14000316d  jnz     loc_140003213
0x140003173  mov     rdi, [rbx+10h]
0x140003177  mov     rcx, [rdi+40h]; MemoryDescriptorList
0x14000317b  test    rcx, rcx
0x14000317e  jz      short loc_1400031C2
0x140003180  test    byte ptr [rcx+0Ah], 5
0x140003184  jz      short loc_14000318C
0x140003186  mov     rax, [rcx+18h]
0x14000318a  jmp     short loc_1400031B1
0x14000318c  xor     r9d, r9d; RequestedAddress
0x14000318f  mov     [rsp+38h+Priority], 40000010h; Priority
0x140003197  xor     edx, edx; AccessMode
0x140003199  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400031a1  lea     r8d, [r9+1]; CacheType
0x1400031a5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400031ac  nop     dword ptr [rax+rax+00h]
0x1400031b1  test    rax, rax
0x1400031b4  jz      short loc_1400031BB
0x1400031b6  mov     rcx, rax
0x1400031b9  jmp     short loc_1400031FC
0x1400031bb  mov     eax, 0C000009Ah
0x1400031c0  jmp     short loc_140003204
0x1400031c2  mov     eax, [rbx]
0x1400031c4  test    al, 0Ah
0x1400031c6  jnz     short loc_1400031F8
0x1400031c8  lea     rax, [rsp+38h+RetPostOperationStatus]
0x1400031cd  mov     rcx, rbx; Data
0x1400031d0  mov     qword ptr [rsp+38h+Priority], rax; RetPostOperationStatus
0x1400031d5  lea     rax, LuafvPostDirectoryControlSafe
0x1400031dc  mov     qword ptr [rsp+38h+BugCheckOnFailure], rax; SafePostCallback
0x1400031e1  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400031e8  nop     dword ptr [rax+rax+00h]
0x1400031ed  test    al, al
0x1400031ef  jnz     short loc_140003213
0x1400031f1  mov     eax, 0C0000001h
0x1400031f6  jmp     short loc_140003208
0x1400031f8  mov     rcx, [rdi+38h]
0x1400031fc  mov     edx, [rdi+18h]
0x1400031ff  call    LuafvMarkVirtualDirectoryEntries
0x140003204  test    eax, eax
0x140003206  jns     short loc_140003213
0x140003208  mov     [rbx+18h], eax
0x14000320b  mov     qword ptr [rbx+20h], 0
0x140003213  mov     eax, [rsp+38h+RetPostOperationStatus]
0x140003217  mov     rbx, [rsp+38h+arg_8]
0x14000321c  add     rsp, 30h
0x140003220  pop     rdi
0x140003221  retn
```
