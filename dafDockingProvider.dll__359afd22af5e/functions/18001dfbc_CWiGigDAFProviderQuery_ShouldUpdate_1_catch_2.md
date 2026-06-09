# _CWiGigDAFProviderQuery::ShouldUpdate_::_1_::catch$2

- ea: `0x18001dfbc`
- end: `0x18001e013`
- name: `_CWiGigDAFProviderQuery::ShouldUpdate_::_1_::catch$2`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000c308`
- `0x18001dfbc`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderQuery::ShouldUpdate_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids,
      *(_QWORD *)(a2 + 64));
  }
  return 0;
}

```

## disassembly

```asm
0x18001dfbc  mov     [rsp+arg_8], rdx
0x18001dfc1  push    rbp
0x18001dfc2  sub     rsp, 30h
0x18001dfc6  mov     rbp, rdx
0x18001dfc9  lea     rax, WPP_GLOBAL_Control
0x18001dfd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfd7  cmp     rcx, rax
0x18001dfda  jz      short loc_18001E002
0x18001dfdc  cmp     byte ptr [rcx+19h], 1
0x18001dfe0  jb      short loc_18001E002
0x18001dfe2  test    byte ptr [rcx+1Ch], 1
0x18001dfe6  jz      short loc_18001E002
0x18001dfe8  mov     edx, 1Fh
0x18001dfed  mov     r9, [rbp+40h]
0x18001dff1  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x18001dff8  mov     rcx, [rcx+10h]
0x18001dffc  call    WPP_SF_q
0x18001e001  nop
0x18001e002  mov     rax, 0
0x18001e00c  add     rsp, 30h
0x18001e010  pop     rbp
0x18001e011  retn
```
