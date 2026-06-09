# CKsFilter::DispatchClose(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180051660`
- end: `0x1800519ff`
- name: `?DispatchClose@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `927`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000aa80`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000da50`
- `0x18000dddc`
- `0x180019c60`
- `0x1800332f4`
- `0x180051660`
- `0x180051a08`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1800519b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800519b9`
- `ntoskrnl!IofCompleteRequest` at `0x18005185a`
- `ntoskrnl!IofCompleteRequest` at `0x1800518c5`
- `ntoskrnl!IofCompleteRequest` at `0x18005185a`
- `ntoskrnl!IofCompleteRequest` at `0x1800518c5`
- `ntoskrnl!KeInitializeEvent` at `0x180051826`
- `ntoskrnl!KeInitializeEvent` at `0x180051826`

## pseudocode

```c
__int64 __fastcall CKsFilter::DispatchClose(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int MajorFunction; // edx
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 Notification; // rax
  void *v11; // rcx
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // esi
  __int64 v15; // rbx
  __int64 v16; // rcx
  int v17; // edx
  int v19; // edx
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      31,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( (_BYTE)MajorFunction == 18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(MajorFunction) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        MajorFunction,
        1,
        32,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
    }
    v2->IoStatus.Status = 0;
    IofCompleteRequest(v2, 0);
    return 0;
  }
  else
  {
    v6 = *(_QWORD *)(*(_QWORD *)CurrentStackLocation->FileObject->FsContext + 112LL);
    v7 = v6 - 88;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(MajorFunction) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        MajorFunction,
        1,
        33,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        CurrentStackLocation->MajorFunction);
    }
    if ( v2->IoStatus.Status != -1073741802 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 72) + 40LL))(*(_QWORD *)(v6 + 72));
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 72) + 72LL))(*(_QWORD *)(v6 + 72), v7 + 616);
    if ( v2->IoStatus.Status != -1073741802 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 72) + 48LL))(*(_QWORD *)(v6 + 72));
    Notification = KspGetNotification(v9, v8);
    if ( Notification && *(_BYTE *)(v7 + 768) )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)Notification + 24LL))(
        Notification,
        v7 + 264,
        *(unsigned __int8 *)(v6 + 208),
        *(unsigned int *)(v6 + 224),
        v7 + 216);
    v11 = *(void **)(v7 + 552);
    if ( v11 )
    {
      KsUnregisterWorker(v11);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          v13,
          34,
          (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
          v6 - 88,
          *(_QWORD *)(v7 + 552));
      }
      *(_QWORD *)(v7 + 552) = 0;
    }
    v14 = KspClose(v2, v6);
    if ( v14 != 259 )
    {
      v15 = *(_QWORD *)(*(_QWORD *)(v6 + 40) + 56LL);
      v16 = *(_QWORD *)(*(_QWORD *)a1->DeviceExtension + 128LL);
      if ( v16 )
        (*(void (__fastcall **)(_QWORD))(v16 + 40))(*(_QWORD *)(v16 + 8));
      if ( v14 == -1073741802 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        *(_QWORD *)(v7 + 720) = &Event;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              1,
              35,
              (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
              v7);
          }
          KeWaitForSingleObject(&Event, Suspended, 0, 0, 0);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              1,
              36,
              (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
              v7);
          }
        }
        IofCompleteRequest(v2, 0);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x180051660  push    rdi
0x180051662  push    r12
0x180051664  push    r13
0x180051666  push    r15
0x180051668  sub     rsp, 68h
0x18005166c  mov     rdi, rdx
0x18005166f  mov     r15, rcx
0x180051672  lea     r12, WPP_RECORDER_INITIALIZED
0x180051679  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180051680  lea     r13, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180051687  jz      short loc_18005169B
0x180051689  mov     rcx, cs:WPP_GLOBAL_Control
0x180051690  cmp     word ptr [rcx+48h], 0
0x180051695  jnz     loc_1800518D5
0x18005169b  mov     rax, [rdi+0B8h]
0x1800516a2  mov     [rsp+88h+arg_8], rbp
0x1800516aa  movzx   edx, byte ptr [rax]
0x1800516ad  cmp     dl, 12h
0x1800516b0  jz      loc_1800518B2
0x1800516b6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800516bd  mov     rax, [rax+30h]
0x1800516c1  mov     [rsp+88h+arg_0], rbx
0x1800516c9  mov     [rsp+88h+arg_10], rsi
0x1800516d1  mov     [rsp+88h+var_28], r14
0x1800516d6  mov     rcx, [rax+18h]
0x1800516da  mov     rbx, [rcx]
0x1800516dd  mov     rbx, [rbx+70h]
0x1800516e1  lea     r14, [rbx-58h]
0x1800516e5  jz      short loc_1800516F9
0x1800516e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516ee  cmp     word ptr [rcx+48h], 0
0x1800516f3  jnz     loc_180051922
0x1800516f9  cmp     dword ptr [rdi+30h], 0C0000016h
0x180051700  jz      short loc_180051712
0x180051702  mov     rcx, [rbx+48h]
0x180051706  mov     rax, [rcx]
0x180051709  mov     rax, [rax+28h]
0x18005170d  call    _guard_dispatch_icall
0x180051712  mov     rcx, [rbx+48h]
0x180051716  lea     rdx, [r14+268h]
0x18005171d  mov     rax, [rcx]
0x180051720  mov     rax, [rax+48h]
0x180051724  call    _guard_dispatch_icall
0x180051729  cmp     dword ptr [rdi+30h], 0C0000016h
0x180051730  jz      short loc_180051742
0x180051732  mov     rcx, [rbx+48h]
0x180051736  mov     rax, [rcx]
0x180051739  mov     rax, [rax+30h]
0x18005173d  call    _guard_dispatch_icall
0x180051742  call    KspGetNotification
0x180051747  mov     r10, rax
0x18005174a  test    rax, rax
0x18005174d  jz      short loc_18005178A
0x18005174f  cmp     byte ptr [r14+300h], 0
0x180051757  jz      short loc_18005178A
0x180051759  mov     rcx, [rax]
0x18005175c  lea     r8, [r14+0D8h]
0x180051763  mov     r9d, [rbx+0E0h]
0x18005176a  lea     rdx, [r14+108h]
0x180051771  mov     [rsp+88h+Timeout], r8
0x180051776  movzx   r8d, byte ptr [rbx+0D0h]
0x18005177e  mov     rax, [rcx+18h]
0x180051782  mov     rcx, r10
0x180051785  call    _guard_dispatch_icall
0x18005178a  mov     rcx, [r14+228h]; Worker
0x180051791  xor     ebp, ebp
0x180051793  test    rcx, rcx
0x180051796  jz      short loc_1800517BE
0x180051798  call    KsUnregisterWorker
0x18005179d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800517a4  jz      short loc_1800517B7
0x1800517a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800517ad  cmp     [rcx+48h], bp
0x1800517b1  jnz     loc_180051947
0x1800517b7  mov     [r14+228h], rbp
0x1800517be  mov     rdx, rbx
0x1800517c1  mov     rcx, rdi
0x1800517c4  call    KspClose
0x1800517c9  mov     esi, eax
0x1800517cb  cmp     eax, 103h
0x1800517d0  jz      loc_180051875
0x1800517d6  mov     rcx, [rbx+28h]
0x1800517da  mov     rbx, [rcx+38h]
0x1800517de  mov     rcx, [r15+40h]
0x1800517e2  mov     rdx, [rcx]
0x1800517e5  mov     rcx, [rdx+80h]
0x1800517ec  test    rcx, rcx
0x1800517ef  jz      short loc_1800517FE
0x1800517f1  mov     rax, [rcx+28h]
0x1800517f5  mov     rcx, [rcx+8]
0x1800517f9  call    _guard_dispatch_icall
0x1800517fe  cmp     esi, 0C0000016h
0x180051804  jz      loc_1800518A1
0x18005180a  xorps   xmm0, xmm0
0x18005180d  lea     rcx, [rsp+88h+Event]; Event
0x180051812  xor     eax, eax
0x180051814  xor     r8d, r8d; State
0x180051817  mov     edx, 1; Type
0x18005181c  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x180051821  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x180051826  call    cs:__imp_KeInitializeEvent
0x18005182d  nop     dword ptr [rax+rax+00h]
0x180051832  lea     rax, [rsp+88h+Event]
0x180051837  mov     rcx, r14
0x18005183a  mov     [r14+2D0h], rax
0x180051841  mov     rax, [r14]
0x180051844  mov     rax, [rax+10h]
0x180051848  call    _guard_dispatch_icall
0x18005184d  test    eax, eax
0x18005184f  jnz     loc_180051973
0x180051855  xor     edx, edx; PriorityBoost
0x180051857  mov     rcx, rdi; Irp
0x18005185a  call    cs:__imp_IofCompleteRequest
0x180051861  nop     dword ptr [rax+rax+00h]
0x180051866  mov     rax, [rbx]
0x180051869  mov     rcx, rbx
0x18005186c  mov     rax, [rax+10h]
0x180051870  call    _guard_dispatch_icall
0x180051875  mov     r14, [rsp+88h+var_28]
0x18005187a  mov     eax, esi
0x18005187c  mov     rsi, [rsp+88h+arg_10]
0x180051884  mov     rbx, [rsp+88h+arg_0]
0x18005188c  mov     rbp, [rsp+88h+arg_8]
0x180051894  add     rsp, 68h
0x180051898  pop     r15
0x18005189a  pop     r13
0x18005189c  pop     r12
0x18005189e  pop     rdi
0x18005189f  retn
0x1800518a1  mov     rax, [r14]
0x1800518a4  mov     rcx, r14
0x1800518a7  mov     rax, [rax+10h]
0x1800518ab  call    _guard_dispatch_icall
0x1800518b0  jmp     short loc_180051866
0x1800518b2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800518b9  jnz     short loc_1800518F6
0x1800518bb  xor     ebp, ebp
0x1800518bd  xor     edx, edx; PriorityBoost
0x1800518bf  mov     rcx, rdi; Irp
0x1800518c2  mov     [rdi+30h], ebp
0x1800518c5  call    cs:__imp_IofCompleteRequest
0x1800518cc  nop     dword ptr [rax+rax+00h]
0x1800518d1  xor     eax, eax
0x1800518d3  jmp     short loc_18005188C
0x1800518d5  mov     rcx, [rcx+40h]
0x1800518d9  mov     r9d, 1Fh
0x1800518df  mov     r8d, 1
0x1800518e5  mov     [rsp+88h+Timeout], r13
0x1800518ea  mov     dl, 5
0x1800518ec  call    WPP_RECORDER_SF_
0x1800518f1  jmp     loc_18005169B
0x1800518f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800518fd  cmp     word ptr [rcx+48h], 0
0x180051902  jz      short loc_1800518BB
0x180051904  mov     rcx, [rcx+40h]
0x180051908  mov     r9d, 20h ; ' '
0x18005190e  mov     r8d, 1
0x180051914  mov     [rsp+88h+Timeout], r13
0x180051919  mov     dl, 5
0x18005191b  call    WPP_RECORDER_SF_
0x180051920  jmp     short loc_1800518BB
0x180051922  mov     rcx, [rcx+40h]
0x180051926  mov     r9d, 21h ; '!'
0x18005192c  mov     dword ptr [rsp+88h+var_60], edx
0x180051930  mov     r8d, 1
0x180051936  mov     dl, 5
0x180051938  mov     [rsp+88h+Timeout], r13
0x18005193d  call    WPP_RECORDER_SF_D
0x180051942  jmp     loc_1800516F9
0x180051947  mov     rax, [r14+228h]
0x18005194e  mov     r9d, 22h ; '"'
0x180051954  mov     rcx, [rcx+40h]
0x180051958  mov     dl, 5
0x18005195a  mov     [rsp+88h+var_58], rax
0x18005195f  mov     [rsp+88h+var_60], r14
0x180051964  mov     [rsp+88h+Timeout], r13
0x180051969  call    WPP_RECORDER_SF_qq
0x18005196e  jmp     loc_1800517B7
0x180051973  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005197a  jz      short loc_1800519A4
0x18005197c  mov     rcx, cs:WPP_GLOBAL_Control
0x180051983  mov     r9d, 23h ; '#'
0x180051989  mov     [rsp+88h+var_60], r14
0x18005198e  mov     r8d, 1
0x180051994  mov     dl, 4
0x180051996  mov     [rsp+88h+Timeout], r13
0x18005199b  mov     rcx, [rcx+40h]
0x18005199f  call    WPP_RECORDER_SF_q
0x1800519a4  xor     r9d, r9d; Alertable
0x1800519a7  mov     [rsp+88h+Timeout], rbp; Timeout
0x1800519ac  xor     r8d, r8d; WaitMode
0x1800519af  lea     rcx, [rsp+88h+Event]; Object
0x1800519b4  mov     edx, 5; WaitReason
0x1800519b9  call    cs:__imp_KeWaitForSingleObject
0x1800519c0  nop     dword ptr [rax+rax+00h]
0x1800519c5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800519cc  jz      loc_180051855
0x1800519d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800519d9  mov     r9d, 24h ; '$'
0x1800519df  mov     [rsp+88h+var_60], r14
0x1800519e4  mov     r8d, 1
0x1800519ea  mov     dl, 4
0x1800519ec  mov     [rsp+88h+Timeout], r13
0x1800519f1  mov     rcx, [rcx+40h]
0x1800519f5  call    WPP_RECORDER_SF_q
0x1800519fa  jmp     loc_180051855
```
