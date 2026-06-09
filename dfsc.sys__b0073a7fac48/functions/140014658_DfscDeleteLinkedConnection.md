# DfscDeleteLinkedConnection

- ea: `0x140014658`
- end: `0x140014800`
- name: `DfscDeleteLinkedConnection`
- size: `424`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140028004`

## callees

- `0x140014658`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400147ce`
- `ntoskrnl!ZwClose` at `0x1400147e4`
- `ntoskrnl!ZwClose` at `0x1400147ce`
- `ntoskrnl!ZwClose` at `0x1400147e4`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400146ce`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400146ce`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400146f7`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400146f7`
- `ntoskrnl!PsCreateSystemThread` at `0x140014777`
- `ntoskrnl!PsCreateSystemThread` at `0x140014777`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001479e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001479e`
- `ntoskrnl!KeInitializeEvent` at `0x140014741`
- `ntoskrnl!KeInitializeEvent` at `0x140014741`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001470e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001470e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147b8`
- `ntoskrnl!ExAllocatePool2` at `0x140014691`
- `ntoskrnl!ExAllocatePool2` at `0x140014691`

## pseudocode

```c
__int64 __fastcall DfscDeleteLinkedConnection(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _DWORD *StartContext; // rbx
  NTSTATUS v10; // edi
  HANDLE Handle; // [rsp+40h] [rbp-48h] BYREF
  void *ThreadHandle; // [rsp+48h] [rbp-40h] BYREF

  Handle = 0;
  ThreadHandle = 0;
  StartContext = (_DWORD *)ExAllocatePool2(66, 72, 1279485508);
  if ( !StartContext )
    return 3221225626LL;
  v10 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, 0x200u, &Handle);
  if ( v10 == -1073741700 )
    v10 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &Handle);
  if ( v10 >= 0 )
  {
    *((_QWORD *)StartContext + 5) = a3;
    *((_QWORD *)StartContext + 6) = a2;
    *(_QWORD *)StartContext = &Handle;
    StartContext[14] = a4;
    *((_QWORD *)StartContext + 8) = a1;
    KeInitializeEvent((PRKEVENT)(StartContext + 2), SynchronizationEvent, 0);
    v10 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, DfscDeleteLinkedConnectionWorker, StartContext);
    if ( v10 >= 0 )
    {
      v10 = KeWaitForSingleObject(StartContext + 2, Executive, 0, 0, 0);
      if ( v10 >= 0 )
        v10 = StartContext[8];
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
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140014658  push    rbx
0x14001465a  push    rbp
0x14001465b  push    rsi
0x14001465c  push    rdi
0x14001465d  push    r14
0x14001465f  push    r15
0x140014661  sub     rsp, 58h
0x140014665  mov     r14, rdx
0x140014668  mov     [rsp+88h+Handle], 0
0x140014671  mov     edx, 48h ; 'H'
0x140014676  mov     [rsp+88h+ThreadHandle], 0
0x14001467f  mov     rbp, r8
0x140014682  mov     r15, rcx
0x140014685  mov     r8d, 4C436644h
0x14001468b  mov     esi, r9d
0x14001468e  lea     ecx, [rdx-6]
0x140014691  call    cs:__imp_ExAllocatePool2
0x140014698  nop     dword ptr [rax+rax+00h]
0x14001469d  mov     rbx, rax
0x1400146a0  test    rax, rax
0x1400146a3  jnz     short loc_1400146AF
0x1400146a5  mov     eax, 0C000009Ah
0x1400146aa  jmp     loc_1400147F2
0x1400146af  lea     rax, [rsp+88h+Handle]
0x1400146b4  mov     r9d, 200h; HandleAttributes
0x1400146ba  mov     r8b, 1; OpenAsSelf
0x1400146bd  mov     [rsp+88h+TokenHandle], rax; TokenHandle
0x1400146c2  mov     edx, 8; DesiredAccess
0x1400146c7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400146ce  call    cs:__imp_ZwOpenThreadTokenEx
0x1400146d5  nop     dword ptr [rax+rax+00h]
0x1400146da  mov     edi, eax
0x1400146dc  cmp     eax, 0C000007Ch
0x1400146e1  jnz     short loc_140014705
0x1400146e3  lea     r9, [rsp+88h+Handle]; TokenHandle
0x1400146e8  mov     edx, 8; DesiredAccess
0x1400146ed  mov     r8d, 200h; HandleAttributes
0x1400146f3  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400146f7  call    cs:__imp_ZwOpenProcessTokenEx
0x1400146fe  nop     dword ptr [rax+rax+00h]
0x140014703  mov     edi, eax
0x140014705  test    edi, edi
0x140014707  jns     short loc_14001471F
0x140014709  xor     edx, edx; Tag
0x14001470b  mov     rcx, rbx; P
0x14001470e  call    cs:__imp_ExFreePoolWithTag
0x140014715  nop     dword ptr [rax+rax+00h]
0x14001471a  jmp     loc_1400147F0
0x14001471f  xor     r8d, r8d; State
0x140014722  mov     [rbx+28h], rbp
0x140014726  lea     rax, [rsp+88h+Handle]
0x14001472b  mov     [rbx+30h], r14
0x14001472f  lea     rcx, [rbx+8]; Event
0x140014733  mov     [rbx], rax
0x140014736  mov     [rbx+38h], esi
0x140014739  lea     edx, [r8+1]; Type
0x14001473d  mov     [rbx+40h], r15
0x140014741  call    cs:__imp_KeInitializeEvent
0x140014748  nop     dword ptr [rax+rax+00h]
0x14001474d  lea     rax, DfscDeleteLinkedConnectionWorker
0x140014754  mov     [rsp+88h+StartContext], rbx; StartContext
0x140014759  mov     [rsp+88h+StartRoutine], rax; StartRoutine
0x14001475e  lea     rcx, [rsp+88h+ThreadHandle]; ThreadHandle
0x140014763  xor     r9d, r9d; ProcessHandle
0x140014766  mov     [rsp+88h+TokenHandle], 0; ClientId
0x14001476f  xor     r8d, r8d; ObjectAttributes
0x140014772  mov     edx, 1FFFFFh; DesiredAccess
0x140014777  call    cs:__imp_PsCreateSystemThread
0x14001477e  nop     dword ptr [rax+rax+00h]
0x140014783  mov     edi, eax
0x140014785  test    eax, eax
0x140014787  js      short loc_1400147B3
0x140014789  xor     r9d, r9d; Alertable
0x14001478c  mov     [rsp+88h+TokenHandle], 0; Timeout
0x140014795  xor     r8d, r8d; WaitMode
0x140014798  lea     rcx, [rbx+8]; Object
0x14001479c  xor     edx, edx; WaitReason
0x14001479e  call    cs:__imp_KeWaitForSingleObject
0x1400147a5  nop     dword ptr [rax+rax+00h]
0x1400147aa  mov     edi, eax
0x1400147ac  test    eax, eax
0x1400147ae  js      short loc_1400147B3
0x1400147b0  mov     edi, [rbx+20h]
0x1400147b3  xor     edx, edx; Tag
0x1400147b5  mov     rcx, rbx; P
0x1400147b8  call    cs:__imp_ExFreePoolWithTag
0x1400147bf  nop     dword ptr [rax+rax+00h]
0x1400147c4  mov     rcx, [rsp+88h+Handle]; Handle
0x1400147c9  test    rcx, rcx
0x1400147cc  jz      short loc_1400147DA
0x1400147ce  call    cs:__imp_ZwClose
0x1400147d5  nop     dword ptr [rax+rax+00h]
0x1400147da  mov     rcx, [rsp+88h+ThreadHandle]; Handle
0x1400147df  test    rcx, rcx
0x1400147e2  jz      short loc_1400147F0
0x1400147e4  call    cs:__imp_ZwClose
0x1400147eb  nop     dword ptr [rax+rax+00h]
0x1400147f0  mov     eax, edi
0x1400147f2  add     rsp, 58h
0x1400147f6  pop     r15
0x1400147f8  pop     r14
0x1400147fa  pop     rdi
0x1400147fb  pop     rsi
0x1400147fc  pop     rbp
0x1400147fd  pop     rbx
0x1400147fe  retn
```
