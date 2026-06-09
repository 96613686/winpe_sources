# LuafvPostDirectoryControl

- ea: `0x140002f10`
- end: `0x140002ff3`
- name: `LuafvPostDirectoryControl`
- size: `227`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002650`
- `0x140002f10`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140002f75`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140002f75`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x140002fb1`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x140002fb1`

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
0x140002f10  mov     [rsp+arg_8], rbx
0x140002f15  push    rdi
0x140002f16  sub     rsp, 30h
0x140002f1a  mov     r10d, 80000000h
0x140002f20  mov     [rsp+38h+RetPostOperationStatus], 0
0x140002f28  mov     rbx, rcx
0x140002f2b  mov     ecx, [rcx+18h]
0x140002f2e  lea     eax, [rcx+r10]
0x140002f32  test    r10d, eax
0x140002f35  jnz     short loc_140002F43
0x140002f37  cmp     ecx, 80000005h
0x140002f3d  jnz     loc_140002FE3
0x140002f43  mov     rdi, [rbx+10h]
0x140002f47  mov     rcx, [rdi+40h]; MemoryDescriptorList
0x140002f4b  test    rcx, rcx
0x140002f4e  jz      short loc_140002F92
0x140002f50  test    byte ptr [rcx+0Ah], 5
0x140002f54  jz      short loc_140002F5C
0x140002f56  mov     rax, [rcx+18h]
0x140002f5a  jmp     short loc_140002F81
0x140002f5c  xor     r9d, r9d; RequestedAddress
0x140002f5f  mov     [rsp+38h+Priority], 40000010h; Priority
0x140002f67  xor     edx, edx; AccessMode
0x140002f69  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140002f71  lea     r8d, [r9+1]; CacheType
0x140002f75  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140002f7c  nop     dword ptr [rax+rax+00h]
0x140002f81  test    rax, rax
0x140002f84  jz      short loc_140002F8B
0x140002f86  mov     rcx, rax
0x140002f89  jmp     short loc_140002FCC
0x140002f8b  mov     eax, 0C000009Ah
0x140002f90  jmp     short loc_140002FD4
0x140002f92  mov     eax, [rbx]
0x140002f94  test    al, 0Ah
0x140002f96  jnz     short loc_140002FC8
0x140002f98  lea     rax, [rsp+38h+RetPostOperationStatus]
0x140002f9d  mov     rcx, rbx; Data
0x140002fa0  mov     qword ptr [rsp+38h+Priority], rax; RetPostOperationStatus
0x140002fa5  lea     rax, LuafvPostDirectoryControlSafe
0x140002fac  mov     qword ptr [rsp+38h+BugCheckOnFailure], rax; SafePostCallback
0x140002fb1  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x140002fb8  nop     dword ptr [rax+rax+00h]
0x140002fbd  test    al, al
0x140002fbf  jnz     short loc_140002FE3
0x140002fc1  mov     eax, 0C0000001h
0x140002fc6  jmp     short loc_140002FD8
0x140002fc8  mov     rcx, [rdi+38h]
0x140002fcc  mov     edx, [rdi+18h]
0x140002fcf  call    LuafvMarkVirtualDirectoryEntries
0x140002fd4  test    eax, eax
0x140002fd6  jns     short loc_140002FE3
0x140002fd8  mov     [rbx+18h], eax
0x140002fdb  mov     qword ptr [rbx+20h], 0
0x140002fe3  mov     eax, [rsp+38h+RetPostOperationStatus]
0x140002fe7  mov     rbx, [rsp+38h+arg_8]
0x140002fec  add     rsp, 30h
0x140002ff0  pop     rdi
0x140002ff1  retn
```
