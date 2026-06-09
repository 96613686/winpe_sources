# PACreateQMPolicyState

- ea: `0x180028884`
- end: `0x180028a84`
- name: `PACreateQMPolicyState`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009174`

## callees

- `0x180006f00`
- `0x18000964c`
- `0x18000c828`
- `0x18000e510`
- `0x18001cc18`
- `0x180027954`
- `0x180028884`
- `0x18004d090`

## pseudocode

```c
__int64 __fastcall PACreateQMPolicyState(__int64 a1, _QWORD *a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  __int64 v6; // r9
  unsigned int v7; // ebp
  _QWORD *v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rdx
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rax
  unsigned __int16 v13; // ax
  unsigned __int16 *v14; // rax
  __int64 result; // rax
  __int128 v16; // xmm1
  wchar_t pszDest[512]; // [rsp+20h] [rbp-438h] BYREF

  v4 = IpsecAllocMem(0x50u);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_25:
      *a2 = 0;
      return v7;
    }
    v9 = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_20;
    v10 = 11;
    goto LABEL_19;
  }
  v9 = *(_QWORD *)(a1 + 104);
  *v4 = *(_OWORD *)v9;
  v11 = *(unsigned __int16 **)(v9 + 72);
  if ( v11 && *v11 )
  {
    v12 = IpsecAllocStr(v11);
    *((_QWORD *)v5 + 2) = v12;
    if ( !v12 )
    {
      v6 = 8;
      v7 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_20;
        v10 = 12;
        goto LABEL_19;
      }
      goto LABEL_24;
    }
  }
  else
  {
    ++gdwQMPolicyCounter;
    v13 = StringCchPrintfW(pszDest, 0x200u, L"%d");
    v7 = v13;
    if ( v13 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_20;
        v10 = 13;
        v6 = v13;
        goto LABEL_19;
      }
      goto LABEL_24;
    }
    v14 = IpsecAllocStr(pszDest);
    *((_QWORD *)v5 + 2) = v14;
    if ( !v14 )
    {
      v6 = 8;
      v7 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_20;
        v10 = 14;
LABEL_19:
        WPP_SF_d(v8[2], v10, WPP_23b1f3110213325002571ebd730d21df_Traceguids, v6);
        v8 = WPP_GLOBAL_Control;
LABEL_20:
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
          WPP_SF__guid_(v8[2], 15, WPP_23b1f3110213325002571ebd730d21df_Traceguids, v9);
        if ( !v5 )
          goto LABEL_25;
      }
LABEL_24:
      PAFreeMMPolicyState(v5);
      goto LABEL_25;
    }
  }
  result = 0;
  *(_OWORD *)((char *)v5 + 24) = *(_OWORD *)(v9 + 32);
  v16 = *(_OWORD *)(v9 + 16);
  *((_DWORD *)v5 + 14) = 0;
  *(_QWORD *)((char *)v5 + 60) = 1;
  *(_OWORD *)((char *)v5 + 40) = v16;
  *((_DWORD *)v5 + 17) = 0;
  *((_QWORD *)v5 + 9) = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180028884  mov     [rsp+arg_10], rbx
0x180028889  mov     [rsp+arg_18], rbp
0x18002888e  push    rsi
0x18002888f  push    rdi
0x180028890  push    r12
0x180028892  push    r14
0x180028894  push    r15
0x180028896  sub     rsp, 430h
0x18002889d  mov     rax, cs:__security_cookie
0x1800288a4  xor     rax, rsp
0x1800288a7  mov     [rsp+458h+var_38], rax
0x1800288af  mov     rsi, rcx
0x1800288b2  mov     r14, rdx
0x1800288b5  mov     ecx, 50h ; 'P'
0x1800288ba  call    IpsecAllocMem
0x1800288bf  xor     r15d, r15d
0x1800288c2  lea     r12, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x1800288c9  mov     rbx, rax
0x1800288cc  test    rax, rax
0x1800288cf  jnz     short loc_180028904
0x1800288d1  lea     r9d, [rax+8]
0x1800288d5  mov     ebp, r9d
0x1800288d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288df  lea     rdi, WPP_GLOBAL_Control
0x1800288e6  cmp     rcx, rdi
0x1800288e9  jz      loc_180028A26
0x1800288ef  test    byte ptr [rcx+1Ch], 10h
0x1800288f3  mov     esi, r15d
0x1800288f6  jz      loc_1800289FA
0x1800288fc  lea     edx, [rax+0Bh]
0x1800288ff  jmp     loc_1800289E7
0x180028904  mov     rsi, [rsi+68h]
0x180028908  movups  xmm0, xmmword ptr [rsi]
0x18002890b  movdqu  xmmword ptr [rax], xmm0
0x18002890f  mov     rcx, [rsi+48h]; unsigned __int16 *
0x180028913  test    rcx, rcx
0x180028916  jz      short loc_180028960
0x180028918  cmp     [rcx], r15w
0x18002891c  jz      short loc_180028960
0x18002891e  call    IpsecAllocStr
0x180028923  mov     [rbx+10h], rax
0x180028927  test    rax, rax
0x18002892a  jnz     loc_180028A2D
0x180028930  lea     r9d, [rax+8]
0x180028934  mov     ebp, r9d
0x180028937  mov     rcx, cs:WPP_GLOBAL_Control
0x18002893e  lea     rdi, WPP_GLOBAL_Control
0x180028945  cmp     rcx, rdi
0x180028948  jz      loc_180028A1E
0x18002894e  test    byte ptr [rcx+1Ch], 10h
0x180028952  jz      loc_1800289FA
0x180028958  lea     edx, [rax+0Ch]
0x18002895b  jmp     loc_1800289E7
0x180028960  mov     r9d, cs:gdwQMPolicyCounter
0x180028967  lea     r8, aD; "%d"
0x18002896e  inc     r9d
0x180028971  lea     rcx, [rsp+458h+pszDest]; pszDest
0x180028976  mov     edx, 200h; cchDest
0x18002897b  mov     cs:gdwQMPolicyCounter, r9d
0x180028982  call    StringCchPrintfW
0x180028987  movzx   ebp, ax
0x18002898a  test    ebp, ebp
0x18002898c  jz      short loc_1800289B1
0x18002898e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028995  lea     rdi, WPP_GLOBAL_Control
0x18002899c  cmp     rcx, rdi
0x18002899f  jz      short loc_180028A1E
0x1800289a1  test    byte ptr [rcx+1Ch], 10h
0x1800289a5  jz      short loc_1800289FA
0x1800289a7  mov     edx, 0Dh
0x1800289ac  mov     r9d, ebp
0x1800289af  jmp     short loc_1800289E7
0x1800289b1  lea     rcx, [rsp+458h+pszDest]; unsigned __int16 *
0x1800289b6  call    IpsecAllocStr
0x1800289bb  mov     [rbx+10h], rax
0x1800289bf  test    rax, rax
0x1800289c2  jnz     short loc_180028A2D
0x1800289c4  lea     r9d, [rax+8]
0x1800289c8  mov     ebp, r9d
0x1800289cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289d2  lea     rdi, WPP_GLOBAL_Control
0x1800289d9  cmp     rcx, rdi
0x1800289dc  jz      short loc_180028A1E
0x1800289de  test    byte ptr [rcx+1Ch], 10h
0x1800289e2  jz      short loc_1800289FA
0x1800289e4  lea     edx, [rax+0Eh]
0x1800289e7  mov     rcx, [rcx+10h]
0x1800289eb  mov     r8, r12
0x1800289ee  call    WPP_SF_d
0x1800289f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289fa  cmp     rcx, rdi
0x1800289fd  jz      short loc_180028A19
0x1800289ff  test    byte ptr [rcx+1Ch], 10h
0x180028a03  jz      short loc_180028A19
0x180028a05  mov     rcx, [rcx+10h]
0x180028a09  mov     edx, 0Fh
0x180028a0e  mov     r9, rsi
0x180028a11  mov     r8, r12
0x180028a14  call    WPP_SF__guid_
0x180028a19  test    rbx, rbx
0x180028a1c  jz      short loc_180028A26
0x180028a1e  mov     rcx, rbx; lpMem
0x180028a21  call    PAFreeMMPolicyState
0x180028a26  mov     [r14], r15
0x180028a29  mov     eax, ebp
0x180028a2b  jmp     short loc_180028A58
0x180028a2d  movups  xmm0, xmmword ptr [rsi+20h]
0x180028a31  xor     eax, eax
0x180028a33  movdqu  xmmword ptr [rbx+18h], xmm0
0x180028a38  movups  xmm1, xmmword ptr [rsi+10h]
0x180028a3c  mov     [rbx+38h], r15d
0x180028a40  mov     qword ptr [rbx+3Ch], 1
0x180028a48  movdqu  xmmword ptr [rbx+28h], xmm1
0x180028a4d  mov     [rbx+44h], r15d
0x180028a51  mov     [rbx+48h], r15
0x180028a55  mov     [r14], rbx
0x180028a58  mov     rcx, [rsp+458h+var_38]
0x180028a60  xor     rcx, rsp; StackCookie
0x180028a63  call    __security_check_cookie
0x180028a68  lea     r11, [rsp+458h+var_28]
0x180028a70  mov     rbx, [r11+40h]
0x180028a74  mov     rbp, [r11+48h]
0x180028a78  mov     rsp, r11
0x180028a7b  pop     r15
0x180028a7d  pop     r14
0x180028a7f  pop     r12
0x180028a81  pop     rdi
0x180028a82  pop     rsi
0x180028a83  retn
```
