# CKsQueue::ForwardWaitingIrps(void)

- ea: `0x180001e30`
- end: `0x180001ef1`
- name: `?ForwardWaitingIrps@CKsQueue@@AEAAXXZ`
- size: `193`
- prototype: `void __fastcall(CKsQueue *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001960`
- `0x180005580`
- `0x180015ce0`

## callees

- `0x180001e30`
- `0x180002640`
- `0x18000b7bc`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001e6e`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001ea7`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001e6e`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180001ea7`

## pseudocode

```c
void __fastcall CKsQueue::ForwardWaitingIrps(CKsQueue *this)
{
  PLIST_ENTRY i; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      68,
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
  for ( i = ExInterlockedRemoveHeadList(&this->m_WaitingIrps, &this->m_FrameQueue.SpinLock);
        i;
        i = ExInterlockedRemoveHeadList(&this->m_WaitingIrps, &this->m_FrameQueue.SpinLock) )
  {
    CKsQueue::ForwardIrp(this, (struct _IRP *)&i[-11].Blink, (struct KSPIRP_FRAMING_ *)&i[1].Flink->Blink, 0);
  }
}

```

## disassembly

```asm
0x180001e30  mov     [rsp+arg_0], rbx
0x180001e35  mov     [rsp+arg_8], rsi
0x180001e3a  push    rdi
0x180001e3b  sub     rsp, 30h
0x180001e3f  mov     rbx, rcx
0x180001e42  lea     rax, WPP_RECORDER_INITIALIZED
0x180001e49  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180001e50  jz      short loc_180001E60
0x180001e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e59  cmp     word ptr [rcx+48h], 0
0x180001e5e  jnz     short loc_180001EC9
0x180001e60  lea     rdx, [rbx+140h]; Lock
0x180001e67  lea     rcx, [rbx+178h]; ListHead
0x180001e6e  call    cs:__imp_ExInterlockedRemoveHeadList
0x180001e75  nop     dword ptr [rax+rax+00h]
0x180001e7a  test    rax, rax
0x180001e7d  jz      short loc_180001EB8
0x180001e7f  mov     r8, [rax+10h]
0x180001e83  lea     rdx, [rax-0A8h]; struct _IRP *
0x180001e8a  add     r8, 8; struct KSPIRP_FRAMING_ *
0x180001e8e  xor     r9d, r9d; struct IKsTransport **
0x180001e91  mov     rcx, rbx; this
0x180001e94  call    ?ForwardIrp@CKsQueue@@AEAAXPEAU_IRP@@PEAUKSPIRP_FRAMING_@@PEAPEAUIKsTransport@@@Z; CKsQueue::ForwardIrp(_IRP *,KSPIRP_FRAMING_ *,IKsTransport * *)
0x180001e99  lea     rdx, [rbx+140h]; Lock
0x180001ea0  lea     rcx, [rbx+178h]; ListHead
0x180001ea7  call    cs:__imp_ExInterlockedRemoveHeadList
0x180001eae  nop     dword ptr [rax+rax+00h]
0x180001eb3  test    rax, rax
0x180001eb6  jnz     short loc_180001E7F
0x180001eb8  mov     rbx, [rsp+38h+arg_0]
0x180001ebd  mov     rsi, [rsp+38h+arg_8]
0x180001ec2  add     rsp, 30h
0x180001ec6  pop     rdi
0x180001ec7  retn
0x180001ec9  mov     rcx, [rcx+40h]
0x180001ecd  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x180001ed4  mov     r9d, 44h ; 'D'
0x180001eda  mov     [rsp+38h+var_18], rax
0x180001edf  mov     r8d, 1
0x180001ee5  mov     dl, 5
0x180001ee7  call    WPP_RECORDER_SF_
0x180001eec  jmp     loc_180001E60
```
