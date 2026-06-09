# CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)

- ea: `0x14000fbb4`
- end: `0x14000fdaa`
- name: `?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400015e0`
- `0x140003840`
- `0x14000919c`
- `0x14000e690`
- `0x14000e710`
- `0x14000e790`
- `0x14000e880`
- `0x14000ef80`
- `0x14000f370`
- `0x140018a80`
- `0x14001b6e8`
- `0x14001f270`
- `0x1400226b0`
- `0x140027c80`
- `0x140028a40`
- `0x14002b5f0`
- `0x140032000`
- `0x140033134`
- `0x1400332b0`
- `0x14003461c`

## callees

- `0x14000fbb4`
- `0x140010670`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000fc57`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fc57`
- `ntoskrnl!KeClearEvent` at `0x14000fc6a`
- `ntoskrnl!KeClearEvent` at `0x14000fc6a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000fbc9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000fbc9`
- `ntoskrnl!KeSetEvent` at `0x14000fc33`
- `ntoskrnl!KeSetEvent` at `0x14000fc33`
- `ntoskrnl!DbgPrint` at `0x14000fd4e`
- `ntoskrnl!DbgPrint` at `0x14000fd4e`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000fd37`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000fd75`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000fd75`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fcb4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fd03`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fcb4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000fd03`
- `watchdog!WdLogSingleEntry0` at `0x14000fc9e`
- `watchdog!WdLogSingleEntry0` at `0x14000fced`
- `watchdog!WdLogSingleEntry0` at `0x14000fd5f`
- `watchdog!WdLogSingleEntry0` at `0x14000fc9e`
- `watchdog!WdLogSingleEntry0` at `0x14000fced`
- `watchdog!WdLogSingleEntry0` at `0x14000fd5f`

## string_xrefs

- `0x14000fd47`: `CddIssueCommand: worker thread submission mutex is not held\n`

## pseudocode

```c
__int64 __fastcall CddIssueCommand(__int64 a1, int a2)
{
  __int64 result; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax

  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2021;
    v5 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v5[3] = gCddImageInfo;
    v5[4] = (unsigned int)dword_14003E570;
    v5[5] = 215857758;
    WdLogGlobalForLineNumber = 2021;
  }
  if ( (a2 & 0xFFFFFFEF) == 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2022;
    v6 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 2022;
  }
  if ( *(struct _KTHREAD **)(*(_QWORD *)(a1 + 5488) + 8LL) != KeGetCurrentThread() && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("CddIssueCommand: worker thread submission mutex is not held\n");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 2025;
    v7 = (_QWORD *)WdLogNewEntry5_WdError();
    v7[3] = gCddImageInfo;
    v7[4] = (unsigned int)dword_14003E570;
    v7[5] = 215857758;
    WdLogGlobalForLineNumber = 2025;
    __debugbreak();
  }
  *(_QWORD *)(a1 + 2576) = KeGetCurrentThread();
  *(_DWORD *)(a1 + 3600) = a2;
  GetConnectedStandbyProcessName((struct CDDPDEV *)a1);
  KeSetEvent(*(PRKEVENT *)(a1 + 2608), 0, 0);
  KeWaitForSingleObject(*(PVOID *)(a1 + 2632), Executive, 0, 0, 0);
  KeClearEvent(*(PRKEVENT *)(a1 + 2608));
  result = *(unsigned int *)(a1 + 3608);
  *(_QWORD *)(a1 + 2576) = 0;
  return result;
}

```

## disassembly

```asm
0x14000fbb4  mov     [rsp+arg_0], rbx
0x14000fbb9  mov     [rsp+arg_8], rdi
0x14000fbbe  push    r14
0x14000fbc0  sub     rsp, 30h
0x14000fbc4  mov     edi, edx
0x14000fbc6  mov     rbx, rcx
0x14000fbc9  call    cs:__imp_KeGetCurrentIrql
0x14000fbd0  nop     dword ptr [rax+rax+00h]
0x14000fbd5  mov     r14d, 0CDDBA5Eh
0x14000fbdb  test    al, al
0x14000fbdd  jnz     loc_14000FC99
0x14000fbe3  test    edi, 0FFFFFFEFh
0x14000fbe9  jz      loc_14000FCE8
0x14000fbef  mov     rcx, gs:188h
0x14000fbf8  mov     rax, [rbx+1570h]
0x14000fbff  cmp     [rax+8], rcx
0x14000fc03  jnz     loc_14000FD37
0x14000fc09  mov     rax, gs:188h
0x14000fc12  mov     rcx, rbx; struct CDDPDEV *
0x14000fc15  mov     [rbx+0A10h], rax
0x14000fc1c  mov     [rbx+0E10h], edi
0x14000fc22  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x14000fc27  mov     rcx, [rbx+0A30h]; Event
0x14000fc2e  xor     r8d, r8d; Wait
0x14000fc31  xor     edx, edx; Increment
0x14000fc33  call    cs:__imp_KeSetEvent
0x14000fc3a  nop     dword ptr [rax+rax+00h]
0x14000fc3f  mov     rcx, [rbx+0A48h]; Object
0x14000fc46  xor     r9d, r9d; Alertable
0x14000fc49  xor     r8d, r8d; WaitMode
0x14000fc4c  mov     [rsp+38h+Timeout], 0; Timeout
0x14000fc55  xor     edx, edx; WaitReason
0x14000fc57  call    cs:__imp_KeWaitForSingleObject
0x14000fc5e  nop     dword ptr [rax+rax+00h]
0x14000fc63  mov     rcx, [rbx+0A30h]; Event
0x14000fc6a  call    cs:__imp_KeClearEvent
0x14000fc71  nop     dword ptr [rax+rax+00h]
0x14000fc76  mov     eax, [rbx+0E18h]
0x14000fc7c  mov     rdi, [rsp+38h+arg_8]
0x14000fc81  mov     qword ptr [rbx+0A10h], 0
0x14000fc8c  mov     rbx, [rsp+38h+arg_0]
0x14000fc91  add     rsp, 30h
0x14000fc95  pop     r14
0x14000fc97  retn
0x14000fc99  mov     ecx, 1
0x14000fc9e  call    cs:__imp_WdLogSingleEntry0
0x14000fca5  nop     dword ptr [rax+rax+00h]
0x14000fcaa  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x14000fcb4  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000fcbb  nop     dword ptr [rax+rax+00h]
0x14000fcc0  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000fcc7  mov     [rax+18h], rdx
0x14000fccb  mov     edx, cs:dword_14003E570
0x14000fcd1  mov     [rax+20h], rdx
0x14000fcd5  mov     [rax+28h], r14
0x14000fcd9  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x14000fce3  jmp     loc_14000FBE3
0x14000fce8  mov     ecx, 1
0x14000fced  call    cs:__imp_WdLogSingleEntry0
0x14000fcf4  nop     dword ptr [rax+rax+00h]
0x14000fcf9  mov     cs:WdLogGlobalForLineNumber, 7E6h
0x14000fd03  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000fd0a  nop     dword ptr [rax+rax+00h]
0x14000fd0f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000fd16  mov     [rax+18h], rcx
0x14000fd1a  mov     ecx, cs:dword_14003E570
0x14000fd20  mov     [rax+20h], rcx
0x14000fd24  mov     [rax+28h], r14
0x14000fd28  mov     cs:WdLogGlobalForLineNumber, 7E6h
0x14000fd32  jmp     loc_14000FBEF
0x14000fd37  mov     rax, cs:KdDebuggerEnabled
0x14000fd3e  cmp     byte ptr [rax], 0
0x14000fd41  jz      loc_14000FC09
0x14000fd47  lea     rcx, aCddissuecomman; "CddIssueCommand: worker thread submissi"...
0x14000fd4e  call    cs:__imp_DbgPrint
0x14000fd55  nop     dword ptr [rax+rax+00h]
0x14000fd5a  mov     ecx, 2
0x14000fd5f  call    cs:__imp_WdLogSingleEntry0
0x14000fd66  nop     dword ptr [rax+rax+00h]
0x14000fd6b  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x14000fd75  call    cs:__imp_WdLogNewEntry5_WdError
0x14000fd7c  nop     dword ptr [rax+rax+00h]
0x14000fd81  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000fd88  mov     [rax+18h], rcx
0x14000fd8c  mov     ecx, cs:dword_14003E570
0x14000fd92  mov     [rax+20h], rcx
0x14000fd96  mov     [rax+28h], r14
0x14000fd9a  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x14000fda4  int     3; Trap to Debugger
0x14000fda5  jmp     loc_14000FC09
```
