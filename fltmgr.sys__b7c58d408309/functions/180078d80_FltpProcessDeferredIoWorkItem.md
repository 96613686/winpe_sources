# FltpProcessDeferredIoWorkItem

- ea: `0x180078d80`
- end: `0x180078ecf`
- name: `FltpProcessDeferredIoWorkItem`
- size: `335`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009f20`
- `0x180010400`
- `0x1800147b0`
- `0x1800247a0`
- `0x180024880`
- `0x180078d80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180078db2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180078db2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180078ea5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180078ea5`
- `ntoskrnl!IoClearActivityIdThread` at `0x180078e5a`
- `ntoskrnl!IoClearActivityIdThread` at `0x180078e5a`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078e18`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078e91`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078e18`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078e91`
- `ntoskrnl!IoSetActivityIdThread` at `0x180078e34`
- `ntoskrnl!IoSetActivityIdThread` at `0x180078e34`

## pseudocode

```c
void __fastcall FltpProcessDeferredIoWorkItem(__int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rbp
  NTSTATUS v4; // edi
  __int64 v5; // rbx
  int v6; // [rsp+20h] [rbp-98h]
  int v7; // [rsp+40h] [rbp-78h]
  __int128 v8; // [rsp+50h] [rbp-68h] BYREF
  struct _IO_PRIORITY_INFO OutputPriorityInfo; // [rsp+60h] [rbp-58h] BYREF

  OutputPriorityInfo = 0;
  v8 = 0;
  KeEnterCriticalRegion();
  v3 = *(void **)(a1 + 96);
  if ( (byte_1800404C4 & 1) != 0 )
  {
    v7 = *(_DWORD *)(a1 + 76);
    v6 = *(_DWORD *)(a1 + 40);
    McTemplateU0spdpppd_EtwWriteTransfer(
      v2,
      (__int64)WorkSup_c585,
      "FltpProcessDeferredIoWorkItem",
      a1,
      v6,
      v3,
      *(_QWORD *)(a1 + 48),
      *(_QWORD *)(a1 + 56),
      v7);
  }
  v4 = IoApplyPriorityInfoThread((PIO_PRIORITY_INFO)(a1 + 64), &OutputPriorityInfo, KeGetCurrentThread());
  v8 = *(_OWORD *)(a1 + 80);
  v5 = IoSetActivityIdThread(&v8);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(a1 + 48))(a1, *(_QWORD *)(a1 + 104), *(_QWORD *)(a1 + 56));
  IoClearActivityIdThread(v5);
  if ( (int)FltpDbgStatus(v4) >= 0 )
    IoApplyPriorityInfoThread(&OutputPriorityInfo, 0, KeGetCurrentThread());
  FltObjectDereference(v3);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x180078d80  push    rbx
0x180078d82  push    rbp
0x180078d83  push    rsi
0x180078d84  push    rdi
0x180078d85  push    r14
0x180078d87  push    r15
0x180078d89  sub     rsp, 88h
0x180078d90  mov     rax, cs:__security_cookie
0x180078d97  xor     rax, rsp
0x180078d9a  mov     [rsp+0B8h+var_48], rax
0x180078d9f  xorps   xmm0, xmm0
0x180078da2  xorps   xmm1, xmm1
0x180078da5  movups  xmmword ptr [rsp+0B8h+OutputPriorityInfo.Size], xmm0
0x180078daa  mov     rsi, rcx
0x180078dad  movups  [rsp+0B8h+var_68], xmm1
0x180078db2  call    cs:__imp_KeEnterCriticalRegion
0x180078db9  nop     dword ptr [rax+rax+00h]
0x180078dbe  test    cs:byte_1800404C4, 1
0x180078dc5  mov     rbp, [rsi+60h]
0x180078dc9  jz      short loc_180078E06
0x180078dcb  mov     eax, [rsi+4Ch]
0x180078dce  lea     r8, aFltpprocessdef; "FltpProcessDeferredIoWorkItem"
0x180078dd5  mov     [rsp+0B8h+var_78], eax
0x180078dd9  lea     rdx, WorkSup_c585
0x180078de0  mov     rax, [rsi+38h]
0x180078de4  mov     r9, rsi
0x180078de7  mov     [rsp+0B8h+var_80], rax
0x180078dec  mov     rax, [rsi+30h]
0x180078df0  mov     [rsp+0B8h+var_88], rax
0x180078df5  mov     eax, [rsi+28h]
0x180078df8  mov     [rsp+0B8h+var_90], rbp
0x180078dfd  mov     [rsp+0B8h+var_98], eax
0x180078e01  call    McTemplateU0spdpppd_EtwWriteTransfer
0x180078e06  mov     r8, gs:188h; Thread
0x180078e0f  lea     rcx, [rsi+40h]; InputPriorityInfo
0x180078e13  lea     rdx, [rsp+0B8h+OutputPriorityInfo]; OutputPriorityInfo
0x180078e18  call    cs:__imp_IoApplyPriorityInfoThread
0x180078e1f  nop     dword ptr [rax+rax+00h]
0x180078e24  movups  xmm0, xmmword ptr [rsi+50h]
0x180078e28  lea     rcx, [rsp+0B8h+var_68]
0x180078e2d  mov     edi, eax
0x180078e2f  movups  [rsp+0B8h+var_68], xmm0
0x180078e34  call    cs:__imp_IoSetActivityIdThread
0x180078e3b  nop     dword ptr [rax+rax+00h]
0x180078e40  mov     r8, [rsi+38h]
0x180078e44  mov     rcx, rsi
0x180078e47  mov     rdx, [rsi+68h]
0x180078e4b  mov     rbx, rax
0x180078e4e  mov     rax, [rsi+30h]
0x180078e52  call    _guard_dispatch_icall
0x180078e57  mov     rcx, rbx
0x180078e5a  call    cs:__imp_IoClearActivityIdThread
0x180078e61  nop     dword ptr [rax+rax+00h]
0x180078e66  mov     r8d, 279h
0x180078e6c  lea     rdx, aMinkernelFsFil_5; "minkernel\\fs\\filtermgr\\filter\\works"...
0x180078e73  xor     r9d, r9d
0x180078e76  mov     ecx, edi
0x180078e78  call    FltpDbgStatus
0x180078e7d  test    eax, eax
0x180078e7f  js      short loc_180078E9D
0x180078e81  mov     r8, gs:188h; Thread
0x180078e8a  lea     rcx, [rsp+0B8h+OutputPriorityInfo]; InputPriorityInfo
0x180078e8f  xor     edx, edx; OutputPriorityInfo
0x180078e91  call    cs:__imp_IoApplyPriorityInfoThread
0x180078e98  nop     dword ptr [rax+rax+00h]
0x180078e9d  mov     rcx, rbp; FltObject
0x180078ea0  call    FltObjectDereference
0x180078ea5  call    cs:__imp_KeLeaveCriticalRegion
0x180078eac  nop     dword ptr [rax+rax+00h]
0x180078eb1  mov     rcx, [rsp+0B8h+var_48]
0x180078eb6  xor     rcx, rsp; StackCookie
0x180078eb9  call    __security_check_cookie
0x180078ebe  add     rsp, 88h
0x180078ec5  pop     r15
0x180078ec7  pop     r14
0x180078ec9  pop     rdi
0x180078eca  pop     rsi
0x180078ecb  pop     rbp
0x180078ecc  pop     rbx
0x180078ecd  retn
```
