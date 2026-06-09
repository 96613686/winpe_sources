# CscDriverpFsControlEx

- ea: `0x1800036b0`
- end: `0x18000391a`
- name: `CscDriverpFsControlEx`
- size: `618`
- prototype: `__int64 __fastcall(HANDLE FileHandle, __int64, _DWORD *, void *, ULONG, PVOID, ULONG)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001020`
- `0x1800016b0`
- `0x180002080`
- `0x180002a40`
- `0x180002db0`
- `0x180003920`

## callees

- `0x1800036b0`
- `0x180007bf4`
- `0x180008ccc`
- `0x180008ef4`

## import_xrefs

- `ntdll!NtClose` at `0x1800037ca`
- `ntdll!NtClose` at `0x1800037ca`
- `ntdll!NtFsControlFile` at `0x180003777`
- `ntdll!NtFsControlFile` at `0x180003777`
- `ntdll!NtCreateEvent` at `0x180003735`
- `ntdll!NtCreateEvent` at `0x180003735`
- `ntdll!NtWaitForSingleObject` at `0x18000381b`
- `ntdll!NtWaitForSingleObject` at `0x18000381b`

## pseudocode

```c
__int64 __fastcall CscDriverpFsControlEx(
        HANDLE FileHandle,
        __int64 a2,
        _DWORD *a3,
        void *a4,
        ULONG a5,
        PVOID a6,
        ULONG a7)
{
  ULONG OutputBufferLength; // edi
  PVOID OutputBuffer; // rsi
  ULONG InputBufferLength; // ebp
  NTSTATUS v13; // eax
  __int64 v14; // r8
  unsigned int Status; // ebx
  char *v16; // rcx
  __int64 v18; // rdx
  void *EventHandle; // [rsp+50h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-40h] BYREF

  IoStatusBlock = 0;
  EventHandle = 0;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || *((char *)WPP_GLOBAL_Control + 68) >= 0
    || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
  {
    OutputBufferLength = a7;
    OutputBuffer = a6;
    InputBufferLength = a5;
  }
  else
  {
    OutputBufferLength = a7;
    OutputBuffer = a6;
    InputBufferLength = a5;
    WPP_SF_qcqqDqD(*((_QWORD *)WPP_GLOBAL_Control + 7), a2, a3, FileHandle, 89, a3, a4, a5, a6, a7);
  }
  v13 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
  Status = v13;
  if ( v13 < 0 )
  {
    v16 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 68) >= 0 )
      goto LABEL_8;
    v18 = 25;
LABEL_23:
    WPP_SF_d(*((_QWORD *)v16 + 7), v18, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, (unsigned int)v13);
    goto LABEL_7;
  }
  Status = NtFsControlFile(
             FileHandle,
             EventHandle,
             0,
             0,
             &IoStatusBlock,
             0x901AFu,
             a4,
             InputBufferLength,
             OutputBuffer,
             OutputBufferLength);
  if ( Status != 259 )
  {
LABEL_6:
    *a3 = IoStatusBlock.Information;
LABEL_7:
    v16 = (char *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v13 = NtWaitForSingleObject(EventHandle, 0, 0);
  Status = v13;
  if ( !v13 )
  {
    Status = IoStatusBlock.Status;
    goto LABEL_6;
  }
  if ( v13 < 0 )
  {
    v16 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 68) >= 0 )
      goto LABEL_8;
    v18 = 27;
    goto LABEL_23;
  }
  v16 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 68) < 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      26,
      WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
      (unsigned int)v13);
    v16 = (char *)WPP_GLOBAL_Control;
  }
  Status = -1073740768;
LABEL_8:
  if ( EventHandle )
  {
    NtClose(EventHandle);
    v16 = (char *)WPP_GLOBAL_Control;
  }
  if ( v16 != (char *)&WPP_GLOBAL_Control && v16[68] < 0 && (unsigned __int8)v16[65] >= 4u )
    WPP_SF_DD(*((_QWORD *)v16 + 7), 28, v14, (unsigned int)*a3, Status);
  return Status;
}

```

## disassembly

```asm
0x1800036b0  mov     rax, rsp
0x1800036b3  push    rbx
0x1800036b4  push    r14
0x1800036b6  sub     rsp, 88h
0x1800036bd  mov     [rax+8], rbp
0x1800036c1  xorps   xmm0, xmm0
0x1800036c4  mov     [rax+10h], rsi
0x1800036c8  mov     r14, r8
0x1800036cb  mov     [rax+18h], rdi
0x1800036cf  mov     [rax-18h], r12
0x1800036d3  mov     r12, rcx
0x1800036d6  mov     [rax-20h], r13
0x1800036da  mov     [rax-28h], r15
0x1800036de  mov     r15, r9
0x1800036e1  movups  xmmword ptr [rax-40h], xmm0
0x1800036e5  mov     qword ptr [rax-48h], 0
0x1800036ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036f4  lea     r13, WPP_GLOBAL_Control
0x1800036fb  cmp     rcx, r13
0x1800036fe  jz      short loc_18000370A
0x180003700  test    byte ptr [rcx+44h], 80h
0x180003704  jnz     loc_18000388C
0x18000370a  mov     edi, [rsp+98h+arg_30]
0x180003711  mov     rsi, [rsp+98h+arg_28]
0x180003719  mov     ebp, [rsp+98h+arg_20]
0x180003720  xor     r9d, r9d; EventType
0x180003723  mov     [rsp+98h+InitialState], 0; InitialState
0x180003728  xor     r8d, r8d; ObjectAttributes
0x18000372b  lea     rcx, [rsp+98h+EventHandle]; EventHandle
0x180003730  mov     edx, 1F0003h; DesiredAccess
0x180003735  call    cs:__imp_NtCreateEvent
0x18000373b  mov     ebx, eax
0x18000373d  test    eax, eax
0x18000373f  js      loc_180003834
0x180003745  mov     rdx, [rsp+98h+EventHandle]; Event
0x18000374a  lea     rax, [rsp+98h+IoStatusBlock]
0x18000374f  mov     [rsp+98h+OutputBufferLength], edi; OutputBufferLength
0x180003753  xor     r9d, r9d; ApcContext
0x180003756  mov     [rsp+98h+OutputBuffer], rsi; OutputBuffer
0x18000375b  xor     r8d, r8d; ApcRoutine
0x18000375e  mov     [rsp+98h+InputBufferLength], ebp; InputBufferLength
0x180003762  mov     rcx, r12; FileHandle
0x180003765  mov     [rsp+98h+InputBuffer], r15; InputBuffer
0x18000376a  mov     [rsp+98h+FsControlCode], 901AFh; FsControlCode
0x180003772  mov     qword ptr [rsp+98h+InitialState], rax; IoStatusBlock
0x180003777  call    cs:__imp_NtFsControlFile
0x18000377d  mov     ebx, eax
0x18000377f  cmp     eax, 103h
0x180003784  jz      loc_180003811
0x18000378a  mov     eax, dword ptr [rsp+98h+IoStatusBlock.Information]
0x18000378e  mov     [r14], eax
0x180003791  mov     rcx, cs:WPP_GLOBAL_Control
0x180003798  mov     rax, [rsp+98h+EventHandle]
0x18000379d  mov     r15, [rsp+98h+var_28]
0x1800037a2  mov     r12, [rsp+98h+var_18]
0x1800037aa  mov     rdi, [rsp+98h+arg_10]
0x1800037b2  mov     rsi, [rsp+98h+arg_8]
0x1800037ba  mov     rbp, [rsp+98h+arg_0]
0x1800037c2  test    rax, rax
0x1800037c5  jz      short loc_1800037D7
0x1800037c7  mov     rcx, rax; Handle
0x1800037ca  call    cs:__imp_NtClose
0x1800037d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037d7  cmp     rcx, r13
0x1800037da  mov     r13, [rsp+98h+var_20]
0x1800037df  jnz     short loc_1800037EE
0x1800037e1  mov     eax, ebx
0x1800037e3  add     rsp, 88h
0x1800037ea  pop     r14
0x1800037ec  pop     rbx
0x1800037ed  retn
0x1800037ee  test    byte ptr [rcx+44h], 80h
0x1800037f2  jz      short loc_1800037E1
0x1800037f4  cmp     byte ptr [rcx+41h], 4
0x1800037f8  jb      short loc_1800037E1
0x1800037fa  mov     r9d, [r14]
0x1800037fd  mov     edx, 1Ch
0x180003802  mov     rcx, [rcx+38h]
0x180003806  mov     dword ptr [rsp+98h+InitialState], ebx
0x18000380a  call    WPP_SF_DD
0x18000380f  jmp     short loc_1800037E1
0x180003811  mov     rcx, [rsp+98h+EventHandle]; Handle
0x180003816  xor     r8d, r8d; Timeout
0x180003819  xor     edx, edx; Alertable
0x18000381b  call    cs:__imp_NtWaitForSingleObject
0x180003821  mov     ebx, eax
0x180003823  test    eax, eax
0x180003825  jnz     loc_1800038D9
0x18000382b  mov     ebx, dword ptr [rsp+98h+IoStatusBlock]
0x18000382f  jmp     loc_18000378A
0x180003834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000383b  cmp     rcx, r13
0x18000383e  jz      loc_180003798
0x180003844  test    byte ptr [rcx+44h], 80h
0x180003848  jz      loc_180003798
0x18000384e  mov     edx, 19h
0x180003853  jmp     short loc_180003874
0x180003855  mov     rcx, cs:WPP_GLOBAL_Control
0x18000385c  cmp     rcx, r13
0x18000385f  jz      loc_180003798
0x180003865  test    byte ptr [rcx+44h], 80h
0x180003869  jz      loc_180003798
0x18000386f  mov     edx, 1Bh
0x180003874  mov     rcx, [rcx+38h]
0x180003878  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x18000387f  mov     r9d, eax
0x180003882  call    WPP_SF_d
0x180003887  jmp     loc_180003791
0x18000388c  cmp     byte ptr [rcx+41h], 4
0x180003890  jb      loc_18000370A
0x180003896  mov     edi, [rsp+98h+arg_30]
0x18000389d  mov     r9, r12
0x1800038a0  mov     rsi, [rsp+98h+arg_28]
0x1800038a8  mov     ebp, [rsp+98h+arg_20]
0x1800038af  mov     rcx, [rcx+38h]
0x1800038b3  mov     [rsp+98h+OutputBufferLength], edi
0x1800038b7  mov     [rsp+98h+OutputBuffer], rsi
0x1800038bc  mov     [rsp+98h+InputBufferLength], ebp
0x1800038c0  mov     [rsp+98h+InputBuffer], r15
0x1800038c5  mov     qword ptr [rsp+98h+FsControlCode], r14
0x1800038ca  mov     [rsp+98h+InitialState], 59h ; 'Y'
0x1800038cf  call    WPP_SF_qcqqDqD
0x1800038d4  jmp     loc_180003720
0x1800038d9  js      loc_180003855
0x1800038df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038e6  cmp     rcx, r13
0x1800038e9  jz      short loc_180003910
0x1800038eb  test    byte ptr [rcx+44h], 80h
0x1800038ef  jz      short loc_180003910
0x1800038f1  mov     rcx, [rcx+38h]
0x1800038f5  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x1800038fc  mov     edx, 1Ah
0x180003901  mov     r9d, eax
0x180003904  call    WPP_SF_d
0x180003909  mov     rcx, cs:WPP_GLOBAL_Control
0x180003910  mov     ebx, 0C0000420h
0x180003915  jmp     loc_180003798
```
