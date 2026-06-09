# CKsPin::DispatchCreateClock(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003f440`
- end: `0x18003f603`
- name: `?DispatchCreateClock@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x180019bd0`
- `0x180019cb0`
- `0x1800370e0`
- `0x180037310`
- `0x18003f440`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003f5be`
- `ntoskrnl!KeReleaseMutex` at `0x18003f5be`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003f512`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003f512`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f4ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f4ca`
- `ntoskrnl!IofCompleteRequest` at `0x18003f5da`
- `ntoskrnl!IofCompleteRequest` at `0x18003f5da`

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
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
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
0x18003f440  push    rbx
0x18003f442  push    rbp
0x18003f443  push    rsi
0x18003f444  push    rdi
0x18003f445  push    r14
0x18003f447  push    r15
0x18003f449  sub     rsp, 68h
0x18003f44d  mov     rax, cs:__security_cookie
0x18003f454  xor     rax, rsp
0x18003f457  mov     [rsp+98h+var_48], rax
0x18003f45c  mov     rdi, rdx
0x18003f45f  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f466  xor     r15d, r15d
0x18003f469  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f470  jz      short loc_18003F49F
0x18003f472  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f479  cmp     [rcx+48h], r15w
0x18003f47e  jz      short loc_18003F49F
0x18003f480  mov     rcx, [rcx+40h]
0x18003f484  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18003f48b  lea     r9d, [r15+53h]
0x18003f48f  mov     [rsp+98h+Timeout], rax
0x18003f494  lea     r8d, [r15+1]
0x18003f498  mov     dl, 5
0x18003f49a  call    WPP_RECORDER_SF_
0x18003f49f  mov     rax, [rdi+0B8h]
0x18003f4a6  xor     r9d, r9d; Alertable
0x18003f4a9  xor     r8d, r8d; WaitMode
0x18003f4ac  mov     [rsp+98h+Timeout], r15; Timeout
0x18003f4b1  xor     edx, edx; WaitReason
0x18003f4b3  mov     rcx, [rax+30h]
0x18003f4b7  mov     rax, [rcx+40h]
0x18003f4bb  mov     rcx, [rax+18h]
0x18003f4bf  mov     rax, [rcx]
0x18003f4c2  mov     rbp, [rax+70h]
0x18003f4c6  mov     rcx, [rbp+58h]; Object
0x18003f4ca  call    cs:__imp_KeWaitForSingleObject
0x18003f4d1  nop     dword ptr [rax+rax+00h]
0x18003f4d6  lea     r14, [rbp+80h]
0x18003f4dd  mov     rcx, [r14]
0x18003f4e0  mov     rax, [rcx]
0x18003f4e3  test    rax, rax
0x18003f4e6  jz      short loc_18003F4EE
0x18003f4e8  cmp     [rax+40h], r15
0x18003f4ec  jnz     short loc_18003F4FB
0x18003f4ee  test    dword ptr [rcx+68h], 400000h
0x18003f4f5  jz      loc_18003F5B3
0x18003f4fb  lea     rsi, [rbp+2F0h]
0x18003f502  cmp     [rsi], r15
0x18003f505  jnz     loc_18003F5A4
0x18003f50b  lea     rcx, [rbp+2B8h]; SpinLock
0x18003f512  call    cs:__imp_KeInitializeSpinLock
0x18003f519  nop     dword ptr [rax+rax+00h]
0x18003f51e  mov     rax, [r14]
0x18003f521  mov     rbx, [rax]
0x18003f524  test    rbx, rbx
0x18003f527  jz      short loc_18003F57E
0x18003f529  mov     rbx, [rbx+40h]
0x18003f52d  test    rbx, rbx
0x18003f530  jz      short loc_18003F57E
0x18003f532  xorps   xmm0, xmm0
0x18003f535  movups  [rsp+98h+var_58], xmm0
0x18003f53a  mov     rax, [rbx+18h]
0x18003f53e  test    rax, rax
0x18003f541  jz      short loc_18003F550
0x18003f543  lea     rdx, [rsp+98h+var_58]
0x18003f548  mov     rcx, r14
0x18003f54b  call    _guard_dispatch_icall
0x18003f550  mov     rax, [rbx+18h]
0x18003f554  mov     r9, [rbx+8]
0x18003f558  neg     rax
0x18003f55b  mov     r8, [rbx]
0x18003f55e  lea     rax, [rsp+98h+var_58]
0x18003f563  mov     [rsp+98h+Flags], r15d
0x18003f568  sbb     rcx, rcx
0x18003f56b  and     rcx, rax
0x18003f56e  mov     rax, [rbx+10h]
0x18003f572  mov     [rsp+98h+Resolution], rcx
0x18003f577  mov     [rsp+98h+Timeout], rax
0x18003f57c  jmp     short loc_18003F593
0x18003f57e  mov     [rsp+98h+Flags], r15d; Flags
0x18003f583  xor     r9d, r9d; CancelTimer
0x18003f586  mov     [rsp+98h+Resolution], r15; Resolution
0x18003f58b  xor     r8d, r8d; SetTimer
0x18003f58e  mov     [rsp+98h+Timeout], r15; CorrelatedTime
0x18003f593  mov     rdx, r14; Context
0x18003f596  mov     rcx, rsi; DefaultClock
0x18003f599  call    KsAllocateDefaultClockEx
0x18003f59e  mov     ebx, eax
0x18003f5a0  test    eax, eax
0x18003f5a2  js      short loc_18003F5B8
0x18003f5a4  mov     rdx, [rsi]; DefaultClock
0x18003f5a7  mov     rcx, rdi; Irp
0x18003f5aa  call    KsCreateDefaultClock
0x18003f5af  mov     ebx, eax
0x18003f5b1  jmp     short loc_18003F5B8
0x18003f5b3  mov     ebx, 0C0000010h
0x18003f5b8  mov     rcx, [rbp+58h]; Mutex
0x18003f5bc  xor     edx, edx; Wait
0x18003f5be  call    cs:__imp_KeReleaseMutex
0x18003f5c5  nop     dword ptr [rax+rax+00h]
0x18003f5ca  cmp     ebx, 103h
0x18003f5d0  jz      short loc_18003F5E6
0x18003f5d2  xor     edx, edx; PriorityBoost
0x18003f5d4  mov     [rdi+30h], ebx
0x18003f5d7  mov     rcx, rdi; Irp
0x18003f5da  call    cs:__imp_IofCompleteRequest
0x18003f5e1  nop     dword ptr [rax+rax+00h]
0x18003f5e6  mov     eax, ebx
0x18003f5e8  mov     rcx, [rsp+98h+var_48]
0x18003f5ed  xor     rcx, rsp; StackCookie
0x18003f5f0  call    __security_check_cookie
0x18003f5f5  add     rsp, 68h
0x18003f5f9  pop     r15
0x18003f5fb  pop     r14
0x18003f5fd  pop     rdi
0x18003f5fe  pop     rsi
0x18003f5ff  pop     rbp
0x18003f600  pop     rbx
0x18003f601  retn
```
