# ShowPlan(x,x)

- ea: `0x100f01aa`
- end: `0x100f049f`
- name: `_ShowPlan@8`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x100aab45`

## callees

- `0x100f01aa`
- `0x100f066f`
- `0x100f0cfd`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strdate` at `0x100f01e3`
- `api-ms-win-crt-private-l1-1-0!_o__strdate` at `0x100f01e3`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100f0482`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100f0482`

## string_xrefs

- `0x100f022e`: `temp query`
- `0x100f0447`: `%02d) Update`
- `0x100f043f`: `%02d) Delete`

## pseudocode

```c
FILE *__fastcall ShowPlan(int a1, FILE **a2)
{
  int v2; // ebx
  const char *v3; // eax
  const wchar_t *v4; // ecx
  int v5; // edi
  const wchar_t *v6; // ecx
  const wchar_t *v7; // ecx
  int v8; // eax
  int **v9; // esi
  int *v10; // eax
  int *v11; // eax
  const char *v12; // eax
  const char *v13; // eax
  int v14; // ecx
  int v15; // ecx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  FILE *result; // eax
  const char *v21; // [esp-14h] [ebp-3Ch]
  const char *v22; // [esp-Ch] [ebp-34h]
  int v25; // [esp+Ch] [ebp-1Ch] BYREF
  char v26[20]; // [esp+10h] [ebp-18h] BYREF

  v2 = a1;
  v25 = 0;
  if ( dword_1012C390 )
  {
    OutputString("\n\n---------------------------------------------\n");
    v3 = (const char *)__o__strdate(v26);
    OutputString("DATE: %s\n", v3);
    OutputString("VER:  %d.%02d.%04d\n\n", 4, 0, 9801);
    OutputString("NOTE: Currently does not handle subqueries, vt parameters, and subqueries\n");
    OutputString("NOTE: You may see ERROR messages in these cases\n");
    dword_1012C390 = 0;
  }
  v4 = L"temp query";
  if ( *(_DWORD *)(v2 + 164) )
    v4 = *(const wchar_t **)(v2 + 164);
  OutputString("\n\n\n--- %S ---\n", v4);
  OutputString("\n- Inputs to Query -\n");
  v5 = *(_DWORD *)(v2 + 60);
  if ( v5 )
  {
    do
    {
      switch ( *(_DWORD *)(v5 + 192) )
      {
        case 1:
          v7 = L"Un-named";
          if ( *(_DWORD *)(v5 + 200) )
            v7 = *(const wchar_t **)(v5 + 200);
          OutputString("Table '%S'\n", v7);
          break;
        case 2:
          v6 = L"Un-named";
          if ( *(_DWORD *)(v5 + 200) )
            v6 = *(const wchar_t **)(v5 + 200);
          OutputString("ODBC table '%S'\n", v6);
          break;
        case 3:
          OutputString("Recordset\n");
          break;
      }
      if ( *(_DWORD *)(v5 + 208) )
        OutputString("    Database '%S'\n", *(const wchar_t **)(v5 + 208));
      if ( *(_DWORD *)(v5 + 168) )
        OutputString("    Connect '%S'\n", *(const wchar_t **)(v5 + 168));
      v8 = *(_DWORD *)(v5 + 196);
      if ( v8 )
        OutputString("    Using index '%S'\n", *(const wchar_t **)(v8 + 4));
      v9 = *(int ***)(v5 + 196);
      if ( v9 )
      {
        OutputString("    Having Indexes:\n");
        do
        {
          v10 = &dword_1000B7C0;
          if ( v9[4] != (int *)1 )
            v10 = (int *)"s";
          v22 = (const char *)v10;
          v11 = &dword_1000B7C0;
          if ( v9[3] != (int *)1 )
            v11 = (int *)"s";
          v21 = (const char *)v11;
          v12 = (const char *)&dword_1000B7C0;
          if ( v9[2] != (int *)1 )
            v12 = "s";
          OutputString(
            "    %S %d entrie%s, %d page%s, %d value%s\n",
            (const wchar_t *)v9[1],
            v9[2],
            v12,
            v9[3],
            v21,
            v9[4],
            v22);
          v13 = (const char *)&dword_1000B7C0;
          v14 = (int)((_DWORD)v9[5] << 17) >> 27;
          if ( v14 != 1 )
            v13 = "s";
          OutputString("      which has %d column%s", v14, v13);
          if ( ((_BYTE)v9[5] & 3) != 0 )
            OutputString(", fixed");
          if ( ((_BYTE)v9[5] & 4) != 0 )
            OutputString(", unique");
          if ( ((_BYTE)v9[5] & 8) != 0 )
            OutputString(", clustered and/or counter");
          if ( ((_BYTE)v9[5] & 0x10) != 0 )
            OutputString(", primary-key");
          if ( ((_BYTE)v9[5] & 0x20) != 0 )
            OutputString(", no-nulls");
          if ( ((_BYTE)v9[5] & 0x40) != 0 )
            OutputString(", nulls ignored");
          OutputString("\n");
          v9 = (int **)*v9;
        }
        while ( v9 );
      }
      v5 = *(_DWORD *)(v5 + 240);
    }
    while ( v5 );
    v2 = a1;
  }
  OutputString("- End inputs to Query -\n\n");
  DoShowPlan(v2, a2, &v25);
  v15 = v25 + 1;
  v16 = *(unsigned __int16 *)(v2 + 136) - 1;
  ++v25;
  v17 = v16 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 == 1 )
          OutputString("%02d) Delete", v15);
      }
      else
      {
        OutputString("%02d) Update", v15);
      }
    }
    else
    {
      OutputString("%02d) Insert into '%S'\n", v15, *(_DWORD *)(v2 + 148));
    }
  }
  else
  {
    OutputString("%02d) Select into '%S'\n", v15, *(_DWORD *)(v2 + 148));
  }
  result = Stream;
  if ( Stream )
    result = (FILE *)_fclose(Stream);
  Stream = 0;
  return result;
}

```

## disassembly

```asm
0x100f01aa  mov     edi, edi
0x100f01ac  push    ebp
0x100f01ad  mov     ebp, esp
0x100f01af  sub     esp, 24h
0x100f01b2  mov     eax, ___security_cookie
0x100f01b7  xor     eax, ebp
0x100f01b9  mov     [ebp+var_4], eax
0x100f01bc  cmp     dword_1012C390, 0
0x100f01c3  push    ebx; ArgList
0x100f01c4  mov     ebx, ecx
0x100f01c6  mov     [ebp+var_24], edx
0x100f01c9  mov     [ebp+var_20], ebx
0x100f01cc  mov     [ebp+var_1C], 0
0x100f01d3  jz      short loc_100F0228
0x100f01d5  push    offset asc_1000F66C; "\n\n-----------------------------------"...
0x100f01da  call    _OutputString
0x100f01df  lea     eax, [ebp+var_18]
0x100f01e2  push    eax
0x100f01e3  call    ds:__imp___o__strdate
0x100f01e9  push    eax; ArgList
0x100f01ea  push    offset aDateS; "DATE: %s\n"
0x100f01ef  call    _OutputString
0x100f01f4  push    2649h
0x100f01f9  push    0
0x100f01fb  push    4; ArgList
0x100f01fd  push    offset aVerD02d04d; "VER:  %d.%02d.%04d\n\n"
0x100f0202  call    _OutputString
0x100f0207  push    offset aNoteCurrentlyD; "NOTE: Currently does not handle subquer"...
0x100f020c  call    _OutputString
0x100f0211  push    offset aNoteYouMaySeeE; "NOTE: You may see ERROR messages in the"...
0x100f0216  call    _OutputString
0x100f021b  add     esp, 28h
0x100f021e  mov     dword_1012C390, 0
0x100f0228  mov     eax, [ebx+0A4h]
0x100f022e  mov     ecx, offset aTempQuery; "temp query"
0x100f0233  test    eax, eax
0x100f0235  push    edi; ArgList
0x100f0236  cmovnz  ecx, eax
0x100f0239  push    ecx; ArgList
0x100f023a  push    offset aS; "\n\n\n--- %S ---\n"
0x100f023f  call    _OutputString
0x100f0244  push    offset aInputsToQuery; "\n- Inputs to Query -\n"
0x100f0249  call    _OutputString
0x100f024e  mov     edi, [ebx+3Ch]
0x100f0251  add     esp, 0Ch
0x100f0254  test    edi, edi
0x100f0256  jz      loc_100F0401
0x100f025c  mov     ebx, offset aS_2; "s"
0x100f0261  push    esi; ArgList
0x100f0262  mov     eax, [edi+0C0h]
0x100f0268  sub     eax, 1
0x100f026b  jz      short loc_100F029B
0x100f026d  sub     eax, 1
0x100f0270  jz      short loc_100F0283
0x100f0272  sub     eax, 1
0x100f0275  jnz     short loc_100F02B8
0x100f0277  push    offset aRecordset; "Recordset\n"
0x100f027c  call    _OutputString
0x100f0281  jmp     short loc_100F02B7
0x100f0283  mov     eax, [edi+0C8h]
0x100f0289  mov     ecx, offset aUnNamed; "Un-named"
0x100f028e  test    eax, eax
0x100f0290  cmovnz  ecx, eax
0x100f0293  push    ecx
0x100f0294  push    offset aOdbcTableS; "ODBC table '%S'\n"
0x100f0299  jmp     short loc_100F02B1
0x100f029b  mov     eax, [edi+0C8h]
0x100f02a1  mov     ecx, offset aUnNamed; "Un-named"
0x100f02a6  test    eax, eax
0x100f02a8  cmovnz  ecx, eax
0x100f02ab  push    ecx; ArgList
0x100f02ac  push    offset aTableS; "Table '%S'\n"
0x100f02b1  call    _OutputString
0x100f02b6  pop     ecx
0x100f02b7  pop     ecx
0x100f02b8  mov     eax, [edi+0D0h]
0x100f02be  test    eax, eax
0x100f02c0  jz      short loc_100F02CF
0x100f02c2  push    eax; ArgList
0x100f02c3  push    offset aDatabaseS; "    Database '%S'\n"
0x100f02c8  call    _OutputString
0x100f02cd  pop     ecx
0x100f02ce  pop     ecx
0x100f02cf  mov     eax, [edi+0A8h]
0x100f02d5  test    eax, eax
0x100f02d7  jz      short loc_100F02E6
0x100f02d9  push    eax; ArgList
0x100f02da  push    offset aConnectS; "    Connect '%S'\n"
0x100f02df  call    _OutputString
0x100f02e4  pop     ecx
0x100f02e5  pop     ecx
0x100f02e6  mov     eax, [edi+0C4h]
0x100f02ec  test    eax, eax
0x100f02ee  jz      short loc_100F02FF
0x100f02f0  push    dword ptr [eax+4]; ArgList
0x100f02f3  push    offset aUsingIndexS_0; "    Using index '%S'\n"
0x100f02f8  call    _OutputString
0x100f02fd  pop     ecx
0x100f02fe  pop     ecx
0x100f02ff  mov     esi, [edi+0C4h]
0x100f0305  test    esi, esi
0x100f0307  jz      loc_100F03EF
0x100f030d  push    offset aHavingIndexes; "    Having Indexes:\n"
0x100f0312  call    _OutputString
0x100f0317  pop     ecx
0x100f0318  cmp     dword ptr [esi+10h], 1
0x100f031c  mov     ecx, offset dword_1000B7C0
0x100f0321  mov     eax, ecx
0x100f0323  cmovnz  eax, ebx
0x100f0326  cmp     dword ptr [esi+0Ch], 1
0x100f032a  push    eax
0x100f032b  push    dword ptr [esi+10h]
0x100f032e  mov     eax, ecx
0x100f0330  cmovnz  eax, ebx
0x100f0333  cmp     dword ptr [esi+8], 1
0x100f0337  push    eax
0x100f0338  push    dword ptr [esi+0Ch]
0x100f033b  mov     eax, ecx
0x100f033d  cmovnz  eax, ebx
0x100f0340  push    eax
0x100f0341  push    dword ptr [esi+8]
0x100f0344  push    dword ptr [esi+4]; ArgList
0x100f0347  push    offset aSDEntrieSDPage; "    %S %d entrie%s, %d page%s, %d value"...
0x100f034c  call    _OutputString
0x100f0351  mov     ecx, [esi+14h]
0x100f0354  mov     eax, offset dword_1000B7C0
0x100f0359  shl     ecx, 11h
0x100f035c  sar     ecx, 1Bh
0x100f035f  cmp     ecx, 1
0x100f0362  cmovnz  eax, ebx
0x100f0365  push    eax
0x100f0366  push    ecx; ArgList
0x100f0367  push    offset aWhichHasDColum; "      which has %d column%s"
0x100f036c  call    _OutputString
0x100f0371  add     esp, 2Ch
0x100f0374  test    byte ptr [esi+14h], 3
0x100f0378  jz      short loc_100F0385
0x100f037a  push    offset aFixed; ", fixed"
0x100f037f  call    _OutputString
0x100f0384  pop     ecx
0x100f0385  test    byte ptr [esi+14h], 4
0x100f0389  jz      short loc_100F0396
0x100f038b  push    offset aUnique; ", unique"
0x100f0390  call    _OutputString
0x100f0395  pop     ecx
0x100f0396  test    byte ptr [esi+14h], 8
0x100f039a  jz      short loc_100F03A7
0x100f039c  push    offset aClusteredAndOr; ", clustered and/or counter"
0x100f03a1  call    _OutputString
0x100f03a6  pop     ecx
0x100f03a7  test    byte ptr [esi+14h], 10h
0x100f03ab  jz      short loc_100F03B8
0x100f03ad  push    offset aPrimaryKey; ", primary-key"
0x100f03b2  call    _OutputString
0x100f03b7  pop     ecx
0x100f03b8  test    byte ptr [esi+14h], 20h
0x100f03bc  jz      short loc_100F03C9
0x100f03be  push    offset aNoNulls; ", no-nulls"
0x100f03c3  call    _OutputString
0x100f03c8  pop     ecx
0x100f03c9  test    byte ptr [esi+14h], 40h
0x100f03cd  jz      short loc_100F03DA
0x100f03cf  push    offset aNullsIgnored; ", nulls ignored"
0x100f03d4  call    _OutputString
0x100f03d9  pop     ecx
0x100f03da  push    offset asc_1000BFC0; "\n"
0x100f03df  call    _OutputString
0x100f03e4  mov     esi, [esi]
0x100f03e6  pop     ecx
0x100f03e7  test    esi, esi
0x100f03e9  jnz     loc_100F0318
0x100f03ef  mov     edi, [edi+0F0h]
0x100f03f5  test    edi, edi
0x100f03f7  jnz     loc_100F0262
0x100f03fd  mov     ebx, [ebp+var_20]
0x100f0400  pop     esi
0x100f0401  push    offset aEndInputsToQue; "- End inputs to Query -\n\n"
0x100f0406  call    _OutputString
0x100f040b  mov     edx, [ebp+var_24]
0x100f040e  lea     eax, [ebp+var_1C]
0x100f0411  pop     ecx
0x100f0412  push    eax
0x100f0413  mov     ecx, ebx
0x100f0415  call    _DoShowPlan@12; DoShowPlan(x,x,x)
0x100f041a  mov     ecx, [ebp+var_1C]
0x100f041d  movzx   eax, word ptr [ebx+88h]
0x100f0424  inc     ecx
0x100f0425  dec     eax
0x100f0426  mov     [ebp+var_1C], ecx
0x100f0429  pop     edi
0x100f042a  sub     eax, 1
0x100f042d  jz      short loc_100F0463
0x100f042f  sub     eax, 1
0x100f0432  jz      short loc_100F0455
0x100f0434  sub     eax, 1
0x100f0437  jz      short loc_100F0446
0x100f0439  sub     eax, 1
0x100f043c  jnz     short loc_100F0477
0x100f043e  push    ecx
0x100f043f  push    offset a02dDelete; "%02d) Delete"
0x100f0444  jmp     short loc_100F044C
0x100f0446  push    ecx; ArgList
0x100f0447  push    offset a02dUpdate; "%02d) Update"
0x100f044c  call    _OutputString
0x100f0451  pop     ecx
0x100f0452  pop     ecx
0x100f0453  jmp     short loc_100F0477
0x100f0455  push    dword ptr [ebx+94h]
0x100f045b  push    ecx
0x100f045c  push    offset a02dInsertIntoS; "%02d) Insert into '%S'\n"
0x100f0461  jmp     short loc_100F046F
0x100f0463  push    dword ptr [ebx+94h]
0x100f0469  push    ecx; ArgList
0x100f046a  push    offset a02dSelectIntoS; "%02d) Select into '%S'\n"
0x100f046f  call    _OutputString
0x100f0474  add     esp, 0Ch
0x100f0477  mov     eax, Stream
0x100f047c  pop     ebx
0x100f047d  test    eax, eax
0x100f047f  jz      short loc_100F0489
0x100f0481  push    eax; Stream
0x100f0482  call    ds:__imp__fclose
0x100f0488  pop     ecx
0x100f0489  mov     ecx, [ebp+var_4]
0x100f048c  xor     ecx, ebp; StackCookie
0x100f048e  mov     Stream, 0
0x100f0498  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100f049d  leave
0x100f049e  retn
```
