# _DockCache::LivenessUnknown_::_1_::catch$3

- ea: `0x18001d48b`
- end: `0x18001d4eb`
- name: `_DockCache::LivenessUnknown_::_1_::catch$3`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb40`
- `0x18001d48b`

## pseudocode

```c
__int64 __fastcall DockCache::LivenessUnknown_::_1_::catch_3(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64),
      *(_QWORD *)(a2 + 80));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d48b  mov     [rsp+arg_8], rdx
0x18001d490  push    rbp
0x18001d491  sub     rsp, 40h
0x18001d495  mov     rbp, rdx
0x18001d498  lea     rax, WPP_GLOBAL_Control
0x18001d49f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4a6  cmp     rcx, rax
0x18001d4a9  jz      short loc_18001D4DA
0x18001d4ab  cmp     byte ptr [rcx+19h], 1
0x18001d4af  jb      short loc_18001D4DA
0x18001d4b1  test    byte ptr [rcx+1Ch], 1
0x18001d4b5  jz      short loc_18001D4DA
0x18001d4b7  mov     edx, 37h ; '7'
0x18001d4bc  mov     rax, [rbp+50h]
0x18001d4c0  mov     [rsp+48h+var_28], rax
0x18001d4c5  mov     r9, [rbp+40h]
0x18001d4c9  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d4d0  mov     rcx, [rcx+10h]
0x18001d4d4  call    WPP_SF_qS
0x18001d4d9  nop
0x18001d4da  mov     rax, 0
0x18001d4e4  add     rsp, 40h
0x18001d4e8  pop     rbp
0x18001d4e9  retn
```
