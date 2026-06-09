# DbgkpWerWriteTriageDump

- ea: `0x1407525cc`
- end: `0x1407526b2`
- name: `DbgkpWerWriteTriageDump`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x140751e34`

## callees

- `0x1402a2f90`
- `0x1406dd4e0`
- `0x1406dd5c0`
- `0x1407523a4`
- `0x140752454`
- `0x1407525cc`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x1407525f2`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x1407525f2`

## string_xrefs

- `0x140752604`: `DBGK: DbgkWerWriteTriageDump: WerLiveKernelOpenDumpFile failed, status 0x%X\n`
- `0x140752665`: `DBGK: Triage dump write failed with Status 0x%X\n`

## pseudocode

```c
__int64 __fastcall DbgkpWerWriteTriageDump(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int updated; // ebx
  NTSTATUS v5; // eax
  int v6; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp+8h] BYREF

  FileHandle = 0;
  v2 = *(_QWORD *)(a1 + 96);
  IoStatusBlock = 0;
  v3 = WerLiveKernelOpenDumpFile(v2, &FileHandle);
  updated = v3;
  if ( v3 >= 0 )
  {
    updated = DbgkpWerUpdateTriageDumpHeader(a1);
    if ( updated >= 0 )
    {
      v5 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 136), *(_DWORD *)(a1 + 144), 0, 0);
      updated = v5;
      if ( v5 >= 0 )
      {
        v6 = DbgkpWerWriteSecondaryData(a1, FileHandle);
        updated = v6;
        if ( v6 < 0 )
          DbgPrintEx(5u, 0, "DBGK: Writing secondary data failed with Status 0x%X\n", (unsigned int)v6);
      }
      else
      {
        DbgPrintEx(5u, 0, "DBGK: Triage dump write failed with Status 0x%X\n", (unsigned int)v5);
      }
    }
  }
  else
  {
    DbgPrintEx(5u, 0, "DBGK: DbgkWerWriteTriageDump: WerLiveKernelOpenDumpFile failed, status 0x%X\n", (unsigned int)v3);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1407525cc  mov     rax, rsp
0x1407525cf  mov     [rax+10h], rbx
0x1407525d3  push    rdi
0x1407525d4  sub     rsp, 60h
0x1407525d8  mov     rdi, rcx
0x1407525db  mov     qword ptr [rax+8], 0
0x1407525e3  mov     rcx, [rcx+60h]
0x1407525e7  lea     rdx, [rax+8]
0x1407525eb  xorps   xmm0, xmm0
0x1407525ee  movups  xmmword ptr [rax-18h], xmm0
0x1407525f2  call    cs:__imp_WerLiveKernelOpenDumpFile
0x1407525f9  nop     dword ptr [rax+rax+00h]
0x1407525fe  mov     ebx, eax
0x140752600  test    eax, eax
0x140752602  jns     short loc_14075260D
0x140752604  lea     r8, aDbgkDbgkwerwri; "DBGK: DbgkWerWriteTriageDump: WerLiveKe"...
0x14075260b  jmp     short loc_140752688
0x14075260d  mov     rcx, rdi
0x140752610  call    DbgkpWerUpdateTriageDumpHeader
0x140752615  mov     ebx, eax
0x140752617  test    eax, eax
0x140752619  js      short loc_140752695
0x14075261b  mov     eax, [rdi+90h]
0x140752621  xor     r9d, r9d; ApcContext
0x140752624  mov     rcx, [rsp+68h+FileHandle]; FileHandle
0x140752629  xor     r8d, r8d; ApcRoutine
0x14075262c  mov     [rsp+68h+Key], 0; Key
0x140752635  xor     edx, edx; Event
0x140752637  mov     [rsp+68h+ByteOffset], 0; ByteOffset
0x140752640  mov     [rsp+68h+Length], eax; Length
0x140752644  mov     rax, [rdi+88h]
0x14075264b  mov     [rsp+68h+Buffer], rax; Buffer
0x140752650  lea     rax, [rsp+68h+var_18]
0x140752655  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14075265a  call    ZwWriteFile
0x14075265f  mov     ebx, eax
0x140752661  test    eax, eax
0x140752663  jns     short loc_14075266E
0x140752665  lea     r8, aDbgkTriageDump; "DBGK: Triage dump write failed with Sta"...
0x14075266c  jmp     short loc_140752688
0x14075266e  mov     rdx, [rsp+68h+FileHandle]
0x140752673  mov     rcx, rdi
0x140752676  call    DbgkpWerWriteSecondaryData
0x14075267b  mov     ebx, eax
0x14075267d  test    eax, eax
0x14075267f  jns     short loc_140752695
0x140752681  lea     r8, aDbgkWritingSec; "DBGK: Writing secondary data failed wit"...
0x140752688  xor     edx, edx; Level
0x14075268a  mov     r9d, eax
0x14075268d  lea     ecx, [rdx+5]; ComponentId
0x140752690  call    DbgPrintEx
0x140752695  mov     rcx, [rsp+68h+FileHandle]; Handle
0x14075269a  test    rcx, rcx
0x14075269d  jz      short loc_1407526A4
0x14075269f  call    ZwClose
0x1407526a4  mov     eax, ebx
0x1407526a6  mov     rbx, [rsp+68h+arg_8]
0x1407526ab  add     rsp, 60h
0x1407526af  pop     rdi
0x1407526b0  retn
```
