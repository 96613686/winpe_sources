# MSCryptKDGetAlgProperty

- ea: `0x180043270`
- end: `0x18004346e`
- name: `MSCryptKDGetAlgProperty`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180043270`
- `0x1800a4232`

## string_xrefs

- `0x18004334d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800433bb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800433e2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004340f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004344c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDGetAlgProperty(_DWORD *a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int *a5)
{
  int v9; // edi
  int v10; // ebp
  unsigned int v11; // ebx
  __int64 v13; // r9

  v9 = *a5;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        7);
    goto LABEL_17;
  }
  if ( a1[1] != 1297301836 || *a1 != 20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        17);
    goto LABEL_17;
  }
  v10 = a1[2];
  if ( (unsigned int)(v10 - 393217) > 6 )
  {
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      286);
LABEL_17:
    v11 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        96);
    goto LABEL_11;
  }
  if ( !wcscmp_0(a2, L"KeyLengths") )
  {
    v9 = 12;
    if ( !a3 )
      goto LABEL_10;
    if ( a4 < 0xC )
      goto LABEL_25;
    switch ( v10 )
    {
      case 393217:
      case 393218:
      case 393219:
      case 393220:
      case 393221:
      case 393222:
      case 393223:
        v11 = 0;
        *a3 = 0;
        a3[1] = 0x4000;
        a3[2] = 8;
        break;
      default:
        v13 = 683;
        goto LABEL_27;
    }
  }
  else
  {
    if ( !wcscmp_0(a2, L"ObjectLength") )
    {
      v9 = 4;
      if ( !a3 )
      {
LABEL_10:
        v11 = 0;
        goto LABEL_11;
      }
      if ( a4 >= 4 )
      {
        *a3 = a1[3];
        goto LABEL_10;
      }
LABEL_25:
      v11 = -1073741789;
      goto LABEL_11;
    }
    v13 = 712;
LABEL_27:
    v11 = -1073741637;
    DebugTraceError(
      3221225659LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v13);
  }
LABEL_11:
  *a5 = v9;
  return v11;
}

```

## disassembly

```asm
0x180043270  push    rbx
0x180043272  push    rbp
0x180043273  push    rsi
0x180043274  push    rdi
0x180043275  push    r12
0x180043277  push    r14
0x180043279  push    r15
0x18004327b  sub     rsp, 40h
0x18004327f  mov     r14, [rsp+78h+arg_20]
0x180043287  mov     r12d, r9d
0x18004328a  mov     rsi, r8
0x18004328d  mov     r15, rdx
0x180043290  mov     rbx, rcx
0x180043293  mov     edi, [r14]
0x180043296  test    rcx, rcx
0x180043299  jz      loc_18004332F
0x18004329f  cmp     dword ptr [rcx+4], 4D53414Ch
0x1800432a6  jnz     loc_1800433C4
0x1800432ac  cmp     dword ptr [rcx], 14h
0x1800432af  jnz     loc_1800433C4
0x1800432b5  mov     ebp, [rcx+8]
0x1800432b8  lea     eax, [rbp-60001h]
0x1800432be  cmp     eax, 6
0x1800432c1  ja      loc_18004340F
0x1800432c7  lea     rdx, aKeylengths; "KeyLengths"
0x1800432ce  mov     rcx, r15; Str1
0x1800432d1  call    wcscmp_0
0x1800432d6  test    eax, eax
0x1800432d8  jz      short loc_180043320
0x1800432da  lea     rdx, aObjectlength; "ObjectLength"
0x1800432e1  mov     rcx, r15; Str1
0x1800432e4  call    wcscmp_0
0x1800432e9  test    eax, eax
0x1800432eb  jnz     loc_180043446
0x1800432f1  mov     edi, 4
0x1800432f6  test    rsi, rsi
0x1800432f9  jz      short loc_180043309
0x1800432fb  cmp     r12d, edi
0x1800432fe  jb      loc_18004343C
0x180043304  mov     eax, [rbx+0Ch]
0x180043307  mov     [rsi], eax
0x180043309  xor     ebx, ebx
0x18004330b  mov     [r14], edi
0x18004330e  mov     eax, ebx
0x180043310  add     rsp, 40h
0x180043314  pop     r15
0x180043316  pop     r14
0x180043318  pop     r12
0x18004331a  pop     rdi
0x18004331b  pop     rsi
0x18004331c  pop     rbp
0x18004331d  pop     rbx
0x18004331e  retn
0x180043320  mov     edi, 0Ch
0x180043325  test    rsi, rsi
0x180043328  jz      short loc_180043309
0x18004332a  jmp     loc_1800A7DF0
0x18004332f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043336  lea     rsi, WPP_GLOBAL_Control
0x18004333d  cmp     rcx, rsi
0x180043340  jz      short loc_1800433BB
0x180043342  mov     eax, [rcx+2Ch]
0x180043345  test    al, 1
0x180043347  jz      short loc_1800433BB
0x180043349  mov     rcx, [rcx+18h]
0x18004334d  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043354  mov     [rsp+78h+var_48], 107h
0x18004335c  lea     r9, aStatus; "Status"
0x180043363  mov     [rsp+78h+var_50], rbp
0x180043368  mov     [rsp+78h+var_58], 0C0000008h
0x180043370  call    WPP_SF_sDsd
0x180043375  mov     ebx, 0C0000008h
0x18004337a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043381  cmp     rcx, rsi
0x180043384  jz      short loc_18004330B
0x180043386  mov     eax, [rcx+2Ch]
0x180043389  test    al, 1
0x18004338b  jz      loc_18004330B
0x180043391  mov     rcx, [rcx+18h]
0x180043395  lea     r9, aStatus; "Status"
0x18004339c  mov     [rsp+78h+var_48], 260h
0x1800433a4  mov     [rsp+78h+var_50], rbp
0x1800433a9  mov     [rsp+78h+var_58], 0C0000008h
0x1800433b1  call    WPP_SF_sDsd
0x1800433b6  jmp     loc_18004330B
0x1800433bb  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800433c2  jmp     short loc_180043375
0x1800433c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433cb  lea     rsi, WPP_GLOBAL_Control
0x1800433d2  cmp     rcx, rsi
0x1800433d5  jz      short loc_1800433BB
0x1800433d7  mov     eax, [rcx+2Ch]
0x1800433da  test    al, 1
0x1800433dc  jz      short loc_1800433BB
0x1800433de  mov     rcx, [rcx+18h]
0x1800433e2  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800433e9  mov     [rsp+78h+var_48], 111h
0x1800433f1  lea     r9, aStatus; "Status"
0x1800433f8  mov     [rsp+78h+var_50], rbp
0x1800433fd  mov     [rsp+78h+var_58], 0C0000008h
0x180043405  call    WPP_SF_sDsd
0x18004340a  jmp     loc_180043375
0x18004340f  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043416  mov     r9d, 11Eh
0x18004341c  mov     r8, rbp
0x18004341f  lea     rdx, aStatus; "Status"
0x180043426  mov     ecx, 0C0000008h
0x18004342b  call    DebugTraceError
0x180043430  lea     rsi, WPP_GLOBAL_Control
0x180043437  jmp     loc_180043375
0x18004343c  mov     ebx, 0C0000023h
0x180043441  jmp     loc_18004330B
0x180043446  mov     r9d, 2C8h
0x18004344c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043453  mov     ecx, 0C00000BBh
0x180043458  lea     rdx, aStatus; "Status"
0x18004345f  mov     ebx, 0C00000BBh
0x180043464  call    DebugTraceError
0x180043469  jmp     loc_18004330B
0x1800a7df0  cmp     r12d, edi
0x1800a7df3  jb      loc_18004343C
0x1800a7df9  add     ebp, 0FFF9FFFFh; switch 7 cases
0x1800a7dff  cmp     ebp, 6
0x1800a7e02  ja      short def_1800A7E15; jumptable 00000001800A7E15 default case
0x1800a7e04  lea     rcx, cs:180000000h
0x1800a7e0b  mov     eax, ds:(jpt_1800A7E15 - 180000000h)[rcx+rbp*4]
0x1800a7e12  add     rax, rcx
0x1800a7e15  jmp     rax; switch jump
0x1800a7e1b  xor     ebx, ebx; jumptable 00000001800A7E15 cases 393217-393223
0x1800a7e1d  mov     [rsi], ebx
0x1800a7e1f  mov     dword ptr [rsi+4], 4000h
0x1800a7e26  mov     dword ptr [rsi+8], 8
0x1800a7e2d  jmp     loc_18004330B
0x1800a7e32  mov     r9d, 2ABh; jumptable 00000001800A7E15 default case
0x1800a7e38  jmp     loc_18004344C
```
