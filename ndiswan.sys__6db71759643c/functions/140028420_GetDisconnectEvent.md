# GetDisconnectEvent

- ea: `0x140028420`
- end: `0x14002856d`
- name: `GetDisconnectEvent`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000a290`
- `0x14000bd50`
- `0x140028420`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400284e6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400284e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140028513`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002853c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140028513`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002853c`
- `NDIS!NdisAcquireRWLockRead` at `0x1400284b5`
- `NDIS!NdisAcquireRWLockRead` at `0x1400284b5`
- `NDIS!NdisReleaseRWLock` at `0x140028554`
- `NDIS!NdisReleaseRWLock` at `0x140028554`

## pseudocode

```c
__int64 __fastcall GetDisconnectEvent(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, _DWORD *a5)
{
  unsigned int v7; // esi
  _QWORD *v8; // rbx
  KSPIN_LOCK *v9; // rdi
  __int64 v10; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+20h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  if ( a4 >= 8 )
  {
    v7 = 0;
    NdisAcquireRWLockRead(ConnTableLock, &LockState, 0);
    v8 = (_QWORD *)*((_QWORD *)ConnectionTable + 5);
    while ( v8 != (_QWORD *)((char *)ConnectionTable + 40) )
    {
      v9 = v8 + 60;
      KeAcquireSpinLockAtDpcLevel(v8 + 60);
      if ( *((_DWORD *)v8 - 57) )
      {
        v10 = *(v8 - 23);
        if ( v10 )
        {
          if ( (*(_DWORD *)(v10 + 20) & 0x20) != 0 )
          {
            *a5 = 8;
            *a3 = *(v8 - 26);
            KeReleaseSpinLockFromDpcLevel(v8 + 60);
            break;
          }
        }
      }
      v8 = (_QWORD *)*v8;
      KeReleaseSpinLockFromDpcLevel(v9);
    }
    NdisReleaseRWLock(ConnTableLock, &LockState);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_LL(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a4);
    }
    return (unsigned int)-1073741789;
  }
  return v7;
}

```

## disassembly

```asm
0x140028420  push    rbx
0x140028422  push    rsi
0x140028423  push    rdi
0x140028424  push    r14
0x140028426  sub     rsp, 38h
0x14002842a  xor     eax, eax
0x14002842c  mov     ebx, r9d
0x14002842f  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x140028434  mov     r14, r8
0x140028437  mov     [rsp+58h+LockState.Flags], al
0x14002843b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028442  lea     rdi, WPP_GLOBAL_Control
0x140028449  cmp     rcx, rdi
0x14002844c  jz      short loc_140028470
0x14002844e  mov     eax, [rcx+2Ch]
0x140028451  test    al, 20h
0x140028453  jz      short loc_140028470
0x140028455  cmp     byte ptr [rcx+29h], 5
0x140028459  jb      short loc_140028470
0x14002845b  mov     rcx, [rcx+18h]
0x14002845f  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028466  mov     edx, 6Bh ; 'k'
0x14002846b  call    WPP_SF_
0x140028470  cmp     ebx, 8
0x140028473  jnb     short loc_1400284A4
0x140028475  mov     rcx, cs:WPP_GLOBAL_Control
0x14002847c  cmp     rcx, rdi
0x14002847f  jz      short loc_14002849A
0x140028481  mov     eax, [rcx+2Ch]
0x140028484  test    al, 20h
0x140028486  jz      short loc_14002849A
0x140028488  cmp     byte ptr [rcx+29h], 3
0x14002848c  jb      short loc_14002849A
0x14002848e  mov     rcx, [rcx+18h]
0x140028492  mov     r9d, ebx
0x140028495  call    WPP_SF_LL
0x14002849a  mov     esi, 0C0000023h
0x14002849f  jmp     loc_140028560
0x1400284a4  mov     rcx, cs:ConnTableLock; Lock
0x1400284ab  lea     rdx, [rsp+58h+LockState]; LockState
0x1400284b0  xor     esi, esi
0x1400284b2  xor     r8d, r8d; Flags
0x1400284b5  call    cs:__imp_NdisAcquireRWLockRead
0x1400284bc  nop     dword ptr [rax+rax+00h]
0x1400284c1  mov     rax, cs:ConnectionTable
0x1400284c8  mov     rbx, [rax+28h]
0x1400284cc  mov     rax, cs:ConnectionTable
0x1400284d3  add     rax, 28h ; '('
0x1400284d7  cmp     rbx, rax
0x1400284da  jz      short loc_140028548
0x1400284dc  lea     rdi, [rbx+1E0h]
0x1400284e3  mov     rcx, rdi; SpinLock
0x1400284e6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400284ed  nop     dword ptr [rax+rax+00h]
0x1400284f2  cmp     [rbx-0E4h], esi
0x1400284f8  jz      short loc_14002850D
0x1400284fa  mov     rax, [rbx-0B8h]
0x140028501  test    rax, rax
0x140028504  jz      short loc_14002850D
0x140028506  mov     eax, [rax+14h]
0x140028509  test    al, 20h
0x14002850b  jnz     short loc_140028521
0x14002850d  mov     rbx, [rbx]
0x140028510  mov     rcx, rdi; SpinLock
0x140028513  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002851a  nop     dword ptr [rax+rax+00h]
0x14002851f  jmp     short loc_1400284CC
0x140028521  mov     rcx, [rsp+58h+arg_20]
0x140028529  mov     dword ptr [rcx], 8
0x14002852f  mov     rcx, [rbx-0D0h]
0x140028536  mov     [r14], rcx
0x140028539  mov     rcx, rdi; SpinLock
0x14002853c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140028543  nop     dword ptr [rax+rax+00h]
0x140028548  mov     rcx, cs:ConnTableLock; Lock
0x14002854f  lea     rdx, [rsp+58h+LockState]; LockState
0x140028554  call    cs:__imp_NdisReleaseRWLock
0x14002855b  nop     dword ptr [rax+rax+00h]
0x140028560  mov     eax, esi
0x140028562  add     rsp, 38h
0x140028566  pop     r14
0x140028568  pop     rdi
0x140028569  pop     rsi
0x14002856a  pop     rbx
0x14002856b  retn
```
