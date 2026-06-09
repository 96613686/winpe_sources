# CalcUncompactFontSize

- ea: `0x1800089c8`
- end: `0x180008c60`
- name: `CalcUncompactFontSize`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009544`

## callees

- `0x180008990`
- `0x1800089c8`
- `0x180019a40`
- `0x180019e04`
- `0x180019e64`
- `0x18001a2cc`
- `0x18001a3bc`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall CalcUncompactFontSize(__int64 a1, unsigned int *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  __int64 result; // rax
  int v7; // r15d
  unsigned __int16 GenericSize; // ax
  unsigned int v9; // edi
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned __int16 v12; // ax
  unsigned int v13; // ebx
  unsigned int v14; // edi
  unsigned int v15; // eax
  unsigned __int16 v16; // ax
  unsigned int v17; // ebx
  unsigned int v18; // edi
  unsigned int v19; // eax
  unsigned __int16 v20; // ax
  unsigned int v21; // edi
  unsigned int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // edi
  unsigned int v25; // ebx
  unsigned int v26; // eax
  __int16 v27; // [rsp+30h] [rbp-39h] BYREF
  __int64 v28; // [rsp+38h] [rbp-31h] BYREF
  __int128 v29; // [rsp+40h] [rbp-29h] BYREF
  int v30; // [rsp+50h] [rbp-19h]
  _OWORD v31[3]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v32; // [rsp+88h] [rbp+1Fh]

  v30 = 0;
  v32 = 0;
  *a2 = *(_DWORD *)(a1 + 8);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  memset(v31, 0, sizeof(v31));
  v4 = TTTableOffset(a1, "dttf");
  v5 = TTTableLength(a1, "dttf");
  if ( v4 && v5 )
  {
    result = ReadGeneric(a1, (__int64)&v29, 0x12u, (unsigned __int8 *)&DTTF_HEADER_CONTROL, v4, &v27);
    if ( (_WORD)result )
      return result;
    if ( (unsigned __int16)(WORD6(v29) - 1) <= 1u )
    {
      v7 = WORD4(v29);
      if ( (unsigned int)TTTableOffset(a1, "LTSH") )
      {
        GenericSize = GetGenericSize(&LTSH_CONTROL);
        v9 = *a2;
        v10 = v7 + GenericSize;
        v11 = TTTableLength(a1, "LTSH");
        *a2 = CalcNewUncompactSize(v9, v11, v10);
      }
      if ( (unsigned int)TTTableOffset(a1, "hmtx") )
      {
        v12 = GetGenericSize(&LONGHORMETRIC_CONTROL);
        v13 = *a2;
        v14 = v7 * v12;
        v15 = TTTableLength(a1, "hmtx");
        *a2 = CalcNewUncompactSize(v13, v15, v14);
      }
      if ( (unsigned int)TTTableOffset(a1, "vmtx") )
      {
        v16 = GetGenericSize(&LONGVERMETRIC_CONTROL);
        v17 = *a2;
        v18 = v7 * v16;
        v19 = TTTableLength(a1, "vmtx");
        *a2 = CalcNewUncompactSize(v17, v19, v18);
      }
      if ( (unsigned int)GetGeneric(a1, &v28, 8) )
      {
        v20 = GetGenericSize(&HDMX_DEVICE_REC_CONTROL);
        v21 = *a2;
        v22 = SWORD1(v28) * ((v7 + v20 + 3) & 0xFFFFFFFC);
        v23 = TTTableLength(a1, "hdmx");
        *a2 = CalcNewUncompactSize(v21, v23, v22 + 8);
      }
      if ( !(unsigned int)GetGeneric(a1, v31, 0) )
        return 1032;
      if ( !(unsigned int)TTTableOffset(a1, "loca") )
        return 1035;
      v24 = *a2;
      v25 = (WORD1(v32) != 0 ? 4 : 2) * (v7 + 1);
      v26 = TTTableLength(a1, "loca");
      *a2 = CalcNewUncompactSize(v24, v26, v25);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800089c8  mov     [rsp-8+arg_10], rbx
0x1800089cd  mov     [rsp-8+arg_18], rsi
0x1800089d2  push    rbp
0x1800089d3  push    rdi
0x1800089d4  push    r12
0x1800089d6  push    r14
0x1800089d8  push    r15
0x1800089da  lea     rbp, [rsp-37h]
0x1800089df  sub     rsp, 0A0h
0x1800089e6  mov     rax, cs:__security_cookie
0x1800089ed  xor     rax, rsp
0x1800089f0  mov     [rbp+57h+var_30], rax
0x1800089f4  xor     eax, eax
0x1800089f6  xorps   xmm1, xmm1
0x1800089f9  mov     [rbp+57h+var_70], eax
0x1800089fc  mov     r14, rdx
0x1800089ff  mov     [rbp+57h+var_38], rax
0x180008a03  xor     r12d, r12d
0x180008a06  mov     eax, [rcx+8]
0x180008a09  xorps   xmm0, xmm0
0x180008a0c  mov     [rdx], eax
0x180008a0e  mov     rsi, rcx
0x180008a11  lea     rdx, aDttf; "dttf"
0x180008a18  mov     [rbp+57h+var_90], r12w
0x180008a1d  mov     [rbp+57h+var_88], r12
0x180008a21  movups  [rbp+57h+var_80], xmm0
0x180008a25  movups  [rbp+57h+var_68], xmm1
0x180008a29  movups  [rbp+57h+var_58], xmm1
0x180008a2d  movups  [rbp+57h+var_48], xmm1
0x180008a31  call    TTTableOffset
0x180008a36  lea     rdx, aDttf; "dttf"
0x180008a3d  mov     rcx, rsi
0x180008a40  mov     ebx, eax
0x180008a42  call    TTTableLength
0x180008a47  test    ebx, ebx
0x180008a49  jz      loc_180008C35
0x180008a4f  test    eax, eax
0x180008a51  jz      loc_180008C35
0x180008a57  lea     rax, [rbp+57h+var_90]
0x180008a5b  mov     rcx, rsi
0x180008a5e  mov     [rsp+0C0h+var_98], rax
0x180008a63  lea     r8d, [r12+12h]
0x180008a68  lea     r9, DTTF_HEADER_CONTROL
0x180008a6f  mov     [rsp+0C0h+var_A0], ebx
0x180008a73  lea     rdx, [rbp+57h+var_80]
0x180008a77  call    ReadGeneric
0x180008a7c  test    ax, ax
0x180008a7f  jnz     loc_180008C38
0x180008a85  movzx   eax, word ptr [rbp+57h+var_80+0Ch]
0x180008a89  dec     ax
0x180008a8c  cmp     ax, 1
0x180008a90  ja      loc_180008C35
0x180008a96  movzx   r15d, word ptr [rbp+57h+var_80+8]
0x180008a9b  lea     rdx, aLtsh; "LTSH"
0x180008aa2  mov     rcx, rsi
0x180008aa5  call    TTTableOffset
0x180008aaa  test    eax, eax
0x180008aac  jz      short loc_180008AE1
0x180008aae  lea     rcx, LTSH_CONTROL
0x180008ab5  call    GetGenericSize
0x180008aba  mov     edi, [r14]
0x180008abd  lea     rdx, aLtsh; "LTSH"
0x180008ac4  movzx   ebx, ax
0x180008ac7  mov     rcx, rsi
0x180008aca  add     ebx, r15d
0x180008acd  call    TTTableLength
0x180008ad2  mov     edx, eax
0x180008ad4  mov     r8d, ebx
0x180008ad7  mov     ecx, edi
0x180008ad9  call    CalcNewUncompactSize
0x180008ade  mov     [r14], eax
0x180008ae1  lea     rdx, Str2; "hmtx"
0x180008ae8  mov     rcx, rsi
0x180008aeb  call    TTTableOffset
0x180008af0  test    eax, eax
0x180008af2  jz      short loc_180008B28
0x180008af4  lea     rcx, LONGHORMETRIC_CONTROL
0x180008afb  call    GetGenericSize
0x180008b00  mov     ebx, [r14]
0x180008b03  lea     rdx, Str2; "hmtx"
0x180008b0a  movzx   edi, ax
0x180008b0d  mov     rcx, rsi
0x180008b10  imul    edi, r15d
0x180008b14  call    TTTableLength
0x180008b19  mov     edx, eax
0x180008b1b  mov     r8d, edi
0x180008b1e  mov     ecx, ebx
0x180008b20  call    CalcNewUncompactSize
0x180008b25  mov     [r14], eax
0x180008b28  lea     rdx, Str1; "vmtx"
0x180008b2f  mov     rcx, rsi
0x180008b32  call    TTTableOffset
0x180008b37  test    eax, eax
0x180008b39  jz      short loc_180008B6F
0x180008b3b  lea     rcx, LONGVERMETRIC_CONTROL
0x180008b42  call    GetGenericSize
0x180008b47  mov     ebx, [r14]
0x180008b4a  lea     rdx, Str1; "vmtx"
0x180008b51  movzx   edi, ax
0x180008b54  mov     rcx, rsi
0x180008b57  imul    edi, r15d
0x180008b5b  call    TTTableLength
0x180008b60  mov     edx, eax
0x180008b62  mov     r8d, edi
0x180008b65  mov     ecx, ebx
0x180008b67  call    CalcNewUncompactSize
0x180008b6c  mov     [r14], eax
0x180008b6f  mov     r8d, 8
0x180008b75  lea     rdx, [rbp+57h+var_88]
0x180008b79  mov     rcx, rsi
0x180008b7c  call    GetGeneric
0x180008b81  test    eax, eax
0x180008b83  jz      short loc_180008BC6
0x180008b85  lea     rcx, HDMX_DEVICE_REC_CONTROL
0x180008b8c  call    GetGenericSize
0x180008b91  mov     edi, [r14]
0x180008b94  lea     rdx, aHdmx; "hdmx"
0x180008b9b  movzx   ebx, ax
0x180008b9e  mov     rcx, rsi
0x180008ba1  movsx   eax, word ptr [rbp+57h+var_88+2]
0x180008ba5  add     ebx, 3
0x180008ba8  add     ebx, r15d
0x180008bab  and     ebx, 0FFFFFFFCh
0x180008bae  imul    ebx, eax
0x180008bb1  call    TTTableLength
0x180008bb6  mov     edx, eax
0x180008bb8  lea     r8d, [rbx+8]
0x180008bbc  mov     ecx, edi
0x180008bbe  call    CalcNewUncompactSize
0x180008bc3  mov     [r14], eax
0x180008bc6  xor     r8d, r8d
0x180008bc9  lea     rdx, [rbp+57h+var_68]
0x180008bcd  mov     rcx, rsi
0x180008bd0  call    GetGeneric
0x180008bd5  test    eax, eax
0x180008bd7  jnz     short loc_180008BE0
0x180008bd9  mov     eax, 408h
0x180008bde  jmp     short loc_180008C38
0x180008be0  lea     rdx, aLoca; "loca"
0x180008be7  mov     rcx, rsi
0x180008bea  call    TTTableOffset
0x180008bef  test    eax, eax
0x180008bf1  jnz     short loc_180008BFA
0x180008bf3  mov     eax, 40Bh
0x180008bf8  jmp     short loc_180008C38
0x180008bfa  movzx   eax, word ptr [rbp+57h+var_38+2]
0x180008bfe  lea     ebx, [r15+1]
0x180008c02  mov     edi, [r14]
0x180008c05  lea     rdx, aLoca; "loca"
0x180008c0c  neg     ax
0x180008c0f  mov     rcx, rsi
0x180008c12  sbb     r8d, r8d
0x180008c15  and     r8d, 2
0x180008c19  add     r8d, 2
0x180008c1d  imul    ebx, r8d
0x180008c21  call    TTTableLength
0x180008c26  mov     edx, eax
0x180008c28  mov     r8d, ebx
0x180008c2b  mov     ecx, edi
0x180008c2d  call    CalcNewUncompactSize
0x180008c32  mov     [r14], eax
0x180008c35  mov     eax, r12d
0x180008c38  mov     rcx, [rbp+57h+var_30]
0x180008c3c  xor     rcx, rsp; StackCookie
0x180008c3f  call    __security_check_cookie
0x180008c44  lea     r11, [rsp+0C0h+var_20]
0x180008c4c  mov     rbx, [r11+40h]
0x180008c50  mov     rsi, [r11+48h]
0x180008c54  mov     rsp, r11
0x180008c57  pop     r15
0x180008c59  pop     r14
0x180008c5b  pop     r12
0x180008c5d  pop     rdi
0x180008c5e  pop     rbp
0x180008c5f  retn
```
