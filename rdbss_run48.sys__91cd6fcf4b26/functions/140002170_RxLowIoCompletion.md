# RxLowIoCompletion

- ea: `0x140002170`
- end: `0x1400022f1`
- name: `RxLowIoCompletion`
- size: `385`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013260`
- `0x140024cf0`

## callees

- `0x140002170`
- `0x140002300`
- `0x140002580`
- `0x140007ca0`
- `0x140016e70`
- `0x14001810c`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002195`
- `ntoskrnl!KeSetEvent` at `0x140002195`
- `ntoskrnl!KeBugCheckEx` at `0x140026d81`
- `ntoskrnl!KeBugCheckEx` at `0x140026d81`

## pseudocode

```c
NTSTATUS __stdcall RxLowIoCompletion(PRX_CONTEXT RxContext)
{
  int RdbssDbgExtension; // eax
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  NTSTATUS v6; // edi
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v8; // rcx
  struct _LIST_ENTRY *v9; // rax
  struct _LIST_ENTRY *Flink; // rax

  RdbssDbgExtension = (int)RxContext->RdbssDbgExtension;
  if ( (RdbssDbgExtension & 0x1000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids, RxContext);
    }
    v4 = RxLowIoCompletionTail(RxContext);
    v6 = v4;
    switch ( v4 )
    {
      case -1073741802:
      case -1069481981:
        Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
        if ( Blink )
        {
          Flink = Blink[42].Flink;
          if ( Flink )
          {
            LOBYTE(v5) = 11;
            ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(RxContext, v5);
          }
        }
        if ( (PRDBSS_DEVICE_OBJECT)RxContext->BlockedOperations.Blink == RxFileSystemDeviceObject
          && RxContext->SyncEvent.Header.WaitListHead.Blink == (struct _LIST_ENTRY *)RxpProcessWorkItem
          && (KEVENT *)RxContext->BlockedOperations.Flink == &RxContext->SyncEvent )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) )
              WPP_SF_qqq(
                WPP_GLOBAL_Control->AttachedDevice,
                16,
                &WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids,
                &RxContext->SyncEvent,
                RxContext->BlockedOpsMutex,
                RxContext->RxContextSerializationQLinks.Flink);
          }
          KeBugCheckEx(
            0x27u,
            0x80233u,
            (ULONG_PTR)&RxContext->SyncEvent,
            (ULONG_PTR)RxContext->BlockedOpsMutex,
            (ULONG_PTR)RxContext->RxContextSerializationQLinks.Flink);
        }
        RxpPostToWorkerThread(RxFileSystemDeviceObject, (__int64)RxContext, 0);
        break;
      case -1069481983:
        v8 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
        if ( v8 )
        {
          v9 = v8[42].Flink;
          if ( v9 )
          {
            LOBYTE(v5) = 12;
            ((void (__fastcall *)(PRX_CONTEXT, __int64))v9)(RxContext, v5);
          }
        }
        RxContext->OverflowListEntry.Blink = (struct _LIST_ENTRY *)RxLowIoSubmitRETRY;
        RxFsdPostRequest(RxContext);
        return -1073741802;
      case -1071906810:
        return -1073741802;
    }
    return v6;
  }
  else
  {
    LODWORD(RxContext->RdbssDbgExtension) = RdbssDbgExtension & 0xFFEFFFFF;
    KeSetEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, 0, 0);
    return -1073741802;
  }
}

```

## disassembly

```asm
0x140002170  push    rbx
0x140002172  sub     rsp, 30h
0x140002176  mov     eax, [rcx+78h]
0x140002179  mov     rbx, rcx
0x14000217c  bt      eax, 0Ch
0x140002180  jb      short loc_1400021AD
0x140002182  btr     eax, 14h
0x140002186  xor     r8d, r8d; Wait
0x140002189  mov     [rcx+78h], eax
0x14000218c  xor     edx, edx; Increment
0x14000218e  add     rcx, 180h; Event
0x140002195  call    cs:__imp_KeSetEvent
0x14000219c  nop     dword ptr [rax+rax+00h]
0x1400021a1  mov     eax, 0C0000016h
0x1400021a6  add     rsp, 30h
0x1400021aa  pop     rbx
0x1400021ab  retn
0x1400021ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021b4  mov     [rsp+38h+arg_0], rbp
0x1400021b9  lea     rbp, WPP_GLOBAL_Control
0x1400021c0  mov     [rsp+38h+arg_10], rdi
0x1400021c5  cmp     rcx, rbp
0x1400021c8  jz      short loc_1400021D5
0x1400021ca  mov     eax, [rcx+2Ch]
0x1400021cd  test    al, 4
0x1400021cf  jnz     loc_140002277
0x1400021d5  mov     rcx, rbx; RxContext
0x1400021d8  mov     [rsp+38h+arg_8], rsi
0x1400021dd  call    RxLowIoCompletionTail
0x1400021e2  mov     edi, eax
0x1400021e4  cmp     eax, 0C0000016h
0x1400021e9  jnz     short loc_140002249
0x1400021eb  mov     rax, [rbx+50h]
0x1400021ef  mov     rcx, [rax+160h]
0x1400021f6  test    rcx, rcx
0x1400021f9  jnz     loc_1400022D2
0x1400021ff  mov     rcx, cs:RxFileSystemDeviceObject; Object
0x140002206  lea     rsi, [rbx+130h]
0x14000220d  cmp     [rsi+20h], rcx
0x140002211  jz      short loc_140002265
0x140002213  mov     [rsp+38h+var_10], 0; char
0x140002218  lea     r9, RxLowIoCompletion
0x14000221f  mov     r8, rsi
0x140002222  mov     [rsp+38h+BugCheckParameter4], rbx; __int64
0x140002227  mov     edx, 3
0x14000222c  call    RxpPostToWorkerThread
0x140002231  mov     rsi, [rsp+38h+arg_8]
0x140002236  mov     eax, edi
0x140002238  mov     rdi, [rsp+38h+arg_10]
0x14000223d  mov     rbp, [rsp+38h+arg_0]
0x140002242  add     rsp, 30h
0x140002246  pop     rbx
0x140002247  retn
0x140002249  cmp     eax, 0C0410003h
0x14000224e  jz      short loc_1400021EB
0x140002250  cmp     eax, 0C0410001h
0x140002255  jz      short loc_14000229E
0x140002257  cmp     eax, 0C01C0006h
0x14000225c  jnz     short loc_140002231
0x14000225e  mov     edi, 0C0000016h
0x140002263  jmp     short loc_140002231
0x140002265  lea     rax, RxpProcessWorkItem
0x14000226c  cmp     [rsi+10h], rax
0x140002270  jnz     short loc_140002213
0x140002272  jmp     loc_140026D1A
0x140002277  cmp     byte ptr [rcx+29h], 4
0x14000227b  jb      loc_1400021D5
0x140002281  mov     rcx, [rcx+18h]
0x140002285  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x14000228c  mov     edx, 14h
0x140002291  mov     r9, rbx
0x140002294  call    WPP_SF_q
0x140002299  jmp     loc_1400021D5
0x14000229e  mov     rax, [rbx+50h]
0x1400022a2  mov     rcx, [rax+160h]
0x1400022a9  test    rcx, rcx
0x1400022ac  jz      loc_140026CFA
0x1400022b2  mov     rax, [rcx+2A0h]
0x1400022b9  test    rax, rax
0x1400022bc  jz      loc_140026CFA
0x1400022c2  mov     dl, 0Ch
0x1400022c4  mov     rcx, rbx
0x1400022c7  call    _guard_dispatch_icall
0x1400022cc  nop
0x1400022cd  jmp     loc_140026CFA
0x1400022d2  mov     rax, [rcx+2A0h]
0x1400022d9  test    rax, rax
0x1400022dc  jz      loc_1400021FF
0x1400022e2  mov     dl, 0Bh
0x1400022e4  mov     rcx, rbx
0x1400022e7  call    _guard_dispatch_icall
0x1400022ec  jmp     loc_1400021FF
0x140026cfa  lea     rax, RxLowIoSubmitRETRY
0x140026d01  mov     rcx, rbx; RxContext
0x140026d04  mov     [rbx+128h], rax
0x140026d0b  call    RxFsdPostRequest
0x140026d10  mov     edi, 0C0000016h
0x140026d15  jmp     loc_140002231
0x140026d1a  cmp     [rsi+18h], rsi
0x140026d1e  jnz     loc_140002213
0x140026d24  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d2b  cmp     rcx, rbp
0x140026d2e  jz      short loc_140026D67
0x140026d30  mov     eax, [rcx+2Ch]
0x140026d33  test    al, 1
0x140026d35  jz      short loc_140026D67
0x140026d37  cmp     byte ptr [rcx+29h], 1
0x140026d3b  jb      short loc_140026D67
0x140026d3d  mov     rax, [rsi+30h]
0x140026d41  lea     r8, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids
0x140026d48  mov     rcx, [rcx+18h]
0x140026d4c  mov     edx, 10h
0x140026d51  mov     qword ptr [rsp+38h+var_10], rax
0x140026d56  mov     r9, rsi
0x140026d59  mov     rax, [rsi+28h]
0x140026d5d  mov     [rsp+38h+BugCheckParameter4], rax
0x140026d62  call    WPP_SF_qqq
0x140026d67  mov     rax, [rsi+30h]
0x140026d6b  mov     r8, rsi; BugCheckParameter2
0x140026d6e  mov     r9, [rsi+28h]; BugCheckParameter3
0x140026d72  mov     edx, 80233h; BugCheckParameter1
0x140026d77  mov     ecx, 27h ; '''; BugCheckCode
0x140026d7c  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140026d81  call    cs:__imp_KeBugCheckEx
```
