# BrbUpdateCompletion

- ea: `0x14000de90`
- end: `0x14000df62`
- name: `BrbUpdateCompletion`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000de90`
- `0x14000f1b4`
- `0x140018330`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000dec9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000dec9`

## pseudocode

```c
__int64 __fastcall BrbUpdateCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  int *v6; // rbx
  int *v7; // rdi
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  __int64 result; // rax
  int v12; // edx

  v6 = (int *)(a2 + 132);
  v7 = (int *)(a2 + 128);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    WPP_RECORDER_SF_dDDqqd(WPP_GLOBAL_Control->DeviceExtension, v8, v9, v10);
  }
  SessionProcessPendingUpdates(a3, *v7, *v6);
  result = (*(__int64 (__fastcall **)(__int64))(a1 + 320))(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v12,
             3,
             43,
             (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000de90  push    rbx
0x14000de92  push    rbp
0x14000de93  push    rsi
0x14000de94  push    rdi
0x14000de95  push    r12
0x14000de97  push    r14
0x14000de99  push    r15
0x14000de9b  sub     rsp, 60h
0x14000de9f  mov     r14d, r9d
0x14000dea2  mov     rbp, r8
0x14000dea5  mov     rsi, rdx
0x14000dea8  mov     r15, rcx
0x14000deab  lea     r12, WPP_RECORDER_INITIALIZED
0x14000deb2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000deb9  lea     rbx, [rdx+84h]
0x14000dec0  lea     rdi, [rdx+80h]
0x14000dec7  jz      short loc_14000DF07
0x14000dec9  call    cs:__imp_KeGetCurrentIrql
0x14000ded0  nop     dword ptr [rax+rax+00h]
0x14000ded5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dedc  movzx   eax, al
0x14000dedf  mov     [rsp+98h+var_48], eax
0x14000dee3  mov     eax, [rbx]
0x14000dee5  mov     rcx, [rcx+40h]
0x14000dee9  mov     [rsp+98h+var_50], rsi
0x14000deee  mov     [rsp+98h+var_58], rbp
0x14000def3  mov     [rsp+98h+var_60], eax
0x14000def7  mov     eax, [rdi]
0x14000def9  mov     [rsp+98h+var_68], eax
0x14000defd  mov     [rsp+98h+var_70], r14d
0x14000df02  call    WPP_RECORDER_SF_dDDqqd
0x14000df07  mov     r8d, [rbx]
0x14000df0a  mov     rcx, rbp
0x14000df0d  mov     edx, [rdi]
0x14000df0f  call    SessionProcessPendingUpdates
0x14000df14  mov     rax, [r15+140h]
0x14000df1b  mov     rcx, rsi
0x14000df1e  call    _guard_dispatch_icall
0x14000df23  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000df2a  jz      short loc_14000DF52
0x14000df2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df33  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000df3a  mov     r9d, 2Bh ; '+'
0x14000df40  mov     [rsp+98h+var_78], rax
0x14000df45  mov     rcx, [rcx+40h]
0x14000df49  lea     r8d, [r9-28h]
0x14000df4d  call    WPP_RECORDER_SF_
0x14000df52  add     rsp, 60h
0x14000df56  pop     r15
0x14000df58  pop     r14
0x14000df5a  pop     r12
0x14000df5c  pop     rdi
0x14000df5d  pop     rsi
0x14000df5e  pop     rbp
0x14000df5f  pop     rbx
0x14000df60  retn
```
