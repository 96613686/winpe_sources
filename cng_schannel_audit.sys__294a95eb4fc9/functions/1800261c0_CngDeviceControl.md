# CngDeviceControl

- ea: `0x1800261c0`
- end: `0x180026557`
- name: `CngDeviceControl`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026080`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18000dbf0`
- `0x18001b0a0`
- `0x1800261c0`
- `0x180026560`
- `0x18005cd80`
- `0x18005d3a8`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!SeAuditFipsCryptoSelftests` at `0x1800a086c`
- `ntoskrnl!SeAuditFipsCryptoSelftests` at `0x1800a086c`

## string_xrefs

- `0x18002634f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800263ab`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800263de`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18002653c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800a08b8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

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
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, off_1800A7220);
      case 0x390044u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &off_1800A7070);
      case 0x390048u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &off_1800A70C0);
      case 0x390064u:
        return CryptIoctlReturnKernelmodePointer(v7, a4, a6, &qword_1800A70D0);
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
0x1800261c0  mov     [rsp+arg_8], rbx
0x1800261c5  mov     [rsp+arg_10], rsi
0x1800261ca  push    rdi
0x1800261cb  sub     rsp, 40h
0x1800261cf  mov     ebx, [rsp+48h+arg_20]
0x1800261d3  mov     rdi, r9
0x1800261d6  mov     rsi, r8
0x1800261d9  mov     r10, rcx
0x1800261dc  cmp     ebx, 390400h
0x1800261e2  jnz     short loc_1800261FA
0x1800261e4  call    ConfigIoHandler_Safeguarded
0x1800261e9  mov     rbx, [rsp+48h+arg_8]
0x1800261ee  mov     rsi, [rsp+48h+arg_10]
0x1800261f3  add     rsp, 40h
0x1800261f7  pop     rdi
0x1800261f8  retn
0x1800261fa  mov     [rsp+48h+arg_0], rbp
0x1800261ff  cmp     ebx, 39007Eh
0x180026205  jnz     loc_1800262AC
0x18002620b  test    rsi, rsi; jumptable 00000001800262DC cases 3735566,3735570,3735574,3735578,3735582,3735586,3735674
0x18002620e  jz      loc_180026329
0x180026214  test    rdi, rdi
0x180026217  jz      loc_180026329
0x18002621d  mov     eax, [rdi]
0x18002621f  cmp     edx, eax
0x180026221  jb      loc_18002650A
0x180026227  xor     ebp, ebp
0x180026229  mov     r8d, 1
0x18002622f  cmp     ebx, 390016h
0x180026235  jz      loc_180026379
0x18002623b  mov     r9d, ebp
0x18002623e  cmp     ebx, 39001Ah
0x180026244  jz      loc_180026379
0x18002624a  lea     eax, [rbx-39001Eh]
0x180026250  test    eax, 0FFFFFFFBh
0x180026255  jz      loc_180026520
0x18002625b  lea     eax, [rbx-39007Ah]
0x180026261  test    eax, 0FFFFFFFBh
0x180026266  jz      loc_18002652B
0x18002626c  lea     eax, [rbx-390012h]
0x180026272  test    eax, 0FFFFFFE7h
0x180026277  jnz     short loc_180026286
0x180026279  cmp     ebx, 39002Ah
0x18002627f  jz      short loc_180026286
0x180026281  mov     r8d, ebp
0x180026284  jmp     short loc_18002628E
0x180026286  cmp     ebx, 39007Eh
0x18002628c  jz      short loc_180026281
0x18002628e  mov     edx, [rdi]
0x180026290  mov     rcx, rsi
0x180026293  call    CngEncryptMemoryEx
0x180026298  mov     esi, eax
0x18002629a  test    eax, eax
0x18002629c  js      loc_180026536
0x1800262a2  mov     rbp, [rsp+48h+arg_0]
0x1800262a7  jmp     loc_1800261E9
0x1800262ac  lea     eax, [rbx-390004h]; switch 129 cases
0x1800262b2  mov     r8d, 80h
0x1800262b8  cmp     eax, r8d
0x1800262bb  ja      def_1800262DC; jumptable 00000001800262DC default case, cases 3735557-3735559,3735561-3735565,3735567-3735569,3735571-3735573,3735575-3735577,3735579-3735581,3735583-3735585,3735587,3735589-3735615,3735617-3735619,3735621-3735623,3735625-3735651,3735653-3735666,3735669-3735673,3735675-3735683
0x1800262c1  lea     r9, cs:180000000h
0x1800262c8  movzx   eax, ds:(byte_1800C01BC - 180000000h)[r9+rax]
0x1800262d1  mov     ecx, ds:(jpt_1800262DC - 180000000h)[r9+rax*4]
0x1800262d9  add     rcx, r9
0x1800262dc  jmp     rcx; switch jump
0x1800262e2  test    rsi, rsi; jumptable 00000001800262DC cases 3735556,3735560
0x1800262e5  jz      loc_180026381
0x1800262eb  test    rdi, rdi
0x1800262ee  jz      loc_180026381
0x1800262f4  mov     eax, [rdi]
0x1800262f6  cmp     edx, eax
0x1800262f8  jnb     short loc_18002630B
0x1800262fa  sub     eax, edx
0x1800262fc  mov     ecx, edx
0x1800262fe  mov     r8d, eax; Size
0x180026301  add     rcx, rsi; void *
0x180026304  xor     edx, edx; Val
0x180026306  call    memset
0x18002630b  mov     edx, [rdi]
0x18002630d  mov     rcx, rsi; void *
0x180026310  call    SystemPrng
0x180026315  test    eax, eax
0x180026317  jz      loc_1800263A5
0x18002631d  mov     rbp, [rsp+48h+arg_0]
0x180026322  xor     eax, eax
0x180026324  jmp     loc_1800261E9
0x180026329  mov     rcx, cs:WPP_GLOBAL_Control
0x180026330  lea     rax, WPP_GLOBAL_Control
0x180026337  cmp     rcx, rax
0x18002633a  jz      short loc_18002636F
0x18002633c  mov     eax, [rcx+2Ch]
0x18002633f  test    al, 1
0x180026341  jz      short loc_18002636F
0x180026343  mov     [rsp+48h+var_18], 533h
0x18002634b  mov     rcx, [rcx+18h]
0x18002634f  lea     rax, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180026356  mov     [rsp+48h+var_20], rax
0x18002635b  lea     r9, aStatus; "Status"
0x180026362  mov     [rsp+48h+var_28], 0C000000Dh
0x18002636a  call    WPP_SF_sDsd
0x18002636f  mov     eax, 0C000000Dh
0x180026374  jmp     loc_1800262A2
0x180026379  mov     r9d, r8d
0x18002637c  jmp     loc_18002624A
0x180026381  mov     rcx, cs:WPP_GLOBAL_Control
0x180026388  lea     rax, WPP_GLOBAL_Control
0x18002638f  cmp     rcx, rax
0x180026392  jz      short loc_18002636F
0x180026394  mov     eax, [rcx+2Ch]
0x180026397  test    al, 1
0x180026399  jz      short loc_18002636F
0x18002639b  mov     [rsp+48h+var_18], 50Fh
0x1800263a3  jmp     short loc_18002634B
0x1800263a5  mov     r9d, 51Fh
0x1800263ab  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800263b2  lea     rdx, aStatus; "Status"
0x1800263b9  mov     ecx, 0C0000001h
0x1800263be  call    DebugTraceError
0x1800263c3  mov     eax, 0C0000001h
0x1800263c8  jmp     loc_1800262A2
0x1800263cd  cmp     [rsp+48h+arg_28], 0; jumptable 00000001800262DC case 3735588
0x1800263d2  jz      loc_1800A0706
0x1800263d8  mov     r9d, 573h
0x1800263de  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800263e5  lea     rdx, aStatus; "Status"
0x1800263ec  mov     ecx, 0C0000022h
0x1800263f1  call    DebugTraceError
0x1800263f6  mov     eax, 0C0000022h
0x1800263fb  jmp     loc_1800262A2
0x180026400  movzx   r8d, [rsp+48h+arg_28]; jumptable 00000001800262DC case 3735616
0x180026406  lea     r9, off_1800A7220; void *
0x18002640d  mov     rdx, rdi; unsigned int *
0x180026410  mov     rcx, rsi; void *
0x180026413  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180026418  jmp     loc_1800262A2
0x18002641d  movzx   r8d, [rsp+48h+arg_28]; jumptable 00000001800262DC case 3735652
0x180026423  lea     r9, qword_1800A70D0; void *
0x18002642a  mov     rdx, rdi; unsigned int *
0x18002642d  mov     rcx, rsi; void *
0x180026430  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180026435  jmp     loc_1800262A2
0x18002643a  movzx   r8d, [rsp+48h+arg_28]; jumptable 00000001800262DC case 3735620
0x180026440  lea     r9, off_1800A7070; void *
0x180026447  mov     rdx, rdi; unsigned int *
0x18002644a  mov     rcx, rsi; void *
0x18002644d  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x180026452  jmp     loc_1800262A2
0x180026457  movzx   r8d, [rsp+48h+arg_28]; jumptable 00000001800262DC case 3735624
0x18002645d  lea     r9, off_1800A70C0; void *
0x180026464  mov     rdx, rdi; unsigned int *
0x180026467  mov     rcx, rsi; void *
0x18002646a  call    ?CryptIoctlReturnKernelmodePointer@@YAJPEAXPEAKDPEBX@Z; CryptIoctlReturnKernelmodePointer(void *,ulong *,char,void const *)
0x18002646f  jmp     loc_1800262A2
0x180026474  test    rdi, rdi; jumptable 00000001800262DC case 3735667
0x180026477  jz      loc_1800A0859
0x18002647d  cmp     dword ptr [rdi], 0
0x180026480  jz      loc_1800A0859
0x180026486  jmp     loc_1800A0881
0x18002648b  test    rdi, rdi; jumptable 00000001800262DC case 3735668
0x18002648e  jz      loc_1800A0889
0x180026494  cmp     dword ptr [rdi], 0
0x180026497  jz      loc_1800A0889
0x18002649d  jmp     loc_1800A08AA
0x1800264a2  test    rdi, rdi; jumptable 00000001800262DC case 3735684
0x1800264a5  jz      loc_1800A08B2
0x1800264ab  cmp     dword ptr [rdi], 8
0x1800264ae  jnz     loc_1800A08B2
0x1800264b4  test    rsi, rsi
0x1800264b7  jz      loc_1800A08B2
0x1800264bd  mov     rax, cs:g_selftestDuration
0x1800264c4  mov     [rsi], rax
0x1800264c7  jmp     loc_18002631D
0x1800264cc  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001800262DC default case, cases 3735557-3735559,3735561-3735565,3735567-3735569,3735571-3735573,3735575-3735577,3735579-3735581,3735583-3735585,3735587,3735589-3735615,3735617-3735619,3735621-3735623,3735625-3735651,3735653-3735666,3735669-3735673,3735675-3735683
0x1800264d3  lea     rax, WPP_GLOBAL_Control
0x1800264da  mov     esi, 0C00000BBh
0x1800264df  cmp     rcx, rax
0x1800264e2  jz      loc_1800A0849
0x1800264e8  mov     eax, [rcx+2Ch]
0x1800264eb  test    al, 1
0x1800264ed  jz      loc_1800A0849
0x1800264f3  mov     rcx, [rcx+18h]
0x1800264f7  mov     edx, 0Ch
0x1800264fc  mov     r9d, ebx
0x1800264ff  call    WPP_SF_D
0x180026504  nop
0x180026505  jmp     loc_1800A0849
0x18002650a  sub     eax, edx
0x18002650c  mov     ecx, edx
0x18002650e  mov     r8d, eax; Size
0x180026511  add     rcx, rsi; void *
0x180026514  xor     edx, edx; Val
0x180026516  call    memset
0x18002651b  jmp     loc_180026227
0x180026520  mov     r9d, 2
0x180026526  jmp     loc_18002625B
0x18002652b  mov     r9d, 4
0x180026531  jmp     loc_18002626C
0x180026536  mov     r9d, 564h
0x18002653c  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180026543  lea     rdx, aStatus; "Status"
0x18002654a  mov     ecx, eax
0x18002654c  call    DebugTraceError
0x180026551  nop
0x180026552  jmp     loc_1800A0850
0x1800a0706  mov     eax, [rdi]
0x1800a0708  cmp     eax, r8d
0x1800a070b  jb      loc_1800A07C2
0x1800a0711  lea     rax, FipsDesKey
0x1800a0718  mov     [rsi], rax
0x1800a071b  lea     rax, FipsDes
0x1800a0722  mov     [rsi+8], rax
0x1800a0726  lea     rax, Fips3Des3Key
0x1800a072d  mov     [rsi+10h], rax
0x1800a0731  lea     rax, Fips3Des
0x1800a0738  mov     [rsi+18h], rax
0x1800a073c  lea     rax, FipsSHAInit
0x1800a0743  mov     [rsi+20h], rax
0x1800a0747  lea     rax, FipsHmacSHAUpdate
0x1800a074e  mov     [rsi+28h], rax
0x1800a0752  lea     rax, FipsSHAFinal
0x1800a0759  mov     [rsi+30h], rax
0x1800a075d  lea     rax, FipsCBC
0x1800a0764  mov     [rsi+38h], rax
0x1800a0768  lea     rax, FIPSGenRandom
0x1800a076f  mov     [rsi+40h], rax
0x1800a0773  lea     rax, FipsBlockCBC
0x1800a077a  mov     [rsi+48h], rax
0x1800a077e  lea     rax, FipsHmacSHAInit
0x1800a0785  mov     [rsi+50h], rax
0x1800a0789  lea     rax, FipsHmacSHAUpdate
0x1800a0790  mov     [rsi+58h], rax
0x1800a0794  lea     rax, FipsHmacSHAFinal
0x1800a079b  mov     [rsi+60h], rax
0x1800a079f  lea     rax, HmacMD5Init
0x1800a07a6  mov     [rsi+68h], rax
0x1800a07aa  lea     rax, HmacMD5Update
0x1800a07b1  mov     [rsi+70h], rax
0x1800a07b5  lea     rax, HmacMD5Final
0x1800a07bc  mov     [rsi+78h], rax
0x1800a07c0  jmp     short loc_1800A083A
0x1800a07c2  cmp     eax, 50h ; 'P'
0x1800a07c5  jb      short loc_1800A0844
0x1800a07c7  lea     rax, FipsDesKey
0x1800a07ce  mov     r8d, 50h ; 'P'
0x1800a07d4  mov     [rsi], rax
0x1800a07d7  lea     rax, FipsDes
0x1800a07de  mov     [rsi+8], rax
0x1800a07e2  lea     rax, Fips3Des3Key
0x1800a07e9  mov     [rsi+10h], rax
0x1800a07ed  lea     rax, Fips3Des
0x1800a07f4  mov     [rsi+18h], rax
0x1800a07f8  lea     rax, FipsSHAInit
0x1800a07ff  mov     [rsi+20h], rax
0x1800a0803  lea     rax, FipsHmacSHAUpdate
0x1800a080a  mov     [rsi+28h], rax
0x1800a080e  lea     rax, FipsSHAFinal
0x1800a0815  mov     [rsi+30h], rax
0x1800a0819  lea     rax, FipsCBC
0x1800a0820  mov     [rsi+38h], rax
0x1800a0824  lea     rax, FIPSGenRandom
0x1800a082b  mov     [rsi+40h], rax
0x1800a082f  lea     rax, FipsBlockCBC
0x1800a0836  mov     [rsi+48h], rax
0x1800a083a  mov     [rdi], r8d
0x1800a083d  xor     eax, eax
0x1800a083f  jmp     loc_1800262A2
0x1800a0844  mov     esi, 0C0000023h
0x1800a0849  test    rdi, rdi
0x1800a084c  jz      short loc_1800A0852
0x1800a084e  xor     ebp, ebp
0x1800a0850  mov     [rdi], ebp
0x1800a0852  mov     eax, esi
0x1800a0854  jmp     loc_1800262A2
0x1800a0859  test    r10, r10
0x1800a085c  jnz     short loc_1800A0881
0x1800a085e  test    edx, edx
0x1800a0860  jnz     short loc_1800A0881
0x1800a0862  cmp     cs:g_fSelftest, dl
0x1800a0868  jz      short loc_1800A08A3
0x1800a086a  mov     cl, 1
0x1800a086c  call    cs:__imp_SeAuditFipsCryptoSelftests
0x1800a0873  nop     dword ptr [rax+rax+00h]
0x1800a0878  xor     ebp, ebp
0x1800a087a  mov     eax, ebp
0x1800a087c  jmp     loc_1800262A2
0x1800a0881  mov     r9d, 5DEh
0x1800a0887  jmp     short loc_1800A08B8
0x1800a0889  test    r10, r10
0x1800a088c  jz      short loc_1800A08AA
0x1800a088e  cmp     edx, 4
0x1800a0891  jnz     short loc_1800A08AA
0x1800a0893  cmp     cs:g_fSelftest, 0
0x1800a089a  jz      short loc_1800A08A3
0x1800a089c  mov     edx, [r10]
0x1800a089f  xor     ecx, ecx
0x1800a08a1  jmp     short loc_1800A086C
0x1800a08a3  mov     ebp, 0C0000244h
0x1800a08a8  jmp     short loc_1800A087A
0x1800a08aa  mov     r9d, 5F0h
0x1800a08b0  jmp     short loc_1800A08B8
  ... truncated ...
```
