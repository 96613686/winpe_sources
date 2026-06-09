# _DockCache::ConnectedDock_::_1_::catch$2

- ea: `0x18001d233`
- end: `0x18001d293`
- name: `_DockCache::ConnectedDock_::_1_::catch$2`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d233`

## pseudocode

```c
__int64 __fastcall DockCache::ConnectedDock_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d233  mov     [rsp+arg_8], rdx
0x18001d238  push    rbp
0x18001d239  sub     rsp, 40h
0x18001d23d  mov     rbp, rdx
0x18001d240  lea     rax, WPP_GLOBAL_Control
0x18001d247  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d24e  cmp     rcx, rax
0x18001d251  jz      short loc_18001D282
0x18001d253  cmp     byte ptr [rcx+19h], 1
0x18001d257  jb      short loc_18001D282
0x18001d259  test    byte ptr [rcx+1Ch], 1
0x18001d25d  jz      short loc_18001D282
0x18001d25f  mov     edx, 2Fh ; '/'
0x18001d264  mov     rax, [rbp+50h]
0x18001d268  mov     [rsp+48h+var_28], rax
0x18001d26d  mov     r9, [rbp+40h]
0x18001d271  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d278  mov     rcx, [rcx+10h]
0x18001d27c  call    WPP_SF_qS
0x18001d281  nop
0x18001d282  mov     rax, 0
0x18001d28c  add     rsp, 40h
0x18001d290  pop     rbp
0x18001d291  retn
```
