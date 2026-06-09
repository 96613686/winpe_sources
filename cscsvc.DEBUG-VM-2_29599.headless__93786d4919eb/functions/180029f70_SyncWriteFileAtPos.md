# SyncWriteFileAtPos

- ea: `0x180029f70`
- end: `0x18002a0b8`
- name: `SyncWriteFileAtPos`
- size: `328`
- prototype: `__int64 __fastcall(HANDLE hHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001fb40`

## callees

- `0x180029f70`
- `0x1800360c0`
- `0x180036394`
- `0x18007291c`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18002a039`
- `ntdll!NtWriteFile` at `0x18002a039`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a050`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a050`

## string_xrefs

- `0x180029fc4`: `SyncWriteFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToWrite: %d`
- `0x18002a076`: `SyncWriteFileAtPos: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncWriteFileAtPos(HANDLE hHandle, union _LARGE_INTEGER a2, void *a3, ULONG a4)
{
  unsigned int Status; // ebx
  struct _IO_STATUS_BLOCK v11; // [rsp+50h] [rbp-28h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp+10h] BYREF

  ByteOffset.QuadPart = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncWriteFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToWrite: %d",
      hHandle,
      a2.QuadPart,
      a3,
      a4);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqqD)(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      78,
      WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
      hHandle,
      (union _LARGE_INTEGER)a2.QuadPart,
      a3,
      a4);
  }
  ByteOffset = a2;
  Status = NtWriteFile(hHandle, 0, 0, 0, &v11, a3, a4, &ByteOffset, 0);
  if ( Status == 259 )
  {
    Status = 258;
    if ( !WaitForSingleObject(hHandle, 0x3E8u) )
      Status = v11.Status;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncWriteFileAtPos: 0x%x", Status);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 79, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Status);
  }
  return Status;
}

```

## disassembly

```asm
0x180029f70  mov     rax, rsp
0x180029f73  mov     [rax+8], rbx
0x180029f77  mov     [rax+18h], rbp
0x180029f7b  push    rsi
0x180029f7c  push    rdi
0x180029f7d  push    r14
0x180029f7f  sub     rsp, 60h
0x180029f83  xorps   xmm0, xmm0
0x180029f86  mov     qword ptr [rax+10h], 0
0x180029f8e  movups  xmmword ptr [rax-28h], xmm0
0x180029f92  mov     ebx, r9d
0x180029f95  mov     rsi, r8
0x180029f98  mov     rbp, rdx
0x180029f9b  mov     rdi, rcx
0x180029f9e  mov     rax, cs:WPP_GLOBAL_Control
0x180029fa5  lea     r14, WPP_GLOBAL_Control
0x180029fac  cmp     rax, r14
0x180029faf  jz      short loc_180029FFD
0x180029fb1  test    byte ptr [rax+6Ch], 4
0x180029fb5  jz      short loc_180029FFD
0x180029fb7  mov     r9, r8
0x180029fba  mov     dword ptr [rsp+78h+IoStatusBlock], ebx
0x180029fbe  mov     r8, rdx
0x180029fc1  mov     rdx, rcx
0x180029fc4  lea     rcx, aSyncwritefilea; "SyncWriteFileAtPos: Handle: 0x%p FilePo"...
0x180029fcb  call    SyncTraceOutputInternal
0x180029fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fd7  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180029fde  mov     [rsp+78h+Length], ebx
0x180029fe2  mov     edx, 4Eh ; 'N'
0x180029fe7  mov     [rsp+78h+Buffer], rsi
0x180029fec  mov     r9, rdi
0x180029fef  mov     [rsp+78h+IoStatusBlock], rbp
0x180029ff4  mov     rcx, [rcx+60h]
0x180029ff8  call    WPP_SF_qqqD
0x180029ffd  mov     [rsp+78h+Key], 0; Key
0x18002a006  lea     rax, [rsp+78h+arg_8]
0x18002a00e  mov     [rsp+78h+ByteOffset], rax; ByteOffset
0x18002a013  xor     r9d, r9d; ApcContext
0x18002a016  mov     [rsp+78h+Length], ebx; Length
0x18002a01a  lea     rax, [rsp+78h+var_28]
0x18002a01f  mov     [rsp+78h+Buffer], rsi; Buffer
0x18002a024  xor     r8d, r8d; ApcRoutine
0x18002a027  xor     edx, edx; Event
0x18002a029  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x18002a02e  mov     rcx, rdi; FileHandle
0x18002a031  mov     qword ptr [rsp+78h+arg_8], rbp
0x18002a039  call    cs:__imp_NtWriteFile
0x18002a03f  mov     ebx, eax
0x18002a041  cmp     eax, 103h
0x18002a046  jnz     short loc_18002A062
0x18002a048  mov     edx, 3E8h; dwMilliseconds
0x18002a04d  mov     rcx, rdi; hHandle
0x18002a050  call    cs:__imp_WaitForSingleObject
0x18002a056  test    eax, eax
0x18002a058  mov     ebx, 102h
0x18002a05d  cmovz   ebx, dword ptr [rsp+78h+var_28]
0x18002a062  mov     rax, cs:WPP_GLOBAL_Control
0x18002a069  cmp     rax, r14
0x18002a06c  jz      short loc_18002A0A1
0x18002a06e  test    byte ptr [rax+6Ch], 8
0x18002a072  jz      short loc_18002A0A1
0x18002a074  mov     edx, ebx
0x18002a076  lea     rcx, aSyncwritefilea_0; "SyncWriteFileAtPos: 0x%x"
0x18002a07d  call    SyncTraceOutputInternal
0x18002a082  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a089  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18002a090  mov     edx, 4Fh ; 'O'
0x18002a095  mov     r9d, ebx
0x18002a098  mov     rcx, [rcx+60h]
0x18002a09c  call    WPP_SF_d
0x18002a0a1  lea     r11, [rsp+78h+var_18]
0x18002a0a6  mov     eax, ebx
0x18002a0a8  mov     rbx, [r11+20h]
0x18002a0ac  mov     rbp, [r11+30h]
0x18002a0b0  mov     rsp, r11
0x18002a0b3  pop     r14
0x18002a0b5  pop     rdi
0x18002a0b6  pop     rsi
0x18002a0b7  retn
```
