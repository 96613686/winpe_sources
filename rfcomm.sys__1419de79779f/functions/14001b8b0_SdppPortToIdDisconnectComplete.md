# SdppPortToIdDisconnectComplete

- ea: `0x14001b8b0`
- end: `0x14001b967`
- name: `SdppPortToIdDisconnectComplete`
- size: `183`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001b970`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001b8b0`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14001b915`
- `ntoskrnl!ExFreePool` at `0x14001b924`
- `ntoskrnl!ExFreePool` at `0x14001b915`
- `ntoskrnl!ExFreePool` at `0x14001b924`

## pseudocode

```c
void __fastcall SdppPortToIdDisconnectComplete(unsigned int *P, int a2)
{
  void *v4; // rcx
  int v5; // edx
  int v6; // [rsp+28h] [rbp-30h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      43,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))P + 8))(*P, *((_QWORD *)P + 9), *((_QWORD *)P + 11), P[20]);
  v4 = (void *)*((_QWORD *)P + 11);
  if ( v4 )
    ExFreePool(v4);
  ExFreePool(P);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = a2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      44,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
      v6);
  }
}

```

## disassembly

```asm
0x14001b8b0  push    rbx
0x14001b8b2  push    rsi
0x14001b8b3  push    rdi
0x14001b8b4  push    r14
0x14001b8b6  sub     rsp, 38h
0x14001b8ba  mov     edi, edx
0x14001b8bc  mov     rbx, rcx
0x14001b8bf  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001b8c6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001b8cd  lea     r14, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001b8d4  jz      short loc_14001B8F5
0x14001b8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8dd  mov     r9d, 2Bh ; '+'
0x14001b8e3  mov     [rsp+58h+var_38], r14
0x14001b8e8  mov     rcx, [rcx+40h]
0x14001b8ec  lea     r8d, [r9-28h]
0x14001b8f0  call    WPP_RECORDER_SF_
0x14001b8f5  mov     rax, [rbx+40h]
0x14001b8f9  mov     r9d, [rbx+50h]
0x14001b8fd  mov     r8, [rbx+58h]
0x14001b901  mov     rdx, [rbx+48h]
0x14001b905  mov     ecx, [rbx]
0x14001b907  call    _guard_dispatch_icall
0x14001b90c  mov     rcx, [rbx+58h]; P
0x14001b910  test    rcx, rcx
0x14001b913  jz      short loc_14001B921
0x14001b915  call    cs:__imp_ExFreePool
0x14001b91c  nop     dword ptr [rax+rax+00h]
0x14001b921  mov     rcx, rbx; P
0x14001b924  call    cs:__imp_ExFreePool
0x14001b92b  nop     dword ptr [rax+rax+00h]
0x14001b930  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001b937  jz      short loc_14001B95C
0x14001b939  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b940  mov     r9d, 2Ch ; ','
0x14001b946  mov     [rsp+58h+var_30], edi
0x14001b94a  mov     [rsp+58h+var_38], r14
0x14001b94f  mov     rcx, [rcx+40h]
0x14001b953  lea     r8d, [r9-29h]
0x14001b957  call    WPP_RECORDER_SF_d
0x14001b95c  add     rsp, 38h
0x14001b960  pop     r14
0x14001b962  pop     rdi
0x14001b963  pop     rsi
0x14001b964  pop     rbx
0x14001b965  retn
```
