# _SaveCMCAttributeData(uchar *,ulong,ushort *,ulong,_XCMCRESPONSE *,ulong)

- ea: `0x180005d44`
- end: `0x18000607a`
- name: `?_SaveCMCAttributeData@@YAJPEAEKPEAGKPEAU_XCMCRESPONSE@@K@Z`
- size: `822`
- prototype: `__int64 __fastcall(BYTE *pbEncoded, DWORD cbEncoded, unsigned __int16 *, __int64, struct _XCMCRESPONSE *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007180`

## callees

- `0x180003750`
- `0x180005d44`
- `0x180006f84`

## import_xrefs

- `CRYPT32!CryptDecodeObjectEx` at `0x180005dd2`
- `CRYPT32!CryptDecodeObjectEx` at `0x180005f44`
- `CRYPT32!CryptDecodeObjectEx` at `0x180005dd2`
- `CRYPT32!CryptDecodeObjectEx` at `0x180005f44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006050`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000605a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006050`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000605a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fd6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180005efb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180005efb`

## pseudocode

```c
__int64 __fastcall _SaveCMCAttributeData(
        BYTE *pbEncoded,
        DWORD cbEncoded,
        unsigned __int16 *a3,
        __int64 a4,
        struct _XCMCRESPONSE *a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  unsigned __int64 v8; // r12
  __int64 v9; // r9
  const char *v10; // r8
  unsigned int v11; // ecx
  signed int LastError; // eax
  LPCWSTR *v13; // r14
  const char **v14; // rsi
  const char **v15; // rax
  unsigned int i; // ecx
  const char *v17; // r9
  char **v18; // r15
  char *v19; // rax
  signed __int64 v20; // r9
  unsigned int v21; // edx
  unsigned int v22; // r8d
  unsigned int appended; // eax
  __int64 v24; // rcx
  signed int v25; // eax
  HLOCAL pvStructInfo; // [rsp+40h] [rbp-10h] BYREF
  const char **v28; // [rsp+48h] [rbp-8h]
  HLOCAL hMem; // [rsp+A0h] [rbp+50h] BYREF
  DWORD pcbStructInfo; // [rsp+A8h] [rbp+58h] BYREF

  v6 = 0;
  hMem = 0;
  v8 = -1;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 >= 0x104 )
  {
    v9 = 2147942934LL;
    v10 = "ERROR: cwcTmp >= cwcBodyPartBuffer. Hr=%x\n";
    v11 = 31462080;
    goto LABEL_45;
  }
  if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x3F, pbEncoded, cbEncoded, 0x8000u, 0, &hMem, &pcbStructInfo) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    ekTraceFmt(0x1F312C0u, 1u, "ERROR: CryptDecodeObjectEx. Hr=%x\n", v6);
    goto LABEL_46;
  }
  if ( *(_DWORD *)hMem )
  {
    v10 = "ERROR: 0 != pcmcAttrib->dwCmcDataReference Hr=%x\n";
    v11 = 33166016;
    goto LABEL_44;
  }
  if ( *((_DWORD *)hMem + 1) != 1 )
  {
    v10 = "ERROR: 1 != pcmcAttrib->cCertReference Hr=%x\n";
    v11 = 33559232;
    goto LABEL_44;
  }
  v13 = 0;
  v14 = (const char **)*((_QWORD *)hMem + 3);
  v15 = &v14[3 * *((unsigned int *)hMem + 4)];
  v28 = v15;
LABEL_14:
  if ( v14 < v15 )
  {
    for ( i = 0; ; ++i )
    {
      v17 = *v14;
      if ( i >= 6 )
        break;
      v18 = &(&off_180012000)[4 * i];
      v19 = *v18;
      v20 = v17 - *v18;
      do
      {
        v21 = (unsigned __int8)v19[v20];
        v22 = (unsigned __int8)*v19 - v21;
        if ( v22 )
          break;
        ++v19;
      }
      while ( v21 );
      if ( !v22 )
      {
        if ( *((_DWORD *)v14 + 2) != 1 )
        {
          v10 = "ERROR: 1 != pAttr->cValue Hr=%x\n";
          v11 = 35132096;
          goto LABEL_44;
        }
        if ( *(_DWORD *)v14[2] >= 0x4000000u )
        {
          v9 = 2147942934LL;
          v10 = "ERROR: CMCPARSE_MAXELEMENT Hr=%x\n";
          v11 = 35590848;
          goto LABEL_45;
        }
        appended = _AppendBodyPart(a3, v21, v8, **((_DWORD **)hMem + 1));
        v6 = appended;
        if ( appended )
        {
          ekTraceFmt(0x22F12C0u, 1u, "ERROR: _AppendBodyPart Hr=%x\n", appended);
          goto LABEL_46;
        }
        v6 = 0;
        if ( !v13 )
        {
          while ( v6 < a6 )
          {
            v13 = (LPCWSTR *)((char *)a5 + 104 * v6);
            if ( !lstrcmpW(v13[5], a3 + 1) )
            {
              v6 = 0;
              if ( v13 )
                goto LABEL_30;
              break;
            }
            ++v6;
          }
          v10 = "ERROR: _FindCMCResponse Hr=%x\n";
          v11 = 37491392;
LABEL_44:
          v9 = 2147942413LL;
LABEL_45:
          v6 = v9;
          ekTraceFmt(v11, 1u, v10, v9);
          goto LABEL_46;
        }
LABEL_30:
        if ( !CryptDecodeObjectEx(
                1u,
                v18[2],
                *((const BYTE **)v14[2] + 1),
                *(_DWORD *)v14[2],
                0x8000u,
                0,
                &pvStructInfo,
                &pcbStructInfo) )
        {
          v25 = GetLastError();
          v6 = v25;
          if ( v25 > 0 )
            v6 = (unsigned __int16)v25 | 0x80070000;
          ekTraceFmt(0x24C12C0u, 1u, "ERROR: CryptDecodeObjectEx. Hr=%x\n", v6);
          goto LABEL_46;
        }
        v24 = *((unsigned int *)v18 + 2);
        if ( *(LPCWSTR *)((char *)v13 + v24) || ((_DWORD)v13[12] & (_DWORD)v18[3]) != 0 )
        {
          v10 = "ERROR: Attributes Hr=%x\n";
          v11 = 39326400;
          goto LABEL_44;
        }
        *(LPCWSTR *)((char *)v13 + v24) = (LPCWSTR)pvStructInfo;
        *((_DWORD *)v13 + 24) |= *((_DWORD *)v18 + 6);
        pvStructInfo = 0;
LABEL_35:
        v15 = v28;
        v14 += 3;
        goto LABEL_14;
      }
    }
    ekTraceFmt(0x3C12C0u, 2u, "TRACE: FindDataAttribute not found. Oid=%s\n", v17);
    ekTraceFmt(0x21112C0u, 2u, "TRACE: Skipped attribute: %s\n", *v14);
    goto LABEL_35;
  }
LABEL_46:
  a3[(unsigned int)v8] = 0;
  LocalFree(hMem);
  LocalFree(pvStructInfo);
  return v6;
}

```

## disassembly

```asm
0x180005d44  mov     [rsp-38h+arg_0], rbx
0x180005d49  mov     [rsp-38h+arg_18], r9d
0x180005d4e  push    rbp
0x180005d4f  push    rsi
0x180005d50  push    rdi
0x180005d51  push    r12
0x180005d53  push    r13
0x180005d55  push    r14
0x180005d57  push    r15
0x180005d59  mov     rbp, rsp
0x180005d5c  sub     rsp, 50h
0x180005d60  xor     ebx, ebx
0x180005d62  mov     r13, r8
0x180005d65  mov     [rbp+hMem], rbx
0x180005d69  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005d6d  mov     [rbp+var_10], rbx
0x180005d71  mov     [rbp+arg_18], ebx
0x180005d74  inc     r12
0x180005d77  cmp     [r8+r12*2], bx
0x180005d7c  jnz     short loc_180005D74
0x180005d7e  cmp     r12, 104h
0x180005d85  jb      short loc_180005DA3
0x180005d87  mov     r9d, 80070216h
0x180005d8d  lea     r8, aErrorCwctmpCwc; "ERROR: cwcTmp >= cwcBodyPartBuffer. Hr="...
0x180005d94  mov     edx, 1
0x180005d99  mov     ecx, 1E012C0h
0x180005d9e  jmp     loc_180006039
0x180005da3  mov     r9d, edx; cbEncoded
0x180005da6  lea     rax, [rbp+arg_18]
0x180005daa  mov     [rsp+50h+pcbStructInfo], rax; pcbStructInfo
0x180005daf  mov     edx, 3Fh ; '?'; lpszStructType
0x180005db4  lea     rax, [rbp+hMem]
0x180005db8  mov     r8, rcx; pbEncoded
0x180005dbb  mov     [rsp+50h+pvStructInfo], rax; pvStructInfo
0x180005dc0  mov     [rsp+50h+pDecodePara], rbx; pDecodePara
0x180005dc5  lea     edi, [rdx-3Eh]
0x180005dc8  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x180005dd0  mov     ecx, edi; dwCertEncodingType
0x180005dd2  call    cs:__imp_CryptDecodeObjectEx
0x180005dd8  test    eax, eax
0x180005dda  jnz     short loc_180005E07
0x180005ddc  call    cs:__imp_GetLastError
0x180005de2  mov     ebx, eax
0x180005de4  test    eax, eax
0x180005de6  jle     short loc_180005DF1
0x180005de8  movzx   ebx, ax
0x180005deb  or      ebx, 80070000h
0x180005df1  mov     r9d, ebx
0x180005df4  lea     r8, aErrorCryptdeco_1; "ERROR: CryptDecodeObjectEx. Hr=%x\n"
0x180005dfb  mov     edx, edi
0x180005dfd  mov     ecx, 1F312C0h
0x180005e02  jmp     loc_18000603C
0x180005e07  mov     rax, [rbp+hMem]
0x180005e0b  cmp     [rax], ebx
0x180005e0d  jz      short loc_180005E20
0x180005e0f  lea     r8, aError0Pcmcattr; "ERROR: 0 != pcmcAttrib->dwCmcDataRefere"...
0x180005e16  mov     ecx, 1FA12C0h
0x180005e1b  jmp     loc_180006031
0x180005e20  mov     rax, [rbp+hMem]
0x180005e24  cmp     [rax+4], edi
0x180005e27  jz      short loc_180005E3A
0x180005e29  lea     r8, aError1Pcmcattr; "ERROR: 1 != pcmcAttrib->cCertReference "...
0x180005e30  mov     ecx, 20012C0h
0x180005e35  jmp     loc_180006031
0x180005e3a  mov     rax, [rbp+hMem]
0x180005e3e  mov     r14, rbx
0x180005e41  mov     rsi, [rax+18h]
0x180005e45  mov     eax, [rax+10h]
0x180005e48  lea     rcx, [rax+rax*2]
0x180005e4c  lea     rax, [rsi+rcx*8]
0x180005e50  mov     [rbp+var_8], rax
0x180005e54  cmp     rsi, rax
0x180005e57  jnb     loc_180006041
0x180005e5d  mov     ecx, ebx
0x180005e5f  mov     r9, [rsi]
0x180005e62  cmp     ecx, 6
0x180005e65  jnb     loc_180005F7C
0x180005e6b  mov     r15d, ecx
0x180005e6e  lea     rdx, off_180012000; "1.3.6.1.4.1.311.21.17"
0x180005e75  shl     r15, 5
0x180005e79  add     r15, rdx
0x180005e7c  mov     rax, [r15]
0x180005e7f  sub     r9, rax
0x180005e82  movzx   r8d, byte ptr [rax]
0x180005e86  movzx   edx, byte ptr [rax+r9]; unsigned int
0x180005e8b  sub     r8d, edx
0x180005e8e  jnz     short loc_180005E97
0x180005e90  add     rax, rdi
0x180005e93  test    edx, edx
0x180005e95  jnz     short loc_180005E82
0x180005e97  test    r8d, r8d
0x180005e9a  jz      short loc_180005EA0
0x180005e9c  add     ecx, edi
0x180005e9e  jmp     short loc_180005E5F
0x180005ea0  cmp     [rsi+8], edi
0x180005ea3  jnz     loc_180006025
0x180005ea9  mov     rax, [rsi+10h]
0x180005ead  cmp     dword ptr [rax], 4000000h
0x180005eb3  jnb     loc_180006011
0x180005eb9  mov     rax, [rbp+hMem]
0x180005ebd  mov     r8d, r12d; unsigned int
0x180005ec0  mov     rcx, r13; unsigned __int16 *
0x180005ec3  mov     r9, [rax+8]
0x180005ec7  mov     r9d, [r9]; unsigned int
0x180005eca  call    ?_AppendBodyPart@@YAJPEAGKKK@Z; _AppendBodyPart(ushort *,ulong,ulong,ulong)
0x180005ecf  mov     ebx, eax
0x180005ed1  test    eax, eax
0x180005ed3  jnz     loc_180005FFE
0x180005ed9  xor     ebx, ebx
0x180005edb  test    r14, r14
0x180005ede  jnz     short loc_180005F14
0x180005ee0  cmp     ebx, [rbp+arg_28]
0x180005ee3  jnb     loc_180005FBA
0x180005ee9  mov     eax, ebx
0x180005eeb  lea     rdx, [r13+2]; lpString2
0x180005eef  imul    r14, rax, 68h ; 'h'
0x180005ef3  add     r14, [rbp+arg_20]
0x180005ef7  mov     rcx, [r14+28h]; lpString1
0x180005efb  call    cs:__imp_lstrcmpW
0x180005f01  test    eax, eax
0x180005f03  jz      short loc_180005F09
0x180005f05  add     ebx, edi
0x180005f07  jmp     short loc_180005EE0
0x180005f09  xor     ebx, ebx
0x180005f0b  test    r14, r14
0x180005f0e  jz      loc_180005FBA
0x180005f14  mov     r8, [rsi+10h]
0x180005f18  lea     rax, [rbp+arg_18]
0x180005f1c  mov     rdx, [r15+10h]; lpszStructType
0x180005f20  mov     ecx, edi; dwCertEncodingType
0x180005f22  mov     [rsp+50h+pcbStructInfo], rax; pcbStructInfo
0x180005f27  lea     rax, [rbp+var_10]
0x180005f2b  mov     [rsp+50h+pvStructInfo], rax; pvStructInfo
0x180005f30  mov     r9d, [r8]; cbEncoded
0x180005f33  mov     r8, [r8+8]; pbEncoded
0x180005f37  mov     [rsp+50h+pDecodePara], rbx; pDecodePara
0x180005f3c  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x180005f44  call    cs:__imp_CryptDecodeObjectEx
0x180005f4a  test    eax, eax
0x180005f4c  jz      loc_180005FD6
0x180005f52  mov     ecx, [r15+8]
0x180005f56  cmp     [rcx+r14], rbx
0x180005f5a  jnz     short loc_180005FC8
0x180005f5c  mov     eax, [r14+60h]
0x180005f60  test    [r15+18h], eax
0x180005f64  jnz     short loc_180005FC8
0x180005f66  mov     rax, [rbp+var_10]
0x180005f6a  mov     [rcx+r14], rax
0x180005f6e  mov     eax, [r15+18h]
0x180005f72  or      [r14+60h], eax
0x180005f76  mov     [rbp+var_10], rbx
0x180005f7a  jmp     short loc_180005FAD
0x180005f7c  mov     r15d, 2
0x180005f82  lea     r8, aTraceFinddataa; "TRACE: FindDataAttribute not found. Oid"...
0x180005f89  mov     edx, r15d; unsigned int
0x180005f8c  mov     ecx, 3C12C0h; unsigned int
0x180005f91  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005f96  mov     r9, [rsi]
0x180005f99  lea     r8, aTraceSkippedAt; "TRACE: Skipped attribute: %s\n"
0x180005fa0  mov     edx, r15d; unsigned int
0x180005fa3  mov     ecx, 21112C0h; unsigned int
0x180005fa8  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005fad  mov     rax, [rbp+var_8]
0x180005fb1  add     rsi, 18h
0x180005fb5  jmp     loc_180005E54
0x180005fba  lea     r8, aErrorFindcmcre; "ERROR: _FindCMCResponse Hr=%x\n"
0x180005fc1  mov     ecx, 23C12C0h
0x180005fc6  jmp     short loc_180006031
0x180005fc8  lea     r8, aErrorAttribute; "ERROR: Attributes Hr=%x\n"
0x180005fcf  mov     ecx, 25812C0h
0x180005fd4  jmp     short loc_180006031
0x180005fd6  call    cs:__imp_GetLastError
0x180005fdc  mov     ebx, eax
0x180005fde  test    eax, eax
0x180005fe0  jle     short loc_180005FEB
0x180005fe2  movzx   ebx, ax
0x180005fe5  or      ebx, 80070000h
0x180005feb  mov     r9d, ebx
0x180005fee  lea     r8, aErrorCryptdeco_1; "ERROR: CryptDecodeObjectEx. Hr=%x\n"
0x180005ff5  mov     edx, edi
0x180005ff7  mov     ecx, 24C12C0h
0x180005ffc  jmp     short loc_18000603C
0x180005ffe  mov     r9d, eax
0x180006001  lea     r8, aErrorAppendbod; "ERROR: _AppendBodyPart Hr=%x\n"
0x180006008  mov     edx, edi
0x18000600a  mov     ecx, 22F12C0h
0x18000600f  jmp     short loc_18000603C
0x180006011  mov     r9d, 80070216h
0x180006017  lea     r8, aErrorCmcparseM_0; "ERROR: CMCPARSE_MAXELEMENT Hr=%x\n"
0x18000601e  mov     ecx, 21F12C0h
0x180006023  jmp     short loc_180006037
0x180006025  lea     r8, aError1PattrCva; "ERROR: 1 != pAttr->cValue Hr=%x\n"
0x18000602c  mov     ecx, 21812C0h; unsigned int
0x180006031  mov     r9d, 8007000Dh
0x180006037  mov     edx, edi; unsigned int
0x180006039  mov     ebx, r9d
0x18000603c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180006041  mov     ecx, r12d
0x180006044  xor     eax, eax
0x180006046  mov     [r13+rcx*2+0], ax
0x18000604c  mov     rcx, [rbp+hMem]; hMem
0x180006050  call    cs:__imp_LocalFree
0x180006056  mov     rcx, [rbp+var_10]; hMem
0x18000605a  call    cs:__imp_LocalFree
0x180006060  mov     eax, ebx
0x180006062  mov     rbx, [rsp+50h+arg_0]
0x18000606a  add     rsp, 50h
0x18000606e  pop     r15
0x180006070  pop     r14
0x180006072  pop     r13
0x180006074  pop     r12
0x180006076  pop     rdi
0x180006077  pop     rsi
0x180006078  pop     rbp
0x180006079  retn
```
