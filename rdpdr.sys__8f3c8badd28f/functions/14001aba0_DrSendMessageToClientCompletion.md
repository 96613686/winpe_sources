# DrSendMessageToClientCompletion

- ea: `0x14001aba0`
- end: `0x14001ac0a`
- name: `DrSendMessageToClientCompletion`
- size: `106`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001e30`
- `0x14000327c`
- `0x140006560`
- `0x14001aba0`

## pseudocode

```c
__int64 __fastcall DrSendMessageToClientCompletion(_QWORD *a1, unsigned int *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids, *a2);
  if ( *a1 )
    ((void (__fastcall *)(_QWORD, _QWORD))*a1)(a1[1], *a2);
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x14001aba0  mov     [rsp+arg_0], rbx
0x14001aba5  push    rdi
0x14001aba6  sub     rsp, 20h
0x14001abaa  mov     rdi, rdx
0x14001abad  mov     rbx, rcx
0x14001abb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001abb7  lea     rax, WPP_GLOBAL_Control
0x14001abbe  cmp     rcx, rax
0x14001abc1  jz      short loc_14001ABE1
0x14001abc3  cmp     byte ptr [rcx+29h], 4
0x14001abc7  jb      short loc_14001ABE1
0x14001abc9  mov     r9d, [rdi]
0x14001abcc  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x14001abd3  mov     rcx, [rcx+18h]
0x14001abd7  mov     edx, 23h ; '#'
0x14001abdc  call    WPP_SF_d
0x14001abe1  mov     rax, [rbx]
0x14001abe4  test    rax, rax
0x14001abe7  jz      short loc_14001ABF4
0x14001abe9  mov     edx, [rdi]
0x14001abeb  mov     rcx, [rbx+8]
0x14001abef  call    _guard_dispatch_icall
0x14001abf4  mov     rcx, rbx; void *
0x14001abf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001abfc  mov     rbx, [rsp+28h+arg_0]
0x14001ac01  xor     eax, eax
0x14001ac03  add     rsp, 20h
0x14001ac07  pop     rdi
0x14001ac08  retn
```
