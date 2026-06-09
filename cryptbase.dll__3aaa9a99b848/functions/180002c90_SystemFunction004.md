# SystemFunction004

- ea: `0x180002c90`
- end: `0x180002e09`
- name: `SystemFunction004`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001980`
- `0x180002350`
- `0x180002aa8`
- `0x180002bdc`
- `0x180002c90`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall SystemFunction004(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v4; // edi
  __int64 v6; // r14
  int v7; // r11d
  unsigned int v8; // r11d
  __int64 result; // rax
  unsigned int v10; // ebx
  __int64 v11; // r10
  int v12; // r11d
  __int64 v13; // r14
  _DWORD v14[2]; // [rsp+20h] [rbp-60h] BYREF
  _BYTE *v15; // [rsp+28h] [rbp-58h]
  _BYTE *v16; // [rsp+30h] [rbp-50h]
  _DWORD v17[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+40h] [rbp-40h]
  __int64 v19; // [rsp+48h] [rbp-38h]
  _DWORD v20[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-20h]
  int v23; // [rsp+68h] [rbp-18h] BYREF
  __int16 v24; // [rsp+6Ch] [rbp-14h]
  char v25; // [rsp+6Eh] [rbp-12h]
  _DWORD v26[2]; // [rsp+70h] [rbp-10h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_DWORD *)a1;
  v6 = *(_QWORD *)(a3 + 8);
  v7 = *(_DWORD *)(a3 + 4);
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v20[1] = *(_DWORD *)(a1 + 4);
  v17[0] = *(_DWORD *)a3;
  v14[0] = *(_DWORD *)a2;
  v14[1] = *(_DWORD *)(a2 + 4);
  v15 = *(_BYTE **)(a2 + 8);
  v16 = v15;
  v19 = 0;
  v20[0] = v4;
  v21 = v3;
  v22 = v3;
  v17[1] = v7;
  v18 = v6;
  if ( !(unsigned __int8)ValidateDataKey(v14, &v23) )
    return 3221225712LL;
  v10 = v4 + 8;
  if ( (((_BYTE)v4 + 8) & 7) != 0 )
    v10 = v10 - (((_BYTE)v4 + 8) & 7) + 8;
  if ( v8 < v10 )
  {
    result = 3221225507LL;
LABEL_15:
    *(_DWORD *)a3 = v10;
    return result;
  }
  v26[0] = v4;
  v26[1] = 1;
  SystemFunction001((__int64)v26, v16, v6);
  v19 = v6 + 8;
  AdvanceDataKey(v14);
  if ( v12 < 0 )
    return (unsigned int)v12;
  while ( 1 )
  {
    v13 = v11;
    if ( v4 < 8 )
      break;
    SystemFunction001(v3, v16, v11);
    v3 += 8;
    v19 = v13 + 8;
    v22 = v3;
    AdvanceDataKey(v14);
    if ( v12 < 0 )
      return (unsigned int)v12;
    v4 -= 8;
  }
  if ( !v4 || (result = EncryptPartialBlock(v20, v14, v17, v4), (int)result >= 0) )
  {
    result = 0;
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x180002c90  mov     [rsp-28h+arg_8], rbx
0x180002c95  push    rbp
0x180002c96  push    rsi
0x180002c97  push    rdi
0x180002c98  push    r14
0x180002c9a  push    r15
0x180002c9c  mov     rbp, rsp
0x180002c9f  sub     rsp, 80h
0x180002ca6  mov     rax, cs:__security_cookie
0x180002cad  xor     rax, rsp
0x180002cb0  mov     [rbp+var_8], rax
0x180002cb4  mov     rsi, [rcx+8]
0x180002cb8  xor     eax, eax
0x180002cba  mov     edi, [rcx]
0x180002cbc  mov     r15, r8
0x180002cbf  mov     r14, [r8+8]
0x180002cc3  mov     r11d, [r8+4]
0x180002cc7  mov     [rbp+var_18], eax
0x180002cca  mov     [rbp+var_14], ax
0x180002cce  mov     [rbp+var_12], al
0x180002cd1  mov     eax, [rcx+4]
0x180002cd4  lea     rcx, [rbp+var_60]
0x180002cd8  mov     [rbp+var_2C], eax
0x180002cdb  mov     eax, [r8]
0x180002cde  mov     [rbp+var_48], eax
0x180002ce1  mov     eax, [rdx]
0x180002ce3  mov     [rbp+var_60], eax
0x180002ce6  mov     eax, [rdx+4]
0x180002ce9  mov     [rbp+var_5C], eax
0x180002cec  mov     rax, [rdx+8]
0x180002cf0  lea     rdx, [rbp+var_18]
0x180002cf4  mov     [rbp+var_30], 0
0x180002cfb  mov     [rbp+var_58], rax
0x180002cff  mov     [rbp+var_50], rax
0x180002d03  mov     [rbp+var_38], 0
0x180002d0b  mov     [rbp+var_30], edi
0x180002d0e  mov     [rbp+var_28], rsi
0x180002d12  mov     [rbp+var_20], rsi
0x180002d16  mov     [rbp+var_44], r11d
0x180002d1a  mov     [rbp+var_40], r14
0x180002d1e  call    ValidateDataKey
0x180002d23  test    al, al
0x180002d25  jnz     short loc_180002D31
0x180002d27  mov     eax, 0C00000F0h
0x180002d2c  jmp     loc_180002DE5
0x180002d31  lea     ebx, [rdi+8]
0x180002d34  mov     eax, ebx
0x180002d36  and     eax, 7
0x180002d39  jbe     short loc_180002D40
0x180002d3b  sub     ebx, eax
0x180002d3d  add     ebx, 8
0x180002d40  cmp     r11d, ebx
0x180002d43  jnb     short loc_180002D4F
0x180002d45  mov     eax, 0C0000023h
0x180002d4a  jmp     loc_180002DE2
0x180002d4f  mov     rdx, [rbp+var_50]
0x180002d53  lea     rcx, [rbp+var_10]
0x180002d57  mov     r8, r14
0x180002d5a  mov     [rbp+var_10], edi
0x180002d5d  mov     [rbp+var_C], 1
0x180002d64  call    SystemFunction001
0x180002d69  lea     r10, [r14+8]
0x180002d6d  mov     r11d, eax
0x180002d70  lea     rcx, [rbp+var_60]
0x180002d74  mov     [rbp+var_38], r10
0x180002d78  call    AdvanceDataKey
0x180002d7d  test    r11d, r11d
0x180002d80  jns     short loc_180002D87
0x180002d82  mov     eax, r11d
0x180002d85  jmp     short loc_180002DE5
0x180002d87  mov     r14, r10
0x180002d8a  cmp     edi, 8
0x180002d8d  jb      short loc_180002DC4
0x180002d8f  mov     rdx, [rbp+var_50]
0x180002d93  mov     r8, r10
0x180002d96  mov     rcx, rsi
0x180002d99  call    SystemFunction001
0x180002d9e  lea     r10, [r14+8]
0x180002da2  add     rsi, 8
0x180002da6  lea     rcx, [rbp+var_60]
0x180002daa  mov     [rbp+var_38], r10
0x180002dae  mov     r11d, eax
0x180002db1  mov     [rbp+var_20], rsi
0x180002db5  call    AdvanceDataKey
0x180002dba  test    r11d, r11d
0x180002dbd  js      short loc_180002D82
0x180002dbf  add     edi, 0FFFFFFF8h
0x180002dc2  jmp     short loc_180002D87
0x180002dc4  test    edi, edi
0x180002dc6  jz      short loc_180002DE0
0x180002dc8  mov     r9d, edi
0x180002dcb  lea     r8, [rbp+var_48]
0x180002dcf  lea     rdx, [rbp+var_60]
0x180002dd3  lea     rcx, [rbp+var_30]
0x180002dd7  call    EncryptPartialBlock
0x180002ddc  test    eax, eax
0x180002dde  js      short loc_180002DE5
0x180002de0  xor     eax, eax
0x180002de2  mov     [r15], ebx
0x180002de5  mov     rcx, [rbp+var_8]
0x180002de9  xor     rcx, rsp; StackCookie
0x180002dec  call    __security_check_cookie
0x180002df1  mov     rbx, [rsp+80h+arg_8]
0x180002df9  add     rsp, 80h
0x180002e00  pop     r15
0x180002e02  pop     r14
0x180002e04  pop     rdi
0x180002e05  pop     rsi
0x180002e06  pop     rbp
0x180002e07  retn
```
