# DPSendCompleteCallback

- ea: `0x140019760`
- end: `0x14001984c`
- name: `DPSendCompleteCallback`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003a64`
- `0x140019760`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019785`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019785`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400197ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400197ce`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400197e9`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400197e9`

## pseudocode

```c
void __fastcall DPSendCompleteCallback(__int64 a1, struct _NET_BUFFER_LIST *a2)
{
  _QWORD *v4; // rbx
  KIRQL v5; // al
  _QWORD *i; // r8

  v4 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
  for ( i = (_QWORD *)*((_QWORD *)SstpGlobals + 60); i != (_QWORD *)((char *)SstpGlobals + 480); v4 = 0 )
  {
    v4 = i - 2;
    if ( *((_BYTE *)i + 21116) && a1 == v4[2642] )
      break;
    i = (_QWORD *)*i;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 59, v5);
  if ( v4 )
  {
    NdisMCoSendNetBufferListsComplete((NDIS_HANDLE)v4[5], a2, 0);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, a1);
  }
}

```

## disassembly

```asm
0x140019760  mov     [rsp+arg_0], rbx
0x140019765  mov     [rsp+arg_8], rsi
0x14001976a  push    rdi
0x14001976b  sub     rsp, 20h
0x14001976f  mov     rsi, rcx
0x140019772  mov     rdi, rdx
0x140019775  mov     rcx, cs:SstpGlobals
0x14001977c  xor     ebx, ebx
0x14001977e  add     rcx, 1D8h; SpinLock
0x140019785  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001978c  nop     dword ptr [rax+rax+00h]
0x140019791  mov     r9, cs:SstpGlobals
0x140019798  add     r9, 1E0h
0x14001979f  mov     r8, [r9]
0x1400197a2  cmp     r8, r9
0x1400197a5  jz      short loc_1400197BD
0x1400197a7  lea     rbx, [r8-10h]
0x1400197ab  cmp     byte ptr [rbx+528Ch], 0
0x1400197b2  jz      short loc_140019806
0x1400197b4  cmp     rsi, [rbx+5290h]
0x1400197bb  jnz     short loc_140019806
0x1400197bd  mov     rcx, cs:SstpGlobals
0x1400197c4  movzx   edx, al; NewIrql
0x1400197c7  add     rcx, 1D8h; SpinLock
0x1400197ce  call    cs:__imp_KeReleaseSpinLock
0x1400197d5  nop     dword ptr [rax+rax+00h]
0x1400197da  test    rbx, rbx
0x1400197dd  jz      short loc_140019812
0x1400197df  mov     rcx, [rbx+28h]; NdisVcHandle
0x1400197e3  xor     r8d, r8d; SendCompleteFlags
0x1400197e6  mov     rdx, rdi; NetBufferLists
0x1400197e9  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x1400197f0  nop     dword ptr [rax+rax+00h]
0x1400197f5  mov     rbx, [rsp+28h+arg_0]
0x1400197fa  mov     rsi, [rsp+28h+arg_8]
0x1400197ff  add     rsp, 20h
0x140019803  pop     rdi
0x140019804  retn
0x140019806  mov     r8, [r8]
0x140019809  xor     ebx, ebx
0x14001980b  cmp     r8, r9
0x14001980e  jz      short loc_1400197BD
0x140019810  jmp     short loc_1400197A7
0x140019812  mov     rcx, cs:WPP_GLOBAL_Control
0x140019819  lea     rax, WPP_GLOBAL_Control
0x140019820  cmp     rcx, rax
0x140019823  jz      short loc_1400197F5
0x140019825  mov     eax, [rcx+2Ch]
0x140019828  test    al, 1
0x14001982a  jz      short loc_1400197F5
0x14001982c  cmp     byte ptr [rcx+29h], 1
0x140019830  jb      short loc_1400197F5
0x140019832  mov     rcx, [rcx+18h]
0x140019836  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001983d  mov     edx, 5Bh ; '['
0x140019842  mov     r9, rsi
0x140019845  call    WPP_SF_q
0x14001984a  jmp     short loc_1400197F5
```
