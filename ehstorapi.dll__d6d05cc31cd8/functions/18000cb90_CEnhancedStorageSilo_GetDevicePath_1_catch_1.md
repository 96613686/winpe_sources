# _CEnhancedStorageSilo::GetDevicePath_::_1_::catch$1

- ea: `0x18000cb90`
- end: `0x18000cbe5`
- name: `_CEnhancedStorageSilo::GetDevicePath_::_1_::catch$1`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c54`
- `0x18000cb90`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::GetDevicePath_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 36);
  *(_DWORD *)(a2 + 32) = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x18000cb90  mov     [rsp+arg_8], rdx
0x18000cb95  push    rbp
0x18000cb96  sub     rsp, 20h
0x18000cb9a  mov     rbp, rdx
0x18000cb9d  mov     r9d, [rbp+24h]
0x18000cba1  mov     [rbp+20h], r9d
0x18000cba5  lea     rax, WPP_GLOBAL_Control
0x18000cbac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbb3  cmp     rcx, rax
0x18000cbb6  jz      short loc_18000CBD4
0x18000cbb8  test    byte ptr [rcx+1Ch], 2
0x18000cbbc  jz      short loc_18000CBD4
0x18000cbbe  mov     edx, 3Ah ; ':'
0x18000cbc3  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x18000cbca  mov     rcx, [rcx+10h]
0x18000cbce  call    WPP_SF_d
0x18000cbd3  nop
0x18000cbd4  mov     rax, 0
0x18000cbde  add     rsp, 20h
0x18000cbe2  pop     rbp
0x18000cbe3  retn
```
