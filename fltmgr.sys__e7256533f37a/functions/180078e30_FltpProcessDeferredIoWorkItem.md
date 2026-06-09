# FltpProcessDeferredIoWorkItem

- ea: `0x180078e30`
- end: `0x180078f7f`
- name: `FltpProcessDeferredIoWorkItem`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009f20`
- `0x180010400`
- `0x1800147b0`
- `0x180024800`
- `0x1800248e0`
- `0x180078e30`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180078e62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180078e62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180078f55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180078f55`
- `ntoskrnl!IoClearActivityIdThread` at `0x180078f0a`
- `ntoskrnl!IoClearActivityIdThread` at `0x180078f0a`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078ec8`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078f41`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078ec8`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078f41`
- `ntoskrnl!IoSetActivityIdThread` at `0x180078ee4`
- `ntoskrnl!IoSetActivityIdThread` at `0x180078ee4`

## pseudocode

```c
void __fastcall FltpProcessDeferredIoWorkItem(__int64 a1)
{
  int v2; // ecx
  void *v3; // rbp
  unsigned int v4; // edi
  __int64 v5; // rbx
  __int128 v6; // [rsp+50h] [rbp-68h] BYREF
  struct _IO_PRIORITY_INFO OutputPriorityInfo; // [rsp+60h] [rbp-58h] BYREF

  OutputPriorityInfo = 0;
  v6 = 0;
  KeEnterCriticalRegion();
  v3 = *(void **)(a1 + 96);
  if ( (byte_180040A44 & 1) != 0 )
    McTemplateU0spdpppd_EtwWriteTransfer(
      v2,
      (unsigned int)WorkSup_c585,
      (unsigned int)"FltpProcessDeferredIoWorkItem",
      a1,
      *(_DWORD *)(a1 + 40),
      (char)v3,
      *(_QWORD *)(a1 + 48),
      *(_QWORD *)(a1 + 56),
      *(_DWORD *)(a1 + 76));
  v4 = IoApplyPriorityInfoThread((PIO_PRIORITY_INFO)(a1 + 64), &OutputPriorityInfo, KeGetCurrentThread());
  v6 = *(_OWORD *)(a1 + 80);
  v5 = IoSetActivityIdThread(&v6);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(a1 + 48))(a1, *(_QWORD *)(a1 + 104), *(_QWORD *)(a1 + 56));
  IoClearActivityIdThread(v5);
  if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\worksup.c", 633, 0) >= 0 )
    IoApplyPriorityInfoThread(&OutputPriorityInfo, 0, KeGetCurrentThread());
  FltObjectDereference(v3);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x180078e30  push    rbx
0x180078e32  push    rbp
0x180078e33  push    rsi
0x180078e34  push    rdi
0x180078e35  push    r14
0x180078e37  push    r15
0x180078e39  sub     rsp, 88h
0x180078e40  mov     rax, cs:__security_cookie
0x180078e47  xor     rax, rsp
0x180078e4a  mov     [rsp+0B8h+var_48], rax
0x180078e4f  xorps   xmm0, xmm0
0x180078e52  xorps   xmm1, xmm1
0x180078e55  movups  xmmword ptr [rsp+0B8h+OutputPriorityInfo.Size], xmm0
0x180078e5a  mov     rsi, rcx
0x180078e5d  movups  [rsp+0B8h+var_68], xmm1
0x180078e62  call    cs:__imp_KeEnterCriticalRegion
0x180078e69  nop     dword ptr [rax+rax+00h]
0x180078e6e  test    cs:byte_180040A44, 1
0x180078e75  mov     rbp, [rsi+60h]
0x180078e79  jz      short loc_180078EB6
0x180078e7b  mov     eax, [rsi+4Ch]
0x180078e7e  lea     r8, aFltpprocessdef; "FltpProcessDeferredIoWorkItem"
0x180078e85  mov     [rsp+0B8h+var_78], eax
0x180078e89  lea     rdx, WorkSup_c585
0x180078e90  mov     rax, [rsi+38h]
0x180078e94  mov     r9, rsi
0x180078e97  mov     [rsp+0B8h+var_80], rax
0x180078e9c  mov     rax, [rsi+30h]
0x180078ea0  mov     [rsp+0B8h+var_88], rax
0x180078ea5  mov     eax, [rsi+28h]
0x180078ea8  mov     [rsp+0B8h+var_90], rbp
0x180078ead  mov     [rsp+0B8h+var_98], eax
0x180078eb1  call    McTemplateU0spdpppd_EtwWriteTransfer
0x180078eb6  mov     r8, gs:188h; Thread
0x180078ebf  lea     rcx, [rsi+40h]; InputPriorityInfo
0x180078ec3  lea     rdx, [rsp+0B8h+OutputPriorityInfo]; OutputPriorityInfo
0x180078ec8  call    cs:__imp_IoApplyPriorityInfoThread
0x180078ecf  nop     dword ptr [rax+rax+00h]
0x180078ed4  movups  xmm0, xmmword ptr [rsi+50h]
0x180078ed8  lea     rcx, [rsp+0B8h+var_68]
0x180078edd  mov     edi, eax
0x180078edf  movups  [rsp+0B8h+var_68], xmm0
0x180078ee4  call    cs:__imp_IoSetActivityIdThread
0x180078eeb  nop     dword ptr [rax+rax+00h]
0x180078ef0  mov     r8, [rsi+38h]
0x180078ef4  mov     rcx, rsi
0x180078ef7  mov     rdx, [rsi+68h]
0x180078efb  mov     rbx, rax
0x180078efe  mov     rax, [rsi+30h]
0x180078f02  call    _guard_dispatch_icall
0x180078f07  mov     rcx, rbx
0x180078f0a  call    cs:__imp_IoClearActivityIdThread
0x180078f11  nop     dword ptr [rax+rax+00h]
0x180078f16  mov     r8d, 279h
0x180078f1c  lea     rdx, aMinkernelFsFil_5; "minkernel\\fs\\filtermgr\\filter\\works"...
0x180078f23  xor     r9d, r9d
0x180078f26  mov     ecx, edi
0x180078f28  call    FltpDbgStatus
0x180078f2d  test    eax, eax
0x180078f2f  js      short loc_180078F4D
0x180078f31  mov     r8, gs:188h; Thread
0x180078f3a  lea     rcx, [rsp+0B8h+OutputPriorityInfo]; InputPriorityInfo
0x180078f3f  xor     edx, edx; OutputPriorityInfo
0x180078f41  call    cs:__imp_IoApplyPriorityInfoThread
0x180078f48  nop     dword ptr [rax+rax+00h]
0x180078f4d  mov     rcx, rbp; FltObject
0x180078f50  call    FltObjectDereference
0x180078f55  call    cs:__imp_KeLeaveCriticalRegion
0x180078f5c  nop     dword ptr [rax+rax+00h]
0x180078f61  mov     rcx, [rsp+0B8h+var_48]
0x180078f66  xor     rcx, rsp; StackCookie
0x180078f69  call    __security_check_cookie
0x180078f6e  add     rsp, 88h
0x180078f75  pop     r15
0x180078f77  pop     r14
0x180078f79  pop     rdi
0x180078f7a  pop     rsi
0x180078f7b  pop     rbp
0x180078f7c  pop     rbx
0x180078f7d  retn
```
