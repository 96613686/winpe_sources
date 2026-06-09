# AddDriverW

- ea: `0x180007628`
- end: `0x180007c05`
- name: `AddDriverW`
- size: `1501`
- prototype: `__int64 __fastcall(wchar_t *String1, wchar_t *, wchar_t *, unsigned __int16, _WORD *, __int16, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x180009050`

## callees

- `0x180001010`
- `0x1800017c0`
- `0x180002940`
- `0x180002e14`
- `0x180004bac`
- `0x180005fd4`
- `0x1800069d8`
- `0x180007628`
- `0x18000829c`
- `0x18000844c`
- `0x18000a320`
- `0x18000a378`
- `0x180013fa8`
- `0x180014ae0`

## import_xrefs

- `msvcrt!wcschr` at `0x180007b59`
- `msvcrt!wcschr` at `0x180007b59`
- `msvcrt!_waccess` at `0x180007835`
- `msvcrt!_waccess` at `0x180007869`
- `msvcrt!_waccess` at `0x180007835`
- `msvcrt!_waccess` at `0x180007869`
- `msvcrt!_wmakepath_s` at `0x180007813`
- `msvcrt!_wmakepath_s` at `0x180007813`
- `msvcrt!_wcsicmp` at `0x180007b82`
- `msvcrt!_wcsicmp` at `0x180007b96`
- `msvcrt!_wcsicmp` at `0x180007baa`
- `msvcrt!_wcsicmp` at `0x180007b82`
- `msvcrt!_wcsicmp` at `0x180007b96`
- `msvcrt!_wcsicmp` at `0x180007baa`
- `msvcrt!_wsplitpath_s` at `0x1800077f2`
- `msvcrt!_wsplitpath_s` at `0x1800077f2`
- `msvcrt!malloc` at `0x18000768f`
- `msvcrt!malloc` at `0x18000768f`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007a90`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007acd`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007ae7`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007b1a`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007a90`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007acd`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007ae7`
- `KERNEL32!WritePrivateProfileStringW` at `0x180007b1a`

## string_xrefs

- `0x180007af0`: `Installed`
- `0x180007b09`: `Installed`

## pseudocode

```c
__int64 __fastcall AddDriverW(
        wchar_t *String1,
        wchar_t *a2,
        wchar_t *a3,
        unsigned __int16 a4,
        _WORD *a5,
        __int16 a6,
        int *a7)
{
  size_t v9; // r13
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  wchar_t *v14; // r12
  unsigned int v15; // r14d
  unsigned int v16; // r9d
  wchar_t *v17; // rdi
  __int64 v18; // rcx
  wchar_t v19; // ax
  __int64 v20; // rdx
  int v21; // r12d
  __int64 v22; // rax
  int v23; // eax
  wchar_t *v24; // r12
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  const wchar_t *i; // rdi
  __int64 v29; // rax
  __int64 v30; // r12
  wchar_t *v31; // rax
  const WCHAR *v32; // rsi
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v34; // [rsp+54h] [rbp-ACh]
  STRSAFE_LPWSTR pszDest; // [rsp+58h] [rbp-A8h]
  _WORD *v36; // [rsp+60h] [rbp-A0h]
  int *v37; // [rsp+68h] [rbp-98h]
  wchar_t Drive[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Dir[264]; // [rsp+290h] [rbp+190h] BYREF

  v36 = a5;
  v37 = a7;
  v9 = a4;
  pszDest = a3;
  v34 = 0;
  *(_DWORD *)Data = 0;
  v11 = (wchar_t *)malloc(0xA28u);
  v12 = v11;
  if ( !v11 )
  {
    PostInstError(21);
    return 0;
  }
  v14 = v11 + 260;
  if ( (unsigned int)GetFilename(String1, (wchar_t *)L"Driver", v11, v11 + 260) )
  {
    if ( a2 )
    {
      if ( *v12 )
      {
        if ( *a2 && !(unsigned int)IsSamePath(v12, a2) )
        {
          PostInstError(12);
          v15 = v16;
          goto LABEL_69;
        }
      }
      else if ( *a2 )
      {
        StringCchCopyW(v12, 0x104u, a2);
      }
    }
    v17 = v14 + 260;
    if ( (unsigned int)GetFilename(String1, (wchar_t *)L"Setup", v14 + 260, v14 + 520) )
    {
      if ( *v17 )
      {
        if ( *v12 )
        {
          if ( !(unsigned int)IsSamePath(v12, v17) )
          {
            v18 = 12;
LABEL_18:
            PostInstError(v18);
            v15 = 0;
            goto LABEL_69;
          }
        }
        else
        {
          StringCchCopyW(v12, 0x104u, v17);
        }
      }
    }
    else
    {
      StringCchCopyW(v14 + 520, 0x104u, v14);
    }
    if ( (int)SQLGetPrivateProfileStringCover(String1, L"Driver", &SubKey, v17, 260, L"ODBCINST.INI") <= 0 )
    {
      *v17 = 0;
      v19 = 0;
    }
    else
    {
      _wsplitpath_s(v17, Drive, 0x104u, Dir, 0x104u, 0, 0, 0, 0);
      _wmakepath_s(v17, 0x104u, Drive, Dir, 0, 0);
      v19 = *v17;
    }
    if ( !*v12 )
    {
      if ( !v19 || _waccess(v17, 0) )
        GetTargetDirectory(v12);
      else
        StringCchCopyW(v12, 0x104u, v17);
    }
    if ( *v17 && !_waccess(v17, 0) )
      StringCchCopyW(v12, 0x104u, v17);
    v18 = 2;
    if ( a6 != 2 )
      goto LABEL_37;
    if ( !a3 )
      goto LABEL_37;
    if ( !(_WORD)v9 )
      goto LABEL_37;
    v20 = -1;
    do
      ++v20;
    while ( v12[v20] );
    if ( v20 + 1 <= v9 )
    {
LABEL_37:
      v15 = 1;
      v21 = 1;
      if ( pszDest && (_WORD)v9 )
        StringCchCopyW(pszDest, v9, v12);
      if ( v36 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v12[v22] );
        *v36 = 2 * v22;
      }
      if ( !(unsigned int)cpGetPrivateProfileString(
                            -2147483646,
                            String1,
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
        if ( (int)cpGetPrivateProfileString(
                    -2147483646,
                    L"ODBC Drivers",
                    String1,
                    &SubKey,
                    0xFFFF,
                    0,
                    Drive,
                    260,
                    L"ODBCINST.INI",
                    0) > 0 )
          v21 = 2;
      }
      v23 = *(_DWORD *)Data;
      if ( a6 == 2 )
      {
        v23 = v21 + *(_DWORD *)Data;
        *(_DWORD *)Data += v21;
      }
      if ( v37 )
        *v37 = v23;
      if ( a6 != 1 )
      {
        v24 = v17 + 520;
        cpWritePrivateProfileString(HKEY_LOCAL_MACHINE, Data, (__int64)L"ODBCINST.INI");
        MakePath(v17, v12, v12 + 260);
        SQLWritePrivateProfileStringW(String1, L"Driver", v17, L"ODBCINST.INI");
        StringCchCopyW(v17 + 520, 0x104u, String1);
        v25 = -1;
        v26 = -1;
        do
          ++v26;
        while ( String1[v26] );
        do
          ++v25;
        while ( v24[v25] );
        SetString(&v24[v25], 260 - v26);
        WritePrivateProfileStringW(v17 + 520, L"Driver", v17, L"ODBCINST.INI");
        MakePath(v17, v12, v17 + 260);
        SQLWritePrivateProfileStringW(String1, L"Setup", v17, L"ODBCINST.INI");
        WritePrivateProfileStringW(v17 + 520, L"Setup", v17, L"ODBCINST.INI");
        WritePrivateProfileStringW(v17 + 520, L"32Bit", L"1", L"ODBCINST.INI");
        SQLWritePrivateProfileStringW(L"ODBC Drivers", String1, L"Installed", L"ODBCINST.INI");
        WritePrivateProfileStringW(L"ODBC 32 bit Drivers", v17 + 520, L"Installed", L"ODBCINST.INI");
        v27 = -1;
        do
          ++v27;
        while ( String1[v27] );
        for ( i = &String1[v27 + 1]; *i; i += v30 )
        {
          v29 = -1;
          do
            ++v29;
          while ( i[v29] );
          v30 = (unsigned __int16)(v29 + 1);
          v31 = wcschr(i, 0x3Du);
          if ( v31 )
          {
            *v31 = 0;
            v32 = v31 + 1;
          }
          else
          {
            v32 = &SubKey;
          }
          if ( _wcsicmp(i, L"Setup") && _wcsicmp(i, L"Driver") )
          {
            if ( _wcsicmp(i, L"UsageCount") )
              SQLWritePrivateProfileStringW(String1, i, v32, L"ODBCINST.INI");
          }
        }
      }
      goto LABEL_69;
    }
    goto LABEL_18;
  }
  v15 = 0;
LABEL_69:
  OFree(v12);
  return v15;
}

```

## disassembly

```asm
0x180007628  push    rbp
0x18000762a  push    rbx
0x18000762b  push    rsi
0x18000762c  push    rdi
0x18000762d  push    r12
0x18000762f  push    r13
0x180007631  push    r14
0x180007633  push    r15
0x180007635  lea     rbp, [rsp-3B8h]
0x18000763d  sub     rsp, 4B8h
0x180007644  mov     rax, cs:__security_cookie
0x18000764b  xor     rax, rsp
0x18000764e  mov     [rbp+3F0h+var_50], rax
0x180007655  mov     rax, [rbp+3F0h+arg_20]
0x18000765c  mov     r15, rcx
0x18000765f  mov     [rsp+4F0h+var_490], rax
0x180007664  xor     esi, esi
0x180007666  mov     rax, [rbp+3F0h+arg_30]
0x18000766d  mov     ecx, 0A28h; Size
0x180007672  mov     [rsp+4F0h+var_488], rax
0x180007677  mov     r14, r8
0x18000767a  movzx   r13d, r9w
0x18000767e  mov     rdi, rdx
0x180007681  mov     [rsp+4F0h+pszDest], r8
0x180007686  mov     [rsp+4F0h+var_49C], si
0x18000768b  mov     dword ptr [rsp+4F0h+Data], esi
0x18000768f  call    cs:__imp_malloc
0x180007695  mov     rbx, rax
0x180007698  test    rax, rax
0x18000769b  jnz     short loc_1800076AC
0x18000769d  lea     ecx, [rsi+15h]
0x1800076a0  call    PostInstError
0x1800076a5  xor     eax, eax
0x1800076a7  jmp     loc_180007BE2
0x1800076ac  lea     r12, [rax+208h]
0x1800076b3  mov     r8, rbx; pszDest
0x1800076b6  lea     rdx, aDriver_0; "Driver"
0x1800076bd  mov     [rsp+4F0h+DirCount], r12; STRSAFE_LPWSTR
0x1800076c2  mov     rcx, r15; String1
0x1800076c5  call    GetFilename
0x1800076ca  test    eax, eax
0x1800076cc  jnz     short loc_1800076D6
0x1800076ce  mov     r14d, esi
0x1800076d1  jmp     loc_180007BD7
0x1800076d6  xor     eax, eax
0x1800076d8  mov     esi, 104h
0x1800076dd  test    rdi, rdi
0x1800076e0  jz      short loc_180007721
0x1800076e2  cmp     [rbx], ax
0x1800076e5  jz      short loc_18000770E
0x1800076e7  cmp     [rdi], ax
0x1800076ea  jz      short loc_180007721
0x1800076ec  mov     rdx, rdi; wchar_t *
0x1800076ef  mov     rcx, rbx; Path
0x1800076f2  call    IsSamePath
0x1800076f7  xor     r9d, r9d
0x1800076fa  test    eax, eax
0x1800076fc  jnz     short loc_180007721
0x1800076fe  lea     ecx, [rax+0Ch]
0x180007701  call    PostInstError
0x180007706  mov     r14d, r9d
0x180007709  jmp     loc_180007BD7
0x18000770e  cmp     [rdi], ax
0x180007711  jz      short loc_180007721
0x180007713  mov     r8, rdi; pszSrc
0x180007716  mov     rdx, rsi; cchDest
0x180007719  mov     rcx, rbx; pszDest
0x18000771c  call    StringCchCopyW
0x180007721  lea     rdi, [r12+208h]
0x180007729  mov     rcx, r15; String1
0x18000772c  lea     rax, [rdi+208h]
0x180007733  mov     r8, rdi; pszDest
0x180007736  lea     rdx, aSetup; "Setup"
0x18000773d  mov     [rsp+4F0h+DirCount], rax; STRSAFE_LPWSTR
0x180007742  call    GetFilename
0x180007747  test    eax, eax
0x180007749  jnz     short loc_180007762
0x18000774b  mov     r8, r12; pszSrc
0x18000774e  lea     rcx, [rdi+208h]; pszDest
0x180007755  mov     rdx, rsi; cchDest
0x180007758  call    StringCchCopyW
0x18000775d  xor     r12d, r12d
0x180007760  jmp     short loc_18000779B
0x180007762  xor     r12d, r12d
0x180007765  cmp     [rdi], r12w
0x180007769  jz      short loc_18000779B
0x18000776b  mov     rcx, rbx; Path
0x18000776e  cmp     [rbx], r12w
0x180007772  jz      short loc_180007790
0x180007774  mov     rdx, rdi; wchar_t *
0x180007777  call    IsSamePath
0x18000777c  test    eax, eax
0x18000777e  jnz     short loc_18000779B
0x180007780  lea     ecx, [rax+0Ch]
0x180007783  call    PostInstError
0x180007788  mov     r14d, r12d
0x18000778b  jmp     loc_180007BD7
0x180007790  mov     r8, rdi; pszSrc
0x180007793  mov     rdx, rsi; cchDest
0x180007796  call    StringCchCopyW
0x18000779b  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800077a2  mov     r9, rdi
0x1800077a5  mov     [rsp+4F0h+Filename], rax
0x1800077aa  lea     r8, SubKey
0x1800077b1  lea     rdx, aDriver_0; "Driver"
0x1800077b8  mov     dword ptr [rsp+4F0h+DirCount], esi
0x1800077bc  mov     rcx, r15
0x1800077bf  call    SQLGetPrivateProfileStringCover
0x1800077c4  test    eax, eax
0x1800077c6  jle     short loc_18000781E
0x1800077c8  mov     [rsp+4F0h+ExtCount], r12; ExtCount
0x1800077cd  lea     r9, [rbp+3F0h+Dir]; Dir
0x1800077d4  mov     [rsp+4F0h+Ext], r12; Ext
0x1800077d9  lea     rdx, [rbp+3F0h+Drive]; Drive
0x1800077dd  mov     [rsp+4F0h+FilenameCount], r12; FilenameCount
0x1800077e2  mov     r8, rsi; DriveCount
0x1800077e5  mov     [rsp+4F0h+Filename], r12; Filename
0x1800077ea  mov     rcx, rdi; FullPath
0x1800077ed  mov     [rsp+4F0h+DirCount], rsi; DirCount
0x1800077f2  call    cs:__imp__wsplitpath_s
0x1800077f8  lea     r9, [rbp+3F0h+Dir]; Dir
0x1800077ff  mov     [rsp+4F0h+Filename], r12; Ext
0x180007804  lea     r8, [rbp+3F0h+Drive]; Drive
0x180007808  mov     [rsp+4F0h+DirCount], r12; Filename
0x18000780d  mov     rdx, rsi; BufferCount
0x180007810  mov     rcx, rdi; Buffer
0x180007813  call    cs:__imp__wmakepath_s
0x180007819  movzx   eax, word ptr [rdi]
0x18000781c  jmp     short loc_180007825
0x18000781e  mov     [rdi], r12w
0x180007822  mov     eax, r12d
0x180007825  cmp     [rbx], r12w
0x180007829  jnz     short loc_18000785E
0x18000782b  test    ax, ax
0x18000782e  jz      short loc_18000784F
0x180007830  xor     edx, edx; AccessMode
0x180007832  mov     rcx, rdi; FileName
0x180007835  call    cs:__imp__waccess
0x18000783b  test    eax, eax
0x18000783d  jnz     short loc_18000784F
0x18000783f  mov     r8, rdi; pszSrc
0x180007842  mov     rdx, rsi; cchDest
0x180007845  mov     rcx, rbx; pszDest
0x180007848  call    StringCchCopyW
0x18000784d  jmp     short loc_18000785E
0x18000784f  mov     edx, esi
0x180007851  lea     r8, [rsp+4F0h+var_49C]
0x180007856  mov     rcx, rbx; Buffer
0x180007859  call    GetTargetDirectory
0x18000785e  cmp     [rdi], r12w
0x180007862  jz      short loc_180007881
0x180007864  xor     edx, edx; AccessMode
0x180007866  mov     rcx, rdi; FileName
0x180007869  call    cs:__imp__waccess
0x18000786f  test    eax, eax
0x180007871  jnz     short loc_180007881
0x180007873  mov     r8, rdi; pszSrc
0x180007876  mov     rdx, rsi; cchDest
0x180007879  mov     rcx, rbx; pszDest
0x18000787c  call    StringCchCopyW
0x180007881  mov     ecx, 2
0x180007886  cmp     [rbp+3F0h+arg_28], cx
0x18000788d  jnz     short loc_1800078B4
0x18000788f  test    r14, r14
0x180007892  jz      short loc_1800078B4
0x180007894  test    r13w, r13w
0x180007898  jz      short loc_1800078B4
0x18000789a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000789e  inc     rdx
0x1800078a1  cmp     [rbx+rdx*2], r12w
0x1800078a6  jnz     short loc_18000789E
0x1800078a8  inc     rdx
0x1800078ab  cmp     rdx, r13
0x1800078ae  ja      loc_180007783
0x1800078b4  mov     rcx, [rsp+4F0h+pszDest]; pszDest
0x1800078b9  mov     r14d, 1
0x1800078bf  mov     r12d, r14d
0x1800078c2  test    rcx, rcx
0x1800078c5  jz      short loc_1800078D8
0x1800078c7  test    r13w, r13w
0x1800078cb  jz      short loc_1800078D8
0x1800078cd  mov     rdx, r13; cchDest
0x1800078d0  mov     r8, rbx; pszSrc
0x1800078d3  call    StringCchCopyW
0x1800078d8  mov     rcx, [rsp+4F0h+var_490]
0x1800078dd  xor     r13d, r13d
0x1800078e0  test    rcx, rcx
0x1800078e3  jz      short loc_1800078F9
0x1800078e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800078e9  inc     rax
0x1800078ec  cmp     [rbx+rax*2], r13w
0x1800078f1  jnz     short loc_1800078E9
0x1800078f3  add     ax, ax
0x1800078f6  mov     [rcx], ax
0x1800078f9  mov     [rsp+4F0h+var_4A8], r13
0x1800078fe  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180007905  mov     [rsp+4F0h+ExtCount], rax
0x18000790a  lea     r9, SubKey
0x180007911  mov     dword ptr [rsp+4F0h+Ext], 4
0x180007919  lea     rax, [rsp+4F0h+Data]
0x18000791e  mov     [rsp+4F0h+FilenameCount], rax
0x180007923  lea     r8, aUsagecount; "UsageCount"
0x18000792a  mov     [rsp+4F0h+Filename], r13
0x18000792f  mov     rdx, r15
0x180007932  mov     rcx, 0FFFFFFFF80000002h
0x180007939  mov     dword ptr [rsp+4F0h+DirCount], 10h
0x180007941  call    cpGetPrivateProfileString
0x180007946  test    eax, eax
0x180007948  jnz     short loc_1800079A4
0x18000794a  mov     [rsp+4F0h+var_4A8], r13
0x18000794f  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180007956  mov     [rsp+4F0h+ExtCount], rax
0x18000795b  lea     r9, SubKey
0x180007962  mov     dword ptr [rsp+4F0h+Ext], esi
0x180007966  lea     rax, [rbp+3F0h+Drive]
0x18000796a  mov     [rsp+4F0h+FilenameCount], rax
0x18000796f  lea     rdx, aOdbcDrivers; "ODBC Drivers"
0x180007976  mov     [rsp+4F0h+Filename], r13
0x18000797b  mov     r8, r15
0x18000797e  mov     rcx, 0FFFFFFFF80000002h
0x180007985  mov     dword ptr [rsp+4F0h+DirCount], 0FFFFh
0x18000798d  mov     dword ptr [rsp+4F0h+Data], r13d
0x180007992  call    cpGetPrivateProfileString
0x180007997  test    eax, eax
0x180007999  mov     eax, 2
0x18000799e  cmovg   r12d, eax
0x1800079a2  jmp     short loc_1800079A9
0x1800079a4  mov     eax, 2
0x1800079a9  cmp     [rbp+3F0h+arg_28], ax
0x1800079b0  mov     eax, dword ptr [rsp+4F0h+Data]
0x1800079b4  jnz     short loc_1800079BD
0x1800079b6  add     eax, r12d
0x1800079b9  mov     dword ptr [rsp+4F0h+Data], eax
0x1800079bd  mov     rdx, [rsp+4F0h+var_488]
0x1800079c2  test    rdx, rdx
0x1800079c5  jz      short loc_1800079C9
0x1800079c7  mov     [rdx], eax
0x1800079c9  cmp     [rbp+3F0h+arg_28], r14w
0x1800079d1  jz      loc_180007BD7
0x1800079d7  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800079de  mov     r9d, 4
0x1800079e4  mov     [rsp+4F0h+Filename], rax; __int64
0x1800079e9  lea     r8, aUsagecount; "UsageCount"
0x1800079f0  lea     rax, [rsp+4F0h+Data]
0x1800079f5  mov     rdx, r15
0x1800079f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800079ff  mov     [rsp+4F0h+DirCount], rax; lpData
0x180007a04  lea     r12, [rdi+410h]
0x180007a0b  call    cpWritePrivateProfileString
0x180007a10  lea     r8, [rbx+208h]; STRSAFE_LPCWSTR
0x180007a17  mov     rdx, rbx; pszSrc
0x180007a1a  mov     rcx, rdi; pszDest
0x180007a1d  call    MakePath
0x180007a22  lea     r9, aOdbcinstIni; "ODBCINST.INI"
0x180007a29  mov     r8, rdi; lpszString
0x180007a2c  lea     rdx, aDriver_0; "Driver"
0x180007a33  mov     rcx, r15; lpszSection
0x180007a36  call    SQLWritePrivateProfileStringW
0x180007a3b  mov     r8, r15; pszSrc
0x180007a3e  mov     rdx, rsi; cchDest
0x180007a41  mov     rcx, r12; pszDest
0x180007a44  call    StringCchCopyW
0x180007a49  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007a4d  mov     rcx, rax
0x180007a50  xor     edx, edx
0x180007a52  inc     rcx
0x180007a55  cmp     [r15+rcx*2], dx
0x180007a5a  jnz     short loc_180007A52
0x180007a5c  inc     rax
0x180007a5f  cmp     [r12+rax*2], dx
0x180007a64  jnz     short loc_180007A5C
0x180007a66  sub     esi, ecx
0x180007a68  mov     r8d, 54Ch
0x180007a6e  mov     edx, esi; cchBufferMax
0x180007a70  lea     rcx, [r12+rax*2]; lpBuffer
0x180007a74  call    SetString
0x180007a79  lea     rsi, aOdbcinstIni; "ODBCINST.INI"
0x180007a80  mov     r8, rdi; lpString
0x180007a83  mov     r9, rsi; lpFileName
0x180007a86  lea     rdx, aDriver_0; "Driver"
0x180007a8d  mov     rcx, r12; lpAppName
0x180007a90  call    cs:__imp_WritePrivateProfileStringW
0x180007a96  lea     r8, [rdi+208h]; STRSAFE_LPCWSTR
0x180007a9d  mov     rdx, rbx; pszSrc
0x180007aa0  mov     rcx, rdi; pszDest
0x180007aa3  call    MakePath
0x180007aa8  mov     r9, rsi; lpszFilename
0x180007aab  lea     rdx, aSetup; "Setup"
0x180007ab2  mov     r8, rdi; lpszString
0x180007ab5  mov     rcx, r15; lpszSection
0x180007ab8  call    SQLWritePrivateProfileStringW
0x180007abd  mov     r9, rsi; lpFileName
0x180007ac0  lea     rdx, aSetup; "Setup"
0x180007ac7  mov     r8, rdi; lpString
0x180007aca  mov     rcx, r12; lpAppName
0x180007acd  call    cs:__imp_WritePrivateProfileStringW
0x180007ad3  mov     r9, rsi; lpFileName
0x180007ad6  lea     r8, Data; "1"
0x180007add  lea     rdx, a32bit; "32Bit"
0x180007ae4  mov     rcx, r12; lpAppName
  ... truncated ...
```
