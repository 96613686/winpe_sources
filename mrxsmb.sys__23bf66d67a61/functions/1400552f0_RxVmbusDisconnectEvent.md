# RxVmbusDisconnectEvent

- ea: `0x1400552f0`
- end: `0x140055403`
- name: `RxVmbusDisconnectEvent`
- size: `275`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140056060`
- `0x140056180`

## callees

- `0x1400215b0`
- `0x1400383d0`
- `0x14003e14c`
- `0x1400552f0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400553c4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400553c4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140055354`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140055354`
- `rdbss!RxDispatchToWorkerThread` at `0x140055377`
- `rdbss!RxDispatchToWorkerThread` at `0x140055377`

## pseudocode

```c
__int64 __fastcall RxVmbusDisconnectEvent(__int64 pContext)
{
  __int64 result; // rax
  NTSTATUS v3; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, pContext);
  }
  result = VctSetEndpointState(pContext, 1, 0);
  if ( (_DWORD)result != 1 )
  {
    if ( ExAcquireRundownProtection(*(PEX_RUNDOWN_REF *)(pContext + 128)) )
    {
      v3 = RxDispatchToWorkerThread(
             *(PRDBSS_DEVICE_OBJECT *)(pContext + 24),
             BackgroundWorkQueue,
             RxVmbusDisconnectConnectionWorker,
             (PVOID)pContext);
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) )
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              34,
              WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids,
              pContext,
              v3);
        }
        ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(pContext + 128));
      }
    }
    return (**(__int64 (__fastcall ***)(__int64, __int64))(pContext + 392))(pContext, 0x7C000020CLL);
  }
  return result;
}

```

## disassembly

```asm
0x1400552f0  mov     [rsp+arg_0], rbx
0x1400552f5  push    rsi
0x1400552f6  sub     rsp, 30h
0x1400552fa  mov     rbx, rcx
0x1400552fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055304  lea     rsi, WPP_GLOBAL_Control
0x14005530b  cmp     rcx, rsi
0x14005530e  jz      short loc_140055335
0x140055310  mov     eax, [rcx+2Ch]
0x140055313  test    al, 1
0x140055315  jz      short loc_140055335
0x140055317  cmp     byte ptr [rcx+29h], 1
0x14005531b  jb      short loc_140055335
0x14005531d  mov     rcx, [rcx+18h]
0x140055321  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140055328  mov     edx, 21h ; '!'
0x14005532d  mov     r9, rbx
0x140055330  call    WPP_SF_q
0x140055335  xor     r8d, r8d
0x140055338  mov     rcx, rbx
0x14005533b  lea     edx, [r8+1]
0x14005533f  call    VctSetEndpointState
0x140055344  cmp     eax, 1
0x140055347  jz      loc_1400553F7
0x14005534d  mov     rcx, [rbx+80h]; RunRef
0x140055354  call    cs:__imp_ExAcquireRundownProtection
0x14005535b  nop     dword ptr [rax+rax+00h]
0x140055360  test    al, al
0x140055362  jz      short loc_1400553D0
0x140055364  mov     rcx, [rbx+18h]; pMRxDeviceObject
0x140055368  lea     r8, RxVmbusDisconnectConnectionWorker; Routine
0x14005536f  mov     r9, rbx; pContext
0x140055372  mov     edx, 4; WorkQueueType
0x140055377  call    cs:__imp_RxDispatchToWorkerThread
0x14005537e  nop     dword ptr [rax+rax+00h]
0x140055383  test    eax, eax
0x140055385  jns     short loc_1400553D0
0x140055387  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005538e  cmp     rcx, rsi
0x140055391  jz      short loc_1400553BD
0x140055393  mov     edx, [rcx+2Ch]
0x140055396  test    dl, 1
0x140055399  jz      short loc_1400553BD
0x14005539b  cmp     byte ptr [rcx+29h], 1
0x14005539f  jb      short loc_1400553BD
0x1400553a1  mov     rcx, [rcx+18h]
0x1400553a5  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x1400553ac  mov     edx, 22h ; '"'
0x1400553b1  mov     [rsp+38h+var_18], eax
0x1400553b5  mov     r9, rbx
0x1400553b8  call    WPP_SF_qD
0x1400553bd  mov     rcx, [rbx+80h]; RunRef
0x1400553c4  call    cs:__imp_ExReleaseRundownProtection
0x1400553cb  nop     dword ptr [rax+rax+00h]
0x1400553d0  mov     rax, [rbx+188h]
0x1400553d7  mov     rcx, rbx
0x1400553da  mov     dword ptr [rsp+38h+arg_8], 0C000020Ch
0x1400553e2  mov     dword ptr [rsp+38h+arg_8+4], 7
0x1400553ea  mov     rdx, [rsp+38h+arg_8]
0x1400553ef  mov     rax, [rax]
0x1400553f2  call    _guard_dispatch_icall
0x1400553f7  mov     rbx, [rsp+38h+arg_0]
0x1400553fc  add     rsp, 30h
0x140055400  pop     rsi
0x140055401  retn
```
