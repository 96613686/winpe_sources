# SyncWriteFile

- ea: `0x1800339b4`
- end: `0x180033ac7`
- name: `SyncWriteFile`
- size: `275`
- prototype: `__int64 __fastcall(HANDLE hHandle, PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001fb40`

## callees

- `0x1800339b4`
- `0x1800360c0`
- `0x180036394`
- `0x18005fa04`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180033a54`
- `ntdll!NtWriteFile` at `0x180033a54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033a6b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033a6b`

## string_xrefs

- `0x1800339f0`: `SyncWriteFile: Handle: 0x%p Buffer: 0x%p BytesToWrite: %d`
- `0x180033a91`: `SyncWriteFile: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncWriteFile(HANDLE hHandle, PVOID Buffer, ULONG Length)
{
  unsigned int Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncWriteFile: Handle: 0x%p Buffer: 0x%p BytesToWrite: %d", hHandle, Buffer, Length);
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      82,
      WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
      hHandle,
      Buffer,
      Length);
  }
  Status = NtWriteFile(hHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, 0, 0);
  if ( Status == 259 )
  {
    Status = 258;
    if ( !WaitForSingleObject(hHandle, 0x3E8u) )
      Status = IoStatusBlock.Status;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncWriteFile: 0x%x", Status);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 83, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Status);
  }
  return Status;
}

```

## disassembly

```asm
0x1800339b4  push    rbx
0x1800339b6  push    rbp
0x1800339b7  push    rsi
0x1800339b8  push    rdi
0x1800339b9  sub     rsp, 68h
0x1800339bd  xorps   xmm0, xmm0
0x1800339c0  mov     ebx, r8d
0x1800339c3  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x1800339c8  mov     rsi, rdx
0x1800339cb  mov     rdi, rcx
0x1800339ce  mov     rax, cs:WPP_GLOBAL_Control
0x1800339d5  lea     rbp, WPP_GLOBAL_Control
0x1800339dc  cmp     rax, rbp
0x1800339df  jz      short loc_180033A24
0x1800339e1  test    byte ptr [rax+6Ch], 4
0x1800339e5  jz      short loc_180033A24
0x1800339e7  mov     r8, rdx
0x1800339ea  mov     r9d, ebx
0x1800339ed  mov     rdx, rcx
0x1800339f0  lea     rcx, aSyncwritefileH; "SyncWriteFile: Handle: 0x%p Buffer: 0x%"...
0x1800339f7  call    SyncTraceOutputInternal
0x1800339fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a03  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180033a0a  mov     edx, 52h ; 'R'
0x180033a0f  mov     dword ptr [rsp+88h+Buffer], ebx
0x180033a13  mov     r9, rdi
0x180033a16  mov     [rsp+88h+IoStatusBlock], rsi
0x180033a1b  mov     rcx, [rcx+60h]
0x180033a1f  call    WPP_SF_qqD
0x180033a24  mov     [rsp+88h+Key], 0; Key
0x180033a2d  lea     rax, [rsp+88h+var_38]
0x180033a32  mov     [rsp+88h+ByteOffset], 0; ByteOffset
0x180033a3b  xor     r9d, r9d; ApcContext
0x180033a3e  mov     [rsp+88h+Length], ebx; Length
0x180033a42  xor     r8d, r8d; ApcRoutine
0x180033a45  mov     [rsp+88h+Buffer], rsi; Buffer
0x180033a4a  xor     edx, edx; Event
0x180033a4c  mov     rcx, rdi; FileHandle
0x180033a4f  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x180033a54  call    cs:__imp_NtWriteFile
0x180033a5a  mov     ebx, eax
0x180033a5c  cmp     eax, 103h
0x180033a61  jnz     short loc_180033A7D
0x180033a63  mov     edx, 3E8h; dwMilliseconds
0x180033a68  mov     rcx, rdi; hHandle
0x180033a6b  call    cs:__imp_WaitForSingleObject
0x180033a71  test    eax, eax
0x180033a73  mov     ebx, 102h
0x180033a78  cmovz   ebx, dword ptr [rsp+88h+var_38]
0x180033a7d  mov     rax, cs:WPP_GLOBAL_Control
0x180033a84  cmp     rax, rbp
0x180033a87  jz      short loc_180033ABC
0x180033a89  test    byte ptr [rax+6Ch], 8
0x180033a8d  jz      short loc_180033ABC
0x180033a8f  mov     edx, ebx
0x180033a91  lea     rcx, aSyncwritefile0; "SyncWriteFile: 0x%x"
0x180033a98  call    SyncTraceOutputInternal
0x180033a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033aa4  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180033aab  mov     edx, 53h ; 'S'
0x180033ab0  mov     r9d, ebx
0x180033ab3  mov     rcx, [rcx+60h]
0x180033ab7  call    WPP_SF_d
0x180033abc  mov     eax, ebx
0x180033abe  add     rsp, 68h
0x180033ac2  pop     rdi
0x180033ac3  pop     rsi
0x180033ac4  pop     rbp
0x180033ac5  pop     rbx
0x180033ac6  retn
```
