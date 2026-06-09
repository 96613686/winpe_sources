# RtlpIsEmptyImageFileOptionsKey

- ea: `0x180123b28`
- end: `0x180123d5c`
- name: `RtlpIsEmptyImageFileOptionsKey`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180123b28`
- `0x18013afcc`

## callees

- `0x180029590`
- `0x18002b2a0`
- `0x180123b28`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e530`
- `0x18015e910`
- `0x180162000`

## string_xrefs

- `0x180123bf7`: `FilterFullPath`

## pseudocode

```c
bool __fastcall RtlpIsEmptyImageFileOptionsKey(__int64 a1)
{
  int inited; // ebx
  unsigned int v3; // edi
  int v4; // edi
  unsigned int v5; // esi
  char IsEmptyImageFileOptionsKey; // bl
  int v8; // [rsp+20h] [rbp-E0h]
  int v9; // [rsp+20h] [rbp-E0h]
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v17; // [rsp+A8h] [rbp-58h]
  __int16 v18; // [rsp+ACh] [rbp-54h] BYREF
  char v19; // [rsp+B0h] [rbp-50h] BYREF

  inited = 0;
  v10 = 0;
  Handle = 0;
  v3 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  memset(v15, 0, 44);
  while ( inited >= 0 )
  {
    inited = ZwEnumerateValueKey(a1, v3, 0, v16, 560, &v10);
    if ( inited >= 0 )
    {
      if ( v3 )
        return 0;
      LOWORD(v11) = v17;
      WORD1(v11) = v17;
      *((_QWORD *)&v11 + 1) = &v18;
      if ( (int)RtlInitUnicodeStringEx(&v13, L"UseFilter") < 0 )
        return 0;
      inited = RtlInitUnicodeStringEx(&v14, L"FilterFullPath");
      if ( inited < 0 )
        return 0;
      LOBYTE(v8) = 1;
      if ( (unsigned int)RtlCompareUnicodeStrings(
                           *((_QWORD *)&v11 + 1),
                           (unsigned __int64)(unsigned __int16)v11 >> 1,
                           *((_QWORD *)&v13 + 1),
                           (unsigned __int64)(unsigned __int16)v13 >> 1,
                           v8) )
      {
        LOBYTE(v9) = 1;
        if ( (unsigned int)RtlCompareUnicodeStrings(
                             *((_QWORD *)&v11 + 1),
                             (unsigned __int64)(unsigned __int16)v11 >> 1,
                             *((_QWORD *)&v14 + 1),
                             (unsigned __int64)(unsigned __int16)v14 >> 1,
                             v9) )
          return 0;
      }
    }
    ++v3;
  }
  if ( inited != -2147483622 )
    return 0;
  v4 = 0;
  v5 = 0;
  while ( v4 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _BYTE *, int, int *))NtEnumerateKey)(
           a1,
           v5,
           0,
           v16,
           560,
           &v10);
    if ( v4 >= 0 )
    {
      LOWORD(v11) = v18;
      WORD1(v11) = v18;
      *(_DWORD *)v15 = 48;
      *((_QWORD *)&v11 + 1) = &v19;
      *(_QWORD *)&v15[8] = a1;
      *(_QWORD *)&v15[16] = &v11;
      *(_DWORD *)&v15[24] = 576;
      *(_OWORD *)&v15[32] = 0;
      v4 = NtOpenKey(&Handle, 9, v15);
      if ( v4 >= 0 )
      {
        IsEmptyImageFileOptionsKey = RtlpIsEmptyImageFileOptionsKey(Handle);
        NtClose(Handle);
        if ( !IsEmptyImageFileOptionsKey )
          return 0;
      }
    }
    ++v5;
  }
  return v4 == -2147483622;
}

```

## disassembly

```asm
0x180123b28  mov     [rsp-8+arg_8], rbx
0x180123b2d  mov     [rsp-8+arg_10], rsi
0x180123b32  push    rbp
0x180123b33  push    rdi
0x180123b34  push    r14
0x180123b36  lea     rbp, [rsp-1E0h]
0x180123b3e  sub     rsp, 2E0h
0x180123b45  mov     rax, cs:__security_cookie
0x180123b4c  xor     rax, rsp
0x180123b4f  mov     [rbp+1F0h+var_20], rax
0x180123b56  xorps   xmm0, xmm0
0x180123b59  xor     ebx, ebx
0x180123b5b  xorps   xmm1, xmm1
0x180123b5e  mov     [rsp+2F0h+var_2C0], ebx
0x180123b62  xor     eax, eax
0x180123b64  mov     [rsp+2F0h+Handle], rbx
0x180123b69  movups  [rbp+1F0h+var_270], xmm0
0x180123b6d  mov     r14, rcx
0x180123b70  xor     edi, edi
0x180123b72  movups  [rbp+1F0h+var_270+0Ch], xmm0
0x180123b76  movups  [rsp+2F0h+var_2B8], xmm0
0x180123b7b  movups  [rsp+2F0h+var_2A0], xmm1
0x180123b80  movups  [rsp+2F0h+var_290], xmm0
0x180123b85  movups  [rsp+2F0h+var_280], xmm0
0x180123b8a  test    ebx, ebx
0x180123b8c  js      loc_180123C6F
0x180123b92  lea     rax, [rsp+2F0h+var_2C0]
0x180123b97  xor     r8d, r8d
0x180123b9a  mov     [rsp+2F0h+var_2C8], rax
0x180123b9f  lea     r9, [rbp+1F0h+var_250]
0x180123ba3  mov     edx, edi
0x180123ba5  mov     [rsp+2F0h+var_2D0], 230h
0x180123bad  mov     rcx, r14
0x180123bb0  call    ZwEnumerateValueKey
0x180123bb5  mov     ebx, eax
0x180123bb7  test    eax, eax
0x180123bb9  js      loc_180123C68
0x180123bbf  test    edi, edi
0x180123bc1  jnz     loc_180123D32
0x180123bc7  movzx   eax, [rbp+1F0h+var_248]
0x180123bcb  lea     rdx, aUsefilter; "UseFilter"
0x180123bd2  mov     word ptr [rsp+2F0h+var_2B8], ax
0x180123bd7  lea     rcx, [rsp+2F0h+var_2A0]
0x180123bdc  mov     word ptr [rsp+2F0h+var_2B8+2], ax
0x180123be1  lea     rax, [rbp+1F0h+var_244]
0x180123be5  mov     qword ptr [rsp+2F0h+var_2B8+8], rax
0x180123bea  call    RtlInitUnicodeStringEx
0x180123bef  test    eax, eax
0x180123bf1  js      loc_180123D32
0x180123bf7  lea     rdx, aFilterfullpath; "FilterFullPath"
0x180123bfe  lea     rcx, [rsp+2F0h+var_290]
0x180123c03  call    RtlInitUnicodeStringEx
0x180123c08  mov     ebx, eax
0x180123c0a  test    eax, eax
0x180123c0c  js      loc_180123D32
0x180123c12  movzx   edx, word ptr [rsp+2F0h+var_2B8]
0x180123c17  movzx   r9d, word ptr [rsp+2F0h+var_2A0]
0x180123c1d  mov     r8, qword ptr [rsp+2F0h+var_2A0+8]
0x180123c22  mov     rcx, qword ptr [rsp+2F0h+var_2B8+8]
0x180123c27  shr     r9, 1
0x180123c2a  shr     rdx, 1
0x180123c2d  mov     byte ptr [rsp+2F0h+var_2D0], 1
0x180123c32  call    RtlCompareUnicodeStrings
0x180123c37  test    eax, eax
0x180123c39  jz      short loc_180123C68
0x180123c3b  movzx   edx, word ptr [rsp+2F0h+var_2B8]
0x180123c40  movzx   r9d, word ptr [rsp+2F0h+var_290]
0x180123c46  mov     r8, qword ptr [rsp+2F0h+var_290+8]
0x180123c4b  mov     rcx, qword ptr [rsp+2F0h+var_2B8+8]
0x180123c50  shr     r9, 1
0x180123c53  shr     rdx, 1
0x180123c56  mov     byte ptr [rsp+2F0h+var_2D0], 1
0x180123c5b  call    RtlCompareUnicodeStrings
0x180123c60  test    eax, eax
0x180123c62  jnz     loc_180123D32
0x180123c68  inc     edi
0x180123c6a  jmp     loc_180123B8A
0x180123c6f  cmp     ebx, 8000001Ah
0x180123c75  jnz     loc_180123D32
0x180123c7b  xor     edi, edi
0x180123c7d  xor     esi, esi
0x180123c7f  test    edi, edi
0x180123c81  js      loc_180123D27
0x180123c87  lea     rax, [rsp+2F0h+var_2C0]
0x180123c8c  xor     r8d, r8d
0x180123c8f  mov     [rsp+2F0h+var_2C8], rax
0x180123c94  lea     r9, [rbp+1F0h+var_250]
0x180123c98  mov     edx, esi
0x180123c9a  mov     [rsp+2F0h+var_2D0], 230h
0x180123ca2  mov     rcx, r14
0x180123ca5  call    NtEnumerateKey
0x180123caa  mov     edi, eax
0x180123cac  test    eax, eax
0x180123cae  js      short loc_180123D20
0x180123cb0  movzx   eax, [rbp+1F0h+var_244]
0x180123cb4  lea     r8, [rsp+2F0h+var_280]
0x180123cb9  mov     word ptr [rsp+2F0h+var_2B8], ax
0x180123cbe  lea     rcx, [rsp+2F0h+Handle]
0x180123cc3  mov     word ptr [rsp+2F0h+var_2B8+2], ax
0x180123cc8  xorps   xmm0, xmm0
0x180123ccb  lea     rax, [rbp+1F0h+var_240]
0x180123ccf  mov     dword ptr [rsp+2F0h+var_280], 30h ; '0'
0x180123cd7  mov     qword ptr [rsp+2F0h+var_2B8+8], rax
0x180123cdc  mov     edx, 9
0x180123ce1  lea     rax, [rsp+2F0h+var_2B8]
0x180123ce6  mov     qword ptr [rsp+2F0h+var_280+8], r14
0x180123ceb  mov     qword ptr [rbp+1F0h+var_270], rax
0x180123cef  mov     dword ptr [rbp+1F0h+var_270+8], 240h
0x180123cf6  movdqu  [rbp+1F0h+var_260], xmm0
0x180123cfb  call    NtOpenKey
0x180123d00  mov     edi, eax
0x180123d02  test    eax, eax
0x180123d04  js      short loc_180123D20
0x180123d06  mov     rcx, [rsp+2F0h+Handle]
0x180123d0b  call    RtlpIsEmptyImageFileOptionsKey
0x180123d10  mov     rcx, [rsp+2F0h+Handle]; Handle
0x180123d15  mov     bl, al
0x180123d17  call    NtClose
0x180123d1c  test    bl, bl
0x180123d1e  jz      short loc_180123D32
0x180123d20  inc     esi
0x180123d22  jmp     loc_180123C7F
0x180123d27  cmp     edi, 8000001Ah
0x180123d2d  setz    al
0x180123d30  jmp     short loc_180123D34
0x180123d32  xor     al, al
0x180123d34  mov     rcx, [rbp+1F0h+var_20]
0x180123d3b  xor     rcx, rsp; StackCookie
0x180123d3e  call    __security_check_cookie
0x180123d43  lea     r11, [rsp+2F0h+var_10]
0x180123d4b  mov     rbx, [r11+28h]
0x180123d4f  mov     rsi, [r11+30h]
0x180123d53  mov     rsp, r11
0x180123d56  pop     r14
0x180123d58  pop     rdi
0x180123d59  pop     rbp
0x180123d5a  retn
```
