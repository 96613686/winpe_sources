# LuafvUnload

- ea: `0x140016670`
- end: `0x14001682c`
- name: `LuafvUnload`
- size: `444`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400291a8`

## callees

- `0x1400049e0`
- `0x140016670`
- `0x140016834`
- `0x14001686c`
- `0x140016d08`
- `0x14001dd90`
- `0x14001fe20`
- `0x140024a8c`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140016681`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140016681`
- `ntoskrnl!DbgPrint` at `0x14001669f`
- `ntoskrnl!DbgPrint` at `0x14001669f`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400166bd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400166bd`
- `ntoskrnl!EtwUnregister` at `0x140016801`
- `ntoskrnl!EtwUnregister` at `0x140016801`
- `ntoskrnl!SeUnregisterLogonSessionTerminatedRoutineEx` at `0x1400166e0`
- `ntoskrnl!SeUnregisterLogonSessionTerminatedRoutineEx` at `0x1400166e0`
- `FLTMGR!FltUnregisterFilter` at `0x1400166ff`
- `FLTMGR!FltUnregisterFilter` at `0x1400166ff`

## pseudocode

```c
__int64 LuafvUnload()
{
  __int64 v0; // rcx
  __int64 v1; // rbx
  __int64 *v2; // rdi
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // rax
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp+10h] BYREF

  ExWaitForRundownProtectionRelease(&RunRef);
  while ( LuafvActiveDvfcbCount )
  {
    Interval.QuadPart = 0;
    DbgPrint("***\n*** LUAFV stalling unload due to delayed virtualization\n***\n");
    Interval.QuadPart = -300000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  LuafvTerminateScavenger();
  SeUnregisterLogonSessionTerminatedRoutineEx(UserLogoffCallback, 0);
  LOBYTE(v0) = 1;
  LuafvScavengeUserList(v0);
  if ( LuafvDriverData )
    FltUnregisterFilter(LuafvDriverData);
  if ( qword_14000E8C0 )
    LuafvFreePool(qword_14000E8C0);
  if ( Sid1 )
    LuafvFreePool((__int64)Sid1);
  Sid1 = 0;
  if ( qword_14000F2E0 )
  {
    LuafvFreePool(qword_14000F2E0);
    qword_14000F2E0 = 0;
  }
  if ( stru_14000F128.Buffer )
  {
    LuafvFreePool((__int64)stru_14000F128.Buffer);
    stru_14000F128.Buffer = 0;
  }
  if ( String1.Buffer )
  {
    LuafvFreePool((__int64)String1.Buffer);
    String1.Buffer = 0;
  }
  LuafvEnumerateFileTable((__int64)&PushLock, 0, 0, (void (__fastcall *)(__int64, __int64))ClearFileTablePostWorker, 2);
  v1 = 0;
  do
  {
    v2 = &SdTable[3 * v1];
    while ( 1 )
    {
      v5 = (_QWORD *)*v2;
      if ( (__int64 *)*v2 == v2 )
        break;
      v3 = *v5;
      if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v4 = (_QWORD *)v5[1], (_QWORD *)*v4 != v5) )
        __fastfail(3u);
      *v4 = v3;
      *(_QWORD *)(v3 + 8) = v4;
      LuafvFreePool((__int64)v5);
    }
    v1 = (unsigned int)(v1 + 1);
  }
  while ( (unsigned int)v1 < 0x10 );
  LuafvTerminatePool();
  if ( qword_14000F120 )
    EtwUnregister(qword_14000F120);
  TraceLoggingUnregister_EtwUnregister();
  wil_UninitializeFeatureStaging();
  return 0;
}

```

## disassembly

```asm
0x140016670  mov     [rsp+arg_0], rbx
0x140016675  push    rdi
0x140016676  sub     rsp, 30h
0x14001667a  lea     rcx, RunRef; RunRef
0x140016681  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140016688  nop     dword ptr [rax+rax+00h]
0x14001668d  jmp     short loc_1400166C9
0x14001668f  lea     rcx, Format; "***\n*** LUAFV stalling unload due to d"...
0x140016696  mov     qword ptr [rsp+38h+Interval], 0
0x14001669f  call    cs:__imp_DbgPrint
0x1400166a6  nop     dword ptr [rax+rax+00h]
0x1400166ab  lea     r8, [rsp+38h+Interval]; Interval
0x1400166b0  mov     qword ptr [rsp+38h+Interval], 0FFFFFFFFEE1E5D00h
0x1400166b9  xor     edx, edx; Alertable
0x1400166bb  xor     ecx, ecx; WaitMode
0x1400166bd  call    cs:__imp_KeDelayExecutionThread
0x1400166c4  nop     dword ptr [rax+rax+00h]
0x1400166c9  cmp     cs:LuafvActiveDvfcbCount, 0
0x1400166d0  jnz     short loc_14001668F
0x1400166d2  call    LuafvTerminateScavenger
0x1400166d7  xor     edx, edx
0x1400166d9  lea     rcx, UserLogoffCallback
0x1400166e0  call    cs:__imp_SeUnregisterLogonSessionTerminatedRoutineEx
0x1400166e7  nop     dword ptr [rax+rax+00h]
0x1400166ec  mov     cl, 1
0x1400166ee  call    LuafvScavengeUserList
0x1400166f3  mov     rcx, cs:LuafvDriverData; Filter
0x1400166fa  test    rcx, rcx
0x1400166fd  jz      short loc_14001670B
0x1400166ff  call    cs:__imp_FltUnregisterFilter
0x140016706  nop     dword ptr [rax+rax+00h]
0x14001670b  mov     rcx, cs:qword_14000E8C0
0x140016712  test    rcx, rcx
0x140016715  jz      short loc_14001671C
0x140016717  call    LuafvFreePool
0x14001671c  mov     rcx, cs:Sid1
0x140016723  test    rcx, rcx
0x140016726  jz      short loc_14001672D
0x140016728  call    LuafvFreePool
0x14001672d  mov     rcx, cs:qword_14000F2E0
0x140016734  mov     cs:Sid1, 0
0x14001673f  test    rcx, rcx
0x140016742  jz      short loc_140016754
0x140016744  call    LuafvFreePool
0x140016749  mov     cs:qword_14000F2E0, 0
0x140016754  mov     rcx, cs:stru_14000F128.Buffer
0x14001675b  test    rcx, rcx
0x14001675e  jz      short loc_140016770
0x140016760  call    LuafvFreePool
0x140016765  mov     cs:stru_14000F128.Buffer, 0
0x140016770  mov     rcx, cs:String1.Buffer
0x140016777  test    rcx, rcx
0x14001677a  jz      short loc_14001678C
0x14001677c  call    LuafvFreePool
0x140016781  mov     cs:String1.Buffer, 0
0x14001678c  lea     r9, ClearFileTablePostWorker
0x140016793  mov     [rsp+38h+var_18], 2
0x14001679c  xor     r8d, r8d
0x14001679f  lea     rcx, PushLock
0x1400167a6  xor     edx, edx
0x1400167a8  call    LuafvEnumerateFileTable
0x1400167ad  xor     ebx, ebx
0x1400167af  lea     rcx, [rbx+rbx*2]
0x1400167b3  lea     rax, SdTable
0x1400167ba  lea     rdi, [rax+rcx*8]
0x1400167be  jmp     short loc_1400167E1
0x1400167c0  mov     rcx, [rax]
0x1400167c3  cmp     [rcx+8], rax
0x1400167c7  jnz     short loc_140016825
0x1400167c9  mov     rdx, [rax+8]
0x1400167cd  cmp     [rdx], rax
0x1400167d0  jnz     short loc_140016825
0x1400167d2  mov     [rdx], rcx
0x1400167d5  mov     [rcx+8], rdx
0x1400167d9  mov     rcx, rax
0x1400167dc  call    LuafvFreePool
0x1400167e1  mov     rax, [rdi]
0x1400167e4  cmp     rax, rdi
0x1400167e7  jnz     short loc_1400167C0
0x1400167e9  inc     ebx
0x1400167eb  cmp     ebx, 10h
0x1400167ee  jb      short loc_1400167AF
0x1400167f0  call    LuafvTerminatePool
0x1400167f5  mov     rcx, cs:qword_14000F120; RegHandle
0x1400167fc  test    rcx, rcx
0x1400167ff  jz      short loc_14001680D
0x140016801  call    cs:__imp_EtwUnregister
0x140016808  nop     dword ptr [rax+rax+00h]
0x14001680d  call    TraceLoggingUnregister_EtwUnregister
0x140016812  call    wil_UninitializeFeatureStaging
0x140016817  mov     rbx, [rsp+38h+arg_0]
0x14001681c  xor     eax, eax
0x14001681e  add     rsp, 30h
0x140016822  pop     rdi
0x140016823  retn
0x140016825  mov     ecx, 3
0x14001682a  int     29h; Win8: RtlFailFast(ecx)
```
