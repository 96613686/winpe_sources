# _CWorkerThread::Create_::_1_::catch$58

- ea: `0x180011ba0`
- end: `0x180011c09`
- name: `_CWorkerThread::Create_::_1_::catch$58`
- size: `105`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ca14`
- `0x180011ba0`

## pseudocode

```c
__int64 __fastcall CWorkerThread::Create_::_1_::catch_58(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 128);
  *(_DWORD *)(a2 + 104) = v2;
  if ( (int)v2 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x180011ba0  mov     [rsp+arg_8], rdx
0x180011ba5  push    rbp
0x180011ba6  sub     rsp, 40h
0x180011baa  mov     rbp, rdx
0x180011bad  mov     r9d, [rbp+80h]
0x180011bb4  mov     [rbp+68h], r9d
0x180011bb8  test    r9d, r9d
0x180011bbb  jns     short loc_180011BF8
0x180011bbd  lea     rax, WPP_GLOBAL_Control
0x180011bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bcb  cmp     rcx, rax
0x180011bce  jz      short loc_180011BEC
0x180011bd0  test    byte ptr [rcx+1Ch], 1
0x180011bd4  jz      short loc_180011BEC
0x180011bd6  mov     edx, 26h ; '&'
0x180011bdb  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180011be2  mov     rcx, [rcx+10h]
0x180011be6  call    WPP_SF_d
0x180011beb  nop
0x180011bec  mov     rax, 0
0x180011bf6  jmp     short loc_180011C02
0x180011bf8  mov     rax, 0
0x180011c02  add     rsp, 40h
0x180011c06  pop     rbp
0x180011c07  retn
```
