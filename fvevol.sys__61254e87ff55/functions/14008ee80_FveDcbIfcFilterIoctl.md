# FveDcbIfcFilterIoctl

- ea: `0x14008ee80`
- end: `0x14008f19c`
- name: `FveDcbIfcFilterIoctl`
- size: `796`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140008f04`
- `0x14000bda8`
- `0x14000e6fc`
- `0x14002dbac`
- `0x140053480`
- `0x14008ee80`
- `0x1400e0468`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008f03a`
- `ntoskrnl!IofCompleteRequest` at `0x14008f05b`
- `ntoskrnl!IofCompleteRequest` at `0x14008f03a`
- `ntoskrnl!IofCompleteRequest` at `0x14008f05b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008ef29`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008ef29`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008efe7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008efe7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14008ef74`
- `ntoskrnl!PsGetCurrentProcess` at `0x14008ef74`

## pseudocode

```c
__int64 __fastcall FveDcbIfcFilterIoctl(__int64 a1, IRP *a2)
{
  __int64 v4; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  NTSTATUS v6; // ebx
  DWORD LowPart; // r12d
  __int64 v8; // r14
  _QWORD *v9; // r14
  __int64 v10; // r15
  int v12; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  __int64 v14; // rax

  if ( !a1 || (v4 = *(_QWORD *)(a1 + 200)) == 0 )
  {
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741811;
    goto LABEL_20;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v6 = -1073741822;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_Lq(
      WPP_GLOBAL_Control->AttachedDevice,
      72,
      WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
      *(unsigned int *)(v4 + 8),
      CurrentStackLocation->FileObject);
  }
  if ( *(_DWORD *)(a1 + 176) == 3 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    if ( v8 )
    {
      v9 = *(_QWORD **)(v8 + 200);
      if ( v9 )
      {
        v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 1), v9, File, 1u, 0x20u);
        if ( v6 >= 0 )
        {
          if ( *v9 )
          {
            v10 = *v9;
            if ( HIWORD(LowPart) != 17750 )
            {
              v6 = -1073741822;
              if ( HIWORD(LowPart) != 21574 )
                goto LABEL_15;
            }
            v6 = FveCheckControlAllowed(*v9, LowPart);
            if ( v6 >= 0 )
            {
              a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)PsGetCurrentProcess();
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v12 = *(_DWORD *)(v4 + 8);
                AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                v14 = FveIoctlToString(LowPart);
                WPP_SF_qLsq(
                  (_DWORD)AttachedDevice,
                  74,
                  (unsigned int)WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
                  v10,
                  v12,
                  v14,
                  (char)a2);
              }
              v6 = FveQueueAutoWorkItemEx(
                     v10,
                     (unsigned int)IoctlFveWorker,
                     (_DWORD)a2,
                     1,
                     (__int64)FveFailIrpOnRemoval,
                     (__int64)a2);
              if ( v6 == 259 )
                goto LABEL_15;
            }
            a2->IoStatus.Information = 0;
            if ( v6 == -1073741822 )
              v6 = -1073741823;
            a2->IoStatus.Status = v6;
          }
          else
          {
            a2->IoStatus.Information = 0;
            v6 = -1073741811;
            a2->IoStatus.Status = -1073741811;
          }
          IofCompleteRequest(a2, 0);
LABEL_15:
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v9 + 1), v9, 0x20u);
          goto LABEL_16;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            73,
            WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
            (unsigned int)v6);
        }
        a2->IoStatus.Information = 0;
        if ( v6 == -1073741822 )
          v6 = -1073741823;
        a2->IoStatus.Status = v6;
LABEL_21:
        IofCompleteRequest(a2, 0);
        goto LABEL_16;
      }
    }
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741811;
LABEL_20:
    v6 = -1073741811;
    goto LABEL_21;
  }
LABEL_16:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14008ee80  push    rbx
0x14008ee82  push    rbp
0x14008ee83  push    rsi
0x14008ee84  push    rdi
0x14008ee85  push    r12
0x14008ee87  push    r13
0x14008ee89  push    r14
0x14008ee8b  push    r15
0x14008ee8d  sub     rsp, 48h
0x14008ee91  xor     r15d, r15d
0x14008ee94  lea     rax, WPP_GLOBAL_Control
0x14008ee9b  mov     rsi, rdx
0x14008ee9e  mov     rdi, rcx
0x14008eea1  test    rcx, rcx
0x14008eea4  jz      loc_14008F06C
0x14008eeaa  mov     rbp, [rcx+0C8h]
0x14008eeb1  test    rbp, rbp
0x14008eeb4  jz      loc_14008F06C
0x14008eeba  mov     r8, [rdx+0B8h]
0x14008eec1  mov     ebx, 0C0000002h
0x14008eec6  mov     r12d, [r8+18h]
0x14008eeca  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eed1  cmp     rcx, rax
0x14008eed4  jz      short loc_14008EEE3
0x14008eed6  test    dword ptr [rcx+2Ch], 400h
0x14008eedd  jnz     loc_14008F07A
0x14008eee3  cmp     dword ptr [rdi+0B0h], 3
0x14008eeea  jnz     loc_14008EFF3
0x14008eef0  mov     r14, [rdi+8]
0x14008eef4  test    r14, r14
0x14008eef7  jz      loc_14008F027
0x14008eefd  mov     r14, [r14+0C8h]
0x14008ef04  test    r14, r14
0x14008ef07  jz      loc_14008F027
0x14008ef0d  mov     r9d, 1; Line
0x14008ef13  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x14008ef1b  lea     r8, File; File
0x14008ef22  mov     rdx, r14; Tag
0x14008ef25  lea     rcx, [r14+8]; RemoveLock
0x14008ef29  call    cs:__imp_IoAcquireRemoveLockEx
0x14008ef30  nop     dword ptr [rax+rax+00h]
0x14008ef35  mov     ebx, eax
0x14008ef37  test    eax, eax
0x14008ef39  js      loc_14008F0AB
0x14008ef3f  mov     rax, [r14]
0x14008ef42  test    rax, rax
0x14008ef45  jz      loc_14008F048
0x14008ef4b  mov     r15, [r14]
0x14008ef4e  mov     eax, r12d
0x14008ef51  shr     eax, 10h
0x14008ef54  cmp     eax, 4556h
0x14008ef59  jnz     loc_14008F0FF
0x14008ef5f  mov     edx, r12d
0x14008ef62  mov     rcx, r15
0x14008ef65  call    FveCheckControlAllowed
0x14008ef6a  mov     ebx, eax
0x14008ef6c  test    eax, eax
0x14008ef6e  js      loc_14008F157
0x14008ef74  call    cs:__imp_PsGetCurrentProcess
0x14008ef7b  nop     dword ptr [rax+rax+00h]
0x14008ef80  mov     [rsi+78h], rax
0x14008ef84  mov     rdi, cs:WPP_GLOBAL_Control
0x14008ef8b  lea     rax, WPP_GLOBAL_Control
0x14008ef92  cmp     rdi, rax
0x14008ef95  jz      short loc_14008EFA4
0x14008ef97  test    dword ptr [rdi+2Ch], 400h
0x14008ef9e  jnz     loc_14008F114
0x14008efa4  lea     rax, FveFailIrpOnRemoval
0x14008efab  mov     [rsp+88h+var_60], rsi
0x14008efb0  mov     r9d, 1
0x14008efb6  mov     qword ptr [rsp+88h+RemlockSize], rax
0x14008efbb  mov     r8, rsi
0x14008efbe  lea     rdx, IoctlFveWorker
0x14008efc5  mov     rcx, r15
0x14008efc8  call    FveQueueAutoWorkItemEx
0x14008efcd  mov     ebx, eax
0x14008efcf  cmp     eax, 103h
0x14008efd4  jnz     loc_14008F157
0x14008efda  mov     r8d, 20h ; ' '; RemlockSize
0x14008efe0  lea     rcx, [r14+8]; RemoveLock
0x14008efe4  mov     rdx, r14; Tag
0x14008efe7  call    cs:__imp_IoReleaseRemoveLockEx
0x14008efee  nop     dword ptr [rax+rax+00h]
0x14008eff3  mov     rcx, cs:WPP_GLOBAL_Control
0x14008effa  lea     rax, WPP_GLOBAL_Control
0x14008f001  cmp     rcx, rax
0x14008f004  jz      short loc_14008F013
0x14008f006  test    dword ptr [rcx+2Ch], 400h
0x14008f00d  jnz     loc_14008F175
0x14008f013  mov     eax, ebx
0x14008f015  add     rsp, 48h
0x14008f019  pop     r15
0x14008f01b  pop     r14
0x14008f01d  pop     r13
0x14008f01f  pop     r12
0x14008f021  pop     rdi
0x14008f022  pop     rsi
0x14008f023  pop     rbp
0x14008f024  pop     rbx
0x14008f025  retn
0x14008f027  mov     eax, 0C000000Dh
0x14008f02c  mov     [rsi+38h], r15
0x14008f030  mov     [rsi+30h], eax
0x14008f033  mov     ebx, eax
0x14008f035  xor     edx, edx; PriorityBoost
0x14008f037  mov     rcx, rsi; Irp
0x14008f03a  call    cs:__imp_IofCompleteRequest
0x14008f041  nop     dword ptr [rax+rax+00h]
0x14008f046  jmp     short loc_14008EFF3
0x14008f048  mov     eax, 0C000000Dh
0x14008f04d  mov     [rsi+38h], r15
0x14008f051  mov     ebx, eax
0x14008f053  mov     [rsi+30h], eax
0x14008f056  xor     edx, edx; PriorityBoost
0x14008f058  mov     rcx, rsi; Irp
0x14008f05b  call    cs:__imp_IofCompleteRequest
0x14008f062  nop     dword ptr [rax+rax+00h]
0x14008f067  jmp     loc_14008EFDA
0x14008f06c  mov     eax, 0C000000Dh
0x14008f071  mov     [rdx+38h], r15
0x14008f075  mov     [rdx+30h], eax
0x14008f078  jmp     short loc_14008F033
0x14008f07a  cmp     byte ptr [rcx+29h], 5
0x14008f07e  jb      loc_14008EEE3
0x14008f084  mov     rax, [r8+30h]
0x14008f088  mov     edx, 48h ; 'H'
0x14008f08d  mov     r9d, [rbp+8]
0x14008f091  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008f098  mov     rcx, [rcx+18h]
0x14008f09c  mov     qword ptr [rsp+88h+RemlockSize], rax
0x14008f0a1  call    WPP_SF_Lq
0x14008f0a6  jmp     loc_14008EEE3
0x14008f0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f0b2  lea     rax, WPP_GLOBAL_Control
0x14008f0b9  cmp     rcx, rax
0x14008f0bc  jz      short loc_14008F0E5
0x14008f0be  test    dword ptr [rcx+2Ch], 400h
0x14008f0c5  jz      short loc_14008F0E5
0x14008f0c7  cmp     byte ptr [rcx+29h], 2
0x14008f0cb  jb      short loc_14008F0E5
0x14008f0cd  mov     rcx, [rcx+18h]
0x14008f0d1  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008f0d8  mov     edx, 49h ; 'I'
0x14008f0dd  mov     r9d, ebx
0x14008f0e0  call    WPP_SF_d
0x14008f0e5  cmp     ebx, 0C0000002h
0x14008f0eb  mov     [rsi+38h], r15
0x14008f0ef  mov     eax, 0C0000001h
0x14008f0f4  cmovz   ebx, eax
0x14008f0f7  mov     [rsi+30h], ebx
0x14008f0fa  jmp     loc_14008F035
0x14008f0ff  mov     ebx, 0C0000002h
0x14008f104  cmp     eax, 5446h
0x14008f109  jnz     loc_14008EFDA
0x14008f10f  jmp     loc_14008EF5F
0x14008f114  cmp     byte ptr [rdi+29h], 5
0x14008f118  jb      loc_14008EFA4
0x14008f11e  mov     ebx, [rbp+8]
0x14008f121  mov     ecx, r12d
0x14008f124  mov     rdi, [rdi+18h]
0x14008f128  call    FveIoctlToString
0x14008f12d  mov     [rsp+88h+var_58], rsi
0x14008f132  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008f139  mov     [rsp+88h+var_60], rax
0x14008f13e  mov     edx, 4Ah ; 'J'
0x14008f143  mov     r9, r15
0x14008f146  mov     [rsp+88h+RemlockSize], ebx
0x14008f14a  mov     rcx, rdi
0x14008f14d  call    WPP_SF_qLsq
0x14008f152  jmp     loc_14008EFA4
0x14008f157  cmp     ebx, 0C0000002h
0x14008f15d  mov     qword ptr [rsi+38h], 0
0x14008f165  mov     eax, 0C0000001h
0x14008f16a  cmovz   ebx, eax
0x14008f16d  mov     [rsi+30h], ebx
0x14008f170  jmp     loc_14008F056
0x14008f175  cmp     byte ptr [rcx+29h], 5
0x14008f179  jb      loc_14008F013
0x14008f17f  mov     rcx, [rcx+18h]
0x14008f183  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008f18a  mov     edx, 4Bh ; 'K'
0x14008f18f  mov     r9d, ebx
0x14008f192  call    WPP_SF_d
0x14008f197  jmp     loc_14008F013
```
