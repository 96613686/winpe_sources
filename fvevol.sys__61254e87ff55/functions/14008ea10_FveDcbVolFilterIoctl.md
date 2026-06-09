# FveDcbVolFilterIoctl

- ea: `0x14008ea10`
- end: `0x14008eda5`
- name: `FveDcbVolFilterIoctl`
- size: `917`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000a210`
- `0x14008ea10`
- `0x14008edac`
- `0x1400dfc40`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008eb55`
- `ntoskrnl!IofCompleteRequest` at `0x14008ebd1`
- `ntoskrnl!IofCompleteRequest` at `0x14008ebf9`
- `ntoskrnl!IofCompleteRequest` at `0x14008ec32`
- `ntoskrnl!IofCompleteRequest` at `0x14008eccc`
- `ntoskrnl!IofCompleteRequest` at `0x14008eb55`
- `ntoskrnl!IofCompleteRequest` at `0x14008ebd1`
- `ntoskrnl!IofCompleteRequest` at `0x14008ebf9`
- `ntoskrnl!IofCompleteRequest` at `0x14008ec32`
- `ntoskrnl!IofCompleteRequest` at `0x14008eccc`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008eaa7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14008eaa7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008eb87`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008eb87`

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
0x14008ea10  push    rbx
0x14008ea12  push    rbp
0x14008ea13  push    rsi
0x14008ea14  push    rdi
0x14008ea15  push    r12
0x14008ea17  push    r13
0x14008ea19  push    r14
0x14008ea1b  push    r15
0x14008ea1d  sub     rsp, 38h
0x14008ea21  xor     r12d, r12d
0x14008ea24  lea     rax, WPP_GLOBAL_Control
0x14008ea2b  mov     rbx, rdx
0x14008ea2e  mov     rsi, rcx
0x14008ea31  test    rcx, rcx
0x14008ea34  jz      loc_14008EBBE
0x14008ea3a  cmp     [rcx+0C8h], r12
0x14008ea41  jz      loc_14008EBBE
0x14008ea47  mov     r9, [rdx+0B8h]
0x14008ea4e  mov     edi, 0C0000002h
0x14008ea53  mov     ebp, [r9+18h]
0x14008ea57  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ea5e  cmp     rcx, rax
0x14008ea61  jz      short loc_14008EA6E
0x14008ea63  bt      dword ptr [rcx+2Ch], 0Ah
0x14008ea68  jb      loc_14008EC43
0x14008ea6e  cmp     dword ptr [rsi+0B0h], 2
0x14008ea75  jnz     loc_14008EBDD
0x14008ea7b  mov     r14, [rsi+0C8h]
0x14008ea82  test    r14, r14
0x14008ea85  jz      loc_14008EC6B
0x14008ea8b  mov     r9d, 1; Line
0x14008ea91  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x14008ea99  lea     r8, File; File
0x14008eaa0  mov     rdx, r14; Tag
0x14008eaa3  lea     rcx, [r14+8]; RemoveLock
0x14008eaa7  call    cs:__imp_IoAcquireRemoveLockEx
0x14008eaae  nop     dword ptr [rax+rax+00h]
0x14008eab3  mov     esi, eax
0x14008eab5  test    eax, eax
0x14008eab7  js      loc_14008EC7C
0x14008eabd  mov     rax, [r14]
0x14008eac0  test    rax, rax
0x14008eac3  jz      loc_14008EBE6
0x14008eac9  mov     rsi, [r14]
0x14008eacc  mov     rax, [rsi]
0x14008eacf  mov     ecx, [rax+30h]
0x14008ead2  test    cl, cl
0x14008ead4  js      loc_14008EC0A
0x14008eada  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eae1  lea     r12, WPP_GLOBAL_Control
0x14008eae8  cmp     rcx, r12
0x14008eaeb  jz      short loc_14008EAF8
0x14008eaed  bt      dword ptr [rcx+2Ch], 0Ah
0x14008eaf2  jb      loc_14008ED0C
0x14008eaf8  mov     r8d, ebp
0x14008eafb  lea     rdx, FVE_PERF_FVE_IOCTL_START
0x14008eb02  mov     rcx, rsi
0x14008eb05  call    FvePerfTraceDevOp
0x14008eb0a  cmp     ebp, 4D0008h
0x14008eb10  jnz     short loc_14008EB61
0x14008eb12  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eb19  cmp     rcx, r12
0x14008eb1c  jz      short loc_14008EB29
0x14008eb1e  bt      dword ptr [rcx+2Ch], 0Ah
0x14008eb23  jb      loc_14008ED33
0x14008eb29  mov     rdx, rbx
0x14008eb2c  mov     rcx, rsi
0x14008eb2f  call    IoctlFveQueryDeviceName
0x14008eb34  mov     edi, eax
0x14008eb36  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eb3d  cmp     rcx, r12
0x14008eb40  jz      short loc_14008EB4D
0x14008eb42  bt      dword ptr [rcx+2Ch], 0Ah
0x14008eb47  jb      loc_14008ED57
0x14008eb4d  xor     edx, edx; PriorityBoost
0x14008eb4f  mov     [rbx+30h], edi
0x14008eb52  mov     rcx, rbx; Irp
0x14008eb55  call    cs:__imp_IofCompleteRequest
0x14008eb5c  nop     dword ptr [rax+rax+00h]
0x14008eb61  mov     r8d, ebp
0x14008eb64  lea     rdx, FVE_PERF_FVE_IOCTL_STOP
0x14008eb6b  mov     rcx, rsi
0x14008eb6e  call    FvePerfTraceDevOp
0x14008eb73  lea     rbp, WPP_GLOBAL_Control
0x14008eb7a  mov     r8d, 20h ; ' '; RemlockSize
0x14008eb80  lea     rcx, [r14+8]; RemoveLock
0x14008eb84  mov     rdx, r14; Tag
0x14008eb87  call    cs:__imp_IoReleaseRemoveLockEx
0x14008eb8e  nop     dword ptr [rax+rax+00h]
0x14008eb93  mov     rcx, cs:WPP_GLOBAL_Control
0x14008eb9a  cmp     rcx, rbp
0x14008eb9d  jz      short loc_14008EBAA
0x14008eb9f  bt      dword ptr [rcx+2Ch], 0Ah
0x14008eba4  jb      loc_14008ED7E
0x14008ebaa  mov     eax, edi
0x14008ebac  add     rsp, 38h
0x14008ebb0  pop     r15
0x14008ebb2  pop     r14
0x14008ebb4  pop     r13
0x14008ebb6  pop     r12
0x14008ebb8  pop     rdi
0x14008ebb9  pop     rsi
0x14008ebba  pop     rbp
0x14008ebbb  pop     rbx
0x14008ebbc  retn
0x14008ebbe  mov     eax, 0C000000Dh
0x14008ebc3  mov     [rdx+38h], r12
0x14008ebc7  mov     [rdx+30h], eax
0x14008ebca  xor     edx, edx; PriorityBoost
0x14008ebcc  mov     rcx, rbx; Irp
0x14008ebcf  mov     edi, eax
0x14008ebd1  call    cs:__imp_IofCompleteRequest
0x14008ebd8  nop     dword ptr [rax+rax+00h]
0x14008ebdd  lea     rbp, WPP_GLOBAL_Control
0x14008ebe4  jmp     short loc_14008EB93
0x14008ebe6  mov     eax, 0C000000Dh
0x14008ebeb  mov     [rbx+38h], r12
0x14008ebef  xor     edx, edx; PriorityBoost
0x14008ebf1  mov     [rbx+30h], eax
0x14008ebf4  mov     rcx, rbx; Irp
0x14008ebf7  mov     edi, eax
0x14008ebf9  call    cs:__imp_IofCompleteRequest
0x14008ec00  nop     dword ptr [rax+rax+00h]
0x14008ec05  jmp     loc_14008EB73
0x14008ec0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ec11  lea     rbp, WPP_GLOBAL_Control
0x14008ec18  cmp     rcx, rbp
0x14008ec1b  jnz     loc_14008ECDD
0x14008ec21  mov     edi, 0C000000Eh
0x14008ec26  mov     [rbx+38h], r12
0x14008ec2a  xor     edx, edx; PriorityBoost
0x14008ec2c  mov     [rbx+30h], edi
0x14008ec2f  mov     rcx, rbx; Irp
0x14008ec32  call    cs:__imp_IofCompleteRequest
0x14008ec39  nop     dword ptr [rax+rax+00h]
0x14008ec3e  jmp     loc_14008EB7A
0x14008ec43  cmp     byte ptr [rcx+29h], 5
0x14008ec47  jb      loc_14008EA6E
0x14008ec4d  mov     r9, [r9+30h]
0x14008ec51  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ec58  mov     rcx, [rcx+18h]
0x14008ec5c  mov     edx, 41h ; 'A'
0x14008ec61  call    WPP_SF_q
0x14008ec66  jmp     loc_14008EA6E
0x14008ec6b  mov     eax, 0C000000Dh
0x14008ec70  mov     [rbx+38h], r12
0x14008ec74  mov     [rbx+30h], eax
0x14008ec77  jmp     loc_14008EBCA
0x14008ec7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ec83  lea     rbp, WPP_GLOBAL_Control
0x14008ec8a  cmp     rcx, rbp
0x14008ec8d  jz      short loc_14008ECB4
0x14008ec8f  bt      dword ptr [rcx+2Ch], 0Ah
0x14008ec94  jnb     short loc_14008ECB4
0x14008ec96  cmp     byte ptr [rcx+29h], 2
0x14008ec9a  jb      short loc_14008ECB4
0x14008ec9c  mov     rcx, [rcx+18h]
0x14008eca0  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008eca7  mov     edx, 42h ; 'B'
0x14008ecac  mov     r9d, esi
0x14008ecaf  call    WPP_SF_d
0x14008ecb4  cmp     esi, edi
0x14008ecb6  mov     [rbx+38h], r12
0x14008ecba  mov     eax, 0C0000001h
0x14008ecbf  mov     rcx, rbx; Irp
0x14008ecc2  cmovz   esi, eax
0x14008ecc5  xor     edx, edx; PriorityBoost
0x14008ecc7  mov     edi, esi
0x14008ecc9  mov     [rbx+30h], esi
0x14008eccc  call    cs:__imp_IofCompleteRequest
0x14008ecd3  nop     dword ptr [rax+rax+00h]
0x14008ecd8  jmp     loc_14008EB93
0x14008ecdd  bt      dword ptr [rcx+2Ch], 0Ah
0x14008ece2  jnb     loc_14008EC21
0x14008ece8  cmp     byte ptr [rcx+29h], 3
0x14008ecec  jb      loc_14008EC21
0x14008ecf2  mov     rcx, [rcx+18h]
0x14008ecf6  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ecfd  mov     edx, 43h ; 'C'
0x14008ed02  call    WPP_SF_
0x14008ed07  jmp     loc_14008EC21
0x14008ed0c  cmp     byte ptr [rcx+29h], 4
0x14008ed10  jb      loc_14008EAF8
0x14008ed16  mov     rcx, [rcx+18h]
0x14008ed1a  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ed21  mov     edx, 44h ; 'D'
0x14008ed26  mov     r9, rsi
0x14008ed29  call    WPP_SF_q
0x14008ed2e  jmp     loc_14008EAF8
0x14008ed33  cmp     byte ptr [rcx+29h], 5
0x14008ed37  jb      loc_14008EB29
0x14008ed3d  mov     rcx, [rcx+18h]
0x14008ed41  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ed48  mov     edx, 45h ; 'E'
0x14008ed4d  call    WPP_SF_
0x14008ed52  jmp     loc_14008EB29
0x14008ed57  cmp     byte ptr [rcx+29h], 5
0x14008ed5b  jb      loc_14008EB4D
0x14008ed61  mov     rcx, [rcx+18h]
0x14008ed65  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ed6c  mov     edx, 46h ; 'F'
0x14008ed71  mov     r9d, edi
0x14008ed74  call    WPP_SF_d
0x14008ed79  jmp     loc_14008EB4D
0x14008ed7e  cmp     byte ptr [rcx+29h], 5
0x14008ed82  jb      loc_14008EBAA
0x14008ed88  mov     rcx, [rcx+18h]
0x14008ed8c  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008ed93  mov     edx, 47h ; 'G'
0x14008ed98  mov     r9d, edi
0x14008ed9b  call    WPP_SF_d
0x14008eda0  jmp     loc_14008EBAA
```
