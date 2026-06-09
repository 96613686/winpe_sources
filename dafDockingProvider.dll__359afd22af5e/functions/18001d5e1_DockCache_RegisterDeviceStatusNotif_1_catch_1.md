# _DockCache::RegisterDeviceStatusNotif_::_1_::catch$1

- ea: `0x18001d5e1`
- end: `0x18001d638`
- name: `_DockCache::RegisterDeviceStatusNotif_::_1_::catch$1`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c308`
- `0x18001d5e1`

## pseudocode

```c
__int64 __fastcall DockCache::RegisterDeviceStatusNotif_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 64));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d5e1  mov     [rsp+arg_8], rdx
0x18001d5e6  push    rbp
0x18001d5e7  sub     rsp, 20h
0x18001d5eb  mov     rbp, rdx
0x18001d5ee  lea     rax, WPP_GLOBAL_Control
0x18001d5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5fc  cmp     rcx, rax
0x18001d5ff  jz      short loc_18001D627
0x18001d601  cmp     byte ptr [rcx+19h], 1
0x18001d605  jb      short loc_18001D627
0x18001d607  test    byte ptr [rcx+1Ch], 1
0x18001d60b  jz      short loc_18001D627
0x18001d60d  mov     edx, 43h ; 'C'
0x18001d612  mov     r9, [rbp+40h]
0x18001d616  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d61d  mov     rcx, [rcx+10h]
0x18001d621  call    WPP_SF_q
0x18001d626  nop
0x18001d627  mov     rax, 0
0x18001d631  add     rsp, 20h
0x18001d635  pop     rbp
0x18001d636  retn
```
