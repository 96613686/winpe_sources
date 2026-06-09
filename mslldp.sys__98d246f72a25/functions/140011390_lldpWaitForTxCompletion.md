# lldpWaitForTxCompletion

- ea: `0x140011390`
- end: `0x140011446`
- name: `lldpWaitForTxCompletion`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010f20`

## callees

- `0x140005a6c`
- `0x140011390`
- `0x140011450`

## pseudocode

```c
__int64 __fastcall lldpWaitForTxCompletion(__int64 a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids,
      HIWORD(*(_QWORD *)(a1 + 120)),
      (*(_QWORD *)(a1 + 120) >> 24) & 0xFFFFFF);
  lldpWaitForValueToZero((_DWORD *)(a1 + 152));
  result = lldpWaitForValueToZero((_DWORD *)(a1 + 184));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_DD(
             WPP_GLOBAL_Control->AttachedDevice,
             14,
             WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids,
             HIWORD(*(_QWORD *)(a1 + 120)),
             (*(_QWORD *)(a1 + 120) >> 24) & 0xFFFFFF);
  return result;
}

```

## disassembly

```asm
0x140011390  mov     [rsp+arg_0], rbx
0x140011395  push    rdi
0x140011396  sub     rsp, 30h
0x14001139a  mov     rbx, rcx
0x14001139d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113a4  lea     rdi, WPP_GLOBAL_Control
0x1400113ab  cmp     rcx, rdi
0x1400113ae  jz      short loc_1400113E3
0x1400113b0  cmp     byte ptr [rcx+29h], 4
0x1400113b4  jb      short loc_1400113E3
0x1400113b6  mov     r9, [rbx+78h]
0x1400113ba  lea     r8, WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids
0x1400113c1  mov     rcx, [rcx+18h]
0x1400113c5  mov     rax, r9
0x1400113c8  shr     rax, 18h
0x1400113cc  mov     edx, 0Dh
0x1400113d1  and     eax, 0FFFFFFh
0x1400113d6  shr     r9, 30h
0x1400113da  mov     [rsp+38h+var_18], eax
0x1400113de  call    WPP_SF_DD
0x1400113e3  lea     rcx, [rbx+98h]
0x1400113ea  call    lldpWaitForValueToZero
0x1400113ef  lea     rcx, [rbx+0B8h]
0x1400113f6  call    lldpWaitForValueToZero
0x1400113fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011402  cmp     rcx, rdi
0x140011405  jz      short loc_14001143A
0x140011407  cmp     byte ptr [rcx+29h], 4
0x14001140b  jb      short loc_14001143A
0x14001140d  mov     r9, [rbx+78h]
0x140011411  lea     r8, WPP_546502ed7e6b3bd4e6d6388a8a9b5935_Traceguids
0x140011418  mov     rcx, [rcx+18h]
0x14001141c  mov     rax, r9
0x14001141f  shr     rax, 18h
0x140011423  mov     edx, 0Eh
0x140011428  and     eax, 0FFFFFFh
0x14001142d  shr     r9, 30h
0x140011431  mov     [rsp+38h+var_18], eax
0x140011435  call    WPP_SF_DD
0x14001143a  mov     rbx, [rsp+38h+arg_0]
0x14001143f  add     rsp, 30h
0x140011443  pop     rdi
0x140011444  retn
```
