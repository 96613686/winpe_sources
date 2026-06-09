# NdisWanFreeOpenCB

- ea: `0x140004ab8`
- end: `0x140004bd8`
- name: `NdisWanFreeOpenCB`
- size: `288`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400040a0`
- `0x14000f2d0`
- `0x14000f690`
- `0x140037b70`

## callees

- `0x140004ab8`
- `0x140005728`
- `0x14000a290`
- `0x14000a648`
- `0x14000f254`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004b5c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004b5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004b16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004b8b`
- `NDIS!NdisFreeIoWorkItem` at `0x140004b7a`
- `NDIS!NdisFreeIoWorkItem` at `0x140004b7a`

## pseudocode

```c
void __fastcall NdisWanFreeOpenCB(PVOID **P)
{
  PVOID *v2; // rdx
  PVOID *v3; // rax
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, P);
  }
  if ( (*((_BYTE *)P + 20) & 9) == 9 )
    NdisWanFreeSendResources((__int64)P);
  *((_BYTE *)&WPP_MAIN_CB.Reserved + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  v2 = *P;
  if ( (*P)[1] != P || (v3 = P[1], *v3 != P) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  --dword_14001E1B0;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, *((KIRQL *)&WPP_MAIN_CB.Reserved + 8));
  NdisWanFreeNdisString(P + 8);
  v4 = P[13];
  if ( v4 )
    NdisFreeIoWorkItem(v4);
  ExFreePoolWithTag(P, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
  }
}

```

## disassembly

```asm
0x140004ab8  mov     [rsp+arg_0], rbx
0x140004abd  push    rdi
0x140004abe  sub     rsp, 20h
0x140004ac2  mov     rbx, rcx
0x140004ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140004acc  lea     rdi, WPP_GLOBAL_Control
0x140004ad3  cmp     rcx, rdi
0x140004ad6  jz      short loc_140004AFD
0x140004ad8  mov     eax, [rcx+2Ch]
0x140004adb  test    al, 40h
0x140004add  jz      short loc_140004AFD
0x140004adf  cmp     byte ptr [rcx+29h], 5
0x140004ae3  jb      short loc_140004AFD
0x140004ae5  mov     rcx, [rcx+18h]
0x140004ae9  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140004af0  mov     edx, 18h
0x140004af5  mov     r9, rbx
0x140004af8  call    WPP_SF_q
0x140004afd  mov     eax, [rbx+14h]
0x140004b00  and     eax, 9
0x140004b03  cmp     al, 9
0x140004b05  jnz     short loc_140004B0F
0x140004b07  mov     rcx, rbx
0x140004b0a  call    NdisWanFreeSendResources
0x140004b0f  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140004b16  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004b1d  nop     dword ptr [rax+rax+00h]
0x140004b22  mov     byte ptr cs:WPP_MAIN_CB+148h, al
0x140004b28  mov     rdx, [rbx]
0x140004b2b  cmp     [rdx+8], rbx
0x140004b2f  jnz     loc_140004BD1
0x140004b35  mov     rax, [rbx+8]
0x140004b39  cmp     [rax], rbx
0x140004b3c  jnz     loc_140004BD1
0x140004b42  mov     [rax], rdx
0x140004b45  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140004b4c  mov     [rdx+8], rax
0x140004b50  mov     dl, byte ptr cs:WPP_MAIN_CB+148h; NewIrql
0x140004b56  dec     cs:dword_14001E1B0
0x140004b5c  call    cs:__imp_KeReleaseSpinLock
0x140004b63  nop     dword ptr [rax+rax+00h]
0x140004b68  lea     rcx, [rbx+40h]
0x140004b6c  call    NdisWanFreeNdisString
0x140004b71  mov     rcx, [rbx+68h]; NdisIoWorkItemHandle
0x140004b75  test    rcx, rcx
0x140004b78  jz      short loc_140004B86
0x140004b7a  call    cs:__imp_NdisFreeIoWorkItem
0x140004b81  nop     dword ptr [rax+rax+00h]
0x140004b86  xor     edx, edx; Tag
0x140004b88  mov     rcx, rbx; P
0x140004b8b  call    cs:__imp_ExFreePoolWithTag
0x140004b92  nop     dword ptr [rax+rax+00h]
0x140004b97  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b9e  cmp     rcx, rdi
0x140004ba1  jz      short loc_140004BC5
0x140004ba3  mov     eax, [rcx+2Ch]
0x140004ba6  test    al, 40h
0x140004ba8  jz      short loc_140004BC5
0x140004baa  cmp     byte ptr [rcx+29h], 5
0x140004bae  jb      short loc_140004BC5
0x140004bb0  mov     rcx, [rcx+18h]
0x140004bb4  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140004bbb  mov     edx, 19h
0x140004bc0  call    WPP_SF_
0x140004bc5  mov     rbx, [rsp+28h+arg_0]
0x140004bca  add     rsp, 20h
0x140004bce  pop     rdi
0x140004bcf  retn
0x140004bd1  mov     ecx, 3
0x140004bd6  int     29h; Win8: RtlFailFast(ecx)
```
