# TSDeleteQueue

- ea: `0x140005d58`
- end: `0x140005eda`
- name: `TSDeleteQueue`
- size: `386`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140017cac`

## callees

- `0x1400016e0`
- `0x140005d58`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005ebb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ebb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005d83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005d83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ddc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005eaa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ddc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005eaa`
- `ntoskrnl!ZwClose` at `0x140005e7d`
- `ntoskrnl!ZwClose` at `0x140005e7d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140005e30`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140005e30`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e5b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005e5b`
- `ntoskrnl!ObfDereferenceObject` at `0x140005e6c`
- `ntoskrnl!ObfDereferenceObject` at `0x140005e6c`
- `ntoskrnl!KeSetEvent` at `0x140005dc7`
- `ntoskrnl!KeSetEvent` at `0x140005dc7`
- `ntoskrnl!PsThreadType` at `0x140005e05`

## pseudocode

```c
__int64 __fastcall TSDeleteQueue(void *a1)
{
  __int64 v1; // rbx
  KIRQL v2; // al
  int v3; // ecx
  KIRQL v4; // di
  __int64 i; // rdi
  char *v7; // rcx
  KIRQL v8; // al
  PVOID Object; // [rsp+40h] [rbp+8h] BYREF

  Object = a1;
  v1 = *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement;
  if ( *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement )
  {
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement + 112LL));
    v3 = *(_DWORD *)(v1 + 16);
    v4 = v2;
    if ( (v3 & 0x80u) != 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 112), v2);
      return 3221225506LL;
    }
    *(_DWORD *)(v1 + 16) = v3 | 0x80;
    KeSetEvent((PRKEVENT)(v1 + 128), 0, 0);
    ++*(_DWORD *)(v1 + 24);
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 112), v4);
    TSQueueWorker((PVOID)v1);
    for ( i = 0; i != 10; ++i )
    {
      v7 = *(char **)(v1 + 8 * i + 32);
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        Object = 0;
        if ( !ObReferenceObjectByHandle(v7, 0, (POBJECT_TYPE)PsThreadType, 0, &Object, 0) )
        {
          if ( Object )
          {
            KeWaitForSingleObject(Object, Executive, 0, 0, 0);
            ObfDereferenceObject(Object);
          }
        }
        ZwClose(*(HANDLE *)(v1 + 8 * i + 32));
      }
    }
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 112));
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 112), v8);
    ExFreePoolWithTag((PVOID)v1, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140005d58  mov     [rsp+arg_8], rbx
0x140005d5d  mov     [rsp+arg_10], rsi
0x140005d62  mov     [rsp+arg_0], rcx
0x140005d67  push    rdi
0x140005d68  sub     rsp, 30h
0x140005d6c  mov     rbx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x140005d73  test    rbx, rbx
0x140005d76  jz      loc_140005EC7
0x140005d7c  lea     rsi, [rbx+70h]
0x140005d80  mov     rcx, rsi; SpinLock
0x140005d83  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005d8a  nop     dword ptr [rax+rax+00h]
0x140005d8f  mov     ecx, [rbx+10h]
0x140005d92  mov     dil, al
0x140005d95  test    cl, cl
0x140005d97  jns     short loc_140005DB4
0x140005d99  mov     dl, al; NewIrql
0x140005d9b  mov     rcx, rsi; SpinLock
0x140005d9e  call    cs:__imp_KeReleaseSpinLock
0x140005da5  nop     dword ptr [rax+rax+00h]
0x140005daa  mov     eax, 0C0000022h
0x140005daf  jmp     loc_140005EC9
0x140005db4  bts     ecx, 7
0x140005db8  xor     r8d, r8d; Wait
0x140005dbb  mov     [rbx+10h], ecx
0x140005dbe  xor     edx, edx; Increment
0x140005dc0  lea     rcx, [rbx+80h]; Event
0x140005dc7  call    cs:__imp_KeSetEvent
0x140005dce  nop     dword ptr [rax+rax+00h]
0x140005dd3  inc     dword ptr [rbx+18h]
0x140005dd6  mov     dl, dil; NewIrql
0x140005dd9  mov     rcx, rsi; SpinLock
0x140005ddc  call    cs:__imp_KeReleaseSpinLock
0x140005de3  nop     dword ptr [rax+rax+00h]
0x140005de8  mov     rcx, rbx; StartContext
0x140005deb  call    TSQueueWorker
0x140005df0  xor     edi, edi
0x140005df2  mov     rcx, [rbx+rdi*8+20h]; Handle
0x140005df7  lea     rax, [rcx-1]
0x140005dfb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005dff  ja      loc_140005E89
0x140005e05  mov     r8, cs:__imp_PsThreadType
0x140005e0c  lea     rax, [rsp+38h+arg_0]
0x140005e11  mov     [rsp+38h+arg_0], 0
0x140005e1a  xor     r9d, r9d; AccessMode
0x140005e1d  mov     [rsp+38h+HandleInformation], 0; HandleInformation
0x140005e26  xor     edx, edx; DesiredAccess
0x140005e28  mov     [rsp+38h+Object], rax; Object
0x140005e2d  mov     r8, [r8]; ObjectType
0x140005e30  call    cs:__imp_ObReferenceObjectByHandle
0x140005e37  nop     dword ptr [rax+rax+00h]
0x140005e3c  test    eax, eax
0x140005e3e  jnz     short loc_140005E78
0x140005e40  mov     rcx, [rsp+38h+arg_0]; Object
0x140005e45  test    rcx, rcx
0x140005e48  jz      short loc_140005E78
0x140005e4a  xor     r9d, r9d; Alertable
0x140005e4d  mov     [rsp+38h+Object], 0; Timeout
0x140005e56  xor     r8d, r8d; WaitMode
0x140005e59  xor     edx, edx; WaitReason
0x140005e5b  call    cs:__imp_KeWaitForSingleObject
0x140005e62  nop     dword ptr [rax+rax+00h]
0x140005e67  mov     rcx, [rsp+38h+arg_0]; Object
0x140005e6c  call    cs:__imp_ObfDereferenceObject
0x140005e73  nop     dword ptr [rax+rax+00h]
0x140005e78  mov     rcx, [rbx+rdi*8+20h]; Handle
0x140005e7d  call    cs:__imp_ZwClose
0x140005e84  nop     dword ptr [rax+rax+00h]
0x140005e89  inc     rdi
0x140005e8c  cmp     rdi, 0Ah
0x140005e90  jnz     loc_140005DF2
0x140005e96  mov     rcx, rsi; SpinLock
0x140005e99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005ea0  nop     dword ptr [rax+rax+00h]
0x140005ea5  mov     dl, al; NewIrql
0x140005ea7  mov     rcx, rsi; SpinLock
0x140005eaa  call    cs:__imp_KeReleaseSpinLock
0x140005eb1  nop     dword ptr [rax+rax+00h]
0x140005eb6  xor     edx, edx; Tag
0x140005eb8  mov     rcx, rbx; P
0x140005ebb  call    cs:__imp_ExFreePoolWithTag
0x140005ec2  nop     dword ptr [rax+rax+00h]
0x140005ec7  xor     eax, eax
0x140005ec9  mov     rbx, [rsp+38h+arg_8]
0x140005ece  mov     rsi, [rsp+38h+arg_10]
0x140005ed3  add     rsp, 30h
0x140005ed7  pop     rdi
0x140005ed8  retn
```
