# MSCryptKDGetAlgProperty

- ea: `0x180039200`
- end: `0x1800393fe`
- name: `MSCryptKDGetAlgProperty`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180039200`
- `0x18009d746`

## string_xrefs

- `0x1800392dd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18003934b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180039372`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18003939f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800393dc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x180039200  push    rbx
0x180039202  push    rbp
0x180039203  push    rsi
0x180039204  push    rdi
0x180039205  push    r12
0x180039207  push    r14
0x180039209  push    r15
0x18003920b  sub     rsp, 40h
0x18003920f  mov     r14, [rsp+78h+arg_20]
0x180039217  mov     r12d, r9d
0x18003921a  mov     rsi, r8
0x18003921d  mov     r15, rdx
0x180039220  mov     rbx, rcx
0x180039223  mov     edi, [r14]
0x180039226  test    rcx, rcx
0x180039229  jz      loc_1800392BF
0x18003922f  cmp     dword ptr [rcx+4], 4D53414Ch
0x180039236  jnz     loc_180039354
0x18003923c  cmp     dword ptr [rcx], 14h
0x18003923f  jnz     loc_180039354
0x180039245  mov     ebp, [rcx+8]
0x180039248  lea     eax, [rbp-60001h]
0x18003924e  cmp     eax, 6
0x180039251  ja      loc_18003939F
0x180039257  lea     rdx, aKeylengths; "KeyLengths"
0x18003925e  mov     rcx, r15; Str1
0x180039261  call    wcscmp_0
0x180039266  test    eax, eax
0x180039268  jz      short loc_1800392B0
0x18003926a  lea     rdx, aObjectlength; "ObjectLength"
0x180039271  mov     rcx, r15; Str1
0x180039274  call    wcscmp_0
0x180039279  test    eax, eax
0x18003927b  jnz     loc_1800393D6
0x180039281  mov     edi, 4
0x180039286  test    rsi, rsi
0x180039289  jz      short loc_180039299
0x18003928b  cmp     r12d, edi
0x18003928e  jb      loc_1800393CC
0x180039294  mov     eax, [rbx+0Ch]
0x180039297  mov     [rsi], eax
0x180039299  xor     ebx, ebx
0x18003929b  mov     [r14], edi
0x18003929e  mov     eax, ebx
0x1800392a0  add     rsp, 40h
0x1800392a4  pop     r15
0x1800392a6  pop     r14
0x1800392a8  pop     r12
0x1800392aa  pop     rdi
0x1800392ab  pop     rsi
0x1800392ac  pop     rbp
0x1800392ad  pop     rbx
0x1800392ae  retn
0x1800392b0  mov     edi, 0Ch
0x1800392b5  test    rsi, rsi
0x1800392b8  jz      short loc_180039299
0x1800392ba  jmp     loc_1800A1052
0x1800392bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392c6  lea     rsi, WPP_GLOBAL_Control
0x1800392cd  cmp     rcx, rsi
0x1800392d0  jz      short loc_18003934B
0x1800392d2  mov     eax, [rcx+2Ch]
0x1800392d5  test    al, 1
0x1800392d7  jz      short loc_18003934B
0x1800392d9  mov     rcx, [rcx+18h]
0x1800392dd  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800392e4  mov     [rsp+78h+var_48], 107h
0x1800392ec  lea     r9, aStatus; "Status"
0x1800392f3  mov     [rsp+78h+var_50], rbp
0x1800392f8  mov     [rsp+78h+var_58], 0C0000008h
0x180039300  call    WPP_SF_sDsd
0x180039305  mov     ebx, 0C0000008h
0x18003930a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039311  cmp     rcx, rsi
0x180039314  jz      short loc_18003929B
0x180039316  mov     eax, [rcx+2Ch]
0x180039319  test    al, 1
0x18003931b  jz      loc_18003929B
0x180039321  mov     rcx, [rcx+18h]
0x180039325  lea     r9, aStatus; "Status"
0x18003932c  mov     [rsp+78h+var_48], 260h
0x180039334  mov     [rsp+78h+var_50], rbp
0x180039339  mov     [rsp+78h+var_58], 0C0000008h
0x180039341  call    WPP_SF_sDsd
0x180039346  jmp     loc_18003929B
0x18003934b  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039352  jmp     short loc_180039305
0x180039354  mov     rcx, cs:WPP_GLOBAL_Control
0x18003935b  lea     rsi, WPP_GLOBAL_Control
0x180039362  cmp     rcx, rsi
0x180039365  jz      short loc_18003934B
0x180039367  mov     eax, [rcx+2Ch]
0x18003936a  test    al, 1
0x18003936c  jz      short loc_18003934B
0x18003936e  mov     rcx, [rcx+18h]
0x180039372  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039379  mov     [rsp+78h+var_48], 111h
0x180039381  lea     r9, aStatus; "Status"
0x180039388  mov     [rsp+78h+var_50], rbp
0x18003938d  mov     [rsp+78h+var_58], 0C0000008h
0x180039395  call    WPP_SF_sDsd
0x18003939a  jmp     loc_180039305
0x18003939f  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800393a6  mov     r9d, 11Eh
0x1800393ac  mov     r8, rbp
0x1800393af  lea     rdx, aStatus; "Status"
0x1800393b6  mov     ecx, 0C0000008h
0x1800393bb  call    DebugTraceError
0x1800393c0  lea     rsi, WPP_GLOBAL_Control
0x1800393c7  jmp     loc_180039305
0x1800393cc  mov     ebx, 0C0000023h
0x1800393d1  jmp     loc_18003929B
0x1800393d6  mov     r9d, 2C8h
0x1800393dc  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800393e3  mov     ecx, 0C00000BBh
0x1800393e8  lea     rdx, aStatus; "Status"
0x1800393ef  mov     ebx, 0C00000BBh
0x1800393f4  call    DebugTraceError
0x1800393f9  jmp     loc_18003929B
0x1800a1052  cmp     r12d, edi
0x1800a1055  jb      loc_1800393CC
0x1800a105b  add     ebp, 0FFF9FFFFh; switch 7 cases
0x1800a1061  cmp     ebp, 6
0x1800a1064  ja      short def_1800A1077; jumptable 00000001800A1077 default case
0x1800a1066  lea     rcx, cs:180000000h
0x1800a106d  mov     eax, ds:(jpt_1800A1077 - 180000000h)[rcx+rbp*4]
0x1800a1074  add     rax, rcx
0x1800a1077  jmp     rax; switch jump
0x1800a107d  xor     ebx, ebx; jumptable 00000001800A1077 cases 393217-393223
0x1800a107f  mov     [rsi], ebx
0x1800a1081  mov     dword ptr [rsi+4], 4000h
0x1800a1088  mov     dword ptr [rsi+8], 8
0x1800a108f  jmp     loc_18003929B
0x1800a1094  mov     r9d, 2ABh; jumptable 00000001800A1077 default case
0x1800a109a  jmp     loc_1800393DC
```
