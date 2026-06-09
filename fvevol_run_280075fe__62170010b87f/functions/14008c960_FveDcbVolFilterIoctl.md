# FveDcbVolFilterIoctl

- ea: `0x14008c960`
- end: `0x14008ccf5`
- name: `FveDcbVolFilterIoctl`
- size: `917`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000a150`
- `0x14008c960`
- `0x14008ccfc`
- `0x1400dcd40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008caa5`
- `ntoskrnl!IofCompleteRequest` at `0x14008cb21`
- `ntoskrnl!IofCompleteRequest` at `0x14008cb49`
- `ntoskrnl!IofCompleteRequest` at `0x14008cb82`
- `ntoskrnl!IofCompleteRequest` at `0x14008cc1c`
- `ntoskrnl!IofCompleteRequest` at `0x14008caa5`
- `ntoskrnl!IofCompleteRequest` at `0x14008cb21`
- `ntoskrnl!IofCompleteRequest` at `0x14008cb49`
- `ntoskrnl!IofCompleteRequest` at `0x14008cb82`
- `ntoskrnl!IofCompleteRequest` at `0x14008cc1c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008c9f7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008c9f7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008cad7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008cad7`

## pseudocode

```c
__int64 __fastcall FveDcbVolFilterIoctl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  unsigned int v5; // edi
  DWORD LowPart; // ebp
  _QWORD *v7; // r14
  NTSTATUS v8; // eax
  int v9; // esi
  __int64 v10; // rsi
  unsigned int DeviceName; // eax

  if ( !a1 || !*(_QWORD *)(a1 + 200) )
  {
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741811;
    goto LABEL_24;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = -1073741822;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      65,
      WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
      CurrentStackLocation->FileObject);
  }
  if ( *(_DWORD *)(a1 + 176) == 2 )
  {
    v7 = *(_QWORD **)(a1 + 200);
    if ( v7 )
    {
      v8 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v7 + 1), v7, File, 1u, 0x20u);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            66,
            WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
            (unsigned int)v8);
        }
        a2->IoStatus.Information = 0;
        if ( v9 == -1073741822 )
          v9 = -1073741823;
        v5 = v9;
        a2->IoStatus.Status = v9;
        IofCompleteRequest(a2, 0);
      }
      else
      {
        if ( *v7 )
        {
          v10 = *v7;
          if ( (*(_DWORD *)(*(_QWORD *)*v7 + 48LL) & 0x80u) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
            }
            v5 = -1073741810;
            a2->IoStatus.Information = 0;
            a2->IoStatus.Status = -1073741810;
            IofCompleteRequest(a2, 0);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, *v7);
            }
            FvePerfTraceDevOp(v10, FVE_PERF_FVE_IOCTL_START, LowPart);
            if ( LowPart == 5046280 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
              }
              DeviceName = IoctlFveQueryDeviceName(v10, a2);
              v5 = DeviceName;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  70,
                  WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
                  DeviceName);
              }
              a2->IoStatus.Status = v5;
              IofCompleteRequest(a2, 0);
            }
            FvePerfTraceDevOp(v10, FVE_PERF_FVE_IOCTL_STOP, LowPart);
          }
        }
        else
        {
          a2->IoStatus.Information = 0;
          a2->IoStatus.Status = -1073741811;
          v5 = -1073741811;
          IofCompleteRequest(a2, 0);
        }
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v7 + 1), v7, 0x20u);
      }
      goto LABEL_20;
    }
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741811;
LABEL_24:
    v5 = -1073741811;
    IofCompleteRequest(a2, 0);
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x14008c960  push    rbx
0x14008c962  push    rbp
0x14008c963  push    rsi
0x14008c964  push    rdi
0x14008c965  push    r12
0x14008c967  push    r13
0x14008c969  push    r14
0x14008c96b  push    r15
0x14008c96d  sub     rsp, 38h
0x14008c971  xor     r12d, r12d
0x14008c974  lea     rax, WPP_GLOBAL_Control
0x14008c97b  mov     rbx, rdx
0x14008c97e  mov     rsi, rcx
0x14008c981  test    rcx, rcx
0x14008c984  jz      loc_14008CB0E
0x14008c98a  cmp     [rcx+0C8h], r12
0x14008c991  jz      loc_14008CB0E
0x14008c997  mov     r9, [rdx+0B8h]
0x14008c99e  mov     edi, 0C0000002h
0x14008c9a3  mov     ebp, [r9+18h]
0x14008c9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c9ae  cmp     rcx, rax
0x14008c9b1  jz      short loc_14008C9BE
0x14008c9b3  bt      dword ptr [rcx+2Ch], 0Ah
0x14008c9b8  jb      loc_14008CB93
0x14008c9be  cmp     dword ptr [rsi+0B0h], 2
0x14008c9c5  jnz     loc_14008CB2D
0x14008c9cb  mov     r14, [rsi+0C8h]
0x14008c9d2  test    r14, r14
0x14008c9d5  jz      loc_14008CBBB
0x14008c9db  mov     r9d, 1; Line
0x14008c9e1  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x14008c9e9  lea     r8, File; File
0x14008c9f0  mov     rdx, r14; Tag
0x14008c9f3  lea     rcx, [r14+8]; RemoveLock
0x14008c9f7  call    cs:__imp_IoAcquireRemoveLockEx
0x14008c9fe  nop     dword ptr [rax+rax+00h]
0x14008ca03  mov     esi, eax
0x14008ca05  test    eax, eax
0x14008ca07  js      loc_14008CBCC
0x14008ca0d  mov     rax, [r14]
0x14008ca10  test    rax, rax
0x14008ca13  jz      loc_14008CB36
0x14008ca19  mov     rsi, [r14]
0x14008ca1c  mov     rax, [rsi]
0x14008ca1f  mov     ecx, [rax+30h]
0x14008ca22  test    cl, cl
0x14008ca24  js      loc_14008CB5A
0x14008ca2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ca31  lea     r12, WPP_GLOBAL_Control
0x14008ca38  cmp     rcx, r12
0x14008ca3b  jz      short loc_14008CA48
0x14008ca3d  bt      dword ptr [rcx+2Ch], 0Ah
0x14008ca42  jb      loc_14008CC5C
0x14008ca48  mov     r8d, ebp
0x14008ca4b  lea     rdx, FVE_PERF_FVE_IOCTL_START
0x14008ca52  mov     rcx, rsi
0x14008ca55  call    FvePerfTraceDevOp
0x14008ca5a  cmp     ebp, 4D0008h
0x14008ca60  jnz     short loc_14008CAB1
0x14008ca62  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ca69  cmp     rcx, r12
0x14008ca6c  jz      short loc_14008CA79
0x14008ca6e  bt      dword ptr [rcx+2Ch], 0Ah
0x14008ca73  jb      loc_14008CC83
0x14008ca79  mov     rdx, rbx
0x14008ca7c  mov     rcx, rsi
0x14008ca7f  call    IoctlFveQueryDeviceName
0x14008ca84  mov     edi, eax
0x14008ca86  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ca8d  cmp     rcx, r12
0x14008ca90  jz      short loc_14008CA9D
0x14008ca92  bt      dword ptr [rcx+2Ch], 0Ah
0x14008ca97  jb      loc_14008CCA7
0x14008ca9d  xor     edx, edx; PriorityBoost
0x14008ca9f  mov     [rbx+30h], edi
0x14008caa2  mov     rcx, rbx; Irp
0x14008caa5  call    cs:__imp_IofCompleteRequest
0x14008caac  nop     dword ptr [rax+rax+00h]
0x14008cab1  mov     r8d, ebp
0x14008cab4  lea     rdx, FVE_PERF_FVE_IOCTL_STOP
0x14008cabb  mov     rcx, rsi
0x14008cabe  call    FvePerfTraceDevOp
0x14008cac3  lea     rbp, WPP_GLOBAL_Control
0x14008caca  mov     r8d, 20h ; ' '; RemlockSize
0x14008cad0  lea     rcx, [r14+8]; RemoveLock
0x14008cad4  mov     rdx, r14; Tag
0x14008cad7  call    cs:__imp_IoReleaseRemoveLockEx
0x14008cade  nop     dword ptr [rax+rax+00h]
0x14008cae3  mov     rcx, cs:WPP_GLOBAL_Control
0x14008caea  cmp     rcx, rbp
0x14008caed  jz      short loc_14008CAFA
0x14008caef  bt      dword ptr [rcx+2Ch], 0Ah
0x14008caf4  jb      loc_14008CCCE
0x14008cafa  mov     eax, edi
0x14008cafc  add     rsp, 38h
0x14008cb00  pop     r15
0x14008cb02  pop     r14
0x14008cb04  pop     r13
0x14008cb06  pop     r12
0x14008cb08  pop     rdi
0x14008cb09  pop     rsi
0x14008cb0a  pop     rbp
0x14008cb0b  pop     rbx
0x14008cb0c  retn
0x14008cb0e  mov     eax, 0C000000Dh
0x14008cb13  mov     [rdx+38h], r12
0x14008cb17  mov     [rdx+30h], eax
0x14008cb1a  xor     edx, edx; PriorityBoost
0x14008cb1c  mov     rcx, rbx; Irp
0x14008cb1f  mov     edi, eax
0x14008cb21  call    cs:__imp_IofCompleteRequest
0x14008cb28  nop     dword ptr [rax+rax+00h]
0x14008cb2d  lea     rbp, WPP_GLOBAL_Control
0x14008cb34  jmp     short loc_14008CAE3
0x14008cb36  mov     eax, 0C000000Dh
0x14008cb3b  mov     [rbx+38h], r12
0x14008cb3f  xor     edx, edx; PriorityBoost
0x14008cb41  mov     [rbx+30h], eax
0x14008cb44  mov     rcx, rbx; Irp
0x14008cb47  mov     edi, eax
0x14008cb49  call    cs:__imp_IofCompleteRequest
0x14008cb50  nop     dword ptr [rax+rax+00h]
0x14008cb55  jmp     loc_14008CAC3
0x14008cb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cb61  lea     rbp, WPP_GLOBAL_Control
0x14008cb68  cmp     rcx, rbp
0x14008cb6b  jnz     loc_14008CC2D
0x14008cb71  mov     edi, 0C000000Eh
0x14008cb76  mov     [rbx+38h], r12
0x14008cb7a  xor     edx, edx; PriorityBoost
0x14008cb7c  mov     [rbx+30h], edi
0x14008cb7f  mov     rcx, rbx; Irp
0x14008cb82  call    cs:__imp_IofCompleteRequest
0x14008cb89  nop     dword ptr [rax+rax+00h]
0x14008cb8e  jmp     loc_14008CACA
0x14008cb93  cmp     byte ptr [rcx+29h], 5
0x14008cb97  jb      loc_14008C9BE
0x14008cb9d  mov     r9, [r9+30h]
0x14008cba1  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cba8  mov     rcx, [rcx+18h]
0x14008cbac  mov     edx, 41h ; 'A'
0x14008cbb1  call    WPP_SF_q
0x14008cbb6  jmp     loc_14008C9BE
0x14008cbbb  mov     eax, 0C000000Dh
0x14008cbc0  mov     [rbx+38h], r12
0x14008cbc4  mov     [rbx+30h], eax
0x14008cbc7  jmp     loc_14008CB1A
0x14008cbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cbd3  lea     rbp, WPP_GLOBAL_Control
0x14008cbda  cmp     rcx, rbp
0x14008cbdd  jz      short loc_14008CC04
0x14008cbdf  bt      dword ptr [rcx+2Ch], 0Ah
0x14008cbe4  jnb     short loc_14008CC04
0x14008cbe6  cmp     byte ptr [rcx+29h], 2
0x14008cbea  jb      short loc_14008CC04
0x14008cbec  mov     rcx, [rcx+18h]
0x14008cbf0  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cbf7  mov     edx, 42h ; 'B'
0x14008cbfc  mov     r9d, esi
0x14008cbff  call    WPP_SF_d
0x14008cc04  cmp     esi, edi
0x14008cc06  mov     [rbx+38h], r12
0x14008cc0a  mov     eax, 0C0000001h
0x14008cc0f  mov     rcx, rbx; Irp
0x14008cc12  cmovz   esi, eax
0x14008cc15  xor     edx, edx; PriorityBoost
0x14008cc17  mov     edi, esi
0x14008cc19  mov     [rbx+30h], esi
0x14008cc1c  call    cs:__imp_IofCompleteRequest
0x14008cc23  nop     dword ptr [rax+rax+00h]
0x14008cc28  jmp     loc_14008CAE3
0x14008cc2d  bt      dword ptr [rcx+2Ch], 0Ah
0x14008cc32  jnb     loc_14008CB71
0x14008cc38  cmp     byte ptr [rcx+29h], 3
0x14008cc3c  jb      loc_14008CB71
0x14008cc42  mov     rcx, [rcx+18h]
0x14008cc46  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cc4d  mov     edx, 43h ; 'C'
0x14008cc52  call    WPP_SF_
0x14008cc57  jmp     loc_14008CB71
0x14008cc5c  cmp     byte ptr [rcx+29h], 4
0x14008cc60  jb      loc_14008CA48
0x14008cc66  mov     rcx, [rcx+18h]
0x14008cc6a  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cc71  mov     edx, 44h ; 'D'
0x14008cc76  mov     r9, rsi
0x14008cc79  call    WPP_SF_q
0x14008cc7e  jmp     loc_14008CA48
0x14008cc83  cmp     byte ptr [rcx+29h], 5
0x14008cc87  jb      loc_14008CA79
0x14008cc8d  mov     rcx, [rcx+18h]
0x14008cc91  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cc98  mov     edx, 45h ; 'E'
0x14008cc9d  call    WPP_SF_
0x14008cca2  jmp     loc_14008CA79
0x14008cca7  cmp     byte ptr [rcx+29h], 5
0x14008ccab  jb      loc_14008CA9D
0x14008ccb1  mov     rcx, [rcx+18h]
0x14008ccb5  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ccbc  mov     edx, 46h ; 'F'
0x14008ccc1  mov     r9d, edi
0x14008ccc4  call    WPP_SF_d
0x14008ccc9  jmp     loc_14008CA9D
0x14008ccce  cmp     byte ptr [rcx+29h], 5
0x14008ccd2  jb      loc_14008CAFA
0x14008ccd8  mov     rcx, [rcx+18h]
0x14008ccdc  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008cce3  mov     edx, 47h ; 'G'
0x14008cce8  mov     r9d, edi
0x14008cceb  call    WPP_SF_d
0x14008ccf0  jmp     loc_14008CAFA
```
