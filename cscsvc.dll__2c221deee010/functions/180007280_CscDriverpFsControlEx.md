# CscDriverpFsControlEx

- ea: `0x180007280`
- end: `0x18000749c`
- name: `CscDriverpFsControlEx`
- size: `540`
- prototype: `__int64 __fastcall(HANDLE FileHandle, __int64, _DWORD *, void *, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `61`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800023f0`
- `0x180005030`
- `0x180005270`
- `0x1800053e0`
- `0x1800057f0`
- `0x1800060a0`
- `0x1800068b0`
- `0x180007230`
- `0x180007b40`
- `0x180008310`
- `0x18000a0d0`
- `0x18000adc0`
- `0x18000b5dc`
- `0x18000b740`
- `0x180027df0`
- `0x18002a560`
- `0x18002a6dc`
- `0x18002aa98`
- `0x18002c73c`
- `0x180031c58`
- `0x1800325f0`
- `0x1800333e4`
- `0x180033b24`
- `0x180034eb8`
- `0x18006c3bc`
- `0x18006c44c`
- `0x18006c6ec`
- `0x18006db00`
- `0x18006e144`
- `0x18006ebf8`
- `0x18006ed94`
- `0x18006eef4`
- `0x18006ef64`
- `0x18006f200`
- `0x18006f290`
- `0x18006f6e0`
- `0x18006f75c`
- `0x18006f8a8`
- `0x18006f914`
- `0x18006f9ec`
- `0x18006fb4c`
- `0x18006fc2c`
- `0x18006fd8c`
- `0x18006ff20`
- `0x18006ffb8`
- `0x1800700b0`
- `0x1800701b4`
- `0x1800702bc`
- `0x180070354`
- `0x180070458`

## callees

- `0x180007280`
- `0x180036394`
- `0x18003e928`
- `0x18007153c`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x1800072f4`
- `ntdll!NtCreateEvent` at `0x1800072f4`
- `ntdll!NtWaitForSingleObject` at `0x1800073d9`
- `ntdll!NtWaitForSingleObject` at `0x1800073d9`
- `ntdll!NtFsControlFile` at `0x180007337`
- `ntdll!NtFsControlFile` at `0x180007337`
- `ntdll!NtClose` at `0x180007366`
- `ntdll!NtClose` at `0x180007366`

## pseudocode

```c
__int64 __fastcall CscDriverpFsControlEx(
        HANDLE FileHandle,
        __int64 a2,
        _DWORD *a3,
        void *a4,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  NTSTATUS v10; // eax
  unsigned int Status; // ebx
  CObjectMonitor *v12; // rcx
  __int64 v14; // rdx
  void *EventHandle; // [rsp+50h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-60h] BYREF

  EventHandle = 0;
  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 68) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_qcqqDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      a2,
      a3,
      FileHandle,
      89,
      a3,
      a4,
      InputBufferLength,
      OutputBuffer,
      OutputBufferLength);
  }
  v10 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
  Status = v10;
  if ( v10 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 68) >= 0 )
      goto LABEL_7;
    v14 = 25;
LABEL_21:
    WPP_SF_d(*((_QWORD *)v12 + 7), v14, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, (unsigned int)v10);
    goto LABEL_6;
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
LABEL_5:
    *a3 = IoStatusBlock.Information;
LABEL_6:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v10 = NtWaitForSingleObject(EventHandle, 0, 0);
  Status = v10;
  if ( !v10 )
  {
    Status = IoStatusBlock.Status;
    goto LABEL_5;
  }
  if ( v10 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 68) >= 0 )
      goto LABEL_7;
    v14 = 27;
    goto LABEL_21;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 68) < 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      26,
      WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids,
      (unsigned int)v10);
    v12 = WPP_GLOBAL_Control;
  }
  Status = -1073740768;
LABEL_7:
  if ( EventHandle )
  {
    NtClose(EventHandle);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && *((char *)v12 + 68) < 0 && *((_BYTE *)v12 + 65) >= 4u )
    WPP_SF_dd(*((_QWORD *)v12 + 7), 28, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, (unsigned int)*a3, Status);
  return Status;
}

```

## disassembly

```asm
0x180007280  push    rbx
0x180007282  push    rbp
0x180007283  push    rsi
0x180007284  push    rdi
0x180007285  push    r12
0x180007287  push    r13
0x180007289  push    r14
0x18000728b  push    r15
0x18000728d  sub     rsp, 78h
0x180007291  xorps   xmm0, xmm0
0x180007294  mov     [rsp+0B8h+EventHandle], 0
0x18000729d  movups  xmmword ptr [rsp+0B8h+IoStatusBlock], xmm0
0x1800072a2  mov     rdi, r9
0x1800072a5  mov     r12, r8
0x1800072a8  mov     rsi, rcx
0x1800072ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072b2  lea     r13, WPP_GLOBAL_Control
0x1800072b9  mov     ebp, [rsp+0B8h+arg_30]
0x1800072c0  mov     r14, [rsp+0B8h+arg_28]
0x1800072c8  mov     r15d, [rsp+0B8h+arg_20]
0x1800072d0  cmp     rcx, r13
0x1800072d3  jz      short loc_1800072DF
0x1800072d5  test    byte ptr [rcx+44h], 80h
0x1800072d9  jnz     loc_1800073EE
0x1800072df  xor     r9d, r9d; EventType
0x1800072e2  mov     [rsp+0B8h+InitialState], 0; InitialState
0x1800072e7  xor     r8d, r8d; ObjectAttributes
0x1800072ea  lea     rcx, [rsp+0B8h+EventHandle]; EventHandle
0x1800072ef  mov     edx, 1F0003h; DesiredAccess
0x1800072f4  call    cs:__imp_NtCreateEvent
0x1800072fa  mov     ebx, eax
0x1800072fc  test    eax, eax
0x1800072fe  js      loc_1800073B6
0x180007304  mov     rdx, [rsp+0B8h+EventHandle]; Event
0x180007309  lea     rax, [rsp+0B8h+IoStatusBlock]
0x18000730e  mov     [rsp+0B8h+OutputBufferLength], ebp; OutputBufferLength
0x180007312  xor     r9d, r9d; ApcContext
0x180007315  mov     [rsp+0B8h+OutputBuffer], r14; OutputBuffer
0x18000731a  xor     r8d, r8d; ApcRoutine
0x18000731d  mov     [rsp+0B8h+InputBufferLength], r15d; InputBufferLength
0x180007322  mov     rcx, rsi; FileHandle
0x180007325  mov     [rsp+0B8h+InputBuffer], rdi; InputBuffer
0x18000732a  mov     [rsp+0B8h+FsControlCode], 901AFh; FsControlCode
0x180007332  mov     qword ptr [rsp+0B8h+InitialState], rax; IoStatusBlock
0x180007337  call    cs:__imp_NtFsControlFile
0x18000733d  mov     ebx, eax
0x18000733f  cmp     eax, 103h
0x180007344  jz      loc_1800073CF
0x18000734a  mov     eax, dword ptr [rsp+0B8h+IoStatusBlock.Information]
0x18000734e  mov     [r12], eax
0x180007352  mov     rcx, cs:WPP_GLOBAL_Control
0x180007359  mov     rax, [rsp+0B8h+EventHandle]
0x18000735e  test    rax, rax
0x180007361  jz      short loc_180007373
0x180007363  mov     rcx, rax; Handle
0x180007366  call    cs:__imp_NtClose
0x18000736c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007373  cmp     rcx, r13
0x180007376  jnz     short loc_18000738B
0x180007378  mov     eax, ebx
0x18000737a  add     rsp, 78h
0x18000737e  pop     r15
0x180007380  pop     r14
0x180007382  pop     r13
0x180007384  pop     r12
0x180007386  pop     rdi
0x180007387  pop     rsi
0x180007388  pop     rbp
0x180007389  pop     rbx
0x18000738a  retn
0x18000738b  test    byte ptr [rcx+44h], 80h
0x18000738f  jz      short loc_180007378
0x180007391  cmp     byte ptr [rcx+41h], 4
0x180007395  jb      short loc_180007378
0x180007397  mov     r9d, [r12]
0x18000739b  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x1800073a2  mov     rcx, [rcx+38h]
0x1800073a6  mov     edx, 1Ch
0x1800073ab  mov     dword ptr [rsp+0B8h+InitialState], ebx
0x1800073af  call    WPP_SF_dd
0x1800073b4  jmp     short loc_180007378
0x1800073b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073bd  cmp     rcx, r13
0x1800073c0  jz      short loc_180007359
0x1800073c2  test    byte ptr [rcx+44h], 80h
0x1800073c6  jz      short loc_180007359
0x1800073c8  mov     edx, 19h
0x1800073cd  jmp     short loc_18000742B
0x1800073cf  mov     rcx, [rsp+0B8h+EventHandle]; Handle
0x1800073d4  xor     r8d, r8d; Timeout
0x1800073d7  xor     edx, edx; Alertable
0x1800073d9  call    cs:__imp_NtWaitForSingleObject
0x1800073df  mov     ebx, eax
0x1800073e1  test    eax, eax
0x1800073e3  jnz     short loc_180007443
0x1800073e5  mov     ebx, dword ptr [rsp+0B8h+IoStatusBlock]
0x1800073e9  jmp     loc_18000734A
0x1800073ee  cmp     byte ptr [rcx+41h], 4
0x1800073f2  jb      loc_1800072DF
0x1800073f8  mov     rcx, [rcx+38h]
0x1800073fc  mov     r9, rsi
0x1800073ff  mov     [rsp+0B8h+OutputBufferLength], ebp
0x180007403  mov     [rsp+0B8h+OutputBuffer], r14
0x180007408  mov     [rsp+0B8h+InputBufferLength], r15d
0x18000740d  mov     [rsp+0B8h+InputBuffer], rdi
0x180007412  mov     qword ptr [rsp+0B8h+FsControlCode], r12
0x180007417  mov     [rsp+0B8h+InitialState], 59h ; 'Y'
0x18000741c  call    WPP_SF_qcqqDqD
0x180007421  jmp     loc_1800072DF
0x180007426  mov     edx, 1Bh
0x18000742b  mov     rcx, [rcx+38h]
0x18000742f  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x180007436  mov     r9d, eax
0x180007439  call    WPP_SF_d
0x18000743e  jmp     loc_180007352
0x180007443  js      short loc_180007480
0x180007445  mov     rcx, cs:WPP_GLOBAL_Control
0x18000744c  cmp     rcx, r13
0x18000744f  jz      short loc_180007476
0x180007451  test    byte ptr [rcx+44h], 80h
0x180007455  jz      short loc_180007476
0x180007457  mov     rcx, [rcx+38h]
0x18000745b  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x180007462  mov     edx, 1Ah
0x180007467  mov     r9d, eax
0x18000746a  call    WPP_SF_d
0x18000746f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007476  mov     ebx, 0C0000420h
0x18000747b  jmp     loc_180007359
0x180007480  mov     rcx, cs:WPP_GLOBAL_Control
0x180007487  cmp     rcx, r13
0x18000748a  jz      loc_180007359
0x180007490  test    byte ptr [rcx+44h], 80h
0x180007494  jz      loc_180007359
0x18000749a  jmp     short loc_180007426
```
