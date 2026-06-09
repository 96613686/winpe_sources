# NbtCancelLmhSvcIrp

- ea: `0x1400214c0`
- end: `0x1400215fd`
- name: `NbtCancelLmhSvcIrp`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400214c0`
- `0x14004025c`
- `0x140040294`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140021566`
- `ntoskrnl!IofCompleteRequest` at `0x140021566`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400214d0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400214d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400214e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400214e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002150d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021555`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002150d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021555`

## pseudocode

```c
void __fastcall NbtCancelLmhSvcIrp(__int64 a1, IRP *a2)
{
  KIRQL v3; // al
  KIRQL v4; // si
  __int64 *v5; // rax

  IoReleaseCancelSpinLock(a2->CancelIrql);
  v3 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v4 = v3;
  if ( a2 == (IRP *)CheckAddr )
  {
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    {
      WPP_SF_(1049, 86, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
      if ( (BYTE3(xmmword_140038420) & 2) != 0 )
        WPP_SF_q(1049, 87, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, a2);
    }
    v5 = &CheckAddr;
  }
  else
  {
    if ( a2 != (IRP *)DnsQueries )
    {
      KeReleaseSpinLock(&SpinLock, v3);
      return;
    }
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    {
      WPP_SF_(1049, 88, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
      if ( (BYTE3(xmmword_140038420) & 2) != 0 )
        WPP_SF_q(1049, 89, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, a2);
    }
    v5 = &DnsQueries;
  }
  a2->IoStatus.Status = -1073741536;
  *v5 = 0;
  v5[4] = 0;
  KeReleaseSpinLock(&SpinLock, v4);
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x1400214c0  mov     [rsp+arg_0], rbx
0x1400214c5  push    rsi
0x1400214c6  sub     rsp, 20h
0x1400214ca  mov     cl, [rdx+45h]; Irql
0x1400214cd  mov     rbx, rdx
0x1400214d0  call    cs:__imp_IoReleaseCancelSpinLock
0x1400214d7  nop     dword ptr [rax+rax+00h]
0x1400214dc  lea     rcx, SpinLock; SpinLock
0x1400214e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400214ea  nop     dword ptr [rax+rax+00h]
0x1400214ef  cmp     rbx, cs:CheckAddr
0x1400214f6  mov     sil, al
0x1400214f9  jz      short loc_140021525
0x1400214fb  cmp     rbx, cs:DnsQueries
0x140021502  jz      short loc_140021574
0x140021504  mov     dl, al; NewIrql
0x140021506  lea     rcx, SpinLock; SpinLock
0x14002150d  call    cs:__imp_KeReleaseSpinLock
0x140021514  nop     dword ptr [rax+rax+00h]
0x140021519  mov     rbx, [rsp+28h+arg_0]
0x14002151e  add     rsp, 20h
0x140021522  pop     rsi
0x140021523  retn
0x140021525  test    byte ptr cs:xmmword_140038420+3, 2
0x14002152c  jnz     short loc_140021586
0x14002152e  lea     rax, CheckAddr
0x140021535  mov     dword ptr [rbx+30h], 0C0000120h
0x14002153c  lea     rcx, SpinLock; SpinLock
0x140021543  mov     dl, sil; NewIrql
0x140021546  mov     qword ptr [rax], 0
0x14002154d  mov     qword ptr [rax+20h], 0
0x140021555  call    cs:__imp_KeReleaseSpinLock
0x14002155c  nop     dword ptr [rax+rax+00h]
0x140021561  mov     dl, 2; PriorityBoost
0x140021563  mov     rcx, rbx; Irp
0x140021566  call    cs:__imp_IofCompleteRequest
0x14002156d  nop     dword ptr [rax+rax+00h]
0x140021572  jmp     short loc_140021519
0x140021574  test    byte ptr cs:xmmword_140038420+3, 2
0x14002157b  jnz     short loc_1400215C3
0x14002157d  lea     rax, DnsQueries
0x140021584  jmp     short loc_140021535
0x140021586  mov     edx, 56h ; 'V'
0x14002158b  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140021592  mov     ecx, 419h
0x140021597  call    WPP_SF_
0x14002159c  test    byte ptr cs:xmmword_140038420+3, 2
0x1400215a3  jz      short loc_14002152E
0x1400215a5  mov     edx, 57h ; 'W'
0x1400215aa  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x1400215b1  mov     ecx, 419h
0x1400215b6  mov     r9, rbx
0x1400215b9  call    WPP_SF_q
0x1400215be  jmp     loc_14002152E
0x1400215c3  mov     edx, 58h ; 'X'
0x1400215c8  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x1400215cf  mov     ecx, 419h
0x1400215d4  call    WPP_SF_
0x1400215d9  test    byte ptr cs:xmmword_140038420+3, 2
0x1400215e0  jz      short loc_14002157D
0x1400215e2  mov     edx, 59h ; 'Y'
0x1400215e7  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x1400215ee  mov     ecx, 419h
0x1400215f3  mov     r9, rbx
0x1400215f6  call    WPP_SF_q
0x1400215fb  jmp     short loc_14002157D
```
