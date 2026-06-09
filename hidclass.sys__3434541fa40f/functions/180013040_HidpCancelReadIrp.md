# HidpCancelReadIrp

- ea: `0x180013040`
- end: `0x1800131a9`
- name: `HidpCancelReadIrp`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800127d0`
- `0x180013040`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180013075`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x180013075`
- `ntoskrnl!IofCompleteRequest` at `0x180013128`
- `ntoskrnl!IofCompleteRequest` at `0x180013128`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800130cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800130cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180013085`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180013085`

## pseudocode

```c
void __fastcall HidpCancelReadIrp(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  __int64 v6; // rbp
  KSPIN_LOCK *FsContext; // rbx
  KIRQL v8; // al
  _LIST_ENTRY *Flink; // r10
  _LIST_ENTRY *Blink; // r9
  int v11; // edx
  int v12; // r8d

  v2 = *(_QWORD *)(a1 + 64);
  v4 = *(_QWORD *)(v2 + 96);
  v5 = *(unsigned int *)(v2 + 44);
  v6 = *(_QWORD *)(v4 + 184);
  FsContext = (KSPIN_LOCK *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v8 = KeAcquireSpinLockRaiseToDpc(FsContext + 9);
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (void **)Flink->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (void **)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  _InterlockedDecrement((volatile signed __int32 *)(424 * v5 + v6 + 16));
  KeReleaseSpinLock(FsContext + 9, v8);
  a2->IoStatus.Status = -1073741536;
  LOBYTE(v12) = 1;
  LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
    LOBYTE(v12) = 0;
  if ( (_BYTE)v11 || (_BYTE)v12 )
    WPP_RECORDER_AND_TRACE_SF_qdqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v12,
      *(_QWORD *)(v4 + 704),
      5,
      5,
      10,
      (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
      *(_QWORD *)(*(_QWORD *)(v2 + 96) + 32LL),
      *(_DWORD *)(v2 + 40),
      *(_QWORD *)(v2 + 80),
      (char)a2,
      -1073741536);
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x180013040  push    rbx
0x180013042  push    rbp
0x180013043  push    rsi
0x180013044  push    rdi
0x180013045  push    r14
0x180013047  push    r15
0x180013049  sub     rsp, 78h
0x18001304d  mov     rsi, [rcx+40h]
0x180013051  mov     rdi, rdx
0x180013054  mov     rax, [rdx+0B8h]
0x18001305b  mov     r15, [rsi+60h]
0x18001305f  mov     rcx, [rax+30h]
0x180013063  mov     r14d, [rsi+2Ch]
0x180013067  mov     rbp, [r15+0B8h]
0x18001306e  mov     rbx, [rcx+18h]
0x180013072  mov     cl, [rdx+45h]; Irql
0x180013075  call    cs:__imp_IoReleaseCancelSpinLock
0x18001307c  nop     dword ptr [rax+rax+00h]
0x180013081  lea     rcx, [rbx+48h]; SpinLock
0x180013085  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001308c  nop     dword ptr [rax+rax+00h]
0x180013091  lea     rdx, [rdi+0A8h]
0x180013098  mov     r10, [rdx]
0x18001309b  cmp     [r10+8], rdx
0x18001309f  jnz     short loc_1800130AA
0x1800130a1  mov     r9, [rdx+8]
0x1800130a5  cmp     [r9], rdx
0x1800130a8  jz      short loc_1800130B1
0x1800130aa  mov     ecx, 3
0x1800130af  int     29h; Win8: RtlFailFast(ecx)
0x1800130b1  mov     [r9], r10
0x1800130b4  lea     rcx, [rbx+48h]; SpinLock
0x1800130b8  imul    r8, r14, 1A8h
0x1800130bf  mov     [r10+8], r9
0x1800130c3  mov     dl, al; NewIrql
0x1800130c5  lock dec dword ptr [r8+rbp+10h]
0x1800130cb  call    cs:__imp_KeReleaseSpinLock
0x1800130d2  nop     dword ptr [rax+rax+00h]
0x1800130d7  mov     r11d, 0C0000120h
0x1800130dd  mov     [rdi+30h], r11d
0x1800130e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130e8  lea     rax, WPP_GLOBAL_Control
0x1800130ef  mov     r8b, 1
0x1800130f2  cmp     rcx, rax
0x1800130f5  jz      short loc_1800130FE
0x1800130f7  mov     eax, [rcx+2Ch]
0x1800130fa  test    al, 10h
0x1800130fc  jnz     short loc_180013142
0x1800130fe  xor     dl, dl
0x180013100  lea     rax, WPP_RECORDER_INITIALIZED
0x180013107  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001310e  jz      short loc_180013117
0x180013110  cmp     word ptr [rcx+48h], 0
0x180013115  jnz     short loc_18001311A
0x180013117  xor     r8b, r8b
0x18001311a  test    dl, dl
0x18001311c  jnz     short loc_18001314D
0x18001311e  test    r8b, r8b
0x180013121  jnz     short loc_18001314D
0x180013123  xor     edx, edx; PriorityBoost
0x180013125  mov     rcx, rdi; Irp
0x180013128  call    cs:__imp_IofCompleteRequest
0x18001312f  nop     dword ptr [rax+rax+00h]
0x180013134  add     rsp, 78h
0x180013138  pop     r15
0x18001313a  pop     r14
0x18001313c  pop     rdi
0x18001313d  pop     rsi
0x18001313e  pop     rbp
0x18001313f  pop     rbx
0x180013140  retn
0x180013142  cmp     byte ptr [rcx+29h], 5
0x180013146  jb      short loc_1800130FE
0x180013148  mov     dl, r8b
0x18001314b  jmp     short loc_180013100
0x18001314d  mov     rax, [rsi+50h]
0x180013151  mov     r10, [rsi+60h]
0x180013155  mov     r9, [r15+2C0h]
0x18001315c  mov     rcx, [rcx+18h]
0x180013160  mov     [rsp+0A8h+var_48], r11d
0x180013165  mov     [rsp+0A8h+var_50], rdi
0x18001316a  mov     [rsp+0A8h+var_58], rax
0x18001316f  mov     eax, [rsi+28h]
0x180013172  mov     [rsp+0A8h+var_60], eax
0x180013176  mov     rax, [r10+20h]
0x18001317a  mov     [rsp+0A8h+var_68], rax
0x18001317f  lea     rax, WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids
0x180013186  mov     [rsp+0A8h+var_70], rax
0x18001318b  mov     [rsp+0A8h+var_78], 0Ah
0x180013192  mov     [rsp+0A8h+var_80], 5
0x18001319a  mov     [rsp+0A8h+var_88], 5
0x18001319f  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x1800131a4  jmp     loc_180013123
```
