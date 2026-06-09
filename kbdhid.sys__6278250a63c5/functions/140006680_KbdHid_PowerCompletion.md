# KbdHid_PowerCompletion

- ea: `0x140006680`
- end: `0x1400067db`
- name: `KbdHid_PowerCompletion`
- size: `347`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001d30`
- `0x140005a0c`
- `0x140005d88`
- `0x140006680`
- `0x140007540`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000675b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000675b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000679f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000679f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400067bb`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400067bb`

## pseudocode

```c
__int64 __fastcall KbdHid_PowerCompletion(PDEVICE_OBJECT DeviceObject, PIRP Irp, char *Context)
{
  NTSTATUS Status; // ebx
  __int64 v5; // r15
  char v7; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 *v9; // rdx
  KIRQL v10; // bl

  Status = Irp->IoStatus.Status;
  v5 = *((_QWORD *)Context + 14);
  v7 = (char)DeviceObject;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    v9 = WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        4,
        23,
        (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
      v9 = WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_qqd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        4,
        24,
        (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
        v7,
        (char)Irp,
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 1);
    }
  }
  if ( Irp->PendingReturned )
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( Status >= 0 )
  {
    KbdHid_CancelAutoRepeatTimer(Context);
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 136));
    memset(*(void **)(*((_QWORD *)Context + 14) + 120LL), 0, 4LL * *(unsigned int *)(*((_QWORD *)Context + 14) + 72LL));
    memset(*(void **)(*((_QWORD *)Context + 14) + 128LL), 0, 4LL * *(unsigned int *)(*((_QWORD *)Context + 14) + 72LL));
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 136), v10);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), Irp, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x140006680  push    rbx
0x140006682  push    rbp
0x140006683  push    rsi
0x140006684  push    rdi
0x140006685  push    r12
0x140006687  push    r13
0x140006689  push    r14
0x14000668b  push    r15
0x14000668d  sub     rsp, 48h
0x140006691  mov     ebx, [rdx+30h]
0x140006694  mov     rbp, r8
0x140006697  mov     r15, [r8+70h]
0x14000669b  mov     rsi, rdx
0x14000669e  mov     r14, rcx
0x1400066a1  lea     r13, WPP_RECORDER_INITIALIZED
0x1400066a8  xor     r12d, r12d
0x1400066ab  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400066b2  jz      short loc_14000672F
0x1400066b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066bb  mov     rdi, [rdx+0B8h]
0x1400066c2  lea     rdx, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x1400066c9  cmp     [rcx+48h], r12w
0x1400066ce  jz      short loc_1400066F1
0x1400066d0  mov     rcx, [rcx+40h]
0x1400066d4  lea     r9d, [r12+17h]
0x1400066d9  mov     [rsp+88h+var_68], rdx
0x1400066de  lea     r8d, [r12+4]
0x1400066e3  mov     dl, 5
0x1400066e5  call    WPP_RECORDER_SF_
0x1400066ea  lea     rdx, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x1400066f1  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400066f8  jz      short loc_14000672F
0x1400066fa  mov     eax, [rdi+18h]
0x1400066fd  mov     r9d, 18h
0x140006703  mov     rcx, cs:WPP_GLOBAL_Control
0x14000670a  dec     eax
0x14000670c  mov     [rsp+88h+var_50], eax
0x140006710  mov     [rsp+88h+var_58], rsi
0x140006715  lea     r8d, [r9-14h]
0x140006719  mov     [rsp+88h+var_60], r14
0x14000671e  mov     rcx, [rcx+40h]
0x140006722  mov     [rsp+88h+var_68], rdx
0x140006727  mov     dl, r8b
0x14000672a  call    WPP_RECORDER_SF_qqd
0x14000672f  cmp     [rsi+41h], r12b
0x140006733  jz      short loc_140006740
0x140006735  mov     rax, [rsi+0B8h]
0x14000673c  or      byte ptr [rax+3], 1
0x140006740  test    ebx, ebx
0x140006742  js      short loc_1400067AB
0x140006744  mov     edx, 3
0x140006749  mov     rcx, rbp; Context
0x14000674c  call    KbdHid_CancelAutoRepeatTimer
0x140006751  lea     rdi, [r15+88h]
0x140006758  mov     rcx, rdi; SpinLock
0x14000675b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006762  nop     dword ptr [rax+rax+00h]
0x140006767  mov     rcx, [rbp+70h]
0x14000676b  xor     edx, edx; Val
0x14000676d  mov     bl, al
0x14000676f  mov     r8d, [rcx+48h]
0x140006773  mov     rcx, [rcx+78h]; void *
0x140006777  shl     r8, 2; Size
0x14000677b  call    memset
0x140006780  mov     rcx, [rbp+70h]
0x140006784  xor     edx, edx; Val
0x140006786  mov     r8d, [rcx+48h]
0x14000678a  mov     rcx, [rcx+80h]; void *
0x140006791  shl     r8, 2; Size
0x140006795  call    memset
0x14000679a  mov     dl, bl; NewIrql
0x14000679c  mov     rcx, rdi; SpinLock
0x14000679f  call    cs:__imp_KeReleaseSpinLock
0x1400067a6  nop     dword ptr [rax+rax+00h]
0x1400067ab  lea     rcx, [rbp+98h]; RemoveLock
0x1400067b2  mov     r8d, 20h ; ' '; RemlockSize
0x1400067b8  mov     rdx, rsi; Tag
0x1400067bb  call    cs:__imp_IoReleaseRemoveLockEx
0x1400067c2  nop     dword ptr [rax+rax+00h]
0x1400067c7  xor     eax, eax
0x1400067c9  add     rsp, 48h
0x1400067cd  pop     r15
0x1400067cf  pop     r14
0x1400067d1  pop     r13
0x1400067d3  pop     r12
0x1400067d5  pop     rdi
0x1400067d6  pop     rsi
0x1400067d7  pop     rbp
0x1400067d8  pop     rbx
0x1400067d9  retn
```
