# InitializePrinter

- ea: `0x180005058`
- end: `0x18000553f`
- name: `InitializePrinter`
- size: `1255`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003480`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x180005058`
- `0x180006a8c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800050fb`
- `KERNEL32!LocalAlloc` at `0x180005165`
- `KERNEL32!LocalAlloc` at `0x18000522b`
- `KERNEL32!LocalAlloc` at `0x1800052a0`
- `KERNEL32!LocalAlloc` at `0x1800053b3`
- `KERNEL32!LocalAlloc` at `0x1800050fb`
- `KERNEL32!LocalAlloc` at `0x180005165`
- `KERNEL32!LocalAlloc` at `0x18000522b`
- `KERNEL32!LocalAlloc` at `0x1800052a0`
- `KERNEL32!LocalAlloc` at `0x1800053b3`
- `KERNEL32!GetLastError` at `0x180005148`
- `KERNEL32!GetLastError` at `0x1800051d4`
- `KERNEL32!GetLastError` at `0x180005203`
- `KERNEL32!GetLastError` at `0x180005283`
- `KERNEL32!GetLastError` at `0x18000530d`
- `KERNEL32!GetLastError` at `0x180005148`
- `KERNEL32!GetLastError` at `0x1800051d4`
- `KERNEL32!GetLastError` at `0x180005203`
- `KERNEL32!GetLastError` at `0x180005283`
- `KERNEL32!GetLastError` at `0x18000530d`
- `KERNEL32!LocalFree` at `0x18000515a`
- `KERNEL32!LocalFree` at `0x180005295`
- `KERNEL32!LocalFree` at `0x180005329`
- `KERNEL32!LocalFree` at `0x180005332`
- `KERNEL32!LocalFree` at `0x18000535a`
- `KERNEL32!LocalFree` at `0x180005432`
- `KERNEL32!LocalFree` at `0x180005440`
- `KERNEL32!LocalFree` at `0x1800054c5`
- `KERNEL32!LocalFree` at `0x1800054d3`
- `KERNEL32!LocalFree` at `0x1800054e3`
- `KERNEL32!LocalFree` at `0x1800054ec`
- `KERNEL32!LocalFree` at `0x18000515a`
- `KERNEL32!LocalFree` at `0x180005295`
- `KERNEL32!LocalFree` at `0x180005329`
- `KERNEL32!LocalFree` at `0x180005332`
- `KERNEL32!LocalFree` at `0x18000535a`
- `KERNEL32!LocalFree` at `0x180005432`
- `KERNEL32!LocalFree` at `0x180005440`
- `KERNEL32!LocalFree` at `0x1800054c5`
- `KERNEL32!LocalFree` at `0x1800054d3`
- `KERNEL32!LocalFree` at `0x1800054e3`
- `KERNEL32!LocalFree` at `0x1800054ec`
- `WINSPOOL!OpenPrinterA` at `0x1800050dc`
- `WINSPOOL!OpenPrinterA` at `0x180005497`
- `WINSPOOL!OpenPrinterA` at `0x1800050dc`
- `WINSPOOL!OpenPrinterA` at `0x180005497`
- `WINSPOOL!GetPrinterA` at `0x18000513a`
- `WINSPOOL!GetPrinterA` at `0x1800051b4`
- `WINSPOOL!GetPrinterA` at `0x18000513a`
- `WINSPOOL!GetPrinterA` at `0x1800051b4`
- `WINSPOOL!GetPrinterDriverA` at `0x180005275`
- `WINSPOOL!GetPrinterDriverA` at `0x1800052ed`
- `WINSPOOL!GetPrinterDriverA` at `0x180005275`
- `WINSPOOL!GetPrinterDriverA` at `0x1800052ed`
- `WINSPOOL!DocumentPropertiesA` at `0x180005383`
- `WINSPOOL!DocumentPropertiesA` at `0x180005402`
- `WINSPOOL!DocumentPropertiesA` at `0x180005383`
- `WINSPOOL!DocumentPropertiesA` at `0x180005402`

## pseudocode

```c
__int64 __fastcall InitializePrinter(__int64 a1)
{
  _QWORD *v2; // rcx
  BYTE *v3; // rax
  LPDEVMODEA *v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v8; // rbx
  __int64 v9; // rbx
  DWORD v10; // eax
  __int64 v11; // rbx
  DWORD LastError; // eax
  unsigned int v13; // ebx
  BYTE *v14; // rax
  BYTE *v15; // rsi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  BYTE *v18; // rax
  __int64 v19; // rbx
  DWORD v20; // eax
  LPDEVMODEA v21; // rax
  LONG v22; // eax
  struct _devicemodeA *v23; // rax
  struct _devicemodeA *v24; // rbx
  CHAR *v25; // rcx
  _PRINTER_DEFAULTSA pDefault; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbBuf; // [rsp+80h] [rbp+30h] BYREF
  HANDLE phPrinter; // [rsp+88h] [rbp+38h] BYREF

  phPrinter = 0;
  cbBuf = 0;
  memset(&pDefault, 0, sizeof(pDefault));
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !*(_QWORD *)(a1 + 88) )
    goto LABEL_72;
  if ( !OpenPrinterA(*(LPSTR *)(a1 + 88), &phPrinter, 0) )
  {
    v2 = WPP_GLOBAL_Control;
LABEL_72:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(v2[2], 15, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20004;
  }
  *(_QWORD *)(a1 + 96) = phPrinter;
  v3 = (BYTE *)LocalAlloc(0, 0x1000u);
  v4 = (LPDEVMODEA *)v3;
  if ( !v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 20001;
    v6 = 16;
LABEL_16:
    WPP_SF_(v5[2], v6, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20001;
  }
  if ( !GetPrinterA(phPrinter, 2u, v3, 0x1000u, &cbBuf) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_22;
    LocalFree(v4);
    v4 = (LPDEVMODEA *)LocalAlloc(0, cbBuf);
    if ( !v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return 20001;
      v6 = 17;
      goto LABEL_16;
    }
    if ( !GetPrinterA(phPrinter, 2u, (LPBYTE)v4, cbBuf, &cbBuf) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_26:
        v13 = 20004;
LABEL_59:
        LocalFree(v4);
        return v13;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
LABEL_23:
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
        {
          v11 = v8[2];
          LastError = GetLastError();
          WPP_SF_d(v11, 19, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids, LastError);
        }
        goto LABEL_26;
      }
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v10 = GetLastError();
      WPP_SF_d(v9, 18, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids, v10);
LABEL_22:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_23;
    }
  }
  v14 = (BYTE *)LocalAlloc(0, 0x1000u);
  v15 = v14;
  if ( !v14 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_58;
    v17 = 20;
LABEL_52:
    WPP_SF_(v16[2], v17, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
LABEL_58:
    v13 = 20001;
    goto LABEL_59;
  }
  if ( !GetPrinterDriverA(phPrinter, 0, 8u, v14, 0x1000u, &cbBuf) )
  {
    if ( GetLastError() != 122 )
    {
      v13 = 20006;
      goto LABEL_59;
    }
    LocalFree(v15);
    v18 = (BYTE *)LocalAlloc(0, cbBuf);
    v15 = v18;
    if ( !v18 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_58;
      v17 = 21;
      goto LABEL_52;
    }
    if ( !GetPrinterDriverA(phPrinter, 0, 8u, v18, cbBuf, &cbBuf) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v20 = GetLastError();
        WPP_SF_d(v19, 22, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids, v20);
      }
      LocalFree(v4);
      LocalFree(v15);
      return 20001;
    }
  }
  *(_DWORD *)(a1 + 260) = *((_DWORD *)v15 + 42) & 2;
  LocalFree(v15);
  v21 = v4[7];
  if ( v21 )
  {
    v24 = 0;
  }
  else
  {
    v22 = DocumentPropertiesA(0, phPrinter, *(LPSTR *)(a1 + 88), 0, 0, 0);
    if ( v22 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_58;
      v17 = 23;
      goto LABEL_52;
    }
    v23 = (struct _devicemodeA *)LocalAlloc(0, v22);
    v24 = v23;
    if ( !v23 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_58;
      v17 = 24;
      goto LABEL_52;
    }
    if ( DocumentPropertiesA(0, phPrinter, *(LPSTR *)(a1 + 88), v23, 0, 2u) < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
      LocalFree(v24);
      goto LABEL_58;
    }
    v4[7] = v24;
    v21 = v24;
  }
  v21->dmCopies = 1;
  *(_DWORD *)(a1 + 188) = 0;
  pDefault.pDatatype = (LPSTR)"RAW";
  ShutdownPrinter(a1);
  v25 = *(CHAR **)(a1 + 88);
  pDefault.pDevMode = v4[7];
  pDefault.DesiredAccess = 12;
  if ( !OpenPrinterA(v25, &phPrinter, &pDefault) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    LocalFree(v4);
    if ( v24 )
      LocalFree(v24);
    return 20004;
  }
  if ( v24 )
    LocalFree(v24);
  LocalFree(v4);
  *(_QWORD *)(a1 + 96) = phPrinter;
  return 0;
}

```

## disassembly

```asm
0x180005058  mov     [rsp-28h+arg_10], rbx
0x18000505d  mov     [rsp-28h+arg_18], rsi
0x180005062  push    rbp
0x180005063  push    rdi
0x180005064  push    r12
0x180005066  push    r13
0x180005068  push    r14
0x18000506a  mov     rbp, rsp
0x18000506d  sub     rsp, 50h
0x180005071  xorps   xmm0, xmm0
0x180005074  mov     [rbp+phPrinter], 0
0x18000507c  xor     eax, eax
0x18000507e  mov     [rbp+cbBuf], 0
0x180005085  movups  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180005089  mov     qword ptr [rbp+pDefault.DesiredAccess], rax
0x18000508d  mov     r14, rcx
0x180005090  mov     rcx, cs:WPP_GLOBAL_Control
0x180005097  lea     r12, WPP_GLOBAL_Control
0x18000509e  lea     r13, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x1800050a5  cmp     rcx, r12
0x1800050a8  jz      short loc_1800050C6
0x1800050aa  test    byte ptr [rcx+1Ch], 1
0x1800050ae  jz      short loc_1800050C6
0x1800050b0  mov     rcx, [rcx+10h]
0x1800050b4  lea     edx, [rax+0Eh]
0x1800050b7  mov     r8, r13
0x1800050ba  call    WPP_SF_
0x1800050bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050c6  cmp     qword ptr [r14+58h], 0
0x1800050cb  jz      loc_180005505
0x1800050d1  mov     rcx, [r14+58h]; pPrinterName
0x1800050d5  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800050d9  xor     r8d, r8d; pDefault
0x1800050dc  call    cs:__imp_OpenPrinterA
0x1800050e2  test    eax, eax
0x1800050e4  jz      loc_1800054FE
0x1800050ea  mov     rax, [rbp+phPrinter]
0x1800050ee  mov     ebx, 1000h
0x1800050f3  mov     edx, ebx; uBytes
0x1800050f5  mov     [r14+60h], rax
0x1800050f9  xor     ecx, ecx; uFlags
0x1800050fb  call    cs:__imp_LocalAlloc
0x180005101  mov     rdi, rax
0x180005104  test    rax, rax
0x180005107  jnz     short loc_180005120
0x180005109  mov     rcx, cs:WPP_GLOBAL_Control
0x180005110  cmp     rcx, r12
0x180005113  jz      short loc_180005194
0x180005115  test    byte ptr [rcx+1Ch], 8
0x180005119  jz      short loc_180005194
0x18000511b  lea     edx, [rax+10h]
0x18000511e  jmp     short loc_180005188
0x180005120  mov     rcx, [rbp+phPrinter]; hPrinter
0x180005124  lea     rax, [rbp+cbBuf]
0x180005128  mov     esi, 2
0x18000512d  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x180005132  mov     edx, esi; Level
0x180005134  mov     r9d, ebx; cbBuf
0x180005137  mov     r8, rdi; pPrinter
0x18000513a  call    cs:__imp_GetPrinterA
0x180005140  test    eax, eax
0x180005142  jnz     loc_180005226
0x180005148  call    cs:__imp_GetLastError
0x18000514e  cmp     eax, 7Ah ; 'z'
0x180005151  jnz     loc_1800051ED
0x180005157  mov     rcx, rdi; hMem
0x18000515a  call    cs:__imp_LocalFree
0x180005160  mov     edx, [rbp+cbBuf]; uBytes
0x180005163  xor     ecx, ecx; uFlags
0x180005165  call    cs:__imp_LocalAlloc
0x18000516b  mov     rdi, rax
0x18000516e  test    rax, rax
0x180005171  jnz     short loc_18000519E
0x180005173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000517a  cmp     rcx, r12
0x18000517d  jz      short loc_180005194
0x18000517f  test    byte ptr [rcx+1Ch], 8
0x180005183  jz      short loc_180005194
0x180005185  lea     edx, [rsi+0Fh]
0x180005188  mov     rcx, [rcx+10h]
0x18000518c  mov     r8, r13
0x18000518f  call    WPP_SF_
0x180005194  mov     eax, 4E21h
0x180005199  jmp     loc_180005526
0x18000519e  mov     r9d, [rbp+cbBuf]; cbBuf
0x1800051a2  lea     rax, [rbp+cbBuf]
0x1800051a6  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800051aa  mov     r8, rdi; pPrinter
0x1800051ad  mov     edx, esi; Level
0x1800051af  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x1800051b4  call    cs:__imp_GetPrinterA
0x1800051ba  test    eax, eax
0x1800051bc  jnz     short loc_180005226
0x1800051be  mov     rbx, cs:WPP_GLOBAL_Control
0x1800051c5  cmp     rbx, r12
0x1800051c8  jz      short loc_18000521C
0x1800051ca  test    byte ptr [rbx+1Ch], 8
0x1800051ce  jz      short loc_1800051F4
0x1800051d0  mov     rbx, [rbx+10h]
0x1800051d4  call    cs:__imp_GetLastError
0x1800051da  mov     edx, 12h
0x1800051df  mov     r8, r13
0x1800051e2  mov     r9d, eax
0x1800051e5  mov     rcx, rbx
0x1800051e8  call    WPP_SF_d
0x1800051ed  mov     rbx, cs:WPP_GLOBAL_Control
0x1800051f4  cmp     rbx, r12
0x1800051f7  jz      short loc_18000521C
0x1800051f9  test    byte ptr [rbx+1Ch], 8
0x1800051fd  jz      short loc_18000521C
0x1800051ff  mov     rbx, [rbx+10h]
0x180005203  call    cs:__imp_GetLastError
0x180005209  mov     edx, 13h
0x18000520e  mov     r8, r13
0x180005211  mov     r9d, eax
0x180005214  mov     rcx, rbx
0x180005217  call    WPP_SF_d
0x18000521c  mov     ebx, 4E24h
0x180005221  jmp     loc_18000543D
0x180005226  mov     rdx, rbx; uBytes
0x180005229  xor     ecx, ecx; uFlags
0x18000522b  call    cs:__imp_LocalAlloc
0x180005231  mov     rsi, rax
0x180005234  test    rax, rax
0x180005237  jnz     short loc_18000525B
0x180005239  mov     rcx, cs:WPP_GLOBAL_Control
0x180005240  cmp     rcx, r12
0x180005243  jz      loc_180005438
0x180005249  test    byte ptr [rcx+1Ch], 8
0x18000524d  jz      loc_180005438
0x180005253  lea     edx, [rax+14h]
0x180005256  jmp     loc_1800053D6
0x18000525b  mov     rcx, [rbp+phPrinter]; hPrinter
0x18000525f  lea     rax, [rbp+cbBuf]
0x180005263  xor     edx, edx; pEnvironment
0x180005265  mov     [rsp+50h+var_28], rax; pcbNeeded
0x18000526a  mov     r9, rsi; pDriverInfo
0x18000526d  mov     dword ptr [rsp+50h+pcbNeeded], ebx; cbBuf
0x180005271  lea     r8d, [rdx+8]; Level
0x180005275  call    cs:__imp_GetPrinterDriverA
0x18000527b  test    eax, eax
0x18000527d  jnz     loc_180005347
0x180005283  call    cs:__imp_GetLastError
0x180005289  cmp     eax, 7Ah ; 'z'
0x18000528c  jnz     loc_18000533D
0x180005292  mov     rcx, rsi; hMem
0x180005295  call    cs:__imp_LocalFree
0x18000529b  mov     edx, [rbp+cbBuf]; uBytes
0x18000529e  xor     ecx, ecx; uFlags
0x1800052a0  call    cs:__imp_LocalAlloc
0x1800052a6  mov     rsi, rax
0x1800052a9  test    rax, rax
0x1800052ac  jnz     short loc_1800052D0
0x1800052ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052b5  cmp     rcx, r12
0x1800052b8  jz      loc_180005438
0x1800052be  test    byte ptr [rcx+1Ch], 8
0x1800052c2  jz      loc_180005438
0x1800052c8  lea     edx, [rax+15h]
0x1800052cb  jmp     loc_1800053D6
0x1800052d0  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800052d4  lea     rax, [rbp+cbBuf]
0x1800052d8  mov     [rsp+50h+var_28], rax; pcbNeeded
0x1800052dd  xor     edx, edx; pEnvironment
0x1800052df  mov     eax, [rbp+cbBuf]
0x1800052e2  mov     r9, rsi; pDriverInfo
0x1800052e5  mov     dword ptr [rsp+50h+pcbNeeded], eax; cbBuf
0x1800052e9  lea     r8d, [rdx+8]; Level
0x1800052ed  call    cs:__imp_GetPrinterDriverA
0x1800052f3  test    eax, eax
0x1800052f5  jnz     short loc_180005347
0x1800052f7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800052fe  cmp     rbx, r12
0x180005301  jz      short loc_180005326
0x180005303  test    byte ptr [rbx+1Ch], 8
0x180005307  jz      short loc_180005326
0x180005309  mov     rbx, [rbx+10h]
0x18000530d  call    cs:__imp_GetLastError
0x180005313  mov     edx, 16h
0x180005318  mov     r8, r13
0x18000531b  mov     r9d, eax
0x18000531e  mov     rcx, rbx
0x180005321  call    WPP_SF_d
0x180005326  mov     rcx, rdi; hMem
0x180005329  call    cs:__imp_LocalFree
0x18000532f  mov     rcx, rsi; hMem
0x180005332  call    cs:__imp_LocalFree
0x180005338  jmp     loc_180005194
0x18000533d  mov     ebx, 4E26h
0x180005342  jmp     loc_18000543D
0x180005347  mov     eax, [rsi+0A8h]
0x18000534d  mov     rcx, rsi; hMem
0x180005350  and     eax, 2
0x180005353  mov     [r14+104h], eax
0x18000535a  call    cs:__imp_LocalFree
0x180005360  mov     rax, [rdi+38h]
0x180005364  test    rax, rax
0x180005367  jnz     loc_180005456
0x18000536d  mov     r8, [r14+58h]; pDeviceName
0x180005371  xor     r9d, r9d; pDevModeOutput
0x180005374  mov     rdx, [rbp+phPrinter]; hPrinter
0x180005378  xor     ecx, ecx; hWnd
0x18000537a  mov     dword ptr [rsp+50h+var_28], eax; fMode
0x18000537e  mov     [rsp+50h+pcbNeeded], rax; pDevModeInput
0x180005383  call    cs:__imp_DocumentPropertiesA
0x180005389  test    eax, eax
0x18000538b  jns     short loc_1800053AE
0x18000538d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005394  cmp     rcx, r12
0x180005397  jz      loc_180005438
0x18000539d  test    byte ptr [rcx+1Ch], 8
0x1800053a1  jz      loc_180005438
0x1800053a7  mov     edx, 17h
0x1800053ac  jmp     short loc_1800053D6
0x1800053ae  movsxd  rdx, eax; uBytes
0x1800053b1  xor     ecx, ecx; uFlags
0x1800053b3  call    cs:__imp_LocalAlloc
0x1800053b9  mov     rbx, rax
0x1800053bc  test    rax, rax
0x1800053bf  jnz     short loc_1800053E4
0x1800053c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053c8  cmp     rcx, r12
0x1800053cb  jz      short loc_180005438
0x1800053cd  test    byte ptr [rcx+1Ch], 8
0x1800053d1  jz      short loc_180005438
0x1800053d3  lea     edx, [rax+18h]
0x1800053d6  mov     rcx, [rcx+10h]
0x1800053da  mov     r8, r13
0x1800053dd  call    WPP_SF_
0x1800053e2  jmp     short loc_180005438
0x1800053e4  mov     r8, [r14+58h]; pDeviceName
0x1800053e8  mov     r9, rbx; pDevModeOutput
0x1800053eb  mov     rdx, [rbp+phPrinter]; hPrinter
0x1800053ef  xor     ecx, ecx; hWnd
0x1800053f1  mov     dword ptr [rsp+50h+var_28], 2; fMode
0x1800053f9  mov     [rsp+50h+pcbNeeded], 0; pDevModeInput
0x180005402  call    cs:__imp_DocumentPropertiesA
0x180005408  test    eax, eax
0x18000540a  jns     short loc_18000544D
0x18000540c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005413  cmp     rcx, r12
0x180005416  jz      short loc_18000542F
0x180005418  test    byte ptr [rcx+1Ch], 8
0x18000541c  jz      short loc_18000542F
0x18000541e  mov     rcx, [rcx+10h]
0x180005422  mov     edx, 19h
0x180005427  mov     r8, r13
0x18000542a  call    WPP_SF_
0x18000542f  mov     rcx, rbx; hMem
0x180005432  call    cs:__imp_LocalFree
0x180005438  mov     ebx, 4E21h
0x18000543d  mov     rcx, rdi; hMem
0x180005440  call    cs:__imp_LocalFree
0x180005446  mov     eax, ebx
0x180005448  jmp     loc_180005526
0x18000544d  mov     [rdi+38h], rbx
0x180005451  mov     rax, rbx
0x180005454  jmp     short loc_180005458
0x180005456  xor     ebx, ebx
0x180005458  mov     word ptr [rax+36h], 1
0x18000545e  mov     rcx, r14
0x180005461  lea     rax, Str2; "RAW"
0x180005468  mov     dword ptr [r14+0BCh], 0
0x180005473  mov     [rbp+pDefault.pDatatype], rax
0x180005477  call    ShutdownPrinter
0x18000547c  mov     rax, [rdi+38h]
0x180005480  lea     r8, [rbp+pDefault]; pDefault
0x180005484  mov     rcx, [r14+58h]; pPrinterName
0x180005488  lea     rdx, [rbp+phPrinter]; phPrinter
0x18000548c  mov     [rbp+pDefault.pDevMode], rax
0x180005490  mov     [rbp+pDefault.DesiredAccess], 0Ch
0x180005497  call    cs:__imp_OpenPrinterA
0x18000549d  test    eax, eax
0x18000549f  jnz     short loc_1800054DB
0x1800054a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054a8  cmp     rcx, r12
0x1800054ab  jz      short loc_1800054C2
0x1800054ad  test    byte ptr [rcx+1Ch], 8
0x1800054b1  jz      short loc_1800054C2
0x1800054b3  mov     rcx, [rcx+10h]
0x1800054b7  lea     edx, [rax+1Ah]
0x1800054ba  mov     r8, r13
0x1800054bd  call    WPP_SF_
0x1800054c2  mov     rcx, rdi; hMem
0x1800054c5  call    cs:__imp_LocalFree
0x1800054cb  test    rbx, rbx
0x1800054ce  jz      short loc_180005521
0x1800054d0  mov     rcx, rbx; hMem
0x1800054d3  call    cs:__imp_LocalFree
0x1800054d9  jmp     short loc_180005521
0x1800054db  test    rbx, rbx
0x1800054de  jz      short loc_1800054E9
0x1800054e0  mov     rcx, rbx; hMem
0x1800054e3  call    cs:__imp_LocalFree
0x1800054e9  mov     rcx, rdi; hMem
0x1800054ec  call    cs:__imp_LocalFree
0x1800054f2  mov     rax, [rbp+phPrinter]
0x1800054f6  mov     [r14+60h], rax
0x1800054fa  xor     eax, eax
0x1800054fc  jmp     short loc_180005526
  ... truncated ...
```
