# MSMDeleteOneXUserProfile

- ea: `0x1800280d0`
- end: `0x1800281d5`
- name: `MSMDeleteOneXUserProfile`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a318`
- `0x180025dbc`

## callees

- `0x180004f40`
- `0x180005440`
- `0x180007f60`
- `0x18001d838`
- `0x18001e4e8`
- `0x1800214f0`
- `0x1800280d0`

## pseudocode

```c
__int64 __fastcall MSMDeleteOneXUserProfile(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  char *v5; // rcx
  int v6; // eax
  _QWORD *v7; // rcx

  v2 = *(_DWORD *)(a1 + 20);
  v5 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v5 = (char *)WPP_GLOBAL_Control;
    }
    if ( v5 != (char *)&WPP_GLOBAL_Control && v5[68] < 0 )
      WPP_SF_dq(*((_QWORD *)v5 + 7), 67, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v2, a2);
  }
  if ( (byte_18003DF41 & 4) != 0 )
    McTemplateU0q_EtwEventWriteTransfer((__int64)v5, (__int64)Delete1XUserProfile, v2);
  v6 = MSMSetOneXUserProfile(a1, a2, 0, 0);
  if ( !v6 )
    goto LABEL_13;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v2, v6);
LABEL_13:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_D(v7[7], 69, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800280d0  push    rbx
0x1800280d2  push    rbp
0x1800280d3  push    rsi
0x1800280d4  push    rdi
0x1800280d5  sub     rsp, 38h
0x1800280d9  mov     ebx, [rcx+14h]
0x1800280dc  mov     rdi, rdx
0x1800280df  mov     rsi, rcx
0x1800280e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280e9  lea     rbp, WPP_GLOBAL_Control
0x1800280f0  cmp     rcx, rbp
0x1800280f3  jz      short loc_180028142
0x1800280f5  test    dword ptr [rcx+44h], 800h
0x1800280fc  jz      short loc_18002811A
0x1800280fe  mov     rcx, [rcx+38h]
0x180028102  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028109  mov     edx, 42h ; 'B'
0x18002810e  call    WPP_SF_
0x180028113  mov     rcx, cs:WPP_GLOBAL_Control
0x18002811a  cmp     rcx, rbp
0x18002811d  jz      short loc_180028142
0x18002811f  test    byte ptr [rcx+44h], 80h
0x180028123  jz      short loc_180028142
0x180028125  mov     rcx, [rcx+38h]
0x180028129  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028130  mov     edx, 43h ; 'C'
0x180028135  mov     [rsp+58h+var_38], rdi
0x18002813a  mov     r9d, ebx
0x18002813d  call    WPP_SF_dq
0x180028142  test    cs:byte_18003DF41, 4
0x180028149  jz      short loc_18002815A
0x18002814b  mov     r8d, ebx
0x18002814e  lea     rdx, Delete1XUserProfile
0x180028155  call    McTemplateU0q_EtwEventWriteTransfer
0x18002815a  xor     r9d, r9d
0x18002815d  xor     r8d, r8d
0x180028160  mov     rdx, rdi
0x180028163  mov     rcx, rsi
0x180028166  call    MSMSetOneXUserProfile
0x18002816b  test    eax, eax
0x18002816d  jz      short loc_18002819D
0x18002816f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028176  cmp     rcx, rbp
0x180028179  jz      short loc_1800281CA
0x18002817b  test    byte ptr [rcx+44h], 1
0x18002817f  jz      short loc_1800281A4
0x180028181  mov     rcx, [rcx+38h]
0x180028185  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18002818c  mov     edx, 44h ; 'D'
0x180028191  mov     dword ptr [rsp+58h+var_38], eax
0x180028195  mov     r9d, ebx
0x180028198  call    WPP_SF_dd
0x18002819d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281a4  cmp     rcx, rbp
0x1800281a7  jz      short loc_1800281CA
0x1800281a9  test    dword ptr [rcx+44h], 800h
0x1800281b0  jz      short loc_1800281CA
0x1800281b2  mov     rcx, [rcx+38h]
0x1800281b6  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800281bd  mov     edx, 45h ; 'E'
0x1800281c2  xor     r9d, r9d
0x1800281c5  call    WPP_SF_D
0x1800281ca  xor     eax, eax
0x1800281cc  add     rsp, 38h
0x1800281d0  pop     rdi
0x1800281d1  pop     rsi
0x1800281d2  pop     rbp
0x1800281d3  pop     rbx
0x1800281d4  retn
```
