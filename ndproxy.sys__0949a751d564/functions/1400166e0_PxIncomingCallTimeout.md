# PxIncomingCallTimeout

- ea: `0x1400166e0`
- end: `0x14001679a`
- name: `PxIncomingCallTimeout`
- size: `186`
- prototype: `NDIS_TIMER_FUNCTION`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007d84`
- `0x140015290`
- `0x1400156d8`
- `0x1400166e0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400166f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400166f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016782`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016782`

## pseudocode

```c
void __fastcall PxIncomingCallTimeout(
        PVOID SystemSpecific1,
        KSPIN_LOCK *FunctionContext,
        PVOID SystemSpecific2,
        PVOID SystemSpecific3)
{
  KSPIN_LOCK *v4; // rdi
  __int64 v6; // r8

  v4 = FunctionContext + 64;
  *((_BYTE *)FunctionContext + 520) = KeAcquireSpinLockRaiseToDpc(FunctionContext + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_qLqLL(
      WPP_GLOBAL_Control->AttachedDevice,
      35,
      v6,
      FunctionContext,
      *((_DWORD *)FunctionContext + 8),
      FunctionContext[5],
      *((_DWORD *)FunctionContext + 73),
      *((_DWORD *)FunctionContext + 74));
  *((_DWORD *)FunctionContext + 8) &= ~4u;
  *((_DWORD *)FunctionContext + 9) |= 0x40u;
  PxVcCleanup((__int64)FunctionContext, 0, v6);
  if ( (*((_DWORD *)FunctionContext + 7))-- == 1 )
    DoDerefVcWork(FunctionContext);
  else
    KeReleaseSpinLock(v4, *((_BYTE *)FunctionContext + 520));
}

```

## disassembly

```asm
0x1400166e0  mov     [rsp+arg_0], rbx
0x1400166e5  push    rdi
0x1400166e6  sub     rsp, 40h
0x1400166ea  lea     rdi, [rdx+200h]
0x1400166f1  mov     rbx, rdx
0x1400166f4  mov     rcx, rdi; SpinLock
0x1400166f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400166fe  nop     dword ptr [rax+rax+00h]
0x140016703  mov     [rbx+208h], al
0x140016709  mov     rcx, cs:WPP_GLOBAL_Control
0x140016710  lea     rax, WPP_GLOBAL_Control
0x140016717  cmp     rcx, rax
0x14001671a  jz      short loc_140016757
0x14001671c  cmp     byte ptr [rcx+29h], 3
0x140016720  jb      short loc_140016757
0x140016722  mov     eax, [rbx+128h]
0x140016728  mov     edx, 23h ; '#'
0x14001672d  mov     rcx, [rcx+18h]
0x140016731  mov     r9, rbx
0x140016734  mov     [rsp+48h+var_10], eax
0x140016738  mov     eax, [rbx+124h]
0x14001673e  mov     [rsp+48h+var_18], eax
0x140016742  mov     rax, [rbx+28h]
0x140016746  mov     [rsp+48h+var_20], rax
0x14001674b  mov     eax, [rbx+20h]
0x14001674e  mov     [rsp+48h+var_28], eax
0x140016752  call    WPP_SF_qLqLL
0x140016757  and     dword ptr [rbx+20h], 0FFFFFFFBh
0x14001675b  xor     edx, edx
0x14001675d  or      dword ptr [rbx+24h], 40h
0x140016761  mov     rcx, rbx
0x140016764  call    PxVcCleanup
0x140016769  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x14001676d  jnz     short loc_140016779
0x14001676f  mov     rcx, rbx; Entry
0x140016772  call    DoDerefVcWork
0x140016777  jmp     short loc_14001678E
0x140016779  mov     dl, [rbx+208h]; NewIrql
0x14001677f  mov     rcx, rdi; SpinLock
0x140016782  call    cs:__imp_KeReleaseSpinLock
0x140016789  nop     dword ptr [rax+rax+00h]
0x14001678e  mov     rbx, [rsp+48h+arg_0]
0x140016793  add     rsp, 40h
0x140016797  pop     rdi
0x140016798  retn
```
