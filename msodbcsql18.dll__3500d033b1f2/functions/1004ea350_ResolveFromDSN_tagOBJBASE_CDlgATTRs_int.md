# ResolveFromDSN(tagOBJBASE *,CDlgATTRs &,int *)

- ea: `0x1004ea350`
- end: `0x1004ea8d2`
- name: `?ResolveFromDSN@@YAJPEAUtagOBJBASE@@AEAVCDlgATTRs@@PEAH@Z`
- size: `1410`
- prototype: `int(struct tagOBJBASE *, struct CDlgATTRs *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100495b60`
- `0x1004e7ee8`

## callees

- `0x10046d140`
- `0x10046d408`
- `0x1004e6e44`
- `0x1004e8600`
- `0x1004ea350`
- `0x100546a24`
- `0x100546f80`
- `0x100548210`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x1004ea43b`
- `VCRUNTIME140!wcsrchr` at `0x1004ea4f9`
- `VCRUNTIME140!wcsrchr` at `0x1004ea43b`
- `VCRUNTIME140!wcsrchr` at `0x1004ea4f9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ea411`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ea6a0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ea6d1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ea411`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ea6a0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004ea6d1`

## string_xrefs

- `0x1004ea68e`: `ActiveDirectoryIntegrated`
- `0x1004ea6bf`: `ActiveDirectoryMSI`

## pseudocode

```c
__int64 __fastcall ResolveFromDSN(struct tagOBJBASE *a1, struct CDlgATTRs *a2, int *a3)
{
  int v5; // ebp
  const unsigned __int16 **v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rcx
  wchar_t *v9; // rax
  const unsigned __int16 *v10; // rax
  int DSNField; // eax
  __int64 v12; // r9
  unsigned int v13; // edi
  __int64 v14; // rdx
  wchar_t *v15; // rax
  unsigned __int64 i; // rsi
  int v17; // edx
  const unsigned __int16 *v18; // r9
  __int64 v19; // r8
  __int16 v20; // dx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // eax
  const unsigned __int16 *v24; // r8
  __int64 v25; // r8
  __int64 v26; // rdx
  WCHAR szRetBuffer[4]; // [rsp+30h] [rbp-48h] BYREF

  v5 = 0;
  if ( *((_DWORD *)a1 + 1) == 2 )
    v6 = (const unsigned __int16 **)((char *)a1 + 192);
  else
    v6 = (const unsigned __int16 **)(*((_QWORD *)a1 + 9) + 1952LL);
  *a3 = 0;
  v7 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v7 + 48) & 1) != 0 )
  {
    wcscpy(szRetBuffer, L"No");
    szRetBuffer[3] = 0;
    SQLGetPrivateProfileStringW(
      (LPCWSTR)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v7 + 56)),
      L"RegPrecedence",
      L"No",
      szRetBuffer,
      4,
      L"ODBC.INI");
    LOBYTE(v5) = _wcsicmp(szRetBuffer, L"No") != 0;
  }
  v8 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)v8 & 1) != 0 )
  {
    v9 = wcsrchr((const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v8 + 8)), 0x5Cu);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = (const unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL));
    DSNField = CDlgATTRs::SetATTRValueSafe(a2, 1, v10);
    v13 = DSNField;
    if ( DSNField < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v14 = 4795401;
LABEL_77:
        _mm_lfence();
        bidTraceHR(0, v14, (unsigned int)DSNField, v12);
        return v13;
      }
      return v13;
    }
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)a2 + 1) + 24LL) |= 1u;
    *(_WORD *)(*((_QWORD *)a2 + 1) + 24LL) |= 2u;
  }
  else if ( (*(_BYTE *)(v8 + 24) & 1) != 0 )
  {
    v15 = wcsrchr((const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v8 + 32)), 0x5Cu);
    if ( v15 )
    {
      DSNField = CDlgATTRs::SetATTRValueSafe(a2, 1, v15 + 1);
      v13 = DSNField;
      if ( DSNField < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v14 = 4809737;
          goto LABEL_77;
        }
        return v13;
      }
    }
  }
  if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 264LL) & 1) != 0 )
  {
    if ( v5 )
    {
      DSNField = GetDSNField(a2, 11, L"Database", L"(Default)", v5);
      v13 = DSNField;
      if ( DSNField < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v14 = 4839433;
          goto LABEL_77;
        }
        return v13;
      }
    }
    goto LABEL_25;
  }
  if ( !*v6 )
  {
    DSNField = GetDSNField(a2, 11, L"Database", L"(Default)", v5);
    v13 = DSNField;
    if ( DSNField < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v14 = 4830217;
        goto LABEL_77;
      }
      return v13;
    }
LABEL_25:
    for ( i = 0; i < 138; i += 3LL )
    {
      v17 = qword_1005A2B80[i];
      if ( v17 == 5 )
      {
        v18 = (const unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)
                                       + *(_QWORD *)(*((_QWORD *)a2 + 1) + 56LL));
      }
      else if ( v17 == 31 )
      {
        v18 = g_ApplicationIntentMap;
      }
      else
      {
        v18 = (const unsigned __int16 *)qword_1005A2B80[i + 2];
      }
      DSNField = GetDSNField(a2, v17, (const unsigned __int16 *)qword_1005A2B80[i + 1], v18, v5);
      v13 = DSNField;
      if ( DSNField < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 4867081;
        goto LABEL_77;
      }
    }
    v19 = *((_QWORD *)a2 + 1);
    v20 = *(_WORD *)(v19 + 912);
    if ( (v20 & 1) != 0 && !*(_WORD *)(*(_QWORD *)(v19 + 920) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)) )
      *(_WORD *)(v19 + 912) = v20 & 0xFFFE;
    v21 = *((_QWORD *)a2 + 1);
    if ( (*(_BYTE *)(v21 + 144) & 1) == 0
      && ((*(_BYTE *)(v21 + 912) & 1) == 0
       || _wcsicmp(
            L"ActiveDirectoryIntegrated",
            (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v21 + 920)))) )
    {
      v22 = *((_QWORD *)a2 + 1);
      if ( (*(_BYTE *)(v22 + 912) & 1) == 0
        || (v23 = _wcsicmp(
                    L"ActiveDirectoryMSI",
                    (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v22 + 920))),
            v24 = &szDefault,
            v23) )
      {
        v24 = &g_szUserName;
      }
      DSNField = CDlgATTRs::SetATTRValue(a2, 6, v24);
      v13 = DSNField;
      if ( DSNField < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 4890633;
        goto LABEL_77;
      }
      _mm_lfence();
      *(_WORD *)(*((_QWORD *)a2 + 1) + 144LL) |= 1u;
      *(_WORD *)(*((_QWORD *)a2 + 1) + 144LL) |= 8u;
    }
    if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 240LL) & 1) == 0 )
    {
      DSNField = CDlgATTRs::SetATTRValue(a2, 10, &g_szComputerName);
      v13 = DSNField;
      if ( DSNField < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 4899849;
        goto LABEL_77;
      }
      _mm_lfence();
      *(_WORD *)(*((_QWORD *)a2 + 1) + 240LL) |= 1u;
      *(_WORD *)(*((_QWORD *)a2 + 1) + 240LL) |= 8u;
    }
    if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 216LL) & 1) == 0 )
    {
      DSNField = CDlgATTRs::SetATTRValue(a2, 9, &g_szAppName);
      v13 = DSNField;
      if ( DSNField < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v13;
        v14 = 4909065;
        goto LABEL_77;
      }
      _mm_lfence();
      if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 224LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)) )
      {
        _mm_lfence();
        *(_WORD *)(*((_QWORD *)a2 + 1) + 216LL) |= 1u;
        *(_WORD *)(*((_QWORD *)a2 + 1) + 216LL) |= 8u;
      }
    }
    v25 = *((_QWORD *)a2 + 1);
    if ( !*(_WORD *)(*(_QWORD *)(v25 + 680) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)) )
      *(_WORD *)(v25 + 672) |= 0x20u;
    v26 = *((_QWORD *)a2 + 1);
    if ( !*(_WORD *)(*(_QWORD *)(v26 + 440) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)) )
      *(_WORD *)(v26 + 432) |= 0x20u;
    DSNField = ConvertCheckBoxField(a2, 20);
    v13 = DSNField;
    if ( DSNField >= 0 )
    {
      _mm_lfence();
      DSNField = ConvertCheckBoxField(a2, 23);
      v13 = DSNField;
      if ( DSNField >= 0 )
      {
        *a3 = v5;
        return v13;
      }
      if ( (bidGblFlags & 2) == 0 )
        return v13;
      v14 = 4934665;
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        return v13;
      v14 = 4931593;
    }
    goto LABEL_77;
  }
  DSNField = CDlgATTRs::SetATTRValue(a2, 11, *v6);
  v13 = DSNField;
  if ( DSNField >= 0 )
  {
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)a2 + 1) + 264LL) |= 1u;
    *(_WORD *)(*((_QWORD *)a2 + 1) + 264LL) |= 8u;
    goto LABEL_25;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v14 = 4822025;
    goto LABEL_77;
  }
  return v13;
}

```

## disassembly

```asm
0x1004ea350  mov     [rsp+arg_18], rbx
0x1004ea355  push    rbp
0x1004ea356  push    rsi
0x1004ea357  push    rdi
0x1004ea358  push    r12
0x1004ea35a  push    r13
0x1004ea35c  push    r14
0x1004ea35e  push    r15
0x1004ea360  sub     rsp, 40h
0x1004ea364  mov     rax, cs:__security_cookie
0x1004ea36b  xor     rax, rsp
0x1004ea36e  mov     [rsp+78h+var_40], rax
0x1004ea373  xor     r15d, r15d
0x1004ea376  mov     r14, r8
0x1004ea379  mov     rbx, rdx
0x1004ea37c  mov     ebp, r15d
0x1004ea37f  lea     r12d, [r15+2]
0x1004ea383  cmp     [rcx+4], r12d
0x1004ea387  jnz     short loc_1004EA392
0x1004ea389  lea     rsi, [rcx+0C0h]
0x1004ea390  jmp     short loc_1004EA39D
0x1004ea392  mov     rsi, [rcx+48h]
0x1004ea396  add     rsi, 7A0h
0x1004ea39d  mov     [r8], r15d
0x1004ea3a0  mov     r13d, 1
0x1004ea3a6  mov     rcx, [rdx+8]
0x1004ea3aa  test    [rcx+30h], r13b
0x1004ea3ae  jz      short loc_1004EA41D
0x1004ea3b0  mov     eax, dword ptr cs:aNo; "No"
0x1004ea3b6  lea     r9, [rsp+78h+szRetBuffer]; lpszRetBuffer
0x1004ea3bb  mov     dword ptr [rsp+78h+szRetBuffer], eax
0x1004ea3bf  lea     r8, aNo; "No"
0x1004ea3c6  movzx   eax, word ptr cs:aNo+4; ""
0x1004ea3cd  mov     [rsp+78h+var_44], ax
0x1004ea3d2  xor     eax, eax
0x1004ea3d4  mov     [rsp+78h+var_42], ax
0x1004ea3d9  mov     rax, [rdx+10h]
0x1004ea3dd  lea     rdx, aRegprecedence; "RegPrecedence"
0x1004ea3e4  mov     rcx, [rcx+38h]
0x1004ea3e8  add     rcx, [rax+20h]; lpszSection
0x1004ea3ec  lea     rax, szFilename; "ODBC.INI"
0x1004ea3f3  mov     [rsp+78h+lpszFilename], rax; lpszFilename
0x1004ea3f8  mov     [rsp+78h+cchRetBuffer], 4; cchRetBuffer
0x1004ea400  call    SQLGetPrivateProfileStringW
0x1004ea405  lea     rdx, aNo; "No"
0x1004ea40c  lea     rcx, [rsp+78h+szRetBuffer]; String1
0x1004ea411  call    cs:__imp__wcsicmp
0x1004ea417  test    eax, eax
0x1004ea419  setnz   bpl
0x1004ea41d  mov     rcx, [rbx+8]
0x1004ea421  test    [rcx], r13b
0x1004ea424  jz      loc_1004EA4E2
0x1004ea42a  mov     rax, [rbx+10h]
0x1004ea42e  mov     edx, 5Ch ; '\'; Ch
0x1004ea433  mov     rcx, [rcx+8]
0x1004ea437  add     rcx, [rax+20h]; Str
0x1004ea43b  call    cs:__imp_wcsrchr
0x1004ea441  test    rax, rax
0x1004ea444  jnz     short loc_1004EA458
0x1004ea446  mov     rax, [rbx+8]
0x1004ea44a  mov     rcx, [rbx+10h]
0x1004ea44e  mov     rax, [rax+8]
0x1004ea452  add     rax, [rcx+20h]
0x1004ea456  jmp     short loc_1004EA45B
0x1004ea458  add     rax, r12
0x1004ea45b  mov     r8, rax; unsigned __int16 *
0x1004ea45e  mov     edx, r13d; int
0x1004ea461  mov     rcx, rbx; this
0x1004ea464  call    ?SetATTRValueSafe@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValueSafe(int,ushort const *)
0x1004ea469  mov     edi, eax
0x1004ea46b  test    eax, eax
0x1004ea46d  jns     short loc_1004EA486
0x1004ea46f  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea476  jz      loc_1004EA8AB
0x1004ea47c  mov     edx, 492C09h
0x1004ea481  jmp     loc_1004EA89E
0x1004ea486  lfence
0x1004ea489  mov     rax, [rbx+8]
0x1004ea48d  or      [rax+18h], r13w
0x1004ea492  mov     rax, [rbx+8]
0x1004ea496  or      [rax+18h], r12w
0x1004ea49b  mov     rax, [rbx+8]
0x1004ea49f  test    [rax+108h], r13b
0x1004ea4a6  jnz     loc_1004EA5A9
0x1004ea4ac  mov     r8, [rsi]; unsigned __int16 *
0x1004ea4af  mov     edx, 0Bh; int
0x1004ea4b4  mov     rcx, rbx; this
0x1004ea4b7  test    r8, r8
0x1004ea4ba  jz      loc_1004EA575
0x1004ea4c0  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004ea4c5  mov     edi, eax
0x1004ea4c7  test    eax, eax
0x1004ea4c9  jns     short loc_1004EA530
0x1004ea4cb  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea4d2  jz      loc_1004EA8AB
0x1004ea4d8  mov     edx, 499409h
0x1004ea4dd  jmp     loc_1004EA89E
0x1004ea4e2  test    [rcx+18h], r13b
0x1004ea4e6  jz      short loc_1004EA49B
0x1004ea4e8  mov     rax, [rbx+10h]
0x1004ea4ec  mov     edx, 5Ch ; '\'; Ch
0x1004ea4f1  mov     rcx, [rcx+20h]
0x1004ea4f5  add     rcx, [rax+20h]; Str
0x1004ea4f9  call    cs:__imp_wcsrchr
0x1004ea4ff  test    rax, rax
0x1004ea502  jz      short loc_1004EA49B
0x1004ea504  lea     r8, [rax+2]; unsigned __int16 *
0x1004ea508  mov     edx, r13d; int
0x1004ea50b  mov     rcx, rbx; this
0x1004ea50e  call    ?SetATTRValueSafe@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValueSafe(int,ushort const *)
0x1004ea513  mov     edi, eax
0x1004ea515  test    eax, eax
0x1004ea517  jns     short loc_1004EA49B
0x1004ea519  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea520  jz      loc_1004EA8AB
0x1004ea526  mov     edx, 496409h
0x1004ea52b  jmp     loc_1004EA89E
0x1004ea530  lfence
0x1004ea533  mov     rax, [rbx+8]
0x1004ea537  or      [rax+108h], r13w
0x1004ea53f  mov     rax, [rbx+8]
0x1004ea543  or      word ptr [rax+108h], 8
0x1004ea54b  mov     rsi, r15
0x1004ea54e  lea     r8, qword_1005A2B80
0x1004ea555  mov     edx, [rsi+r8]; int
0x1004ea559  cmp     edx, 5
0x1004ea55c  jz      loc_1004EA5F6
0x1004ea562  cmp     edx, 1Fh
0x1004ea565  jz      loc_1004EA5ED
0x1004ea56b  mov     r9, [rsi+r8+10h]
0x1004ea570  jmp     loc_1004EA606
0x1004ea575  lea     r9, aDefault_0; "(Default)"
0x1004ea57c  mov     [rsp+78h+cchRetBuffer], ebp; int
0x1004ea580  lea     r8, aDatabase; "Database"
0x1004ea587  call    ?GetDSNField@@YAJAEAVCDlgATTRs@@HPEBG1H@Z; GetDSNField(CDlgATTRs &,int,ushort const *,ushort const *,int)
0x1004ea58c  mov     edi, eax
0x1004ea58e  test    eax, eax
0x1004ea590  jns     short loc_1004EA54B
0x1004ea592  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea599  jz      loc_1004EA8AB
0x1004ea59f  mov     edx, 49B409h
0x1004ea5a4  jmp     loc_1004EA89E
0x1004ea5a9  test    ebp, ebp
0x1004ea5ab  jz      short loc_1004EA54B
0x1004ea5ad  lea     r9, aDefault_0; "(Default)"
0x1004ea5b4  mov     [rsp+78h+cchRetBuffer], ebp; int
0x1004ea5b8  lea     r8, aDatabase; "Database"
0x1004ea5bf  mov     edx, 0Bh; int
0x1004ea5c4  mov     rcx, rbx; this
0x1004ea5c7  call    ?GetDSNField@@YAJAEAVCDlgATTRs@@HPEBG1H@Z; GetDSNField(CDlgATTRs &,int,ushort const *,ushort const *,int)
0x1004ea5cc  mov     edi, eax
0x1004ea5ce  test    eax, eax
0x1004ea5d0  jns     loc_1004EA54B
0x1004ea5d6  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea5dd  jz      loc_1004EA8AB
0x1004ea5e3  mov     edx, 49D809h
0x1004ea5e8  jmp     loc_1004EA89E
0x1004ea5ed  mov     r9, cs:g_ApplicationIntentMap
0x1004ea5f4  jmp     short loc_1004EA606
0x1004ea5f6  mov     rax, [rbx+8]
0x1004ea5fa  mov     rcx, [rbx+10h]
0x1004ea5fe  mov     r9, [rax+38h]
0x1004ea602  add     r9, [rcx+20h]; unsigned __int16 *
0x1004ea606  mov     r8, [rsi+r8+8]; unsigned __int16 *
0x1004ea60b  mov     rcx, rbx; this
0x1004ea60e  mov     [rsp+78h+cchRetBuffer], ebp; int
0x1004ea612  call    ?GetDSNField@@YAJAEAVCDlgATTRs@@HPEBG1H@Z; GetDSNField(CDlgATTRs &,int,ushort const *,ushort const *,int)
0x1004ea617  mov     edi, eax
0x1004ea619  test    eax, eax
0x1004ea61b  js      loc_1004EA890
0x1004ea621  add     rsi, 18h
0x1004ea625  lea     r8, qword_1005A2B80
0x1004ea62c  cmp     rsi, 450h
0x1004ea633  jb      loc_1004EA555
0x1004ea639  mov     r8, [rbx+8]
0x1004ea63d  movzx   edx, word ptr [r8+390h]
0x1004ea645  test    r13b, dl
0x1004ea648  jz      short loc_1004EA670
0x1004ea64a  mov     rax, [rbx+10h]
0x1004ea64e  mov     rcx, [r8+398h]
0x1004ea655  mov     rax, [rax+20h]
0x1004ea659  cmp     [rcx+rax], r15w
0x1004ea65e  jnz     short loc_1004EA670
0x1004ea660  mov     eax, 0FFFEh
0x1004ea665  and     dx, ax
0x1004ea668  mov     [r8+390h], dx
0x1004ea670  mov     rdx, [rbx+8]
0x1004ea674  test    [rdx+90h], r13b
0x1004ea67b  jnz     loc_1004EA72E
0x1004ea681  test    [rdx+390h], r13b
0x1004ea688  jz      short loc_1004EA6AE
0x1004ea68a  mov     rax, [rbx+10h]
0x1004ea68e  lea     rcx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x1004ea695  mov     rdx, [rdx+398h]
0x1004ea69c  add     rdx, [rax+20h]; String2
0x1004ea6a0  call    cs:__imp__wcsicmp
0x1004ea6a6  test    eax, eax
0x1004ea6a8  jz      loc_1004EA72E
0x1004ea6ae  mov     rdx, [rbx+8]
0x1004ea6b2  test    [rdx+390h], r13b
0x1004ea6b9  jz      short loc_1004EA6E2
0x1004ea6bb  mov     rax, [rbx+10h]
0x1004ea6bf  lea     rcx, aActivedirector_3; "ActiveDirectoryMSI"
0x1004ea6c6  mov     rdx, [rdx+398h]
0x1004ea6cd  add     rdx, [rax+20h]; String2
0x1004ea6d1  call    cs:__imp__wcsicmp
0x1004ea6d7  lea     r8, szDefault
0x1004ea6de  test    eax, eax
0x1004ea6e0  jz      short loc_1004EA6E9
0x1004ea6e2  lea     r8, ?g_szUserName@@3PAGA; unsigned __int16 *
0x1004ea6e9  mov     edx, 6; int
0x1004ea6ee  mov     rcx, rbx; this
0x1004ea6f1  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004ea6f6  mov     edi, eax
0x1004ea6f8  test    eax, eax
0x1004ea6fa  jns     short loc_1004EA713
0x1004ea6fc  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea703  jz      loc_1004EA8AB
0x1004ea709  mov     edx, 4AA009h
0x1004ea70e  jmp     loc_1004EA89E
0x1004ea713  lfence
0x1004ea716  mov     rax, [rbx+8]
0x1004ea71a  or      [rax+90h], r13w
0x1004ea722  mov     rax, [rbx+8]
0x1004ea726  or      word ptr [rax+90h], 8
0x1004ea72e  mov     rax, [rbx+8]
0x1004ea732  test    [rax+0F0h], r13b
0x1004ea739  jnz     short loc_1004EA787
0x1004ea73b  lea     r8, ?g_szComputerName@@3PAGA; unsigned __int16 *
0x1004ea742  mov     edx, 0Ah; int
0x1004ea747  mov     rcx, rbx; this
0x1004ea74a  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004ea74f  mov     edi, eax
0x1004ea751  test    eax, eax
0x1004ea753  jns     short loc_1004EA76C
0x1004ea755  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea75c  jz      loc_1004EA8AB
0x1004ea762  mov     edx, 4AC409h
0x1004ea767  jmp     loc_1004EA89E
0x1004ea76c  lfence
0x1004ea76f  mov     rax, [rbx+8]
0x1004ea773  or      [rax+0F0h], r13w
0x1004ea77b  mov     rax, [rbx+8]
0x1004ea77f  or      word ptr [rax+0F0h], 8
0x1004ea787  mov     rax, [rbx+8]
0x1004ea78b  test    [rax+0D8h], r13b
0x1004ea792  jnz     short loc_1004EA7FD
0x1004ea794  lea     r8, ?g_szAppName@@3PAGA; unsigned __int16 *
0x1004ea79b  mov     edx, 9; int
0x1004ea7a0  mov     rcx, rbx; this
0x1004ea7a3  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1004ea7a8  mov     edi, eax
0x1004ea7aa  test    eax, eax
0x1004ea7ac  jns     short loc_1004EA7C5
0x1004ea7ae  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea7b5  jz      loc_1004EA8AB
0x1004ea7bb  mov     edx, 4AE809h
0x1004ea7c0  jmp     loc_1004EA89E
0x1004ea7c5  lfence
0x1004ea7c8  mov     rax, [rbx+8]
0x1004ea7cc  mov     rcx, [rbx+10h]
0x1004ea7d0  mov     rdx, [rax+0E0h]
0x1004ea7d7  mov     rax, [rcx+20h]
0x1004ea7db  cmp     [rdx+rax], r15w
0x1004ea7e0  jz      short loc_1004EA7FD
0x1004ea7e2  lfence
0x1004ea7e5  mov     rax, [rbx+8]
0x1004ea7e9  or      [rax+0D8h], r13w
0x1004ea7f1  mov     rax, [rbx+8]
0x1004ea7f5  or      word ptr [rax+0D8h], 8
0x1004ea7fd  mov     r8, [rbx+8]
0x1004ea801  mov     rax, [rbx+10h]
0x1004ea805  mov     rdx, [r8+2A8h]
0x1004ea80c  mov     rcx, [rax+20h]
0x1004ea810  cmp     [rdx+rcx], r15w
0x1004ea815  jnz     short loc_1004EA820
0x1004ea817  or      word ptr [r8+2A0h], 20h
0x1004ea820  mov     rdx, [rbx+8]
0x1004ea824  mov     rax, [rbx+10h]
0x1004ea828  mov     rcx, [rdx+1B8h]
0x1004ea82f  mov     rax, [rax+20h]
0x1004ea833  cmp     [rcx+rax], r15w
0x1004ea838  jnz     short loc_1004EA842
0x1004ea83a  or      word ptr [rdx+1B0h], 20h
0x1004ea842  mov     edx, 14h; int
0x1004ea847  mov     rcx, rbx; this
0x1004ea84a  call    ?ConvertCheckBoxField@@YAJAEAVCDlgATTRs@@H@Z; ConvertCheckBoxField(CDlgATTRs &,int)
0x1004ea84f  mov     edi, eax
0x1004ea851  test    eax, eax
0x1004ea853  jns     short loc_1004EA865
0x1004ea855  test    byte ptr cs:_bidGblFlags, r12b
0x1004ea85c  jz      short loc_1004EA8AB
0x1004ea85e  mov     edx, 4B4009h
0x1004ea863  jmp     short loc_1004EA89E
0x1004ea865  lfence
0x1004ea868  mov     edx, 17h; int
0x1004ea86d  mov     rcx, rbx; this
0x1004ea870  call    ?ConvertCheckBoxField@@YAJAEAVCDlgATTRs@@H@Z; ConvertCheckBoxField(CDlgATTRs &,int)
0x1004ea875  mov     edi, eax
0x1004ea877  test    eax, eax
  ... truncated ...
```
