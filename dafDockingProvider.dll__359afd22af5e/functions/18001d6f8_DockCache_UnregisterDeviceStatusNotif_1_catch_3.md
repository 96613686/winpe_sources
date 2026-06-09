# _DockCache::UnregisterDeviceStatusNotif_::_1_::catch$3

- ea: `0x18001d6f8`
- end: `0x18001d74f`
- name: `_DockCache::UnregisterDeviceStatusNotif_::_1_::catch$3`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c308`
- `0x18001d6f8`

## pseudocode

```c
__int64 __fastcall DockCache::UnregisterDeviceStatusNotif_::_1_::catch_3(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 48));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d6f8  mov     [rsp+arg_8], rdx
0x18001d6fd  push    rbp
0x18001d6fe  sub     rsp, 20h
0x18001d702  mov     rbp, rdx
0x18001d705  lea     rax, WPP_GLOBAL_Control
0x18001d70c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d713  cmp     rcx, rax
0x18001d716  jz      short loc_18001D73E
0x18001d718  cmp     byte ptr [rcx+19h], 1
0x18001d71c  jb      short loc_18001D73E
0x18001d71e  test    byte ptr [rcx+1Ch], 1
0x18001d722  jz      short loc_18001D73E
0x18001d724  mov     edx, 46h ; 'F'
0x18001d729  mov     r9, [rbp+30h]
0x18001d72d  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d734  mov     rcx, [rcx+10h]
0x18001d738  call    WPP_SF_q
0x18001d73d  nop
0x18001d73e  mov     rax, 0
0x18001d748  add     rsp, 20h
0x18001d74c  pop     rbp
0x18001d74d  retn
```
