# _CManagerThread::GetConfigDescriptor_::_1_::catch$3

- ea: `0x180011ea3`
- end: `0x180011f09`
- name: `_CManagerThread::GetConfigDescriptor_::_1_::catch$3`
- size: `102`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000ca14`
- `0x180011ea3`

## pseudocode

```c
__int64 __fastcall CManagerThread::GetConfigDescriptor_::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v2; // r9

  v2 = *(unsigned int *)(a2 + 32);
  *(_DWORD *)(a2 + 96) = v2;
  if ( (int)v2 >= 0 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x180011ea3  mov     [rsp+arg_8], rdx
0x180011ea8  push    rbp
0x180011ea9  sub     rsp, 20h
0x180011ead  mov     rbp, rdx
0x180011eb0  mov     r9d, [rbp+20h]
0x180011eb4  mov     [rbp+60h], r9d
0x180011eb8  test    r9d, r9d
0x180011ebb  jns     short loc_180011EF8
0x180011ebd  lea     rax, WPP_GLOBAL_Control
0x180011ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ecb  cmp     rcx, rax
0x180011ece  jz      short loc_180011EEC
0x180011ed0  test    byte ptr [rcx+1Ch], 1
0x180011ed4  jz      short loc_180011EEC
0x180011ed6  mov     edx, 2Bh ; '+'
0x180011edb  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180011ee2  mov     rcx, [rcx+10h]
0x180011ee6  call    WPP_SF_d
0x180011eeb  nop
0x180011eec  mov     rax, 0
0x180011ef6  jmp     short loc_180011F02
0x180011ef8  mov     rax, 1
0x180011f02  add     rsp, 20h
0x180011f06  pop     rbp
0x180011f07  retn
```
