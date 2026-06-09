# PACreateEmptyMMFilter

- ea: `0x180028cd8`
- end: `0x180028f46`
- name: `PACreateEmptyMMFilter`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002a4bc`

## callees

- `0x180006f00`
- `0x18000964c`
- `0x18000c828`
- `0x18000e510`
- `0x18001cc50`
- `0x180028cd8`
- `0x180029418`
- `0x180029504`
- `0x1800441a4`
- `0x18004d090`

## pseudocode

```c
__int64 __fastcall PACreateEmptyMMFilter(int a1, _OWORD *a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v6; // r15d
  unsigned int v10; // eax
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  char *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r9
  char *v16; // rax
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rax
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax
  __int64 result; // rax
  wchar_t pszDest[512]; // [rsp+30h] [rbp-458h] BYREF

  v6 = *(_DWORD *)(a3 + 76);
  v10 = ValidateIpsecFilterSpec(a4);
  v11 = v10;
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v13 = 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_10;
      v14 = 16;
      v15 = v10;
      goto LABEL_5;
    }
LABEL_30:
    *a5 = 0;
    return v11;
  }
  v16 = (char *)IpsecAllocMem(0xA8u);
  v13 = v16;
  if ( !v16 )
  {
    v11 = 8;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_30;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_94fccf207eb13dd497c8568c00b6a40a_Traceguids, 8);
      v12 = WPP_GLOBAL_Control;
    }
LABEL_10:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      WPP_SF__guid_D(v12[2], 21, WPP_94fccf207eb13dd497c8568c00b6a40a_Traceguids, a4 + 24, v11);
    if ( !v13 )
      goto LABEL_30;
    goto LABEL_14;
  }
  *(_DWORD *)v16 = a1;
  *(_OWORD *)(v16 + 4) = *(_OWORD *)(a4 + 24);
  v17 = *(unsigned __int16 **)(a4 + 16);
  if ( !v17 || !*v17 )
  {
    ++gdwMMFilterCounter;
    v19 = StringCchPrintfW(pszDest, 0x200u, L"%d");
    v11 = v19;
    if ( v19 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_14;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_10;
      v14 = 19;
    }
    else
    {
      v20 = IpsecAllocStr(pszDest);
      *((_QWORD *)v13 + 3) = v20;
      if ( v20 )
        goto LABEL_31;
      v11 = 8;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_14;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_10;
      v14 = 20;
    }
LABEL_21:
    v15 = v11;
LABEL_5:
    WPP_SF_d(v12[2], v14, WPP_94fccf207eb13dd497c8568c00b6a40a_Traceguids, v15);
    v12 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v18 = IpsecAllocStr(v17);
  *((_QWORD *)v13 + 3) = v18;
  if ( !v18 )
  {
    v11 = 8;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_10;
      v14 = 18;
      goto LABEL_21;
    }
LABEL_14:
    PAFreeTxFilter(v13);
    goto LABEL_30;
  }
LABEL_31:
  PASetInterfaceType(*(unsigned int *)(a3 + 40), v13 + 32);
  *((_DWORD *)v13 + 10) = 0;
  if ( (v6 & 3) != 0 )
    *((_DWORD *)v13 + 10) = 256;
  *(_QWORD *)(v13 + 44) = 0;
  result = 0;
  *(_OWORD *)(v13 + 68) = *a2;
  *(_OWORD *)(v13 + 52) = *(_OWORD *)(a3 + 8);
  *a5 = v13;
  return result;
}

```

## disassembly

```asm
0x180028cd8  push    rbx
0x180028cda  push    rbp
0x180028cdb  push    rsi
0x180028cdc  push    rdi
0x180028cdd  push    r12
0x180028cdf  push    r13
0x180028ce1  push    r14
0x180028ce3  push    r15
0x180028ce5  sub     rsp, 448h
0x180028cec  mov     rax, cs:__security_cookie
0x180028cf3  xor     rax, rsp
0x180028cf6  mov     [rsp+488h+var_58], rax
0x180028cfe  mov     r12, [rsp+488h+arg_20]
0x180028d06  mov     ebp, ecx
0x180028d08  mov     r15d, [r8+4Ch]
0x180028d0c  mov     rcx, r9
0x180028d0f  mov     r13, r9
0x180028d12  mov     rdi, r8
0x180028d15  mov     r14, rdx
0x180028d18  call    ValidateIpsecFilterSpec
0x180028d1d  mov     esi, eax
0x180028d1f  test    eax, eax
0x180028d21  jz      short loc_180028D63
0x180028d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d2a  lea     rdi, WPP_GLOBAL_Control
0x180028d31  xor     ebp, ebp
0x180028d33  cmp     rcx, rdi
0x180028d36  jz      loc_180028EE2
0x180028d3c  test    byte ptr [rcx+1Ch], 10h
0x180028d40  mov     ebx, ebp
0x180028d42  jz      short loc_180028DB4
0x180028d44  lea     edx, [rbp+10h]
0x180028d47  mov     r9d, eax
0x180028d4a  mov     rcx, [rcx+10h]
0x180028d4e  lea     r8, WPP_94fccf207eb13dd497c8568c00b6a40a_Traceguids
0x180028d55  call    WPP_SF_d
0x180028d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d61  jmp     short loc_180028DB4
0x180028d63  mov     ecx, 0A8h
0x180028d68  call    IpsecAllocMem
0x180028d6d  mov     rbx, rax
0x180028d70  test    rax, rax
0x180028d73  jnz     short loc_180028DF2
0x180028d75  lea     esi, [rax+8]
0x180028d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d7f  lea     rdi, WPP_GLOBAL_Control
0x180028d86  cmp     rcx, rdi
0x180028d89  jz      loc_180028EE0
0x180028d8f  test    byte ptr [rcx+1Ch], 10h
0x180028d93  jz      short loc_180028DB2
0x180028d95  mov     rcx, [rcx+10h]
0x180028d99  lea     edx, [rax+11h]
0x180028d9c  mov     r9d, esi
0x180028d9f  lea     r8, WPP_94fccf207eb13dd497c8568c00b6a40a_Traceguids
0x180028da6  call    WPP_SF_d
0x180028dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180028db2  xor     ebp, ebp
0x180028db4  cmp     rcx, rdi
0x180028db7  jz      short loc_180028DDC
0x180028db9  test    byte ptr [rcx+1Ch], 8
0x180028dbd  jz      short loc_180028DDC
0x180028dbf  mov     rcx, [rcx+10h]
0x180028dc3  lea     r9, [r13+18h]
0x180028dc7  mov     edx, 15h
0x180028dcc  mov     [rsp+488h+var_468], esi
0x180028dd0  lea     r8, WPP_94fccf207eb13dd497c8568c00b6a40a_Traceguids
0x180028dd7  call    WPP_SF__guid_D
0x180028ddc  test    rbx, rbx
0x180028ddf  jz      loc_180028EE2
0x180028de5  mov     rcx, rbx; lpMem
0x180028de8  call    PAFreeTxFilter
0x180028ded  jmp     loc_180028EE2
0x180028df2  mov     [rax], ebp
0x180028df4  xor     ebp, ebp
0x180028df6  movups  xmm0, xmmword ptr [r13+18h]
0x180028dfb  movdqu  xmmword ptr [rax+4], xmm0
0x180028e00  mov     rcx, [r13+10h]; unsigned __int16 *
0x180028e04  test    rcx, rcx
0x180028e07  jz      short loc_180028E4B
0x180028e09  cmp     [rcx], bp
0x180028e0c  jz      short loc_180028E4B
0x180028e0e  call    IpsecAllocStr
0x180028e13  mov     [rbx+18h], rax
0x180028e17  test    rax, rax
0x180028e1a  jnz     loc_180028EEA
0x180028e20  lea     esi, [rbp+8]
0x180028e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e2a  lea     rdi, WPP_GLOBAL_Control
0x180028e31  cmp     rcx, rdi
0x180028e34  jz      short loc_180028DE5
0x180028e36  test    byte ptr [rcx+1Ch], 10h
0x180028e3a  jz      loc_180028DB4
0x180028e40  lea     edx, [rbp+12h]
0x180028e43  mov     r9d, esi
0x180028e46  jmp     loc_180028D4A
0x180028e4b  mov     r9d, cs:gdwMMFilterCounter
0x180028e52  lea     r8, aD; "%d"
0x180028e59  inc     r9d
0x180028e5c  lea     rcx, [rsp+488h+pszDest]; pszDest
0x180028e61  mov     edx, 200h; cchDest
0x180028e66  mov     cs:gdwMMFilterCounter, r9d
0x180028e6d  call    StringCchPrintfW
0x180028e72  movzx   esi, ax
0x180028e75  test    esi, esi
0x180028e77  jz      short loc_180028EA1
0x180028e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e80  lea     rdi, WPP_GLOBAL_Control
0x180028e87  cmp     rcx, rdi
0x180028e8a  jz      loc_180028DE5
0x180028e90  test    byte ptr [rcx+1Ch], 10h
0x180028e94  jz      loc_180028DB4
0x180028e9a  mov     edx, 13h
0x180028e9f  jmp     short loc_180028E43
0x180028ea1  lea     rcx, [rsp+488h+pszDest]; unsigned __int16 *
0x180028ea6  call    IpsecAllocStr
0x180028eab  mov     [rbx+18h], rax
0x180028eaf  test    rax, rax
0x180028eb2  jnz     short loc_180028EEA
0x180028eb4  lea     esi, [rax+8]
0x180028eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ebe  lea     rdi, WPP_GLOBAL_Control
0x180028ec5  cmp     rcx, rdi
0x180028ec8  jz      loc_180028DE5
0x180028ece  test    byte ptr [rcx+1Ch], 10h
0x180028ed2  jz      loc_180028DB4
0x180028ed8  lea     edx, [rax+14h]
0x180028edb  jmp     loc_180028E43
0x180028ee0  xor     ebp, ebp
0x180028ee2  mov     [r12], rbp
0x180028ee6  mov     eax, esi
0x180028ee8  jmp     short loc_180028F22
0x180028eea  mov     ecx, [rdi+28h]
0x180028eed  lea     rdx, [rbx+20h]
0x180028ef1  call    PASetInterfaceType
0x180028ef6  mov     [rbx+28h], ebp
0x180028ef9  test    r15b, 3
0x180028efd  jz      short loc_180028F06
0x180028eff  mov     dword ptr [rbx+28h], 100h
0x180028f06  mov     [rbx+2Ch], rbp
0x180028f0a  xor     eax, eax
0x180028f0c  movups  xmm0, xmmword ptr [r14]
0x180028f10  movdqu  xmmword ptr [rbx+44h], xmm0
0x180028f15  movups  xmm1, xmmword ptr [rdi+8]
0x180028f19  movdqu  xmmword ptr [rbx+34h], xmm1
0x180028f1e  mov     [r12], rbx
0x180028f22  mov     rcx, [rsp+488h+var_58]
0x180028f2a  xor     rcx, rsp; StackCookie
0x180028f2d  call    __security_check_cookie
0x180028f32  add     rsp, 448h
0x180028f39  pop     r15
0x180028f3b  pop     r14
0x180028f3d  pop     r13
0x180028f3f  pop     r12
0x180028f41  pop     rdi
0x180028f42  pop     rsi
0x180028f43  pop     rbp
0x180028f44  pop     rbx
0x180028f45  retn
```
