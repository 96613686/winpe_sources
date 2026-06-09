# KbdHid_S0IdleStateChangeWorkItem

- ea: `0x140004d30`
- end: `0x140004e3f`
- name: `KbdHid_S0IdleStateChangeWorkItem`
- size: `271`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140004d30`
- `0x140005a0c`
- `0x14000fd50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004d87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004d87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004dab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004dd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004dab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004dd4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004df4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004df4`

## pseudocode

```c
void __fastcall KbdHid_S0IdleStateChangeWorkItem(PDEVICE_OBJECT DeviceObject, char *Context)
{
  char *v2; // rbx
  KIRQL v3; // al
  unsigned int v4; // esi
  KSPIN_LOCK *v5; // rcx
  int v6; // edx

  v2 = Context;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Context) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Context,
      2,
      27,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  }
  while ( 1 )
  {
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2 + 97);
    v4 = *((_DWORD *)v2 + 196);
    v5 = (KSPIN_LOCK *)(v2 + 776);
    if ( v4 == *((_DWORD *)v2 + 192) )
      break;
    KeReleaseSpinLock(v5, v3);
    if ( (int)KbdHid_SendS0IdleStopResumeIrp(v2, v4) < 0 )
      goto LABEL_8;
    *((_DWORD *)v2 + 192) = v4;
  }
  v2[788] = 0;
  KeReleaseSpinLock(v5, v3);
LABEL_8:
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 152), KbdHid_S0IdleStateChangeWorkItem, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        2,
        28,
        (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x140004d30  push    rbx
0x140004d32  push    rbp
0x140004d33  push    rsi
0x140004d34  push    rdi
0x140004d35  push    r14
0x140004d37  sub     rsp, 30h
0x140004d3b  mov     rbx, rdx
0x140004d3e  lea     rbp, WPP_RECORDER_INITIALIZED
0x140004d45  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140004d4c  lea     r14, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140004d53  jz      short loc_140004D80
0x140004d55  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d5c  cmp     word ptr [rcx+48h], 0
0x140004d61  jz      short loc_140004D80
0x140004d63  mov     rcx, [rcx+40h]
0x140004d67  mov     r9d, 1Bh
0x140004d6d  mov     r8d, 2
0x140004d73  mov     [rsp+58h+var_38], r14
0x140004d78  mov     dl, 5
0x140004d7a  call    WPP_RECORDER_SF_
0x140004d7f  nop
0x140004d80  lea     rcx, [rbx+308h]; SpinLock
0x140004d87  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004d8e  nop     dword ptr [rax+rax+00h]
0x140004d93  mov     esi, [rbx+310h]
0x140004d99  lea     rcx, [rbx+308h]; SpinLock
0x140004da0  movzx   edx, al; NewIrql
0x140004da3  cmp     esi, [rbx+300h]
0x140004da9  jz      short loc_140004DCD
0x140004dab  call    cs:__imp_KeReleaseSpinLock
0x140004db2  nop     dword ptr [rax+rax+00h]
0x140004db7  mov     edx, esi
0x140004db9  mov     rcx, rbx
0x140004dbc  call    KbdHid_SendS0IdleStopResumeIrp
0x140004dc1  test    eax, eax
0x140004dc3  js      short loc_140004DE0
0x140004dc5  mov     [rbx+300h], esi
0x140004dcb  jmp     short loc_140004D80
0x140004dcd  mov     byte ptr [rbx+314h], 0
0x140004dd4  call    cs:__imp_KeReleaseSpinLock
0x140004ddb  nop     dword ptr [rax+rax+00h]
0x140004de0  lea     rcx, [rbx+98h]; RemoveLock
0x140004de7  mov     r8d, 20h ; ' '; RemlockSize
0x140004ded  lea     rdx, KbdHid_S0IdleStateChangeWorkItem; Tag
0x140004df4  call    cs:__imp_IoReleaseRemoveLockEx
0x140004dfb  nop     dword ptr [rax+rax+00h]
0x140004e00  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140004e07  jz      short loc_140004E33
0x140004e09  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e10  cmp     word ptr [rcx+48h], 0
0x140004e15  jz      short loc_140004E33
0x140004e17  mov     rcx, [rcx+40h]
0x140004e1b  mov     r9d, 1Ch
0x140004e21  mov     r8d, 2
0x140004e27  mov     [rsp+58h+var_38], r14
0x140004e2c  mov     dl, 5
0x140004e2e  call    WPP_RECORDER_SF_
0x140004e33  add     rsp, 30h
0x140004e37  pop     r14
0x140004e39  pop     rdi
0x140004e3a  pop     rsi
0x140004e3b  pop     rbp
0x140004e3c  pop     rbx
0x140004e3d  retn
```
