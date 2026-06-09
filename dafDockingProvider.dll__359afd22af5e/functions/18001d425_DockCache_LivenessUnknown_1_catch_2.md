# _DockCache::LivenessUnknown_::_1_::catch$2

- ea: `0x18001d425`
- end: `0x18001d485`
- name: `_DockCache::LivenessUnknown_::_1_::catch$2`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d425`

## pseudocode

```c
__int64 __fastcall DockCache::LivenessUnknown_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d425  mov     [rsp+arg_8], rdx
0x18001d42a  push    rbp
0x18001d42b  sub     rsp, 40h
0x18001d42f  mov     rbp, rdx
0x18001d432  lea     rax, WPP_GLOBAL_Control
0x18001d439  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d440  cmp     rcx, rax
0x18001d443  jz      short loc_18001D474
0x18001d445  cmp     byte ptr [rcx+19h], 1
0x18001d449  jb      short loc_18001D474
0x18001d44b  test    byte ptr [rcx+1Ch], 1
0x18001d44f  jz      short loc_18001D474
0x18001d451  mov     edx, 36h ; '6'
0x18001d456  mov     rax, [rbp+50h]
0x18001d45a  mov     [rsp+48h+var_28], rax
0x18001d45f  mov     r9, [rbp+40h]
0x18001d463  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d46a  mov     rcx, [rcx+10h]
0x18001d46e  call    WPP_SF_qS
0x18001d473  nop
0x18001d474  mov     rax, 0
0x18001d47e  add     rsp, 40h
0x18001d482  pop     rbp
0x18001d483  retn
```
