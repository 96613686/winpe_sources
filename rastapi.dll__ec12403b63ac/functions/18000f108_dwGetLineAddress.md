# dwGetLineAddress

- ea: `0x18000f108`
- end: `0x18000f534`
- name: `dwGetLineAddress`
- size: `1068`
- prototype: `__int64 __usercall@<rax>(DWORD dwAPIVersion@<ecx>, DWORD dwExtVersion@<edx>, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000de88`

## callees

- `0x18000d92c`
- `0x18000f108`
- `0x180023610`
- `0x180025244`
- `0x18002619c`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x18000f22e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x18000f4ea`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x18000f22e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x18000f4ea`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x18000f1c7`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x18000f1c7`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetIDA` at `0x18000f211`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetIDA` at `0x18000f211`

## string_xrefs

- `0x18000f1d5`: `dwGetLineAddress: lineOpen failed. 0x%x`
- `0x18000f259`: `dwGetLineAddress: RasLineOpen failed 0x%x`

## pseudocode

```c
__int64 __fastcall dwGetLineAddress(
        DWORD dwAPIVersion,
        DWORD dwExtVersion,
        _OWORD *a3,
        unsigned int a4,
        int a5,
        int a6,
        _BYTE *a7,
        _DWORD *a8)
{
  unsigned int ID; // edi
  const CHAR *v13; // rcx
  __int64 dwStringOffset; // rax
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // r8
  int v20; // ebx
  _BYTE *v21; // r10
  _BYTE *v22; // rax
  _QWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+64h] [rbp-9Ch]
  int v27; // [rsp+6Ch] [rbp-94h]
  char v28[5]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+75h] [rbp-8Bh]
  __int16 v30; // [rsp+7Dh] [rbp-83h]
  char v31; // [rsp+7Fh] [rbp-81h]
  char v32[7]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+87h] [rbp-79h]
  char v34; // [rsp+8Fh] [rbp-71h]
  char v35[16]; // [rsp+90h] [rbp-70h] BYREF
  int v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A4h] [rbp-5Ch]
  int v38; // [rsp+ACh] [rbp-54h]
  char v39[6]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+B6h] [rbp-4Ah]
  __int16 v41; // [rsp+BEh] [rbp-42h]
  char v42[5]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+C5h] [rbp-3Bh]
  __int16 v44; // [rsp+CDh] [rbp-33h]
  char v45; // [rsp+CFh] [rbp-31h]
  int v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D4h] [rbp-2Ch]
  int v48; // [rsp+DCh] [rbp-24h]
  int v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E4h] [rbp-1Ch]
  int v51; // [rsp+ECh] [rbp-14h]
  char v52[5]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+F5h] [rbp-Bh]
  __int16 v54; // [rsp+FDh] [rbp-3h]
  char v55; // [rsp+FFh] [rbp-1h]
  char v56[16]; // [rsp+100h] [rbp+0h] BYREF
  char v57[6]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v58; // [rsp+116h] [rbp+16h]
  __int16 v59; // [rsp+11Eh] [rbp+1Eh]
  int v60; // [rsp+120h] [rbp+20h]
  __int64 v61; // [rsp+124h] [rbp+24h]
  int v62; // [rsp+12Ch] [rbp+2Ch]
  int v63; // [rsp+130h] [rbp+30h]
  __int64 v64; // [rsp+134h] [rbp+34h]
  int v65; // [rsp+13Ch] [rbp+3Ch]
  int v66; // [rsp+140h] [rbp+40h]
  __int64 v67; // [rsp+144h] [rbp+44h]
  int v68; // [rsp+14Ch] [rbp+4Ch]
  HLINE hLine[4]; // [rsp+150h] [rbp+50h] BYREF
  struct linecallparams_tag CallParams; // [rsp+160h] [rbp+60h] BYREF
  struct varstring_tag DeviceID; // [rsp+220h] [rbp+120h] BYREF

  hLine[0] = 0;
  memset_0(&CallParams, 0, sizeof(CallParams));
  memset_0(&DeviceID, 0, 0x320u);
  RasTapiTrace("dwGetLineAddress:...");
  if ( a6 )
  {
    ID = RasLineOpen(a4, 1, 2u, 0, (__int64)hLine);
    if ( ID )
    {
      v13 = "dwGetLineAddress: RasLineOpen failed 0x%x";
      goto LABEL_22;
    }
    DeviceID.dwTotalSize = 800;
    ID = RasLineGetID(hLine[0], 0, 0, 1, (wchar_t *)L"LineGuid", &DeviceID.dwTotalSize);
    RasLineClose(hLine[0]);
  }
  else
  {
    ID = lineOpenA(RasLine, a4, hLine, dwAPIVersion, dwExtVersion, 0, 1u, 2u, &CallParams);
    if ( ID )
    {
      v13 = "dwGetLineAddress: lineOpen failed. 0x%x";
LABEL_22:
      RasTapiTrace(v13);
      goto LABEL_23;
    }
    DeviceID.dwTotalSize = 800;
    ID = lineGetIDA(hLine[0], 0, 0, 1u, &DeviceID, "LineGuid");
    if ( ID )
    {
      v13 = "dwGetLineAddress: lineGetID LineGuid failed. 0x%x";
      goto LABEL_22;
    }
    lineClose(hLine[0]);
  }
  hLine[0] = 0;
  if ( DeviceID.dwStringSize < 2 )
  {
    ID = -2147467259;
    v13 = "dwGetLineAddress: pvar->dwStringSize != 0,1 returning 0x%x";
    goto LABEL_22;
  }
  v24[0] = 0x434952454E4547LL;
  strcpy(v35, "FRAMERELAY");
  v24[1] = 0;
  v26 = 0;
  v27 = 0;
  strcpy(v28, "ISDN");
  v29 = 0;
  v30 = 0;
  v31 = 0;
  strcpy(v32, "SERIAL");
  v33 = 0;
  v34 = 0;
  *(_DWORD *)&v35[11] = 0;
  v35[15] = 0;
  v37 = 0;
  v38 = 0;
  strcpy(v39, "SONET");
  v40 = 0;
  v41 = 0;
  strcpy(v42, "SW56");
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v50 = 0;
  v51 = 0;
  strcpy(v52, "IRDA");
  v53 = 0;
  v54 = 0;
  v55 = 0;
  *(_DWORD *)&v56[9] = 0;
  *(_WORD *)&v56[13] = 0;
  v56[15] = 0;
  strcpy(v57, "PPPoE");
  v58 = 0;
  v59 = 0;
  v61 = 0;
  v25 = 3486296;
  v36 = 5067841;
  v46 = 5132374;
  v49 = 5132374;
  strcpy(v56, "PARALLEL");
  v60 = 5132374;
  v62 = 0;
  v64 = 0;
  v65 = 0;
  v67 = 0;
  v68 = 0;
  dwStringOffset = DeviceID.dwStringOffset;
  v63 = 5132374;
  v66 = 4543047;
  *a3 = *(_OWORD *)((char *)&DeviceID.dwTotalSize + DeviceID.dwStringOffset);
  v15 = *(DWORD *)((char *)&DeviceID.dwStringSize + dwStringOffset);
  RasTapiTrace("Media type for index %d");
  v16 = 0;
  v17 = 2147483646;
  v18 = 16;
  if ( v15 <= 0xF )
    v16 = v15;
  v20 = v16;
  v21 = &v24[2 * v16];
  do
  {
    if ( !v17 )
      break;
    if ( !*v21 )
      break;
    *a7++ = *v21++;
    --v17;
    --v18;
  }
  while ( v18 );
  v22 = a7 - 1;
  if ( v18 )
    v22 = a7;
  *v22 = 0;
  RasTapiTrace("MediaType being returned as %s");
  if ( a8 )
    *a8 = v20;
LABEL_23:
  if ( hLine[0] )
  {
    if ( a6 )
      RasLineClose(hLine[0]);
    else
      lineClose(hLine[0]);
  }
  RasTapiTrace("dwGetLineAddress: done. 0x%x");
  RasTapiTrace(" ");
  return ID;
}

```

## disassembly

```asm
0x18000f108  push    rbp
0x18000f10a  push    rbx
0x18000f10b  push    rsi
0x18000f10c  push    rdi
0x18000f10d  push    r12
0x18000f10f  push    r13
0x18000f111  push    r15
0x18000f113  lea     rbp, [rsp-450h]
0x18000f11b  sub     rsp, 550h
0x18000f122  mov     rax, cs:__security_cookie
0x18000f129  xor     rax, rsp
0x18000f12c  mov     [rbp+480h+var_40], rax
0x18000f133  mov     r12, [rbp+480h+arg_30]
0x18000f13a  mov     r13, r8
0x18000f13d  mov     rsi, [rbp+480h+arg_38]
0x18000f144  mov     r15d, edx
0x18000f147  mov     edi, ecx
0x18000f149  mov     [rbp+480h+hLine], 0
0x18000f150  xor     edx, edx; Val
0x18000f152  lea     rcx, [rbp+480h+CallParams]; void *
0x18000f156  mov     r8d, 0B4h; Size
0x18000f15c  mov     ebx, r9d
0x18000f15f  call    memset_0
0x18000f164  xor     edx, edx; Val
0x18000f166  lea     rcx, [rbp+480h+DeviceID]; void *
0x18000f16d  mov     r8d, 320h; Size
0x18000f173  call    memset_0
0x18000f178  lea     rcx, aDwgetlineaddre_4; "dwGetLineAddress:..."
0x18000f17f  call    RasTapiTrace
0x18000f184  cmp     [rbp+480h+arg_28], 0
0x18000f18b  jnz     loc_18000F236
0x18000f191  mov     ecx, cs:RasLine; hLineApp
0x18000f197  lea     rax, [rbp+480h+CallParams]
0x18000f19b  mov     [rsp+580h+lpCallParams], rax; lpCallParams
0x18000f1a0  lea     r8, [rbp+480h+hLine]; lphLine
0x18000f1a4  mov     [rsp+580h+dwMediaModes], 2; dwMediaModes
0x18000f1ac  mov     r9d, edi; dwAPIVersion
0x18000f1af  mov     [rsp+580h+dwPrivileges], 1; dwPrivileges
0x18000f1b7  mov     edx, ebx; dwDeviceID
0x18000f1b9  mov     [rsp+580h+dwCallbackInstance], 0; dwCallbackInstance
0x18000f1c2  mov     [rsp+580h+dwExtVersion], r15d; dwExtVersion
0x18000f1c7  call    cs:__imp_lineOpenA
0x18000f1cd  mov     edi, eax
0x18000f1cf  test    eax, eax
0x18000f1d1  jz      short loc_18000F1E1
0x18000f1d3  mov     edx, eax
0x18000f1d5  lea     rcx, aDwgetlineaddre_0; "dwGetLineAddress: lineOpen failed. 0x%x"
0x18000f1dc  jmp     loc_18000F4D5
0x18000f1e1  mov     ecx, [rbp+480h+hLine]; hLine
0x18000f1e4  lea     rax, aLineguid_0; "LineGuid"
0x18000f1eb  mov     [rsp+580h+dwCallbackInstance], rax; lpszDeviceClass
0x18000f1f0  mov     r9d, 1; dwSelect
0x18000f1f6  lea     rax, [rbp+480h+DeviceID]
0x18000f1fd  mov     [rbp+480h+DeviceID.dwTotalSize], 320h
0x18000f207  xor     r8d, r8d; hCall
0x18000f20a  mov     qword ptr [rsp+580h+dwExtVersion], rax; lpDeviceID
0x18000f20f  xor     edx, edx; dwAddressID
0x18000f211  call    cs:__imp_lineGetIDA
0x18000f217  mov     edi, eax
0x18000f219  test    eax, eax
0x18000f21b  jz      short loc_18000F22B
0x18000f21d  mov     edx, eax
0x18000f21f  lea     rcx, aDwgetlineaddre_2; "dwGetLineAddress: lineGetID LineGuid fa"...
0x18000f226  jmp     loc_18000F4D5
0x18000f22b  mov     ecx, [rbp+480h+hLine]; hLine
0x18000f22e  call    cs:__imp_lineClose
0x18000f234  jmp     short loc_18000F2A4
0x18000f236  xor     r9d, r9d
0x18000f239  lea     rax, [rbp+480h+hLine]
0x18000f23d  mov     ecx, ebx
0x18000f23f  mov     qword ptr [rsp+580h+dwExtVersion], rax
0x18000f244  lea     edx, [r9+1]
0x18000f248  lea     r8d, [r9+2]
0x18000f24c  call    RasLineOpen
0x18000f251  mov     edi, eax
0x18000f253  test    eax, eax
0x18000f255  jz      short loc_18000F265
0x18000f257  mov     edx, eax
0x18000f259  lea     rcx, aDwgetlineaddre; "dwGetLineAddress: RasLineOpen failed 0x"...
0x18000f260  jmp     loc_18000F4D5
0x18000f265  mov     ecx, [rbp+480h+hLine]; int
0x18000f268  lea     rax, [rbp+480h+DeviceID]
0x18000f26f  mov     [rsp+580h+dwCallbackInstance], rax; void *
0x18000f274  mov     r9d, 1; int
0x18000f27a  lea     rax, aLineguid; "LineGuid"
0x18000f281  mov     [rbp+480h+DeviceID.dwTotalSize], 320h
0x18000f28b  xor     r8d, r8d; int
0x18000f28e  mov     qword ptr [rsp+580h+dwExtVersion], rax; String1
0x18000f293  xor     edx, edx; int
0x18000f295  call    RasLineGetID
0x18000f29a  mov     ecx, [rbp+480h+hLine]
0x18000f29d  mov     edi, eax
0x18000f29f  call    RasLineClose
0x18000f2a4  mov     eax, [rbp+480h+DeviceID.dwStringSize]
0x18000f2aa  mov     [rbp+480h+hLine], 0
0x18000f2b1  test    eax, eax
0x18000f2b3  jz      loc_18000F4C7
0x18000f2b9  cmp     eax, 1
0x18000f2bc  jz      loc_18000F4C7
0x18000f2c2  movsd   xmm0, qword ptr cs:aFramerelay; "FRAMERELAY"
0x18000f2ca  mov     rax, 434952454E4547h
0x18000f2d4  mov     [rsp+580h+var_530], rax
0x18000f2d9  mov     ecx, 4E5056h
0x18000f2de  xor     eax, eax
0x18000f2e0  movsd   qword ptr [rbp+480h+var_4F0], xmm0
0x18000f2e5  movsd   xmm0, qword ptr cs:aParallel; "PARALLEL"
0x18000f2ed  mov     [rsp+580h+var_528], rax
0x18000f2f2  mov     [rsp+580h+var_51C], rax
0x18000f2f7  mov     [rsp+580h+var_514], eax
0x18000f2fb  mov     eax, dword ptr cs:aIsdn; "ISDN"
0x18000f301  mov     dword ptr [rsp+580h+var_510], eax
0x18000f305  mov     al, byte ptr cs:aIsdn+4; ""
0x18000f30b  mov     [rsp+580h+var_510+4], al
0x18000f30f  xor     eax, eax
0x18000f311  mov     [rsp+580h+var_50B], rax
0x18000f316  mov     [rsp+580h+var_503], ax
0x18000f31b  mov     [rsp+580h+var_501], al
0x18000f31f  mov     eax, dword ptr cs:aSerial; "SERIAL"
0x18000f325  mov     dword ptr [rbp+480h+var_500], eax
0x18000f328  movzx   eax, word ptr cs:aSerial+4; "AL"
0x18000f32f  mov     word ptr [rbp+480h+var_500+4], ax
0x18000f333  mov     al, byte ptr cs:aSerial+6; ""
0x18000f339  mov     [rbp+480h+var_500+6], al
0x18000f33c  xor     eax, eax
0x18000f33e  mov     [rbp+480h+var_4F9], rax
0x18000f342  mov     [rbp+480h+var_4F1], al
0x18000f345  mov     eax, dword ptr cs:aFramerelay+7; "LAY"
0x18000f34b  mov     dword ptr [rbp+480h+var_4F0+7], eax
0x18000f34e  xor     eax, eax
0x18000f350  mov     dword ptr [rbp+480h+var_4F0+0Bh], eax
0x18000f353  mov     [rbp+480h+var_4F0+0Fh], al
0x18000f356  mov     [rbp+480h+var_4DC], rax
0x18000f35a  mov     [rbp+480h+var_4D4], eax
0x18000f35d  mov     eax, dword ptr cs:aSonet; "SONET"
0x18000f363  mov     dword ptr [rbp+480h+var_4D0], eax
0x18000f366  movzx   eax, word ptr cs:aSonet+4; "T"
0x18000f36d  mov     word ptr [rbp+480h+var_4D0+4], ax
0x18000f371  xor     eax, eax
0x18000f373  mov     [rbp+480h+var_4CA], rax
0x18000f377  mov     [rbp+480h+var_4C2], ax
0x18000f37b  mov     eax, dword ptr cs:aSw56; "SW56"
0x18000f381  mov     dword ptr [rbp+480h+var_4C0], eax
0x18000f384  mov     al, byte ptr cs:aSw56+4; ""
0x18000f38a  mov     [rbp+480h+var_4C0+4], al
0x18000f38d  xor     eax, eax
0x18000f38f  mov     [rbp+480h+var_4BB], rax
0x18000f393  mov     [rbp+480h+var_4B3], ax
0x18000f397  mov     [rbp+480h+var_4B1], al
0x18000f39a  mov     [rbp+480h+var_4AC], rax
0x18000f39e  mov     [rbp+480h+var_4A4], eax
0x18000f3a1  mov     [rbp+480h+var_49C], rax
0x18000f3a5  mov     [rbp+480h+var_494], eax
0x18000f3a8  mov     eax, dword ptr cs:aIrda; "IRDA"
0x18000f3ae  mov     dword ptr [rbp+480h+var_490], eax
0x18000f3b1  mov     al, byte ptr cs:aIrda+4; ""
0x18000f3b7  mov     [rbp+480h+var_490+4], al
0x18000f3ba  xor     eax, eax
0x18000f3bc  mov     [rbp+480h+var_48B], rax
0x18000f3c0  mov     [rbp+480h+var_483], ax
0x18000f3c4  mov     [rbp+480h+var_481], al
0x18000f3c7  mov     al, byte ptr cs:aParallel+8; ""
0x18000f3cd  mov     [rbp+480h+var_480+8], al
0x18000f3d0  xor     eax, eax
0x18000f3d2  mov     dword ptr [rbp+480h+var_480+9], eax
0x18000f3d5  mov     word ptr [rbp+480h+var_480+0Dh], ax
0x18000f3d9  mov     [rbp+480h+var_480+0Fh], al
0x18000f3dc  mov     eax, dword ptr cs:aPppoe; "PPPoE"
0x18000f3e2  mov     dword ptr [rbp+480h+var_470], eax
0x18000f3e5  movzx   eax, word ptr cs:aPppoe+4; "E"
0x18000f3ec  mov     word ptr [rbp+480h+var_470+4], ax
0x18000f3f0  xor     eax, eax
0x18000f3f2  mov     [rbp+480h+var_46A], rax
0x18000f3f6  mov     [rbp+480h+var_462], ax
0x18000f3fa  mov     [rbp+480h+var_45C], rax
0x18000f3fe  mov     [rsp+580h+var_520], 353258h
0x18000f406  mov     [rbp+480h+var_4E0], 4D5441h
0x18000f40d  mov     [rbp+480h+var_4B0], ecx
0x18000f410  mov     [rbp+480h+var_4A0], ecx
0x18000f413  movsd   qword ptr [rbp+480h+var_480], xmm0
0x18000f418  mov     [rbp+480h+var_460], ecx
0x18000f41b  mov     [rbp+480h+var_454], eax
0x18000f41e  mov     [rbp+480h+var_44C], rax
0x18000f422  mov     [rbp+480h+var_444], eax
0x18000f425  mov     [rbp+480h+var_43C], rax
0x18000f429  mov     [rbp+480h+var_434], eax
0x18000f42c  mov     eax, [rbp+480h+DeviceID.dwStringOffset]
0x18000f432  mov     [rbp+480h+var_450], ecx
0x18000f435  lea     rcx, aMediaTypeForIn; "Media type for index %d"
0x18000f43c  mov     [rbp+480h+var_440], 455247h
0x18000f443  movups  xmm0, xmmword ptr [rbp+rax+480h+DeviceID.dwTotalSize]
0x18000f44b  movdqu  xmmword ptr [r13+0], xmm0
0x18000f451  mov     ebx, [rbp+rax+480h+DeviceID.dwStringSize]
0x18000f458  mov     edx, ebx
0x18000f45a  call    RasTapiTrace
0x18000f45f  xor     eax, eax
0x18000f461  lea     r10, [rsp+580h+var_530]
0x18000f466  cmp     ebx, 0Fh
0x18000f469  mov     r9d, 7FFFFFFEh
0x18000f46f  mov     r8d, 10h
0x18000f475  mov     rcx, r12
0x18000f478  cmovbe  eax, ebx
0x18000f47b  mov     ebx, eax
0x18000f47d  shl     rax, 4
0x18000f481  add     r10, rax
0x18000f484  test    r9, r9
0x18000f487  jz      short loc_18000F4A1
0x18000f489  mov     al, [r10]
0x18000f48c  test    al, al
0x18000f48e  jz      short loc_18000F4A1
0x18000f490  mov     [rcx], al
0x18000f492  inc     r10
0x18000f495  inc     rcx
0x18000f498  dec     r9
0x18000f49b  sub     r8, 1
0x18000f49f  jnz     short loc_18000F484
0x18000f4a1  lea     rax, [rcx-1]
0x18000f4a5  test    r8, r8
0x18000f4a8  mov     rdx, r12
0x18000f4ab  cmovnz  rax, rcx
0x18000f4af  lea     rcx, aMediatypeBeing; "MediaType being returned as %s"
0x18000f4b6  mov     byte ptr [rax], 0
0x18000f4b9  call    RasTapiTrace
0x18000f4be  test    rsi, rsi
0x18000f4c1  jz      short loc_18000F4DA
0x18000f4c3  mov     [rsi], ebx
0x18000f4c5  jmp     short loc_18000F4DA
0x18000f4c7  mov     edi, 80004005h
0x18000f4cc  lea     rcx, aDwgetlineaddre_1; "dwGetLineAddress: pvar->dwStringSize !="...
0x18000f4d3  mov     edx, edi
0x18000f4d5  call    RasTapiTrace
0x18000f4da  mov     ecx, [rbp+480h+hLine]; hLine
0x18000f4dd  test    ecx, ecx
0x18000f4df  jz      short loc_18000F4F7
0x18000f4e1  cmp     [rbp+480h+arg_28], 0
0x18000f4e8  jnz     short loc_18000F4F2
0x18000f4ea  call    cs:__imp_lineClose
0x18000f4f0  jmp     short loc_18000F4F7
0x18000f4f2  call    RasLineClose
0x18000f4f7  mov     edx, edi
0x18000f4f9  lea     rcx, aDwgetlineaddre_3; "dwGetLineAddress: done. 0x%x"
0x18000f500  call    RasTapiTrace
0x18000f505  lea     rcx, asc_18002C0B8; " "
0x18000f50c  call    RasTapiTrace
0x18000f511  mov     eax, edi
0x18000f513  mov     rcx, [rbp+480h+var_40]
0x18000f51a  xor     rcx, rsp; StackCookie
0x18000f51d  call    __security_check_cookie
0x18000f522  add     rsp, 550h
0x18000f529  pop     r15
0x18000f52b  pop     r13
0x18000f52d  pop     r12
0x18000f52f  pop     rdi
0x18000f530  pop     rsi
0x18000f531  pop     rbx
0x18000f532  pop     rbp
0x18000f533  retn
```
