# NfsUpCallCheckAndWaitForInFlightRequests

- ea: `0x1400391f8`
- end: `0x140039322`
- name: `NfsUpCallCheckAndWaitForInFlightRequests`
- size: `298`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140039b40`

## callees

- `0x1400391f8`
- `0x14003a490`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039228`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039298`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039228`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039298`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039253`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400392c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039253`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400392c3`
- `ntoskrnl!KeDelayExecutionThread` at `0x140039279`
- `ntoskrnl!KeDelayExecutionThread` at `0x140039279`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039217`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039287`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039217`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140039287`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003925f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400392cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003925f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400392cf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400392fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400392fe`

## pseudocode

```c
__int64 __fastcall NfsUpCallCheckAndWaitForInFlightRequests(__int64 a1)
{
  struct _ERESOURCE *v2; // rdi
  bool v3; // si
  bool v4; // si
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp+8h] BYREF

  Interval.QuadPart = -1000000;
  v2 = (struct _ERESOURCE *)(a1 + 8);
  while ( 1 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(v2, 1u);
    v3 = *(_DWORD *)(a1 + 148) || *(_DWORD *)(a1 + 152);
    ExReleaseResourceLite(v2);
    KeLeaveCriticalRegion();
    if ( !v3 )
      break;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  while ( 1 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(v2, 1u);
    v4 = *(_DWORD *)(a1 + 140) || *(_DWORD *)(a1 + 144);
    ExReleaseResourceLite(v2);
    KeLeaveCriticalRegion();
    if ( !v4 )
      break;
    UpCallRundownQueue(*(PKSPIN_LOCK *)a1);
    KeWaitForSingleObject((PVOID)(a1 + 112), Executive, 0, 0, &Interval);
  }
  return 0;
}

```

## disassembly

```asm
0x1400391f8  mov     [rsp+arg_8], rbx
0x1400391fd  mov     [rsp+arg_10], rsi
0x140039202  push    rdi
0x140039203  sub     rsp, 30h
0x140039207  mov     rbx, rcx
0x14003920a  mov     qword ptr [rsp+38h+Interval], 0FFFFFFFFFFF0BDC0h
0x140039213  lea     rdi, [rcx+8]
0x140039217  call    cs:__imp_KeEnterCriticalRegion
0x14003921e  nop     dword ptr [rax+rax+00h]
0x140039223  mov     dl, 1; Wait
0x140039225  mov     rcx, rdi; Resource
0x140039228  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003922f  nop     dword ptr [rax+rax+00h]
0x140039234  mov     eax, [rbx+94h]
0x14003923a  test    eax, eax
0x14003923c  jnz     short loc_14003924D
0x14003923e  mov     eax, [rbx+98h]
0x140039244  test    eax, eax
0x140039246  jnz     short loc_14003924D
0x140039248  xor     sil, sil
0x14003924b  jmp     short loc_140039250
0x14003924d  mov     sil, 1
0x140039250  mov     rcx, rdi; Resource
0x140039253  call    cs:__imp_ExReleaseResourceLite
0x14003925a  nop     dword ptr [rax+rax+00h]
0x14003925f  call    cs:__imp_KeLeaveCriticalRegion
0x140039266  nop     dword ptr [rax+rax+00h]
0x14003926b  test    sil, sil
0x14003926e  jz      short loc_140039287
0x140039270  lea     r8, [rsp+38h+Interval]; Interval
0x140039275  xor     edx, edx; Alertable
0x140039277  xor     ecx, ecx; WaitMode
0x140039279  call    cs:__imp_KeDelayExecutionThread
0x140039280  nop     dword ptr [rax+rax+00h]
0x140039285  jmp     short loc_140039217
0x140039287  call    cs:__imp_KeEnterCriticalRegion
0x14003928e  nop     dword ptr [rax+rax+00h]
0x140039293  mov     dl, 1; Wait
0x140039295  mov     rcx, rdi; Resource
0x140039298  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003929f  nop     dword ptr [rax+rax+00h]
0x1400392a4  mov     eax, [rbx+8Ch]
0x1400392aa  test    eax, eax
0x1400392ac  jnz     short loc_1400392BD
0x1400392ae  mov     eax, [rbx+90h]
0x1400392b4  test    eax, eax
0x1400392b6  jnz     short loc_1400392BD
0x1400392b8  xor     sil, sil
0x1400392bb  jmp     short loc_1400392C0
0x1400392bd  mov     sil, 1
0x1400392c0  mov     rcx, rdi; Resource
0x1400392c3  call    cs:__imp_ExReleaseResourceLite
0x1400392ca  nop     dword ptr [rax+rax+00h]
0x1400392cf  call    cs:__imp_KeLeaveCriticalRegion
0x1400392d6  nop     dword ptr [rax+rax+00h]
0x1400392db  test    sil, sil
0x1400392de  jz      short loc_14003930F
0x1400392e0  mov     rcx, [rbx]; SpinLock
0x1400392e3  call    UpCallRundownQueue
0x1400392e8  lea     rax, [rsp+38h+Interval]
0x1400392ed  xor     r9d, r9d; Alertable
0x1400392f0  lea     rcx, [rbx+70h]; Object
0x1400392f4  mov     [rsp+38h+Timeout], rax; Timeout
0x1400392f9  xor     r8d, r8d; WaitMode
0x1400392fc  xor     edx, edx; WaitReason
0x1400392fe  call    cs:__imp_KeWaitForSingleObject
0x140039305  nop     dword ptr [rax+rax+00h]
0x14003930a  jmp     loc_140039287
0x14003930f  mov     rbx, [rsp+38h+arg_8]
0x140039314  xor     eax, eax
0x140039316  mov     rsi, [rsp+38h+arg_10]
0x14003931b  add     rsp, 30h
0x14003931f  pop     rdi
0x140039320  retn
```
