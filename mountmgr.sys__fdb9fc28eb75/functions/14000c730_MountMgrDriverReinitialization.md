# MountMgrDriverReinitialization

- ea: `0x14000c730`
- end: `0x14000c7d0`
- name: `MountMgrDriverReinitialization`
- size: `160`
- prototype: `DRIVER_REINITIALIZE`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140002afc`
- `0x14000c730`
- `0x14000fcc0`
- `0x140019140`
- `0x140019af0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000c7b2`
- `ntoskrnl!KeReleaseMutex` at `0x14000c7b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c751`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c751`

## pseudocode

```c
void __fastcall MountMgrDriverReinitialization(
        struct _DRIVER_OBJECT *DriverObject,
        struct _KMUTANT *Context,
        ULONG Count)
{
  struct _LIST_ENTRY **p_Blink; // rdi
  struct _LIST_ENTRY *i; // rbx
  struct _LIST_ENTRY *j; // rbx
  __int16 v7; // [rsp+68h] [rbp+10h] BYREF

  KeWaitForSingleObject(&Context[1], Executive, 0, 0, 0);
  LOBYTE(Context[2].MutantListEntry.Blink) = 1;
  v7 = 0;
  ProcessSuggestedDriveLetters(Context);
  p_Blink = &Context->Header.WaitListHead.Blink;
  for ( i = Context->Header.WaitListHead.Blink; i != (struct _LIST_ENTRY *)p_Blink; i = i->Flink )
    MountMgrNextDriveLetterWorker(Context, (__int64)i, &v7);
  for ( j = *p_Blink; j != (struct _LIST_ENTRY *)p_Blink; j = j->Flink )
    ReconcileThisDatabaseWithMaster(Context);
  KeReleaseMutex(Context + 1, 0);
  WaitForOnlinesToComplete(Context);
}

```

## disassembly

```asm
0x14000c730  push    rbx
0x14000c732  push    rbp
0x14000c733  push    rsi
0x14000c734  push    rdi
0x14000c735  sub     rsp, 38h
0x14000c739  mov     rsi, rdx
0x14000c73c  mov     [rsp+58h+Timeout], 0; Timeout
0x14000c745  xor     r9d, r9d; Alertable
0x14000c748  xor     r8d, r8d; WaitMode
0x14000c74b  xor     edx, edx; WaitReason
0x14000c74d  lea     rcx, [rsi+38h]; Object
0x14000c751  call    cs:__imp_KeWaitForSingleObject
0x14000c758  nop     dword ptr [rax+rax+00h]
0x14000c75d  xor     eax, eax
0x14000c75f  mov     byte ptr [rsi+90h], 1
0x14000c766  mov     rcx, rsi; Context
0x14000c769  mov     [rsp+58h+arg_8], ax
0x14000c76e  call    ProcessSuggestedDriveLetters
0x14000c773  lea     rdi, [rsi+10h]
0x14000c777  mov     rbx, [rdi]
0x14000c77a  jmp     short loc_14000C78F
0x14000c77c  lea     r8, [rsp+58h+arg_8]
0x14000c781  mov     rdx, rbx
0x14000c784  mov     rcx, rsi; Context
0x14000c787  call    MountMgrNextDriveLetterWorker
0x14000c78c  mov     rbx, [rbx]
0x14000c78f  cmp     rbx, rdi
0x14000c792  jnz     short loc_14000C77C
0x14000c794  mov     rbx, [rdi]
0x14000c797  jmp     short loc_14000C7A7
0x14000c799  mov     rdx, rbx
0x14000c79c  mov     rcx, rsi; Context
0x14000c79f  call    ReconcileThisDatabaseWithMaster
0x14000c7a4  mov     rbx, [rbx]
0x14000c7a7  cmp     rbx, rdi
0x14000c7aa  jnz     short loc_14000C799
0x14000c7ac  xor     edx, edx; Wait
0x14000c7ae  lea     rcx, [rsi+38h]; Mutex
0x14000c7b2  call    cs:__imp_KeReleaseMutex
0x14000c7b9  nop     dword ptr [rax+rax+00h]
0x14000c7be  mov     rcx, rsi
0x14000c7c1  call    WaitForOnlinesToComplete
0x14000c7c6  add     rsp, 38h
0x14000c7ca  pop     rdi
0x14000c7cb  pop     rsi
0x14000c7cc  pop     rbp
0x14000c7cd  pop     rbx
0x14000c7ce  retn
```
