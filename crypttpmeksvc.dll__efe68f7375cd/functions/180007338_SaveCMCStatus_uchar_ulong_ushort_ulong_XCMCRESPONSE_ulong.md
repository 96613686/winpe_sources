# _SaveCMCStatus(uchar *,ulong,ushort *,ulong,_XCMCRESPONSE * *,ulong *)

- ea: `0x180007338`
- end: `0x180007712`
- name: `?_SaveCMCStatus@@YAJPEAEKPEAGKPEAPEAU_XCMCRESPONSE@@PEAK@Z`
- size: `986`
- prototype: `__int64 __fastcall(BYTE *pbEncoded, DWORD cbEncoded, unsigned __int16 *, __int64, struct _XCMCRESPONSE **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007180`

## callees

- `0x180003750`
- `0x180006f84`
- `0x1800072c0`
- `0x180007338`
- `0x18000a7c2`

## import_xrefs

- `CRYPT32!CryptDecodeObjectEx` at `0x1800073dd`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800073dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800076f2`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000747e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000747e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000745e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007548`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007579`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000745e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007548`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e7`

## pseudocode

```c
__int64 __fastcall _SaveCMCStatus(
        BYTE *pbEncoded,
        DWORD cbEncoded,
        unsigned __int16 *a3,
        __int64 a4,
        struct _XCMCRESPONSE **a5,
        unsigned int *a6)
{
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // r14
  void *v8; // r12
  unsigned __int64 v9; // r13
  const char *v10; // r8
  unsigned int v11; // ecx
  int v12; // r9d
  unsigned int appended; // ebx
  __int64 v14; // rdx
  signed int LastError; // eax
  unsigned int *v16; // r15
  __int64 i; // rax
  __int64 v18; // r9
  unsigned int v19; // eax
  struct _XCMCRESPONSE *v20; // rax
  struct _XCMCRESPONSE **v21; // rbx
  struct _XCMCRESPONSE *v22; // rsi
  __int64 v23; // r15
  _QWORD *v24; // rax
  const unsigned __int16 *v25; // rcx
  unsigned int v26; // eax
  unsigned int *v27; // rcx
  HLOCAL v28; // rax
  _QWORD *v29; // rax
  DWORD pcbStructInfo; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL pvStructInfo; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-18h] BYREF
  __int64 v35; // [rsp+60h] [rbp-10h]
  int v37; // [rsp+C8h] [rbp+58h]

  v6 = a3;
  pvStructInfo = 0;
  v7 = 0;
  pcbStructInfo = 0;
  v8 = 0;
  hMem = 0;
  v9 = -1;
  v33 = 0;
  do
    ++v9;
  while ( a3[v9] );
  if ( v9 >= 0x104 )
  {
    v10 = "ERROR: cwcTmp >= cwcBodyPartBuffer. Hr=%x\n";
    v11 = 14160576;
LABEL_5:
    v12 = -2147024362;
LABEL_6:
    appended = v12;
    ekTraceFmt(v11, 1u, v10);
    goto LABEL_45;
  }
  if ( CryptDecodeObjectEx(1u, (LPCSTR)0x3D, pbEncoded, cbEncoded, 0x8000u, 0, &pvStructInfo, &pcbStructInfo) )
  {
    v16 = a6;
    for ( i = 0; ; i = (unsigned int)(v37 + 1) )
    {
      v37 = i;
      if ( (unsigned int)i >= *((_DWORD *)pvStructInfo + 1) )
      {
        appended = 0;
        goto LABEL_45;
      }
      v18 = *((_QWORD *)pvStructInfo + 1);
      v35 = i;
      appended = _AppendBodyPart(v6, v14, v9, *(_DWORD *)(v18 + 4 * i));
      if ( appended )
      {
        ekTraceFmt(0xF812C0u, 1u, "ERROR: _AppendBodyPart Hr=%x\n");
        goto LABEL_45;
      }
      v19 = *v16;
      if ( *v16 > 0x4000000 )
      {
        v10 = "ERROR: CMCPARSE_MAXELEMENT < *pcResponse. Hr=%x\n";
        v11 = 17175232;
        goto LABEL_5;
      }
      if ( v19 )
      {
        v21 = a5;
        v20 = (struct _XCMCRESPONSE *)LocalReAlloc(*a5, 104LL * (v19 + 1), 0x42u);
      }
      else
      {
        v20 = (struct _XCMCRESPONSE *)LocalAlloc(appended + 64, appended + 104);
        v21 = a5;
      }
      v22 = v20;
      if ( !v20 )
        break;
      *v21 = v20;
      v23 = 104LL * *v16;
      *(_DWORD *)((char *)v20 + v23 + 96) = 0;
      *(_DWORD *)((char *)v20 + v23) = *(_DWORD *)pvStructInfo;
      *(_DWORD *)((char *)v20 + v23 + 4) = *(_DWORD *)(*((_QWORD *)pvStructInfo + 1) + 4 * v35);
      *(_DWORD *)((char *)v20 + v23 + 24) = *((_DWORD *)pvStructInfo + 6);
      if ( *((_DWORD *)pvStructInfo + 6) == 1 )
        *(_DWORD *)((char *)v20 + v23 + 32) = *((_DWORD *)pvStructInfo + 8);
      appended = _DuplicateString(a3 + 1, (unsigned __int16 **)&hMem);
      if ( appended )
      {
        ekTraceFmt(0x13412C0u, 1u, "ERROR:_DuplicateString Hr=%x\n");
        goto LABEL_45;
      }
      v24 = pvStructInfo;
      v25 = (const unsigned __int16 *)*((_QWORD *)pvStructInfo + 2);
      if ( v25 )
      {
        v26 = _DuplicateString(v25, &v33);
        appended = v26;
        if ( v26 )
        {
          ekTraceFmt(0x13D12C0u, 1u, "ERROR:_DuplicateString Hr=%x\n", v26);
          v7 = v33;
          goto LABEL_45;
        }
        v24 = pvStructInfo;
        v7 = v33;
      }
      if ( *((_DWORD *)v24 + 6) == 2 )
      {
        v27 = (unsigned int *)v24[4];
        if ( v27 )
        {
          if ( *((_QWORD *)v27 + 1) && *v27 )
          {
            v28 = LocalAlloc(0, *v27);
            v8 = v28;
            if ( !v28 )
            {
              appended = -2147024882;
              ekTraceFmt(0x14E12C0u, 1u, "ERROR: LocalAlloc Hr=%x\n");
              goto LABEL_45;
            }
            memcpy_0(v28, *(const void **)(*((_QWORD *)pvStructInfo + 4) + 8LL), **((unsigned int **)pvStructInfo + 4));
          }
          v29 = LocalAlloc(0x40u, 0x18u);
          *(_QWORD *)((char *)v22 + v23 + 32) = v29;
          if ( !v29 )
          {
            appended = -2147024882;
            ekTraceFmt(0x15C12C0u, 1u, "ERROR: LocalAlloc Hr=%x\n");
            goto LABEL_45;
          }
          v14 = *((_QWORD *)pvStructInfo + 4);
          v29[2] = *(_QWORD *)(v14 + 16);
          if ( v8 )
          {
            *(_QWORD *)(*(_QWORD *)((char *)v22 + v23 + 32) + 8LL) = v8;
            v8 = 0;
            **(_DWORD **)((char *)v22 + v23 + 32) = **((_DWORD **)pvStructInfo + 4);
          }
        }
      }
      v6 = a3;
      *(_QWORD *)((char *)v22 + v23 + 40) = hMem;
      *(_QWORD *)((char *)v22 + v23 + 16) = v7;
      v16 = a6;
      v7 = 0;
      hMem = 0;
      v33 = 0;
      ++*a6;
    }
    v10 = "ERROR: LocalAlloc Hr=%x\n";
    v11 = 18551488;
    v12 = -2147024882;
    if ( *v16 )
    {
      v10 = "ERROR:LocalReAlloc Hr=%x\n";
      v11 = 18813632;
    }
    goto LABEL_6;
  }
  LastError = GetLastError();
  appended = LastError;
  if ( LastError > 0 )
    appended = (unsigned __int16)LastError | 0x80070000;
  ekTraceFmt(0xEB12C0u, 1u, "ERROR: CryptDecodeObjectEx. Hr=%x\n");
LABEL_45:
  a3[(unsigned int)v9] = 0;
  if ( hMem )
    LocalFree(hMem);
  if ( v7 )
    LocalFree(v7);
  if ( v8 )
    LocalFree(v8);
  if ( pvStructInfo )
    LocalFree(pvStructInfo);
  return appended;
}

```

## disassembly

```asm
0x180007338  mov     [rsp-38h+arg_0], rbx
0x18000733d  mov     [rsp-38h+arg_18], r9d
0x180007342  mov     [rsp-38h+arg_10], r8
0x180007347  push    rbp
0x180007348  push    rsi
0x180007349  push    rdi
0x18000734a  push    r12
0x18000734c  push    r13
0x18000734e  push    r14
0x180007350  push    r15
0x180007352  mov     rbp, rsp
0x180007355  sub     rsp, 70h
0x180007359  xor     esi, esi
0x18000735b  mov     rbx, r8
0x18000735e  mov     [rbp+var_28], rsi
0x180007362  mov     r14d, esi
0x180007365  mov     [rbp+var_30], esi
0x180007368  mov     r12d, esi
0x18000736b  mov     [rbp+hMem], rsi
0x18000736f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180007373  mov     [rbp+var_20], rsi
0x180007377  inc     r13
0x18000737a  cmp     [r8+r13*2], si
0x18000737f  jnz     short loc_180007377
0x180007381  cmp     r13, 104h
0x180007388  jb      short loc_1800073AE
0x18000738a  lea     r8, aErrorCwctmpCwc; "ERROR: cwcTmp >= cwcBodyPartBuffer. Hr="...
0x180007391  mov     edx, 1; unsigned int
0x180007396  mov     ecx, 0D812C0h; unsigned int
0x18000739b  mov     r9d, 80070216h
0x1800073a1  mov     ebx, r9d
0x1800073a4  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800073a9  jmp     loc_1800076B3
0x1800073ae  mov     r9d, edx; cbEncoded
0x1800073b1  lea     rax, [rbp+var_30]
0x1800073b5  mov     [rsp+70h+pcbStructInfo], rax; pcbStructInfo
0x1800073ba  mov     edx, 3Dh ; '='; lpszStructType
0x1800073bf  lea     rax, [rbp+var_28]
0x1800073c3  mov     r8, rcx; pbEncoded
0x1800073c6  mov     [rsp+70h+pvStructInfo], rax; pvStructInfo
0x1800073cb  mov     [rsp+70h+pDecodePara], rsi; pDecodePara
0x1800073d0  lea     edi, [rdx-3Ch]
0x1800073d3  mov     [rsp+70h+dwFlags], 8000h; dwFlags
0x1800073db  mov     ecx, edi; dwCertEncodingType
0x1800073dd  call    cs:__imp_CryptDecodeObjectEx
0x1800073e3  test    eax, eax
0x1800073e5  jnz     short loc_18000740F
0x1800073e7  call    cs:__imp_GetLastError
0x1800073ed  mov     ebx, eax
0x1800073ef  test    eax, eax
0x1800073f1  jle     short loc_1800073FC
0x1800073f3  movzx   ebx, ax
0x1800073f6  or      ebx, 80070000h
0x1800073fc  mov     r9d, ebx
0x1800073ff  lea     r8, aErrorCryptdeco_1; "ERROR: CryptDecodeObjectEx. Hr=%x\n"
0x180007406  mov     edx, edi
0x180007408  mov     ecx, 0EB12C0h
0x18000740d  jmp     short loc_1800073A4
0x18000740f  mov     r15, [rbp+arg_28]
0x180007413  mov     eax, esi
0x180007415  mov     rcx, [rbp+var_28]
0x180007419  mov     [rbp+arg_18], eax
0x18000741c  cmp     eax, [rcx+4]
0x18000741f  jnb     loc_1800076B1
0x180007425  mov     r9, [rcx+8]
0x180007429  mov     r8d, r13d; unsigned int
0x18000742c  mov     rcx, rbx; unsigned __int16 *
0x18000742f  mov     [rbp+var_10], rax
0x180007433  mov     r9d, [r9+rax*4]; unsigned int
0x180007437  call    ?_AppendBodyPart@@YAJPEAGKKK@Z; _AppendBodyPart(ushort *,ulong,ulong,ulong)
0x18000743c  mov     ebx, eax
0x18000743e  test    eax, eax
0x180007440  jnz     loc_18000769B
0x180007446  mov     eax, [r15]
0x180007449  cmp     eax, 4000000h
0x18000744e  ja      loc_180007688
0x180007454  test    eax, eax
0x180007456  jnz     short loc_18000746A
0x180007458  lea     edx, [rbx+68h]; uBytes
0x18000745b  lea     ecx, [rbx+40h]; uFlags
0x18000745e  call    cs:__imp_LocalAlloc
0x180007464  mov     rbx, [rbp+arg_20]
0x180007468  jmp     short loc_180007484
0x18000746a  mov     rbx, [rbp+arg_20]
0x18000746e  lea     ecx, [rax+1]
0x180007471  imul    rdx, rcx, 68h ; 'h'; uBytes
0x180007475  mov     rcx, [rbx]; hMem
0x180007478  mov     r8d, 42h ; 'B'; uFlags
0x18000747e  call    cs:__imp_LocalReAlloc
0x180007484  mov     rsi, rax
0x180007487  test    rax, rax
0x18000748a  jz      loc_180007657
0x180007490  mov     [rbx], rax
0x180007493  mov     eax, [r15]
0x180007496  imul    r15, rax, 68h ; 'h'
0x18000749a  mov     dword ptr [r15+rsi+60h], 0
0x1800074a3  mov     rax, [rbp+var_28]
0x1800074a7  mov     ecx, [rax]
0x1800074a9  mov     [r15+rsi], ecx
0x1800074ad  mov     rax, [rbp+var_28]
0x1800074b1  mov     rcx, [rax+8]
0x1800074b5  mov     rax, [rbp+var_10]
0x1800074b9  mov     eax, [rcx+rax*4]
0x1800074bc  mov     [r15+rsi+4], eax
0x1800074c1  mov     rax, [rbp+var_28]
0x1800074c5  mov     ecx, [rax+18h]
0x1800074c8  mov     [r15+rsi+18h], ecx
0x1800074cd  mov     rax, [rbp+var_28]
0x1800074d1  cmp     [rax+18h], edi
0x1800074d4  jnz     short loc_1800074DE
0x1800074d6  mov     eax, [rax+20h]
0x1800074d9  mov     [r15+rsi+20h], eax
0x1800074de  mov     rcx, [rbp+arg_10]
0x1800074e2  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x1800074e6  add     rcx, 2; Src
0x1800074ea  call    ?_DuplicateString@@YAJPEBGPEAPEAG@Z; _DuplicateString(ushort const *,ushort * *)
0x1800074ef  mov     ebx, eax
0x1800074f1  test    eax, eax
0x1800074f3  jnz     loc_18000763D
0x1800074f9  mov     rax, [rbp+var_28]
0x1800074fd  mov     rcx, [rax+10h]; Src
0x180007501  test    rcx, rcx
0x180007504  jz      short loc_180007521
0x180007506  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18000750a  call    ?_DuplicateString@@YAJPEBGPEAPEAG@Z; _DuplicateString(ushort const *,ushort * *)
0x18000750f  mov     ebx, eax
0x180007511  test    eax, eax
0x180007513  jnz     loc_1800075F3
0x180007519  mov     rax, [rbp+var_28]
0x18000751d  mov     r14, [rbp+var_20]
0x180007521  cmp     dword ptr [rax+18h], 2
0x180007525  jnz     loc_1800075BF
0x18000752b  mov     rcx, [rax+20h]
0x18000752f  test    rcx, rcx
0x180007532  jz      loc_1800075BF
0x180007538  cmp     qword ptr [rcx+8], 0
0x18000753d  jz      short loc_180007571
0x18000753f  cmp     dword ptr [rcx], 0
0x180007542  jz      short loc_180007571
0x180007544  mov     edx, [rcx]; uBytes
0x180007546  xor     ecx, ecx; uFlags
0x180007548  call    cs:__imp_LocalAlloc
0x18000754e  mov     r12, rax
0x180007551  test    rax, rax
0x180007554  jz      loc_18000760F
0x18000755a  mov     rcx, [rbp+var_28]
0x18000755e  mov     rdx, [rcx+20h]
0x180007562  mov     rcx, rax; void *
0x180007565  mov     r8d, [rdx]; Size
0x180007568  mov     rdx, [rdx+8]; Src
0x18000756c  call    memcpy_0
0x180007571  mov     edx, 18h; uBytes
0x180007576  lea     ecx, [rdx+28h]; uFlags
0x180007579  call    cs:__imp_LocalAlloc
0x18000757f  mov     [r15+rsi+20h], rax
0x180007584  test    rax, rax
0x180007587  jz      loc_180007626
0x18000758d  mov     rcx, [rbp+var_28]
0x180007591  mov     rdx, [rcx+20h]
0x180007595  mov     rcx, [rdx+10h]
0x180007599  mov     [rax+10h], rcx
0x18000759d  test    r12, r12
0x1800075a0  jz      short loc_1800075BF
0x1800075a2  mov     rax, [r15+rsi+20h]
0x1800075a7  mov     [rax+8], r12
0x1800075ab  xor     r12d, r12d
0x1800075ae  mov     rax, [rbp+var_28]
0x1800075b2  mov     rcx, [r15+rsi+20h]
0x1800075b7  mov     rax, [rax+20h]
0x1800075bb  mov     eax, [rax]
0x1800075bd  mov     [rcx], eax
0x1800075bf  mov     rax, [rbp+hMem]
0x1800075c3  mov     rbx, [rbp+arg_10]
0x1800075c7  mov     [r15+rsi+28h], rax
0x1800075cc  mov     eax, [rbp+arg_18]
0x1800075cf  mov     [r15+rsi+10h], r14
0x1800075d4  xor     esi, esi
0x1800075d6  mov     r15, [rbp+arg_28]
0x1800075da  mov     r14d, esi
0x1800075dd  mov     [rbp+hMem], 0
0x1800075e5  mov     [rbp+var_20], rsi
0x1800075e9  add     [r15], edi
0x1800075ec  add     eax, edi
0x1800075ee  jmp     loc_180007415
0x1800075f3  mov     r9d, eax
0x1800075f6  lea     r8, aErrorDuplicate; "ERROR:_DuplicateString Hr=%x\n"
0x1800075fd  mov     edx, edi; unsigned int
0x1800075ff  mov     ecx, 13D12C0h; unsigned int
0x180007604  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180007609  mov     r14, [rbp+var_20]
0x18000760d  jmp     short loc_180007653
0x18000760f  mov     r9d, 8007000Eh
0x180007615  lea     r8, aErrorLocalallo; "ERROR: LocalAlloc Hr=%x\n"
0x18000761c  mov     ebx, r9d
0x18000761f  mov     ecx, 14E12C0h
0x180007624  jmp     short loc_18000764C
0x180007626  mov     r9d, 8007000Eh
0x18000762c  lea     r8, aErrorLocalallo; "ERROR: LocalAlloc Hr=%x\n"
0x180007633  mov     ebx, r9d
0x180007636  mov     ecx, 15C12C0h
0x18000763b  jmp     short loc_18000764C
0x18000763d  mov     r9d, eax
0x180007640  lea     r8, aErrorDuplicate; "ERROR:_DuplicateString Hr=%x\n"
0x180007647  mov     ecx, 13412C0h; unsigned int
0x18000764c  mov     edx, edi; unsigned int
0x18000764e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180007653  xor     esi, esi
0x180007655  jmp     short loc_1800076B3
0x180007657  lea     rax, aErrorLocalreal; "ERROR:LocalReAlloc Hr=%x\n"
0x18000765e  xor     esi, esi
0x180007660  cmp     [r15], esi
0x180007663  lea     r8, aErrorLocalallo; "ERROR: LocalAlloc Hr=%x\n"
0x18000766a  mov     ecx, 11B12C0h
0x18000766f  mov     r9d, 8007000Eh
0x180007675  cmovnz  r8, rax
0x180007679  mov     edx, edi
0x18000767b  mov     eax, 11F12C0h
0x180007680  cmovnz  ecx, eax
0x180007683  jmp     loc_1800073A1
0x180007688  lea     r8, aErrorCmcparseM; "ERROR: CMCPARSE_MAXELEMENT < *pcRespons"...
0x18000768f  mov     edx, edi
0x180007691  mov     ecx, 10612C0h
0x180007696  jmp     loc_18000739B
0x18000769b  mov     r9d, eax
0x18000769e  lea     r8, aErrorAppendbod; "ERROR: _AppendBodyPart Hr=%x\n"
0x1800076a5  mov     edx, edi
0x1800076a7  mov     ecx, 0F812C0h
0x1800076ac  jmp     loc_1800073A4
0x1800076b1  mov     ebx, esi
0x1800076b3  mov     rcx, [rbp+arg_10]
0x1800076b7  mov     edx, r13d
0x1800076ba  mov     [rcx+rdx*2], si
0x1800076be  mov     rcx, [rbp+hMem]; hMem
0x1800076c2  test    rcx, rcx
0x1800076c5  jz      short loc_1800076CD
0x1800076c7  call    cs:__imp_LocalFree
0x1800076cd  test    r14, r14
0x1800076d0  jz      short loc_1800076DB
0x1800076d2  mov     rcx, r14; hMem
0x1800076d5  call    cs:__imp_LocalFree
0x1800076db  test    r12, r12
0x1800076de  jz      short loc_1800076E9
0x1800076e0  mov     rcx, r12; hMem
0x1800076e3  call    cs:__imp_LocalFree
0x1800076e9  mov     rcx, [rbp+var_28]; hMem
0x1800076ed  test    rcx, rcx
0x1800076f0  jz      short loc_1800076F8
0x1800076f2  call    cs:__imp_LocalFree
0x1800076f8  mov     eax, ebx
0x1800076fa  mov     rbx, [rsp+70h+arg_0]
0x180007702  add     rsp, 70h
0x180007706  pop     r15
0x180007708  pop     r14
0x18000770a  pop     r13
0x18000770c  pop     r12
0x18000770e  pop     rdi
0x18000770f  pop     rsi
0x180007710  pop     rbp
0x180007711  retn
```
