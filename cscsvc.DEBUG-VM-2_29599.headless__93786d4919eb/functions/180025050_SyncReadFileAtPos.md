# SyncReadFileAtPos

- ea: `0x180025050`
- end: `0x180025199`
- name: `SyncReadFileAtPos`
- size: `329`
- prototype: `__int64 __fastcall(HANDLE hHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001fb40`

## callees

- `0x180025050`
- `0x1800360c0`
- `0x180036394`
- `0x18007291c`

## import_xrefs

- `ntdll!NtReadFile` at `0x1800250c7`
- `ntdll!NtReadFile` at `0x1800250c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025150`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025150`

## string_xrefs

- `0x180025107`: `SyncReadFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToRead: %d`
- `0x180025169`: `SyncReadFileAtPos: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncReadFileAtPos(HANDLE hHandle, union _LARGE_INTEGER a2, void *a3, ULONG a4)
{
  unsigned int Status; // ebx
  struct _IO_STATUS_BLOCK v11; // [rsp+50h] [rbp-48h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+A8h] [rbp+10h] BYREF

  v11 = 0;
  ByteOffset.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncReadFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToRead: %d",
      hHandle,
      a2.QuadPart,
      a3,
      a4);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqqD)(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      76,
      WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
      hHandle,
      (union _LARGE_INTEGER)a2.QuadPart,
      a3,
      a4);
  }
  ByteOffset = a2;
  Status = NtReadFile(hHandle, 0, 0, 0, &v11, a3, a4, &ByteOffset, 0);
  if ( Status == 259 )
  {
    Status = 258;
    if ( !WaitForSingleObject(hHandle, 0x3E8u) )
      Status = v11.Status;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncReadFileAtPos: 0x%x", Status);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 77, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Status);
  }
  return Status;
}

```

## disassembly

```asm
0x180025050  push    rbx
0x180025052  push    rbp
0x180025053  push    rsi
0x180025054  push    rdi
0x180025055  push    r14
0x180025057  push    r15
0x180025059  sub     rsp, 68h
0x18002505d  xorps   xmm0, xmm0
0x180025060  xor     r15d, r15d
0x180025063  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180025068  mov     qword ptr [rsp+98h+arg_8], r15
0x180025070  mov     ebx, r9d
0x180025073  mov     rsi, r8
0x180025076  mov     rbp, rdx
0x180025079  mov     rdi, rcx
0x18002507c  mov     rax, cs:WPP_GLOBAL_Control
0x180025083  lea     r14, WPP_GLOBAL_Control
0x18002508a  cmp     rax, r14
0x18002508d  jnz     short loc_1800250F7
0x18002508f  mov     [rsp+98h+Key], r15; Key
0x180025094  lea     rax, [rsp+98h+arg_8]
0x18002509c  mov     [rsp+98h+ByteOffset], rax; ByteOffset
0x1800250a1  xor     r9d, r9d; ApcContext
0x1800250a4  mov     [rsp+98h+Length], ebx; Length
0x1800250a8  lea     rax, [rsp+98h+var_48]
0x1800250ad  mov     [rsp+98h+Buffer], rsi; Buffer
0x1800250b2  xor     r8d, r8d; ApcRoutine
0x1800250b5  xor     edx, edx; Event
0x1800250b7  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x1800250bc  mov     rcx, rdi; FileHandle
0x1800250bf  mov     qword ptr [rsp+98h+arg_8], rbp
0x1800250c7  call    cs:__imp_NtReadFile
0x1800250cd  mov     ebx, eax
0x1800250cf  cmp     eax, 103h
0x1800250d4  jz      short loc_180025148
0x1800250d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800250dd  cmp     rax, r14
0x1800250e0  jz      short loc_1800250E8
0x1800250e2  test    byte ptr [rax+6Ch], 8
0x1800250e6  jnz     short loc_180025167
0x1800250e8  mov     eax, ebx
0x1800250ea  add     rsp, 68h
0x1800250ee  pop     r15
0x1800250f0  pop     r14
0x1800250f2  pop     rdi
0x1800250f3  pop     rsi
0x1800250f4  pop     rbp
0x1800250f5  pop     rbx
0x1800250f6  retn
0x1800250f7  test    byte ptr [rax+6Ch], 4
0x1800250fb  jz      short loc_18002508F
0x1800250fd  mov     r9, rsi
0x180025100  mov     dword ptr [rsp+98h+IoStatusBlock], ebx
0x180025104  mov     r8, rbp
0x180025107  lea     rcx, aSyncreadfileat; "SyncReadFileAtPos: Handle: 0x%p FilePos"...
0x18002510e  mov     rdx, rdi
0x180025111  call    SyncTraceOutputInternal
0x180025116  mov     rcx, cs:WPP_GLOBAL_Control
0x18002511d  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180025124  mov     [rsp+98h+Length], ebx
0x180025128  mov     edx, 4Ch ; 'L'
0x18002512d  mov     [rsp+98h+Buffer], rsi
0x180025132  mov     r9, rdi
0x180025135  mov     [rsp+98h+IoStatusBlock], rbp
0x18002513a  mov     rcx, [rcx+60h]
0x18002513e  call    WPP_SF_qqqD
0x180025143  jmp     loc_18002508F
0x180025148  mov     edx, 3E8h; dwMilliseconds
0x18002514d  mov     rcx, rdi; hHandle
0x180025150  call    cs:__imp_WaitForSingleObject
0x180025156  test    eax, eax
0x180025158  mov     ebx, 102h
0x18002515d  cmovz   ebx, dword ptr [rsp+98h+var_48]
0x180025162  jmp     loc_1800250D6
0x180025167  mov     edx, ebx
0x180025169  lea     rcx, aSyncreadfileat_0; "SyncReadFileAtPos: 0x%x"
0x180025170  call    SyncTraceOutputInternal
0x180025175  mov     rcx, cs:WPP_GLOBAL_Control
0x18002517c  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180025183  mov     edx, 4Dh ; 'M'
0x180025188  mov     r9d, ebx
0x18002518b  mov     rcx, [rcx+60h]
0x18002518f  call    WPP_SF_d
0x180025194  jmp     loc_1800250E8
```
