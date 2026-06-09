# FreeTapiProvider

- ea: `0x140006cac`
- end: `0x140006e01`
- name: `FreeTapiProvider`
- size: `341`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005480`
- `0x1400062c0`

## callees

- `0x140001c0c`
- `0x140006c1c`
- `0x140006cac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006de4`
- `NDIS!NdisAcquireRWLockWrite` at `0x140006d7a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140006d7a`
- `NDIS!NdisReleaseRWLock` at `0x140006dbf`
- `NDIS!NdisReleaseRWLock` at `0x140006dbf`

## pseudocode

```c
void __fastcall FreeTapiProvider(char *P)
{
  _QWORD **v2; // rbx
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  void **v5; // rdi
  void ***v6; // rbx
  void **v7; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  v2 = (_QWORD **)(P + 56);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
LABEL_18:
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    FreeTapiLine(v3);
  }
  v5 = (void **)(P + 40);
  while ( 1 )
  {
    v6 = (void ***)*v5;
    if ( *v5 == v5 )
      break;
    if ( v6[1] != v5 )
      goto LABEL_18;
    v7 = *v6;
    if ( (*v6)[1] != v6 )
      goto LABEL_18;
    *v5 = v7;
    v7[1] = v5;
    if ( (*((_DWORD *)v6 + 9) & 1) != 0 )
    {
      *(_WORD *)&LockState.OldIrql = 0;
      LockState.Flags = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          156,
          WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
          v6,
          *((_DWORD *)v6 + 12));
      NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState, 0);
      WPP_MAIN_CB.Dpc.DpcListEntry.Next[*((unsigned int *)v6 + 12)].Next = 0;
      *((_DWORD *)v6 + 9) &= ~1u;
      --*(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy;
      if ( *((_DWORD *)v6 + 12) < WPP_MAIN_CB.Dpc.TargetInfoAsUlong )
        WPP_MAIN_CB.Dpc.TargetInfoAsUlong = *((_DWORD *)v6 + 12);
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)WPP_MAIN_CB.Dpc.ProcessorHistory, &LockState);
    }
    FreeTapiLine(v6);
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140006cac  mov     [rsp+arg_8], rbx
0x140006cb1  mov     [rsp+arg_10], rsi
0x140006cb6  push    rdi
0x140006cb7  sub     rsp, 30h
0x140006cbb  mov     rsi, rcx
0x140006cbe  lea     rbx, [rcx+38h]
0x140006cc2  mov     rcx, [rbx]; P
0x140006cc5  cmp     rcx, rbx
0x140006cc8  jz      short loc_140006CEF
0x140006cca  cmp     [rcx+8], rbx
0x140006cce  jnz     loc_140006DD8
0x140006cd4  mov     rax, [rcx]
0x140006cd7  cmp     [rax+8], rcx
0x140006cdb  jnz     loc_140006DD8
0x140006ce1  mov     [rbx], rax
0x140006ce4  mov     [rax+8], rbx
0x140006ce8  call    FreeTapiLine
0x140006ced  jmp     short loc_140006CC2
0x140006cef  lea     rdi, [rsi+28h]
0x140006cf3  mov     rbx, [rdi]
0x140006cf6  cmp     rbx, rdi
0x140006cf9  jz      loc_140006DDF
0x140006cff  cmp     [rbx+8], rdi
0x140006d03  jnz     loc_140006DD8
0x140006d09  mov     rax, [rbx]
0x140006d0c  cmp     [rax+8], rbx
0x140006d10  jnz     loc_140006DD8
0x140006d16  mov     [rdi], rax
0x140006d19  mov     [rax+8], rdi
0x140006d1d  mov     eax, [rbx+24h]
0x140006d20  test    al, 1
0x140006d22  jz      loc_140006DCB
0x140006d28  xor     eax, eax
0x140006d2a  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x140006d2f  mov     [rsp+38h+LockState.Flags], al
0x140006d33  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d3a  lea     rax, WPP_GLOBAL_Control
0x140006d41  cmp     rcx, rax
0x140006d44  jz      short loc_140006D6B
0x140006d46  cmp     byte ptr [rcx+29h], 4
0x140006d4a  jb      short loc_140006D6B
0x140006d4c  mov     eax, [rbx+30h]
0x140006d4f  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140006d56  mov     rcx, [rcx+18h]
0x140006d5a  mov     edx, 9Ch
0x140006d5f  mov     r9, rbx
0x140006d62  mov     [rsp+38h+var_18], eax
0x140006d66  call    WPP_SF_qD
0x140006d6b  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140006d72  lea     rdx, [rsp+38h+LockState]; LockState
0x140006d77  xor     r8d, r8d; Flags
0x140006d7a  call    cs:__imp_NdisAcquireRWLockWrite
0x140006d81  nop     dword ptr [rax+rax+00h]
0x140006d86  mov     rax, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140006d8d  mov     ecx, [rbx+30h]
0x140006d90  mov     qword ptr [rax+rcx*8], 0
0x140006d98  and     dword ptr [rbx+24h], 0FFFFFFFEh
0x140006d9c  dec     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x140006da2  mov     eax, [rbx+30h]
0x140006da5  cmp     eax, dword ptr cs:WPP_MAIN_CB.Dpc
0x140006dab  jnb     short loc_140006DB3
0x140006dad  mov     dword ptr cs:WPP_MAIN_CB.Dpc, eax
0x140006db3  mov     rcx, cs:WPP_MAIN_CB.Dpc.ProcessorHistory; Lock
0x140006dba  lea     rdx, [rsp+38h+LockState]; LockState
0x140006dbf  call    cs:__imp_NdisReleaseRWLock
0x140006dc6  nop     dword ptr [rax+rax+00h]
0x140006dcb  mov     rcx, rbx; P
0x140006dce  call    FreeTapiLine
0x140006dd3  jmp     loc_140006CF3
0x140006dd8  mov     ecx, 3
0x140006ddd  int     29h; Win8: RtlFailFast(ecx)
0x140006ddf  xor     edx, edx; Tag
0x140006de1  mov     rcx, rsi; P
0x140006de4  call    cs:__imp_ExFreePoolWithTag
0x140006deb  nop     dword ptr [rax+rax+00h]
0x140006df0  mov     rbx, [rsp+38h+arg_8]
0x140006df5  mov     rsi, [rsp+38h+arg_10]
0x140006dfa  add     rsp, 30h
0x140006dfe  pop     rdi
0x140006dff  retn
```
