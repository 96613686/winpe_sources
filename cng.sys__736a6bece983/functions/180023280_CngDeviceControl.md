# CngDeviceControl

- ea: `0x180023280`
- end: `0x180023617`
- name: `CngDeviceControl`
- size: `919`
- prototype: `__int64 __fastcall(void *, unsigned int, _QWORD *, unsigned int *, unsigned int, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023140`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18000dbf0`
- `0x180018150`
- `0x180023280`
- `0x180023620`
- `0x18005d670`
- `0x18005dc98`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!SeAuditFipsCryptoSelftests` at `0x1800a2422`
- `ntoskrnl!SeAuditFipsCryptoSelftests` at `0x1800a2422`

## string_xrefs

- `0x18002340f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18002346b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18002349e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800235fc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800a246e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

## pseudocode

```c
__int64 __fastcall CngDeviceControl(void *a1, unsigned int a2, _QWORD *a3, unsigned int *a4, unsigned int a5, char a6)
{
  _QWORD *v7; // rsi
  __int64 result; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // esi
  __int64 v13; // r9

  v7 = a3;
  if ( a5 == 3736576 )
    return ConfigIoHandler_Safeguarded(a1, a2);
  if ( a5 != 3735678 )
  {
    LODWORD(a3) = 128;
    switch ( a5 )
    {
      case 0x390004u:
      case 0x390008u:
        if ( !v7 || !a4 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              a2,
              128,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
              15);
          return 3221225485LL;
        }
        if ( a2 < *a4 )
          memset((char *)v7 + a2, 0, *a4 - a2);
        if ( !(unsigned int)SystemPrng(v7) )
        {
          DebugTraceError(
            3221225473LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
            1311);
          return 3221225473LL;
        }
        return 0;
      case 0x39000Eu:
      case 0x390012u:
      case 0x390016u:
      case 0x39001Au:
      case 0x39001Eu:
      case 0x390022u:
      case 0x39007Au:
        break;
      case 0x390024u:
        if ( a6 )
        {
          DebugTraceError(
            3221225506LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
            1395);
          return 3221225506LL;
        }
        if ( *a4 < 0x80 )
        {
          if ( *a4 < 0x50 )
          {
            v11 = -1073741789;
LABEL_62:
            if ( !a4 )
              return v11;
            goto LABEL_63;
          }
          LODWORD(a3) = 80;
          *v7 = FipsDesKey;
          v7[1] = FipsDes;
          v7[2] = Fips3Des3Key;
          v7[3] = Fips3Des;
          v7[4] = FipsSHAInit;
          v7[5] = FipsHmacSHAUpdate;
          v7[6] = FipsSHAFinal;
          v7[7] = &FipsCBC;
          v7[8] = FIPSGenRandom;
          v7[9] = FipsBlockCBC;
        }
        else
        {
          *v7 = FipsDesKey;
          v7[1] = FipsDes;
          v7[2] = Fips3Des3Key;
          v7[3] = Fips3Des;
          v7[4] = FipsSHAInit;
          v7[5] = FipsHmacSHAUpdate;
          v7[6] = FipsSHAFinal;
          v7[7] = &FipsCBC;
          v7[8] = FIPSGenRandom;
          v7[9] = FipsBlockCBC;
          v7[10] = &FipsHmacSHAInit;
          v7[11] = FipsHmacSHAUpdate;
          v7[12] = &FipsHmacSHAFinal;
          v7[13] = &HmacMD5Init;
          v7[14] = HmacMD5Update;
          v7[15] = &HmacMD5Final;
        }
        *a4 = (unsigned int)a3;
        return 0;
      case 0x390040u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, off_1800A9220);
      case 0x390044u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &off_1800A9070);
      case 0x390048u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &off_1800A90C0);
      case 0x390064u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &qword_1800A90D0);
      case 0x390073u:
        if ( a4 && *a4 || a1 || a2 )
        {
          v13 = 1502;
          goto LABEL_79;
        }
        if ( !g_fSelftest )
          return (unsigned int)-1073741244;
        LOBYTE(a1) = 1;
        goto LABEL_69;
      case 0x390074u:
        if ( a4 && *a4 || !a1 || a2 != 4 )
        {
          v13 = 1520;
          goto LABEL_79;
        }
        if ( g_fSelftest )
        {
          a1 = 0;
LABEL_69:
          SeAuditFipsCryptoSelftests(a1);
          return 0;
        }
        else
        {
          return (unsigned int)-1073741244;
        }
      case 0x390084u:
        if ( a4 && *a4 == 8 && v7 )
        {
          *v7 = g_selftestDuration;
          return 0;
        }
        v13 = 1533;
LABEL_79:
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx", v13);
        return 3221225485LL;
      default:
        v11 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, 128, a5);
        goto LABEL_62;
    }
  }
  if ( v7 && a4 )
  {
    if ( a2 < *a4 )
      memset((char *)v7 + a2, 0, *a4 - a2);
    v9 = 1;
    if ( a5 == 3735574 || (v10 = 0, a5 == 3735578) )
      v10 = 1;
    if ( ((a5 - 3735582) & 0xFFFFFFFB) == 0 )
      v10 = 2;
    if ( ((a5 - 3735674) & 0xFFFFFFFB) == 0 )
      v10 = 4;
    if ( ((a5 - 3735570) & 0xFFFFFFE7) == 0 && a5 != 3735594 || a5 == 3735678 )
      v9 = 0;
    result = CngEncryptMemoryEx(v7, *a4, v9, v10);
    v11 = result;
    if ( (int)result >= 0 )
      return result;
    DebugTraceError(
      (unsigned int)result,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
      1380);
LABEL_63:
    *a4 = 0;
    return v11;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
      51);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180023280  mov     [rsp+arg_8], rbx
0x180023285  mov     [rsp+arg_10], rsi
0x18002328a  push    rdi
0x18002328b  sub     rsp, 40h
0x18002328f  mov     ebx, [rsp+48h+arg_20]
0x180023293  mov     rdi, r9
0x180023296  mov     rsi, r8
0x180023299  mov     r10, rcx
0x18002329c  cmp     ebx, 390400h
0x1800232a2  jnz     short loc_1800232BA
0x1800232a4  call    ConfigIoHandler_Safeguarded
0x1800232a9  mov     rbx, [rsp+48h+arg_8]
0x1800232ae  mov     rsi, [rsp+48h+arg_10]
0x1800232b3  add     rsp, 40h
0x1800232b7  pop     rdi
0x1800232b8  retn
0x1800232ba  mov     [rsp+48h+arg_0], rbp
0x1800232bf  cmp     ebx, 39007Eh
0x1800232c5  jnz     loc_18002336C
0x1800232cb  test    rsi, rsi; jumptable 000000018002339C cases 3735566,3735570,3735574,3735578,3735582,3735586,3735674
0x1800232ce  jz      loc_1800233E9
0x1800232d4  test    rdi, rdi
0x1800232d7  jz      loc_1800233E9
0x1800232dd  mov     eax, [rdi]
0x1800232df  cmp     edx, eax
0x1800232e1  jb      loc_1800235CA
0x1800232e7  xor     ebp, ebp
0x1800232e9  mov     r8d, 1
0x1800232ef  cmp     ebx, 390016h
0x1800232f5  jz      loc_180023439
0x1800232fb  mov     r9d, ebp
0x1800232fe  cmp     ebx, 39001Ah
0x180023304  jz      loc_180023439
0x18002330a  lea     eax, [rbx-39001Eh]
0x180023310  test    eax, 0FFFFFFFBh
0x180023315  jz      loc_1800235E0
0x18002331b  lea     eax, [rbx-39007Ah]
0x180023321  test    eax, 0FFFFFFFBh
0x180023326  jz      loc_1800235EB
0x18002332c  lea     eax, [rbx-390012h]
0x180023332  test    eax, 0FFFFFFE7h
0x180023337  jnz     short loc_180023346
0x180023339  cmp     ebx, 39002Ah
0x18002333f  jz      short loc_180023346
0x180023341  mov     r8d, ebp
0x180023344  jmp     short loc_18002334E
0x180023346  cmp     ebx, 39007Eh
0x18002334c  jz      short loc_180023341
0x18002334e  mov     edx, [rdi]
0x180023350  mov     rcx, rsi
0x180023353  call    CngEncryptMemoryEx
0x180023358  mov     esi, eax
0x18002335a  test    eax, eax
0x18002335c  js      loc_1800235F6
0x180023362  mov     rbp, [rsp+48h+arg_0]
0x180023367  jmp     loc_1800232A9
0x18002336c  lea     eax, [rbx-390004h]; switch 129 cases
0x180023372  mov     r8d, 80h
0x180023378  cmp     eax, r8d
0x18002337b  ja      def_18002339C; jumptable 000000018002339C default case, cases 3735557-3735559,3735561-3735565,3735567-3735569,3735571-3735573,3735575-3735577,3735579-3735581,3735583-3735585,3735587,3735589-3735615,3735617-3735619,3735621-3735623,3735625-3735651,3735653-3735666,3735669-3735673,3735675-3735683
0x180023381  lea     r9, cs:180000000h
0x180023388  movzx   eax, ds:(byte_1800C277C - 180000000h)[r9+rax]
0x180023391  mov     ecx, ds:(jpt_18002339C - 180000000h)[r9+rax*4]
0x180023399  add     rcx, r9
0x18002339c  jmp     rcx; switch jump
0x1800233a2  test    rsi, rsi; jumptable 000000018002339C cases 3735556,3735560
0x1800233a5  jz      loc_180023441
0x1800233ab  test    rdi, rdi
0x1800233ae  jz      loc_180023441
0x1800233b4  mov     eax, [rdi]
0x1800233b6  cmp     edx, eax
0x1800233b8  jnb     short loc_1800233CB
0x1800233ba  sub     eax, edx
0x1800233bc  mov     ecx, edx
0x1800233be  mov     r8d, eax; Size
0x1800233c1  add     rcx, rsi; void *
0x1800233c4  xor     edx, edx; Val
0x1800233c6  call    memset
0x1800233cb  mov     edx, [rdi]
0x1800233cd  mov     rcx, rsi; void *
0x1800233d0  call    SystemPrng
0x1800233d5  test    eax, eax
0x1800233d7  jz      loc_180023465
0x1800233dd  mov     rbp, [rsp+48h+arg_0]
0x1800233e2  xor     eax, eax
0x1800233e4  jmp     loc_1800232A9
0x1800233e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233f0  lea     rax, WPP_GLOBAL_Control
0x1800233f7  cmp     rcx, rax
0x1800233fa  jz      short loc_18002342F
0x1800233fc  mov     eax, [rcx+2Ch]
0x1800233ff  test    al, 1
0x180023401  jz      short loc_18002342F
0x180023403  mov     [rsp+48h+var_18], 533h
0x18002340b  mov     rcx, [rcx+18h]
0x18002340f  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023416  mov     [rsp+48h+var_20], rax
0x18002341b  lea     r9, aStatus; "Status"
0x180023422  mov     [rsp+48h+var_28], 0C000000Dh
0x18002342a  call    WPP_SF_sDsd
0x18002342f  mov     eax, 0C000000Dh
0x180023434  jmp     loc_180023362
0x180023439  mov     r9d, r8d
0x18002343c  jmp     loc_18002330A
0x180023441  mov     rcx, cs:WPP_GLOBAL_Control
0x180023448  lea     rax, WPP_GLOBAL_Control
0x18002344f  cmp     rcx, rax
0x180023452  jz      short loc_18002342F
0x180023454  mov     eax, [rcx+2Ch]
0x180023457  test    al, 1
0x180023459  jz      short loc_18002342F
0x18002345b  mov     [rsp+48h+var_18], 50Fh
0x180023463  jmp     short loc_18002340B
0x180023465  mov     r9d, 51Fh
0x18002346b  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023472  lea     rdx, aStatus; "Status"
0x180023479  mov     ecx, 0C0000001h
0x18002347e  call    DebugTraceError
0x180023483  mov     eax, 0C0000001h
0x180023488  jmp     loc_180023362
0x18002348d  cmp     [rsp+48h+arg_28], 0; jumptable 000000018002339C case 3735588
0x180023492  jz      loc_1800A22BC
0x180023498  mov     r9d, 573h
0x18002349e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800234a5  lea     rdx, aStatus; "Status"
0x1800234ac  mov     ecx, 0C0000022h
0x1800234b1  call    DebugTraceError
0x1800234b6  mov     eax, 0C0000022h
0x1800234bb  jmp     loc_180023362
0x1800234c0  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018002339C case 3735616
0x1800234c6  lea     r9, off_1800A9220; void *
0x1800234cd  mov     rdx, rdi; unsigned int *
0x1800234d0  mov     rcx, rsi; void *
0x1800234d3  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x1800234d8  jmp     loc_180023362
0x1800234dd  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018002339C case 3735652
0x1800234e3  lea     r9, qword_1800A90D0; void *
0x1800234ea  mov     rdx, rdi; unsigned int *
0x1800234ed  mov     rcx, rsi; void *
0x1800234f0  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x1800234f5  jmp     loc_180023362
0x1800234fa  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018002339C case 3735620
0x180023500  lea     r9, off_1800A9070; void *
0x180023507  mov     rdx, rdi; unsigned int *
0x18002350a  mov     rcx, rsi; void *
0x18002350d  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180023512  jmp     loc_180023362
0x180023517  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018002339C case 3735624
0x18002351d  lea     r9, off_1800A90C0; void *
0x180023524  mov     rdx, rdi; unsigned int *
0x180023527  mov     rcx, rsi; void *
0x18002352a  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x18002352f  jmp     loc_180023362
0x180023534  test    rdi, rdi; jumptable 000000018002339C case 3735667
0x180023537  jz      loc_1800A240F
0x18002353d  cmp     dword ptr [rdi], 0
0x180023540  jz      loc_1800A240F
0x180023546  jmp     loc_1800A2437
0x18002354b  test    rdi, rdi; jumptable 000000018002339C case 3735668
0x18002354e  jz      loc_1800A243F
0x180023554  cmp     dword ptr [rdi], 0
0x180023557  jz      loc_1800A243F
0x18002355d  jmp     loc_1800A2460
0x180023562  test    rdi, rdi; jumptable 000000018002339C case 3735684
0x180023565  jz      loc_1800A2468
0x18002356b  cmp     dword ptr [rdi], 8
0x18002356e  jnz     loc_1800A2468
0x180023574  test    rsi, rsi
0x180023577  jz      loc_1800A2468
0x18002357d  mov     rax, cs:g_selftestDuration
0x180023584  mov     [rsi], rax
0x180023587  jmp     loc_1800233DD
0x18002358c  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018002339C default case, cases 3735557-3735559,3735561-3735565,3735567-3735569,3735571-3735573,3735575-3735577,3735579-3735581,3735583-3735585,3735587,3735589-3735615,3735617-3735619,3735621-3735623,3735625-3735651,3735653-3735666,3735669-3735673,3735675-3735683
0x180023593  lea     rax, WPP_GLOBAL_Control
0x18002359a  mov     esi, 0C00000BBh
0x18002359f  cmp     rcx, rax
0x1800235a2  jz      loc_1800A23FF
0x1800235a8  mov     eax, [rcx+2Ch]
0x1800235ab  test    al, 1
0x1800235ad  jz      loc_1800A23FF
0x1800235b3  mov     rcx, [rcx+18h]
0x1800235b7  mov     edx, 0Ch
0x1800235bc  mov     r9d, ebx
0x1800235bf  call    WPP_SF_D
0x1800235c4  nop
0x1800235c5  jmp     loc_1800A23FF
0x1800235ca  sub     eax, edx
0x1800235cc  mov     ecx, edx
0x1800235ce  mov     r8d, eax; Size
0x1800235d1  add     rcx, rsi; void *
0x1800235d4  xor     edx, edx; Val
0x1800235d6  call    memset
0x1800235db  jmp     loc_1800232E7
0x1800235e0  mov     r9d, 2
0x1800235e6  jmp     loc_18002331B
0x1800235eb  mov     r9d, 4
0x1800235f1  jmp     loc_18002332C
0x1800235f6  mov     r9d, 564h
0x1800235fc  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023603  lea     rdx, aStatus; "Status"
0x18002360a  mov     ecx, eax
0x18002360c  call    DebugTraceError
0x180023611  nop
0x180023612  jmp     loc_1800A2406
0x1800a22bc  mov     eax, [rdi]
0x1800a22be  cmp     eax, r8d
0x1800a22c1  jb      loc_1800A2378
0x1800a22c7  lea     rax, FipsDesKey
0x1800a22ce  mov     [rsi], rax
0x1800a22d1  lea     rax, FipsDes
0x1800a22d8  mov     [rsi+8], rax
0x1800a22dc  lea     rax, Fips3Des3Key
0x1800a22e3  mov     [rsi+10h], rax
0x1800a22e7  lea     rax, Fips3Des
0x1800a22ee  mov     [rsi+18h], rax
0x1800a22f2  lea     rax, FipsSHAInit
0x1800a22f9  mov     [rsi+20h], rax
0x1800a22fd  lea     rax, FipsHmacSHAUpdate
0x1800a2304  mov     [rsi+28h], rax
0x1800a2308  lea     rax, FipsSHAFinal
0x1800a230f  mov     [rsi+30h], rax
0x1800a2313  lea     rax, FipsCBC
0x1800a231a  mov     [rsi+38h], rax
0x1800a231e  lea     rax, FIPSGenRandom
0x1800a2325  mov     [rsi+40h], rax
0x1800a2329  lea     rax, FipsBlockCBC
0x1800a2330  mov     [rsi+48h], rax
0x1800a2334  lea     rax, FipsHmacSHAInit
0x1800a233b  mov     [rsi+50h], rax
0x1800a233f  lea     rax, FipsHmacSHAUpdate
0x1800a2346  mov     [rsi+58h], rax
0x1800a234a  lea     rax, FipsHmacSHAFinal
0x1800a2351  mov     [rsi+60h], rax
0x1800a2355  lea     rax, HmacMD5Init
0x1800a235c  mov     [rsi+68h], rax
0x1800a2360  lea     rax, HmacMD5Update
0x1800a2367  mov     [rsi+70h], rax
0x1800a236b  lea     rax, HmacMD5Final
0x1800a2372  mov     [rsi+78h], rax
0x1800a2376  jmp     short loc_1800A23F0
0x1800a2378  cmp     eax, 50h ; 'P'
0x1800a237b  jb      short loc_1800A23FA
0x1800a237d  lea     rax, FipsDesKey
0x1800a2384  mov     r8d, 50h ; 'P'
0x1800a238a  mov     [rsi], rax
0x1800a238d  lea     rax, FipsDes
0x1800a2394  mov     [rsi+8], rax
0x1800a2398  lea     rax, Fips3Des3Key
0x1800a239f  mov     [rsi+10h], rax
0x1800a23a3  lea     rax, Fips3Des
0x1800a23aa  mov     [rsi+18h], rax
0x1800a23ae  lea     rax, FipsSHAInit
0x1800a23b5  mov     [rsi+20h], rax
0x1800a23b9  lea     rax, FipsHmacSHAUpdate
0x1800a23c0  mov     [rsi+28h], rax
0x1800a23c4  lea     rax, FipsSHAFinal
0x1800a23cb  mov     [rsi+30h], rax
0x1800a23cf  lea     rax, FipsCBC
0x1800a23d6  mov     [rsi+38h], rax
0x1800a23da  lea     rax, FIPSGenRandom
0x1800a23e1  mov     [rsi+40h], rax
0x1800a23e5  lea     rax, FipsBlockCBC
0x1800a23ec  mov     [rsi+48h], rax
0x1800a23f0  mov     [rdi], r8d
0x1800a23f3  xor     eax, eax
0x1800a23f5  jmp     loc_180023362
0x1800a23fa  mov     esi, 0C0000023h
0x1800a23ff  test    rdi, rdi
0x1800a2402  jz      short loc_1800A2408
0x1800a2404  xor     ebp, ebp
0x1800a2406  mov     [rdi], ebp
0x1800a2408  mov     eax, esi
0x1800a240a  jmp     loc_180023362
0x1800a240f  test    r10, r10
0x1800a2412  jnz     short loc_1800A2437
0x1800a2414  test    edx, edx
0x1800a2416  jnz     short loc_1800A2437
0x1800a2418  cmp     cs:g_fSelftest, dl
0x1800a241e  jz      short loc_1800A2459
0x1800a2420  mov     cl, 1
0x1800a2422  call    cs:__imp_SeAuditFipsCryptoSelftests
0x1800a2429  nop     dword ptr [rax+rax+00h]
0x1800a242e  xor     ebp, ebp
0x1800a2430  mov     eax, ebp
0x1800a2432  jmp     loc_180023362
0x1800a2437  mov     r9d, 5DEh
0x1800a243d  jmp     short loc_1800A246E
0x1800a243f  test    r10, r10
0x1800a2442  jz      short loc_1800A2460
0x1800a2444  cmp     edx, 4
0x1800a2447  jnz     short loc_1800A2460
0x1800a2449  cmp     cs:g_fSelftest, 0
0x1800a2450  jz      short loc_1800A2459
0x1800a2452  mov     edx, [r10]
0x1800a2455  xor     ecx, ecx
0x1800a2457  jmp     short loc_1800A2422
0x1800a2459  mov     ebp, 0C0000244h
0x1800a245e  jmp     short loc_1800A2430
0x1800a2460  mov     r9d, 5F0h
0x1800a2466  jmp     short loc_1800A246E
  ... truncated ...
```
