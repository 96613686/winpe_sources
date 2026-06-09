# _LoadUserConfiguration_::_1_::catch$2

- ea: `0x180011ce0`
- end: `0x180011d46`
- name: `_LoadUserConfiguration_::_1_::catch$2`
- size: `102`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000ca14`
- `0x180011ce0`

## pseudocode

```c
__int64 __fastcall LoadUserConfiguration_::_1_::catch_2(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 68);
  *(_DWORD *)(a2 + 112) = v2;
  if ( (int)v2 >= 0 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_efece49b8938379c060169b7945fb4b7_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x180011ce0  mov     [rsp+arg_8], rdx
0x180011ce5  push    rbp
0x180011ce6  sub     rsp, 40h
0x180011cea  mov     rbp, rdx
0x180011ced  mov     r9d, [rbp+44h]
0x180011cf1  mov     [rbp+70h], r9d
0x180011cf5  test    r9d, r9d
0x180011cf8  jns     short loc_180011D35
0x180011cfa  lea     rax, WPP_GLOBAL_Control
0x180011d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d08  cmp     rcx, rax
0x180011d0b  jz      short loc_180011D29
0x180011d0d  test    byte ptr [rcx+1Ch], 1
0x180011d11  jz      short loc_180011D29
0x180011d13  mov     edx, 18h
0x180011d18  lea     r8, WPP_efece49b8938379c060169b7945fb4b7_Traceguids
0x180011d1f  mov     rcx, [rcx+10h]
0x180011d23  call    WPP_SF_d
0x180011d28  nop
0x180011d29  mov     rax, 0
0x180011d33  jmp     short loc_180011D3F
0x180011d35  mov     rax, 1
0x180011d3f  add     rsp, 40h
0x180011d43  pop     rbp
0x180011d44  retn
```
