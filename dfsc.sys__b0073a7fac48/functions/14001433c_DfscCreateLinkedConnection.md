# DfscCreateLinkedConnection

- ea: `0x14001433c`
- end: `0x140014511`
- name: `DfscCreateLinkedConnection`
- size: `469`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140029160`

## callees

- `0x14001433c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400144df`
- `ntoskrnl!ZwClose` at `0x1400144f5`
- `ntoskrnl!ZwClose` at `0x1400144df`
- `ntoskrnl!ZwClose` at `0x1400144f5`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400143b2`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400143b2`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400143db`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400143db`
- `ntoskrnl!PsCreateSystemThread` at `0x140014488`
- `ntoskrnl!PsCreateSystemThread` at `0x140014488`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400144af`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400144af`
- `ntoskrnl!KeInitializeEvent` at `0x140014452`
- `ntoskrnl!KeInitializeEvent` at `0x140014452`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400143f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400143f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144c9`
- `ntoskrnl!ExAllocatePool2` at `0x140014375`
- `ntoskrnl!ExAllocatePool2` at `0x140014375`

## pseudocode

```c
__int64 __fastcall DfscCreateLinkedConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8)
{
  _DWORD *StartContext; // rbx
  NTSTATUS v14; // edi
  HANDLE Handle; // [rsp+40h] [rbp-48h] BYREF
  void *ThreadHandle; // [rsp+48h] [rbp-40h] BYREF

  Handle = 0;
  ThreadHandle = 0;
  StartContext = (_DWORD *)ExAllocatePool2(66, 104, 1279485508);
  if ( !StartContext )
    return 3221225626LL;
  v14 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, 0x200u, &Handle);
  if ( v14 == -1073741700 )
    v14 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &Handle);
  if ( v14 >= 0 )
  {
    *((_QWORD *)StartContext + 5) = a2;
    *(_QWORD *)StartContext = &Handle;
    *((_QWORD *)StartContext + 8) = a5;
    *((_QWORD *)StartContext + 9) = a6;
    StartContext[20] = a7;
    StartContext[24] = a8;
    *((_QWORD *)StartContext + 6) = a3;
    *((_QWORD *)StartContext + 7) = a4;
    *((_QWORD *)StartContext + 11) = a1;
    KeInitializeEvent((PRKEVENT)(StartContext + 2), SynchronizationEvent, 0);
    v14 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, DfscCreateLinkedConnectionWorker, StartContext);
    if ( v14 >= 0 )
    {
      v14 = KeWaitForSingleObject(StartContext + 2, Executive, 0, 0, 0);
      if ( v14 >= 0 )
        v14 = StartContext[8];
    }
    ExFreePoolWithTag(StartContext, 0);
    if ( Handle )
      ZwClose(Handle);
    if ( ThreadHandle )
      ZwClose(ThreadHandle);
  }
  else
  {
    ExFreePoolWithTag(StartContext, 0);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14001433c  push    rbx
0x14001433e  push    rbp
0x14001433f  push    rsi
0x140014340  push    rdi
0x140014341  push    r14
0x140014343  push    r15
0x140014345  sub     rsp, 58h
0x140014349  mov     r14, rdx
0x14001434c  mov     [rsp+88h+Handle], 0
0x140014355  mov     edx, 68h ; 'h'
0x14001435a  mov     [rsp+88h+ThreadHandle], 0
0x140014363  mov     rbp, r8
0x140014366  mov     r15, rcx
0x140014369  mov     r8d, 4C436644h
0x14001436f  mov     rsi, r9
0x140014372  lea     ecx, [rdx-26h]
0x140014375  call    cs:__imp_ExAllocatePool2
0x14001437c  nop     dword ptr [rax+rax+00h]
0x140014381  mov     rbx, rax
0x140014384  test    rax, rax
0x140014387  jnz     short loc_140014393
0x140014389  mov     eax, 0C000009Ah
0x14001438e  jmp     loc_140014503
0x140014393  lea     rax, [rsp+88h+Handle]
0x140014398  mov     r9d, 200h; HandleAttributes
0x14001439e  mov     r8b, 1; OpenAsSelf
0x1400143a1  mov     [rsp+88h+TokenHandle], rax; TokenHandle
0x1400143a6  mov     edx, 8; DesiredAccess
0x1400143ab  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400143b2  call    cs:__imp_ZwOpenThreadTokenEx
0x1400143b9  nop     dword ptr [rax+rax+00h]
0x1400143be  mov     edi, eax
0x1400143c0  cmp     eax, 0C000007Ch
0x1400143c5  jnz     short loc_1400143E9
0x1400143c7  lea     r9, [rsp+88h+Handle]; TokenHandle
0x1400143cc  mov     edx, 8; DesiredAccess
0x1400143d1  mov     r8d, 200h; HandleAttributes
0x1400143d7  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400143db  call    cs:__imp_ZwOpenProcessTokenEx
0x1400143e2  nop     dword ptr [rax+rax+00h]
0x1400143e7  mov     edi, eax
0x1400143e9  test    edi, edi
0x1400143eb  jns     short loc_140014403
0x1400143ed  xor     edx, edx; Tag
0x1400143ef  mov     rcx, rbx; P
0x1400143f2  call    cs:__imp_ExFreePoolWithTag
0x1400143f9  nop     dword ptr [rax+rax+00h]
0x1400143fe  jmp     loc_140014501
0x140014403  lea     rax, [rsp+88h+Handle]
0x140014408  mov     [rbx+28h], r14
0x14001440c  mov     [rbx], rax
0x14001440f  lea     rcx, [rbx+8]; Event
0x140014413  mov     rax, [rsp+88h+arg_20]
0x14001441b  xor     r8d, r8d; State
0x14001441e  mov     [rbx+40h], rax
0x140014422  mov     rax, [rsp+88h+arg_28]
0x14001442a  mov     [rbx+48h], rax
0x14001442e  mov     eax, [rsp+88h+arg_30]
0x140014435  lea     edx, [r8+1]; Type
0x140014439  mov     [rbx+50h], eax
0x14001443c  mov     eax, [rsp+88h+arg_38]
0x140014443  mov     [rbx+60h], eax
0x140014446  mov     [rbx+30h], rbp
0x14001444a  mov     [rbx+38h], rsi
0x14001444e  mov     [rbx+58h], r15
0x140014452  call    cs:__imp_KeInitializeEvent
0x140014459  nop     dword ptr [rax+rax+00h]
0x14001445e  lea     rax, DfscCreateLinkedConnectionWorker
0x140014465  mov     [rsp+88h+StartContext], rbx; StartContext
0x14001446a  mov     [rsp+88h+StartRoutine], rax; StartRoutine
0x14001446f  lea     rcx, [rsp+88h+ThreadHandle]; ThreadHandle
0x140014474  xor     r9d, r9d; ProcessHandle
0x140014477  mov     [rsp+88h+TokenHandle], 0; ClientId
0x140014480  xor     r8d, r8d; ObjectAttributes
0x140014483  mov     edx, 1FFFFFh; DesiredAccess
0x140014488  call    cs:__imp_PsCreateSystemThread
0x14001448f  nop     dword ptr [rax+rax+00h]
0x140014494  mov     edi, eax
0x140014496  test    eax, eax
0x140014498  js      short loc_1400144C4
0x14001449a  xor     r9d, r9d; Alertable
0x14001449d  mov     [rsp+88h+TokenHandle], 0; Timeout
0x1400144a6  xor     r8d, r8d; WaitMode
0x1400144a9  lea     rcx, [rbx+8]; Object
0x1400144ad  xor     edx, edx; WaitReason
0x1400144af  call    cs:__imp_KeWaitForSingleObject
0x1400144b6  nop     dword ptr [rax+rax+00h]
0x1400144bb  mov     edi, eax
0x1400144bd  test    eax, eax
0x1400144bf  js      short loc_1400144C4
0x1400144c1  mov     edi, [rbx+20h]
0x1400144c4  xor     edx, edx; Tag
0x1400144c6  mov     rcx, rbx; P
0x1400144c9  call    cs:__imp_ExFreePoolWithTag
0x1400144d0  nop     dword ptr [rax+rax+00h]
0x1400144d5  mov     rcx, [rsp+88h+Handle]; Handle
0x1400144da  test    rcx, rcx
0x1400144dd  jz      short loc_1400144EB
0x1400144df  call    cs:__imp_ZwClose
0x1400144e6  nop     dword ptr [rax+rax+00h]
0x1400144eb  mov     rcx, [rsp+88h+ThreadHandle]; Handle
0x1400144f0  test    rcx, rcx
0x1400144f3  jz      short loc_140014501
0x1400144f5  call    cs:__imp_ZwClose
0x1400144fc  nop     dword ptr [rax+rax+00h]
0x140014501  mov     eax, edi
0x140014503  add     rsp, 58h
0x140014507  pop     r15
0x140014509  pop     r14
0x14001450b  pop     rdi
0x14001450c  pop     rsi
0x14001450d  pop     rbp
0x14001450e  pop     rbx
0x14001450f  retn
```
