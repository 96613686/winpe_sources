# SendQueueStatus

- ea: `0x1800064e4`
- end: `0x180006a84`
- name: `SendQueueStatus`
- size: `1440`
- prototype: `char *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007354`

## callees

- `0x180001ce0`
- `0x180002dfc`
- `0x180002e7c`
- `0x180004c28`
- `0x1800064e4`
- `0x180006a8c`
- `0x180006c2c`
- `0x180009a54`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800065a5`
- `KERNEL32!LocalAlloc` at `0x180006749`
- `KERNEL32!LocalAlloc` at `0x1800067d6`
- `KERNEL32!LocalAlloc` at `0x180006893`
- `KERNEL32!LocalAlloc` at `0x1800065a5`
- `KERNEL32!LocalAlloc` at `0x180006749`
- `KERNEL32!LocalAlloc` at `0x1800067d6`
- `KERNEL32!LocalAlloc` at `0x180006893`
- `KERNEL32!GetLastError` at `0x18000672b`
- `KERNEL32!GetLastError` at `0x18000672b`
- `KERNEL32!LocalFree` at `0x18000673d`
- `KERNEL32!LocalFree` at `0x180006848`
- `KERNEL32!LocalFree` at `0x1800069ae`
- `KERNEL32!LocalFree` at `0x1800069b7`
- `KERNEL32!LocalFree` at `0x180006a5b`
- `KERNEL32!LocalFree` at `0x18000673d`
- `KERNEL32!LocalFree` at `0x180006848`
- `KERNEL32!LocalFree` at `0x1800069ae`
- `KERNEL32!LocalFree` at `0x1800069b7`
- `KERNEL32!LocalFree` at `0x180006a5b`
- `WINSPOOL!OpenPrinterA` at `0x18000657d`
- `WINSPOOL!OpenPrinterA` at `0x18000657d`
- `WINSPOOL!GetPrinterA` at `0x180006640`
- `WINSPOOL!GetPrinterA` at `0x180006640`
- `WINSPOOL!EnumJobsA` at `0x18000678e`
- `WINSPOOL!EnumJobsA` at `0x18000678e`

## pseudocode

```c
char *__fastcall SendQueueStatus(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rbx
  int v4; // edi
  _DWORD *v5; // rsi
  char *v6; // r8
  char *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  char *v10; // rax
  void *v11; // rcx
  const char *v12; // r8
  __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // r12
  __int64 v16; // r15
  __int64 v17; // rdi
  BOOL i; // eax
  int v19; // r12d
  BOOL v20; // r15d
  char *v21; // rax
  char *v22; // rdi
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  char *result; // rax
  char *v28; // rbx
  const char *v29; // rax
  signed int v30; // ecx
  DWORD pcbNeeded; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh]
  DWORD pcReturned; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE phPrinter; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h]
  char pszDest[304]; // [rsp+70h] [rbp-90h] BYREF

  phPrinter = 0;
  pcbNeeded = 0;
  pcReturned = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = -1;
  if ( !*(_QWORD *)(a1 + 88) )
    goto LABEL_74;
  if ( !OpenPrinterA(*(LPSTR *)(a1 + 88), &phPrinter, 0) )
  {
    v2 = WPP_GLOBAL_Control;
LABEL_74:
    v5 = 0;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(v2[2], 43, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    v4 = 1;
    goto LABEL_50;
  }
  v4 = 0;
  *(_QWORD *)(a1 + 96) = phPrinter;
  v32 = 0;
  v5 = LocalAlloc(0, 0x1000u);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
LABEL_50:
    ShutdownPrinter(a1);
    if ( v5 )
      LocalFree(v5);
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(g_ppszStrings[0] + v25) );
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(qword_180013660 + v26) );
    do
      ++v3;
    while ( *(_BYTE *)(qword_180013668 + v3) );
    pcbNeeded = v3 + v26 + v25;
    result = (char *)LocalAlloc(0x40u, pcbNeeded);
    v28 = result;
    if ( result )
    {
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
        v29 = (const char *)qword_180013660;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
        v29 = (const char *)qword_180013668;
      }
      StringCchPrintfA(v28, pcbNeeded, "%s%s", (const char *)g_ppszStrings[0], v29);
      SendData(*(_QWORD *)(a1 + 8), v28, pcbNeeded);
      return (char *)LocalFree(v28);
    }
    return result;
  }
  v6 = *(char **)(a1 + 88);
  v7 = pszDest;
  v8 = 2147483646;
  v9 = 300;
  do
  {
    if ( !v8 )
      break;
    if ( !*v6 )
      break;
    *v7++ = *v6++;
    --v8;
    --v9;
  }
  while ( v9 );
  v10 = v7 - 1;
  if ( v9 )
    v10 = v7;
  v11 = *(void **)(a1 + 96);
  *v10 = 0;
  if ( GetPrinterA(v11, 2u, (LPBYTE)v5, 0x1000u, &pcbNeeded) )
  {
    if ( v5[31] == 1 )
    {
      v12 = (const char *)qword_180013670;
LABEL_21:
      StringCchCatA(pszDest, 0x12Cu, v12);
      goto LABEL_25;
    }
    if ( v5[31] == 4 )
    {
      v12 = pszSrc;
      goto LABEL_21;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
  }
LABEL_25:
  v13 = -1;
  do
    ++v13;
  while ( pszDest[v13] );
  v35 = v13;
  v14 = -1;
  do
    ++v14;
  while ( *(_BYTE *)(g_ppszStrings[0] + v14) );
  v15 = -1;
  do
    ++v15;
  while ( *(_BYTE *)(qword_180013648 + v15) );
  v16 = -1;
  do
    ++v16;
  while ( *(_BYTE *)(qword_180013650 + v16) );
  v17 = -1;
  do
    ++v17;
  while ( *(_BYTE *)(qword_180013658 + v17) );
  pcbNeeded = 4096;
  for ( i = EnumJobsA(*(HANDLE *)(a1 + 96), 0, 0x1F4u, 2u, (LPBYTE)v5, 0x1000u, &pcbNeeded, &pcReturned);
        !i;
        i = EnumJobsA(*(HANDLE *)(a1 + 96), 0, 0x1F4u, 2u, (LPBYTE)v5, pcbNeeded, &pcbNeeded, &pcReturned) )
  {
    if ( !i && GetLastError() != 122 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v24 = 46;
        goto LABEL_48;
      }
LABEL_49:
      v4 = v32;
      goto LABEL_50;
    }
    LocalFree(v5);
    v5 = LocalAlloc(0, pcbNeeded);
    if ( !v5 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v24 = 47;
LABEL_48:
        WPP_SF_(v23[2], v24, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
      }
      goto LABEL_49;
    }
  }
  v19 = v14 + v16 + 1 + v17 + v35 + v15;
  v20 = pcReturned != 0;
  pcbNeeded = v19 + 74 * pcReturned + 2;
  ShutdownPrinter(a1);
  v21 = (char *)LocalAlloc(0, pcbNeeded);
  v22 = v21;
  if ( !v21 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v24 = 48;
      goto LABEL_48;
    }
    goto LABEL_49;
  }
  StringCchPrintfA(
    v21,
    pcbNeeded,
    "%s%s%s%s%s%s",
    (const char *)g_ppszStrings[0],
    (const char *)qword_180013648,
    pszDest,
    (const char *)qword_180013650,
    (const char *)qword_180013658,
    "\n");
  do
    ++v3;
  while ( v22[v3] );
  if ( v20 )
  {
    v30 = FillJobStatus(a1, (int)v22 + v19, pcbNeeded - v19, (_DWORD)v5, pcReturned) + v3;
    if ( v30 > (int)pcbNeeded )
      v30 = pcbNeeded;
    LODWORD(v3) = v30;
  }
  SendData(*(_QWORD *)(a1 + 8), v22, v3);
  LocalFree(v5);
  result = (char *)LocalFree(v22);
  *(_WORD *)(a1 + 20) = 10;
  return result;
}

```

## disassembly

```asm
0x1800064e4  push    rbp
0x1800064e6  push    rbx
0x1800064e7  push    rsi
0x1800064e8  push    rdi
0x1800064e9  push    r12
0x1800064eb  push    r13
0x1800064ed  push    r14
0x1800064ef  push    r15
0x1800064f1  lea     rbp, [rsp-0B8h]
0x1800064f9  sub     rsp, 1B8h
0x180006500  mov     rax, cs:__security_cookie
0x180006507  xor     rax, rsp
0x18000650a  mov     [rbp+0F0h+var_50], rax
0x180006511  mov     r14, rcx
0x180006514  mov     [rsp+1F0h+phPrinter], 0
0x18000651d  mov     [rsp+1F0h+var_1A0], 0
0x180006525  mov     [rsp+1F0h+var_198], 0
0x18000652d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006534  lea     r15, WPP_GLOBAL_Control
0x18000653b  cmp     rcx, r15
0x18000653e  jz      short loc_180006562
0x180006540  test    byte ptr [rcx+1Ch], 1
0x180006544  jz      short loc_180006562
0x180006546  mov     rcx, [rcx+10h]
0x18000654a  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006551  mov     edx, 2Ah ; '*'
0x180006556  call    WPP_SF_
0x18000655b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006562  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006566  cmp     qword ptr [r14+58h], 0
0x18000656b  jz      loc_1800069D0
0x180006571  mov     rcx, [r14+58h]; pPrinterName
0x180006575  lea     rdx, [rsp+1F0h+phPrinter]; phPrinter
0x18000657a  xor     r8d, r8d; pDefault
0x18000657d  call    cs:__imp_OpenPrinterA
0x180006583  test    eax, eax
0x180006585  jz      loc_1800069C9
0x18000658b  mov     rax, [rsp+1F0h+phPrinter]
0x180006590  mov     r12d, 1000h
0x180006596  xor     edi, edi
0x180006598  mov     [r14+60h], rax
0x18000659c  mov     edx, r12d; uBytes
0x18000659f  mov     [rsp+1F0h+var_19C], edi
0x1800065a3  xor     ecx, ecx; uFlags
0x1800065a5  call    cs:__imp_LocalAlloc
0x1800065ab  mov     rsi, rax
0x1800065ae  test    rax, rax
0x1800065b1  jnz     short loc_1800065E5
0x1800065b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065ba  cmp     rcx, r15
0x1800065bd  jz      loc_180006838
0x1800065c3  test    byte ptr [rcx+1Ch], 8
0x1800065c7  jz      loc_180006838
0x1800065cd  mov     rcx, [rcx+10h]
0x1800065d1  lea     edx, [rbx+2Dh]
0x1800065d4  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x1800065db  call    WPP_SF_
0x1800065e0  jmp     loc_180006838
0x1800065e5  mov     r8, [r14+58h]
0x1800065e9  lea     rcx, [rsp+1F0h+pszDest]
0x1800065ee  mov     edi, 12Ch
0x1800065f3  mov     eax, 7FFFFFFEh
0x1800065f8  mov     edx, edi
0x1800065fa  test    rax, rax
0x1800065fd  jz      short loc_180006619
0x1800065ff  mov     r9b, [r8]
0x180006602  test    r9b, r9b
0x180006605  jz      short loc_180006619
0x180006607  mov     [rcx], r9b
0x18000660a  inc     r8
0x18000660d  inc     rcx
0x180006610  dec     rax
0x180006613  sub     rdx, 1
0x180006617  jnz     short loc_1800065FA
0x180006619  test    rdx, rdx
0x18000661c  lea     rax, [rcx-1]
0x180006620  mov     r9d, r12d; cbBuf
0x180006623  mov     r8, rsi; pPrinter
0x180006626  cmovnz  rax, rcx
0x18000662a  mov     edx, 2; Level
0x18000662f  mov     rcx, [r14+60h]; hPrinter
0x180006633  mov     byte ptr [rax], 0
0x180006636  lea     rax, [rsp+1F0h+var_1A0]
0x18000663b  mov     [rsp+1F0h+pcbNeeded], rax; pcbNeeded
0x180006640  call    cs:__imp_GetPrinterA
0x180006646  test    eax, eax
0x180006648  jz      short loc_180006675
0x18000664a  cmp     dword ptr [rsi+7Ch], 1
0x18000664e  jnz     short loc_180006659
0x180006650  mov     r8, cs:qword_180013670
0x180006657  jmp     short loc_180006666
0x180006659  cmp     dword ptr [rsi+7Ch], 4
0x18000665d  jnz     short loc_18000669C
0x18000665f  mov     r8, cs:pszSrc; pszSrc
0x180006666  mov     rdx, rdi; cchDest
0x180006669  lea     rcx, [rsp+1F0h+pszDest]; pszDest
0x18000666e  call    StringCchCatA
0x180006673  jmp     short loc_18000669C
0x180006675  mov     rcx, cs:WPP_GLOBAL_Control
0x18000667c  cmp     rcx, r15
0x18000667f  jz      short loc_18000669C
0x180006681  test    byte ptr [rcx+1Ch], 8
0x180006685  jz      short loc_18000669C
0x180006687  mov     rcx, [rcx+10h]
0x18000668b  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006692  mov     edx, 2Dh ; '-'
0x180006697  call    WPP_SF_
0x18000669c  lea     rcx, [rsp+1F0h+pszDest]
0x1800066a1  mov     rax, rbx
0x1800066a4  inc     rax
0x1800066a7  cmp     byte ptr [rcx+rax], 0
0x1800066ab  jnz     short loc_1800066A4
0x1800066ad  mov     [rsp+1F0h+var_188], rax
0x1800066b2  mov     r13, rbx
0x1800066b5  mov     rax, cs:g_ppszStrings
0x1800066bc  inc     r13
0x1800066bf  cmp     byte ptr [rax+r13], 0
0x1800066c4  jnz     short loc_1800066BC
0x1800066c6  mov     rax, cs:qword_180013648
0x1800066cd  mov     r12, rbx
0x1800066d0  inc     r12
0x1800066d3  cmp     byte ptr [rax+r12], 0
0x1800066d8  jnz     short loc_1800066D0
0x1800066da  mov     rax, cs:qword_180013650
0x1800066e1  mov     r15, rbx
0x1800066e4  inc     r15
0x1800066e7  cmp     byte ptr [rax+r15], 0
0x1800066ec  jnz     short loc_1800066E4
0x1800066ee  mov     rax, cs:qword_180013658
0x1800066f5  mov     rdi, rbx
0x1800066f8  inc     rdi
0x1800066fb  cmp     byte ptr [rax+rdi], 0
0x1800066ff  jnz     short loc_1800066F8
0x180006701  lea     rax, [rsp+1F0h+var_198]
0x180006706  mov     [rsp+1F0h+var_1A0], 1000h
0x18000670e  mov     [rsp+1F0h+pcReturned], rax
0x180006713  lea     rax, [rsp+1F0h+var_1A0]
0x180006718  mov     [rsp+1F0h+var_1C0], rax
0x18000671d  mov     [rsp+1F0h+cbBuf], 1000h
0x180006725  jmp     short loc_180006777
0x180006727  test    eax, eax
0x180006729  jnz     short loc_18000673A
0x18000672b  call    cs:__imp_GetLastError
0x180006731  cmp     eax, 7Ah ; 'z'
0x180006734  jnz     loc_180006806
0x18000673a  mov     rcx, rsi; hMem
0x18000673d  call    cs:__imp_LocalFree
0x180006743  mov     edx, [rsp+1F0h+var_1A0]; uBytes
0x180006747  xor     ecx, ecx; uFlags
0x180006749  call    cs:__imp_LocalAlloc
0x18000674f  mov     rsi, rax
0x180006752  test    rax, rax
0x180006755  jz      loc_1800068E0
0x18000675b  lea     rax, [rsp+1F0h+var_198]
0x180006760  mov     [rsp+1F0h+pcReturned], rax; pcReturned
0x180006765  lea     rax, [rsp+1F0h+var_1A0]
0x18000676a  mov     [rsp+1F0h+var_1C0], rax; pcbNeeded
0x18000676f  mov     eax, [rsp+1F0h+var_1A0]
0x180006773  mov     [rsp+1F0h+cbBuf], eax; cbBuf
0x180006777  mov     rcx, [r14+60h]; hPrinter
0x18000677b  mov     r9d, 2; Level
0x180006781  mov     r8d, 1F4h; NoJobs
0x180006787  mov     [rsp+1F0h+pcbNeeded], rsi; pJob
0x18000678c  xor     edx, edx; FirstJob
0x18000678e  call    cs:__imp_EnumJobsA
0x180006794  cmp     eax, 1
0x180006797  jnz     short loc_180006727
0x180006799  mov     rax, [rsp+1F0h+var_188]
0x18000679e  inc     r15d
0x1800067a1  add     eax, edi
0x1800067a3  add     eax, r15d
0x1800067a6  add     r12d, eax
0x1800067a9  mov     eax, [rsp+1F0h+var_198]
0x1800067ad  add     r12d, r13d
0x1800067b0  neg     eax
0x1800067b2  sbb     r15d, r15d
0x1800067b5  imul    ecx, [rsp+1F0h+var_198], 4Ah ; 'J'
0x1800067ba  and     r15d, 1
0x1800067be  add     ecx, 2
0x1800067c1  add     ecx, r12d
0x1800067c4  mov     [rsp+1F0h+var_1A0], ecx
0x1800067c8  mov     rcx, r14
0x1800067cb  call    ShutdownPrinter
0x1800067d0  mov     edx, [rsp+1F0h+var_1A0]; uBytes
0x1800067d4  xor     ecx, ecx; uFlags
0x1800067d6  call    cs:__imp_LocalAlloc
0x1800067dc  mov     rdi, rax
0x1800067df  test    rax, rax
0x1800067e2  jnz     loc_18000690B
0x1800067e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067ef  lea     r15, WPP_GLOBAL_Control
0x1800067f6  cmp     rcx, r15
0x1800067f9  jz      short loc_180006834
0x1800067fb  test    byte ptr [rcx+1Ch], 8
0x1800067ff  jz      short loc_180006834
0x180006801  lea     edx, [rax+30h]
0x180006804  jmp     short loc_180006824
0x180006806  mov     rcx, cs:WPP_GLOBAL_Control
0x18000680d  lea     r15, WPP_GLOBAL_Control
0x180006814  cmp     rcx, r15
0x180006817  jz      short loc_180006834
0x180006819  test    byte ptr [rcx+1Ch], 8
0x18000681d  jz      short loc_180006834
0x18000681f  mov     edx, 2Eh ; '.'
0x180006824  mov     rcx, [rcx+10h]
0x180006828  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x18000682f  call    WPP_SF_
0x180006834  mov     edi, [rsp+1F0h+var_19C]
0x180006838  mov     rcx, r14
0x18000683b  call    ShutdownPrinter
0x180006840  test    rsi, rsi
0x180006843  jz      short loc_18000684E
0x180006845  mov     rcx, rsi; hMem
0x180006848  call    cs:__imp_LocalFree
0x18000684e  mov     rax, cs:g_ppszStrings
0x180006855  mov     rcx, rbx
0x180006858  inc     rcx
0x18000685b  cmp     byte ptr [rax+rcx], 0
0x18000685f  jnz     short loc_180006858
0x180006861  mov     rdx, cs:qword_180013660
0x180006868  mov     rax, rbx
0x18000686b  inc     rax
0x18000686e  cmp     byte ptr [rdx+rax], 0
0x180006872  jnz     short loc_18000686B
0x180006874  mov     rdx, cs:qword_180013668
0x18000687b  inc     rbx
0x18000687e  cmp     byte ptr [rdx+rbx], 0
0x180006882  jnz     short loc_18000687B
0x180006884  add     eax, ebx
0x180006886  add     ecx, eax
0x180006888  mov     [rsp+1F0h+var_1A0], ecx
0x18000688c  mov     edx, ecx; uBytes
0x18000688e  mov     ecx, 40h ; '@'; uFlags
0x180006893  call    cs:__imp_LocalAlloc
0x180006899  mov     rbx, rax
0x18000689c  test    rax, rax
0x18000689f  jz      loc_180006A61
0x1800068a5  test    edi, edi
0x1800068a7  jz      loc_1800069FA
0x1800068ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068b4  cmp     rcx, r15
0x1800068b7  jz      short loc_1800068D4
0x1800068b9  test    byte ptr [rcx+1Ch], 8
0x1800068bd  jz      short loc_1800068D4
0x1800068bf  mov     rcx, [rcx+10h]
0x1800068c3  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x1800068ca  mov     edx, 31h ; '1'
0x1800068cf  call    WPP_SF_
0x1800068d4  mov     rax, cs:qword_180013660
0x1800068db  jmp     loc_180006A28
0x1800068e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068e7  lea     r15, WPP_GLOBAL_Control
0x1800068ee  cmp     rcx, r15
0x1800068f1  jz      loc_180006834
0x1800068f7  test    byte ptr [rcx+1Ch], 8
0x1800068fb  jz      loc_180006834
0x180006901  mov     edx, 2Fh ; '/'
0x180006906  jmp     loc_180006824
0x18000690b  mov     edx, [rsp+1F0h+var_1A0]; cchDest
0x18000690f  lea     rax, asc_18000F948; "\n"
0x180006916  mov     r9, cs:g_ppszStrings
0x18000691d  lea     r8, aSSSSSS; "%s%s%s%s%s%s"
0x180006924  mov     [rsp+1F0h+var_1B0], rax
0x180006929  mov     rcx, rdi; pszDest
0x18000692c  mov     rax, cs:qword_180013658
0x180006933  mov     [rsp+1F0h+pcReturned], rax
0x180006938  mov     rax, cs:qword_180013650
0x18000693f  mov     [rsp+1F0h+var_1C0], rax
0x180006944  lea     rax, [rsp+1F0h+pszDest]
0x180006949  mov     qword ptr [rsp+1F0h+cbBuf], rax
0x18000694e  mov     rax, cs:qword_180013648
0x180006955  mov     [rsp+1F0h+pcbNeeded], rax
0x18000695a  call    StringCchPrintfA
0x18000695f  inc     rbx
0x180006962  cmp     byte ptr [rdi+rbx], 0
0x180006966  jnz     short loc_18000695F
0x180006968  test    r15d, r15d
0x18000696b  jz      short loc_18000699C
0x18000696d  mov     r8d, [rsp+1F0h+var_1A0]
0x180006972  mov     r9, rsi
0x180006975  mov     eax, [rsp+1F0h+var_198]
0x180006979  sub     r8d, r12d
0x18000697c  mov     edx, r12d
0x18000697f  mov     rcx, r14
0x180006982  add     rdx, rdi
0x180006985  mov     dword ptr [rsp+1F0h+pcbNeeded], eax
0x180006989  call    FillJobStatus
0x18000698e  lea     ecx, [rax+rbx]
0x180006991  cmp     ecx, [rsp+1F0h+var_1A0]
0x180006995  cmovg   ecx, [rsp+1F0h+var_1A0]
0x18000699a  mov     ebx, ecx
0x18000699c  mov     rcx, [r14+8]; s
0x1800069a0  mov     r8d, ebx; len
0x1800069a3  mov     rdx, rdi; buf
0x1800069a6  call    SendData
0x1800069ab  mov     rcx, rsi; hMem
0x1800069ae  call    cs:__imp_LocalFree
0x1800069b4  mov     rcx, rdi; hMem
0x1800069b7  call    cs:__imp_LocalFree
0x1800069bd  mov     word ptr [r14+14h], 0Ah
  ... truncated ...
```
