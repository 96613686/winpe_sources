# PxCmIncomingCallComplete

- ea: `0x1400103c0`
- end: `0x1400104e6`
- name: `PxCmIncomingCallComplete`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140001c0c`
- `0x140006e08`
- `0x1400103c0`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001045e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001045e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400104d0`
- `NDIS!NdisSetEvent` at `0x1400104ab`
- `NDIS!NdisSetEvent` at `0x1400104ab`

## pseudocode

```c
void __fastcall PxCmIncomingCallComplete(int a1, unsigned __int64 a2)
{
  char *v4; // rbx
  PVOID Entry; // [rsp+78h] [rbp+20h] BYREF

  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, a2);
  GetVcFromCtx(a2, &Entry);
  v4 = (char *)Entry;
  if ( Entry )
  {
    v4[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids, v4, a1);
    *((_DWORD *)v4 + 118) = a1;
    NdisSetEvent((PNDIS_EVENT)(v4 + 448));
    if ( (*((_DWORD *)v4 + 7))-- == 1 )
      DoDerefVcWork(v4);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v4 + 64, v4[520]);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)((_DWORD)Entry + 24),
      WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids,
      a2);
  }
}

```

## disassembly

```asm
0x1400103c0  push    rbx
0x1400103c2  push    rbp
0x1400103c3  push    rsi
0x1400103c4  push    rdi
0x1400103c5  sub     rsp, 38h
0x1400103c9  mov     rdi, rdx
0x1400103cc  mov     [rsp+58h+Entry], 0
0x1400103d5  mov     esi, ecx
0x1400103d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103de  lea     rbp, WPP_GLOBAL_Control
0x1400103e5  cmp     rcx, rbp
0x1400103e8  jz      short loc_140010408
0x1400103ea  cmp     byte ptr [rcx+29h], 5
0x1400103ee  jb      short loc_140010408
0x1400103f0  mov     rcx, [rcx+18h]
0x1400103f4  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x1400103fb  mov     edx, 17h
0x140010400  mov     r9, rdi
0x140010403  call    WPP_SF_q
0x140010408  lea     rdx, [rsp+58h+Entry]
0x14001040d  mov     rcx, rdi
0x140010410  call    GetVcFromCtx
0x140010415  mov     rbx, [rsp+58h+Entry]
0x14001041a  test    rbx, rbx
0x14001041d  jnz     short loc_140010454
0x14001041f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010426  cmp     rcx, rbp
0x140010429  jz      loc_1400104DC
0x14001042f  cmp     byte ptr [rcx+29h], 3
0x140010433  jb      loc_1400104DC
0x140010439  mov     rcx, [rcx+18h]
0x14001043d  lea     edx, [rbx+18h]
0x140010440  mov     r9, rdi
0x140010443  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x14001044a  call    WPP_SF_q
0x14001044f  jmp     loc_1400104DC
0x140010454  lea     rdi, [rbx+200h]
0x14001045b  mov     rcx, rdi; SpinLock
0x14001045e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010465  nop     dword ptr [rax+rax+00h]
0x14001046a  mov     [rbx+208h], al
0x140010470  mov     rcx, cs:WPP_GLOBAL_Control
0x140010477  cmp     rcx, rbp
0x14001047a  jz      short loc_14001049E
0x14001047c  cmp     byte ptr [rcx+29h], 5
0x140010480  jb      short loc_14001049E
0x140010482  mov     rcx, [rcx+18h]
0x140010486  lea     r8, WPP_7588bfd817a13d6d25709b3985a2e300_Traceguids
0x14001048d  mov     edx, 19h
0x140010492  mov     [rsp+58h+var_38], esi
0x140010496  mov     r9, rbx
0x140010499  call    WPP_SF_qD
0x14001049e  lea     rcx, [rbx+1C0h]; Event
0x1400104a5  mov     [rbx+1D8h], esi
0x1400104ab  call    cs:__imp_NdisSetEvent
0x1400104b2  nop     dword ptr [rax+rax+00h]
0x1400104b7  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1400104bb  jnz     short loc_1400104C7
0x1400104bd  mov     rcx, rbx; Entry
0x1400104c0  call    DoDerefVcWork
0x1400104c5  jmp     short loc_1400104DC
0x1400104c7  mov     dl, [rbx+208h]; NewIrql
0x1400104cd  mov     rcx, rdi; SpinLock
0x1400104d0  call    cs:__imp_KeReleaseSpinLock
0x1400104d7  nop     dword ptr [rax+rax+00h]
0x1400104dc  add     rsp, 38h
0x1400104e0  pop     rdi
0x1400104e1  pop     rsi
0x1400104e2  pop     rbp
0x1400104e3  pop     rbx
0x1400104e4  retn
```
