# _DockCache::ConnectedDock_::_1_::catch$3

- ea: `0x18001d299`
- end: `0x18001d2f9`
- name: `_DockCache::ConnectedDock_::_1_::catch$3`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d299`

## pseudocode

```c
__int64 __fastcall DockCache::ConnectedDock_::_1_::catch_3(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d299  mov     [rsp+arg_8], rdx
0x18001d29e  push    rbp
0x18001d29f  sub     rsp, 40h
0x18001d2a3  mov     rbp, rdx
0x18001d2a6  lea     rax, WPP_GLOBAL_Control
0x18001d2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2b4  cmp     rcx, rax
0x18001d2b7  jz      short loc_18001D2E8
0x18001d2b9  cmp     byte ptr [rcx+19h], 1
0x18001d2bd  jb      short loc_18001D2E8
0x18001d2bf  test    byte ptr [rcx+1Ch], 1
0x18001d2c3  jz      short loc_18001D2E8
0x18001d2c5  mov     edx, 30h ; '0'
0x18001d2ca  mov     rax, [rbp+50h]
0x18001d2ce  mov     [rsp+48h+var_28], rax
0x18001d2d3  mov     r9, [rbp+40h]
0x18001d2d7  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d2de  mov     rcx, [rcx+10h]
0x18001d2e2  call    WPP_SF_qS
0x18001d2e7  nop
0x18001d2e8  mov     rax, 0
0x18001d2f2  add     rsp, 40h
0x18001d2f6  pop     rbp
0x18001d2f7  retn
```
