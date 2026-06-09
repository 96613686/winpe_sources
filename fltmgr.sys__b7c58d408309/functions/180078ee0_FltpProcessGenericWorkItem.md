# FltpProcessGenericWorkItem

- ea: `0x180078ee0`
- end: `0x18007902e`
- name: `FltpProcessGenericWorkItem`
- size: `334`
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
- `0x180078ee0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180078f12`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180078f12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180079004`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180079004`
- `ntoskrnl!IoClearActivityIdThread` at `0x180078fb9`
- `ntoskrnl!IoClearActivityIdThread` at `0x180078fb9`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078f78`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078ff0`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078f78`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180078ff0`
- `ntoskrnl!IoSetActivityIdThread` at `0x180078f94`
- `ntoskrnl!IoSetActivityIdThread` at `0x180078f94`

## pseudocode

```c
void __fastcall FltpProcessGenericWorkItem(__int64 a1)
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
      (__int64)WorkSup_c464,
      "FltpProcessGenericWorkItem",
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
  (*(void (__fastcall **)(__int64, void *, _QWORD))(a1 + 48))(a1, v3, *(_QWORD *)(a1 + 56));
  IoClearActivityIdThread(v5);
  if ( (int)FltpDbgStatus(v4) >= 0 )
    IoApplyPriorityInfoThread(&OutputPriorityInfo, 0, KeGetCurrentThread());
  FltObjectDereference(v3);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x180078ee0  push    rbx
0x180078ee2  push    rbp
0x180078ee3  push    rsi
0x180078ee4  push    rdi
0x180078ee5  push    r14
0x180078ee7  push    r15
0x180078ee9  sub     rsp, 88h
0x180078ef0  mov     rax, cs:__security_cookie
0x180078ef7  xor     rax, rsp
0x180078efa  mov     [rsp+0B8h+var_48], rax
0x180078eff  xorps   xmm0, xmm0
0x180078f02  xorps   xmm1, xmm1
0x180078f05  movups  xmmword ptr [rsp+0B8h+OutputPriorityInfo.Size], xmm0
0x180078f0a  mov     rsi, rcx
0x180078f0d  movups  [rsp+0B8h+var_68], xmm1
0x180078f12  call    cs:__imp_KeEnterCriticalRegion
0x180078f19  nop     dword ptr [rax+rax+00h]
0x180078f1e  test    cs:byte_1800404C4, 1
0x180078f25  mov     rbp, [rsi+60h]
0x180078f29  jz      short loc_180078F66
0x180078f2b  mov     eax, [rsi+4Ch]
0x180078f2e  lea     r8, aFltpprocessgen; "FltpProcessGenericWorkItem"
0x180078f35  mov     [rsp+0B8h+var_78], eax
0x180078f39  lea     rdx, WorkSup_c464
0x180078f40  mov     rax, [rsi+38h]
0x180078f44  mov     r9, rsi
0x180078f47  mov     [rsp+0B8h+var_80], rax
0x180078f4c  mov     rax, [rsi+30h]
0x180078f50  mov     [rsp+0B8h+var_88], rax
0x180078f55  mov     eax, [rsi+28h]
0x180078f58  mov     [rsp+0B8h+var_90], rbp
0x180078f5d  mov     [rsp+0B8h+var_98], eax
0x180078f61  call    McTemplateU0spdpppd_EtwWriteTransfer
0x180078f66  mov     r8, gs:188h; Thread
0x180078f6f  lea     rcx, [rsi+40h]; InputPriorityInfo
0x180078f73  lea     rdx, [rsp+0B8h+OutputPriorityInfo]; OutputPriorityInfo
0x180078f78  call    cs:__imp_IoApplyPriorityInfoThread
0x180078f7f  nop     dword ptr [rax+rax+00h]
0x180078f84  movups  xmm0, xmmword ptr [rsi+50h]
0x180078f88  lea     rcx, [rsp+0B8h+var_68]
0x180078f8d  mov     edi, eax
0x180078f8f  movups  [rsp+0B8h+var_68], xmm0
0x180078f94  call    cs:__imp_IoSetActivityIdThread
0x180078f9b  nop     dword ptr [rax+rax+00h]
0x180078fa0  mov     r8, [rsi+38h]
0x180078fa4  mov     rdx, rbp
0x180078fa7  mov     rbx, rax
0x180078faa  mov     rcx, rsi
0x180078fad  mov     rax, [rsi+30h]
0x180078fb1  call    _guard_dispatch_icall
0x180078fb6  mov     rcx, rbx
0x180078fb9  call    cs:__imp_IoClearActivityIdThread
0x180078fc0  nop     dword ptr [rax+rax+00h]
0x180078fc5  mov     r8d, 1FFh
0x180078fcb  lea     rdx, aMinkernelFsFil_5; "minkernel\\fs\\filtermgr\\filter\\works"...
0x180078fd2  xor     r9d, r9d
0x180078fd5  mov     ecx, edi
0x180078fd7  call    FltpDbgStatus
0x180078fdc  test    eax, eax
0x180078fde  js      short loc_180078FFC
0x180078fe0  mov     r8, gs:188h; Thread
0x180078fe9  lea     rcx, [rsp+0B8h+OutputPriorityInfo]; InputPriorityInfo
0x180078fee  xor     edx, edx; OutputPriorityInfo
0x180078ff0  call    cs:__imp_IoApplyPriorityInfoThread
0x180078ff7  nop     dword ptr [rax+rax+00h]
0x180078ffc  mov     rcx, rbp; FltObject
0x180078fff  call    FltObjectDereference
0x180079004  call    cs:__imp_KeLeaveCriticalRegion
0x18007900b  nop     dword ptr [rax+rax+00h]
0x180079010  mov     rcx, [rsp+0B8h+var_48]
0x180079015  xor     rcx, rsp; StackCookie
0x180079018  call    __security_check_cookie
0x18007901d  add     rsp, 88h
0x180079024  pop     r15
0x180079026  pop     r14
0x180079028  pop     rdi
0x180079029  pop     rsi
0x18007902a  pop     rbp
0x18007902b  pop     rbx
0x18007902c  retn
```
