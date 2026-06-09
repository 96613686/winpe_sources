# CngDeviceControl

- ea: `0x1800302f0`
- end: `0x180030687`
- name: `CngDeviceControl`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800301b0`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180017d10`
- `0x1800251d0`
- `0x1800302f0`
- `0x180030690`
- `0x180066f50`
- `0x180067578`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!SeAuditFipsCryptoSelftests` at `0x1800a760a`
- `ntoskrnl!SeAuditFipsCryptoSelftests` at `0x1800a760a`

## string_xrefs

- `0x18003047f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800304db`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18003050e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18003066c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800a7656`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

## pseudocode

```c
__int64 __fastcall CngDeviceControl(void *a1, unsigned int a2, _QWORD *a3, unsigned int *a4, unsigned int a5, char a6)
{
  _QWORD *v7; // rsi
  __int64 result; // rax
  int v9; // r8d
  int v10; // r9d
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
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, off_1800AE810);
      case 0x390044u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &off_1800AE660);
      case 0x390048u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &off_1800AE6B0);
      case 0x390064u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &qword_1800AE6C0);
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
    result = CngEncryptMemoryEx((char *)v7, *a4, v9, v10);
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
0x1800302f0  mov     [rsp+arg_8], rbx
0x1800302f5  mov     [rsp+arg_10], rsi
0x1800302fa  push    rdi
0x1800302fb  sub     rsp, 40h
0x1800302ff  mov     ebx, [rsp+48h+arg_20]
0x180030303  mov     rdi, r9
0x180030306  mov     rsi, r8
0x180030309  mov     r10, rcx
0x18003030c  cmp     ebx, 390400h
0x180030312  jnz     short loc_18003032A
0x180030314  call    ConfigIoHandler_Safeguarded
0x180030319  mov     rbx, [rsp+48h+arg_8]
0x18003031e  mov     rsi, [rsp+48h+arg_10]
0x180030323  add     rsp, 40h
0x180030327  pop     rdi
0x180030328  retn
0x18003032a  mov     [rsp+48h+arg_0], rbp
0x18003032f  cmp     ebx, 39007Eh
0x180030335  jnz     loc_1800303DC
0x18003033b  test    rsi, rsi; jumptable 000000018003040C cases 3735566,3735570,3735574,3735578,3735582,3735586,3735674
0x18003033e  jz      loc_180030459
0x180030344  test    rdi, rdi
0x180030347  jz      loc_180030459
0x18003034d  mov     eax, [rdi]
0x18003034f  cmp     edx, eax
0x180030351  jb      loc_18003063A
0x180030357  xor     ebp, ebp
0x180030359  mov     r8d, 1
0x18003035f  cmp     ebx, 390016h
0x180030365  jz      loc_1800304A9
0x18003036b  mov     r9d, ebp
0x18003036e  cmp     ebx, 39001Ah
0x180030374  jz      loc_1800304A9
0x18003037a  lea     eax, [rbx-39001Eh]
0x180030380  test    eax, 0FFFFFFFBh
0x180030385  jz      loc_180030650
0x18003038b  lea     eax, [rbx-39007Ah]
0x180030391  test    eax, 0FFFFFFFBh
0x180030396  jz      loc_18003065B
0x18003039c  lea     eax, [rbx-390012h]
0x1800303a2  test    eax, 0FFFFFFE7h
0x1800303a7  jnz     short loc_1800303B6
0x1800303a9  cmp     ebx, 39002Ah
0x1800303af  jz      short loc_1800303B6
0x1800303b1  mov     r8d, ebp
0x1800303b4  jmp     short loc_1800303BE
0x1800303b6  cmp     ebx, 39007Eh
0x1800303bc  jz      short loc_1800303B1
0x1800303be  mov     edx, [rdi]
0x1800303c0  mov     rcx, rsi
0x1800303c3  call    CngEncryptMemoryEx
0x1800303c8  mov     esi, eax
0x1800303ca  test    eax, eax
0x1800303cc  js      loc_180030666
0x1800303d2  mov     rbp, [rsp+48h+arg_0]
0x1800303d7  jmp     loc_180030319
0x1800303dc  lea     eax, [rbx-390004h]; switch 129 cases
0x1800303e2  mov     r8d, 80h
0x1800303e8  cmp     eax, r8d
0x1800303eb  ja      def_18003040C; jumptable 000000018003040C default case, cases 3735557-3735559,3735561-3735565,3735567-3735569,3735571-3735573,3735575-3735577,3735579-3735581,3735583-3735585,3735587,3735589-3735615,3735617-3735619,3735621-3735623,3735625-3735651,3735653-3735666,3735669-3735673,3735675-3735683
0x1800303f1  lea     r9, cs:180000000h
0x1800303f8  movzx   eax, ds:(byte_1800C8A1C - 180000000h)[r9+rax]
0x180030401  mov     ecx, ds:(jpt_18003040C - 180000000h)[r9+rax*4]
0x180030409  add     rcx, r9
0x18003040c  jmp     rcx; switch jump
0x180030412  test    rsi, rsi; jumptable 000000018003040C cases 3735556,3735560
0x180030415  jz      loc_1800304B1
0x18003041b  test    rdi, rdi
0x18003041e  jz      loc_1800304B1
0x180030424  mov     eax, [rdi]
0x180030426  cmp     edx, eax
0x180030428  jnb     short loc_18003043B
0x18003042a  sub     eax, edx
0x18003042c  mov     ecx, edx
0x18003042e  mov     r8d, eax; Size
0x180030431  add     rcx, rsi; void *
0x180030434  xor     edx, edx; Val
0x180030436  call    memset
0x18003043b  mov     edx, [rdi]
0x18003043d  mov     rcx, rsi; void *
0x180030440  call    SystemPrng
0x180030445  test    eax, eax
0x180030447  jz      loc_1800304D5
0x18003044d  mov     rbp, [rsp+48h+arg_0]
0x180030452  xor     eax, eax
0x180030454  jmp     loc_180030319
0x180030459  mov     rcx, cs:WPP_GLOBAL_Control
0x180030460  lea     rax, WPP_GLOBAL_Control
0x180030467  cmp     rcx, rax
0x18003046a  jz      short loc_18003049F
0x18003046c  mov     eax, [rcx+2Ch]
0x18003046f  test    al, 1
0x180030471  jz      short loc_18003049F
0x180030473  mov     [rsp+48h+var_18], 533h
0x18003047b  mov     rcx, [rcx+18h]
0x18003047f  lea     rax, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180030486  mov     [rsp+48h+var_20], rax
0x18003048b  lea     r9, aStatus; "Status"
0x180030492  mov     [rsp+48h+var_28], 0C000000Dh
0x18003049a  call    WPP_SF_sDsd
0x18003049f  mov     eax, 0C000000Dh
0x1800304a4  jmp     loc_1800303D2
0x1800304a9  mov     r9d, r8d
0x1800304ac  jmp     loc_18003037A
0x1800304b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304b8  lea     rax, WPP_GLOBAL_Control
0x1800304bf  cmp     rcx, rax
0x1800304c2  jz      short loc_18003049F
0x1800304c4  mov     eax, [rcx+2Ch]
0x1800304c7  test    al, 1
0x1800304c9  jz      short loc_18003049F
0x1800304cb  mov     [rsp+48h+var_18], 50Fh
0x1800304d3  jmp     short loc_18003047B
0x1800304d5  mov     r9d, 51Fh
0x1800304db  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800304e2  lea     rdx, aStatus; "Status"
0x1800304e9  mov     ecx, 0C0000001h
0x1800304ee  call    DebugTraceError
0x1800304f3  mov     eax, 0C0000001h
0x1800304f8  jmp     loc_1800303D2
0x1800304fd  cmp     [rsp+48h+arg_28], 0; jumptable 000000018003040C case 3735588
0x180030502  jz      loc_1800A74A4
0x180030508  mov     r9d, 573h
0x18003050e  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180030515  lea     rdx, aStatus; "Status"
0x18003051c  mov     ecx, 0C0000022h
0x180030521  call    DebugTraceError
0x180030526  mov     eax, 0C0000022h
0x18003052b  jmp     loc_1800303D2
0x180030530  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018003040C case 3735616
0x180030536  lea     r9, off_1800AE810; void *
0x18003053d  mov     rdx, rdi; unsigned int *
0x180030540  mov     rcx, rsi; void *
0x180030543  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180030548  jmp     loc_1800303D2
0x18003054d  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018003040C case 3735652
0x180030553  lea     r9, qword_1800AE6C0; void *
0x18003055a  mov     rdx, rdi; unsigned int *
0x18003055d  mov     rcx, rsi; void *
0x180030560  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180030565  jmp     loc_1800303D2
0x18003056a  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018003040C case 3735620
0x180030570  lea     r9, off_1800AE660; void *
0x180030577  mov     rdx, rdi; unsigned int *
0x18003057a  mov     rcx, rsi; void *
0x18003057d  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180030582  jmp     loc_1800303D2
0x180030587  movzx   r8d, [rsp+48h+arg_28]; jumptable 000000018003040C case 3735624
0x18003058d  lea     r9, off_1800AE6B0; void *
0x180030594  mov     rdx, rdi; unsigned int *
0x180030597  mov     rcx, rsi; void *
0x18003059a  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x18003059f  jmp     loc_1800303D2
0x1800305a4  test    rdi, rdi; jumptable 000000018003040C case 3735667
0x1800305a7  jz      loc_1800A75F7
0x1800305ad  cmp     dword ptr [rdi], 0
0x1800305b0  jz      loc_1800A75F7
0x1800305b6  jmp     loc_1800A761F
0x1800305bb  test    rdi, rdi; jumptable 000000018003040C case 3735668
0x1800305be  jz      loc_1800A7627
0x1800305c4  cmp     dword ptr [rdi], 0
0x1800305c7  jz      loc_1800A7627
0x1800305cd  jmp     loc_1800A7648
0x1800305d2  test    rdi, rdi; jumptable 000000018003040C case 3735684
0x1800305d5  jz      loc_1800A7650
0x1800305db  cmp     dword ptr [rdi], 8
0x1800305de  jnz     loc_1800A7650
0x1800305e4  test    rsi, rsi
0x1800305e7  jz      loc_1800A7650
0x1800305ed  mov     rax, cs:g_selftestDuration
0x1800305f4  mov     [rsi], rax
0x1800305f7  jmp     loc_18003044D
0x1800305fc  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018003040C default case, cases 3735557-3735559,3735561-3735565,3735567-3735569,3735571-3735573,3735575-3735577,3735579-3735581,3735583-3735585,3735587,3735589-3735615,3735617-3735619,3735621-3735623,3735625-3735651,3735653-3735666,3735669-3735673,3735675-3735683
0x180030603  lea     rax, WPP_GLOBAL_Control
0x18003060a  mov     esi, 0C00000BBh
0x18003060f  cmp     rcx, rax
0x180030612  jz      loc_1800A75E7
0x180030618  mov     eax, [rcx+2Ch]
0x18003061b  test    al, 1
0x18003061d  jz      loc_1800A75E7
0x180030623  mov     rcx, [rcx+18h]
0x180030627  mov     edx, 0Ch
0x18003062c  mov     r9d, ebx
0x18003062f  call    WPP_SF_D
0x180030634  nop
0x180030635  jmp     loc_1800A75E7
0x18003063a  sub     eax, edx
0x18003063c  mov     ecx, edx
0x18003063e  mov     r8d, eax; Size
0x180030641  add     rcx, rsi; void *
0x180030644  xor     edx, edx; Val
0x180030646  call    memset
0x18003064b  jmp     loc_180030357
0x180030650  mov     r9d, 2
0x180030656  jmp     loc_18003038B
0x18003065b  mov     r9d, 4
0x180030661  jmp     loc_18003039C
0x180030666  mov     r9d, 564h
0x18003066c  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180030673  lea     rdx, aStatus; "Status"
0x18003067a  mov     ecx, eax
0x18003067c  call    DebugTraceError
0x180030681  nop
0x180030682  jmp     loc_1800A75EE
0x1800a74a4  mov     eax, [rdi]
0x1800a74a6  cmp     eax, r8d
0x1800a74a9  jb      loc_1800A7560
0x1800a74af  lea     rax, FipsDesKey
0x1800a74b6  mov     [rsi], rax
0x1800a74b9  lea     rax, FipsDes
0x1800a74c0  mov     [rsi+8], rax
0x1800a74c4  lea     rax, Fips3Des3Key
0x1800a74cb  mov     [rsi+10h], rax
0x1800a74cf  lea     rax, Fips3Des
0x1800a74d6  mov     [rsi+18h], rax
0x1800a74da  lea     rax, FipsSHAInit
0x1800a74e1  mov     [rsi+20h], rax
0x1800a74e5  lea     rax, FipsHmacSHAUpdate
0x1800a74ec  mov     [rsi+28h], rax
0x1800a74f0  lea     rax, FipsSHAFinal
0x1800a74f7  mov     [rsi+30h], rax
0x1800a74fb  lea     rax, FipsCBC
0x1800a7502  mov     [rsi+38h], rax
0x1800a7506  lea     rax, FIPSGenRandom
0x1800a750d  mov     [rsi+40h], rax
0x1800a7511  lea     rax, FipsBlockCBC
0x1800a7518  mov     [rsi+48h], rax
0x1800a751c  lea     rax, FipsHmacSHAInit
0x1800a7523  mov     [rsi+50h], rax
0x1800a7527  lea     rax, FipsHmacSHAUpdate
0x1800a752e  mov     [rsi+58h], rax
0x1800a7532  lea     rax, FipsHmacSHAFinal
0x1800a7539  mov     [rsi+60h], rax
0x1800a753d  lea     rax, HmacMD5Init
0x1800a7544  mov     [rsi+68h], rax
0x1800a7548  lea     rax, HmacMD5Update
0x1800a754f  mov     [rsi+70h], rax
0x1800a7553  lea     rax, HmacMD5Final
0x1800a755a  mov     [rsi+78h], rax
0x1800a755e  jmp     short loc_1800A75D8
0x1800a7560  cmp     eax, 50h ; 'P'
0x1800a7563  jb      short loc_1800A75E2
0x1800a7565  lea     rax, FipsDesKey
0x1800a756c  mov     r8d, 50h ; 'P'
0x1800a7572  mov     [rsi], rax
0x1800a7575  lea     rax, FipsDes
0x1800a757c  mov     [rsi+8], rax
0x1800a7580  lea     rax, Fips3Des3Key
0x1800a7587  mov     [rsi+10h], rax
0x1800a758b  lea     rax, Fips3Des
0x1800a7592  mov     [rsi+18h], rax
0x1800a7596  lea     rax, FipsSHAInit
0x1800a759d  mov     [rsi+20h], rax
0x1800a75a1  lea     rax, FipsHmacSHAUpdate
0x1800a75a8  mov     [rsi+28h], rax
0x1800a75ac  lea     rax, FipsSHAFinal
0x1800a75b3  mov     [rsi+30h], rax
0x1800a75b7  lea     rax, FipsCBC
0x1800a75be  mov     [rsi+38h], rax
0x1800a75c2  lea     rax, FIPSGenRandom
0x1800a75c9  mov     [rsi+40h], rax
0x1800a75cd  lea     rax, FipsBlockCBC
0x1800a75d4  mov     [rsi+48h], rax
0x1800a75d8  mov     [rdi], r8d
0x1800a75db  xor     eax, eax
0x1800a75dd  jmp     loc_1800303D2
0x1800a75e2  mov     esi, 0C0000023h
0x1800a75e7  test    rdi, rdi
0x1800a75ea  jz      short loc_1800A75F0
0x1800a75ec  xor     ebp, ebp
0x1800a75ee  mov     [rdi], ebp
0x1800a75f0  mov     eax, esi
0x1800a75f2  jmp     loc_1800303D2
0x1800a75f7  test    r10, r10
0x1800a75fa  jnz     short loc_1800A761F
0x1800a75fc  test    edx, edx
0x1800a75fe  jnz     short loc_1800A761F
0x1800a7600  cmp     cs:g_fSelftest, dl
0x1800a7606  jz      short loc_1800A7641
0x1800a7608  mov     cl, 1
0x1800a760a  call    cs:__imp_SeAuditFipsCryptoSelftests
0x1800a7611  nop     dword ptr [rax+rax+00h]
0x1800a7616  xor     ebp, ebp
0x1800a7618  mov     eax, ebp
0x1800a761a  jmp     loc_1800303D2
0x1800a761f  mov     r9d, 5DEh
0x1800a7625  jmp     short loc_1800A7656
0x1800a7627  test    r10, r10
0x1800a762a  jz      short loc_1800A7648
0x1800a762c  cmp     edx, 4
0x1800a762f  jnz     short loc_1800A7648
0x1800a7631  cmp     cs:g_fSelftest, 0
0x1800a7638  jz      short loc_1800A7641
0x1800a763a  mov     edx, [r10]
0x1800a763d  xor     ecx, ecx
0x1800a763f  jmp     short loc_1800A760A
0x1800a7641  mov     ebp, 0C0000244h
0x1800a7646  jmp     short loc_1800A7618
0x1800a7648  mov     r9d, 5F0h
0x1800a764e  jmp     short loc_1800A7656
  ... truncated ...
```
