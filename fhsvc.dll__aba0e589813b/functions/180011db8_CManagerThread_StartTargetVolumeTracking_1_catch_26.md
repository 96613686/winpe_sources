# _CManagerThread::StartTargetVolumeTracking_::_1_::catch$26

- ea: `0x180011db8`
- end: `0x180011e0c`
- name: `_CManagerThread::StartTargetVolumeTracking_::_1_::catch$26`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ca14`
- `0x180011db8`

## pseudocode

```c
__int64 __fastcall CManagerThread::StartTargetVolumeTracking_::_1_::catch_26(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      154,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      *(unsigned int *)(a2 + 128));
  return 0;
}

```

## disassembly

```asm
0x180011db8  mov     [rsp+arg_8], rdx
0x180011dbd  push    rbp
0x180011dbe  sub     rsp, 40h
0x180011dc2  mov     rbp, rdx
0x180011dc5  lea     rax, WPP_GLOBAL_Control
0x180011dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dd3  cmp     rcx, rax
0x180011dd6  jz      short loc_180011DFB
0x180011dd8  test    byte ptr [rcx+1Ch], 1
0x180011ddc  jz      short loc_180011DFB
0x180011dde  mov     edx, 9Ah
0x180011de3  mov     r9d, [rbp+80h]
0x180011dea  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180011df1  mov     rcx, [rcx+10h]
0x180011df5  call    WPP_SF_d
0x180011dfa  nop
0x180011dfb  mov     rax, 0
0x180011e05  add     rsp, 40h
0x180011e09  pop     rbp
0x180011e0a  retn
```
