# _DockCache::RegisterDeviceStatusNotif_::_1_::catch$2

- ea: `0x18001d63e`
- end: `0x18001d695`
- name: `_DockCache::RegisterDeviceStatusNotif_::_1_::catch$2`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c308`
- `0x18001d63e`

## pseudocode

```c
__int64 __fastcall DockCache::RegisterDeviceStatusNotif_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d63e  mov     [rsp+arg_8], rdx
0x18001d643  push    rbp
0x18001d644  sub     rsp, 20h
0x18001d648  mov     rbp, rdx
0x18001d64b  lea     rax, WPP_GLOBAL_Control
0x18001d652  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d659  cmp     rcx, rax
0x18001d65c  jz      short loc_18001D684
0x18001d65e  cmp     byte ptr [rcx+19h], 1
0x18001d662  jb      short loc_18001D684
0x18001d664  test    byte ptr [rcx+1Ch], 1
0x18001d668  jz      short loc_18001D684
0x18001d66a  mov     edx, 44h ; 'D'
0x18001d66f  mov     r9, [rbp+40h]
0x18001d673  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d67a  mov     rcx, [rcx+10h]
0x18001d67e  call    WPP_SF_q
0x18001d683  nop
0x18001d684  mov     rax, 0
0x18001d68e  add     rsp, 20h
0x18001d692  pop     rbp
0x18001d693  retn
```
