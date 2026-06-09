# MSMPortDestroyCompletion

- ea: `0x180018c60`
- end: `0x180018d5a`
- name: `MSMPortDestroyCompletion`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180023640`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180018c60`
- `0x1800214f0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall MSMPortDestroyCompletion(__int64 a1)
{
  unsigned int v1; // ebp
  __int64 v3; // rdi
  __int64 v4; // rsi
  _QWORD *v5; // rcx
  __int64 result; // rax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx

  v1 = *(_DWORD *)(a1 + 20);
  v3 = *(_QWORD *)(a1 + 192);
  v4 = *(_QWORD *)(a1 + 2368);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 91, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 4) != 0 )
      WPP_SF_d(v5[7], 92, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v1);
  }
  result = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 2296))(v3, v4);
  v7 = result;
  if ( !(_DWORD)result )
    goto LABEL_11;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v1, result);
LABEL_11:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
    WPP_SF_D(v8[7], 94, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180018c60  push    rbx
0x180018c62  push    rbp
0x180018c63  push    rsi
0x180018c64  push    rdi
0x180018c65  push    r14
0x180018c67  sub     rsp, 30h
0x180018c6b  mov     ebp, [rcx+14h]
0x180018c6e  mov     rbx, rcx
0x180018c71  mov     rdi, [rcx+0C0h]
0x180018c78  mov     rsi, [rcx+940h]
0x180018c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c86  lea     r14, WPP_GLOBAL_Control
0x180018c8d  cmp     rcx, r14
0x180018c90  jz      short loc_180018CDA
0x180018c92  test    dword ptr [rcx+44h], 800h
0x180018c99  jz      short loc_180018CB7
0x180018c9b  mov     rcx, [rcx+38h]
0x180018c9f  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180018ca6  mov     edx, 5Bh ; '['
0x180018cab  call    WPP_SF_
0x180018cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cb7  cmp     rcx, r14
0x180018cba  jz      short loc_180018CDA
0x180018cbc  test    byte ptr [rcx+44h], 4
0x180018cc0  jz      short loc_180018CDA
0x180018cc2  mov     rcx, [rcx+38h]
0x180018cc6  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180018ccd  mov     edx, 5Ch ; '\'
0x180018cd2  mov     r9d, ebp
0x180018cd5  call    WPP_SF_d
0x180018cda  mov     rax, [rbx+8F8h]
0x180018ce1  mov     rdx, rsi
0x180018ce4  mov     rcx, rdi
0x180018ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cec  mov     ebx, eax
0x180018cee  test    eax, eax
0x180018cf0  jz      short loc_180018D20
0x180018cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cf9  cmp     rcx, r14
0x180018cfc  jz      short loc_180018D4F
0x180018cfe  test    byte ptr [rcx+44h], 1
0x180018d02  jz      short loc_180018D27
0x180018d04  mov     rcx, [rcx+38h]
0x180018d08  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180018d0f  mov     edx, 5Dh ; ']'
0x180018d14  mov     [rsp+58h+var_38], eax
0x180018d18  mov     r9d, ebp
0x180018d1b  call    WPP_SF_dd
0x180018d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d27  cmp     rcx, r14
0x180018d2a  jz      short loc_180018D4D
0x180018d2c  test    dword ptr [rcx+44h], 800h
0x180018d33  jz      short loc_180018D4D
0x180018d35  mov     rcx, [rcx+38h]
0x180018d39  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180018d40  mov     edx, 5Eh ; '^'
0x180018d45  mov     r9d, ebx
0x180018d48  call    WPP_SF_D
0x180018d4d  mov     eax, ebx
0x180018d4f  add     rsp, 30h
0x180018d53  pop     r14
0x180018d55  pop     rdi
0x180018d56  pop     rsi
0x180018d57  pop     rbp
0x180018d58  pop     rbx
0x180018d59  retn
```
