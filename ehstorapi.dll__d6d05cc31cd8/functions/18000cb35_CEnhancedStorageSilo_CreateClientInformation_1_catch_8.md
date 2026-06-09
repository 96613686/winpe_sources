# _CEnhancedStorageSilo::CreateClientInformation_::_1_::catch$8

- ea: `0x18000cb35`
- end: `0x18000cb8a`
- name: `_CEnhancedStorageSilo::CreateClientInformation_::_1_::catch$8`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c54`
- `0x18000cb35`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::CreateClientInformation_::_1_::catch_8(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 72);
  *(_DWORD *)(a2 + 48) = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x18000cb35  mov     [rsp+arg_8], rdx
0x18000cb3a  push    rbp
0x18000cb3b  sub     rsp, 30h
0x18000cb3f  mov     rbp, rdx
0x18000cb42  mov     r9d, [rbp+48h]
0x18000cb46  mov     [rbp+30h], r9d
0x18000cb4a  lea     rax, WPP_GLOBAL_Control
0x18000cb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb58  cmp     rcx, rax
0x18000cb5b  jz      short loc_18000CB79
0x18000cb5d  test    byte ptr [rcx+1Ch], 4
0x18000cb61  jz      short loc_18000CB79
0x18000cb63  mov     edx, 3Eh ; '>'
0x18000cb68  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x18000cb6f  mov     rcx, [rcx+10h]
0x18000cb73  call    WPP_SF_d
0x18000cb78  nop
0x18000cb79  mov     rax, 0
0x18000cb83  add     rsp, 30h
0x18000cb87  pop     rbp
0x18000cb88  retn
```
