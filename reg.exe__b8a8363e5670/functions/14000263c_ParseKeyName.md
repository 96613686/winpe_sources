# ParseKeyName

- ea: `0x14000263c`
- end: `0x140002a72`
- name: `ParseKeyName`
- size: `1078`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001e90`

## callees

- `0x140002578`
- `0x14000263c`
- `0x140002ce4`
- `0x14000ce50`
- `0x14000d0c4`
- `0x14000d2d0`
- `0x14000d694`
- `0x14000e600`
- `0x14000ee5c`
- `0x14000ef5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400027dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400027dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400028f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002987`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400026a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000292f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400029c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400026a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000292f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400029c4`

## string_xrefs

- `0x14000269f`: `HKEY_CURRENT_CONFIG`

## pseudocode

```c
__int64 __fastcall ParseKeyName(PCNZWCH lpString1, int *a2, __int64 a3)
{
  const WCHAR *v5; // r14
  int Char2; // eax
  const WCHAR *v7; // rsi
  unsigned int v8; // r15d
  __int64 v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 ResString2FromModule; // rax
  wchar_t *v13; // r8
  const WCHAR *v14; // rdx
  unsigned int v15; // edi
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // esi
  __int64 v26; // rax
  unsigned int v27; // esi
  __int64 v28; // rax
  __int64 Memory; // [rsp+70h] [rbp+8h] BYREF

  if ( !lpString1 || !a2 || (unsigned int)*a2 > 0xB )
  {
    v10 = 87;
    goto LABEL_52;
  }
  v5 = 0;
  Char2 = FindChar2(lpString1, 92, a3, 0);
  if ( Char2 != -1 )
  {
    v5 = &lpString1[Char2 + 1];
    lpString1[Char2] = 0;
  }
  v7 = lpString1 + 1;
  if ( *lpString1 != 34 )
    v7 = lpString1;
  v8 = lstrlenW(L"HKEY_CURRENT_CONFIG") + 1;
  Memory = AllocateMemory(2 * v8);
  v9 = Memory;
  if ( Memory )
  {
    if ( (unsigned int)StringCompareExW(v7, L"HKCU") && (unsigned int)StringCompareExW(v7, L"HKEY_CURRENT_USER") )
    {
      if ( (unsigned int)StringCompareExW(v7, L"HKCR") && (unsigned int)StringCompareExW(v7, L"HKEY_CLASSES_ROOT") )
      {
        if ( (unsigned int)StringCompareExW(v7, L"HKCC") && (unsigned int)StringCompareExW(v7, L"HKEY_CURRENT_CONFIG") )
        {
          if ( (unsigned int)StringCompareExW(v7, L"HKLM") && (unsigned int)StringCompareExW(v7, L"HKEY_LOCAL_MACHINE") )
          {
            if ( (unsigned int)StringCompareExW(v7, L"HKU") && (unsigned int)StringCompareExW(v7, L"HKEY_USERS") )
            {
              SetLastError(0x800401E4);
              ResString2FromModule = GetResString2FromModule(v11, 104, 0);
              v13 = &g_wszOptions[10 * *a2];
LABEL_37:
              SetReason2(1, ResString2FromModule, v13);
              goto LABEL_48;
            }
            *((_QWORD *)a2 + 1) = -2147483645;
            v14 = L"HKEY_USERS";
          }
          else
          {
            *((_QWORD *)a2 + 1) = -2147483646;
            v14 = L"HKEY_LOCAL_MACHINE";
          }
          StringCopyW(v9, v14, v8);
LABEL_23:
          v15 = 1;
          if ( v5 )
          {
            v21 = lstrlenW(v5);
            if ( v21 > 1 )
            {
              v22 = v21 - 1;
              if ( v5[v22] == 92 )
                v5[v22] = 0;
            }
            if ( !(unsigned int)IsValidSubKey(v5) )
            {
              v15 = 0;
              if ( GetLastError() == 87 )
              {
                SaveErrorMessage(0xFFFFFFFFLL);
              }
              else
              {
                SetLastError(0x800401E4);
                v24 = GetResString2FromModule(v23, 104, 0);
                SetReason2(1, v24, &g_wszOptions[10 * *a2]);
              }
              goto LABEL_50;
            }
            v25 = lstrlenW(v5) + 1;
            v26 = AllocateMemory(2 * v25);
            *((_QWORD *)a2 + 10) = v26;
            if ( v26 )
            {
              StringCopyW(v26, v5, v25);
              v27 = v8 + v25 + 2;
              v28 = AllocateMemory(2 * v27);
              *((_QWORD *)a2 + 11) = v28;
              if ( v28 )
              {
                StringCopyW(v28, v9, v27);
                StringConcatW(*((_QWORD *)a2 + 11), L"\\", v27);
                StringConcatW(*((_QWORD *)a2 + 11), *((_QWORD *)a2 + 10), v27);
                goto LABEL_50;
              }
            }
          }
          else
          {
            v16 = AllocateMemory(2u);
            *((_QWORD *)a2 + 10) = v16;
            if ( v16 )
            {
              v17 = AllocateMemory(2 * v8);
              *((_QWORD *)a2 + 11) = v17;
              if ( !v17 )
              {
                SaveErrorMessage(0xFFFFFFFFLL);
                v15 = 0;
              }
              StringCopyW(*((_QWORD *)a2 + 11), v9, v8);
              goto LABEL_50;
            }
          }
          SaveErrorMessage(0xFFFFFFFFLL);
LABEL_48:
          v15 = 0;
LABEL_50:
          FreeMemory(&Memory);
          return v15;
        }
        *((_QWORD *)a2 + 1) = -2147483643;
        v18 = L"HKEY_CURRENT_CONFIG";
      }
      else
      {
        *((_QWORD *)a2 + 1) = 0xFFFFFFFF80000000uLL;
        v18 = L"HKEY_CLASSES_ROOT";
      }
    }
    else
    {
      *((_QWORD *)a2 + 1) = -2147483647;
      v18 = L"HKEY_CURRENT_USER";
    }
    StringCopyW(v9, v18, v8);
    if ( a2[4] == 1 )
    {
      SetLastError(0x800401E4);
      v20 = 105;
    }
    else
    {
      if ( (unsigned int)(*a2 - 6) > 1 )
        goto LABEL_23;
      SetLastError(0x800401E4);
      v20 = 106;
    }
    ResString2FromModule = GetResString2FromModule(v19, v20, 0);
    v13 = &g_wszOptions[10 * *a2];
    goto LABEL_37;
  }
  v10 = 0xFFFFFFFFLL;
LABEL_52:
  SaveErrorMessage(v10);
  return 0;
}

```

## disassembly

```asm
0x14000263c  push    rbx
0x14000263e  push    rbp
0x14000263f  push    rsi
0x140002640  push    rdi
0x140002641  push    r12
0x140002643  push    r13
0x140002645  push    r14
0x140002647  push    r15
0x140002649  sub     rsp, 28h
0x14000264d  mov     rbx, rdx
0x140002650  mov     rdi, rcx
0x140002653  test    rcx, rcx
0x140002656  jz      loc_140002A54
0x14000265c  test    rdx, rdx
0x14000265f  jz      loc_140002A54
0x140002665  cmp     dword ptr [rdx], 0Bh
0x140002668  ja      loc_140002A54
0x14000266e  xor     r14d, r14d
0x140002671  xor     r9d, r9d
0x140002674  lea     edx, [r14+5Ch]
0x140002678  call    FindChar2
0x14000267d  cmp     eax, 0FFFFFFFFh
0x140002680  jz      short loc_140002693
0x140002682  movsxd  rcx, eax
0x140002685  lea     r14, [rdi+2]
0x140002689  xor     eax, eax
0x14000268b  lea     r14, [r14+rcx*2]
0x14000268f  mov     [rdi+rcx*2], ax
0x140002693  cmp     word ptr [rdi], 22h ; '"'
0x140002697  lea     rsi, [rdi+2]
0x14000269b  cmovnz  rsi, rdi
0x14000269f  lea     rdi, String; "HKEY_CURRENT_CONFIG"
0x1400026a6  mov     rcx, rdi; lpString
0x1400026a9  call    cs:__imp_lstrlenW
0x1400026b0  nop     dword ptr [rax+rax+00h]
0x1400026b5  lea     r15d, [rax+1]
0x1400026b9  lea     r12d, [r15+r15]
0x1400026bd  mov     ecx, r12d; dwBytes
0x1400026c0  call    AllocateMemory
0x1400026c5  mov     [rsp+68h+arg_0], rax
0x1400026ca  mov     rbp, rax
0x1400026cd  test    rax, rax
0x1400026d0  jnz     short loc_1400026DA
0x1400026d2  or      ecx, 0FFFFFFFFh
0x1400026d5  jmp     loc_140002A59
0x1400026da  xor     r9d, r9d
0x1400026dd  lea     rdx, aHkcu; "HKCU"
0x1400026e4  mov     rcx, rsi; lpString1
0x1400026e7  call    StringCompareExW
0x1400026ec  mov     r13d, 1
0x1400026f2  test    eax, eax
0x1400026f4  jz      loc_1400028CD
0x1400026fa  xor     r9d, r9d
0x1400026fd  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x140002704  mov     rcx, rsi; lpString1
0x140002707  call    StringCompareExW
0x14000270c  test    eax, eax
0x14000270e  jz      loc_1400028CD
0x140002714  xor     r9d, r9d
0x140002717  lea     rdx, aHkcr; "HKCR"
0x14000271e  mov     rcx, rsi; lpString1
0x140002721  call    StringCompareExW
0x140002726  test    eax, eax
0x140002728  jz      loc_1400028BC
0x14000272e  xor     r9d, r9d
0x140002731  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x140002738  mov     rcx, rsi; lpString1
0x14000273b  call    StringCompareExW
0x140002740  test    eax, eax
0x140002742  jz      loc_1400028BC
0x140002748  xor     r9d, r9d
0x14000274b  lea     rdx, aHkcc; "HKCC"
0x140002752  mov     rcx, rsi; lpString1
0x140002755  call    StringCompareExW
0x14000275a  test    eax, eax
0x14000275c  jz      loc_140002888
0x140002762  xor     r9d, r9d
0x140002765  mov     rdx, rdi; lpString2
0x140002768  mov     rcx, rsi; lpString1
0x14000276b  call    StringCompareExW
0x140002770  test    eax, eax
0x140002772  jz      loc_140002888
0x140002778  xor     r9d, r9d
0x14000277b  lea     rdx, aHklm; "HKLM"
0x140002782  mov     rcx, rsi; lpString1
0x140002785  call    StringCompareExW
0x14000278a  test    eax, eax
0x14000278c  jz      loc_140002877
0x140002792  xor     r9d, r9d
0x140002795  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x14000279c  mov     rcx, rsi; lpString1
0x14000279f  call    StringCompareExW
0x1400027a4  test    eax, eax
0x1400027a6  jz      loc_140002877
0x1400027ac  xor     r9d, r9d
0x1400027af  lea     rdx, aHku; "HKU"
0x1400027b6  mov     rcx, rsi; lpString1
0x1400027b9  call    StringCompareExW
0x1400027be  test    eax, eax
0x1400027c0  jz      short loc_14000280C
0x1400027c2  xor     r9d, r9d
0x1400027c5  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x1400027cc  mov     rcx, rsi; lpString1
0x1400027cf  call    StringCompareExW
0x1400027d4  test    eax, eax
0x1400027d6  jz      short loc_14000280C
0x1400027d8  mov     ecx, 800401E4h; dwErrCode
0x1400027dd  call    cs:__imp_SetLastError
0x1400027e4  nop     dword ptr [rax+rax+00h]
0x1400027e9  xor     r8d, r8d
0x1400027ec  lea     edx, [r13+67h]
0x1400027f0  call    GetResString2FromModule
0x1400027f5  movsxd  rdx, dword ptr [rbx]
0x1400027f8  lea     r9, g_wszOptions; "QUERY"
0x1400027ff  lea     r8, [rdx+rdx*4]
0x140002803  lea     r8, [r9+r8*4]
0x140002807  jmp     loc_14000291C
0x14000280c  mov     qword ptr [rbx+8], 0FFFFFFFF80000003h
0x140002814  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x14000281b  mov     r8d, r15d
0x14000281e  mov     rcx, rbp
0x140002821  call    StringCopyW
0x140002826  mov     edi, r13d
0x140002829  test    r14, r14
0x14000282c  jnz     loc_14000292C
0x140002832  lea     ecx, [r14+2]; dwBytes
0x140002836  call    AllocateMemory
0x14000283b  mov     [rbx+50h], rax
0x14000283f  test    rax, rax
0x140002842  jz      loc_140002A09
0x140002848  mov     ecx, r12d; dwBytes
0x14000284b  call    AllocateMemory
0x140002850  mov     [rbx+58h], rax
0x140002854  test    rax, rax
0x140002857  jnz     short loc_140002863
0x140002859  or      ecx, 0FFFFFFFFh
0x14000285c  call    SaveErrorMessage
0x140002861  xor     edi, edi
0x140002863  mov     rcx, [rbx+58h]
0x140002867  mov     r8d, r15d
0x14000286a  mov     rdx, rbp
0x14000286d  call    StringCopyW
0x140002872  jmp     loc_140002A46
0x140002877  mov     qword ptr [rbx+8], 0FFFFFFFF80000002h
0x14000287f  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x140002886  jmp     short loc_14000281B
0x140002888  mov     qword ptr [rbx+8], 0FFFFFFFF80000005h
0x140002890  mov     rdx, rdi
0x140002893  mov     r8d, r15d
0x140002896  mov     rcx, rbp
0x140002899  call    StringCopyW
0x14000289e  cmp     [rbx+10h], r13d
0x1400028a2  jnz     short loc_1400028DE
0x1400028a4  mov     ecx, 800401E4h; dwErrCode
0x1400028a9  call    cs:__imp_SetLastError
0x1400028b0  nop     dword ptr [rax+rax+00h]
0x1400028b5  mov     edx, 69h ; 'i'
0x1400028ba  jmp     short loc_140002902
0x1400028bc  mov     qword ptr [rbx+8], 0FFFFFFFF80000000h
0x1400028c4  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x1400028cb  jmp     short loc_140002893
0x1400028cd  mov     qword ptr [rbx+8], 0FFFFFFFF80000001h
0x1400028d5  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1400028dc  jmp     short loc_140002893
0x1400028de  mov     eax, [rbx]
0x1400028e0  sub     eax, 6
0x1400028e3  cmp     eax, r13d
0x1400028e6  ja      loc_140002826
0x1400028ec  mov     ecx, 800401E4h; dwErrCode
0x1400028f1  call    cs:__imp_SetLastError
0x1400028f8  nop     dword ptr [rax+rax+00h]
0x1400028fd  mov     edx, 6Ah ; 'j'
0x140002902  xor     r8d, r8d
0x140002905  call    GetResString2FromModule
0x14000290a  movsxd  rcx, dword ptr [rbx]
0x14000290d  lea     r9, g_wszOptions; "QUERY"
0x140002914  lea     rdx, [rcx+rcx*4]
0x140002918  lea     r8, [r9+rdx*4]
0x14000291c  mov     rdx, rax
0x14000291f  mov     ecx, r13d
0x140002922  call    SetReason2
0x140002927  jmp     loc_140002A11
0x14000292c  mov     rcx, r14; lpString
0x14000292f  call    cs:__imp_lstrlenW
0x140002936  nop     dword ptr [rax+rax+00h]
0x14000293b  cmp     eax, r13d
0x14000293e  jbe     short loc_140002956
0x140002940  lea     ecx, [rax-1]
0x140002943  mov     eax, 5Ch ; '\'
0x140002948  cmp     [r14+rcx*2], ax
0x14000294d  jnz     short loc_140002956
0x14000294f  xor     eax, eax
0x140002951  mov     [r14+rcx*2], ax
0x140002956  mov     rcx, r14; lpString
0x140002959  call    IsValidSubKey
0x14000295e  test    eax, eax
0x140002960  jnz     short loc_1400029C1
0x140002962  xor     edi, edi
0x140002964  call    cs:__imp_GetLastError
0x14000296b  nop     dword ptr [rax+rax+00h]
0x140002970  cmp     eax, 57h ; 'W'
0x140002973  jnz     short loc_140002982
0x140002975  or      ecx, 0FFFFFFFFh
0x140002978  call    SaveErrorMessage
0x14000297d  jmp     loc_140002A46
0x140002982  mov     ecx, 800401E4h; dwErrCode
0x140002987  call    cs:__imp_SetLastError
0x14000298e  nop     dword ptr [rax+rax+00h]
0x140002993  xor     r8d, r8d
0x140002996  lea     edx, [r8+68h]
0x14000299a  call    GetResString2FromModule
0x14000299f  movsxd  rcx, dword ptr [rbx]
0x1400029a2  lea     r9, g_wszOptions; "QUERY"
0x1400029a9  lea     rdx, [rcx+rcx*4]
0x1400029ad  mov     ecx, r13d
0x1400029b0  lea     r8, [r9+rdx*4]
0x1400029b4  mov     rdx, rax
0x1400029b7  call    SetReason2
0x1400029bc  jmp     loc_140002A46
0x1400029c1  mov     rcx, r14; lpString
0x1400029c4  call    cs:__imp_lstrlenW
0x1400029cb  nop     dword ptr [rax+rax+00h]
0x1400029d0  lea     esi, [rax+1]
0x1400029d3  lea     ecx, [rsi+rsi]; dwBytes
0x1400029d6  call    AllocateMemory
0x1400029db  mov     [rbx+50h], rax
0x1400029df  test    rax, rax
0x1400029e2  jz      short loc_140002A09
0x1400029e4  mov     r8d, esi
0x1400029e7  mov     rdx, r14
0x1400029ea  mov     rcx, rax
0x1400029ed  call    StringCopyW
0x1400029f2  add     esi, 2
0x1400029f5  add     esi, r15d
0x1400029f8  lea     ecx, [rsi+rsi]; dwBytes
0x1400029fb  call    AllocateMemory
0x140002a00  mov     [rbx+58h], rax
0x140002a04  test    rax, rax
0x140002a07  jnz     short loc_140002A15
0x140002a09  or      ecx, 0FFFFFFFFh
0x140002a0c  call    SaveErrorMessage
0x140002a11  xor     edi, edi
0x140002a13  jmp     short loc_140002A46
0x140002a15  mov     r8d, esi
0x140002a18  mov     rdx, rbp
0x140002a1b  mov     rcx, rax
0x140002a1e  call    StringCopyW
0x140002a23  mov     rcx, [rbx+58h]
0x140002a27  lea     rdx, asc_14001181C; "\\"
0x140002a2e  mov     r8d, esi
0x140002a31  call    StringConcatW
0x140002a36  mov     rdx, [rbx+50h]
0x140002a3a  mov     r8d, esi
0x140002a3d  mov     rcx, [rbx+58h]
0x140002a41  call    StringConcatW
0x140002a46  lea     rcx, [rsp+68h+arg_0]
0x140002a4b  call    FreeMemory
0x140002a50  mov     eax, edi
0x140002a52  jmp     short loc_140002A60
0x140002a54  mov     ecx, 57h ; 'W'
0x140002a59  call    SaveErrorMessage
0x140002a5e  xor     eax, eax
0x140002a60  add     rsp, 28h
0x140002a64  pop     r15
0x140002a66  pop     r14
0x140002a68  pop     r13
0x140002a6a  pop     r12
0x140002a6c  pop     rdi
0x140002a6d  pop     rsi
0x140002a6e  pop     rbp
0x140002a6f  pop     rbx
0x140002a70  retn
```
