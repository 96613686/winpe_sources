# LipsIkeAuthCreate

- ea: `0x18004cb0c`
- end: `0x18004ccf9`
- name: `LipsIkeAuthCreate`
- size: `493`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004a00c`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004c6f0`
- `0x18004ca74`
- `0x18004cb0c`
- `0x18004cd00`
- `0x18004cd7c`

## string_xrefs

- `0x18004ccd6`: `LipsIkeAuthCreate`

## pseudocode

```c
__int64 __fastcall LipsIkeAuthCreate(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // r9
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  LPVOID v10; // rax
  __int128 v12; // [rsp+20h] [rbp-30h] BYREF
  __int128 v13; // [rsp+30h] [rbp-20h]
  unsigned int v14; // [rsp+40h] [rbp-10h]
  LPVOID v15; // [rsp+78h] [rbp+28h] BYREF

  v14 = 0;
  *a2 = 0;
  v12 = 0;
  v13 = 0;
  v15 = IpsecAllocMem(0x10u);
  v4 = (__int64)v15;
  if ( !v15 )
  {
    v5 = 8;
    v6 = 8;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_28;
    v8 = 10;
    goto LABEL_5;
  }
  LipsIkeAuthCount(a1, &v12);
  v9 = v14;
  *(_DWORD *)(v4 + 8) = v14;
  v10 = IpsecAllocMem(v9 << 6);
  *(_QWORD *)v4 = v10;
  if ( !v10 )
  {
    v5 = 8;
    v6 = 8;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_28;
    v8 = 11;
    goto LABEL_5;
  }
  v6 = 0;
  if ( (_DWORD)v12 != 0xFFFF )
  {
    v6 = LipsIkeAuthPresharedKeyCreate(a1, &v12, v4);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_28;
      v8 = 12;
      goto LABEL_15;
    }
  }
  if ( DWORD2(v12) != 0xFFFF )
  {
    v6 = LipsIkeAuthCertCreate(a1, (unsigned int *)&v12, v4);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_28;
      v8 = 13;
LABEL_15:
      v5 = v6;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids, v5);
      goto LABEL_28;
    }
  }
  if ( DWORD2(v13) != 0xFFFF )
  {
    if ( DWORD2(v13) >= *(_DWORD *)(v4 + 8) )
    {
      v5 = 13;
      v6 = 13;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_28;
      v8 = 14;
      goto LABEL_5;
    }
    v6 = 0;
    *(_DWORD *)(((unsigned __int64)DWORD2(v13) << 6) + *(_QWORD *)v4) = 2;
  }
  *a2 = v4;
  v15 = 0;
LABEL_28:
  LipsIkeAuthDestroy(&v15);
  if ( v6 )
    return LipsReportError(v6, "LipsIkeAuthCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004cb0c  mov     [rsp-18h+arg_0], rbx
0x18004cb11  mov     [rsp-18h+arg_10], rsi
0x18004cb16  push    rbp
0x18004cb17  push    rdi
0x18004cb18  push    r14
0x18004cb1a  mov     rbp, rsp
0x18004cb1d  sub     rsp, 50h
0x18004cb21  xor     eax, eax
0x18004cb23  xorps   xmm0, xmm0
0x18004cb26  mov     rsi, rcx
0x18004cb29  mov     [rbp+var_10], eax
0x18004cb2c  mov     r14, rdx
0x18004cb2f  mov     [rdx], rax
0x18004cb32  movups  [rbp+var_30], xmm0
0x18004cb36  lea     ecx, [rax+10h]
0x18004cb39  movups  [rbp+var_20], xmm0
0x18004cb3d  call    IpsecAllocMem
0x18004cb42  mov     [rbp+arg_8], rax
0x18004cb46  mov     rdi, rax
0x18004cb49  test    rax, rax
0x18004cb4c  jnz     short loc_18004CB8E
0x18004cb4e  lea     r9d, [rax+8]
0x18004cb52  mov     ebx, r9d
0x18004cb55  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb5c  lea     rax, WPP_GLOBAL_Control
0x18004cb63  cmp     rcx, rax
0x18004cb66  jz      loc_18004CCC5
0x18004cb6c  test    byte ptr [rcx+1Ch], 10h
0x18004cb70  jz      loc_18004CCC5
0x18004cb76  lea     edx, [rdi+0Ah]
0x18004cb79  mov     rcx, [rcx+10h]
0x18004cb7d  lea     r8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids
0x18004cb84  call    WPP_SF_d
0x18004cb89  jmp     loc_18004CCC5
0x18004cb8e  lea     rdx, [rbp+var_30]
0x18004cb92  mov     rcx, rsi
0x18004cb95  call    LipsIkeAuthCount
0x18004cb9a  mov     edx, [rbp+var_10]
0x18004cb9d  mov     ecx, edx
0x18004cb9f  mov     [rdi+8], edx
0x18004cba2  shl     rcx, 6
0x18004cba6  call    IpsecAllocMem
0x18004cbab  mov     [rdi], rax
0x18004cbae  test    rax, rax
0x18004cbb1  jnz     short loc_18004CBE1
0x18004cbb3  lea     r9d, [rax+8]
0x18004cbb7  mov     ebx, r9d
0x18004cbba  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cbc1  lea     rax, WPP_GLOBAL_Control
0x18004cbc8  cmp     rcx, rax
0x18004cbcb  jz      loc_18004CCC5
0x18004cbd1  test    byte ptr [rcx+1Ch], 10h
0x18004cbd5  jz      loc_18004CCC5
0x18004cbdb  lea     edx, [r9+3]
0x18004cbdf  jmp     short loc_18004CB79
0x18004cbe1  xor     ebx, ebx
0x18004cbe3  cmp     dword ptr [rbp+var_30], 0FFFFh
0x18004cbea  jz      short loc_18004CC2F
0x18004cbec  mov     r8, rdi
0x18004cbef  lea     rdx, [rbp+var_30]
0x18004cbf3  mov     rcx, rsi
0x18004cbf6  call    LipsIkeAuthPresharedKeyCreate
0x18004cbfb  mov     ebx, eax
0x18004cbfd  test    eax, eax
0x18004cbff  jz      short loc_18004CC2F
0x18004cc01  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc08  lea     rax, WPP_GLOBAL_Control
0x18004cc0f  cmp     rcx, rax
0x18004cc12  jz      loc_18004CCC5
0x18004cc18  test    byte ptr [rcx+1Ch], 10h
0x18004cc1c  jz      loc_18004CCC5
0x18004cc22  mov     edx, 0Ch
0x18004cc27  mov     r9d, ebx
0x18004cc2a  jmp     loc_18004CB79
0x18004cc2f  cmp     dword ptr [rbp+var_30+8], 0FFFFh
0x18004cc36  jz      short loc_18004CC6D
0x18004cc38  mov     r8, rdi
0x18004cc3b  lea     rdx, [rbp+var_30]
0x18004cc3f  mov     rcx, rsi
0x18004cc42  call    LipsIkeAuthCertCreate
0x18004cc47  mov     ebx, eax
0x18004cc49  test    eax, eax
0x18004cc4b  jz      short loc_18004CC6D
0x18004cc4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc54  lea     rax, WPP_GLOBAL_Control
0x18004cc5b  cmp     rcx, rax
0x18004cc5e  jz      short loc_18004CCC5
0x18004cc60  test    byte ptr [rcx+1Ch], 10h
0x18004cc64  jz      short loc_18004CCC5
0x18004cc66  mov     edx, 0Dh
0x18004cc6b  jmp     short loc_18004CC27
0x18004cc6d  mov     eax, dword ptr [rbp+var_20+8]
0x18004cc70  cmp     eax, 0FFFFh
0x18004cc75  jz      short loc_18004CCBA
0x18004cc77  cmp     eax, [rdi+8]
0x18004cc7a  jb      short loc_18004CCA7
0x18004cc7c  mov     r9d, 0Dh
0x18004cc82  mov     ebx, r9d
0x18004cc85  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc8c  lea     rax, WPP_GLOBAL_Control
0x18004cc93  cmp     rcx, rax
0x18004cc96  jz      short loc_18004CCC5
0x18004cc98  test    byte ptr [rcx+1Ch], 10h
0x18004cc9c  jz      short loc_18004CCC5
0x18004cc9e  lea     edx, [r9+1]
0x18004cca2  jmp     loc_18004CB79
0x18004cca7  mov     rcx, rax
0x18004ccaa  mov     rax, [rdi]
0x18004ccad  shl     rcx, 6
0x18004ccb1  xor     ebx, ebx
0x18004ccb3  mov     dword ptr [rcx+rax], 2
0x18004ccba  mov     [r14], rdi
0x18004ccbd  mov     [rbp+arg_8], 0
0x18004ccc5  lea     rcx, [rbp+arg_8]
0x18004ccc9  call    LipsIkeAuthDestroy
0x18004ccce  test    ebx, ebx
0x18004ccd0  jnz     short loc_18004CCD6
0x18004ccd2  xor     eax, eax
0x18004ccd4  jmp     short loc_18004CCE4
0x18004ccd6  lea     rdx, aLipsikeauthcre; "LipsIkeAuthCreate"
0x18004ccdd  mov     ecx, ebx
0x18004ccdf  call    LipsReportError
0x18004cce4  lea     r11, [rsp+50h+var_s0]
0x18004cce9  mov     rbx, [r11+20h]
0x18004cced  mov     rsi, [r11+30h]
0x18004ccf1  mov     rsp, r11
0x18004ccf4  pop     r14
0x18004ccf6  pop     rdi
0x18004ccf7  pop     rbp
0x18004ccf8  retn
```
