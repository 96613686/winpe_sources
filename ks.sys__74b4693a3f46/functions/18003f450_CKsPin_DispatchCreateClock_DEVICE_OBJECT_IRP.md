# CKsPin::DispatchCreateClock(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003f450`
- end: `0x18003f613`
- name: `?DispatchCreateClock@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `451`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180019b80`
- `0x180019c60`
- `0x180036fd0`
- `0x180037200`
- `0x18003f450`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003f5ce`
- `ntoskrnl!KeReleaseMutex` at `0x18003f5ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003f522`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003f522`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f4da`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f4da`
- `ntoskrnl!IofCompleteRequest` at `0x18003f5ea`
- `ntoskrnl!IofCompleteRequest` at `0x18003f5ea`

## pseudocode

```c
__int64 __fastcall CKsPin::DispatchCreateClock(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  __int64 v3; // rbp
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rbx
  void (__fastcall *v7)(__int64, __int128 *); // rax
  NTSTATUS DefaultClock; // eax
  unsigned int v9; // ebx
  __int128 v11; // [rsp+40h] [rbp-58h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      83,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
  }
  v3 = *(_QWORD *)(*(_QWORD *)v2->Tail.Overlay.CurrentStackLocation->FileObject->RelatedFileObject->FsContext + 112LL);
  KeWaitForSingleObject(*(PVOID *)(v3 + 88), Executive, 0, 0, 0);
  v4 = *(_DWORD **)(v3 + 128);
  if ( *(_QWORD *)v4 && *(_QWORD *)(*(_QWORD *)v4 + 64LL) || (v4[26] & 0x400000) != 0 )
  {
    if ( *(_QWORD *)(v3 + 752) )
      goto LABEL_15;
    KeInitializeSpinLock((PKSPIN_LOCK)(v3 + 696));
    v5 = **(_QWORD **)(v3 + 128);
    if ( v5 && (v6 = *(_QWORD *)(v5 + 64)) != 0 )
    {
      v11 = 0;
      v7 = *(void (__fastcall **)(__int64, __int128 *))(v6 + 24);
      if ( v7 )
        v7(v3 + 128, &v11);
      DefaultClock = KsAllocateDefaultClockEx(
                       (PKSDEFAULTCLOCK *)(v3 + 752),
                       (PVOID)(v3 + 128),
                       *(PFNKSSETTIMER *)v6,
                       *(PFNKSCANCELTIMER *)(v6 + 8),
                       *(PFNKSCORRELATEDTIME *)(v6 + 16),
                       (const KSRESOLUTION *)((unsigned __int64)&v11 & -(__int64)(*(_QWORD *)(v6 + 24) != 0)),
                       0);
    }
    else
    {
      DefaultClock = KsAllocateDefaultClockEx((PKSDEFAULTCLOCK *)(v3 + 752), (PVOID)(v3 + 128), 0, 0, 0, 0, 0);
    }
    v9 = DefaultClock;
    if ( DefaultClock >= 0 )
LABEL_15:
      v9 = KsCreateDefaultClock(v2, *(PKSDEFAULTCLOCK *)(v3 + 752));
  }
  else
  {
    v9 = -1073741808;
  }
  KeReleaseMutex(*(PRKMUTEX *)(v3 + 88), 0);
  if ( v9 != 259 )
  {
    v2->IoStatus.Status = v9;
    IofCompleteRequest(v2, 0);
  }
  return v9;
}

```

## disassembly

```asm
0x18003f450  push    rbx
0x18003f452  push    rbp
0x18003f453  push    rsi
0x18003f454  push    rdi
0x18003f455  push    r14
0x18003f457  push    r15
0x18003f459  sub     rsp, 68h
0x18003f45d  mov     rax, cs:__security_cookie
0x18003f464  xor     rax, rsp
0x18003f467  mov     [rsp+98h+var_48], rax
0x18003f46c  mov     rdi, rdx
0x18003f46f  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f476  xor     r15d, r15d
0x18003f479  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f480  jz      short loc_18003F4AF
0x18003f482  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f489  cmp     [rcx+48h], r15w
0x18003f48e  jz      short loc_18003F4AF
0x18003f490  mov     rcx, [rcx+40h]
0x18003f494  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18003f49b  lea     r9d, [r15+53h]
0x18003f49f  mov     [rsp+98h+Timeout], rax
0x18003f4a4  lea     r8d, [r15+1]
0x18003f4a8  mov     dl, 5
0x18003f4aa  call    WPP_RECORDER_SF_
0x18003f4af  mov     rax, [rdi+0B8h]
0x18003f4b6  xor     r9d, r9d; Alertable
0x18003f4b9  xor     r8d, r8d; WaitMode
0x18003f4bc  mov     [rsp+98h+Timeout], r15; Timeout
0x18003f4c1  xor     edx, edx; WaitReason
0x18003f4c3  mov     rcx, [rax+30h]
0x18003f4c7  mov     rax, [rcx+40h]
0x18003f4cb  mov     rcx, [rax+18h]
0x18003f4cf  mov     rax, [rcx]
0x18003f4d2  mov     rbp, [rax+70h]
0x18003f4d6  mov     rcx, [rbp+58h]; Object
0x18003f4da  call    cs:__imp_KeWaitForSingleObject
0x18003f4e1  nop     dword ptr [rax+rax+00h]
0x18003f4e6  lea     r14, [rbp+80h]
0x18003f4ed  mov     rcx, [r14]
0x18003f4f0  mov     rax, [rcx]
0x18003f4f3  test    rax, rax
0x18003f4f6  jz      short loc_18003F4FE
0x18003f4f8  cmp     [rax+40h], r15
0x18003f4fc  jnz     short loc_18003F50B
0x18003f4fe  test    dword ptr [rcx+68h], 400000h
0x18003f505  jz      loc_18003F5C3
0x18003f50b  lea     rsi, [rbp+2F0h]
0x18003f512  cmp     [rsi], r15
0x18003f515  jnz     loc_18003F5B4
0x18003f51b  lea     rcx, [rbp+2B8h]; SpinLock
0x18003f522  call    cs:__imp_KeInitializeSpinLock
0x18003f529  nop     dword ptr [rax+rax+00h]
0x18003f52e  mov     rax, [r14]
0x18003f531  mov     rbx, [rax]
0x18003f534  test    rbx, rbx
0x18003f537  jz      short loc_18003F58E
0x18003f539  mov     rbx, [rbx+40h]
0x18003f53d  test    rbx, rbx
0x18003f540  jz      short loc_18003F58E
0x18003f542  xorps   xmm0, xmm0
0x18003f545  movups  [rsp+98h+var_58], xmm0
0x18003f54a  mov     rax, [rbx+18h]
0x18003f54e  test    rax, rax
0x18003f551  jz      short loc_18003F560
0x18003f553  lea     rdx, [rsp+98h+var_58]
0x18003f558  mov     rcx, r14
0x18003f55b  call    _guard_dispatch_icall
0x18003f560  mov     rax, [rbx+18h]
0x18003f564  mov     r9, [rbx+8]
0x18003f568  neg     rax
0x18003f56b  mov     r8, [rbx]
0x18003f56e  lea     rax, [rsp+98h+var_58]
0x18003f573  mov     [rsp+98h+Flags], r15d
0x18003f578  sbb     rcx, rcx
0x18003f57b  and     rcx, rax
0x18003f57e  mov     rax, [rbx+10h]
0x18003f582  mov     [rsp+98h+Resolution], rcx
0x18003f587  mov     [rsp+98h+Timeout], rax
0x18003f58c  jmp     short loc_18003F5A3
0x18003f58e  mov     [rsp+98h+Flags], r15d; Flags
0x18003f593  xor     r9d, r9d; CancelTimer
0x18003f596  mov     [rsp+98h+Resolution], r15; Resolution
0x18003f59b  xor     r8d, r8d; SetTimer
0x18003f59e  mov     [rsp+98h+Timeout], r15; CorrelatedTime
0x18003f5a3  mov     rdx, r14; Context
0x18003f5a6  mov     rcx, rsi; DefaultClock
0x18003f5a9  call    KsAllocateDefaultClockEx
0x18003f5ae  mov     ebx, eax
0x18003f5b0  test    eax, eax
0x18003f5b2  js      short loc_18003F5C8
0x18003f5b4  mov     rdx, [rsi]; DefaultClock
0x18003f5b7  mov     rcx, rdi; Irp
0x18003f5ba  call    KsCreateDefaultClock
0x18003f5bf  mov     ebx, eax
0x18003f5c1  jmp     short loc_18003F5C8
0x18003f5c3  mov     ebx, 0C0000010h
0x18003f5c8  mov     rcx, [rbp+58h]; Mutex
0x18003f5cc  xor     edx, edx; Wait
0x18003f5ce  call    cs:__imp_KeReleaseMutex
0x18003f5d5  nop     dword ptr [rax+rax+00h]
0x18003f5da  cmp     ebx, 103h
0x18003f5e0  jz      short loc_18003F5F6
0x18003f5e2  xor     edx, edx; PriorityBoost
0x18003f5e4  mov     [rdi+30h], ebx
0x18003f5e7  mov     rcx, rdi; Irp
0x18003f5ea  call    cs:__imp_IofCompleteRequest
0x18003f5f1  nop     dword ptr [rax+rax+00h]
0x18003f5f6  mov     eax, ebx
0x18003f5f8  mov     rcx, [rsp+98h+var_48]
0x18003f5fd  xor     rcx, rsp; StackCookie
0x18003f600  call    __security_check_cookie
0x18003f605  add     rsp, 68h
0x18003f609  pop     r15
0x18003f60b  pop     r14
0x18003f60d  pop     rdi
0x18003f60e  pop     rsi
0x18003f60f  pop     rbp
0x18003f610  pop     rbx
0x18003f611  retn
```
