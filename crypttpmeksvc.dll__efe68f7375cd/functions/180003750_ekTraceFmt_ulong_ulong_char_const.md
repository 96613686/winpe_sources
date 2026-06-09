# ekTraceFmt(ulong,ulong,char const *,...)

- ea: `0x180003750`
- end: `0x180003a0e`
- name: `?ekTraceFmt@@YAXKKPEBDZZ`
- size: `702`
- prototype: `void(unsigned int, char, const char *, ...)`
- caller_count: `43`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001060`
- `0x180001140`
- `0x180001480`
- `0x180001850`
- `0x180001970`
- `0x180002310`
- `0x180002850`
- `0x180002b10`
- `0x1800030f0`
- `0x180003ab0`
- `0x180003c90`
- `0x180003e80`
- `0x180004230`
- `0x180004440`
- `0x1800048d0`
- `0x1800049f0`
- `0x180004db0`
- `0x180004ed0`
- `0x180005380`
- `0x180005680`
- `0x180005910`
- `0x180005b68`
- `0x180005d44`
- `0x180006080`
- `0x1800061f4`
- `0x1800062f8`
- `0x180006f84`
- `0x180007098`
- `0x180007180`
- `0x1800072c0`
- `0x180007338`
- `0x1800077f0`
- `0x180008b50`
- `0x180008ca4`
- `0x180008d58`
- `0x180008e84`
- `0x180008f38`
- `0x180009150`
- `0x1800092a0`
- `0x180009330`
- `0x180009470`
- `0x180009880`
- `0x180009b20`

## callees

- `0x180003750`
- `0x180003a20`
- `0x1800078e8`
- `0x180007bcc`
- `0x180007ce4`
- `0x18000a800`

## import_xrefs

- `msvcrt!strrchr` at `0x1800037c7`
- `msvcrt!strrchr` at `0x1800037c7`
- `msvcrt!_vsnprintf` at `0x1800037a5`
- `msvcrt!_vsnprintf` at `0x1800037a5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003881`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003881`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003969`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003969`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003924`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003924`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003871`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003871`

## pseudocode

```c
void ekTraceFmt(unsigned int a1, char a2, const char *a3, ...)
{
  char *v5; // rax
  int v6; // r14d
  __int64 v7; // rcx
  const char *v8; // r9
  __int64 v9; // r10
  char *v10; // rdx
  char *v11; // rax
  __int64 v12; // rdx
  const char *v13; // rcx
  unsigned int v14; // r8d
  int v15; // edi
  __int64 i; // rsi
  const WCHAR *v17; // rdx
  bool v18; // al
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-D0h] BYREF
  FILETIME FileTime2; // [rsp+40h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-BCh] BYREF
  char v23[32]; // [rsp+50h] [rbp-B8h] BYREF
  char Buffer[1024]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v25[1024]; // [rsp+478h] [rbp+370h] BYREF
  va_list ArgList; // [rsp+CF0h] [rbp+BE8h] BYREF

  va_start(ArgList, a3);
  FileTime2 = 0;
  if ( (unsigned int)_vsnprintf(Buffer, 0x3FFu, a3, ArgList) > 0x3FE )
    Buffer[1023] = 0;
  v5 = strrchr(Buffer, 10);
  if ( v5 && !v5[1] )
    *v5 = 0;
  v6 = StringCchPrintfW(v25, 0x400u, L"%hs", Buffer);
  if ( !s_szLogFileName )
  {
    v7 = 2147483646;
    v8 = "CryptTpmEkSvc.log";
    v9 = 128;
    v10 = &s_szLogFileName;
    do
    {
      if ( !v7 )
        break;
      if ( !*v8 )
        break;
      *v10++ = *v8++;
      --v7;
      --v9;
    }
    while ( v9 );
    v11 = v10 - 1;
    if ( v9 )
      v11 = v10;
    *v11 = 0;
  }
  FileTime2 = (FILETIME)(qword_180012978 + 3000000000LL);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) <= 0 )
  {
    v15 = dword_1800126E8;
  }
  else
  {
    qword_180012978 = (__int64)SystemTimeAsFileTime;
    FileTime2 = 0;
    v15 = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Cryptography\\AutoEnrollment",
            0,
            0x20019u,
            (PHKEY)&FileTime2) )
    {
      for ( i = 0; i != 2; ++i )
      {
        v17 = off_18000C1A0[i];
        Type = 0;
        SystemTimeAsFileTime.dwLowDateTime = 0;
        cbData = 4;
        if ( !RegQueryValueExW(*(HKEY *)&FileTime2, v17, 0, &Type, (LPBYTE)&SystemTimeAsFileTime, &cbData)
          && Type == 4
          && cbData == 4
          && SystemTimeAsFileTime.dwLowDateTime )
        {
          v15 |= SystemTimeAsFileTime.dwLowDateTime;
        }
      }
    }
    v13 = (const char *)FileTime2;
    if ( FileTime2 )
      RegCloseKey(*(HKEY *)&FileTime2);
    dword_1800126E8 = v15;
  }
  v18 = (a2 & 1) != 0 && v15;
  if ( ((a2 & 2) != 0 && v15 || v18) && eksvcOpenLog(v13, v12, v14) )
  {
    StringCchPrintfA(v23, 0x24u, "%u.%u.0", (unsigned __int16)a1, HIWORD(a1));
    eksvcLogStringA(v23, v6, v25);
  }
}

```

## disassembly

```asm
0x180003750  mov     r11, rsp
0x180003753  mov     [r11+18h], r8
0x180003757  mov     [r11+20h], r9
0x18000375b  push    rbp
0x18000375c  push    r14
0x18000375e  push    r15
0x180003760  lea     rbp, [r11-0BC8h]
0x180003767  sub     rsp, 0CB0h
0x18000376e  mov     rax, cs:__security_cookie
0x180003775  xor     rax, rsp
0x180003778  mov     [rbp+0BC0h+var_50], rax
0x18000377f  mov     [r11-20h], rbx
0x180003783  lea     r9, [rbp+0BC0h+ArgList]; ArgList
0x18000378a  mov     [r11-38h], r12
0x18000378e  mov     ebx, edx
0x180003790  mov     r15d, ecx
0x180003793  xor     r12d, r12d
0x180003796  mov     edx, 3FFh; BufferCount
0x18000379b  mov     qword ptr [rsp+0CC0h+FileTime2.dwLowDateTime], r12
0x1800037a0  lea     rcx, [rsp+0CC0h+Buffer]; Buffer
0x1800037a5  call    cs:__imp__vsnprintf
0x1800037ab  test    eax, eax
0x1800037ad  js      short loc_1800037B6
0x1800037af  cmp     eax, 3FFh
0x1800037b4  jb      short loc_1800037BD
0x1800037b6  mov     [rbp+0BC0h+var_851], r12b
0x1800037bd  mov     edx, 0Ah; Ch
0x1800037c2  lea     rcx, [rsp+0CC0h+Buffer]; Str
0x1800037c7  call    cs:__imp_strrchr
0x1800037cd  test    rax, rax
0x1800037d0  jz      short loc_1800037DB
0x1800037d2  cmp     [rax+1], r12b
0x1800037d6  jnz     short loc_1800037DB
0x1800037d8  mov     [rax], r12b
0x1800037db  lea     r9, [rsp+0CC0h+Buffer]
0x1800037e0  mov     edx, 400h; unsigned __int64
0x1800037e5  lea     r8, aHs_2; "%hs"
0x1800037ec  lea     rcx, [rbp+0BC0h+var_850]; unsigned __int16 *
0x1800037f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800037f8  cmp     cs:?s_szLogFileName@@3PADA, r12b; char near * s_szLogFileName
0x1800037ff  mov     r14d, eax
0x180003802  jnz     short loc_18000384E
0x180003804  mov     ecx, 7FFFFFFEh
0x180003809  lea     r9, aCrypttpmeksvcL; "CryptTpmEkSvc.log"
0x180003810  mov     r10d, 80h
0x180003816  lea     rdx, ?s_szLogFileName@@3PADA; char near * s_szLogFileName
0x18000381d  nop     dword ptr [rax]
0x180003820  test    rcx, rcx
0x180003823  jz      short loc_180003840
0x180003825  movzx   r8d, byte ptr [r9]
0x180003829  test    r8b, r8b
0x18000382c  jz      short loc_180003840
0x18000382e  mov     [rdx], r8b
0x180003831  inc     r9
0x180003834  inc     rdx
0x180003837  dec     rcx
0x18000383a  sub     r10, 1
0x18000383e  jnz     short loc_180003820
0x180003840  test    r10, r10
0x180003843  lea     rax, [rdx-1]
0x180003847  cmovnz  rax, rdx
0x18000384b  mov     [rax], r12b
0x18000384e  mov     ecx, 0B2D05E00h
0x180003853  mov     [rsp+0CC0h+var_28], rdi
0x18000385b  add     rcx, cs:qword_180012978
0x180003862  mov     qword ptr [rsp+0CC0h+FileTime2.dwLowDateTime], rcx
0x180003867  lea     rcx, [rsp+0CC0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000386c  mov     qword ptr [rsp+0CC0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180003871  call    cs:__imp_GetSystemTimeAsFileTime
0x180003877  lea     rdx, [rsp+0CC0h+FileTime2]; lpFileTime2
0x18000387c  lea     rcx, [rsp+0CC0h+SystemTimeAsFileTime]; lpFileTime1
0x180003881  call    cs:__imp_CompareFileTime
0x180003887  test    eax, eax
0x180003889  jle     loc_180003977
0x18000388f  mov     rax, qword ptr [rsp+0CC0h+SystemTimeAsFileTime.dwLowDateTime]
0x180003894  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\Auto"...
0x18000389b  mov     cs:qword_180012978, rax
0x1800038a2  mov     r9d, 20019h; samDesired
0x1800038a8  lea     rax, [rsp+0CC0h+FileTime2]
0x1800038ad  mov     qword ptr [rsp+0CC0h+FileTime2.dwLowDateTime], r12
0x1800038b2  xor     r8d, r8d; ulOptions
0x1800038b5  mov     [rsp+0CC0h+phkResult], rax; phkResult
0x1800038ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800038c1  mov     edi, r12d
0x1800038c4  call    cs:__imp_RegOpenKeyExW
0x1800038ca  test    eax, eax
0x1800038cc  jnz     loc_18000395F
0x1800038d2  mov     [rsp+0CC0h+var_20], rsi
0x1800038da  mov     rsi, r12
0x1800038dd  mov     [rsp+0CC0h+var_38], r13
0x1800038e5  lea     r13, off_18000C1A0; "Debug"
0x1800038ec  mov     rdx, [r13+rsi*8+0]; lpValueName
0x1800038f1  lea     rax, [rsp+0CC0h+cbData]
0x1800038f6  mov     rcx, qword ptr [rsp+0CC0h+FileTime2.dwLowDateTime]; hKey
0x1800038fb  lea     r9, [rsp+0CC0h+Type]; lpType
0x180003900  mov     [rsp+0CC0h+lpcbData], rax; lpcbData
0x180003905  xor     r8d, r8d; lpReserved
0x180003908  lea     rax, [rsp+0CC0h+SystemTimeAsFileTime]
0x18000390d  mov     [rsp+0CC0h+Type], r12d
0x180003912  mov     [rsp+0CC0h+phkResult], rax; lpData
0x180003917  mov     [rsp+0CC0h+SystemTimeAsFileTime.dwLowDateTime], r12d
0x18000391c  mov     [rsp+0CC0h+cbData], 4
0x180003924  call    cs:__imp_RegQueryValueExW
0x18000392a  test    eax, eax
0x18000392c  jnz     short loc_180003946
0x18000392e  cmp     [rsp+0CC0h+Type], 4
0x180003933  jnz     short loc_180003946
0x180003935  cmp     [rsp+0CC0h+cbData], 4
0x18000393a  jnz     short loc_180003946
0x18000393c  mov     eax, [rsp+0CC0h+SystemTimeAsFileTime.dwLowDateTime]
0x180003940  test    eax, eax
0x180003942  jz      short loc_180003946
0x180003944  or      edi, eax
0x180003946  inc     rsi
0x180003949  cmp     rsi, 2
0x18000394d  jnz     short loc_1800038EC
0x18000394f  mov     r13, [rsp+0CC0h+var_38]
0x180003957  mov     rsi, [rsp+0CC0h+var_20]
0x18000395f  mov     rcx, qword ptr [rsp+0CC0h+FileTime2.dwLowDateTime]; hKey
0x180003964  test    rcx, rcx
0x180003967  jz      short loc_18000396F
0x180003969  call    cs:__imp_RegCloseKey
0x18000396f  mov     cs:dword_1800126E8, edi
0x180003975  jmp     short loc_18000397D
0x180003977  mov     edi, cs:dword_1800126E8
0x18000397d  mov     r12, [rsp+0CC0h+var_30]
0x180003985  test    bl, 1
0x180003988  jz      short loc_180003992
0x18000398a  test    edi, edi
0x18000398c  jz      short loc_180003992
0x18000398e  mov     al, 1
0x180003990  jmp     short loc_180003994
0x180003992  xor     al, al
0x180003994  test    bl, 2
0x180003997  mov     rbx, qword ptr [rsp+0CC0h+var_18]
0x18000399f  jz      short loc_1800039A5
0x1800039a1  test    edi, edi
0x1800039a3  jnz     short loc_1800039A9
0x1800039a5  test    al, al
0x1800039a7  jz      short loc_1800039EA
0x1800039a9  call    ?eksvcOpenLog@@YA_NXZ; eksvcOpenLog(void)
0x1800039ae  test    al, al
0x1800039b0  jz      short loc_1800039EA
0x1800039b2  mov     eax, r15d
0x1800039b5  movzx   r9d, r15w
0x1800039b9  shr     eax, 10h
0x1800039bc  lea     r8, aUU0; "%u.%u.0"
0x1800039c3  mov     edx, 24h ; '$'; unsigned __int64
0x1800039c8  mov     dword ptr [rsp+0CC0h+phkResult], eax
0x1800039cc  lea     rcx, [rsp+0CC0h+var_C78]; char *
0x1800039d1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800039d6  lea     r8, [rbp+0BC0h+var_850]; unsigned __int16 *
0x1800039dd  mov     edx, r14d; int
0x1800039e0  lea     rcx, [rsp+0CC0h+var_C78]; char *
0x1800039e5  call    ?eksvcLogStringA@@YAXPEBDJPEBG@Z; eksvcLogStringA(char const *,long,ushort const *)
0x1800039ea  mov     rdi, [rsp+0CC0h+var_28]
0x1800039f2  mov     rcx, [rbp+0BC0h+var_50]
0x1800039f9  xor     rcx, rsp; StackCookie
0x1800039fc  call    __security_check_cookie
0x180003a01  add     rsp, 0CB0h
0x180003a08  pop     r15
0x180003a0a  pop     r14
0x180003a0c  pop     rbp
0x180003a0d  retn
```
