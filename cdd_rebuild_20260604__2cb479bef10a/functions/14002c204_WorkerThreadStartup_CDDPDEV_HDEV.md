# WorkerThreadStartup(CDDPDEV *,HDEV__ *)

- ea: `0x14002c204`
- end: `0x14002c506`
- name: `?WorkerThreadStartup@@YAHPEAUCDDPDEV@@PEAUHDEV__@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(PVOID StartContext, HDEV)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001d980`

## callees

- `0x14002c204`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c364`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c364`
- `ntoskrnl!PsCreateSystemThread` at `0x14002c421`
- `ntoskrnl!PsCreateSystemThread` at `0x14002c421`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c44c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c44c`
- `ntoskrnl!ZwClose` at `0x14002c45c`
- `ntoskrnl!ZwClose` at `0x14002c4db`
- `ntoskrnl!ZwClose` at `0x14002c45c`
- `ntoskrnl!ZwClose` at `0x14002c4db`
- `ntoskrnl!KeClearEvent` at `0x14002c2f7`
- `ntoskrnl!KeClearEvent` at `0x14002c30a`
- `ntoskrnl!KeClearEvent` at `0x14002c2f7`
- `ntoskrnl!KeClearEvent` at `0x14002c30a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c23d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c23d`
- `watchdog!WdLogSingleEntry5` at `0x14002c39d`
- `watchdog!WdLogSingleEntry5` at `0x14002c492`
- `watchdog!WdLogSingleEntry5` at `0x14002c39d`
- `watchdog!WdLogSingleEntry5` at `0x14002c492`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002c3b4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002c4a8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002c3b4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002c4a8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c26e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c2c1`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c26e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c2c1`
- `watchdog!WdLogSingleEntry0` at `0x14002c258`
- `watchdog!WdLogSingleEntry0` at `0x14002c2ab`
- `watchdog!WdLogSingleEntry0` at `0x14002c258`
- `watchdog!WdLogSingleEntry0` at `0x14002c2ab`

## pseudocode

```c
_BOOL8 __fastcall WorkerThreadStartup(PRKEVENT *StartContext, HDEV a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  PRKEVENT v5; // rcx
  NTSTATUS v6; // eax
  _QWORD *v7; // rax
  _BOOL8 result; // rax
  HANDLE v9; // r9
  NTSTATUS v10; // eax
  _QWORD *v11; // rax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+10h] BYREF
  HANDLE ProcessHandle; // [rsp+88h] [rbp+18h] BYREF

  ProcessHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ThreadHandle = 0;
  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4668;
    v3 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 4668;
  }
  if ( *((_DWORD *)StartContext + 1370) == 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4672;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 4672;
  }
  KeClearEvent(StartContext[326]);
  KeClearEvent(StartContext[329]);
  v5 = StartContext[94];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ObOpenObjectByPointer(v5, 0x200u, 0, 2u, 0, 0, &ProcessHandle);
  if ( v6 >= 0 )
  {
    v9 = ProcessHandle;
    StartContext[322] = (PRKEVENT)KeGetCurrentThread();
    v10 = PsCreateSystemThread(
            &ThreadHandle,
            0x1FFFFFu,
            &ObjectAttributes,
            v9,
            0,
            (PKSTART_ROUTINE)PresentWorkerThread,
            StartContext);
    if ( v10 < 0 )
    {
      WdLogSingleEntry5(
        2,
        StartContext,
        v10,
        *((unsigned int *)StartContext + 196),
        *((unsigned int *)StartContext + 199),
        *((unsigned int *)StartContext + 200));
      WdLogGlobalForLineNumber = 4729;
      v11 = (_QWORD *)WdLogNewEntry5_WdError();
      v11[3] = gCddImageInfo;
      v11[4] = (unsigned int)dword_14003E570;
      v11[5] = 215857758;
      WdLogGlobalForLineNumber = 4729;
    }
    else
    {
      KeWaitForSingleObject(StartContext[329], Executive, 0, 0, 0);
      ZwClose(ThreadHandle);
    }
    ZwClose(ProcessHandle);
    return *((_DWORD *)StartContext + 1370) == 1;
  }
  else
  {
    WdLogSingleEntry5(
      2,
      StartContext,
      v6,
      *((unsigned int *)StartContext + 196),
      *((unsigned int *)StartContext + 199),
      *((unsigned int *)StartContext + 200));
    WdLogGlobalForLineNumber = 4699;
    v7 = (_QWORD *)WdLogNewEntry5_WdError();
    v7[3] = gCddImageInfo;
    v7[4] = (unsigned int)dword_14003E570;
    v7[5] = 215857758;
    result = 0;
    WdLogGlobalForLineNumber = 4699;
  }
  return result;
}

```

## disassembly

```asm
0x14002c204  mov     [rsp-8+arg_10], rbx
0x14002c209  mov     [rsp-8+arg_18], r15
0x14002c20e  mov     [rsp-8+ProcessHandle], rdx
0x14002c213  push    rbp
0x14002c214  mov     rbp, rsp
0x14002c217  sub     rsp, 70h
0x14002c21b  xorps   xmm0, xmm0
0x14002c21e  mov     [rbp+ProcessHandle], 0
0x14002c226  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14002c22a  mov     rbx, rcx
0x14002c22d  mov     [rbp+ThreadHandle], 0
0x14002c235  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002c239  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c23d  call    cs:__imp_KeGetCurrentIrql
0x14002c244  nop     dword ptr [rax+rax+00h]
0x14002c249  mov     r15d, 0CDDBA5Eh
0x14002c24f  test    al, al
0x14002c251  jz      short loc_14002C29D
0x14002c253  mov     ecx, 1
0x14002c258  call    cs:__imp_WdLogSingleEntry0
0x14002c25f  nop     dword ptr [rax+rax+00h]
0x14002c264  mov     cs:WdLogGlobalForLineNumber, 123Ch
0x14002c26e  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002c275  nop     dword ptr [rax+rax+00h]
0x14002c27a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A
0x14002c281  mov     [rax+18h], rcx
0x14002c285  mov     ecx, cs:dword_14003E570
0x14002c28b  mov     [rax+20h], rcx
0x14002c28f  mov     [rax+28h], r15
0x14002c293  mov     cs:WdLogGlobalForLineNumber, 123Ch
0x14002c29d  cmp     dword ptr [rbx+1568h], 1
0x14002c2a4  jnz     short loc_14002C2F0
0x14002c2a6  mov     ecx, 1
0x14002c2ab  call    cs:__imp_WdLogSingleEntry0
0x14002c2b2  nop     dword ptr [rax+rax+00h]
0x14002c2b7  mov     cs:WdLogGlobalForLineNumber, 1240h
0x14002c2c1  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002c2c8  nop     dword ptr [rax+rax+00h]
0x14002c2cd  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A
0x14002c2d4  mov     [rax+18h], rcx
0x14002c2d8  mov     ecx, cs:dword_14003E570
0x14002c2de  mov     [rax+20h], rcx
0x14002c2e2  mov     [rax+28h], r15
0x14002c2e6  mov     cs:WdLogGlobalForLineNumber, 1240h
0x14002c2f0  mov     rcx, [rbx+0A30h]; Event
0x14002c2f7  call    cs:__imp_KeClearEvent
0x14002c2fe  nop     dword ptr [rax+rax+00h]
0x14002c303  mov     rcx, [rbx+0A48h]; Event
0x14002c30a  call    cs:__imp_KeClearEvent
0x14002c311  nop     dword ptr [rax+rax+00h]
0x14002c316  mov     rcx, [rbx+2F0h]; Object
0x14002c31d  lea     rax, [rbp+ProcessHandle]
0x14002c321  mov     [rsp+70h+Handle], rax; Handle
0x14002c326  mov     edx, 200h; HandleAttributes
0x14002c32b  xorps   xmm0, xmm0
0x14002c32e  mov     [rsp+70h+AccessMode], 0; AccessMode
0x14002c333  mov     r9d, 2; DesiredAccess
0x14002c339  mov     [rsp+70h+ObjectType], 0; ObjectType
0x14002c342  xor     r8d, r8d; PassedAccessState
0x14002c345  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14002c34c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14002c354  mov     [rbp+ObjectAttributes.Attributes], edx
0x14002c357  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14002c35f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c364  call    cs:__imp_ObOpenObjectByPointer
0x14002c36b  nop     dword ptr [rax+rax+00h]
0x14002c370  test    eax, eax
0x14002c372  jns     short loc_14002C3E6
0x14002c374  mov     edx, [rbx+320h]
0x14002c37a  mov     ecx, 2
0x14002c37f  mov     r10d, [rbx+31Ch]
0x14002c386  mov     r9d, [rbx+310h]
0x14002c38d  mov     qword ptr [rsp+70h+AccessMode], rdx
0x14002c392  mov     rdx, rbx
0x14002c395  movsxd  r8, eax
0x14002c398  mov     [rsp+70h+ObjectType], r10
0x14002c39d  call    cs:__imp_WdLogSingleEntry5
0x14002c3a4  nop     dword ptr [rax+rax+00h]
0x14002c3a9  mov     ebx, 125Bh
0x14002c3ae  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002c3b4  call    cs:__imp_WdLogNewEntry5_WdError
0x14002c3bb  nop     dword ptr [rax+rax+00h]
0x14002c3c0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A
0x14002c3c7  mov     [rax+18h], rcx
0x14002c3cb  mov     ecx, cs:dword_14003E570
0x14002c3d1  mov     [rax+20h], rcx
0x14002c3d5  mov     [rax+28h], r15
0x14002c3d9  xor     eax, eax
0x14002c3db  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002c3e1  jmp     loc_14002C4F3
0x14002c3e6  mov     rax, gs:188h
0x14002c3ef  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14002c3f3  mov     r9, [rbp+ProcessHandle]; ProcessHandle
0x14002c3f7  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x14002c3fb  mov     [rbx+0A10h], rax
0x14002c402  mov     edx, 1FFFFFh; DesiredAccess
0x14002c407  lea     rax, ?PresentWorkerThread@@YAXPEAUCDDPDEV@@@Z
0x14002c40e  mov     [rsp+70h+Handle], rbx; StartContext
0x14002c413  mov     qword ptr [rsp+70h+AccessMode], rax; StartRoutine
0x14002c418  mov     [rsp+70h+ObjectType], 0; ClientId
0x14002c421  call    cs:__imp_PsCreateSystemThread
0x14002c428  nop     dword ptr [rax+rax+00h]
0x14002c42d  movsxd  rdx, eax
0x14002c430  test    eax, eax
0x14002c432  js      short loc_14002C46A
0x14002c434  mov     rcx, [rbx+0A48h]; Object
0x14002c43b  xor     r9d, r9d; Alertable
0x14002c43e  xor     r8d, r8d; WaitMode
0x14002c441  mov     [rsp+70h+ObjectType], 0; Timeout
0x14002c44a  xor     edx, edx; WaitReason
0x14002c44c  call    cs:__imp_KeWaitForSingleObject
0x14002c453  nop     dword ptr [rax+rax+00h]
0x14002c458  mov     rcx, [rbp+ThreadHandle]; Handle
0x14002c45c  call    cs:__imp_ZwClose
0x14002c463  nop     dword ptr [rax+rax+00h]
0x14002c468  jmp     short loc_14002C4D7
0x14002c46a  mov     ecx, [rbx+31Ch]
0x14002c470  mov     r8, rdx
0x14002c473  mov     eax, [rbx+320h]
0x14002c479  mov     rdx, rbx
0x14002c47c  mov     r9d, [rbx+310h]
0x14002c483  mov     qword ptr [rsp+70h+AccessMode], rax
0x14002c488  mov     [rsp+70h+ObjectType], rcx
0x14002c48d  mov     ecx, 2
0x14002c492  call    cs:__imp_WdLogSingleEntry5
0x14002c499  nop     dword ptr [rax+rax+00h]
0x14002c49e  mov     cs:WdLogGlobalForLineNumber, 1279h
0x14002c4a8  call    cs:__imp_WdLogNewEntry5_WdError
0x14002c4af  nop     dword ptr [rax+rax+00h]
0x14002c4b4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A
0x14002c4bb  mov     [rax+18h], rcx
0x14002c4bf  mov     ecx, cs:dword_14003E570
0x14002c4c5  mov     [rax+20h], rcx
0x14002c4c9  mov     [rax+28h], r15
0x14002c4cd  mov     cs:WdLogGlobalForLineNumber, 1279h
0x14002c4d7  mov     rcx, [rbp+ProcessHandle]; Handle
0x14002c4db  call    cs:__imp_ZwClose
0x14002c4e2  nop     dword ptr [rax+rax+00h]
0x14002c4e7  xor     eax, eax
0x14002c4e9  cmp     dword ptr [rbx+1568h], 1
0x14002c4f0  setz    al
0x14002c4f3  lea     r11, [rsp+70h+var_s0]
0x14002c4f8  mov     rbx, [r11+20h]
0x14002c4fc  mov     r15, [r11+28h]
0x14002c500  mov     rsp, r11
0x14002c503  pop     rbp
0x14002c504  retn
```
