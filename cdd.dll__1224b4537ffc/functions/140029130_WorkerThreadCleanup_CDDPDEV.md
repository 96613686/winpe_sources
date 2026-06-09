# WorkerThreadCleanup(CDDPDEV *)

- ea: `0x140029130`
- end: `0x14002924b`
- name: `?WorkerThreadCleanup@@YAXPEAUCDDPDEV@@@Z`
- size: `283`
- prototype: `void __fastcall(struct CDDPDEV *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140028a40`

## callees

- `0x140029130`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140029238`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029238`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029139`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029139`
- `ntoskrnl!KeSetEvent` at `0x140029214`
- `ntoskrnl!KeSetEvent` at `0x140029214`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140029164`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400291bb`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140029164`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400291bb`
- `watchdog!WdLogSingleEntry0` at `0x14002914e`
- `watchdog!WdLogSingleEntry0` at `0x1400291a5`
- `watchdog!WdLogSingleEntry0` at `0x14002914e`
- `watchdog!WdLogSingleEntry0` at `0x1400291a5`

## pseudocode

```c
void __fastcall WorkerThreadCleanup(struct CDDPDEV *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  struct _KEVENT *v8; // rcx

  if ( KeGetCurrentIrql() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4857;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 4857;
  }
  if ( *((_DWORD *)a1 + 1370) != 1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4859;
    v7 = (_QWORD *)WdLogNewEntry5_WdAssertion(v6, v5);
    v7[3] = gCddImageInfo;
    v7[4] = (unsigned int)dword_14003E570;
    v7[5] = 215857758;
    WdLogGlobalForLineNumber = 4859;
  }
  *((_DWORD *)a1 + 1370) = 0;
  v8 = (struct _KEVENT *)*((_QWORD *)a1 + 326);
  *((_QWORD *)a1 + 322) = KeGetCurrentThread();
  KeSetEvent(v8, 0, 0);
  KeWaitForSingleObject(*((PVOID *)a1 + 329), Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x140029130  push    rbx
0x140029132  sub     rsp, 30h
0x140029136  mov     rbx, rcx
0x140029139  call    cs:__imp_KeGetCurrentIrql
0x140029140  nop     dword ptr [rax+rax+00h]
0x140029145  test    al, al
0x140029147  jz      short loc_140029197
0x140029149  mov     ecx, 1
0x14002914e  call    cs:__imp_WdLogSingleEntry0
0x140029155  nop     dword ptr [rax+rax+00h]
0x14002915a  mov     cs:WdLogGlobalForLineNumber, 12F9h
0x140029164  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002916b  nop     dword ptr [rax+rax+00h]
0x140029170  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140029177  mov     [rax+18h], rdx
0x14002917b  mov     edx, cs:dword_14003E570
0x140029181  mov     [rax+20h], rdx
0x140029185  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002918d  mov     cs:WdLogGlobalForLineNumber, 12F9h
0x140029197  cmp     dword ptr [rbx+1568h], 1
0x14002919e  jz      short loc_1400291EE
0x1400291a0  mov     ecx, 1
0x1400291a5  call    cs:__imp_WdLogSingleEntry0
0x1400291ac  nop     dword ptr [rax+rax+00h]
0x1400291b1  mov     cs:WdLogGlobalForLineNumber, 12FBh
0x1400291bb  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400291c2  nop     dword ptr [rax+rax+00h]
0x1400291c7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400291ce  mov     [rax+18h], rcx
0x1400291d2  mov     ecx, cs:dword_14003E570
0x1400291d8  mov     [rax+20h], rcx
0x1400291dc  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400291e4  mov     cs:WdLogGlobalForLineNumber, 12FBh
0x1400291ee  mov     dword ptr [rbx+1568h], 0
0x1400291f8  xor     r8d, r8d; Wait
0x1400291fb  mov     rax, gs:188h
0x140029204  xor     edx, edx; Increment
0x140029206  mov     rcx, [rbx+0A30h]; Event
0x14002920d  mov     [rbx+0A10h], rax
0x140029214  call    cs:__imp_KeSetEvent
0x14002921b  nop     dword ptr [rax+rax+00h]
0x140029220  mov     rcx, [rbx+0A48h]; Object
0x140029227  xor     r9d, r9d; Alertable
0x14002922a  xor     r8d, r8d; WaitMode
0x14002922d  mov     [rsp+38h+Timeout], 0; Timeout
0x140029236  xor     edx, edx; WaitReason
0x140029238  call    cs:__imp_KeWaitForSingleObject
0x14002923f  nop     dword ptr [rax+rax+00h]
0x140029244  add     rsp, 30h
0x140029248  pop     rbx
0x140029249  retn
```
