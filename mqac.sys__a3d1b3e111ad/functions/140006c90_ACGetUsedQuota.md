# ACGetUsedQuota

- ea: `0x140006c90`
- end: `0x140006d48`
- name: `ACGetUsedQuota`
- size: `184`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140001c04`
- `0x140006c90`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140006ce1`
- `ntoskrnl!ProbeForWrite` at `0x140006ce1`

## pseudocode

```c
__int64 __fastcall ACGetUsedQuota(__int64 a1, _QWORD *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 211, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  ProbeForWrite(a2, 8u, 1u);
  *a2 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 1016LL);
  return 0;
}

```

## disassembly

```asm
0x140006c90  mov     [rsp+arg_0], rbx
0x140006c95  mov     [rsp+arg_8], rdx
0x140006c9a  push    rdi
0x140006c9b  sub     rsp, 30h
0x140006c9f  mov     rbx, rdx
0x140006ca2  mov     rdi, rcx
0x140006ca5  lea     rax, WPP_GLOBAL_Control
0x140006cac  mov     rcx, cs:WPP_GLOBAL_Control
0x140006cb3  cmp     rcx, rax
0x140006cb6  jz      short loc_140006CD5
0x140006cb8  mov     eax, [rcx+6Ch]
0x140006cbb  test    al, 1
0x140006cbd  jz      short loc_140006CD5
0x140006cbf  mov     edx, 0D3h
0x140006cc4  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006ccb  mov     rcx, [rcx+58h]
0x140006ccf  call    WPP_SF_
0x140006cd4  nop
0x140006cd5  mov     edx, 8; Length
0x140006cda  lea     r8d, [rdx-7]; Alignment
0x140006cde  mov     rcx, rbx; Address
0x140006ce1  call    cs:__imp_ProbeForWrite
0x140006ce8  nop     dword ptr [rax+rax+00h]
0x140006ced  mov     rax, [rdi+40h]
0x140006cf1  mov     rcx, [rax+3F8h]
0x140006cf8  mov     [rbx], rcx
0x140006cfb  xor     eax, eax
0x140006cfd  jmp     short loc_140006D3C
0x140006cff  mov     ebx, eax
0x140006d01  lea     rax, WPP_GLOBAL_Control
0x140006d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d0f  cmp     rcx, rax
0x140006d12  jz      short loc_140006D3A
0x140006d14  mov     edx, [rcx+6Ch]
0x140006d17  test    dl, 1
0x140006d1a  jz      short loc_140006D3A
0x140006d1c  mov     edx, 0D4h
0x140006d21  mov     [rsp+38h+var_18], ebx
0x140006d25  mov     r9, [rsp+38h+arg_8]
0x140006d2a  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006d31  mov     rcx, [rcx+58h]
0x140006d35  call    WPP_SF_qD
0x140006d3a  mov     eax, ebx
0x140006d3c  mov     rbx, [rsp+38h+arg_0]
0x140006d41  add     rsp, 30h
0x140006d45  pop     rdi
0x140006d46  retn
```
