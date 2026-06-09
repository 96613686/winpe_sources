# _CDpSearchProtocol::CreateAccessorEx_::_1_::catch$11

- ea: `0x18000b0a7`
- end: `0x18000b0fb`
- name: `_CDpSearchProtocol::CreateAccessorEx_::_1_::catch$11`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800068c4`
- `0x18000b0a7`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::CreateAccessorEx_::_1_::catch_11(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_67d934e699f83311671b1011635d052f_Traceguids,
      **(unsigned int **)(a2 + 80));
  return 0;
}

```

## disassembly

```asm
0x18000b0a7  mov     [rsp+arg_8], rdx
0x18000b0ac  push    rbp
0x18000b0ad  sub     rsp, 30h
0x18000b0b1  mov     rbp, rdx
0x18000b0b4  lea     rax, WPP_GLOBAL_Control
0x18000b0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0c2  cmp     rcx, rax
0x18000b0c5  jz      short loc_18000B0EA
0x18000b0c7  test    byte ptr [rcx+1Ch], 1
0x18000b0cb  jz      short loc_18000B0EA
0x18000b0cd  mov     edx, 0Dh
0x18000b0d2  mov     r9, [rbp+50h]
0x18000b0d6  mov     r9d, [r9]
0x18000b0d9  lea     r8, WPP_67d934e699f83311671b1011635d052f_Traceguids
0x18000b0e0  mov     rcx, [rcx+10h]
0x18000b0e4  call    WPP_SF_D
0x18000b0e9  nop
0x18000b0ea  mov     rax, 0
0x18000b0f4  add     rsp, 30h
0x18000b0f8  pop     rbp
0x18000b0f9  retn
```
