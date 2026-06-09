# ACMoveQueueToGroup

- ea: `0x140006fd8`
- end: `0x140007133`
- name: `ACMoveQueueToGroup`
- size: `347`
- prototype: `__int64 __fastcall(struct CQueueBase *, HANDLE Handle)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x140006fd8`
- `0x14000968c`
- `0x14000b5d8`
- `0x14001a09c`
- `0x14001a564`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140007094`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140007094`
- `ntoskrnl!IoFileObjectType` at `0x140007063`

## pseudocode

```c
__int64 __fastcall ACMoveQueueToGroup(struct CQueueBase *a1, HANDLE Handle)
{
  int v4; // edi
  NTSTATUS v6; // eax
  PVOID v7; // rdi
  PVOID Object; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 97, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
  }
  v4 = CQueueBase::Validate(a1);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 98, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
    }
    return (unsigned int)v4;
  }
  if ( Handle )
  {
    Object = 0;
    v6 = ObReferenceObjectByHandle(Handle, 1u, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_Dq(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          99,
          WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
          (unsigned int)v6,
          a1);
      }
      return (unsigned int)v4;
    }
    v7 = Object;
    Handle = (HANDLE)*((_QWORD *)Object + 3);
  }
  else
  {
    v7 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 100, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, Handle);
  }
  CQueueBase::MoveToGroup(a1, (struct CGroup *)Handle);
  ACpObDereferenceObject(v7);
  return 0;
}

```

## disassembly

```asm
0x140006fd8  push    rbx
0x140006fda  push    rbp
0x140006fdb  push    rsi
0x140006fdc  push    rdi
0x140006fdd  sub     rsp, 38h
0x140006fe1  mov     rsi, rdx
0x140006fe4  mov     rbx, rcx
0x140006fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x140006fee  lea     rbp, WPP_GLOBAL_Control
0x140006ff5  cmp     rcx, rbp
0x140006ff8  jz      short loc_140007019
0x140006ffa  mov     eax, [rcx+6Ch]
0x140006ffd  test    al, 4
0x140006fff  jz      short loc_140007019
0x140007001  mov     rcx, [rcx+58h]
0x140007005  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000700c  mov     edx, 61h ; 'a'
0x140007011  mov     r9, rbx
0x140007014  call    WPP_SF_q
0x140007019  mov     rcx, rbx; struct CQueueBase *
0x14000701c  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140007021  mov     edi, eax
0x140007023  test    eax, eax
0x140007025  jns     short loc_14000705A
0x140007027  mov     rcx, cs:WPP_GLOBAL_Control
0x14000702e  cmp     rcx, rbp
0x140007031  jz      short loc_140007053
0x140007033  mov     edx, [rcx+6Ch]
0x140007036  test    dl, 1
0x140007039  jz      short loc_140007053
0x14000703b  mov     rcx, [rcx+58h]
0x14000703f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140007046  mov     edx, 62h ; 'b'
0x14000704b  mov     r9, rbx
0x14000704e  call    WPP_SF_q
0x140007053  mov     eax, edi
0x140007055  jmp     loc_140007129
0x14000705a  test    rsi, rsi
0x14000705d  jz      loc_1400070E7
0x140007063  mov     r8, cs:__imp_IoFileObjectType
0x14000706a  lea     rax, [rsp+58h+arg_10]
0x14000706f  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x140007078  mov     r9b, 1; AccessMode
0x14000707b  mov     edx, 1; DesiredAccess
0x140007080  mov     [rsp+58h+arg_10], 0
0x140007089  mov     rcx, rsi; Handle
0x14000708c  mov     [rsp+58h+Object], rax; Object
0x140007091  mov     r8, [r8]; ObjectType
0x140007094  call    cs:__imp_ObReferenceObjectByHandle
0x14000709b  nop     dword ptr [rax+rax+00h]
0x1400070a0  mov     edi, eax
0x1400070a2  test    eax, eax
0x1400070a4  jns     short loc_1400070DC
0x1400070a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070ad  cmp     rcx, rbp
0x1400070b0  jz      short loc_140007053
0x1400070b2  mov     edx, [rcx+6Ch]
0x1400070b5  test    dl, 1
0x1400070b8  jz      short loc_140007053
0x1400070ba  mov     rcx, [rcx+58h]
0x1400070be  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400070c5  mov     edx, 63h ; 'c'
0x1400070ca  mov     [rsp+58h+Object], rbx
0x1400070cf  mov     r9d, eax
0x1400070d2  call    WPP_SF_Dq
0x1400070d7  jmp     loc_140007053
0x1400070dc  mov     rdi, [rsp+58h+arg_10]
0x1400070e1  mov     rsi, [rdi+18h]
0x1400070e5  jmp     short loc_1400070E9
0x1400070e7  xor     edi, edi
0x1400070e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070f0  cmp     rcx, rbp
0x1400070f3  jz      short loc_140007114
0x1400070f5  mov     eax, [rcx+6Ch]
0x1400070f8  test    al, 4
0x1400070fa  jz      short loc_140007114
0x1400070fc  mov     rcx, [rcx+58h]
0x140007100  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140007107  mov     edx, 64h ; 'd'
0x14000710c  mov     r9, rsi
0x14000710f  call    WPP_SF_q
0x140007114  mov     rdx, rsi; struct CGroup *
0x140007117  mov     rcx, rbx; this
0x14000711a  call    ?MoveToGroup@CQueueBase@@QEAAXPEAVCGroup@@@Z; CQueueBase::MoveToGroup(CGroup *)
0x14000711f  mov     rcx, rdi; void *
0x140007122  call    ?ACpObDereferenceObject@@YAXPEAX@Z; ACpObDereferenceObject(void *)
0x140007127  xor     eax, eax
0x140007129  add     rsp, 38h
0x14000712d  pop     rdi
0x14000712e  pop     rsi
0x14000712f  pop     rbp
0x140007130  pop     rbx
0x140007131  retn
```
