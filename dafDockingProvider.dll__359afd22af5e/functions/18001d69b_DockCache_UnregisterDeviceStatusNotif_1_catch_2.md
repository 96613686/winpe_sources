# _DockCache::UnregisterDeviceStatusNotif_::_1_::catch$2

- ea: `0x18001d69b`
- end: `0x18001d6f2`
- name: `_DockCache::UnregisterDeviceStatusNotif_::_1_::catch$2`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c308`
- `0x18001d69b`

## pseudocode

```c
__int64 __fastcall DockCache::UnregisterDeviceStatusNotif_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      *(_QWORD *)(a2 + 48));
  }
  return 0;
}

```

## disassembly

```asm
0x18001d69b  mov     [rsp+arg_8], rdx
0x18001d6a0  push    rbp
0x18001d6a1  sub     rsp, 20h
0x18001d6a5  mov     rbp, rdx
0x18001d6a8  lea     rax, WPP_GLOBAL_Control
0x18001d6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6b6  cmp     rcx, rax
0x18001d6b9  jz      short loc_18001D6E1
0x18001d6bb  cmp     byte ptr [rcx+19h], 1
0x18001d6bf  jb      short loc_18001D6E1
0x18001d6c1  test    byte ptr [rcx+1Ch], 1
0x18001d6c5  jz      short loc_18001D6E1
0x18001d6c7  mov     edx, 47h ; 'G'
0x18001d6cc  mov     r9, [rbp+30h]
0x18001d6d0  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001d6d7  mov     rcx, [rcx+10h]
0x18001d6db  call    WPP_SF_q
0x18001d6e0  nop
0x18001d6e1  mov     rax, 0
0x18001d6eb  add     rsp, 20h
0x18001d6ef  pop     rbp
0x18001d6f0  retn
```
