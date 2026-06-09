# _DockCache::FoundDock_::_1_::catch$3

- ea: `0x18001d39b`
- end: `0x18001d3fb`
- name: `_DockCache::FoundDock_::_1_::catch$3`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d39b`

## pseudocode

```c
__int64 __fastcall DockCache::FoundDock_::_1_::catch_3(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d39b  mov     [rsp+arg_8], rdx
0x18001d3a0  push    rbp
0x18001d3a1  sub     rsp, 40h
0x18001d3a5  mov     rbp, rdx
0x18001d3a8  lea     rax, WPP_GLOBAL_Control
0x18001d3af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3b6  cmp     rcx, rax
0x18001d3b9  jz      short loc_18001D3EA
0x18001d3bb  cmp     byte ptr [rcx+19h], 1
0x18001d3bf  jb      short loc_18001D3EA
0x18001d3c1  test    byte ptr [rcx+1Ch], 1
0x18001d3c5  jz      short loc_18001D3EA
0x18001d3c7  mov     edx, 27h ; '''
0x18001d3cc  mov     rax, [rbp+50h]
0x18001d3d0  mov     [rsp+48h+var_28], rax
0x18001d3d5  mov     r9, [rbp+40h]
0x18001d3d9  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d3e0  mov     rcx, [rcx+10h]
0x18001d3e4  call    WPP_SF_qS
0x18001d3e9  nop
0x18001d3ea  mov     rax, 0
0x18001d3f4  add     rsp, 40h
0x18001d3f8  pop     rbp
0x18001d3f9  retn
```
