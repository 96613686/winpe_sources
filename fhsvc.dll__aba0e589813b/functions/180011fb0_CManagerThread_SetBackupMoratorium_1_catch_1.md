# _CManagerThread::SetBackupMoratorium_::_1_::catch$1

- ea: `0x180011fb0`
- end: `0x180012011`
- name: `_CManagerThread::SetBackupMoratorium_::_1_::catch$1`
- size: `97`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ca14`
- `0x180011fb0`

## pseudocode

```c
__int64 __fastcall CManagerThread::SetBackupMoratorium_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = *(unsigned int *)(a2 + 32);
    if ( (int)v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x180011fb0  mov     [rsp+arg_8], rdx
0x180011fb5  push    rbp
0x180011fb6  sub     rsp, 20h
0x180011fba  mov     rbp, rdx
0x180011fbd  lea     rax, WPP_GLOBAL_Control
0x180011fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fcb  cmp     rcx, rax
0x180011fce  jz      short loc_180012000
0x180011fd0  test    byte ptr [rcx+1Ch], 1
0x180011fd4  jz      short loc_180012000
0x180011fd6  mov     r9d, [rbp+20h]
0x180011fda  test    r9d, r9d
0x180011fdd  jle     short loc_180011FEA
0x180011fdf  movzx   r9d, r9w
0x180011fe3  or      r9d, 80070000h
0x180011fea  mov     edx, 5Bh ; '['
0x180011fef  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180011ff6  mov     rcx, [rcx+10h]
0x180011ffa  call    WPP_SF_d
0x180011fff  nop
0x180012000  mov     rax, 0
0x18001200a  add     rsp, 20h
0x18001200e  pop     rbp
0x18001200f  retn
```
