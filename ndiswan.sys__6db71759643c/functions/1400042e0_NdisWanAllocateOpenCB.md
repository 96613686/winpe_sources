# NdisWanAllocateOpenCB

- ea: `0x1400042e0`
- end: `0x140004728`
- name: `NdisWanAllocateOpenCB`
- size: `1096`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400040a0`
- `0x14000f2d0`

## callees

- `0x1400042e0`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000cac8`
- `0x14000cb38`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000440c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000440c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400043ca`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400043ca`
- `ntoskrnl!KeInitializeEvent` at `0x14000435b`
- `ntoskrnl!KeInitializeEvent` at `0x14000435b`
- `ntoskrnl!RtlGUIDFromString` at `0x140004541`
- `ntoskrnl!RtlGUIDFromString` at `0x140004541`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000446f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000446f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400045d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400045d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046e2`
- `ntoskrnl!ExAllocatePool2` at `0x140004337`
- `ntoskrnl!ExAllocatePool2` at `0x140004396`
- `ntoskrnl!ExAllocatePool2` at `0x140004337`
- `ntoskrnl!ExAllocatePool2` at `0x140004396`
- `NDIS!NdisInitializeEvent` at `0x140004449`
- `NDIS!NdisInitializeEvent` at `0x14000445c`
- `NDIS!NdisInitializeEvent` at `0x140004449`
- `NDIS!NdisInitializeEvent` at `0x14000445c`
- `NDIS!NdisAllocateIoWorkItem` at `0x14000436e`
- `NDIS!NdisAllocateIoWorkItem` at `0x14000436e`
- `NDIS!NdisFreeIoWorkItem` at `0x1400046d1`
- `NDIS!NdisFreeIoWorkItem` at `0x1400046d1`

## pseudocode

```c
struct _KEVENT *__fastcall NdisWanAllocateOpenCB(PCUNICODE_STRING SourceString)
{
  struct _KEVENT *Pool2; // rax
  struct _KEVENT *v3; // rdi
  struct _LIST_ENTRY *IoWorkItem; // rax
  __int64 v5; // rax
  unsigned __int16 v6; // ax
  struct _KEVENT **v7; // rax
  int v8; // edx
  int v9; // r8d
  UNICODE_STRING GuidString; // [rsp+30h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids,
        SourceString->Buffer);
    }
  }
  Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 576, 1248747863);
  v3 = Pool2;
  if ( Pool2 )
  {
    KeInitializeEvent(Pool2 + 20, NotificationEvent, 0);
    IoWorkItem = (struct _LIST_ENTRY *)NdisAllocateIoWorkItem(NdisMiniportDriverHandle);
    v3[4].Header.WaitListHead.Flink = IoWorkItem;
    if ( IoWorkItem )
    {
      v5 = ExAllocatePool2(64, SourceString->MaximumLength, 1299079511);
      *(_QWORD *)&v3[3].Header.Lock = v5;
      if ( v5 )
      {
        WORD1(v3[2].Header.WaitListHead.Blink) = SourceString->MaximumLength;
        LOWORD(v3[2].Header.WaitListHead.Blink) = SourceString->Length;
        RtlCopyUnicodeString((PUNICODE_STRING)&v3[2].Header.WaitListHead.Blink, SourceString);
        v6 = LOWORD(v3[2].Header.WaitListHead.Blink) >> 1;
        if ( v6 )
        {
          while ( *(_WORD *)(*(_QWORD *)&v3[3].Header.Lock + 2LL * v6 - 2) != 123 )
          {
            if ( !--v6 )
              goto LABEL_11;
          }
          *(_DWORD *)(&GuidString.MaximumLength + 1) = 0;
          GuidString.Length = SourceString->Length + 2 * (1 - v6);
          GuidString.MaximumLength = GuidString.Length;
          GuidString.Buffer = &SourceString->Buffer[v6 - 1];
          RtlGUIDFromString(&GuidString, (GUID *)&v3[3].Header.WaitListHead);
        }
LABEL_11:
        KeInitializeSpinLock((PKSPIN_LOCK)&v3[21]);
        v3[9].Header.WaitListHead.Blink = &v3[9].Header.WaitListHead;
        v3[9].Header.WaitListHead.Flink = &v3[9].Header.WaitListHead;
        v3[10].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)&v3[10];
        *(_QWORD *)&v3[10].Header.Lock = v3 + 10;
        *(_QWORD *)&v3[9].Header.Lock = (char *)v3 + 208;
        v3[8].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)&v3[8].Header.WaitListHead.Blink;
        NdisInitializeEvent((PNDIS_EVENT)&v3[22]);
        NdisInitializeEvent((PNDIS_EVENT)&v3[23]);
        *((_BYTE *)&WPP_MAIN_CB.Reserved + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
        v7 = (struct _KEVENT **)qword_14001E1C0;
        if ( *(__int64 **)qword_14001E1C0 != &qword_14001E1B8 )
          __fastfail(3u);
        v3->Header.WaitListHead.Flink = (struct _LIST_ENTRY *)qword_14001E1C0;
        *(_QWORD *)&v3->Header.Lock = &qword_14001E1B8;
        *v7 = v3;
        qword_14001E1C0 = (__int64)v3;
        if ( ++dword_14001E1B0 > (unsigned int)dword_14001E1B4 )
          dword_14001E1B4 = dword_14001E1B0;
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, *((KIRQL *)&WPP_MAIN_CB.Reserved + 8));
        LODWORD(v3->Header.WaitListHead.Blink) = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_Sq(WPP_GLOBAL_Control->AttachedDevice, v8, v9, *(_QWORD *)&v3[3].Header.Lock, (char)v3);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
          }
        }
        return v3;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids,
            SourceString->MaximumLength);
        }
        NdisFreeIoWorkItem(v3[4].Header.WaitListHead.Flink);
        ExFreePoolWithTag(v3, 0);
        return 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
      }
      ExFreePoolWithTag(v3, 0);
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400042e0  mov     [rsp+arg_8], rbp
0x1400042e5  mov     [rsp+arg_10], rsi
0x1400042ea  push    rdi
0x1400042eb  sub     rsp, 40h
0x1400042ef  mov     rsi, rcx
0x1400042f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042f9  lea     rbp, WPP_GLOBAL_Control
0x140004300  cmp     rcx, rbp
0x140004303  jz      short loc_140004327
0x140004305  mov     eax, [rcx+2Ch]
0x140004308  test    al, 40h
0x14000430a  jnz     loc_1400045F0
0x140004310  mov     rcx, cs:WPP_GLOBAL_Control
0x140004317  cmp     rcx, rbp
0x14000431a  jz      short loc_140004327
0x14000431c  mov     eax, [rcx+2Ch]
0x14000431f  test    al, 40h
0x140004321  jnz     loc_140004614
0x140004327  mov     edx, 240h
0x14000432c  mov     ecx, 40h ; '@'
0x140004331  mov     r8d, 4A6E6157h
0x140004337  call    cs:__imp_ExAllocatePool2
0x14000433e  nop     dword ptr [rax+rax+00h]
0x140004343  mov     rdi, rax
0x140004346  test    rax, rax
0x140004349  jz      loc_140004599
0x14000434f  lea     rcx, [rax+1E0h]; Event
0x140004356  xor     r8d, r8d; State
0x140004359  xor     edx, edx; Type
0x14000435b  call    cs:__imp_KeInitializeEvent
0x140004362  nop     dword ptr [rax+rax+00h]
0x140004367  mov     rcx, cs:NdisMiniportDriverHandle; NdisObjectHandle
0x14000436e  call    cs:__imp_NdisAllocateIoWorkItem
0x140004375  nop     dword ptr [rax+rax+00h]
0x14000437a  mov     [rdi+68h], rax
0x14000437e  test    rax, rax
0x140004381  jz      loc_1400045BC
0x140004387  movzx   edx, word ptr [rsi+2]
0x14000438b  mov     ecx, 40h ; '@'
0x140004390  mov     r8d, 4D6E6157h
0x140004396  call    cs:__imp_ExAllocatePool2
0x14000439d  nop     dword ptr [rax+rax+00h]
0x1400043a2  mov     [rdi+48h], rax
0x1400043a6  test    rax, rax
0x1400043a9  jz      loc_14000469A
0x1400043af  movzx   eax, word ptr [rsi+2]
0x1400043b3  lea     rcx, [rdi+40h]; DestinationString
0x1400043b7  mov     [rdi+42h], ax
0x1400043bb  mov     rdx, rsi; SourceString
0x1400043be  movzx   eax, word ptr [rsi]
0x1400043c1  mov     [rdi+40h], ax
0x1400043c5  mov     [rsp+48h+arg_0], rbx
0x1400043ca  call    cs:__imp_RtlCopyUnicodeString
0x1400043d1  nop     dword ptr [rax+rax+00h]
0x1400043d6  movzx   eax, word ptr [rdi+40h]
0x1400043da  shr     ax, 1
0x1400043dd  mov     rbx, [rsp+48h+arg_0]
0x1400043e2  jz      short loc_140004405
0x1400043e4  mov     rdx, [rdi+48h]
0x1400043e8  mov     r8d, 0FFFFh
0x1400043ee  xchg    ax, ax
0x1400043f0  movzx   ecx, ax
0x1400043f3  cmp     word ptr [rdx+rcx*2-2], 7Bh ; '{'
0x1400043f9  jz      loc_140004504
0x1400043ff  add     ax, r8w
0x140004403  jnz     short loc_1400043F0
0x140004405  lea     rcx, [rdi+1F8h]; SpinLock
0x14000440c  call    cs:__imp_KeInitializeSpinLock
0x140004413  nop     dword ptr [rax+rax+00h]
0x140004418  lea     rax, [rdi+0E0h]
0x14000441f  mov     [rax+8], rax
0x140004423  lea     rcx, [rdi+210h]; Event
0x14000442a  mov     [rax], rax
0x14000442d  lea     rax, [rdi+0F0h]
0x140004434  mov     [rax+8], rax
0x140004438  mov     [rax], rax
0x14000443b  lea     rax, [rdi+0D0h]
0x140004442  mov     [rax+8], rax
0x140004446  mov     [rax], rax
0x140004449  call    cs:__imp_NdisInitializeEvent
0x140004450  nop     dword ptr [rax+rax+00h]
0x140004455  lea     rcx, [rdi+228h]; Event
0x14000445c  call    cs:__imp_NdisInitializeEvent
0x140004463  nop     dword ptr [rax+rax+00h]
0x140004468  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14000446f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004476  nop     dword ptr [rax+rax+00h]
0x14000447b  mov     byte ptr cs:WPP_MAIN_CB+148h, al
0x140004481  lea     rcx, qword_14001E1B8
0x140004488  mov     rax, cs:qword_14001E1C0
0x14000448f  cmp     [rax], rcx
0x140004492  jnz     loc_1400046F5
0x140004498  mov     [rdi+8], rax
0x14000449c  mov     [rdi], rcx
0x14000449f  mov     [rax], rdi
0x1400044a2  mov     eax, cs:dword_14001E1B0
0x1400044a8  inc     eax
0x1400044aa  mov     cs:qword_14001E1C0, rdi
0x1400044b1  cmp     eax, cs:dword_14001E1B4
0x1400044b7  mov     cs:dword_14001E1B0, eax
0x1400044bd  ja      loc_1400046FC
0x1400044c3  movzx   edx, byte ptr cs:WPP_MAIN_CB+148h; NewIrql
0x1400044ca  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400044d1  call    cs:__imp_KeReleaseSpinLock
0x1400044d8  nop     dword ptr [rax+rax+00h]
0x1400044dd  mov     dword ptr [rdi+10h], 1
0x1400044e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044eb  cmp     rcx, rbp
0x1400044ee  jnz     short loc_140004552
0x1400044f0  mov     rax, rdi
0x1400044f3  mov     rbp, [rsp+48h+arg_8]
0x1400044f8  mov     rsi, [rsp+48h+arg_10]
0x1400044fd  add     rsp, 40h
0x140004501  pop     rdi
0x140004502  retn
0x140004504  mov     ecx, 1
0x140004509  mov     dword ptr [rsp+48h+GuidString+4], 0
0x140004511  sub     cx, ax
0x140004514  lea     rdx, [rdi+50h]; Guid
0x140004518  add     cx, cx
0x14000451b  add     cx, [rsi]
0x14000451e  mov     [rsp+48h+GuidString.Length], cx
0x140004523  mov     [rsp+48h+GuidString.MaximumLength], cx
0x140004528  movzx   ecx, ax
0x14000452b  mov     rax, [rsi+8]
0x14000452f  sub     rax, 2
0x140004533  lea     rcx, [rax+rcx*2]
0x140004537  mov     [rsp+48h+GuidString.Buffer], rcx
0x14000453c  lea     rcx, [rsp+48h+GuidString]; GuidString
0x140004541  call    cs:__imp_RtlGUIDFromString
0x140004548  nop     dword ptr [rax+rax+00h]
0x14000454d  jmp     loc_140004405
0x140004552  mov     eax, [rcx+2Ch]
0x140004555  test    al, 40h
0x140004557  jnz     loc_140004707
0x14000455d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004564  cmp     rcx, rbp
0x140004567  jz      short loc_1400044F0
0x140004569  mov     edx, [rcx+2Ch]
0x14000456c  test    dl, 40h
0x14000456f  jz      loc_1400044F0
0x140004575  cmp     byte ptr [rcx+29h], 5
0x140004579  jb      loc_1400044F0
0x14000457f  mov     rcx, [rcx+18h]
0x140004583  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000458a  mov     edx, 17h
0x14000458f  call    WPP_SF_
0x140004594  jmp     loc_1400044F0
0x140004599  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045a0  cmp     rcx, rbp
0x1400045a3  jnz     loc_14000463C
0x1400045a9  xor     eax, eax
0x1400045ab  mov     rbp, [rsp+48h+arg_8]
0x1400045b0  mov     rsi, [rsp+48h+arg_10]
0x1400045b5  add     rsp, 40h
0x1400045b9  pop     rdi
0x1400045ba  retn
0x1400045bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045c3  cmp     rcx, rbp
0x1400045c6  jnz     loc_14000466B
0x1400045cc  xor     edx, edx; Tag
0x1400045ce  mov     rcx, rdi; P
0x1400045d1  call    cs:__imp_ExFreePoolWithTag
0x1400045d8  nop     dword ptr [rax+rax+00h]
0x1400045dd  mov     rbp, [rsp+48h+arg_8]
0x1400045e2  xor     eax, eax
0x1400045e4  mov     rsi, [rsp+48h+arg_10]
0x1400045e9  add     rsp, 40h
0x1400045ed  pop     rdi
0x1400045ee  retn
0x1400045f0  cmp     byte ptr [rcx+29h], 5
0x1400045f4  jb      loc_140004310
0x1400045fa  mov     rcx, [rcx+18h]
0x1400045fe  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140004605  mov     edx, 11h
0x14000460a  call    WPP_SF_
0x14000460f  jmp     loc_140004310
0x140004614  cmp     byte ptr [rcx+29h], 5
0x140004618  jb      loc_140004327
0x14000461e  mov     r9, [rsi+8]
0x140004622  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140004629  mov     rcx, [rcx+18h]
0x14000462d  mov     edx, 12h
0x140004632  call    WPP_SF_S
0x140004637  jmp     loc_140004327
0x14000463c  mov     eax, [rcx+2Ch]
0x14000463f  test    al, 40h
0x140004641  jz      loc_1400045A9
0x140004647  cmp     byte ptr [rcx+29h], 2
0x14000464b  jb      loc_1400045A9
0x140004651  mov     rcx, [rcx+18h]
0x140004655  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000465c  mov     edx, 13h
0x140004661  call    WPP_SF_
0x140004666  jmp     loc_1400045A9
0x14000466b  mov     eax, [rcx+2Ch]
0x14000466e  test    al, 40h
0x140004670  jz      loc_1400045CC
0x140004676  cmp     byte ptr [rcx+29h], 2
0x14000467a  jb      loc_1400045CC
0x140004680  mov     rcx, [rcx+18h]
0x140004684  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000468b  mov     edx, 14h
0x140004690  call    WPP_SF_
0x140004695  jmp     loc_1400045CC
0x14000469a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046a1  cmp     rcx, rbp
0x1400046a4  jz      short loc_1400046CD
0x1400046a6  mov     eax, [rcx+2Ch]
0x1400046a9  test    al, 40h
0x1400046ab  jz      short loc_1400046CD
0x1400046ad  cmp     byte ptr [rcx+29h], 2
0x1400046b1  jb      short loc_1400046CD
0x1400046b3  movzx   r9d, word ptr [rsi+2]
0x1400046b8  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x1400046bf  mov     rcx, [rcx+18h]
0x1400046c3  mov     edx, 15h
0x1400046c8  call    WPP_SF_d
0x1400046cd  mov     rcx, [rdi+68h]; NdisIoWorkItemHandle
0x1400046d1  call    cs:__imp_NdisFreeIoWorkItem
0x1400046d8  nop     dword ptr [rax+rax+00h]
0x1400046dd  xor     edx, edx; Tag
0x1400046df  mov     rcx, rdi; P
0x1400046e2  call    cs:__imp_ExFreePoolWithTag
0x1400046e9  nop     dword ptr [rax+rax+00h]
0x1400046ee  xor     eax, eax
0x1400046f0  jmp     loc_1400044F3
0x1400046f5  mov     ecx, 3
0x1400046fa  int     29h; Win8: RtlFailFast(ecx)
0x1400046fc  mov     cs:dword_14001E1B4, eax
0x140004702  jmp     loc_1400044C3
0x140004707  cmp     byte ptr [rcx+29h], 5
0x14000470b  jb      loc_14000455D
0x140004711  mov     r9, [rdi+48h]
0x140004715  mov     rcx, [rcx+18h]
0x140004719  mov     [rsp+48h+var_28], rdi
0x14000471e  call    WPP_SF_Sq
0x140004723  jmp     loc_14000455D
```
