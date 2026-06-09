# LuafvPostDirectoryControlSafe

- ea: `0x140016410`
- end: `0x14001649a`
- name: `LuafvPostDirectoryControlSafe`
- size: `138`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002650`
- `0x140016410`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001645a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001645a`
- `FLTMGR!FltLockUserBuffer` at `0x14001641d`
- `FLTMGR!FltLockUserBuffer` at `0x14001641d`

## pseudocode

```c
__int64 __fastcall LuafvPostDirectoryControlSafe(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        PVOID CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  NTSTATUS v5; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdi
  LARGE_INTEGER AllocationSize; // rcx
  char *v8; // rax

  v5 = FltLockUserBuffer(Data);
  if ( v5 < 0 )
    goto LABEL_9;
  Iopb = Data->Iopb;
  AllocationSize = Iopb->Parameters.Create.AllocationSize;
  if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
    v8 = *(char **)(AllocationSize.QuadPart + 24);
  else
    v8 = (char *)MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v8 )
  {
    v5 = -1073741670;
LABEL_9:
    Data->IoStatus.Status = v5;
    Data->IoStatus.Information = 0;
    return 0;
  }
  v5 = LuafvMarkVirtualDirectoryEntries(v8, Iopb->Parameters.Read.Length);
  if ( v5 < 0 )
    goto LABEL_9;
  return 0;
}

```

## disassembly

```asm
0x140016410  mov     [rsp+arg_0], rbx
0x140016415  push    rdi
0x140016416  sub     rsp, 30h
0x14001641a  mov     rbx, rcx
0x14001641d  call    cs:__imp_FltLockUserBuffer
0x140016424  nop     dword ptr [rax+rax+00h]
0x140016429  test    eax, eax
0x14001642b  js      short loc_140016481
0x14001642d  mov     rdi, [rbx+10h]
0x140016431  mov     rcx, [rdi+40h]; MemoryDescriptorList
0x140016435  test    byte ptr [rcx+0Ah], 5
0x140016439  jz      short loc_140016441
0x14001643b  mov     rax, [rcx+18h]
0x14001643f  jmp     short loc_140016466
0x140016441  xor     r9d, r9d; RequestedAddress
0x140016444  mov     [rsp+38h+Priority], 40000010h; Priority
0x14001644c  xor     edx, edx; AccessMode
0x14001644e  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016456  lea     r8d, [r9+1]; CacheType
0x14001645a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016461  nop     dword ptr [rax+rax+00h]
0x140016466  test    rax, rax
0x140016469  jz      short loc_14001647C
0x14001646b  mov     edx, [rdi+18h]
0x14001646e  mov     rcx, rax
0x140016471  call    LuafvMarkVirtualDirectoryEntries
0x140016476  test    eax, eax
0x140016478  jns     short loc_14001648C
0x14001647a  jmp     short loc_140016481
0x14001647c  mov     eax, 0C000009Ah
0x140016481  mov     [rbx+18h], eax
0x140016484  mov     qword ptr [rbx+20h], 0
0x14001648c  mov     rbx, [rsp+38h+arg_0]
0x140016491  xor     eax, eax
0x140016493  add     rsp, 30h
0x140016497  pop     rdi
0x140016498  retn
```
