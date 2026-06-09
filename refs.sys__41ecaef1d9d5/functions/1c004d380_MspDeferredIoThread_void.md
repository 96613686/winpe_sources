# MspDeferredIoThread(void *)

- ea: `0x1c004d380`
- end: `0x1c004d4a2`
- name: `?MspDeferredIoThread@@YAXPEAX@Z`
- size: `290`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1c004d380`
- `0x1c004d4b0`
- `0x1c004e1d0`
- `0x1c0068960`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x1c004d486`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c004d486`
- `ntoskrnl!KeSetEvent` at `0x1c008694a`
- `ntoskrnl!KeSetEvent` at `0x1c008694a`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c004d466`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c004d466`
- `ntoskrnl!KeSetBasePriorityThread` at `0x1c004d3c7`
- `ntoskrnl!KeSetBasePriorityThread` at `0x1c004d3c7`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1c004d41f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1c004d41f`

## pseudocode

```c
void __fastcall MspDeferredIoThread(PVOID StartContext)
{
  GUID *v1; // r15
  unsigned __int8 v2; // si
  unsigned __int8 v3; // r14
  NTSTATUS v4; // eax
  unsigned __int8 v5; // di
  __int64 v6; // rbx
  int v7; // eax
  unsigned __int8 v8; // [rsp+48h] [rbp-79h] BYREF
  unsigned __int8 v9[7]; // [rsp+49h] [rbp-78h] BYREF
  PVOID Object[3]; // [rsp+50h] [rbp-71h] BYREF
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+68h] [rbp-59h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v9[0] = 0;
  KeSetBasePriorityThread(KeGetCurrentThread(), 5);
  Object[0] = &LazyWriterScanEvent;
  Object[1] = &CmsCachedPin::LazyUnpinEvent;
  Object[2] = &StopDeferredIoThreadEvent;
  while ( 1 )
  {
    v4 = KeWaitForMultipleObjects(3u, Object, WaitAny, WrFreePage, 0, 0, 0, &WaitBlockArray);
    if ( !v4 )
    {
      v3 = 0;
      v1 = &MsActivityIdLazyWriterScan;
      v2 = 1;
      goto LABEL_4;
    }
    v7 = v4 - 1;
    if ( !v7 )
    {
      v2 = 0;
      v1 = &MsActivityIdLazyWriterUnpin;
      v5 = 0;
      v3 = 1;
      goto LABEL_6;
    }
    if ( v7 == 1 )
      break;
LABEL_4:
    v5 = 0;
    v8 = 0;
    if ( v2 )
    {
      MspVolumeCheckpointScan(v9, &v8);
      v5 = v8;
    }
LABEL_6:
    if ( v9[0] || v5 )
    {
      v6 = IoSetActivityIdThread(v1);
      MspLazyWriterScan(v3, v2, v5);
      IoClearActivityIdThread(v6);
    }
  }
  KeSetEvent(&DeferredIoThreadTerminatedEvent, 0, 0);
}

```

## disassembly

```asm
0x1c004d380  mov     rax, rsp
0x1c004d383  mov     [rax+8], rbx
0x1c004d387  mov     [rax+10h], rsi
0x1c004d38b  mov     [rax+18h], rdi
0x1c004d38f  push    rbp
0x1c004d390  push    r14
0x1c004d392  push    r15
0x1c004d394  lea     rbp, [rax-5Fh]
0x1c004d398  sub     rsp, 100h
0x1c004d39f  mov     rax, cs:__security_cookie
0x1c004d3a6  xor     rax, rsp
0x1c004d3a9  mov     [rbp+57h+var_20], rax
0x1c004d3ad  mov     rcx, gs:188h; Thread
0x1c004d3b6  xor     r15d, r15d
0x1c004d3b9  xor     sil, sil
0x1c004d3bc  xor     r14b, r14b
0x1c004d3bf  mov     [rbp+57h+var_CF], sil
0x1c004d3c3  lea     edx, [r15+5]; Increment
0x1c004d3c7  call    cs:__imp_KeSetBasePriorityThread
0x1c004d3ce  nop     dword ptr [rax+rax+00h]
0x1c004d3d3  lea     rax, ?LazyWriterScanEvent@@3U_KEVENT@@A; _KEVENT LazyWriterScanEvent
0x1c004d3da  mov     [rbp+57h+Object], rax
0x1c004d3de  lea     rax, ?LazyUnpinEvent@CmsCachedPin@@2U_KEVENT@@A; _KEVENT CmsCachedPin::LazyUnpinEvent
0x1c004d3e5  mov     [rbp+57h+var_C0], rax
0x1c004d3e9  lea     rax, ?StopDeferredIoThreadEvent@@3U_KEVENT@@A; _KEVENT StopDeferredIoThreadEvent
0x1c004d3f0  mov     [rbp+57h+var_B8], rax
0x1c004d3f4  mov     r9d, 8; WaitReason
0x1c004d3fa  lea     rax, [rbp+57h+var_B0]
0x1c004d3fe  mov     [rsp+110h+WaitBlockArray], rax; WaitBlockArray
0x1c004d403  lea     rdx, [rbp+57h+Object]; Object
0x1c004d407  and     [rsp+110h+var_E0], 0
0x1c004d40d  mov     [rsp+110h+Alertable], 0; Alertable
0x1c004d412  lea     r8d, [r9-7]; WaitType
0x1c004d416  mov     [rsp+110h+WaitMode], 0; WaitMode
0x1c004d41b  lea     ecx, [r9-5]; Count
0x1c004d41f  call    cs:__imp_KeWaitForMultipleObjects
0x1c004d426  nop     dword ptr [rax+rax+00h]
0x1c004d42b  test    eax, eax
0x1c004d42d  jnz     loc_1C0086930
0x1c004d433  xor     r14b, r14b
0x1c004d436  lea     r15, ?MsActivityIdLazyWriterScan@@3U_GUID@@B; _GUID const MsActivityIdLazyWriterScan
0x1c004d43d  mov     sil, 1
0x1c004d440  xor     dil, dil
0x1c004d443  mov     [rbp+57h+var_D0], dil
0x1c004d447  test    sil, sil
0x1c004d44a  jz      short loc_1C004D45D
0x1c004d44c  lea     rdx, [rbp+57h+var_D0]; unsigned __int8 *
0x1c004d450  lea     rcx, [rbp+57h+var_CF]; unsigned __int8 *
0x1c004d454  call    ?MspVolumeCheckpointScan@@YAXPEAE0@Z; MspVolumeCheckpointScan(uchar *,uchar *)
0x1c004d459  mov     dil, [rbp+57h+var_D0]
0x1c004d45d  cmp     [rbp+57h+var_CF], 0
0x1c004d461  jz      short loc_1C004D497
0x1c004d463  mov     rcx, r15
0x1c004d466  call    cs:__imp_IoSetActivityIdThread
0x1c004d46d  nop     dword ptr [rax+rax+00h]
0x1c004d472  mov     r8b, dil; unsigned __int8
0x1c004d475  mov     dl, sil; unsigned __int8
0x1c004d478  mov     cl, r14b; unsigned __int8
0x1c004d47b  mov     rbx, rax
0x1c004d47e  call    ?MspLazyWriterScan@@YAXEEE@Z; MspLazyWriterScan(uchar,uchar,uchar)
0x1c004d483  mov     rcx, rbx
0x1c004d486  call    cs:__imp_IoClearActivityIdThread
0x1c004d48d  nop     dword ptr [rax+rax+00h]
0x1c004d492  jmp     loc_1C004D3F4
0x1c004d497  test    dil, dil
0x1c004d49a  jz      loc_1C004D3F4
0x1c004d4a0  jmp     short loc_1C004D463
0x1c0086930  sub     eax, 1
0x1c0086933  jz      short loc_1C0086980
0x1c0086935  cmp     eax, 1
0x1c0086938  jnz     loc_1C004D440
0x1c008693e  xor     r8d, r8d; Wait
0x1c0086941  lea     rcx, ?DeferredIoThreadTerminatedEvent@@3U_KEVENT@@A; Event
0x1c0086948  xor     edx, edx; Increment
0x1c008694a  call    cs:__imp_KeSetEvent
0x1c0086951  nop     dword ptr [rax+rax+00h]
0x1c0086956  mov     rcx, [rbp+57h+var_20]
0x1c008695a  xor     rcx, rsp; StackCookie
0x1c008695d  call    __security_check_cookie
0x1c0086962  lea     r11, [rsp+110h+var_10]
0x1c008696a  mov     rbx, [r11+20h]
0x1c008696e  mov     rsi, [r11+28h]
0x1c0086972  mov     rdi, [r11+30h]
0x1c0086976  mov     rsp, r11
0x1c0086979  pop     r15
0x1c008697b  pop     r14
0x1c008697d  pop     rbp
0x1c008697e  retn
0x1c0086980  xor     sil, sil
0x1c0086983  lea     r15, ?MsActivityIdLazyWriterUnpin@@3U_GUID@@B; _GUID const MsActivityIdLazyWriterUnpin
0x1c008698a  xor     dil, dil
0x1c008698d  mov     r14b, 1
0x1c0086990  jmp     loc_1C004D45D
```
