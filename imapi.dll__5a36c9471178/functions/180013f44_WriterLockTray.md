# WriterLockTray

- ea: `0x180013f44`
- end: `0x1800140a3`
- name: `WriterLockTray`
- size: `351`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d830`
- `0x18000ed70`
- `0x18000ee40`

## callees

- `0x180007d40`
- `0x180007d80`
- `0x180012408`
- `0x180012cd4`
- `0x180013f44`
- `0x180018500`

## pseudocode

```c
__int64 __fastcall WriterLockTray(__int64 a1, char a2, __int64 a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // rcx
  const char *v7; // r9
  int v8; // ebx
  __int64 v9; // r8
  const char *v10; // r9
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF

  v12 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
    {
      v6 = v5[7];
      v7 = byte_18001C1CB;
      if ( !a2 )
        v7 = "Un";
      WPP_SF_s(v6, 60, a3, v7);
      v5 = WPP_GLOBAL_Control;
    }
    v8 = -2147024809;
    goto LABEL_18;
  }
  v12 = 0;
  LOBYTE(v12) = 30;
  BYTE4(v12) = a2 != 0;
  v8 = PrvSptExecCdbImmediateWithTUR(a1, &v12);
  if ( v8 >= 0 )
    goto LABEL_17;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v10 = byte_18001C1CB;
    if ( !a2 )
      v10 = "Un";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 61, v9, v10);
LABEL_17:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_18:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
    WPP_SF_qD(v5[7], 62, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013f44  mov     [rsp+arg_8], rbx
0x180013f49  mov     [rsp+arg_10], rbp
0x180013f4e  push    rsi
0x180013f4f  push    rdi
0x180013f50  push    r14
0x180013f52  sub     rsp, 50h
0x180013f56  mov     rax, cs:__security_cookie
0x180013f5d  xor     rax, rsp
0x180013f60  mov     [rsp+68h+var_28], rax
0x180013f65  xorps   xmm0, xmm0
0x180013f68  mov     sil, dl
0x180013f6b  movups  [rsp+68h+var_38], xmm0
0x180013f70  mov     rdi, rcx
0x180013f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f7a  lea     r14, WPP_GLOBAL_Control
0x180013f81  mov     ebp, 1
0x180013f86  cmp     rcx, r14
0x180013f89  jz      short loc_180013FAE
0x180013f8b  test    [rcx+44h], bpl
0x180013f8f  jz      short loc_180013FAE
0x180013f91  mov     rcx, [rcx+38h]
0x180013f95  lea     edx, [rbp+3Ah]
0x180013f98  mov     r9, rdi
0x180013f9b  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013fa2  call    WPP_SF_q
0x180013fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fae  test    rdi, rdi
0x180013fb1  jnz     short loc_180013FED
0x180013fb3  cmp     rcx, r14
0x180013fb6  jz      short loc_180013FE6
0x180013fb8  test    [rcx+44h], bpl
0x180013fbc  jz      short loc_180013FE6
0x180013fbe  mov     rcx, [rcx+38h]
0x180013fc2  lea     rax, aUn; "Un"
0x180013fc9  test    sil, sil
0x180013fcc  lea     r9, byte_18001C1CB
0x180013fd3  lea     edx, [rdi+3Ch]
0x180013fd6  cmovz   r9, rax
0x180013fda  call    WPP_SF_s
0x180013fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fe6  mov     ebx, 80070057h
0x180013feb  jmp     short loc_180014058
0x180013fed  xorps   xmm0, xmm0
0x180013ff0  lea     rdx, [rsp+68h+var_38]
0x180013ff5  movups  [rsp+68h+var_38], xmm0
0x180013ffa  movzx   eax, byte ptr [rsp+68h+var_38+4]
0x180013fff  test    sil, sil
0x180014002  mov     rcx, rdi
0x180014005  mov     byte ptr [rsp+68h+var_38], 1Eh
0x18001400a  cmovnz  eax, ebp
0x18001400d  mov     byte ptr [rsp+68h+var_38+4], al
0x180014011  call    PrvSptExecCdbImmediateWithTUR
0x180014016  mov     ebx, eax
0x180014018  test    eax, eax
0x18001401a  jns     short loc_180014051
0x18001401c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014023  cmp     rcx, r14
0x180014026  jz      short loc_18001407F
0x180014028  test    [rcx+44h], bpl
0x18001402c  jz      short loc_180014058
0x18001402e  mov     rcx, [rcx+38h]
0x180014032  lea     rax, aUn; "Un"
0x180014039  test    sil, sil
0x18001403c  lea     r9, byte_18001C1CB
0x180014043  mov     edx, 3Dh ; '='
0x180014048  cmovz   r9, rax
0x18001404c  call    WPP_SF_s
0x180014051  mov     rcx, cs:WPP_GLOBAL_Control
0x180014058  cmp     rcx, r14
0x18001405b  jz      short loc_18001407F
0x18001405d  test    [rcx+44h], bpl
0x180014061  jz      short loc_18001407F
0x180014063  mov     rcx, [rcx+38h]
0x180014067  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001406e  mov     edx, 3Eh ; '>'
0x180014073  mov     [rsp+68h+var_48], ebx
0x180014077  mov     r9, rdi
0x18001407a  call    WPP_SF_qD
0x18001407f  mov     eax, ebx
0x180014081  mov     rcx, [rsp+68h+var_28]
0x180014086  xor     rcx, rsp; StackCookie
0x180014089  call    __security_check_cookie
0x18001408e  lea     r11, [rsp+68h+var_18]
0x180014093  mov     rbx, [r11+28h]
0x180014097  mov     rbp, [r11+30h]
0x18001409b  mov     rsp, r11
0x18001409e  pop     r14
0x1800140a0  pop     rdi
0x1800140a1  pop     rsi
0x1800140a2  retn
```
