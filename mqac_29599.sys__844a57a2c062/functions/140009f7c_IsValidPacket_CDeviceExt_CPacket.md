# IsValidPacket(CDeviceExt *,CPacket *)

- ea: `0x140009f7c`
- end: `0x14000a0fe`
- name: `?IsValidPacket@@YAHPEAUCDeviceExt@@PEAVCPacket@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct CDeviceExt *, struct CPacket *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009a54`

## callees

- `0x140003d84`
- `0x140009f7c`
- `0x14000baa0`

## import_xrefs

- `ntoskrnl!MmIsKernelAddress` at `0x140009ff5`
- `ntoskrnl!MmIsKernelAddress` at `0x140009ff5`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a037`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14000a037`

## pseudocode

```c
__int64 __fastcall IsValidPacket(struct CDeviceExt *a1, struct CPacket *a2)
{
  unsigned int v3; // ebx

  v3 = 1;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 11, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, 0);
    }
    return 0;
  }
  if ( (unsigned __int64)a2 < *((_QWORD *)a1 + 59) || (unsigned __int64)a2 > *((_QWORD *)a1 + 58) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_qqq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        12,
        &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        *((_QWORD *)a1 + 59),
        a2,
        *((_QWORD *)a1 + 58));
    }
    return 0;
  }
  if ( !(unsigned __int8)MmIsKernelAddress(a2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a2);
    }
    ExRaiseAccessViolation();
  }
  *(_DWORD *)a2 = *(_DWORD *)a2;
  return v3;
}

```

## disassembly

```asm
0x140009f7c  mov     [rsp+arg_10], rbx
0x140009f81  mov     [rsp+arg_8], rdx
0x140009f86  mov     [rsp+arg_0], rcx
0x140009f8b  push    rdi
0x140009f8c  sub     rsp, 40h
0x140009f90  mov     rdi, rdx
0x140009f93  mov     ebx, 1
0x140009f98  test    rdx, rdx
0x140009f9b  jnz     short loc_140009FDA
0x140009f9d  lea     rax, WPP_GLOBAL_Control
0x140009fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fab  cmp     rcx, rax
0x140009fae  jz      loc_14000A091
0x140009fb4  mov     eax, [rcx+6Ch]
0x140009fb7  test    bl, al
0x140009fb9  jz      loc_14000A091
0x140009fbf  lea     edx, [rdi+0Bh]
0x140009fc2  xor     r9d, r9d
0x140009fc5  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009fcc  mov     rcx, [rcx+58h]
0x140009fd0  call    WPP_SF_q
0x140009fd5  jmp     loc_14000A091
0x140009fda  mov     rax, [rcx+1D8h]
0x140009fe1  cmp     rdi, rax
0x140009fe4  jb      short loc_14000A049
0x140009fe6  mov     rax, [rcx+1D0h]
0x140009fed  cmp     rdi, rax
0x140009ff0  ja      short loc_14000A049
0x140009ff2  mov     rcx, rdi
0x140009ff5  call    cs:__imp_MmIsKernelAddress
0x140009ffc  nop     dword ptr [rax+rax+00h]
0x14000a001  test    al, al
0x14000a003  jnz     short loc_14000A043
0x14000a005  lea     rax, WPP_GLOBAL_Control
0x14000a00c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a013  cmp     rcx, rax
0x14000a016  jz      short loc_14000A037
0x14000a018  mov     eax, [rcx+6Ch]
0x14000a01b  test    bl, al
0x14000a01d  jz      short loc_14000A037
0x14000a01f  mov     edx, 0Ah
0x14000a024  mov     r9, rdi
0x14000a027  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a02e  mov     rcx, [rcx+58h]
0x14000a032  call    WPP_SF_q
0x14000a037  call    cs:__imp_ExRaiseAccessViolation
0x14000a03e  nop     dword ptr [rax+rax+00h]
0x14000a043  mov     eax, [rdi]
0x14000a045  mov     [rdi], eax
0x14000a047  jmp     short loc_14000A097
0x14000a049  lea     rax, WPP_GLOBAL_Control
0x14000a050  mov     r10, cs:WPP_GLOBAL_Control
0x14000a057  cmp     r10, rax
0x14000a05a  jz      short loc_14000A091
0x14000a05c  mov     eax, [r10+6Ch]
0x14000a060  test    bl, al
0x14000a062  jz      short loc_14000A091
0x14000a064  mov     edx, 0Ch
0x14000a069  mov     rax, [rcx+1D0h]
0x14000a070  mov     [rsp+48h+var_20], rax
0x14000a075  mov     [rsp+48h+var_28], rdi
0x14000a07a  mov     r9, [rcx+1D8h]
0x14000a081  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a088  mov     rcx, [r10+58h]
0x14000a08c  call    WPP_SF_qqq
0x14000a091  xor     ebx, ebx
0x14000a093  mov     [rsp+48h+var_18], ebx
0x14000a097  jmp     short loc_14000A0F0
0x14000a099  lea     rax, WPP_GLOBAL_Control
0x14000a0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0a7  cmp     rcx, rax
0x14000a0aa  jz      short loc_14000A0EA
0x14000a0ac  mov     eax, [rcx+6Ch]
0x14000a0af  test    al, 1
0x14000a0b1  jz      short loc_14000A0EA
0x14000a0b3  mov     edx, 0Dh
0x14000a0b8  mov     r9, [rsp+48h+arg_0]
0x14000a0bd  mov     rax, [r9+1D0h]
0x14000a0c4  mov     [rsp+48h+var_20], rax
0x14000a0c9  mov     rax, [rsp+48h+arg_8]
0x14000a0ce  mov     [rsp+48h+var_28], rax
0x14000a0d3  mov     r9, [r9+1D8h]
0x14000a0da  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a0e1  mov     rcx, [rcx+58h]
0x14000a0e5  call    WPP_SF_qqq
0x14000a0ea  xor     ebx, ebx
0x14000a0ec  mov     [rsp+48h+var_18], ebx
0x14000a0f0  mov     eax, ebx
0x14000a0f2  mov     rbx, [rsp+48h+arg_10]
0x14000a0f7  add     rsp, 40h
0x14000a0fb  pop     rdi
0x14000a0fc  retn
```
