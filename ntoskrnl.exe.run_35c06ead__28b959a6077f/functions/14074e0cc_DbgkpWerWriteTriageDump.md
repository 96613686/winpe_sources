# DbgkpWerWriteTriageDump

- ea: `0x14074e0cc`
- end: `0x14074e1b2`
- name: `DbgkpWerWriteTriageDump`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x14074d934`

## callees

- `0x14020fe90`
- `0x1406da990`
- `0x1406daa70`
- `0x14074dea4`
- `0x14074df54`
- `0x14074e0cc`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14074e0f2`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14074e0f2`

## string_xrefs

- `0x14074e104`: `DBGK: DbgkWerWriteTriageDump: WerLiveKernelOpenDumpFile failed, status 0x%X\n`
- `0x14074e165`: `DBGK: Triage dump write failed with Status 0x%X\n`

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
0x14074e0cc  mov     rax, rsp
0x14074e0cf  mov     [rax+10h], rbx
0x14074e0d3  push    rdi
0x14074e0d4  sub     rsp, 60h
0x14074e0d8  mov     rdi, rcx
0x14074e0db  mov     qword ptr [rax+8], 0
0x14074e0e3  mov     rcx, [rcx+60h]
0x14074e0e7  lea     rdx, [rax+8]
0x14074e0eb  xorps   xmm0, xmm0
0x14074e0ee  movups  xmmword ptr [rax-18h], xmm0
0x14074e0f2  call    cs:__imp_WerLiveKernelOpenDumpFile
0x14074e0f9  nop     dword ptr [rax+rax+00h]
0x14074e0fe  mov     ebx, eax
0x14074e100  test    eax, eax
0x14074e102  jns     short loc_14074E10D
0x14074e104  lea     r8, aDbgkDbgkwerwri; "DBGK: DbgkWerWriteTriageDump: WerLiveKe"...
0x14074e10b  jmp     short loc_14074E188
0x14074e10d  mov     rcx, rdi
0x14074e110  call    DbgkpWerUpdateTriageDumpHeader
0x14074e115  mov     ebx, eax
0x14074e117  test    eax, eax
0x14074e119  js      short loc_14074E195
0x14074e11b  mov     eax, [rdi+90h]
0x14074e121  xor     r9d, r9d; ApcContext
0x14074e124  mov     rcx, [rsp+68h+FileHandle]; FileHandle
0x14074e129  xor     r8d, r8d; ApcRoutine
0x14074e12c  mov     [rsp+68h+Key], 0; Key
0x14074e135  xor     edx, edx; Event
0x14074e137  mov     [rsp+68h+ByteOffset], 0; ByteOffset
0x14074e140  mov     [rsp+68h+Length], eax; Length
0x14074e144  mov     rax, [rdi+88h]
0x14074e14b  mov     [rsp+68h+Buffer], rax; Buffer
0x14074e150  lea     rax, [rsp+68h+var_18]
0x14074e155  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14074e15a  call    ZwWriteFile
0x14074e15f  mov     ebx, eax
0x14074e161  test    eax, eax
0x14074e163  jns     short loc_14074E16E
0x14074e165  lea     r8, aDbgkTriageDump; "DBGK: Triage dump write failed with Sta"...
0x14074e16c  jmp     short loc_14074E188
0x14074e16e  mov     rdx, [rsp+68h+FileHandle]
0x14074e173  mov     rcx, rdi
0x14074e176  call    DbgkpWerWriteSecondaryData
0x14074e17b  mov     ebx, eax
0x14074e17d  test    eax, eax
0x14074e17f  jns     short loc_14074E195
0x14074e181  lea     r8, aDbgkWritingSec; "DBGK: Writing secondary data failed wit"...
0x14074e188  xor     edx, edx; Level
0x14074e18a  mov     r9d, eax
0x14074e18d  lea     ecx, [rdx+5]; ComponentId
0x14074e190  call    DbgPrintEx
0x14074e195  mov     rcx, [rsp+68h+FileHandle]; Handle
0x14074e19a  test    rcx, rcx
0x14074e19d  jz      short loc_14074E1A4
0x14074e19f  call    ZwClose
0x14074e1a4  mov     eax, ebx
0x14074e1a6  mov     rbx, [rsp+68h+arg_8]
0x14074e1ab  add     rsp, 60h
0x14074e1af  pop     rdi
0x14074e1b0  retn
```
