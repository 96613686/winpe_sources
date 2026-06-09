# _AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$7

- ea: `0x140011ad0`
- end: `0x140011b07`
- name: `_AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor$7`
- size: `55`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140011ad0`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011afb`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140011afb`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::UpdateGlobalFeatureLevelInfo_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 144) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 144) &= ~1u;
    return std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(a2 + 424);
  }
  return result;
}

```

## disassembly

```asm
0x140011ad0  push    rbp
0x140011ad2  sub     rsp, 20h
0x140011ad6  mov     rbp, rdx
0x140011ad9  mov     eax, [rbp+90h]
0x140011adf  and     eax, 1
0x140011ae2  test    eax, eax
0x140011ae4  jz      short loc_140011B01
0x140011ae6  and     dword ptr [rbp+90h], 0FFFFFFFEh
0x140011aed  lea     rcx, [rbp+110h]
0x140011af4  add     rcx, 98h
0x140011afb  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x140011b01  add     rsp, 20h
0x140011b05  pop     rbp
0x140011b06  retn
```
