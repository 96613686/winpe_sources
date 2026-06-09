# MdaUpdateNetRootState

- ea: `0x140028570`
- end: `0x1400285ff`
- name: `MdaUpdateNetRootState`
- size: `143`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400159cc`
- `0x1400175d4`
- `0x140028570`

## pseudocode

```c
__int64 __fastcall MdaUpdateNetRootState(__int64 a1)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      58,
      WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
      a1,
      *(_QWORD *)(a1 + 40));
  *(_BYTE *)(a1 + 76) = *(_QWORD *)(a1 + 40) == 0 ? 3 : 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140028570  mov     [rsp+arg_0], rbx
0x140028575  push    rdi
0x140028576  sub     rsp, 30h
0x14002857a  mov     rbx, rcx
0x14002857d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028584  lea     rdi, WPP_GLOBAL_Control
0x14002858b  cmp     rcx, rdi
0x14002858e  jz      short loc_1400285B8
0x140028590  mov     eax, [rcx+2Ch]
0x140028593  test    al, 8
0x140028595  jz      short loc_1400285B8
0x140028597  mov     rax, [rbx+28h]
0x14002859b  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400285a2  mov     rcx, [rcx+18h]
0x1400285a6  mov     edx, 3Ah ; ':'
0x1400285ab  mov     r9, rbx
0x1400285ae  mov     [rsp+38h+var_18], rax
0x1400285b3  call    WPP_SF_qq
0x1400285b8  mov     rax, [rbx+28h]
0x1400285bc  neg     rax
0x1400285bf  sbb     cl, cl
0x1400285c1  not     cl
0x1400285c3  and     cl, 3
0x1400285c6  mov     [rbx+4Ch], cl
0x1400285c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400285d0  cmp     rcx, rdi
0x1400285d3  jz      short loc_1400285F1
0x1400285d5  mov     eax, [rcx+2Ch]
0x1400285d8  test    al, 8
0x1400285da  jz      short loc_1400285F1
0x1400285dc  mov     rcx, [rcx+18h]
0x1400285e0  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400285e7  mov     edx, 3Bh ; ';'
0x1400285ec  call    WPP_SF_
0x1400285f1  mov     rbx, [rsp+38h+arg_0]
0x1400285f6  xor     eax, eax
0x1400285f8  add     rsp, 30h
0x1400285fc  pop     rdi
0x1400285fd  retn
```
