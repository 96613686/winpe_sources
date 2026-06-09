# BrbpWriteComplete

- ea: `0x14000ee70`
- end: `0x14000ef41`
- name: `BrbpWriteComplete`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000ee70`
- `0x14000f758`
- `0x140015c4c`
- `0x14001bfa8`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000eee7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eee7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ee9b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ee9b`

## pseudocode

```c
__int64 __fastcall BrbpWriteComplete(__int64 a1, __int64 a2, __int64 *a3, int a4)
{
  void *DeviceExtension; // rdi
  int v9; // edx
  int v10; // r8d
  __int64 result; // rax
  int v12; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    NtStatusTxt(a4);
    WPP_RECORDER_SF_qsd((_DWORD)DeviceExtension, v9, v10, 53);
  }
  RfcommWriteComplete(a3, a4);
  ExFreePoolWithTag(a3, 0);
  result = (*(__int64 (__fastcall **)(__int64))(a1 + 320))(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v12,
             3,
             54,
             (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000ee70  push    rbx
0x14000ee72  push    rbp
0x14000ee73  push    rsi
0x14000ee74  push    rdi
0x14000ee75  push    r12
0x14000ee77  push    r14
0x14000ee79  push    r15
0x14000ee7b  sub     rsp, 40h
0x14000ee7f  mov     esi, r9d
0x14000ee82  mov     r14, r8
0x14000ee85  mov     rbp, rdx
0x14000ee88  mov     r15, rcx
0x14000ee8b  lea     r12, WPP_RECORDER_INITIALIZED
0x14000ee92  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000ee99  jz      short loc_14000EED8
0x14000ee9b  call    cs:__imp_KeGetCurrentIrql
0x14000eea2  nop     dword ptr [rax+rax+00h]
0x14000eea7  movzx   ebx, al
0x14000eeaa  mov     ecx, esi
0x14000eeac  mov     rax, cs:WPP_GLOBAL_Control
0x14000eeb3  mov     rdi, [rax+40h]
0x14000eeb7  call    NtStatusTxt
0x14000eebc  mov     [rsp+78h+var_40], ebx
0x14000eec0  mov     r9d, 35h ; '5'
0x14000eec6  mov     [rsp+78h+var_48], rax
0x14000eecb  mov     rcx, rdi
0x14000eece  mov     [rsp+78h+var_50], rbp
0x14000eed3  call    WPP_RECORDER_SF_qsd
0x14000eed8  mov     edx, esi
0x14000eeda  mov     rcx, r14
0x14000eedd  call    RfcommWriteComplete
0x14000eee2  xor     edx, edx; Tag
0x14000eee4  mov     rcx, r14; P
0x14000eee7  call    cs:__imp_ExFreePoolWithTag
0x14000eeee  nop     dword ptr [rax+rax+00h]
0x14000eef3  mov     rax, [r15+140h]
0x14000eefa  mov     rcx, rbp
0x14000eefd  call    _guard_dispatch_icall
0x14000ef02  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000ef09  jz      short loc_14000EF31
0x14000ef0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef12  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000ef19  mov     r9d, 36h ; '6'
0x14000ef1f  mov     [rsp+78h+var_58], rax
0x14000ef24  mov     rcx, [rcx+40h]
0x14000ef28  lea     r8d, [r9-33h]
0x14000ef2c  call    WPP_RECORDER_SF_
0x14000ef31  add     rsp, 40h
0x14000ef35  pop     r15
0x14000ef37  pop     r14
0x14000ef39  pop     r12
0x14000ef3b  pop     rdi
0x14000ef3c  pop     rsi
0x14000ef3d  pop     rbp
0x14000ef3e  pop     rbx
0x14000ef3f  retn
```
