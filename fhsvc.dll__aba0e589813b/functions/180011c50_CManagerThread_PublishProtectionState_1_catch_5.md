# _CManagerThread::PublishProtectionState_::_1_::catch$5

- ea: `0x180011c50`
- end: `0x180011cb6`
- name: `_CManagerThread::PublishProtectionState_::_1_::catch$5`
- size: `102`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ca14`
- `0x180011c50`

## pseudocode

```c
__int64 __fastcall CManagerThread::PublishProtectionState_::_1_::catch_5(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 88);
  *(_DWORD *)(a2 + 72) = v2;
  if ( (int)v2 >= 0 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x180011c50  mov     [rsp+arg_8], rdx
0x180011c55  push    rbp
0x180011c56  sub     rsp, 40h
0x180011c5a  mov     rbp, rdx
0x180011c5d  mov     r9d, [rbp+58h]
0x180011c61  mov     [rbp+48h], r9d
0x180011c65  test    r9d, r9d
0x180011c68  jns     short loc_180011CA5
0x180011c6a  lea     rax, WPP_GLOBAL_Control
0x180011c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c78  cmp     rcx, rax
0x180011c7b  jz      short loc_180011C99
0x180011c7d  test    byte ptr [rcx+1Ch], 1
0x180011c81  jz      short loc_180011C99
0x180011c83  mov     edx, 85h
0x180011c88  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180011c8f  mov     rcx, [rcx+10h]
0x180011c93  call    WPP_SF_d
0x180011c98  nop
0x180011c99  mov     rax, 0
0x180011ca3  jmp     short loc_180011CAF
0x180011ca5  mov     rax, 1
0x180011caf  add     rsp, 40h
0x180011cb3  pop     rbp
0x180011cb4  retn
```
