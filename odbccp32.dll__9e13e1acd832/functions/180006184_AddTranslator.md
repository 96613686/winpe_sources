# AddTranslator

- ea: `0x180006184`
- end: `0x180006633`
- name: `AddTranslator`
- size: `1199`
- prototype: `__int64 __fastcall(__int64, WCHAR *, wchar_t *, wchar_t *, unsigned __int16, _WORD *, __int16, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180009464`

## callees

- `0x180001010`
- `0x1800017c0`
- `0x180002940`
- `0x180002e14`
- `0x180004bac`
- `0x180005fd4`
- `0x180006184`
- `0x1800069d8`
- `0x1800074c4`
- `0x18000829c`
- `0x18000844c`
- `0x18000a320`
- `0x180013fa8`

## import_xrefs

- `msvcrt!_waccess` at `0x1800063b0`
- `msvcrt!_waccess` at `0x1800063ec`
- `msvcrt!_waccess` at `0x1800063b0`
- `msvcrt!_waccess` at `0x1800063ec`
- `msvcrt!_wmakepath_s` at `0x18000637f`
- `msvcrt!_wmakepath_s` at `0x18000637f`
- `msvcrt!_wsplitpath_s` at `0x180006355`
- `msvcrt!_wsplitpath_s` at `0x180006355`
- `msvcrt!calloc` at `0x1800061d1`
- `msvcrt!calloc` at `0x1800061d1`

## string_xrefs

- `0x180006583`: `Installed`

## pseudocode

```c
__int64 __fastcall AddTranslator(
        __int64 a1,
        WCHAR *a2,
        wchar_t *a3,
        wchar_t *a4,
        unsigned __int16 a5,
        _WORD *a6,
        __int16 a7,
        int *a8)
{
  int *v8; // r12
  unsigned int v11; // ebp
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  wchar_t *v15; // r15
  unsigned int v16; // r9d
  wchar_t *v17; // rbx
  const wchar_t *v18; // r8
  const wchar_t *v19; // r8
  wchar_t *v20; // rcx
  _WORD *v21; // rsi
  __int64 v22; // r11
  __int64 v23; // rdx
  int v24; // esi
  BYTE Data[4]; // [rsp+50h] [rbp-48h] BYREF
  int v26; // [rsp+54h] [rbp-44h] BYREF

  v8 = &v26;
  *(_DWORD *)Data = 0;
  v26 = 0;
  v11 = 1;
  if ( a8 )
    v8 = a8;
  v12 = (wchar_t *)calloc(0xC30u, 1u);
  v13 = v12;
  if ( !v12 )
  {
    MemError();
    return 0;
  }
  v15 = v12 + 260;
  if ( (unsigned int)GetFilename(a2, (wchar_t *)L"Translator", v12, v12 + 260) )
  {
    v17 = v15 + 520;
    if ( *v13 )
    {
      if ( !a3 )
      {
LABEL_17:
        v18 = v13;
        goto LABEL_15;
      }
      if ( *a3 )
      {
        StringCchCopyW(v15 + 520, 0x104u, v13);
        if ( !(unsigned int)IsSamePath(v15 + 520, a3) )
        {
LABEL_11:
          PostInstError(12);
          v11 = 0;
          goto LABEL_57;
        }
LABEL_19:
        if ( (unsigned int)GetFilename(a2, (wchar_t *)L"Setup", v13, v15 + 260) )
        {
          if ( !*v13 )
            goto LABEL_27;
          v20 = v15 + 520;
          if ( *v17 )
          {
            if ( !(unsigned int)IsSamePath(v20, v13) )
              goto LABEL_11;
LABEL_27:
            v21 = v15 + 1040;
            if ( (int)SQLGetPrivateProfileStringCover(a2, L"Translator", &SubKey, v13, 260, L"ODBCINST.INI") <= 0 )
            {
              *v21 = 0;
            }
            else
            {
              _wsplitpath_s(v13, v15 + 780, 0x104u, v15 + 1040, 0x104u, 0, 0, 0, 0);
              _wmakepath_s(v13, 0x104u, v15 + 780, v15 + 1040, 0, 0);
              StringCchCopyW(v15 + 1040, 0x104u, v13);
            }
            if ( !*v17 )
            {
              if ( !*v21 || _waccess(v15 + 1040, 0) )
                GetTargetDirectory(v17);
              else
                StringCchCopyW(v15 + 520, 0x104u, v15 + 1040);
            }
            if ( *v21 && !_waccess(v15 + 1040, 0) )
              StringCchCopyW(v15 + 520, 0x104u, v15 + 1040);
            v22 = -1;
            if ( !a4 )
              goto LABEL_47;
            if ( a7 == 2 )
            {
              if ( a5 )
              {
                v23 = -1;
                do
                  ++v23;
                while ( v17[v23] );
                if ( v23 + 1 > (unsigned __int64)a5 )
                {
                  PostInstError(2);
                  v11 = 0;
                  goto LABEL_57;
                }
                goto LABEL_46;
              }
            }
            else if ( a5 )
            {
LABEL_46:
              StringCchCopyW(a4, a5, v17);
            }
LABEL_47:
            if ( a6 )
            {
              do
                ++v22;
              while ( v17[v22] );
              *a6 = v22;
            }
            if ( a7 != 1 )
            {
              v24 = 1;
              if ( !(unsigned int)cpGetPrivateProfileString(
                                    -2147483646,
                                    a2,
                                    L"UsageCount",
                                    &SubKey,
                                    16,
                                    0,
                                    Data,
                                    4,
                                    L"ODBCINST.INI",
                                    0) )
              {
                *(_DWORD *)Data = 0;
                if ( (int)SQLGetPrivateProfileStringCover(L"ODBC Translators", a2, &SubKey, v13, 260, L"ODBCINST.INI") > 0 )
                  v24 = 2;
              }
              MakePath(v13, v17, v13 + 260);
              SQLWritePrivateProfileStringW(a2, L"Translator", v13, L"ODBCINST.INI");
              MakePath(v13, v17, v15 + 260);
              SQLWritePrivateProfileStringW(a2, L"Setup", v13, L"ODBCINST.INI");
              SQLWritePrivateProfileStringW(L"ODBC Translators", a2, L"Installed", L"ODBCINST.INI");
              *(_DWORD *)Data += v24;
              cpWritePrivateProfileString(HKEY_LOCAL_MACHINE, Data, (__int64)L"ODBCINST.INI");
            }
            if ( !(unsigned int)cpGetPrivateProfileString(
                                  -2147483646,
                                  a2,
                                  L"UsageCount",
                                  &SubKey,
                                  16,
                                  0,
                                  v8,
                                  4,
                                  L"ODBCINST.INI",
                                  0) )
              *v8 = 0;
            goto LABEL_57;
          }
          v19 = v13;
        }
        else
        {
          v19 = v15;
          v20 = v15 + 260;
        }
        StringCchCopyW(v20, 0x104u, v19);
        goto LABEL_27;
      }
    }
    else
    {
      if ( !a3 )
        goto LABEL_18;
      if ( *a3 )
      {
        v18 = a3;
LABEL_15:
        StringCchCopyW(v15 + 520, 0x104u, v18);
        goto LABEL_19;
      }
    }
    if ( *v13 )
      goto LABEL_17;
LABEL_18:
    *v17 = 0;
    goto LABEL_19;
  }
  PostInstError(23);
  v11 = v16;
LABEL_57:
  OFree(v13);
  return v11;
}

```

## disassembly

```asm
0x180006184  mov     rax, rsp
0x180006187  mov     [rax+10h], rbx
0x18000618b  mov     [rax+20h], r9
0x18000618f  mov     [rax+8], rcx
0x180006193  push    rbp
0x180006194  push    rsi
0x180006195  push    rdi
0x180006196  push    r12
0x180006198  push    r13
0x18000619a  push    r14
0x18000619c  push    r15
0x18000619e  sub     rsp, 60h
0x1800061a2  xor     ebx, ebx
0x1800061a4  lea     r12, [rax-44h]
0x1800061a8  mov     [rax+8], bx
0x1800061ac  mov     r14, rdx
0x1800061af  mov     [rax-48h], ebx
0x1800061b2  mov     ecx, 0C30h; Count
0x1800061b7  mov     [rax-44h], ebx
0x1800061ba  mov     rsi, r8
0x1800061bd  mov     rax, [rsp+98h+arg_38]
0x1800061c5  lea     ebp, [rbx+1]
0x1800061c8  test    rax, rax
0x1800061cb  mov     edx, ebp; Size
0x1800061cd  cmovnz  r12, rax
0x1800061d1  call    cs:__imp_calloc
0x1800061d7  mov     rdi, rax
0x1800061da  test    rax, rax
0x1800061dd  jnz     short loc_1800061EB
0x1800061df  call    MemError
0x1800061e4  xor     eax, eax
0x1800061e6  jmp     loc_18000661B
0x1800061eb  lea     r15, [rax+208h]
0x1800061f2  mov     r8, rdi; pszDest
0x1800061f5  lea     rdx, aTranslator; "Translator"
0x1800061fc  mov     [rsp+98h+DirCount], r15; STRSAFE_LPWSTR
0x180006201  mov     rcx, r14; String1
0x180006204  call    GetFilename
0x180006209  xor     r9d, r9d
0x18000620c  test    eax, eax
0x18000620e  jnz     short loc_180006220
0x180006210  lea     ecx, [rax+17h]
0x180006213  call    PostInstError
0x180006218  mov     ebp, r9d
0x18000621b  jmp     loc_180006611
0x180006220  lea     r13, [r15+208h]
0x180006227  mov     eax, 104h
0x18000622c  lea     rbx, [r13+208h]
0x180006233  cmp     [rdi], r9w
0x180006237  jz      short loc_180006273
0x180006239  test    rsi, rsi
0x18000623c  jz      short loc_180006294
0x18000623e  cmp     [rsi], r9w
0x180006242  jz      short loc_18000628E
0x180006244  mov     r8, rdi; pszSrc
0x180006247  mov     edx, eax; cchDest
0x180006249  mov     rcx, rbx; pszDest
0x18000624c  call    StringCchCopyW
0x180006251  mov     rdx, rsi; wchar_t *
0x180006254  mov     rcx, rbx; Path
0x180006257  call    IsSamePath
0x18000625c  xor     esi, esi
0x18000625e  test    eax, eax
0x180006260  jnz     short loc_18000629F
0x180006262  mov     ecx, 0Ch
0x180006267  call    PostInstError
0x18000626c  mov     ebp, esi
0x18000626e  jmp     loc_180006611
0x180006273  test    rsi, rsi
0x180006276  jz      short loc_180006299
0x180006278  cmp     [rsi], r9w
0x18000627c  jz      short loc_18000628E
0x18000627e  mov     r8, rsi; pszSrc
0x180006281  mov     rdx, rax; cchDest
0x180006284  mov     rcx, rbx; pszDest
0x180006287  call    StringCchCopyW
0x18000628c  jmp     short loc_18000629D
0x18000628e  cmp     [rdi], r9w
0x180006292  jz      short loc_180006299
0x180006294  mov     r8, rdi
0x180006297  jmp     short loc_180006281
0x180006299  mov     [rbx], r9w
0x18000629d  xor     esi, esi
0x18000629f  mov     r8, rdi; pszDest
0x1800062a2  mov     [rsp+98h+DirCount], r13; STRSAFE_LPWSTR
0x1800062a7  lea     rdx, aSetup; "Setup"
0x1800062ae  mov     rcx, r14; String1
0x1800062b1  call    GetFilename
0x1800062b6  test    eax, eax
0x1800062b8  jnz     short loc_1800062C2
0x1800062ba  mov     r8, r15
0x1800062bd  mov     rcx, r13
0x1800062c0  jmp     short loc_1800062E0
0x1800062c2  cmp     [rdi], si
0x1800062c5  jz      short loc_1800062EA
0x1800062c7  mov     rcx, rbx; Path
0x1800062ca  cmp     [rbx], si
0x1800062cd  jz      short loc_1800062DD
0x1800062cf  mov     rdx, rdi; wchar_t *
0x1800062d2  call    IsSamePath
0x1800062d7  test    eax, eax
0x1800062d9  jnz     short loc_1800062EA
0x1800062db  jmp     short loc_180006262
0x1800062dd  mov     r8, rdi; pszSrc
0x1800062e0  mov     edx, 104h; cchDest
0x1800062e5  call    StringCchCopyW
0x1800062ea  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800062f1  mov     r9, rdi
0x1800062f4  mov     [rsp+98h+Filename], rax
0x1800062f9  lea     r15, [rbx+208h]
0x180006300  lea     r8, SubKey
0x180006307  mov     dword ptr [rsp+98h+DirCount], 104h
0x18000630f  lea     rdx, aTranslator; "Translator"
0x180006316  mov     rcx, r14
0x180006319  lea     rsi, [r15+208h]
0x180006320  call    SQLGetPrivateProfileStringCover
0x180006325  xor     ecx, ecx
0x180006327  test    eax, eax
0x180006329  jle     short loc_180006398
0x18000632b  mov     [rsp+98h+ExtCount], rcx; ExtCount
0x180006330  mov     eax, 104h
0x180006335  mov     [rsp+98h+Ext], rcx; Ext
0x18000633a  mov     r9, rsi; Dir
0x18000633d  mov     [rsp+98h+FilenameCount], rcx; FilenameCount
0x180006342  mov     r8d, eax; DriveCount
0x180006345  mov     [rsp+98h+Filename], rcx; Filename
0x18000634a  mov     rdx, r15; Drive
0x18000634d  mov     rcx, rdi; FullPath
0x180006350  mov     [rsp+98h+DirCount], rax; DirCount
0x180006355  call    cs:__imp__wsplitpath_s
0x18000635b  mov     r8, r15; Drive
0x18000635e  mov     [rsp+98h+Filename], 0; Ext
0x180006367  mov     r15d, 104h
0x18000636d  mov     [rsp+98h+DirCount], 0; Filename
0x180006376  mov     edx, r15d; BufferCount
0x180006379  mov     r9, rsi; Dir
0x18000637c  mov     rcx, rdi; Buffer
0x18000637f  call    cs:__imp__wmakepath_s
0x180006385  mov     r8, rdi; pszSrc
0x180006388  mov     edx, r15d; cchDest
0x18000638b  mov     rcx, rsi; pszDest
0x18000638e  call    StringCchCopyW
0x180006393  xor     r15d, r15d
0x180006396  jmp     short loc_18000639F
0x180006398  xor     r15d, r15d
0x18000639b  mov     [rsi], r15w
0x18000639f  cmp     [rbx], r15w
0x1800063a3  jnz     short loc_1800063E1
0x1800063a5  cmp     [rsi], r15w
0x1800063a9  jz      short loc_1800063CC
0x1800063ab  xor     edx, edx; AccessMode
0x1800063ad  mov     rcx, rsi; FileName
0x1800063b0  call    cs:__imp__waccess
0x1800063b6  test    eax, eax
0x1800063b8  jnz     short loc_1800063CC
0x1800063ba  mov     r8, rsi; pszSrc
0x1800063bd  mov     edx, 104h; cchDest
0x1800063c2  mov     rcx, rbx; pszDest
0x1800063c5  call    StringCchCopyW
0x1800063ca  jmp     short loc_1800063E1
0x1800063cc  mov     edx, 104h
0x1800063d1  lea     r8, [rsp+98h+arg_0]
0x1800063d9  mov     rcx, rbx; Buffer
0x1800063dc  call    GetTargetDirectory
0x1800063e1  cmp     [rsi], r15w
0x1800063e5  jz      short loc_180006406
0x1800063e7  xor     edx, edx; AccessMode
0x1800063e9  mov     rcx, rsi; FileName
0x1800063ec  call    cs:__imp__waccess
0x1800063f2  test    eax, eax
0x1800063f4  jnz     short loc_180006406
0x1800063f6  mov     r8, rsi; pszSrc
0x1800063f9  mov     edx, 104h; cchDest
0x1800063fe  mov     rcx, rbx; pszDest
0x180006401  call    StringCchCopyW
0x180006406  mov     rcx, [rsp+98h+pszDest]; pszDest
0x18000640e  or      r11, 0FFFFFFFFFFFFFFFFh
0x180006412  lea     r9d, [r11+3]
0x180006416  test    rcx, rcx
0x180006419  jz      short loc_18000646B
0x18000641b  movzx   r8d, [rsp+98h+arg_20]
0x180006424  cmp     [rsp+98h+arg_30], r9w
0x18000642d  jnz     short loc_18000645A
0x18000642f  test    r8w, r8w
0x180006433  jz      short loc_18000646B
0x180006435  mov     rdx, r11
0x180006438  inc     rdx
0x18000643b  cmp     [rbx+rdx*2], r15w
0x180006440  jnz     short loc_180006438
0x180006442  inc     rdx
0x180006445  cmp     rdx, r8
0x180006448  jbe     short loc_180006460
0x18000644a  mov     ecx, r9d
0x18000644d  call    PostInstError
0x180006452  mov     ebp, r15d
0x180006455  jmp     loc_180006611
0x18000645a  test    r8w, r8w
0x18000645e  jz      short loc_18000646B
0x180006460  mov     rdx, r8; cchDest
0x180006463  mov     r8, rbx; pszSrc
0x180006466  call    StringCchCopyW
0x18000646b  mov     rax, [rsp+98h+arg_28]
0x180006473  test    rax, rax
0x180006476  jz      short loc_180006486
0x180006478  inc     r11
0x18000647b  cmp     [rbx+r11*2], r15w
0x180006480  jnz     short loc_180006478
0x180006482  mov     [rax], r11w
0x180006486  cmp     [rsp+98h+arg_30], bp
0x18000648e  jnz     short loc_18000649C
0x180006490  lea     rbx, aOdbcinstIni; "ODBCINST.INI"
0x180006497  jmp     loc_1800065C8
0x18000649c  mov     [rsp+98h+var_50], r15
0x1800064a1  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800064a8  mov     [rsp+98h+ExtCount], rax
0x1800064ad  lea     r9, SubKey
0x1800064b4  mov     dword ptr [rsp+98h+Ext], 4
0x1800064bc  lea     rax, [rsp+98h+Data]
0x1800064c1  mov     [rsp+98h+FilenameCount], rax
0x1800064c6  lea     r8, aUsagecount; "UsageCount"
0x1800064cd  mov     [rsp+98h+Filename], r15
0x1800064d2  mov     rdx, r14
0x1800064d5  mov     rcx, 0FFFFFFFF80000002h
0x1800064dc  mov     dword ptr [rsp+98h+DirCount], 10h
0x1800064e4  mov     esi, ebp
0x1800064e6  call    cpGetPrivateProfileString
0x1800064eb  test    eax, eax
0x1800064ed  jnz     short loc_18000652B
0x1800064ef  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800064f6  mov     dword ptr [rsp+98h+Data], r15d
0x1800064fb  mov     [rsp+98h+Filename], rax
0x180006500  lea     r8, SubKey
0x180006507  mov     r9, rdi
0x18000650a  mov     dword ptr [rsp+98h+DirCount], 104h
0x180006512  mov     rdx, r14
0x180006515  lea     rcx, szSection; "ODBC Translators"
0x18000651c  call    SQLGetPrivateProfileStringCover
0x180006521  test    eax, eax
0x180006523  mov     eax, 2
0x180006528  cmovg   esi, eax
0x18000652b  lea     r8, [rdi+208h]; STRSAFE_LPCWSTR
0x180006532  mov     rdx, rbx; pszSrc
0x180006535  mov     rcx, rdi; pszDest
0x180006538  call    MakePath
0x18000653d  lea     r9, aOdbcinstIni; "ODBCINST.INI"
0x180006544  mov     r8, rdi; lpszString
0x180006547  lea     rdx, aTranslator; "Translator"
0x18000654e  mov     rcx, r14; lpszSection
0x180006551  call    SQLWritePrivateProfileStringW
0x180006556  mov     r8, r13; STRSAFE_LPCWSTR
0x180006559  mov     rdx, rbx; pszSrc
0x18000655c  mov     rcx, rdi; pszDest
0x18000655f  call    MakePath
0x180006564  lea     rbx, aOdbcinstIni; "ODBCINST.INI"
0x18000656b  mov     r8, rdi; lpszString
0x18000656e  mov     r9, rbx; lpszFilename
0x180006571  lea     rdx, aSetup; "Setup"
0x180006578  mov     rcx, r14; lpszSection
0x18000657b  call    SQLWritePrivateProfileStringW
0x180006580  mov     r9, rbx; lpszFilename
0x180006583  lea     r8, szString; "Installed"
0x18000658a  mov     rdx, r14; lpszEntry
0x18000658d  lea     rcx, szSection; "ODBC Translators"
0x180006594  call    SQLWritePrivateProfileStringW
0x180006599  add     dword ptr [rsp+98h+Data], esi
0x18000659d  lea     rax, [rsp+98h+Data]
0x1800065a2  mov     [rsp+98h+Filename], rbx; __int64
0x1800065a7  lea     r8, aUsagecount; "UsageCount"
0x1800065ae  mov     r9d, 4
0x1800065b4  mov     [rsp+98h+DirCount], rax; lpData
0x1800065b9  mov     rdx, r14
0x1800065bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800065c3  call    cpWritePrivateProfileString
0x1800065c8  mov     [rsp+98h+var_50], r15
0x1800065cd  lea     r9, SubKey
0x1800065d4  mov     [rsp+98h+ExtCount], rbx
0x1800065d9  lea     r8, aUsagecount; "UsageCount"
0x1800065e0  mov     dword ptr [rsp+98h+Ext], 4
0x1800065e8  mov     rdx, r14
0x1800065eb  mov     [rsp+98h+FilenameCount], r12
0x1800065f0  mov     rcx, 0FFFFFFFF80000002h
0x1800065f7  mov     [rsp+98h+Filename], r15
0x1800065fc  mov     dword ptr [rsp+98h+DirCount], 10h
0x180006604  call    cpGetPrivateProfileString
0x180006609  test    eax, eax
0x18000660b  jnz     short loc_180006611
0x18000660d  mov     [r12], r15d
0x180006611  mov     rcx, rdi
0x180006614  call    OFree
0x180006619  mov     eax, ebp
0x18000661b  mov     rbx, [rsp+98h+arg_8]
0x180006623  add     rsp, 60h
0x180006627  pop     r15
0x180006629  pop     r14
0x18000662b  pop     r13
0x18000662d  pop     r12
0x18000662f  pop     rdi
0x180006630  pop     rsi
0x180006631  pop     rbp
0x180006632  retn
  ... truncated ...
```
