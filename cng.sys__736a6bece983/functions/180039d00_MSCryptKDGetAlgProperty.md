# MSCryptKDGetAlgProperty

- ea: `0x180039d00`
- end: `0x180039efe`
- name: `MSCryptKDGetAlgProperty`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180039d00`
- `0x18009f616`

## string_xrefs

- `0x180039ddd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180039e4b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180039e72`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180039e9f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180039edc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x180039d00  push    rbx
0x180039d02  push    rbp
0x180039d03  push    rsi
0x180039d04  push    rdi
0x180039d05  push    r12
0x180039d07  push    r14
0x180039d09  push    r15
0x180039d0b  sub     rsp, 40h
0x180039d0f  mov     r14, [rsp+78h+arg_20]
0x180039d17  mov     r12d, r9d
0x180039d1a  mov     rsi, r8
0x180039d1d  mov     r15, rdx
0x180039d20  mov     rbx, rcx
0x180039d23  mov     edi, [r14]
0x180039d26  test    rcx, rcx
0x180039d29  jz      loc_180039DBF
0x180039d2f  cmp     dword ptr [rcx+4], 4D53414Ch
0x180039d36  jnz     loc_180039E54
0x180039d3c  cmp     dword ptr [rcx], 14h
0x180039d3f  jnz     loc_180039E54
0x180039d45  mov     ebp, [rcx+8]
0x180039d48  lea     eax, [rbp-60001h]
0x180039d4e  cmp     eax, 6
0x180039d51  ja      loc_180039E9F
0x180039d57  lea     rdx, aKeylengths; "KeyLengths"
0x180039d5e  mov     rcx, r15; Str1
0x180039d61  call    wcscmp_0
0x180039d66  test    eax, eax
0x180039d68  jz      short loc_180039DB0
0x180039d6a  lea     rdx, aObjectlength; "ObjectLength"
0x180039d71  mov     rcx, r15; Str1
0x180039d74  call    wcscmp_0
0x180039d79  test    eax, eax
0x180039d7b  jnz     loc_180039ED6
0x180039d81  mov     edi, 4
0x180039d86  test    rsi, rsi
0x180039d89  jz      short loc_180039D99
0x180039d8b  cmp     r12d, edi
0x180039d8e  jb      loc_180039ECC
0x180039d94  mov     eax, [rbx+0Ch]
0x180039d97  mov     [rsi], eax
0x180039d99  xor     ebx, ebx
0x180039d9b  mov     [r14], edi
0x180039d9e  mov     eax, ebx
0x180039da0  add     rsp, 40h
0x180039da4  pop     r15
0x180039da6  pop     r14
0x180039da8  pop     r12
0x180039daa  pop     rdi
0x180039dab  pop     rsi
0x180039dac  pop     rbp
0x180039dad  pop     rbx
0x180039dae  retn
0x180039db0  mov     edi, 0Ch
0x180039db5  test    rsi, rsi
0x180039db8  jz      short loc_180039D99
0x180039dba  jmp     loc_1800A2E82
0x180039dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dc6  lea     rsi, WPP_GLOBAL_Control
0x180039dcd  cmp     rcx, rsi
0x180039dd0  jz      short loc_180039E4B
0x180039dd2  mov     eax, [rcx+2Ch]
0x180039dd5  test    al, 1
0x180039dd7  jz      short loc_180039E4B
0x180039dd9  mov     rcx, [rcx+18h]
0x180039ddd  lea     rbp, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039de4  mov     [rsp+78h+var_48], 107h
0x180039dec  lea     r9, aStatus; "Status"
0x180039df3  mov     [rsp+78h+var_50], rbp
0x180039df8  mov     [rsp+78h+var_58], 0C0000008h
0x180039e00  call    WPP_SF_sDsd
0x180039e05  mov     ebx, 0C0000008h
0x180039e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e11  cmp     rcx, rsi
0x180039e14  jz      short loc_180039D9B
0x180039e16  mov     eax, [rcx+2Ch]
0x180039e19  test    al, 1
0x180039e1b  jz      loc_180039D9B
0x180039e21  mov     rcx, [rcx+18h]
0x180039e25  lea     r9, aStatus; "Status"
0x180039e2c  mov     [rsp+78h+var_48], 260h
0x180039e34  mov     [rsp+78h+var_50], rbp
0x180039e39  mov     [rsp+78h+var_58], 0C0000008h
0x180039e41  call    WPP_SF_sDsd
0x180039e46  jmp     loc_180039D9B
0x180039e4b  lea     rbp, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039e52  jmp     short loc_180039E05
0x180039e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e5b  lea     rsi, WPP_GLOBAL_Control
0x180039e62  cmp     rcx, rsi
0x180039e65  jz      short loc_180039E4B
0x180039e67  mov     eax, [rcx+2Ch]
0x180039e6a  test    al, 1
0x180039e6c  jz      short loc_180039E4B
0x180039e6e  mov     rcx, [rcx+18h]
0x180039e72  lea     rbp, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039e79  mov     [rsp+78h+var_48], 111h
0x180039e81  lea     r9, aStatus; "Status"
0x180039e88  mov     [rsp+78h+var_50], rbp
0x180039e8d  mov     [rsp+78h+var_58], 0C0000008h
0x180039e95  call    WPP_SF_sDsd
0x180039e9a  jmp     loc_180039E05
0x180039e9f  lea     rbp, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039ea6  mov     r9d, 11Eh
0x180039eac  mov     r8, rbp
0x180039eaf  lea     rdx, aStatus; "Status"
0x180039eb6  mov     ecx, 0C0000008h
0x180039ebb  call    DebugTraceError
0x180039ec0  lea     rsi, WPP_GLOBAL_Control
0x180039ec7  jmp     loc_180039E05
0x180039ecc  mov     ebx, 0C0000023h
0x180039ed1  jmp     loc_180039D9B
0x180039ed6  mov     r9d, 2C8h
0x180039edc  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039ee3  mov     ecx, 0C00000BBh
0x180039ee8  lea     rdx, aStatus; "Status"
0x180039eef  mov     ebx, 0C00000BBh
0x180039ef4  call    DebugTraceError
0x180039ef9  jmp     loc_180039D9B
0x1800a2e82  cmp     r12d, edi
0x1800a2e85  jb      loc_180039ECC
0x1800a2e8b  add     ebp, 0FFF9FFFFh; switch 7 cases
0x1800a2e91  cmp     ebp, 6
0x1800a2e94  ja      short def_1800A2EA7; jumptable 00000001800A2EA7 default case
0x1800a2e96  lea     rcx, cs:180000000h
0x1800a2e9d  mov     eax, ds:(jpt_1800A2EA7 - 180000000h)[rcx+rbp*4]
0x1800a2ea4  add     rax, rcx
0x1800a2ea7  jmp     rax; switch jump
0x1800a2ead  xor     ebx, ebx; jumptable 00000001800A2EA7 cases 393217-393223
0x1800a2eaf  mov     [rsi], ebx
0x1800a2eb1  mov     dword ptr [rsi+4], 4000h
0x1800a2eb8  mov     dword ptr [rsi+8], 8
0x1800a2ebf  jmp     loc_180039D9B
0x1800a2ec4  mov     r9d, 2ABh; jumptable 00000001800A2EA7 default case
0x1800a2eca  jmp     loc_180039EDC
```
