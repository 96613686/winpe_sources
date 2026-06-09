# CStorageComplete::CompleteStorage(_DEVICE_OBJECT *)

- ea: `0x140021144`
- end: `0x140021277`
- name: `?CompleteStorage@CStorageComplete@@AEAAXPEAU_DEVICE_OBJECT@@@Z`
- size: `307`
- prototype: `void(CStorageComplete *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140021490`

## callees

- `0x140012644`
- `0x140020ebc`
- `0x140021144`
- `0x1400214b4`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140021193`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140021193`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400211bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400211bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400211cb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400211cb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400211ed`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400211ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400211f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400211f9`
- `ntoskrnl!IofCompleteRequest` at `0x14002124e`
- `ntoskrnl!IofCompleteRequest` at `0x14002124e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002116d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002116d`

## pseudocode

```c
void __fastcall CStorageComplete::CompleteStorage(CStorageComplete *this, struct _DEVICE_OBJECT *a2)
{
  char *DeviceExtension; // r13
  __int64 v5; // rax
  __int64 v6; // rdi
  int v7; // r15d
  unsigned int v8; // r14d
  __int64 v9; // r8
  KIRQL Irql; // [rsp+60h] [rbp+8h] BYREF

  DeviceExtension = (char *)a2->DeviceExtension;
  *((_BYTE *)this + 24) = 0;
  while ( 1 )
  {
    IoAcquireCancelSpinLock(&Irql);
    v5 = XList<_IRP,168>::gethead(this);
    v6 = v5;
    if ( v5 )
      _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0);
    IoReleaseCancelSpinLock(Irql);
    if ( !v6 )
      break;
    v7 = *(_DWORD *)(v6 + 112);
    v8 = *(_DWORD *)(*(_QWORD *)(v6 + 184) + 16LL) >> 3;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
    ACpCompleteStorage(a2, v8, *(struct CPacket ***)(v6 + 24), v7);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_qdD(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 18, v9, v6, v8, v7);
    }
    *(_QWORD *)(v6 + 56) = 0;
    *(_DWORD *)(v6 + 48) = 0;
    IofCompleteRequest((PIRP)v6, 0);
  }
}

```

## disassembly

```asm
0x140021144  mov     [rsp+arg_8], rbx
0x140021149  mov     [rsp+arg_10], rbp
0x14002114e  push    rsi
0x14002114f  push    rdi
0x140021150  push    r13
0x140021152  push    r14
0x140021154  push    r15
0x140021156  sub     rsp, 30h
0x14002115a  mov     r13, [rdx+40h]
0x14002115e  mov     rbp, rdx
0x140021161  mov     byte ptr [rcx+18h], 0
0x140021165  mov     rsi, rcx
0x140021168  lea     rcx, [rsp+58h+Irql]; Irql
0x14002116d  call    cs:__imp_IoAcquireCancelSpinLock
0x140021174  nop     dword ptr [rax+rax+00h]
0x140021179  mov     rcx, rsi
0x14002117c  call    ?gethead@?$XList@U_IRP@@$0KI@@@QEAAPEAU_IRP@@XZ; XList<_IRP,168>::gethead(void)
0x140021181  mov     rdi, rax
0x140021184  test    rax, rax
0x140021187  jz      short loc_14002118F
0x140021189  xor     ecx, ecx
0x14002118b  xchg    rcx, [rax+68h]
0x14002118f  mov     cl, [rsp+58h+Irql]; Irql
0x140021193  call    cs:__imp_IoReleaseCancelSpinLock
0x14002119a  nop     dword ptr [rax+rax+00h]
0x14002119f  test    rdi, rdi
0x1400211a2  jz      loc_14002125F
0x1400211a8  mov     rcx, [rdi+0B8h]
0x1400211af  mov     r15d, [rdi+70h]
0x1400211b3  mov     r14d, [rcx+10h]
0x1400211b7  shr     r14d, 3
0x1400211bb  call    cs:__imp_KeEnterCriticalRegion
0x1400211c2  nop     dword ptr [rax+rax+00h]
0x1400211c7  lea     rcx, [r13+8]; FastMutex
0x1400211cb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400211d2  nop     dword ptr [rax+rax+00h]
0x1400211d7  mov     r8, [rdi+18h]; struct CPacket **
0x1400211db  mov     r9d, r15d; int
0x1400211de  mov     edx, r14d; unsigned int
0x1400211e1  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x1400211e4  call    ?ACpCompleteStorage@@YAXPEAU_DEVICE_OBJECT@@KPEAPEAVCPacket@@J@Z; ACpCompleteStorage(_DEVICE_OBJECT *,ulong,CPacket * *,long)
0x1400211e9  lea     rcx, [r13+8]; FastMutex
0x1400211ed  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400211f4  nop     dword ptr [rax+rax+00h]
0x1400211f9  call    cs:__imp_KeLeaveCriticalRegion
0x140021200  nop     dword ptr [rax+rax+00h]
0x140021205  mov     rcx, cs:WPP_GLOBAL_Control
0x14002120c  lea     rax, WPP_GLOBAL_Control
0x140021213  cmp     rcx, rax
0x140021216  jz      short loc_14002123A
0x140021218  mov     eax, [rcx+6Ch]
0x14002121b  test    al, 4
0x14002121d  jz      short loc_14002123A
0x14002121f  mov     rcx, [rcx+58h]
0x140021223  mov     edx, 12h
0x140021228  mov     [rsp+58h+var_30], r15d
0x14002122d  mov     r9, rdi
0x140021230  mov     [rsp+58h+var_38], r14d
0x140021235  call    WPP_SF_qdD
0x14002123a  xor     edx, edx; PriorityBoost
0x14002123c  mov     qword ptr [rdi+38h], 0
0x140021244  mov     rcx, rdi; Irp
0x140021247  mov     dword ptr [rdi+30h], 0
0x14002124e  call    cs:__imp_IofCompleteRequest
0x140021255  nop     dword ptr [rax+rax+00h]
0x14002125a  jmp     loc_140021168
0x14002125f  mov     rbx, [rsp+58h+arg_8]
0x140021264  mov     rbp, [rsp+58h+arg_10]
0x140021269  add     rsp, 30h
0x14002126d  pop     r15
0x14002126f  pop     r14
0x140021271  pop     r13
0x140021273  pop     rdi
0x140021274  pop     rsi
0x140021275  retn
```
