# NdisWanFreeMiniportCB

- ea: `0x14000c930`
- end: `0x14000cac2`
- name: `NdisWanFreeMiniportCB`
- size: `402`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d0c0`
- `0x14002c0bc`
- `0x14002c200`
- `0x14002c3f4`
- `0x140037c40`

## callees

- `0x140005728`
- `0x140006e18`
- `0x14000a290`
- `0x14000a648`
- `0x14000c930`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000ca2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ca2d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c9b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c9b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ca6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ca6f`

## pseudocode

```c
void __fastcall NdisWanFreeMiniportCB(_QWORD *P)
{
  _QWORD *v2; // rcx
  PVOID *v3; // rax
  char v4; // di
  struct _LIST_ENTRY *i; // rcx
  __int16 v6; // ax
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xEu,
        (__int64)WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xFu,
        (__int64)WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids,
        P);
    }
  }
  NdisWanFreeNdisString(P + 13);
  LOBYTE(WPP_MAIN_CB.DeviceType) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  v2 = (_QWORD *)*P;
  if ( *(_QWORD **)(*P + 8LL) != P || (v3 = (PVOID *)P[1], *v3 != P) )
    __fastfail(3u);
  *v3 = v2;
  v4 = 0;
  v2[1] = v3;
  --LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  for ( i = WPP_MAIN_CB.Queue.ListEntry.Blink;
        i != (struct _LIST_ENTRY *)&WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink;
        i = i->Flink )
  {
    if ( WORD2(i[8].Flink) == *((_WORD *)P + 66) )
    {
      v4 = 1;
      break;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, WPP_MAIN_CB.DeviceType);
  if ( !v4 )
  {
    v8 = 0;
    v6 = *((_WORD *)P + 66);
    v7 = 0;
    LOWORD(v7) = v6;
    DWORD1(v7) = 1;
    SetProtocolInfo((__int64)&v7);
  }
  ExFreePoolWithTag(P, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x10u,
      (__int64)WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
  }
}

```

## disassembly

```asm
0x14000c930  mov     [rsp+arg_0], rbx
0x14000c935  mov     [rsp+arg_8], rdi
0x14000c93a  push    r14
0x14000c93c  sub     rsp, 40h
0x14000c940  mov     rbx, rcx
0x14000c943  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c94a  lea     r14, WPP_GLOBAL_Control
0x14000c951  cmp     rcx, r14
0x14000c954  jz      short loc_14000C9A9
0x14000c956  mov     eax, [rcx+2Ch]
0x14000c959  test    al, 40h
0x14000c95b  jz      short loc_14000C978
0x14000c95d  cmp     byte ptr [rcx+29h], 5
0x14000c961  jb      short loc_14000C978
0x14000c963  mov     rcx, [rcx+18h]
0x14000c967  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c96e  mov     edx, 0Eh
0x14000c973  call    WPP_SF_
0x14000c978  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c97f  cmp     rcx, r14
0x14000c982  jz      short loc_14000C9A9
0x14000c984  mov     eax, [rcx+2Ch]
0x14000c987  test    al, 40h
0x14000c989  jz      short loc_14000C9A9
0x14000c98b  cmp     byte ptr [rcx+29h], 5
0x14000c98f  jb      short loc_14000C9A9
0x14000c991  mov     rcx, [rcx+18h]
0x14000c995  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c99c  mov     edx, 0Fh
0x14000c9a1  mov     r9, rbx
0x14000c9a4  call    WPP_SF_q
0x14000c9a9  lea     rcx, [rbx+68h]
0x14000c9ad  call    NdisWanFreeNdisString
0x14000c9b2  lea     rcx, WPP_MAIN_CB.DeviceExtension; SpinLock
0x14000c9b9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c9c0  nop     dword ptr [rax+rax+00h]
0x14000c9c5  mov     byte ptr cs:WPP_MAIN_CB.DeviceType, al
0x14000c9cb  mov     rcx, [rbx]
0x14000c9ce  cmp     [rcx+8], rbx
0x14000c9d2  jnz     loc_14000CABB
0x14000c9d8  mov     rax, [rbx+8]
0x14000c9dc  cmp     [rax], rbx
0x14000c9df  jnz     loc_14000CABB
0x14000c9e5  mov     [rax], rcx
0x14000c9e8  xor     dil, dil
0x14000c9eb  mov     [rcx+8], rax
0x14000c9ef  dec     dword ptr cs:WPP_MAIN_CB.Queue
0x14000c9f5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000c9fc  lea     rax, WPP_MAIN_CB.Queue+8
0x14000ca03  cmp     rcx, rax
0x14000ca06  jz      short loc_14000CA20
0x14000ca08  movzx   eax, word ptr [rbx+84h]
0x14000ca0f  cmp     [rcx+84h], ax
0x14000ca16  jz      short loc_14000CA1D
0x14000ca18  mov     rcx, [rcx]
0x14000ca1b  jmp     short loc_14000C9FC
0x14000ca1d  mov     dil, 1
0x14000ca20  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceType; NewIrql
0x14000ca26  lea     rcx, WPP_MAIN_CB.DeviceExtension; SpinLock
0x14000ca2d  call    cs:__imp_KeReleaseSpinLock
0x14000ca34  nop     dword ptr [rax+rax+00h]
0x14000ca39  test    dil, dil
0x14000ca3c  jnz     short loc_14000CA6A
0x14000ca3e  xor     eax, eax
0x14000ca40  lea     rcx, [rsp+48h+var_28]
0x14000ca45  mov     [rsp+48h+var_18], eax
0x14000ca49  xorps   xmm0, xmm0
0x14000ca4c  movzx   eax, word ptr [rbx+84h]
0x14000ca53  movups  [rsp+48h+var_28], xmm0
0x14000ca58  mov     word ptr [rsp+48h+var_28], ax
0x14000ca5d  mov     dword ptr [rsp+48h+var_28+4], 1
0x14000ca65  call    SetProtocolInfo
0x14000ca6a  xor     edx, edx; Tag
0x14000ca6c  mov     rcx, rbx; P
0x14000ca6f  call    cs:__imp_ExFreePoolWithTag
0x14000ca76  nop     dword ptr [rax+rax+00h]
0x14000ca7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca82  cmp     rcx, r14
0x14000ca85  jz      short loc_14000CAA9
0x14000ca87  mov     eax, [rcx+2Ch]
0x14000ca8a  test    al, 40h
0x14000ca8c  jz      short loc_14000CAA9
0x14000ca8e  cmp     byte ptr [rcx+29h], 5
0x14000ca92  jb      short loc_14000CAA9
0x14000ca94  mov     rcx, [rcx+18h]
0x14000ca98  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000ca9f  mov     edx, 10h
0x14000caa4  call    WPP_SF_
0x14000caa9  mov     rbx, [rsp+48h+arg_0]
0x14000caae  mov     rdi, [rsp+48h+arg_8]
0x14000cab3  add     rsp, 40h
0x14000cab7  pop     r14
0x14000cab9  retn
0x14000cabb  mov     ecx, 3
0x14000cac0  int     29h; Win8: RtlFailFast(ecx)
```
