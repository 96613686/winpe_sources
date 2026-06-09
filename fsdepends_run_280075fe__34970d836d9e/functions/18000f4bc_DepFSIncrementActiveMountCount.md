# DepFSIncrementActiveMountCount

- ea: `0x18000f4bc`
- end: `0x18000f5f2`
- name: `DepFSIncrementActiveMountCount`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e88c`

## callees

- `0x180001430`
- `0x180001a08`
- `0x18000f4bc`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000f4da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18000f4da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000f5d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000f5d5`
- `ntoskrnl!KeSetEvent` at `0x18000f530`
- `ntoskrnl!KeSetEvent` at `0x18000f530`
- `ntoskrnl!KeClearEvent` at `0x18000f5c4`
- `ntoskrnl!KeClearEvent` at `0x18000f5c4`

## pseudocode

```c
__int64 __fastcall DepFSIncrementActiveMountCount(__int64 a1)
{
  __int64 v1; // rdi
  _WORD v4[2]; // [rsp+40h] [rbp-18h] BYREF
  int v5; // [rsp+44h] [rbp-14h]
  __int64 v6; // [rsp+48h] [rbp-10h]

  v1 = a1 + 184;
  ExAcquirePushLockExclusiveEx(a1 + 184, 0);
  if ( *(int *)(a1 + 192) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids);
    }
    KeSetEvent(&Event, 0, 0);
  }
  v4[0] = *(_WORD *)(a1 + 138);
  v4[1] = v4[0];
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 144);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qddZ(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      (unsigned int)WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
      a1,
      *(_DWORD *)(a1 + 192),
      *(_DWORD *)(a1 + 192) + 1,
      (__int64)v4);
  }
  if ( ++*(_DWORD *)(a1 + 192) == 1 )
    KeClearEvent((PRKEVENT)(a1 + 200));
  return ExReleasePushLockExclusiveEx(v1, 0);
}

```

## disassembly

```asm
0x18000f4bc  mov     [rsp+arg_0], rbx
0x18000f4c1  mov     [rsp+arg_8], rsi
0x18000f4c6  push    rdi
0x18000f4c7  sub     rsp, 50h
0x18000f4cb  lea     rdi, [rcx+0B8h]
0x18000f4d2  mov     rbx, rcx
0x18000f4d5  mov     rcx, rdi
0x18000f4d8  xor     edx, edx
0x18000f4da  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18000f4e1  nop     dword ptr [rax+rax+00h]
0x18000f4e6  cmp     dword ptr [rbx+0C0h], 0
0x18000f4ed  lea     rsi, WPP_GLOBAL_Control
0x18000f4f4  jge     short loc_18000F53C
0x18000f4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4fd  cmp     rcx, rsi
0x18000f500  jz      short loc_18000F524
0x18000f502  mov     eax, [rcx+2Ch]
0x18000f505  test    al, 1
0x18000f507  jz      short loc_18000F524
0x18000f509  cmp     byte ptr [rcx+29h], 2
0x18000f50d  jb      short loc_18000F524
0x18000f50f  mov     rcx, [rcx+18h]
0x18000f513  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000f51a  mov     edx, 15h
0x18000f51f  call    WPP_SF_
0x18000f524  xor     r8d, r8d; Wait
0x18000f527  lea     rcx, Event; Event
0x18000f52e  xor     edx, edx; Increment
0x18000f530  call    cs:__imp_KeSetEvent
0x18000f537  nop     dword ptr [rax+rax+00h]
0x18000f53c  movzx   eax, word ptr [rbx+8Ah]
0x18000f543  mov     [rsp+58h+var_18], ax
0x18000f548  mov     [rsp+58h+var_16], ax
0x18000f54d  xor     eax, eax
0x18000f54f  mov     [rsp+58h+var_14], eax
0x18000f553  mov     rax, [rbx+90h]
0x18000f55a  mov     [rsp+58h+var_10], rax
0x18000f55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f566  cmp     rcx, rsi
0x18000f569  jz      short loc_18000F5AE
0x18000f56b  mov     eax, [rcx+2Ch]
0x18000f56e  test    al, 10h
0x18000f570  jz      short loc_18000F5AE
0x18000f572  cmp     byte ptr [rcx+29h], 4
0x18000f576  jb      short loc_18000F5AE
0x18000f578  mov     r9d, [rbx+0C0h]
0x18000f57f  lea     r10, [rsp+58h+var_18]
0x18000f584  mov     rcx, [rcx+18h]
0x18000f588  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000f58f  mov     [rsp+58h+var_28], r10
0x18000f594  mov     edx, 16h
0x18000f599  lea     eax, [r9+1]
0x18000f59d  mov     [rsp+58h+var_30], eax
0x18000f5a1  mov     [rsp+58h+var_38], r9d
0x18000f5a6  mov     r9, rbx
0x18000f5a9  call    WPP_SF_qddZ
0x18000f5ae  inc     dword ptr [rbx+0C0h]
0x18000f5b4  cmp     dword ptr [rbx+0C0h], 1
0x18000f5bb  jnz     short loc_18000F5D0
0x18000f5bd  lea     rcx, [rbx+0C8h]; Event
0x18000f5c4  call    cs:__imp_KeClearEvent
0x18000f5cb  nop     dword ptr [rax+rax+00h]
0x18000f5d0  xor     edx, edx
0x18000f5d2  mov     rcx, rdi
0x18000f5d5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18000f5dc  nop     dword ptr [rax+rax+00h]
0x18000f5e1  mov     rbx, [rsp+58h+arg_0]
0x18000f5e6  mov     rsi, [rsp+58h+arg_8]
0x18000f5eb  add     rsp, 50h
0x18000f5ef  pop     rdi
0x18000f5f0  retn
```
