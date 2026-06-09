# FveDcbIfcFilterIoctl

- ea: `0x14008cdd0`
- end: `0x14008d0ec`
- name: `FveDcbIfcFilterIoctl`
- size: `796`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140008e44`
- `0x14000bc1c`
- `0x14000e514`
- `0x14002cbac`
- `0x140051480`
- `0x14008cdd0`
- `0x1400ddd84`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008cf8a`
- `ntoskrnl!IofCompleteRequest` at `0x14008cfab`
- `ntoskrnl!IofCompleteRequest` at `0x14008cf8a`
- `ntoskrnl!IofCompleteRequest` at `0x14008cfab`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008ce79`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008ce79`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008cf37`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008cf37`
- `ntoskrnl!PsGetCurrentProcess` at `0x14008cec4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14008cec4`

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
0x14008cdd0  push    rbx
0x14008cdd2  push    rbp
0x14008cdd3  push    rsi
0x14008cdd4  push    rdi
0x14008cdd5  push    r12
0x14008cdd7  push    r13
0x14008cdd9  push    r14
0x14008cddb  push    r15
0x14008cddd  sub     rsp, 48h
0x14008cde1  xor     r15d, r15d
0x14008cde4  lea     rax, WPP_GLOBAL_Control
0x14008cdeb  mov     rsi, rdx
0x14008cdee  mov     rdi, rcx
0x14008cdf1  test    rcx, rcx
0x14008cdf4  jz      loc_14008CFBC
0x14008cdfa  mov     rbp, [rcx+0C8h]
0x14008ce01  test    rbp, rbp
0x14008ce04  jz      loc_14008CFBC
0x14008ce0a  mov     r8, [rdx+0B8h]
0x14008ce11  mov     ebx, 0C0000002h
0x14008ce16  mov     r12d, [r8+18h]
0x14008ce1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ce21  cmp     rcx, rax
0x14008ce24  jz      short loc_14008CE33
0x14008ce26  test    dword ptr [rcx+2Ch], 400h
0x14008ce2d  jnz     loc_14008CFCA
0x14008ce33  cmp     dword ptr [rdi+0B0h], 3
0x14008ce3a  jnz     loc_14008CF43
0x14008ce40  mov     r14, [rdi+8]
0x14008ce44  test    r14, r14
0x14008ce47  jz      loc_14008CF77
0x14008ce4d  mov     r14, [r14+0C8h]
0x14008ce54  test    r14, r14
0x14008ce57  jz      loc_14008CF77
0x14008ce5d  mov     r9d, 1; Line
0x14008ce63  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x14008ce6b  lea     r8, File; File
0x14008ce72  mov     rdx, r14; Tag
0x14008ce75  lea     rcx, [r14+8]; RemoveLock
0x14008ce79  call    cs:__imp_IoAcquireRemoveLockEx
0x14008ce80  nop     dword ptr [rax+rax+00h]
0x14008ce85  mov     ebx, eax
0x14008ce87  test    eax, eax
0x14008ce89  js      loc_14008CFFB
0x14008ce8f  mov     rax, [r14]
0x14008ce92  test    rax, rax
0x14008ce95  jz      loc_14008CF98
0x14008ce9b  mov     r15, [r14]
0x14008ce9e  mov     eax, r12d
0x14008cea1  shr     eax, 10h
0x14008cea4  cmp     eax, 4556h
0x14008cea9  jnz     loc_14008D04F
0x14008ceaf  mov     edx, r12d
0x14008ceb2  mov     rcx, r15
0x14008ceb5  call    FveCheckControlAllowed
0x14008ceba  mov     ebx, eax
0x14008cebc  test    eax, eax
0x14008cebe  js      loc_14008D0A7
0x14008cec4  call    cs:__imp_PsGetCurrentProcess
0x14008cecb  nop     dword ptr [rax+rax+00h]
0x14008ced0  mov     [rsi+78h], rax
0x14008ced4  mov     rdi, cs:WPP_GLOBAL_Control
0x14008cedb  lea     rax, WPP_GLOBAL_Control
0x14008cee2  cmp     rdi, rax
0x14008cee5  jz      short loc_14008CEF4
0x14008cee7  test    dword ptr [rdi+2Ch], 400h
0x14008ceee  jnz     loc_14008D064
0x14008cef4  lea     rax, FveFailIrpOnRemoval
0x14008cefb  mov     [rsp+88h+var_60], rsi
0x14008cf00  mov     r9d, 1
0x14008cf06  mov     qword ptr [rsp+88h+RemlockSize], rax
0x14008cf0b  mov     r8, rsi
0x14008cf0e  lea     rdx, IoctlFveWorker
0x14008cf15  mov     rcx, r15
0x14008cf18  call    FveQueueAutoWorkItemEx
0x14008cf1d  mov     ebx, eax
0x14008cf1f  cmp     eax, 103h
0x14008cf24  jnz     loc_14008D0A7
0x14008cf2a  mov     r8d, 20h ; ' '; RemlockSize
0x14008cf30  lea     rcx, [r14+8]; RemoveLock
0x14008cf34  mov     rdx, r14; Tag
0x14008cf37  call    cs:__imp_IoReleaseRemoveLockEx
0x14008cf3e  nop     dword ptr [rax+rax+00h]
0x14008cf43  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cf4a  lea     rax, WPP_GLOBAL_Control
0x14008cf51  cmp     rcx, rax
0x14008cf54  jz      short loc_14008CF63
0x14008cf56  test    dword ptr [rcx+2Ch], 400h
0x14008cf5d  jnz     loc_14008D0C5
0x14008cf63  mov     eax, ebx
0x14008cf65  add     rsp, 48h
0x14008cf69  pop     r15
0x14008cf6b  pop     r14
0x14008cf6d  pop     r13
0x14008cf6f  pop     r12
0x14008cf71  pop     rdi
0x14008cf72  pop     rsi
0x14008cf73  pop     rbp
0x14008cf74  pop     rbx
0x14008cf75  retn
0x14008cf77  mov     eax, 0C000000Dh
0x14008cf7c  mov     [rsi+38h], r15
0x14008cf80  mov     [rsi+30h], eax
0x14008cf83  mov     ebx, eax
0x14008cf85  xor     edx, edx; PriorityBoost
0x14008cf87  mov     rcx, rsi; Irp
0x14008cf8a  call    cs:__imp_IofCompleteRequest
0x14008cf91  nop     dword ptr [rax+rax+00h]
0x14008cf96  jmp     short loc_14008CF43
0x14008cf98  mov     eax, 0C000000Dh
0x14008cf9d  mov     [rsi+38h], r15
0x14008cfa1  mov     ebx, eax
0x14008cfa3  mov     [rsi+30h], eax
0x14008cfa6  xor     edx, edx; PriorityBoost
0x14008cfa8  mov     rcx, rsi; Irp
0x14008cfab  call    cs:__imp_IofCompleteRequest
0x14008cfb2  nop     dword ptr [rax+rax+00h]
0x14008cfb7  jmp     loc_14008CF2A
0x14008cfbc  mov     eax, 0C000000Dh
0x14008cfc1  mov     [rdx+38h], r15
0x14008cfc5  mov     [rdx+30h], eax
0x14008cfc8  jmp     short loc_14008CF83
0x14008cfca  cmp     byte ptr [rcx+29h], 5
0x14008cfce  jb      loc_14008CE33
0x14008cfd4  mov     rax, [r8+30h]
0x14008cfd8  mov     edx, 48h ; 'H'
0x14008cfdd  mov     r9d, [rbp+8]
0x14008cfe1  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cfe8  mov     rcx, [rcx+18h]
0x14008cfec  mov     qword ptr [rsp+88h+RemlockSize], rax
0x14008cff1  call    WPP_SF_Lq
0x14008cff6  jmp     loc_14008CE33
0x14008cffb  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d002  lea     rax, WPP_GLOBAL_Control
0x14008d009  cmp     rcx, rax
0x14008d00c  jz      short loc_14008D035
0x14008d00e  test    dword ptr [rcx+2Ch], 400h
0x14008d015  jz      short loc_14008D035
0x14008d017  cmp     byte ptr [rcx+29h], 2
0x14008d01b  jb      short loc_14008D035
0x14008d01d  mov     rcx, [rcx+18h]
0x14008d021  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008d028  mov     edx, 49h ; 'I'
0x14008d02d  mov     r9d, ebx
0x14008d030  call    WPP_SF_d
0x14008d035  cmp     ebx, 0C0000002h
0x14008d03b  mov     [rsi+38h], r15
0x14008d03f  mov     eax, 0C0000001h
0x14008d044  cmovz   ebx, eax
0x14008d047  mov     [rsi+30h], ebx
0x14008d04a  jmp     loc_14008CF85
0x14008d04f  mov     ebx, 0C0000002h
0x14008d054  cmp     eax, 5446h
0x14008d059  jnz     loc_14008CF2A
0x14008d05f  jmp     loc_14008CEAF
0x14008d064  cmp     byte ptr [rdi+29h], 5
0x14008d068  jb      loc_14008CEF4
0x14008d06e  mov     ebx, [rbp+8]
0x14008d071  mov     ecx, r12d
0x14008d074  mov     rdi, [rdi+18h]
0x14008d078  call    FveIoctlToString
0x14008d07d  mov     [rsp+88h+var_58], rsi
0x14008d082  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008d089  mov     [rsp+88h+var_60], rax
0x14008d08e  mov     edx, 4Ah ; 'J'
0x14008d093  mov     r9, r15
0x14008d096  mov     [rsp+88h+RemlockSize], ebx
0x14008d09a  mov     rcx, rdi
0x14008d09d  call    WPP_SF_qLsq
0x14008d0a2  jmp     loc_14008CEF4
0x14008d0a7  cmp     ebx, 0C0000002h
0x14008d0ad  mov     qword ptr [rsi+38h], 0
0x14008d0b5  mov     eax, 0C0000001h
0x14008d0ba  cmovz   ebx, eax
0x14008d0bd  mov     [rsi+30h], ebx
0x14008d0c0  jmp     loc_14008CFA6
0x14008d0c5  cmp     byte ptr [rcx+29h], 5
0x14008d0c9  jb      loc_14008CF63
0x14008d0cf  mov     rcx, [rcx+18h]
0x14008d0d3  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008d0da  mov     edx, 4Bh ; 'K'
0x14008d0df  mov     r9d, ebx
0x14008d0e2  call    WPP_SF_d
0x14008d0e7  jmp     loc_14008CF63
```
