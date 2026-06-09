# _DockCache::FoundDock_::_1_::catch$2

- ea: `0x18001d335`
- end: `0x18001d395`
- name: `_DockCache::FoundDock_::_1_::catch$2`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d335`

## pseudocode

```c
__int64 __fastcall DockCache::FoundDock_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d335  mov     [rsp+arg_8], rdx
0x18001d33a  push    rbp
0x18001d33b  sub     rsp, 40h
0x18001d33f  mov     rbp, rdx
0x18001d342  lea     rax, WPP_GLOBAL_Control
0x18001d349  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d350  cmp     rcx, rax
0x18001d353  jz      short loc_18001D384
0x18001d355  cmp     byte ptr [rcx+19h], 1
0x18001d359  jb      short loc_18001D384
0x18001d35b  test    byte ptr [rcx+1Ch], 1
0x18001d35f  jz      short loc_18001D384
0x18001d361  mov     edx, 26h ; '&'
0x18001d366  mov     rax, [rbp+50h]
0x18001d36a  mov     [rsp+48h+var_28], rax
0x18001d36f  mov     r9, [rbp+40h]
0x18001d373  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d37a  mov     rcx, [rcx+10h]
0x18001d37e  call    WPP_SF_qS
0x18001d383  nop
0x18001d384  mov     rax, 0
0x18001d38e  add     rsp, 40h
0x18001d392  pop     rbp
0x18001d393  retn
```
