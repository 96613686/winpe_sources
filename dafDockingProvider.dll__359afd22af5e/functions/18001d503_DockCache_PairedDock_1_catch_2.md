# _DockCache::PairedDock_::_1_::catch$2

- ea: `0x18001d503`
- end: `0x18001d563`
- name: `_DockCache::PairedDock_::_1_::catch$2`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d503`

## pseudocode

```c
__int64 __fastcall DockCache::PairedDock_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d503  mov     [rsp+arg_8], rdx
0x18001d508  push    rbp
0x18001d509  sub     rsp, 40h
0x18001d50d  mov     rbp, rdx
0x18001d510  lea     rax, WPP_GLOBAL_Control
0x18001d517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d51e  cmp     rcx, rax
0x18001d521  jz      short loc_18001D552
0x18001d523  cmp     byte ptr [rcx+19h], 1
0x18001d527  jb      short loc_18001D552
0x18001d529  test    byte ptr [rcx+1Ch], 1
0x18001d52d  jz      short loc_18001D552
0x18001d52f  mov     edx, 2Ah ; '*'
0x18001d534  mov     rax, [rbp+50h]
0x18001d538  mov     [rsp+48h+var_28], rax
0x18001d53d  mov     r9, [rbp+40h]
0x18001d541  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d548  mov     rcx, [rcx+10h]
0x18001d54c  call    WPP_SF_qS
0x18001d551  nop
0x18001d552  mov     rax, 0
0x18001d55c  add     rsp, 40h
0x18001d560  pop     rbp
0x18001d561  retn
```
