# FveEowFreeSweepStopThread

- ea: `0x14007da44`
- end: `0x14007dbe7`
- name: `FveEowFreeSweepStopThread`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14007d8c4`
- `0x14007dbf0`

## callees

- `0x140008dc0`
- `0x14002c890`
- `0x14007da44`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14007db12`
- `ntoskrnl!ObfDereferenceObject` at `0x14007db9d`
- `ntoskrnl!ObfDereferenceObject` at `0x14007db12`
- `ntoskrnl!ObfDereferenceObject` at `0x14007db9d`
- `ntoskrnl!ObfReferenceObject` at `0x14007dabc`
- `ntoskrnl!ObfReferenceObject` at `0x14007dabc`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007da9f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007da9f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007dae9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007dae9`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007db6e`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007db6e`
- `ntoskrnl!KeSetEvent` at `0x14007dafe`
- `ntoskrnl!KeSetEvent` at `0x14007dafe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007db8e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007db8e`

## pseudocode

```c
void __fastcall FveEowFreeSweepStopThread(__int64 a1, char a2)
{
  void *v4; // rsi
  struct _KTHREAD *v5; // rdi
  KPRIORITY PriorityFromThread; // ebx
  struct _KTHREAD *CurrentThread; // rcx
  unsigned int v8; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 228, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
  }
  if ( a1 )
  {
    v4 = 0;
    v5 = 0;
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 24));
    if ( a2 )
    {
      v5 = *(struct _KTHREAD **)(a1 + 80);
      if ( v5 )
        ObfReferenceObject(*(PVOID *)(a1 + 80));
    }
    if ( *(struct _KTHREAD **)(a1 + 80) == KeGetCurrentThread() )
    {
      v4 = *(void **)(a1 + 80);
      *(_QWORD *)(a1 + 80) = 0;
    }
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a1 + 24));
    KeSetEvent((PRKEVENT)(a1 + 88), 0, 0);
    if ( v4 )
      ObfDereferenceObject(v4);
    if ( v5 )
    {
      PriorityFromThread = FveGetPriorityFromThreadEx(KeGetCurrentThread(), 18, 0);
      if ( PriorityFromThread <= FveGetPriorityFromThreadEx(v5, 18, 0) )
        CurrentThread = v5;
      else
        CurrentThread = KeGetCurrentThread();
      v8 = FveGetPriorityFromThreadEx(CurrentThread, 18, 0);
      KeSetActualBasePriorityThread(v5, v8);
      KeWaitForSingleObject(v5, Executive, 0, 0, 0);
      ObfDereferenceObject(v5);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
  }
}

```

## disassembly

```asm
0x14007da44  push    rbx
0x14007da46  push    rbp
0x14007da47  push    rsi
0x14007da48  push    rdi
0x14007da49  push    r12
0x14007da4b  push    r14
0x14007da4d  sub     rsp, 38h
0x14007da51  mov     r14b, dl
0x14007da54  mov     rbx, rcx
0x14007da57  mov     rcx, cs:WPP_GLOBAL_Control
0x14007da5e  lea     r12, WPP_GLOBAL_Control
0x14007da65  cmp     rcx, r12
0x14007da68  jz      short loc_14007DA8E
0x14007da6a  test    dword ptr [rcx+2Ch], 100h
0x14007da71  jz      short loc_14007DA8E
0x14007da73  cmp     byte ptr [rcx+29h], 5
0x14007da77  jb      short loc_14007DA8E
0x14007da79  mov     rcx, [rcx+18h]
0x14007da7d  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007da84  mov     edx, 0E4h
0x14007da89  call    WPP_SF_
0x14007da8e  test    rbx, rbx
0x14007da91  jz      loc_14007DBA9
0x14007da97  lea     rcx, [rbx+18h]; Mutex
0x14007da9b  xor     esi, esi
0x14007da9d  xor     edi, edi
0x14007da9f  call    cs:__imp_KeAcquireGuardedMutex
0x14007daa6  nop     dword ptr [rax+rax+00h]
0x14007daab  test    r14b, r14b
0x14007daae  jz      short loc_14007DAC8
0x14007dab0  mov     rdi, [rbx+50h]
0x14007dab4  test    rdi, rdi
0x14007dab7  jz      short loc_14007DAC8
0x14007dab9  mov     rcx, rdi; Object
0x14007dabc  call    cs:__imp_ObfReferenceObject
0x14007dac3  nop     dword ptr [rax+rax+00h]
0x14007dac8  mov     rdx, [rbx+50h]
0x14007dacc  mov     rax, gs:188h
0x14007dad5  cmp     rdx, rax
0x14007dad8  jnz     short loc_14007DAE5
0x14007dada  mov     rsi, rdx
0x14007dadd  mov     qword ptr [rbx+50h], 0
0x14007dae5  lea     rcx, [rbx+18h]; Mutex
0x14007dae9  call    cs:__imp_KeReleaseGuardedMutex
0x14007daf0  nop     dword ptr [rax+rax+00h]
0x14007daf5  lea     rcx, [rbx+58h]; Event
0x14007daf9  xor     r8d, r8d; Wait
0x14007dafc  xor     edx, edx; Increment
0x14007dafe  call    cs:__imp_KeSetEvent
0x14007db05  nop     dword ptr [rax+rax+00h]
0x14007db0a  test    rsi, rsi
0x14007db0d  jz      short loc_14007DB1E
0x14007db0f  mov     rcx, rsi; Object
0x14007db12  call    cs:__imp_ObfDereferenceObject
0x14007db19  nop     dword ptr [rax+rax+00h]
0x14007db1e  test    rdi, rdi
0x14007db21  jz      loc_14007DBA9
0x14007db27  mov     rcx, gs:188h
0x14007db30  xor     r8d, r8d
0x14007db33  lea     esi, [r8+12h]
0x14007db37  mov     edx, esi
0x14007db39  call    FveGetPriorityFromThreadEx
0x14007db3e  xor     r8d, r8d
0x14007db41  mov     edx, esi
0x14007db43  mov     rcx, rdi
0x14007db46  mov     ebx, eax
0x14007db48  call    FveGetPriorityFromThreadEx
0x14007db4d  cmp     ebx, eax
0x14007db4f  jle     short loc_14007DB5C
0x14007db51  mov     rcx, gs:188h
0x14007db5a  jmp     short loc_14007DB5F
0x14007db5c  mov     rcx, rdi
0x14007db5f  xor     r8d, r8d
0x14007db62  mov     edx, esi
0x14007db64  call    FveGetPriorityFromThreadEx
0x14007db69  mov     edx, eax
0x14007db6b  mov     rcx, rdi
0x14007db6e  call    cs:__imp_KeSetActualBasePriorityThread
0x14007db75  nop     dword ptr [rax+rax+00h]
0x14007db7a  xor     r9d, r9d; Alertable
0x14007db7d  mov     [rsp+68h+Timeout], 0; Timeout
0x14007db86  xor     r8d, r8d; WaitMode
0x14007db89  xor     edx, edx; WaitReason
0x14007db8b  mov     rcx, rdi; Object
0x14007db8e  call    cs:__imp_KeWaitForSingleObject
0x14007db95  nop     dword ptr [rax+rax+00h]
0x14007db9a  mov     rcx, rdi; Object
0x14007db9d  call    cs:__imp_ObfDereferenceObject
0x14007dba4  nop     dword ptr [rax+rax+00h]
0x14007dba9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dbb0  cmp     rcx, r12
0x14007dbb3  jz      short loc_14007DBD9
0x14007dbb5  test    dword ptr [rcx+2Ch], 100h
0x14007dbbc  jz      short loc_14007DBD9
0x14007dbbe  cmp     byte ptr [rcx+29h], 5
0x14007dbc2  jb      short loc_14007DBD9
0x14007dbc4  mov     rcx, [rcx+18h]
0x14007dbc8  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007dbcf  mov     edx, 0E5h
0x14007dbd4  call    WPP_SF_
0x14007dbd9  add     rsp, 38h
0x14007dbdd  pop     r14
0x14007dbdf  pop     r12
0x14007dbe1  pop     rdi
0x14007dbe2  pop     rsi
0x14007dbe3  pop     rbp
0x14007dbe4  pop     rbx
0x14007dbe5  retn
```
