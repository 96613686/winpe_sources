# _CManagerThread::StartTargetVolumeTracking_::_1_::catch$27

- ea: `0x180011e12`
- end: `0x180011e66`
- name: `_CManagerThread::StartTargetVolumeTracking_::_1_::catch$27`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ca14`
- `0x180011e12`

## pseudocode

```c
__int64 __fastcall CManagerThread::StartTargetVolumeTracking_::_1_::catch_27(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      149,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      *(unsigned int *)(a2 + 132));
  return 0;
}

```

## disassembly

```asm
0x180011e12  mov     [rsp+arg_8], rdx
0x180011e17  push    rbp
0x180011e18  sub     rsp, 40h
0x180011e1c  mov     rbp, rdx
0x180011e1f  lea     rax, WPP_GLOBAL_Control
0x180011e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e2d  cmp     rcx, rax
0x180011e30  jz      short loc_180011E55
0x180011e32  test    byte ptr [rcx+1Ch], 1
0x180011e36  jz      short loc_180011E55
0x180011e38  mov     edx, 95h
0x180011e3d  mov     r9d, [rbp+84h]
0x180011e44  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180011e4b  mov     rcx, [rcx+10h]
0x180011e4f  call    WPP_SF_d
0x180011e54  nop
0x180011e55  mov     rax, 0
0x180011e5f  add     rsp, 40h
0x180011e63  pop     rbp
0x180011e64  retn
```
