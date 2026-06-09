# WriterSetProperty

- ea: `0x180014c50`
- end: `0x180014d57`
- name: `WriterSetProperty`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010170`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180007d40`
- `0x180007d80`
- `0x180014c50`

## pseudocode

```c
__int64 __fastcall WriterSetProperty(__int64 a1, unsigned int a2, unsigned int a3)
{
  _BYTE *v6; // rcx
  unsigned int v7; // ebx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 105, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v7 = 0;
    switch ( a2 )
    {
      case 1u:
        if ( (*(_BYTE *)(a1 + 16) & 2) != 0 && a3 > *(_DWORD *)(a1 + 24) )
          a3 = *(_DWORD *)(a1 + 24);
        *(_DWORD *)(a1 + 20) = a3;
        break;
      case 3u:
        *(_DWORD *)(a1 + 28) = a3;
        break;
      case 5u:
        *(_DWORD *)(a1 + 36) = a3;
        break;
      default:
        if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[68] & 1) == 0 )
          goto LABEL_9;
        WPP_SF_d(*((_QWORD *)v6 + 7), 108, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a2);
        goto LABEL_8;
    }
    v6 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[68] & 1) == 0 )
    goto LABEL_9;
  WPP_SF_(*((_QWORD *)v6 + 7), 106, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
LABEL_8:
  v6 = WPP_GLOBAL_Control;
LABEL_9:
  v7 = -2147024809;
LABEL_23:
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v6[68] & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)v6 + 7), 109, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v7);
  return v7;
}

```

## disassembly

```asm
0x180014c50  push    rbx
0x180014c52  push    rbp
0x180014c53  push    rsi
0x180014c54  push    rdi
0x180014c55  push    r15
0x180014c57  sub     rsp, 30h
0x180014c5b  mov     edi, r8d
0x180014c5e  mov     ebp, edx
0x180014c60  mov     rsi, rcx
0x180014c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c6a  lea     r15, WPP_GLOBAL_Control
0x180014c71  cmp     rcx, r15
0x180014c74  jz      short loc_180014C9B
0x180014c76  test    byte ptr [rcx+44h], 1
0x180014c7a  jz      short loc_180014C9B
0x180014c7c  mov     rcx, [rcx+38h]
0x180014c80  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014c87  mov     edx, 69h ; 'i'
0x180014c8c  mov     r9, rsi
0x180014c8f  call    WPP_SF_q
0x180014c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c9b  test    rsi, rsi
0x180014c9e  jnz     short loc_180014CCC
0x180014ca0  cmp     rcx, r15
0x180014ca3  jz      short loc_180014CC5
0x180014ca5  test    byte ptr [rcx+44h], 1
0x180014ca9  jz      short loc_180014CC5
0x180014cab  mov     rcx, [rcx+38h]
0x180014caf  lea     edx, [rsi+6Ah]
0x180014cb2  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014cb9  call    WPP_SF_
0x180014cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cc5  mov     ebx, 80070057h
0x180014cca  jmp     short loc_180014D23
0x180014ccc  xor     ebx, ebx
0x180014cce  mov     eax, ebp
0x180014cd0  sub     eax, 1
0x180014cd3  jz      short loc_180014D0C
0x180014cd5  sub     eax, 2
0x180014cd8  jz      short loc_180014D07
0x180014cda  cmp     eax, 2
0x180014cdd  jz      short loc_180014D02
0x180014cdf  cmp     rcx, r15
0x180014ce2  jz      short loc_180014CC5
0x180014ce4  test    byte ptr [rcx+44h], 1
0x180014ce8  jz      short loc_180014CC5
0x180014cea  mov     rcx, [rcx+38h]
0x180014cee  lea     edx, [rbx+6Ch]
0x180014cf1  mov     r9d, ebp
0x180014cf4  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014cfb  call    WPP_SF_d
0x180014d00  jmp     short loc_180014CBE
0x180014d02  mov     [rsi+24h], edi
0x180014d05  jmp     short loc_180014D1C
0x180014d07  mov     [rsi+1Ch], edi
0x180014d0a  jmp     short loc_180014D1C
0x180014d0c  test    byte ptr [rsi+10h], 2
0x180014d10  jz      short loc_180014D19
0x180014d12  cmp     edi, [rsi+18h]
0x180014d15  cmova   edi, [rsi+18h]
0x180014d19  mov     [rsi+14h], edi
0x180014d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d23  cmp     rcx, r15
0x180014d26  jz      short loc_180014D4A
0x180014d28  test    byte ptr [rcx+44h], 1
0x180014d2c  jz      short loc_180014D4A
0x180014d2e  mov     rcx, [rcx+38h]
0x180014d32  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014d39  mov     edx, 6Dh ; 'm'
0x180014d3e  mov     [rsp+58h+var_38], ebx
0x180014d42  mov     r9, rsi
0x180014d45  call    WPP_SF_qD
0x180014d4a  mov     eax, ebx
0x180014d4c  add     rsp, 30h
0x180014d50  pop     r15
0x180014d52  pop     rdi
0x180014d53  pop     rsi
0x180014d54  pop     rbp
0x180014d55  pop     rbx
0x180014d56  retn
```
