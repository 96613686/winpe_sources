# _CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath_::_1_::catch$1

- ea: `0x18000ca69`
- end: `0x18000cac3`
- name: `_CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath_::_1_::catch$1`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c54`
- `0x18000ca69`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 120);
  *(_DWORD *)(a2 + 64) = v2;
  if ( (int)v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x18000ca69  mov     [rsp+arg_8], rdx
0x18000ca6e  push    rbp
0x18000ca6f  sub     rsp, 40h
0x18000ca73  mov     rbp, rdx
0x18000ca76  mov     r9d, [rbp+78h]
0x18000ca7a  mov     [rbp+40h], r9d
0x18000ca7e  test    r9d, r9d
0x18000ca81  jns     short loc_18000CAB2
0x18000ca83  lea     rax, WPP_GLOBAL_Control
0x18000ca8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca91  cmp     rcx, rax
0x18000ca94  jz      short loc_18000CAB2
0x18000ca96  test    byte ptr [rcx+1Ch], 2
0x18000ca9a  jz      short loc_18000CAB2
0x18000ca9c  mov     edx, 30h ; '0'
0x18000caa1  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x18000caa8  mov     rcx, [rcx+10h]
0x18000caac  call    WPP_SF_d
0x18000cab1  nop
0x18000cab2  mov     rax, 0
0x18000cabc  add     rsp, 40h
0x18000cac0  pop     rbp
0x18000cac1  retn
```
