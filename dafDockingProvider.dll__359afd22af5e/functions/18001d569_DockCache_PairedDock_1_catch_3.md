# _DockCache::PairedDock_::_1_::catch$3

- ea: `0x18001d569`
- end: `0x18001d5c9`
- name: `_DockCache::PairedDock_::_1_::catch$3`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d569`

## pseudocode

```c
__int64 __fastcall DockCache::PairedDock_::_1_::catch_3(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d569  mov     [rsp+arg_8], rdx
0x18001d56e  push    rbp
0x18001d56f  sub     rsp, 40h
0x18001d573  mov     rbp, rdx
0x18001d576  lea     rax, WPP_GLOBAL_Control
0x18001d57d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d584  cmp     rcx, rax
0x18001d587  jz      short loc_18001D5B8
0x18001d589  cmp     byte ptr [rcx+19h], 1
0x18001d58d  jb      short loc_18001D5B8
0x18001d58f  test    byte ptr [rcx+1Ch], 1
0x18001d593  jz      short loc_18001D5B8
0x18001d595  mov     edx, 2Bh ; '+'
0x18001d59a  mov     rax, [rbp+50h]
0x18001d59e  mov     [rsp+48h+var_28], rax
0x18001d5a3  mov     r9, [rbp+40h]
0x18001d5a7  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d5ae  mov     rcx, [rcx+10h]
0x18001d5b2  call    WPP_SF_qS
0x18001d5b7  nop
0x18001d5b8  mov     rax, 0
0x18001d5c2  add     rsp, 40h
0x18001d5c6  pop     rbp
0x18001d5c7  retn
```
