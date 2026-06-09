# ShowPlan(x,x)

- ea: `0x100f001a`
- end: `0x100f030f`
- name: `_ShowPlan@8`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x100aa9b5`

## callees

- `0x100f001a`
- `0x100f04df`
- `0x100f0b6d`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strdate` at `0x100f0053`
- `api-ms-win-crt-private-l1-1-0!_o__strdate` at `0x100f0053`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100f02f2`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100f02f2`

## string_xrefs

- `0x100f009e`: `temp query`
- `0x100f02b7`: `%02d) Update`
- `0x100f02af`: `%02d) Delete`

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
  if ( dword_1012C350 )
  {
    OutputString("\n\n---------------------------------------------\n");
    v3 = (const char *)__o__strdate(v26);
    OutputString("DATE: %s\n", v3);
    OutputString("VER:  %d.%02d.%04d\n\n", 4, 0, 9801);
    OutputString("NOTE: Currently does not handle subqueries, vt parameters, and subqueries\n");
    OutputString("NOTE: You may see ERROR messages in these cases\n");
    dword_1012C350 = 0;
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
          v10 = &dword_1000B718;
          if ( v9[4] != (int *)1 )
            v10 = (int *)"s";
          v22 = (const char *)v10;
          v11 = &dword_1000B718;
          if ( v9[3] != (int *)1 )
            v11 = (int *)"s";
          v21 = (const char *)v11;
          v12 = (const char *)&dword_1000B718;
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
          v13 = (const char *)&dword_1000B718;
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
0x100f001a  mov     edi, edi
0x100f001c  push    ebp
0x100f001d  mov     ebp, esp
0x100f001f  sub     esp, 24h
0x100f0022  mov     eax, ___security_cookie
0x100f0027  xor     eax, ebp
0x100f0029  mov     [ebp+var_4], eax
0x100f002c  cmp     dword_1012C350, 0
0x100f0033  push    ebx; ArgList
0x100f0034  mov     ebx, ecx
0x100f0036  mov     [ebp+var_24], edx
0x100f0039  mov     [ebp+var_20], ebx
0x100f003c  mov     [ebp+var_1C], 0
0x100f0043  jz      short loc_100F0098
0x100f0045  push    offset asc_1000F560; "\n\n-----------------------------------"...
0x100f004a  call    _OutputString
0x100f004f  lea     eax, [ebp+var_18]
0x100f0052  push    eax
0x100f0053  call    ds:__imp___o__strdate
0x100f0059  push    eax; ArgList
0x100f005a  push    offset aDateS; "DATE: %s\n"
0x100f005f  call    _OutputString
0x100f0064  push    2649h
0x100f0069  push    0
0x100f006b  push    4; ArgList
0x100f006d  push    offset aVerD02d04d; "VER:  %d.%02d.%04d\n\n"
0x100f0072  call    _OutputString
0x100f0077  push    offset aNoteCurrentlyD; "NOTE: Currently does not handle subquer"...
0x100f007c  call    _OutputString
0x100f0081  push    offset aNoteYouMaySeeE; "NOTE: You may see ERROR messages in the"...
0x100f0086  call    _OutputString
0x100f008b  add     esp, 28h
0x100f008e  mov     dword_1012C350, 0
0x100f0098  mov     eax, [ebx+0A4h]
0x100f009e  mov     ecx, offset aTempQuery; "temp query"
0x100f00a3  test    eax, eax
0x100f00a5  push    edi; ArgList
0x100f00a6  cmovnz  ecx, eax
0x100f00a9  push    ecx; ArgList
0x100f00aa  push    offset aS; "\n\n\n--- %S ---\n"
0x100f00af  call    _OutputString
0x100f00b4  push    offset aInputsToQuery; "\n- Inputs to Query -\n"
0x100f00b9  call    _OutputString
0x100f00be  mov     edi, [ebx+3Ch]
0x100f00c1  add     esp, 0Ch
0x100f00c4  test    edi, edi
0x100f00c6  jz      loc_100F0271
0x100f00cc  mov     ebx, offset aS_2; "s"
0x100f00d1  push    esi; ArgList
0x100f00d2  mov     eax, [edi+0C0h]
0x100f00d8  sub     eax, 1
0x100f00db  jz      short loc_100F010B
0x100f00dd  sub     eax, 1
0x100f00e0  jz      short loc_100F00F3
0x100f00e2  sub     eax, 1
0x100f00e5  jnz     short loc_100F0128
0x100f00e7  push    offset aRecordset; "Recordset\n"
0x100f00ec  call    _OutputString
0x100f00f1  jmp     short loc_100F0127
0x100f00f3  mov     eax, [edi+0C8h]
0x100f00f9  mov     ecx, offset aUnNamed; "Un-named"
0x100f00fe  test    eax, eax
0x100f0100  cmovnz  ecx, eax
0x100f0103  push    ecx
0x100f0104  push    offset aOdbcTableS; "ODBC table '%S'\n"
0x100f0109  jmp     short loc_100F0121
0x100f010b  mov     eax, [edi+0C8h]
0x100f0111  mov     ecx, offset aUnNamed; "Un-named"
0x100f0116  test    eax, eax
0x100f0118  cmovnz  ecx, eax
0x100f011b  push    ecx; ArgList
0x100f011c  push    offset aTableS; "Table '%S'\n"
0x100f0121  call    _OutputString
0x100f0126  pop     ecx
0x100f0127  pop     ecx
0x100f0128  mov     eax, [edi+0D0h]
0x100f012e  test    eax, eax
0x100f0130  jz      short loc_100F013F
0x100f0132  push    eax; ArgList
0x100f0133  push    offset aDatabaseS; "    Database '%S'\n"
0x100f0138  call    _OutputString
0x100f013d  pop     ecx
0x100f013e  pop     ecx
0x100f013f  mov     eax, [edi+0A8h]
0x100f0145  test    eax, eax
0x100f0147  jz      short loc_100F0156
0x100f0149  push    eax; ArgList
0x100f014a  push    offset aConnectS; "    Connect '%S'\n"
0x100f014f  call    _OutputString
0x100f0154  pop     ecx
0x100f0155  pop     ecx
0x100f0156  mov     eax, [edi+0C4h]
0x100f015c  test    eax, eax
0x100f015e  jz      short loc_100F016F
0x100f0160  push    dword ptr [eax+4]; ArgList
0x100f0163  push    offset aUsingIndexS_0; "    Using index '%S'\n"
0x100f0168  call    _OutputString
0x100f016d  pop     ecx
0x100f016e  pop     ecx
0x100f016f  mov     esi, [edi+0C4h]
0x100f0175  test    esi, esi
0x100f0177  jz      loc_100F025F
0x100f017d  push    offset aHavingIndexes; "    Having Indexes:\n"
0x100f0182  call    _OutputString
0x100f0187  pop     ecx
0x100f0188  cmp     dword ptr [esi+10h], 1
0x100f018c  mov     ecx, offset dword_1000B718
0x100f0191  mov     eax, ecx
0x100f0193  cmovnz  eax, ebx
0x100f0196  cmp     dword ptr [esi+0Ch], 1
0x100f019a  push    eax
0x100f019b  push    dword ptr [esi+10h]
0x100f019e  mov     eax, ecx
0x100f01a0  cmovnz  eax, ebx
0x100f01a3  cmp     dword ptr [esi+8], 1
0x100f01a7  push    eax
0x100f01a8  push    dword ptr [esi+0Ch]
0x100f01ab  mov     eax, ecx
0x100f01ad  cmovnz  eax, ebx
0x100f01b0  push    eax
0x100f01b1  push    dword ptr [esi+8]
0x100f01b4  push    dword ptr [esi+4]; ArgList
0x100f01b7  push    offset aSDEntrieSDPage; "    %S %d entrie%s, %d page%s, %d value"...
0x100f01bc  call    _OutputString
0x100f01c1  mov     ecx, [esi+14h]
0x100f01c4  mov     eax, offset dword_1000B718
0x100f01c9  shl     ecx, 11h
0x100f01cc  sar     ecx, 1Bh
0x100f01cf  cmp     ecx, 1
0x100f01d2  cmovnz  eax, ebx
0x100f01d5  push    eax
0x100f01d6  push    ecx; ArgList
0x100f01d7  push    offset aWhichHasDColum; "      which has %d column%s"
0x100f01dc  call    _OutputString
0x100f01e1  add     esp, 2Ch
0x100f01e4  test    byte ptr [esi+14h], 3
0x100f01e8  jz      short loc_100F01F5
0x100f01ea  push    offset aFixed; ", fixed"
0x100f01ef  call    _OutputString
0x100f01f4  pop     ecx
0x100f01f5  test    byte ptr [esi+14h], 4
0x100f01f9  jz      short loc_100F0206
0x100f01fb  push    offset aUnique; ", unique"
0x100f0200  call    _OutputString
0x100f0205  pop     ecx
0x100f0206  test    byte ptr [esi+14h], 8
0x100f020a  jz      short loc_100F0217
0x100f020c  push    offset aClusteredAndOr; ", clustered and/or counter"
0x100f0211  call    _OutputString
0x100f0216  pop     ecx
0x100f0217  test    byte ptr [esi+14h], 10h
0x100f021b  jz      short loc_100F0228
0x100f021d  push    offset aPrimaryKey; ", primary-key"
0x100f0222  call    _OutputString
0x100f0227  pop     ecx
0x100f0228  test    byte ptr [esi+14h], 20h
0x100f022c  jz      short loc_100F0239
0x100f022e  push    offset aNoNulls; ", no-nulls"
0x100f0233  call    _OutputString
0x100f0238  pop     ecx
0x100f0239  test    byte ptr [esi+14h], 40h
0x100f023d  jz      short loc_100F024A
0x100f023f  push    offset aNullsIgnored; ", nulls ignored"
0x100f0244  call    _OutputString
0x100f0249  pop     ecx
0x100f024a  push    offset asc_1000BF10; "\n"
0x100f024f  call    _OutputString
0x100f0254  mov     esi, [esi]
0x100f0256  pop     ecx
0x100f0257  test    esi, esi
0x100f0259  jnz     loc_100F0188
0x100f025f  mov     edi, [edi+0F0h]
0x100f0265  test    edi, edi
0x100f0267  jnz     loc_100F00D2
0x100f026d  mov     ebx, [ebp+var_20]
0x100f0270  pop     esi
0x100f0271  push    offset aEndInputsToQue; "- End inputs to Query -\n\n"
0x100f0276  call    _OutputString
0x100f027b  mov     edx, [ebp+var_24]
0x100f027e  lea     eax, [ebp+var_1C]
0x100f0281  pop     ecx
0x100f0282  push    eax
0x100f0283  mov     ecx, ebx
0x100f0285  call    _DoShowPlan@12; DoShowPlan(x,x,x)
0x100f028a  mov     ecx, [ebp+var_1C]
0x100f028d  movzx   eax, word ptr [ebx+88h]
0x100f0294  inc     ecx
0x100f0295  dec     eax
0x100f0296  mov     [ebp+var_1C], ecx
0x100f0299  pop     edi
0x100f029a  sub     eax, 1
0x100f029d  jz      short loc_100F02D3
0x100f029f  sub     eax, 1
0x100f02a2  jz      short loc_100F02C5
0x100f02a4  sub     eax, 1
0x100f02a7  jz      short loc_100F02B6
0x100f02a9  sub     eax, 1
0x100f02ac  jnz     short loc_100F02E7
0x100f02ae  push    ecx
0x100f02af  push    offset a02dDelete; "%02d) Delete"
0x100f02b4  jmp     short loc_100F02BC
0x100f02b6  push    ecx; ArgList
0x100f02b7  push    offset a02dUpdate; "%02d) Update"
0x100f02bc  call    _OutputString
0x100f02c1  pop     ecx
0x100f02c2  pop     ecx
0x100f02c3  jmp     short loc_100F02E7
0x100f02c5  push    dword ptr [ebx+94h]
0x100f02cb  push    ecx
0x100f02cc  push    offset a02dInsertIntoS; "%02d) Insert into '%S'\n"
0x100f02d1  jmp     short loc_100F02DF
0x100f02d3  push    dword ptr [ebx+94h]
0x100f02d9  push    ecx; ArgList
0x100f02da  push    offset a02dSelectIntoS; "%02d) Select into '%S'\n"
0x100f02df  call    _OutputString
0x100f02e4  add     esp, 0Ch
0x100f02e7  mov     eax, Stream
0x100f02ec  pop     ebx
0x100f02ed  test    eax, eax
0x100f02ef  jz      short loc_100F02F9
0x100f02f1  push    eax; Stream
0x100f02f2  call    ds:__imp__fclose
0x100f02f8  pop     ecx
0x100f02f9  mov     ecx, [ebp+var_4]
0x100f02fc  xor     ecx, ebp; StackCookie
0x100f02fe  mov     Stream, 0
0x100f0308  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100f030d  leave
0x100f030e  retn
```
