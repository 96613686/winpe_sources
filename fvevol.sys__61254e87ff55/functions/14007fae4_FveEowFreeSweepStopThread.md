# FveEowFreeSweepStopThread

- ea: `0x14007fae4`
- end: `0x14007fc87`
- name: `FveEowFreeSweepStopThread`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14007f964`
- `0x14007fc90`

## callees

- `0x140008e80`
- `0x14002d890`
- `0x14007fae4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14007fbb2`
- `ntoskrnl!ObfDereferenceObject` at `0x14007fc3d`
- `ntoskrnl!ObfDereferenceObject` at `0x14007fbb2`
- `ntoskrnl!ObfDereferenceObject` at `0x14007fc3d`
- `ntoskrnl!ObfReferenceObject` at `0x14007fb5c`
- `ntoskrnl!ObfReferenceObject` at `0x14007fb5c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007fb3f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007fb3f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007fb89`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007fb89`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007fc0e`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007fc0e`
- `ntoskrnl!KeSetEvent` at `0x14007fb9e`
- `ntoskrnl!KeSetEvent` at `0x14007fb9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007fc2e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007fc2e`

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
0x14007fae4  push    rbx
0x14007fae6  push    rbp
0x14007fae7  push    rsi
0x14007fae8  push    rdi
0x14007fae9  push    r12
0x14007faeb  push    r14
0x14007faed  sub     rsp, 38h
0x14007faf1  mov     r14b, dl
0x14007faf4  mov     rbx, rcx
0x14007faf7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fafe  lea     r12, WPP_GLOBAL_Control
0x14007fb05  cmp     rcx, r12
0x14007fb08  jz      short loc_14007FB2E
0x14007fb0a  test    dword ptr [rcx+2Ch], 100h
0x14007fb11  jz      short loc_14007FB2E
0x14007fb13  cmp     byte ptr [rcx+29h], 5
0x14007fb17  jb      short loc_14007FB2E
0x14007fb19  mov     rcx, [rcx+18h]
0x14007fb1d  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007fb24  mov     edx, 0E4h
0x14007fb29  call    WPP_SF_
0x14007fb2e  test    rbx, rbx
0x14007fb31  jz      loc_14007FC49
0x14007fb37  lea     rcx, [rbx+18h]; Mutex
0x14007fb3b  xor     esi, esi
0x14007fb3d  xor     edi, edi
0x14007fb3f  call    cs:__imp_KeAcquireGuardedMutex
0x14007fb46  nop     dword ptr [rax+rax+00h]
0x14007fb4b  test    r14b, r14b
0x14007fb4e  jz      short loc_14007FB68
0x14007fb50  mov     rdi, [rbx+50h]
0x14007fb54  test    rdi, rdi
0x14007fb57  jz      short loc_14007FB68
0x14007fb59  mov     rcx, rdi; Object
0x14007fb5c  call    cs:__imp_ObfReferenceObject
0x14007fb63  nop     dword ptr [rax+rax+00h]
0x14007fb68  mov     rdx, [rbx+50h]
0x14007fb6c  mov     rax, gs:188h
0x14007fb75  cmp     rdx, rax
0x14007fb78  jnz     short loc_14007FB85
0x14007fb7a  mov     rsi, rdx
0x14007fb7d  mov     qword ptr [rbx+50h], 0
0x14007fb85  lea     rcx, [rbx+18h]; Mutex
0x14007fb89  call    cs:__imp_KeReleaseGuardedMutex
0x14007fb90  nop     dword ptr [rax+rax+00h]
0x14007fb95  lea     rcx, [rbx+58h]; Event
0x14007fb99  xor     r8d, r8d; Wait
0x14007fb9c  xor     edx, edx; Increment
0x14007fb9e  call    cs:__imp_KeSetEvent
0x14007fba5  nop     dword ptr [rax+rax+00h]
0x14007fbaa  test    rsi, rsi
0x14007fbad  jz      short loc_14007FBBE
0x14007fbaf  mov     rcx, rsi; Object
0x14007fbb2  call    cs:__imp_ObfDereferenceObject
0x14007fbb9  nop     dword ptr [rax+rax+00h]
0x14007fbbe  test    rdi, rdi
0x14007fbc1  jz      loc_14007FC49
0x14007fbc7  mov     rcx, gs:188h
0x14007fbd0  xor     r8d, r8d
0x14007fbd3  lea     esi, [r8+12h]
0x14007fbd7  mov     edx, esi
0x14007fbd9  call    FveGetPriorityFromThreadEx
0x14007fbde  xor     r8d, r8d
0x14007fbe1  mov     edx, esi
0x14007fbe3  mov     rcx, rdi
0x14007fbe6  mov     ebx, eax
0x14007fbe8  call    FveGetPriorityFromThreadEx
0x14007fbed  cmp     ebx, eax
0x14007fbef  jle     short loc_14007FBFC
0x14007fbf1  mov     rcx, gs:188h
0x14007fbfa  jmp     short loc_14007FBFF
0x14007fbfc  mov     rcx, rdi
0x14007fbff  xor     r8d, r8d
0x14007fc02  mov     edx, esi
0x14007fc04  call    FveGetPriorityFromThreadEx
0x14007fc09  mov     edx, eax
0x14007fc0b  mov     rcx, rdi
0x14007fc0e  call    cs:__imp_KeSetActualBasePriorityThread
0x14007fc15  nop     dword ptr [rax+rax+00h]
0x14007fc1a  xor     r9d, r9d; Alertable
0x14007fc1d  mov     [rsp+68h+Timeout], 0; Timeout
0x14007fc26  xor     r8d, r8d; WaitMode
0x14007fc29  xor     edx, edx; WaitReason
0x14007fc2b  mov     rcx, rdi; Object
0x14007fc2e  call    cs:__imp_KeWaitForSingleObject
0x14007fc35  nop     dword ptr [rax+rax+00h]
0x14007fc3a  mov     rcx, rdi; Object
0x14007fc3d  call    cs:__imp_ObfDereferenceObject
0x14007fc44  nop     dword ptr [rax+rax+00h]
0x14007fc49  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fc50  cmp     rcx, r12
0x14007fc53  jz      short loc_14007FC79
0x14007fc55  test    dword ptr [rcx+2Ch], 100h
0x14007fc5c  jz      short loc_14007FC79
0x14007fc5e  cmp     byte ptr [rcx+29h], 5
0x14007fc62  jb      short loc_14007FC79
0x14007fc64  mov     rcx, [rcx+18h]
0x14007fc68  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007fc6f  mov     edx, 0E5h
0x14007fc74  call    WPP_SF_
0x14007fc79  add     rsp, 38h
0x14007fc7d  pop     r14
0x14007fc7f  pop     r12
0x14007fc81  pop     rdi
0x14007fc82  pop     rsi
0x14007fc83  pop     rbp
0x14007fc84  pop     rbx
0x14007fc85  retn
```
