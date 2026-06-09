# ParseKeyName

- ea: `0x1400024a4`
- end: `0x140002937`
- name: `ParseKeyName`
- size: `1171`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001e90`

## callees

- `0x1400024a4`
- `0x140002b70`
- `0x14000c62c`
- `0x14000c810`
- `0x14000c9c0`
- `0x14000cd48`
- `0x14000daa4`
- `0x14000e228`
- `0x14000e2f8`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400028c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400028c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002643`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400026e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400026fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002834`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002643`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400026e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400026fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002834`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028e4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002512`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002797`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400027ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002808`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000283d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002512`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002797`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400027ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140002808`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000283d`

## string_xrefs

- `0x140002507`: `HKEY_CURRENT_CONFIG`
- `0x1400025c7`: `HKEY_CURRENT_CONFIG`
- `0x1400026c7`: `HKEY_CURRENT_CONFIG`

## pseudocode

```c
__int64 __fastcall ParseKeyName(PCNZWCH lpString1, int *a2, __int64 a3)
{
  WCHAR *v5; // r14
  int Char2; // eax
  const WCHAR *v7; // rsi
  unsigned int v8; // r15d
  __int64 v9; // r8
  _WORD *v10; // rbp
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 ResString2FromModule; // rax
  wchar_t *v24; // r8
  WCHAR *v25; // rdx
  LPVOID v26; // rax
  WCHAR *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  LPVOID v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r8
  int v35; // eax
  int v36; // esi
  int v37; // eax
  unsigned int v38; // esi
  _WORD *v39; // rax
  unsigned int v40; // esi
  _WORD *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  _WORD *Memory; // [rsp+70h] [rbp+8h] BYREF

  if ( !lpString1 || !a2 || (unsigned int)*a2 > 0xB )
  {
    v11 = 87;
    goto LABEL_62;
  }
  v5 = 0;
  Char2 = FindChar2(lpString1, 92, a3, 0);
  if ( Char2 != -1 )
  {
    v5 = (WCHAR *)&lpString1[Char2 + 1];
    lpString1[Char2] = 0;
  }
  v7 = lpString1 + 1;
  if ( *lpString1 != 34 )
    v7 = lpString1;
  v8 = lstrlenW(L"HKEY_CURRENT_CONFIG") + 1;
  Memory = AllocateMemory(2 * v8);
  v10 = Memory;
  if ( Memory )
  {
    v13 = 1;
    if ( (unsigned int)StringCompareExW(v7, L"HKCU", v9, 0)
      && (unsigned int)StringCompareExW(v7, L"HKEY_CURRENT_USER", v12, 0) )
    {
      if ( (unsigned int)StringCompareExW(v7, L"HKCR", v14, 0)
        && (unsigned int)StringCompareExW(v7, L"HKEY_CLASSES_ROOT", v15, 0) )
      {
        if ( (unsigned int)StringCompareExW(v7, L"HKCC", v16, 0)
          && (unsigned int)StringCompareExW(v7, L"HKEY_CURRENT_CONFIG", v17, 0) )
        {
          if ( (unsigned int)StringCompareExW(v7, L"HKLM", v18, 0)
            && (unsigned int)StringCompareExW(v7, L"HKEY_LOCAL_MACHINE", v19, 0) )
          {
            if ( (unsigned int)StringCompareExW(v7, L"HKU", v20, 0)
              && (unsigned int)StringCompareExW(v7, L"HKEY_USERS", v21, 0) )
            {
              SetLastError(0x800401E4);
              ResString2FromModule = GetResString2FromModule(v22, 104, 0);
              v24 = &g_wszOptions[10 * *a2];
LABEL_33:
              SetReason2(1, ResString2FromModule, v24);
              goto LABEL_34;
            }
            *((_QWORD *)a2 + 1) = -2147483645;
            v25 = (WCHAR *)L"HKEY_USERS";
          }
          else
          {
            *((_QWORD *)a2 + 1) = -2147483646;
            v25 = (WCHAR *)L"HKEY_LOCAL_MACHINE";
          }
          StringCopyW(v10, v25, v8);
LABEL_23:
          if ( v5 )
          {
            v32 = lstrlenW(v5);
            if ( v32 > 1 )
            {
              v33 = v32 - 1;
              if ( v5[v33] == 92 )
                v5[v33] = 0;
            }
            if ( !lstrlenW(v5) )
              goto LABEL_58;
            v35 = -1;
            v36 = -1;
            do
            {
              if ( v35 != v36 )
              {
                if ( v35 - v36 == 1 || v35 - v36 > 255 )
                  goto LABEL_58;
                v36 = v35;
              }
              v35 = FindChar2(v5, 92, v34, (unsigned int)(v35 + 1));
            }
            while ( v35 != -1 );
            if ( (v37 = lstrlenW(v5), v36 == v37 - 1) || v36 == -1 && v37 > 255 || v37 - v36 > 255 )
            {
LABEL_58:
              SetLastError(0x80090003);
              v13 = 0;
              if ( GetLastError() == 87 )
              {
                SaveErrorMessage(0xFFFFFFFFLL);
              }
              else
              {
                SetLastError(0x800401E4);
                v43 = GetResString2FromModule(v42, 104, 0);
                SetReason2(1, v43, &g_wszOptions[10 * *a2]);
              }
              goto LABEL_35;
            }
            SetLastError(0);
            v38 = lstrlenW(v5) + 1;
            v39 = AllocateMemory(2 * v38);
            *((_QWORD *)a2 + 10) = v39;
            if ( v39 )
            {
              StringCopyW(v39, v5, v38);
              v40 = v8 + v38 + 2;
              v41 = AllocateMemory(2 * v40);
              *((_QWORD *)a2 + 11) = v41;
              if ( v41 )
              {
                StringCopyW(v41, v10, v40);
                StringConcatW(*((_QWORD *)a2 + 11), L"\\", v40);
                StringConcatW(*((_QWORD *)a2 + 11), *((_QWORD *)a2 + 10), v40);
                goto LABEL_35;
              }
            }
          }
          else
          {
            v26 = AllocateMemory(2u);
            *((_QWORD *)a2 + 10) = v26;
            if ( v26 )
            {
              v31 = AllocateMemory(2 * v8);
              *((_QWORD *)a2 + 11) = v31;
              if ( !v31 )
              {
                SaveErrorMessage(0xFFFFFFFFLL);
                v13 = 0;
              }
              StringCopyW(*((_WORD **)a2 + 11), v10, v8);
              goto LABEL_35;
            }
          }
          SaveErrorMessage(0xFFFFFFFFLL);
LABEL_34:
          v13 = 0;
LABEL_35:
          FreeMemory(&Memory);
          return v13;
        }
        *((_QWORD *)a2 + 1) = -2147483643;
        v27 = (WCHAR *)L"HKEY_CURRENT_CONFIG";
      }
      else
      {
        *((_QWORD *)a2 + 1) = 0xFFFFFFFF80000000uLL;
        v27 = (WCHAR *)L"HKEY_CLASSES_ROOT";
      }
    }
    else
    {
      *((_QWORD *)a2 + 1) = -2147483647;
      v27 = (WCHAR *)L"HKEY_CURRENT_USER";
    }
    StringCopyW(v10, v27, v8);
    if ( a2[4] == 1 )
    {
      SetLastError(0x800401E4);
      v29 = 105;
    }
    else
    {
      if ( (unsigned int)(*a2 - 6) > 1 )
        goto LABEL_23;
      SetLastError(0x800401E4);
      v29 = 106;
    }
    ResString2FromModule = GetResString2FromModule(v28, v29, 0);
    v24 = &g_wszOptions[10 * *a2];
    goto LABEL_33;
  }
  v11 = 0xFFFFFFFFLL;
LABEL_62:
  SaveErrorMessage(v11);
  return 0;
}

```

## disassembly

```asm
0x1400024a4  push    rbx
0x1400024a6  push    rbp
0x1400024a7  push    rsi
0x1400024a8  push    rdi
0x1400024a9  push    r12
0x1400024ab  push    r13
0x1400024ad  push    r14
0x1400024af  push    r15
0x1400024b1  sub     rsp, 28h
0x1400024b5  mov     rbx, rdx
0x1400024b8  mov     rdi, rcx
0x1400024bb  test    rcx, rcx
0x1400024be  jz      loc_14000291A
0x1400024c4  test    rdx, rdx
0x1400024c7  jz      loc_14000291A
0x1400024cd  cmp     dword ptr [rdx], 0Bh
0x1400024d0  ja      loc_14000291A
0x1400024d6  xor     r14d, r14d
0x1400024d9  xor     r9d, r9d
0x1400024dc  lea     edx, [r14+5Ch]
0x1400024e0  call    FindChar2
0x1400024e5  or      r13d, 0FFFFFFFFh
0x1400024e9  cmp     eax, r13d
0x1400024ec  jz      short loc_1400024FF
0x1400024ee  movsxd  rcx, eax
0x1400024f1  lea     r14, [rdi+2]
0x1400024f5  xor     eax, eax
0x1400024f7  lea     r14, [r14+rcx*2]
0x1400024fb  mov     [rdi+rcx*2], ax
0x1400024ff  cmp     word ptr [rdi], 22h ; '"'
0x140002503  lea     rsi, [rdi+2]
0x140002507  lea     rcx, String; "HKEY_CURRENT_CONFIG"
0x14000250e  cmovnz  rsi, rdi
0x140002512  call    cs:__imp_lstrlenW
0x140002518  lea     r15d, [rax+1]
0x14000251c  lea     r12d, [r15+r15]
0x140002520  mov     ecx, r12d; dwBytes
0x140002523  call    AllocateMemory
0x140002528  mov     [rsp+68h+arg_0], rax
0x14000252d  mov     rbp, rax
0x140002530  test    rax, rax
0x140002533  jnz     short loc_14000253D
0x140002535  mov     ecx, r13d
0x140002538  jmp     loc_14000291F
0x14000253d  xor     r9d, r9d
0x140002540  lea     rdx, aHkcu; "HKCU"
0x140002547  mov     rcx, rsi; lpString1
0x14000254a  call    StringCompareExW
0x14000254f  mov     edi, 1
0x140002554  test    eax, eax
0x140002556  jz      loc_140002754
0x14000255c  xor     r9d, r9d
0x14000255f  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x140002566  mov     rcx, rsi; lpString1
0x140002569  call    StringCompareExW
0x14000256e  test    eax, eax
0x140002570  jz      loc_140002754
0x140002576  xor     r9d, r9d
0x140002579  lea     rdx, aHkcr; "HKCR"
0x140002580  mov     rcx, rsi; lpString1
0x140002583  call    StringCompareExW
0x140002588  test    eax, eax
0x14000258a  jz      loc_140002740
0x140002590  xor     r9d, r9d
0x140002593  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x14000259a  mov     rcx, rsi; lpString1
0x14000259d  call    StringCompareExW
0x1400025a2  test    eax, eax
0x1400025a4  jz      loc_140002740
0x1400025aa  xor     r9d, r9d
0x1400025ad  lea     rdx, aHkcc; "HKCC"
0x1400025b4  mov     rcx, rsi; lpString1
0x1400025b7  call    StringCompareExW
0x1400025bc  test    eax, eax
0x1400025be  jz      loc_1400026BF
0x1400025c4  xor     r9d, r9d
0x1400025c7  lea     rdx, String; "HKEY_CURRENT_CONFIG"
0x1400025ce  mov     rcx, rsi; lpString1
0x1400025d1  call    StringCompareExW
0x1400025d6  test    eax, eax
0x1400025d8  jz      loc_1400026BF
0x1400025de  xor     r9d, r9d
0x1400025e1  lea     rdx, aHklm; "HKLM"
0x1400025e8  mov     rcx, rsi; lpString1
0x1400025eb  call    StringCompareExW
0x1400025f0  test    eax, eax
0x1400025f2  jz      loc_1400026AE
0x1400025f8  xor     r9d, r9d
0x1400025fb  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x140002602  mov     rcx, rsi; lpString1
0x140002605  call    StringCompareExW
0x14000260a  test    eax, eax
0x14000260c  jz      loc_1400026AE
0x140002612  xor     r9d, r9d
0x140002615  lea     rdx, aHku; "HKU"
0x14000261c  mov     rcx, rsi; lpString1
0x14000261f  call    StringCompareExW
0x140002624  test    eax, eax
0x140002626  jz      short loc_14000266B
0x140002628  xor     r9d, r9d
0x14000262b  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x140002632  mov     rcx, rsi; lpString1
0x140002635  call    StringCompareExW
0x14000263a  test    eax, eax
0x14000263c  jz      short loc_14000266B
0x14000263e  mov     ecx, 800401E4h; dwErrCode
0x140002643  call    cs:__imp_SetLastError
0x140002649  xor     r8d, r8d
0x14000264c  lea     edx, [rdi+67h]
0x14000264f  call    GetResString2FromModule
0x140002654  movsxd  rdx, dword ptr [rbx]
0x140002657  lea     r9, g_wszOptions; "QUERY"
0x14000265e  lea     r8, [rdx+rdx*4]
0x140002662  lea     r8, [r9+r8*4]
0x140002666  jmp     loc_140002723
0x14000266b  mov     qword ptr [rbx+8], 0FFFFFFFF80000003h
0x140002673  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x14000267a  mov     r8d, r15d
0x14000267d  mov     rcx, rbp
0x140002680  call    StringCopyW
0x140002685  test    r14, r14
0x140002688  jnz     loc_140002794
0x14000268e  lea     ecx, [r14+2]; dwBytes
0x140002692  call    AllocateMemory
0x140002697  mov     [rbx+50h], rax
0x14000269b  test    rax, rax
0x14000269e  jnz     loc_140002768
0x1400026a4  mov     ecx, r13d
0x1400026a7  call    SaveErrorMessage
0x1400026ac  jmp     short loc_14000272D
0x1400026ae  mov     qword ptr [rbx+8], 0FFFFFFFF80000002h
0x1400026b6  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x1400026bd  jmp     short loc_14000267A
0x1400026bf  mov     qword ptr [rbx+8], 0FFFFFFFF80000005h
0x1400026c7  lea     rdx, String; "HKEY_CURRENT_CONFIG"
0x1400026ce  mov     r8d, r15d
0x1400026d1  mov     rcx, rbp
0x1400026d4  call    StringCopyW
0x1400026d9  cmp     [rbx+10h], edi
0x1400026dc  jnz     short loc_1400026F0
0x1400026de  mov     ecx, 800401E4h; dwErrCode
0x1400026e3  call    cs:__imp_SetLastError
0x1400026e9  mov     edx, 69h ; 'i'
0x1400026ee  jmp     short loc_140002709
0x1400026f0  mov     eax, [rbx]
0x1400026f2  sub     eax, 6
0x1400026f5  cmp     eax, edi
0x1400026f7  ja      short loc_140002685
0x1400026f9  mov     ecx, 800401E4h; dwErrCode
0x1400026fe  call    cs:__imp_SetLastError
0x140002704  mov     edx, 6Ah ; 'j'
0x140002709  xor     r8d, r8d
0x14000270c  call    GetResString2FromModule
0x140002711  movsxd  rcx, dword ptr [rbx]
0x140002714  lea     r9, g_wszOptions; "QUERY"
0x14000271b  lea     rdx, [rcx+rcx*4]
0x14000271f  lea     r8, [r9+rdx*4]
0x140002723  mov     rdx, rax
0x140002726  mov     ecx, edi
0x140002728  call    SetReason2
0x14000272d  xor     edi, edi
0x14000272f  lea     rcx, [rsp+68h+arg_0]
0x140002734  call    FreeMemory
0x140002739  mov     eax, edi
0x14000273b  jmp     loc_140002926
0x140002740  mov     qword ptr [rbx+8], 0FFFFFFFF80000000h
0x140002748  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x14000274f  jmp     loc_1400026CE
0x140002754  mov     qword ptr [rbx+8], 0FFFFFFFF80000001h
0x14000275c  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x140002763  jmp     loc_1400026CE
0x140002768  mov     ecx, r12d; dwBytes
0x14000276b  call    AllocateMemory
0x140002770  mov     [rbx+58h], rax
0x140002774  test    rax, rax
0x140002777  jnz     short loc_140002783
0x140002779  mov     ecx, r13d
0x14000277c  call    SaveErrorMessage
0x140002781  xor     edi, edi
0x140002783  mov     rcx, [rbx+58h]
0x140002787  mov     r8d, r15d
0x14000278a  mov     rdx, rbp
0x14000278d  call    StringCopyW
0x140002792  jmp     short loc_14000272F
0x140002794  mov     rcx, r14; lpString
0x140002797  call    cs:__imp_lstrlenW
0x14000279d  cmp     eax, edi
0x14000279f  jbe     short loc_1400027B7
0x1400027a1  lea     ecx, [rax-1]
0x1400027a4  mov     eax, 5Ch ; '\'
0x1400027a9  cmp     [r14+rcx*2], ax
0x1400027ae  jnz     short loc_1400027B7
0x1400027b0  xor     eax, eax
0x1400027b2  mov     [r14+rcx*2], ax
0x1400027b7  mov     rcx, r14; lpString
0x1400027ba  call    cs:__imp_lstrlenW
0x1400027c0  test    eax, eax
0x1400027c2  jz      loc_1400028BA
0x1400027c8  mov     eax, r13d
0x1400027cb  mov     esi, r13d
0x1400027ce  mov     r12d, 0FFh
0x1400027d4  cmp     eax, esi
0x1400027d6  jz      short loc_1400027EF
0x1400027d8  mov     ecx, eax
0x1400027da  sub     ecx, esi
0x1400027dc  cmp     ecx, edi
0x1400027de  jz      loc_1400028BA
0x1400027e4  cmp     ecx, r12d
0x1400027e7  jg      loc_1400028BA
0x1400027ed  mov     esi, eax
0x1400027ef  lea     r9d, [rax+1]
0x1400027f3  mov     edx, 5Ch ; '\'
0x1400027f8  mov     rcx, r14
0x1400027fb  call    FindChar2
0x140002800  cmp     eax, r13d
0x140002803  jnz     short loc_1400027D4
0x140002805  mov     rcx, r14; lpString
0x140002808  call    cs:__imp_lstrlenW
0x14000280e  lea     ecx, [rax-1]
0x140002811  cmp     esi, ecx
0x140002813  jz      loc_1400028BA
0x140002819  cmp     esi, r13d
0x14000281c  jnz     short loc_140002827
0x14000281e  cmp     eax, r12d
0x140002821  jg      loc_1400028BA
0x140002827  sub     eax, esi
0x140002829  cmp     eax, r12d
0x14000282c  jg      loc_1400028BA
0x140002832  xor     ecx, ecx; dwErrCode
0x140002834  call    cs:__imp_SetLastError
0x14000283a  mov     rcx, r14; lpString
0x14000283d  call    cs:__imp_lstrlenW
0x140002843  lea     esi, [rax+1]
0x140002846  lea     ecx, [rsi+rsi]; dwBytes
0x140002849  call    AllocateMemory
0x14000284e  mov     [rbx+50h], rax
0x140002852  test    rax, rax
0x140002855  jz      loc_1400026A4
0x14000285b  mov     r8d, esi
0x14000285e  mov     rdx, r14
0x140002861  mov     rcx, rax
0x140002864  call    StringCopyW
0x140002869  add     esi, 2
0x14000286c  add     esi, r15d
0x14000286f  lea     ecx, [rsi+rsi]; dwBytes
0x140002872  call    AllocateMemory
0x140002877  mov     [rbx+58h], rax
0x14000287b  test    rax, rax
0x14000287e  jz      loc_1400026A4
0x140002884  mov     r8d, esi
0x140002887  mov     rdx, rbp
0x14000288a  mov     rcx, rax
0x14000288d  call    StringCopyW
0x140002892  mov     rcx, [rbx+58h]
0x140002896  lea     rdx, asc_14001081C; "\\"
0x14000289d  mov     r8d, esi
0x1400028a0  call    StringConcatW
0x1400028a5  mov     rdx, [rbx+50h]
0x1400028a9  mov     r8d, esi
0x1400028ac  mov     rcx, [rbx+58h]
0x1400028b0  call    StringConcatW
0x1400028b5  jmp     loc_14000272F
0x1400028ba  mov     ecx, 80090003h; dwErrCode
0x1400028bf  call    cs:__imp_SetLastError
0x1400028c5  xor     edi, edi
0x1400028c7  call    cs:__imp_GetLastError
0x1400028cd  cmp     eax, 57h ; 'W'
0x1400028d0  jnz     short loc_1400028DF
0x1400028d2  mov     ecx, r13d
0x1400028d5  call    SaveErrorMessage
0x1400028da  jmp     loc_14000272F
0x1400028df  mov     ecx, 800401E4h; dwErrCode
0x1400028e4  call    cs:__imp_SetLastError
0x1400028ea  xor     r8d, r8d
0x1400028ed  lea     edx, [r8+68h]
0x1400028f1  call    GetResString2FromModule
0x1400028f6  movsxd  rcx, dword ptr [rbx]
0x1400028f9  lea     r9, g_wszOptions; "QUERY"
0x140002900  lea     rdx, [rcx+rcx*4]
0x140002904  mov     ecx, 1
0x140002909  lea     r8, [r9+rdx*4]
0x14000290d  mov     rdx, rax
0x140002910  call    SetReason2
0x140002915  jmp     loc_14000272F
0x14000291a  mov     ecx, 57h ; 'W'
0x14000291f  call    SaveErrorMessage
0x140002924  xor     eax, eax
0x140002926  add     rsp, 28h
0x14000292a  pop     r15
0x14000292c  pop     r14
0x14000292e  pop     r13
0x140002930  pop     r12
0x140002932  pop     rdi
0x140002933  pop     rsi
0x140002934  pop     rbp
0x140002935  pop     rbx
0x140002936  retn
```
