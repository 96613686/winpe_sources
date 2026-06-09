# cpGetPrivateProfileString

- ea: `0x180001010`
- end: `0x1800016aa`
- name: `cpGetPrivateProfileString`
- size: `1690`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, void *, DWORD dwFlags, DWORD *, WCHAR *, int, __int64, DWORD *)`
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800017c0`
- `0x180006184`
- `0x180006afc`
- `0x180006db8`
- `0x180007200`
- `0x180007628`
- `0x180007c0c`
- `0x1800085c8`
- `0x180009a88`
- `0x180009c30`
- `0x18000a1b4`
- `0x18000d208`
- `0x18000dc70`
- `0x180012c98`

## callees

- `0x180001010`
- `0x180001c00`
- `0x180002e4c`
- `0x180013f00`
- `0x180014aa2`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001144`
- `msvcrt!_wcsicmp` at `0x18000118a`
- `msvcrt!_wcsicmp` at `0x18000119e`
- `msvcrt!_wcsicmp` at `0x180001144`
- `msvcrt!_wcsicmp` at `0x18000118a`
- `msvcrt!_wcsicmp` at `0x18000119e`
- `msvcrt!calloc` at `0x1800014c0`
- `msvcrt!calloc` at `0x1800014c0`
- `msvcrt!free` at `0x1800015e1`
- `msvcrt!free` at `0x1800015e1`
- `msvcrt!_snwprintf_s` at `0x18000110e`
- `msvcrt!_snwprintf_s` at `0x1800011d1`
- `msvcrt!_snwprintf_s` at `0x1800011f0`
- `msvcrt!_snwprintf_s` at `0x18000110e`
- `msvcrt!_snwprintf_s` at `0x1800011d1`
- `msvcrt!_snwprintf_s` at `0x1800011f0`
- `KERNEL32!GetPrivateProfileStringW` at `0x180001130`
- `KERNEL32!GetPrivateProfileStringW` at `0x180001172`
- `KERNEL32!GetPrivateProfileStringW` at `0x180001130`
- `KERNEL32!GetPrivateProfileStringW` at `0x180001172`
- `ADVAPI32!RegCloseKey` at `0x180001631`
- `ADVAPI32!RegCloseKey` at `0x180001631`
- `ADVAPI32!RegGetValueW` at `0x1800014a2`
- `ADVAPI32!RegGetValueW` at `0x1800014f9`
- `ADVAPI32!RegGetValueW` at `0x1800014a2`
- `ADVAPI32!RegGetValueW` at `0x1800014f9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800012c3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800012c3`
- `ADVAPI32!RegEnumValueW` at `0x18000134a`
- `ADVAPI32!RegEnumValueW` at `0x1800013ab`
- `ADVAPI32!RegEnumValueW` at `0x18000134a`
- `ADVAPI32!RegEnumValueW` at `0x1800013ab`

## pseudocode

```c
__int64 __fastcall cpGetPrivateProfileString(
        HKEY a1,
        const WCHAR *a2,
        const WCHAR *a3,
        void *a4,
        DWORD dwFlags,
        DWORD *a6,
        WCHAR *a7,
        int a8,
        __int64 a9,
        DWORD *a10)
{
  DWORD *p_pdwType; // rcx
  LPWSTR v14; // r9
  DWORD nSize; // r15d
  __int64 v16; // r12
  int v17; // eax
  wchar_t *v18; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  LSTATUS v22; // ebx
  DWORD v23; // ebx
  DWORD v24; // ecx
  WCHAR *v25; // rsi
  DWORD v26; // edi
  DWORD *v27; // r12
  LSTATUS v28; // eax
  DWORD v29; // edx
  DWORD v30; // ecx
  LPWSTR v31; // rdi
  const WCHAR *v32; // rbx
  LSTATUS ValueW; // eax
  void *v34; // rsi
  DWORD v35; // eax
  DWORD v36; // ebx
  bool v37; // cc
  unsigned int v38; // r15d
  bool v39; // zf
  __int64 v40; // rdi
  LPWSTR v41; // r15
  unsigned __int64 v42; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR lpReturnedString; // [rsp+50h] [rbp-B0h]
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD *v48; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h]
  LPCWSTR lpValue; // [rsp+70h] [rbp-90h]
  void *Src; // [rsp+78h] [rbp-88h]
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[272]; // [rsp+290h] [rbp+190h] BYREF

  hKey = a1;
  p_pdwType = &pdwType;
  Src = a4;
  v14 = a7;
  if ( a10 )
    p_pdwType = a10;
  lpValue = a3;
  lpReturnedString = a7;
  phkResult = 0;
  *p_pdwType = 0;
  pcbData = 0;
  cchValueName = 0;
  v48 = p_pdwType;
  if ( a8 <= 1 || !a3 && a8 <= 2 )
    return 0;
  nSize = a8 & 0xFFFFFFFE;
  v16 = -1;
  if ( !a2 || !a3 )
    goto LABEL_22;
  if ( !(unsigned int)PrivateDriverRootInitialized(0, 0, a3, a7) )
  {
LABEL_21:
    v14 = lpReturnedString;
    goto LABEL_22;
  }
  _snwprintf_s(Buffer, 0x104u, 0xFFFFFFFFFFFFFFFFuLL, L"%ls\\%ls.ini", &szODBCPrivateDriverRoot, a2);
  if ( GetPrivateProfileStringW(a2, a3, 0, lpReturnedString, nSize, Buffer) )
    goto LABEL_12;
  v17 = _wcsicmp(a3, L"Setup");
  v14 = lpReturnedString;
  if ( v17 )
  {
LABEL_22:
    v20 = -1;
    do
      ++v20;
    while ( a2[v20] );
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(a9 + 2 * v21) );
    if ( (unsigned int)(v20 + v21 + 16) <= 0x10E )
    {
      StringCchPrintfW(pszDest, 0x10Eu, L"%s%s\\%s", L"SOFTWARE\\ODBC\\", a9, a2);
      v22 = RegOpenKeyExW(hKey, pszDest, 0, 0x20019u, &phkResult);
      if ( v22 )
        return (unsigned int)cpSetDefault(a4, lpReturnedString);
      v24 = a8 & 0xFFFFFFFE;
      pcbData = a8 & 0xFFFFFFFE;
      if ( a3 )
      {
        v31 = lpReturnedString;
        v32 = lpValue;
        pdwType = 0;
        ValueW = RegGetValueW(phkResult, &SubKey, lpValue, dwFlags, &pdwType, lpReturnedString, &pcbData);
        if ( ValueW != 234 )
        {
          if ( ValueW )
          {
            pcbData = cpSetDefault(a4, v31);
            goto LABEL_79;
          }
          if ( pdwType == 1 )
            pcbData -= 2;
          v27 = v48;
          if ( a6 )
            *a6 = pdwType;
          goto LABEL_78;
        }
        v34 = calloc(pcbData + 2LL, 1u);
        if ( !v34 || RegGetValueW(phkResult, &SubKey, v32, dwFlags, &pdwType, v34, &pcbData) )
        {
          if ( Src )
          {
            do
              ++v16;
            while ( *((_WORD *)Src + v16) );
          }
          else
          {
            LODWORD(v16) = 0;
          }
          v36 = pdwType;
          if ( pdwType == 1 || dwFlags == 2 )
          {
            v37 = 2 * (int)v16 + 2 < (int)nSize;
            v38 = 2 * v16 + 2;
            if ( !v37 )
              v38 = a8 & 0xFFFFFFFE;
            nSize = v38 - 2;
          }
          else if ( 2 * (int)v16 + 2 < (int)nSize )
          {
            nSize = 2 * v16 + 2;
          }
          pcbData = nSize;
          v39 = nSize == 0;
          v40 = nSize;
          v41 = lpReturnedString;
          if ( !v39 )
            memcpy_0(lpReturnedString, Src, (unsigned int)v40);
          if ( v36 == 1 || dwFlags == 2 )
          {
            *(LPWSTR)((char *)v41 + v40) = 0;
            v36 = pdwType;
          }
          if ( a6 )
            *a6 = v36;
          if ( !v34 )
          {
LABEL_79:
            v23 = pcbData;
            RegCloseKey(phkResult);
            return v23;
          }
        }
        else
        {
          memcpy_0(v31, v34, nSize);
          v35 = pdwType;
          if ( pdwType == 1 )
          {
            pcbData = nSize - 2;
            *(LPWSTR)((char *)v31 + nSize - 2) = 0;
            v35 = pdwType;
          }
          else
          {
            pcbData = a8 & 0xFFFFFFFE;
          }
          if ( a6 )
            *a6 = v35;
        }
        free(v34);
        goto LABEL_79;
      }
      v25 = lpReturnedString;
      v26 = 0;
      v27 = v48;
      while ( 1 )
      {
        if ( v24 <= 4 )
        {
LABEL_40:
          *(LPWSTR)((char *)lpReturnedString + ((nSize - v24) & 0xFFFFFFFE)) = 0;
          pcbData = nSize - pcbData;
          if ( a6 )
            *a6 = 1;
          if ( v22 )
            goto LABEL_79;
LABEL_78:
          *v27 = 1;
          goto LABEL_79;
        }
        cchValueName = (v24 - 2) >> 1;
        v28 = RegEnumValueW(phkResult, v26, v25, &cchValueName, 0, 0, 0, 0);
        v22 = v28;
        if ( !cchValueName && !v28 )
          goto LABEL_39;
        v29 = 2 * cchValueName;
        cchValueName *= 2;
        if ( v28 == 234 )
        {
          cchValueName = 256;
          v22 = RegEnumValueW(phkResult, v26, Buffer, &cchValueName, 0, 0, 0, 0);
          if ( !v22 )
          {
            cchValueName = pcbData - 4;
            memcpy_0(v25, Buffer, pcbData - 4);
            *(WCHAR *)((char *)v25 + (cchValueName & 0xFFFFFFFE)) = 0;
            v29 = cchValueName;
            goto LABEL_38;
          }
LABEL_39:
          v24 = pcbData;
          ++v26;
          if ( v22 )
            goto LABEL_40;
        }
        else
        {
          if ( v28 )
            goto LABEL_39;
LABEL_38:
          v30 = pcbData;
          *v27 = 1;
          v24 = -2 - v29 + v30;
          pcbData = v24;
          ++v26;
          v25 += ((unsigned __int64)v29 + 2) >> 1;
        }
      }
    }
    if ( !a4 )
      goto LABEL_87;
    do
      ++v16;
    while ( *((_WORD *)a4 + v16) );
    if ( (_DWORD)v16 && nSize > 2 )
    {
      v42 = 2LL * (unsigned int)v16;
      if ( v42 >= (unsigned __int64)nSize - 2 )
        LODWORD(v42) = nSize - 2;
      v23 = v42;
      memcpy_0(v14, a4, (unsigned int)v42);
      v14 = lpReturnedString;
    }
    else
    {
LABEL_87:
      v23 = 0;
      if ( nSize <= 2 )
        goto LABEL_89;
    }
    *(LPWSTR)((char *)v14 + v23) = 0;
LABEL_89:
    if ( a6 )
      *a6 = 1;
    return v23;
  }
  if ( !GetPrivateProfileStringW(a2, L"Driver", 0, lpReturnedString, nSize, Buffer) )
    goto LABEL_21;
LABEL_12:
  if ( _wcsicmp(a3, L"Driver") && _wcsicmp(a3, L"Setup") )
  {
    v18 = lpReturnedString;
  }
  else
  {
    v18 = lpReturnedString;
    _snwprintf_s(Buffer, 0x104u, 0xFFFFFFFFFFFFFFFFuLL, L"%ls\\%ls", &szODBCPrivateDriverRoot, lpReturnedString);
    _snwprintf_s(v18, nSize, 0xFFFFFFFFFFFFFFFFuLL, L"%ls", Buffer);
  }
  if ( a6 )
    *a6 = 1;
  do
    ++v16;
  while ( v18[v16] );
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180001010  push    rbp
0x180001012  push    rbx
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r13
0x180001017  push    r14
0x180001019  push    r15
0x18000101b  lea     rbp, [rsp-3D0h]
0x180001023  sub     rsp, 4D0h
0x18000102a  mov     rax, cs:__security_cookie
0x180001031  xor     rax, rsp
0x180001034  mov     [rbp+400h+var_50], rax
0x18000103b  mov     rax, [rbp+400h+arg_48]
0x180001042  mov     rbx, rdx
0x180001045  mov     r15d, [rbp+400h+arg_38]
0x18000104c  xor     edx, edx
0x18000104e  mov     r13, [rbp+400h+arg_28]
0x180001055  test    rax, rax
0x180001058  mov     rdi, [rbp+400h+arg_40]
0x18000105f  mov     rsi, r9
0x180001062  mov     [rsp+500h+hKey], rcx
0x180001067  mov     r14, r8
0x18000106a  lea     rcx, [rsp+500h+pdwType]
0x18000106f  mov     [rsp+500h+Src], r9
0x180001074  mov     r9, [rbp+400h+arg_30]
0x18000107b  cmovnz  rcx, rax
0x18000107f  mov     [rsp+500h+lpValue], r8
0x180001084  mov     [rsp+500h+lpReturnedString], r9
0x180001089  mov     [rsp+500h+phkResult], rdx
0x18000108e  mov     [rcx], edx
0x180001090  mov     [rsp+500h+pcbData], edx
0x180001094  mov     [rsp+500h+cchValueName], edx
0x180001098  mov     [rsp+500h+var_4A0], rcx
0x18000109d  cmp     r15d, 1
0x1800010a1  jle     loc_1800016A3
0x1800010a7  test    r8, r8
0x1800010aa  jnz     short loc_1800010B6
0x1800010ac  cmp     r15d, 2
0x1800010b0  jle     loc_1800016A3
0x1800010b6  and     r15d, 0FFFFFFFEh
0x1800010ba  mov     [rsp+500h+var_38], r12
0x1800010c2  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800010c9  test    rbx, rbx
0x1800010cc  jz      loc_180001248
0x1800010d2  test    r14, r14
0x1800010d5  jz      loc_180001248
0x1800010db  xor     ecx, ecx
0x1800010dd  call    PrivateDriverRootInitialized
0x1800010e2  test    eax, eax
0x1800010e4  jz      loc_180001241
0x1800010ea  lea     rax, szODBCPrivateDriverRoot
0x1800010f1  mov     [rsp+500h+lpFileName], rbx
0x1800010f6  lea     r9, aLsLsIni; "%ls\\%ls.ini"
0x1800010fd  mov     qword ptr [rsp+500h+nSize], rax
0x180001102  mov     r8, r12; MaxCount
0x180001105  lea     rcx, [rbp+400h+Buffer]; Buffer
0x180001109  mov     edx, 104h; BufferCount
0x18000110e  call    cs:__imp__snwprintf_s
0x180001114  mov     r9, [rsp+500h+lpReturnedString]; lpReturnedString
0x180001119  lea     rax, [rbp+400h+Buffer]
0x18000111d  mov     [rsp+500h+lpFileName], rax; lpFileName
0x180001122  xor     r8d, r8d; lpDefault
0x180001125  mov     rdx, r14; lpKeyName
0x180001128  mov     [rsp+500h+nSize], r15d; nSize
0x18000112d  mov     rcx, rbx; lpAppName
0x180001130  call    cs:__imp_GetPrivateProfileStringW
0x180001136  test    eax, eax
0x180001138  jnz     short loc_180001180
0x18000113a  lea     rdx, aSetup; "Setup"
0x180001141  mov     rcx, r14; String1
0x180001144  call    cs:__imp__wcsicmp
0x18000114a  mov     r9, [rsp+500h+lpReturnedString]; lpReturnedString
0x18000114f  test    eax, eax
0x180001151  jnz     loc_180001246
0x180001157  lea     rax, [rbp+400h+Buffer]
0x18000115b  xor     r8d, r8d; lpDefault
0x18000115e  mov     [rsp+500h+lpFileName], rax; lpFileName
0x180001163  lea     rdx, aDriver_0; "Driver"
0x18000116a  mov     rcx, rbx; lpAppName
0x18000116d  mov     [rsp+500h+nSize], r15d; nSize
0x180001172  call    cs:__imp_GetPrivateProfileStringW
0x180001178  test    eax, eax
0x18000117a  jz      loc_180001241
0x180001180  lea     rdx, aDriver_0; "Driver"
0x180001187  mov     rcx, r14; String1
0x18000118a  call    cs:__imp__wcsicmp
0x180001190  test    eax, eax
0x180001192  jz      short loc_1800011A8
0x180001194  lea     rdx, aSetup; "Setup"
0x18000119b  mov     rcx, r14; String1
0x18000119e  call    cs:__imp__wcsicmp
0x1800011a4  test    eax, eax
0x1800011a6  jnz     short loc_1800011F8
0x1800011a8  mov     rbx, [rsp+500h+lpReturnedString]
0x1800011ad  lea     rax, szODBCPrivateDriverRoot
0x1800011b4  mov     [rsp+500h+lpFileName], rbx
0x1800011b9  lea     r9, aLsLs; "%ls\\%ls"
0x1800011c0  mov     r8, r12; MaxCount
0x1800011c3  mov     qword ptr [rsp+500h+nSize], rax
0x1800011c8  mov     edx, 104h; BufferCount
0x1800011cd  lea     rcx, [rbp+400h+Buffer]; Buffer
0x1800011d1  call    cs:__imp__snwprintf_s
0x1800011d7  lea     rax, [rbp+400h+Buffer]
0x1800011db  mov     edx, r15d; BufferCount
0x1800011de  lea     r9, aLs; "%ls"
0x1800011e5  mov     qword ptr [rsp+500h+nSize], rax
0x1800011ea  mov     r8, r12; MaxCount
0x1800011ed  mov     rcx, rbx; Buffer
0x1800011f0  call    cs:__imp__snwprintf_s
0x1800011f6  jmp     short loc_1800011FD
0x1800011f8  mov     rbx, [rsp+500h+lpReturnedString]
0x1800011fd  test    r13, r13
0x180001200  jz      short loc_18000120A
0x180001202  mov     dword ptr [r13+0], 1
0x18000120a  inc     r12
0x18000120d  cmp     word ptr [rbx+r12*2], 0
0x180001213  jnz     short loc_18000120A
0x180001215  mov     eax, r12d
0x180001218  mov     r12, [rsp+500h+var_38]
0x180001220  mov     rcx, [rbp+400h+var_50]
0x180001227  xor     rcx, rsp; StackCookie
0x18000122a  call    __security_check_cookie
0x18000122f  add     rsp, 4D0h
0x180001236  pop     r15
0x180001238  pop     r14
0x18000123a  pop     r13
0x18000123c  pop     rdi
0x18000123d  pop     rsi
0x18000123e  pop     rbx
0x18000123f  pop     rbp
0x180001240  retn
0x180001241  mov     r9, [rsp+500h+lpReturnedString]
0x180001246  xor     edx, edx
0x180001248  mov     rax, r12
0x18000124b  nop     dword ptr [rax+rax+00h]
0x180001250  inc     rax
0x180001253  cmp     word ptr [rbx+rax*2], 0
0x180001258  jnz     short loc_180001250
0x18000125a  mov     rcx, r12
0x18000125d  nop     dword ptr [rax]
0x180001260  inc     rcx
0x180001263  cmp     word ptr [rdi+rcx*2], 0
0x180001268  jnz     short loc_180001260
0x18000126a  add     ecx, 10h
0x18000126d  add     ecx, eax
0x18000126f  cmp     ecx, 10Eh
0x180001275  ja      loc_180001639
0x18000127b  mov     [rsp+500h+lpFileName], rbx
0x180001280  lea     r9, aSoftwareOdbc; "SOFTWARE\\ODBC\\"
0x180001287  lea     r8, aSSS; "%s%s\\%s"
0x18000128e  mov     qword ptr [rsp+500h+nSize], rdi
0x180001293  mov     edx, 10Eh; cchDest
0x180001298  lea     rcx, [rbp+400h+pszDest]; pszDest
0x18000129f  call    StringCchPrintfW
0x1800012a4  mov     rcx, [rsp+500h+hKey]; hKey
0x1800012a9  lea     rax, [rsp+500h+phkResult]
0x1800012ae  mov     r9d, 20019h; samDesired
0x1800012b4  mov     qword ptr [rsp+500h+nSize], rax; phkResult
0x1800012b9  xor     r8d, r8d; ulOptions
0x1800012bc  lea     rdx, [rbp+400h+pszDest]; lpSubKey
0x1800012c3  call    cs:__imp_RegOpenKeyExW
0x1800012c9  mov     ebx, eax
0x1800012cb  test    eax, eax
0x1800012cd  jz      short loc_1800012E9
0x1800012cf  mov     rdx, [rsp+500h+lpReturnedString]; void *
0x1800012d4  mov     r9, r13
0x1800012d7  mov     r8d, r15d
0x1800012da  mov     rcx, rsi; Src
0x1800012dd  call    cpSetDefault
0x1800012e2  mov     ebx, eax
0x1800012e4  jmp     loc_18000169C
0x1800012e9  mov     ecx, r15d
0x1800012ec  mov     [rsp+500h+pcbData], ecx
0x1800012f0  test    r14, r14
0x1800012f3  jnz     loc_18000145E
0x1800012f9  mov     rsi, [rsp+500h+lpReturnedString]
0x1800012fe  xor     edi, edi
0x180001300  mov     r12, [rsp+500h+var_4A0]
0x180001305  cmp     ecx, 4
0x180001308  jbe     loc_180001424
0x18000130e  lea     eax, [rcx-2]
0x180001311  mov     [rsp+500h+lpcbData], 0; lpcbData
0x18000131a  mov     rcx, [rsp+500h+phkResult]; hKey
0x18000131f  lea     r9, [rsp+500h+cchValueName]; lpcchValueName
0x180001324  shr     eax, 1
0x180001326  mov     r8, rsi; lpValueName
0x180001329  mov     [rsp+500h+lpData], 0; lpData
0x180001332  mov     edx, edi; dwIndex
0x180001334  mov     [rsp+500h+lpFileName], 0; lpType
0x18000133d  mov     [rsp+500h+cchValueName], eax
0x180001341  mov     qword ptr [rsp+500h+nSize], 0; lpReserved
0x18000134a  call    cs:__imp_RegEnumValueW
0x180001350  mov     edx, [rsp+500h+cchValueName]
0x180001354  mov     ebx, eax
0x180001356  test    edx, edx
0x180001358  jnz     short loc_180001362
0x18000135a  test    eax, eax
0x18000135c  jz      loc_180001416
0x180001362  add     edx, edx
0x180001364  mov     [rsp+500h+cchValueName], edx
0x180001368  cmp     eax, 0EAh
0x18000136d  jnz     short loc_1800013E5
0x18000136f  mov     rcx, [rsp+500h+phkResult]; hKey
0x180001374  lea     r9, [rsp+500h+cchValueName]; lpcchValueName
0x180001379  mov     [rsp+500h+lpcbData], 0; lpcbData
0x180001382  lea     r8, [rbp+400h+Buffer]; lpValueName
0x180001386  mov     [rsp+500h+lpData], 0; lpData
0x18000138f  mov     edx, edi; dwIndex
0x180001391  mov     [rsp+500h+lpFileName], 0; lpType
0x18000139a  mov     qword ptr [rsp+500h+nSize], 0; lpReserved
0x1800013a3  mov     [rsp+500h+cchValueName], 100h
0x1800013ab  call    cs:__imp_RegEnumValueW
0x1800013b1  mov     ebx, eax
0x1800013b3  test    eax, eax
0x1800013b5  jnz     short loc_180001416
0x1800013b7  mov     eax, [rsp+500h+pcbData]
0x1800013bb  lea     rdx, [rbp+400h+Buffer]; Src
0x1800013bf  add     eax, 0FFFFFFFCh
0x1800013c2  mov     rcx, rsi; void *
0x1800013c5  mov     r8d, eax; Size
0x1800013c8  mov     [rsp+500h+cchValueName], eax
0x1800013cc  call    memcpy_0
0x1800013d1  mov     ecx, [rsp+500h+cchValueName]
0x1800013d5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800013d9  xor     eax, eax
0x1800013db  mov     [rcx+rsi], ax
0x1800013df  mov     edx, [rsp+500h+cchValueName]
0x1800013e3  jmp     short loc_1800013E9
0x1800013e5  test    eax, eax
0x1800013e7  jnz     short loc_180001416
0x1800013e9  mov     ecx, [rsp+500h+pcbData]
0x1800013ed  mov     eax, 0FFFFFFFEh
0x1800013f2  sub     eax, edx
0x1800013f4  mov     dword ptr [r12], 1
0x1800013fc  add     ecx, eax
0x1800013fe  mov     eax, edx
0x180001400  add     rax, 2
0x180001404  mov     [rsp+500h+pcbData], ecx
0x180001408  shr     rax, 1
0x18000140b  inc     edi
0x18000140d  lea     rsi, [rsi+rax*2]
0x180001411  jmp     loc_180001305
0x180001416  mov     ecx, [rsp+500h+pcbData]
0x18000141a  inc     edi
0x18000141c  test    ebx, ebx
0x18000141e  jz      loc_180001305
0x180001424  mov     rdx, [rsp+500h+lpReturnedString]
0x180001429  mov     eax, r15d
0x18000142c  sub     eax, ecx
0x18000142e  mov     ecx, eax
0x180001430  xor     eax, eax
0x180001432  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180001436  mov     [rcx+rdx], ax
0x18000143a  sub     r15d, [rsp+500h+pcbData]
0x18000143f  mov     [rsp+500h+pcbData], r15d
0x180001444  test    r13, r13
0x180001447  jz      short loc_180001451
0x180001449  mov     dword ptr [r13+0], 1
0x180001451  test    ebx, ebx
0x180001453  jz      loc_180001620
0x180001459  jmp     loc_180001628
0x18000145e  mov     rdi, [rsp+500h+lpReturnedString]
0x180001463  lea     rax, [rsp+500h+pcbData]
0x180001468  mov     rbx, [rsp+500h+lpValue]
0x18000146d  lea     rdx, SubKey; lpSubKey
0x180001474  mov     r14d, [rbp+400h+dwFlags]
0x18000147b  mov     r8, rbx; lpValue
0x18000147e  mov     rcx, [rsp+500h+phkResult]; hkey
0x180001483  mov     r9d, r14d; dwFlags
0x180001486  mov     [rsp+500h+lpData], rax; pcbData
0x18000148b  lea     rax, [rsp+500h+pdwType]
0x180001490  mov     [rsp+500h+lpFileName], rdi; pvData
0x180001495  mov     qword ptr [rsp+500h+nSize], rax; pdwType
0x18000149a  mov     [rsp+500h+pdwType], 0
0x1800014a2  call    cs:__imp_RegGetValueW
0x1800014a8  cmp     eax, 0EAh
0x1800014ad  jnz     loc_1800015E9
0x1800014b3  mov     ecx, [rsp+500h+pcbData]
0x1800014b7  mov     edx, 1; Size
0x1800014bc  add     rcx, 2; Count
0x1800014c0  call    cs:__imp_calloc
0x1800014c6  mov     rsi, rax
0x1800014c9  test    rax, rax
0x1800014cc  jz      short loc_180001547
0x1800014ce  mov     rcx, [rsp+500h+phkResult]; hkey
0x1800014d3  lea     rax, [rsp+500h+pcbData]
0x1800014d8  mov     [rsp+500h+lpData], rax; pcbData
0x1800014dd  lea     rdx, SubKey; lpSubKey
0x1800014e4  lea     rax, [rsp+500h+pdwType]
0x1800014e9  mov     [rsp+500h+lpFileName], rsi; pvData
0x1800014ee  mov     r9d, r14d; dwFlags
0x1800014f1  mov     qword ptr [rsp+500h+nSize], rax; pdwType
0x1800014f6  mov     r8, rbx; lpValue
0x1800014f9  call    cs:__imp_RegGetValueW
0x1800014ff  test    eax, eax
0x180001501  jnz     short loc_180001547
0x180001503  mov     r8d, r15d; Size
0x180001506  mov     rdx, rsi; Src
0x180001509  mov     rcx, rdi; void *
0x18000150c  call    memcpy_0
  ... truncated ...
```
