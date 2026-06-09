# SystemFunction005

- ea: `0x180001820`
- end: `0x180001978`
- name: `SystemFunction005`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001820`
- `0x180001980`
- `0x180001a50`
- `0x180002aa8`
- `0x180002ae4`
- `0x180002b3c`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall SystemFunction005(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  __int64 v4; // rbx
  __int64 v6; // r11
  __int64 result; // rax
  unsigned int v8; // ebx
  _DWORD v9[2]; // [rsp+20h] [rbp-29h] BYREF
  _BYTE *v10; // [rsp+28h] [rbp-21h]
  _BYTE *v11; // [rsp+30h] [rbp-19h]
  _DWORD v12[2]; // [rsp+38h] [rbp-11h] BYREF
  __int64 v13; // [rsp+40h] [rbp-9h]
  __int64 v14; // [rsp+48h] [rbp-1h]
  _DWORD v15[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v16; // [rsp+58h] [rbp+Fh]
  __int64 v17; // [rsp+60h] [rbp+17h]
  int v18; // [rsp+68h] [rbp+1Fh] BYREF
  __int16 v19; // [rsp+6Ch] [rbp+23h]
  char v20; // [rsp+6Eh] [rbp+25h]
  __int64 v21; // [rsp+70h] [rbp+27h] BYREF

  v3 = *(_DWORD *)a1;
  v4 = *(_QWORD *)(a1 + 8);
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v15[1] = *(_DWORD *)(a3 + 4);
  v16 = *(_QWORD *)(a3 + 8);
  v17 = v16;
  v12[1] = *(_DWORD *)(a1 + 4);
  v9[0] = *(_DWORD *)a2;
  v9[1] = *(_DWORD *)(a2 + 4);
  v10 = *(_BYTE **)(a2 + 8);
  v11 = v10;
  v14 = 0;
  v12[0] = v3;
  v13 = v4;
  if ( !(unsigned __int8)ValidateDataKey(v9, &v18) )
    return 3221225712LL;
  if ( (v3 & 7) != 0 || v3 < 8 )
    return 3221225711LL;
  v21 = v6;
  result = SystemFunction002(v4, v11, (__int64)&v21);
  if ( (int)result < 0 )
    return result;
  v14 = v4 + 8;
  AdvanceDataKey(v9);
  v8 = v21;
  v15[0] = v21;
  if ( HIDWORD(v21) != 1 )
    return 3221225560LL;
  if ( v3 - 8 < (unsigned int)v21 )
    return 3221225711LL;
  if ( *(_DWORD *)(a3 + 4) >= (unsigned int)v21 )
  {
    while ( v8 >= 8 )
    {
      result = DecryptFullBlock(v12, v9, v15);
      if ( (int)result < 0 )
        return result;
      v8 -= 8;
    }
    if ( !v8 || (result = DecryptPartialBlock(v12, v9, v15, v8), (int)result >= 0) )
    {
      *(_DWORD *)a3 = v15[0];
      return 0;
    }
  }
  else
  {
    *(_DWORD *)a3 = v21;
    return 3221225507LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001820  push    rbp
0x180001822  push    rbx
0x180001823  push    rsi
0x180001824  push    rdi
0x180001825  lea     rbp, [rsp-3Fh]
0x18000182a  sub     rsp, 88h
0x180001831  mov     rax, cs:__security_cookie
0x180001838  xor     rax, rsp
0x18000183b  mov     [rbp+57h+var_28], rax
0x18000183f  mov     edi, [rcx]
0x180001841  xor     eax, eax
0x180001843  mov     rbx, [rcx+8]
0x180001847  xor     r11d, r11d
0x18000184a  mov     [rbp+57h+var_38], eax
0x18000184d  mov     rsi, r8
0x180001850  mov     [rbp+57h+var_34], ax
0x180001854  mov     [rbp+57h+var_32], al
0x180001857  mov     eax, [r8+4]
0x18000185b  mov     [rbp+57h+var_4C], eax
0x18000185e  mov     rax, [r8+8]
0x180001862  mov     [rbp+57h+var_48], rax
0x180001866  mov     [rbp+57h+var_40], rax
0x18000186a  mov     eax, [rcx+4]
0x18000186d  lea     rcx, [rbp+57h+var_80]
0x180001871  mov     [rbp+57h+var_64], eax
0x180001874  mov     eax, [rdx]
0x180001876  mov     [rbp+57h+var_80], eax
0x180001879  mov     eax, [rdx+4]
0x18000187c  mov     [rbp+57h+var_7C], eax
0x18000187f  mov     rax, [rdx+8]
0x180001883  lea     rdx, [rbp+57h+var_38]
0x180001887  mov     [rbp+57h+var_78], rax
0x18000188b  mov     [rbp+57h+var_70], rax
0x18000188f  mov     [rbp+57h+var_58], r11
0x180001893  mov     [rbp+57h+var_68], edi
0x180001896  mov     [rbp+57h+var_60], rbx
0x18000189a  call    ValidateDataKey
0x18000189f  test    al, al
0x1800018a1  jnz     short loc_1800018AD
0x1800018a3  mov     eax, 0C00000F0h
0x1800018a8  jmp     loc_18000195F
0x1800018ad  test    dil, 7
0x1800018b1  jnz     loc_18000195A
0x1800018b7  cmp     edi, 8
0x1800018ba  jb      loc_18000195A
0x1800018c0  mov     rdx, [rbp+57h+var_70]
0x1800018c4  lea     r8, [rbp+57h+var_30]
0x1800018c8  mov     rcx, rbx
0x1800018cb  mov     [rbp+57h+var_30], r11
0x1800018cf  call    SystemFunction002
0x1800018d4  test    eax, eax
0x1800018d6  js      loc_18000195F
0x1800018dc  lea     rax, [rbx+8]
0x1800018e0  lea     rcx, [rbp+57h+var_80]
0x1800018e4  mov     [rbp+57h+var_58], rax
0x1800018e8  call    AdvanceDataKey
0x1800018ed  cmp     dword ptr [rbp+57h+var_30+4], 1
0x1800018f1  mov     rbx, [rbp+57h+var_30]
0x1800018f5  mov     [rbp+57h+var_50], ebx
0x1800018f8  jz      short loc_180001901
0x1800018fa  mov     eax, 0C0000058h
0x1800018ff  jmp     short loc_18000195F
0x180001901  lea     eax, [rdi-8]
0x180001904  cmp     eax, ebx
0x180001906  jb      short loc_18000195A
0x180001908  cmp     [rsi+4], ebx
0x18000190b  jnb     short loc_180001916
0x18000190d  mov     [rsi], ebx
0x18000190f  mov     eax, 0C0000023h
0x180001914  jmp     short loc_18000195F
0x180001916  cmp     ebx, 8
0x180001919  jb      short loc_180001935
0x18000191b  lea     r8, [rbp+57h+var_50]
0x18000191f  lea     rdx, [rbp+57h+var_80]
0x180001923  lea     rcx, [rbp+57h+var_68]
0x180001927  call    DecryptFullBlock
0x18000192c  test    eax, eax
0x18000192e  js      short loc_18000195F
0x180001930  add     ebx, 0FFFFFFF8h
0x180001933  jmp     short loc_180001916
0x180001935  test    ebx, ebx
0x180001937  jz      short loc_180001951
0x180001939  mov     r9d, ebx
0x18000193c  lea     r8, [rbp+57h+var_50]
0x180001940  lea     rdx, [rbp+57h+var_80]
0x180001944  lea     rcx, [rbp+57h+var_68]
0x180001948  call    DecryptPartialBlock
0x18000194d  test    eax, eax
0x18000194f  js      short loc_18000195F
0x180001951  mov     eax, [rbp+57h+var_50]
0x180001954  mov     [rsi], eax
0x180001956  xor     eax, eax
0x180001958  jmp     short loc_18000195F
0x18000195a  mov     eax, 0C00000EFh
0x18000195f  mov     rcx, [rbp+57h+var_28]
0x180001963  xor     rcx, rsp; StackCookie
0x180001966  call    __security_check_cookie
0x18000196b  add     rsp, 88h
0x180001972  pop     rdi
0x180001973  pop     rsi
0x180001974  pop     rbx
0x180001975  pop     rbp
0x180001976  retn
```
