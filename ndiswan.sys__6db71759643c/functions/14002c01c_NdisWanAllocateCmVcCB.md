# NdisWanAllocateCmVcCB

- ea: `0x14002c01c`
- end: `0x14002c0b4`
- name: `NdisWanAllocateCmVcCB`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400259b0`

## callees

- `0x14000a290`
- `0x140016700`
- `0x14002c01c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002c038`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002c038`

## pseudocode

```c
_QWORD *__fastcall NdisWanAllocateCmVcCB(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *result; // rax

  v4 = ExAllocateFromNPagedLookasideList(&AfSapVcCBList);
  v5 = v4;
  if ( v4 )
  {
    memset(v4, 0, 0x50u);
    result = v5;
    v5[7] = a1;
    *((_DWORD *)v5 + 4) = 1666608451;
    v5[5] = a2;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002c01c  mov     [rsp+arg_0], rbx
0x14002c021  mov     [rsp+arg_8], rsi
0x14002c026  push    rdi
0x14002c027  sub     rsp, 20h
0x14002c02b  mov     rsi, rcx
0x14002c02e  mov     rdi, rdx
0x14002c031  lea     rcx, AfSapVcCBList; Lookaside
0x14002c038  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002c03f  nop     dword ptr [rax+rax+00h]
0x14002c044  mov     rbx, rax
0x14002c047  test    rax, rax
0x14002c04a  jnz     short loc_14002C083
0x14002c04c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c053  lea     rax, WPP_GLOBAL_Control
0x14002c05a  cmp     rcx, rax
0x14002c05d  jz      short loc_14002C07F
0x14002c05f  mov     eax, [rcx+2Ch]
0x14002c062  test    al, 40h
0x14002c064  jz      short loc_14002C07F
0x14002c066  cmp     byte ptr [rcx+29h], 2
0x14002c06a  jb      short loc_14002C07F
0x14002c06c  mov     rcx, [rcx+18h]
0x14002c070  lea     edx, [rbx+28h]
0x14002c073  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14002c07a  call    WPP_SF_
0x14002c07f  xor     eax, eax
0x14002c081  jmp     short loc_14002C0A3
0x14002c083  xor     edx, edx; Val
0x14002c085  mov     rcx, rbx; void *
0x14002c088  lea     r8d, [rdx+50h]; Size
0x14002c08c  call    memset
0x14002c091  mov     rax, rbx
0x14002c094  mov     [rbx+38h], rsi
0x14002c098  mov     dword ptr [rbx+10h], 63566D43h
0x14002c09f  mov     [rbx+28h], rdi
0x14002c0a3  mov     rbx, [rsp+28h+arg_0]
0x14002c0a8  mov     rsi, [rsp+28h+arg_8]
0x14002c0ad  add     rsp, 20h
0x14002c0b1  pop     rdi
0x14002c0b2  retn
```
