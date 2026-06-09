# ACCompleteRemoteRequest

- ea: `0x140004afc`
- end: `0x140004bbc`
- name: `ACCompleteRemoteRequest`
- size: `192`
- prototype: `__int64 __fastcall(CQueueBase *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140004afc`
- `0x140019e5c`
- `0x14001a564`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140004b9f`
- `ntoskrnl!IofCompleteRequest` at `0x140004b9f`

## pseudocode

```c
__int64 __fastcall ACCompleteRemoteRequest(CQueueBase *this, NTSTATUS a2, unsigned int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  struct _IRP *TaggedRequest; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 65, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, this, a3);
  }
  v6 = CQueueBase::Validate(this);
  v7 = v6;
  if ( v6 >= 0 )
  {
    TaggedRequest = CQueueBase::GetTaggedRequest(this, a3);
    if ( TaggedRequest )
    {
      TaggedRequest->IoStatus.Status = a2;
      IofCompleteRequest(TaggedRequest, 2);
    }
    return 3221226021LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        66,
        &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        this,
        v6);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x140004afc  push    rbx
0x140004afe  push    rbp
0x140004aff  push    rsi
0x140004b00  push    rdi
0x140004b01  push    r14
0x140004b03  sub     rsp, 30h
0x140004b07  mov     esi, r8d
0x140004b0a  mov     ebp, edx
0x140004b0c  mov     rdi, rcx
0x140004b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b16  lea     r14, WPP_GLOBAL_Control
0x140004b1d  cmp     rcx, r14
0x140004b20  jz      short loc_140004B46
0x140004b22  mov     eax, [rcx+6Ch]
0x140004b25  test    al, 4
0x140004b27  jz      short loc_140004B46
0x140004b29  mov     rcx, [rcx+58h]
0x140004b2d  mov     edx, 41h ; 'A'
0x140004b32  mov     [rsp+58h+var_38], r8d
0x140004b37  mov     r9, rdi
0x140004b3a  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004b41  call    WPP_SF_qD
0x140004b46  mov     rcx, rdi; struct CQueueBase *
0x140004b49  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140004b4e  mov     ebx, eax
0x140004b50  test    eax, eax
0x140004b52  jns     short loc_140004B88
0x140004b54  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b5b  cmp     rcx, r14
0x140004b5e  jz      short loc_140004B84
0x140004b60  mov     edx, [rcx+6Ch]
0x140004b63  test    dl, 1
0x140004b66  jz      short loc_140004B84
0x140004b68  mov     rcx, [rcx+58h]
0x140004b6c  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004b73  mov     edx, 42h ; 'B'
0x140004b78  mov     [rsp+58h+var_38], eax
0x140004b7c  mov     r9, rdi
0x140004b7f  call    WPP_SF_qD
0x140004b84  mov     eax, ebx
0x140004b86  jmp     short loc_140004BB0
0x140004b88  mov     edx, esi; unsigned int
0x140004b8a  mov     rcx, rdi; this
0x140004b8d  call    ?GetTaggedRequest@CQueueBase@@IEAAPEAU_IRP@@K@Z; CQueueBase::GetTaggedRequest(ulong)
0x140004b92  test    rax, rax
0x140004b95  jz      short loc_140004BAB
0x140004b97  mov     dl, 2; PriorityBoost
0x140004b99  mov     [rax+30h], ebp
0x140004b9c  mov     rcx, rax; Irp
0x140004b9f  call    cs:__imp_IofCompleteRequest
0x140004ba6  nop     dword ptr [rax+rax+00h]
0x140004bab  mov     eax, 0C0000225h
0x140004bb0  add     rsp, 30h
0x140004bb4  pop     r14
0x140004bb6  pop     rdi
0x140004bb7  pop     rsi
0x140004bb8  pop     rbp
0x140004bb9  pop     rbx
0x140004bba  retn
```
