# Windows::Compat::Inventory::GetMoreData::GetMoreData(char const *)

- ea: `0x14000d128`
- end: `0x14000d42a`
- name: `??0GetMoreData@Inventory@Compat@Windows@@QEAA@PEBD@Z`
- size: `770`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::GetMoreData *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c2f8`

## callees

- `0x140001ba0`
- `0x1400026d8`
- `0x1400093e8`
- `0x14000d128`
- `0x14000e0b8`
- `0x1400151b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x14000d33d`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x14000d33d`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000d31b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000d31b`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x14000d1f9`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x14000d1f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d323`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d27f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d27f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d310`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000d232`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000d263`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000d232`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000d263`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000d244`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000d275`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000d244`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000d275`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14000d36e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14000d36e`

## string_xrefs

- `0x14000d1ab`: `Windows::Compat::Inventory::GetMoreData::GetMoreData`
- `0x14000d2ae`: `Windows::Compat::Inventory::GetMoreData::GetMoreData`
- `0x14000d3d9`: `Windows::Compat::Inventory::GetMoreData::GetMoreData`
- `0x14000d3cc`: `Relative paths not supported "%ls" [%#x]`
- `0x14000d285`: `CreateDirectoryW failed [%d]`
- `0x14000d2a1`: `CreateDirectoryW failed [%d]`
- `0x14000d2df`: `%hs\CompatGmd.txt`
- `0x14000d34c`: `fopen_s failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Windows::Compat::Inventory::GetMoreData *__fastcall Windows::Compat::Inventory::GetMoreData::GetMoreData(
        Windows::Compat::Inventory::GetMoreData *this,
        const char *a2)
{
  FILE **v4; // r14
  int v5; // eax
  signed int v6; // edi
  __int64 v7; // r8
  const char *v8; // r9
  void *v9; // rdx
  unsigned int v10; // r8d
  WCHAR *v11; // rbx
  WCHAR *v12; // rax
  _WORD *i; // rbx
  DWORD LastError; // eax
  signed int v15; // eax
  FILE *v16; // rsi
  DWORD v17; // ebx
  FILE *v18; // rbx
  int wDay; // [rsp+20h] [rbp-E0h]
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v23; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v24[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  *(_QWORD *)this = 0;
  v4 = (FILE **)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = -1;
  *((_BYTE *)this + 24) = 0;
  v5 = StringCchPrintfW(FileName, 0x104u, L"%hs", a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v11 = FileName;
    if ( FileName[0] == 92 && FileName[1] == 92 && FileName[2] == 63 )
    {
      v12 = (WCHAR *)&v23;
      if ( FileName[3] != 92 )
        v12 = FileName;
      v11 = v12;
    }
    if ( (unsigned int)_o_iswalpha(*v11) && v11[1] == 58 && v11[2] == 92 )
    {
      for ( i = v11 + 3; *i; ++i )
      {
        if ( *i == 92 )
        {
          *i = 0;
          if ( GetFileAttributesW(FileName) == -1 && !CreateDirectoryW(FileName, 0) )
          {
            LastError = GetLastError();
            AslLogCallPrintf(
              1,
              "Windows::Compat::Inventory::GetMoreData::GetMoreData",
              45,
              "CreateDirectoryW failed [%d]",
              LastError);
            v15 = GetLastError();
            v6 = v15;
            if ( v15 > 0 )
              v6 = (unsigned __int16)v15 | 0x80070000;
            goto LABEL_34;
          }
          *i = 92;
        }
      }
      if ( GetFileAttributesW(FileName) == -1 && !CreateDirectoryW(FileName, 0) )
      {
        v5 = GetLastError();
        v8 = "CreateDirectoryW failed [%d]";
        v7 = 60;
        goto LABEL_4;
      }
      v5 = StringCchPrintfW(v24, 0x104u, L"%hs\\CompatGmd.txt", a2);
      v6 = v5;
      if ( v5 < 0 )
      {
        v7 = 70;
        goto LABEL_3;
      }
      v16 = *v4;
      if ( *v4 )
      {
        v17 = GetLastError();
        fclose(v16);
        SetLastError(v17);
      }
      *v4 = 0;
      v5 = _wfopen_s(v4, v24, L"wt, ccs=UNICODE");
      if ( v5 )
      {
        v6 = -2147467259;
        v8 = "fopen_s failed [%d]";
        v7 = 78;
        goto LABEL_4;
      }
      v18 = *v4;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      wDay = SystemTime.wDay;
      fwprintf(v18, L"GMD run at %d\\%02d\\%02d %02d:%02d:%02d\n\n", SystemTime.wYear, SystemTime.wMonth);
    }
    else
    {
      v6 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::GetMoreData::GetMoreData",
        31,
        "Relative paths not supported \"%ls\" [%#x]",
        FileName,
        -2147467259);
    }
  }
  else
  {
    v7 = 12;
LABEL_3:
    v8 = "StringCchPrintfW failed [%#x]";
LABEL_4:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::GetMoreData::GetMoreData", v7, v8, v5);
  }
LABEL_34:
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v9, v10, (const char *)(unsigned int)v6, wDay);
  return this;
}

```

## disassembly

```asm
0x14000d128  mov     [rsp-8+arg_10], rbx
0x14000d12d  push    rbp
0x14000d12e  push    rsi
0x14000d12f  push    rdi
0x14000d130  push    r12
0x14000d132  push    r13
0x14000d134  push    r14
0x14000d136  push    r15
0x14000d138  lea     rbp, [rsp-390h]
0x14000d140  sub     rsp, 490h
0x14000d147  mov     rax, cs:__security_cookie
0x14000d14e  xor     rax, rsp
0x14000d151  mov     [rbp+3C0h+var_40], rax
0x14000d158  mov     rsi, rdx
0x14000d15b  mov     r15, rcx
0x14000d15e  mov     [rsp+4C0h+var_480], rcx
0x14000d163  xor     r12d, r12d
0x14000d166  mov     [rcx], r12
0x14000d169  lea     r14, [rcx+8]
0x14000d16d  mov     [r14], r12
0x14000d170  mov     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x14000d178  mov     [rcx+18h], r12b
0x14000d17c  mov     r9, rdx
0x14000d17f  lea     r8, aHs_3; "%hs"
0x14000d186  mov     edx, 104h; unsigned __int64
0x14000d18b  lea     rcx, [rsp+4C0h+FileName]; unsigned __int16 *
0x14000d190  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d195  mov     edi, eax
0x14000d197  test    eax, eax
0x14000d199  jns     short loc_14000D1C1
0x14000d19b  lea     r8d, [r12+0Ch]
0x14000d1a0  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x14000d1a7  mov     [rsp+4C0h+var_4A0], eax
0x14000d1ab  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::GetMoreData"...
0x14000d1b2  mov     ecx, 1
0x14000d1b7  call    AslLogCallPrintf
0x14000d1bc  jmp     loc_14000D3E9
0x14000d1c1  lea     rbx, [rsp+4C0h+FileName]
0x14000d1c6  mov     r13d, 5Ch ; '\'
0x14000d1cc  cmp     [rsp+4C0h+FileName], r13w
0x14000d1d2  jnz     short loc_14000D1F6
0x14000d1d4  cmp     [rsp+4C0h+var_45E], r13w
0x14000d1da  jnz     short loc_14000D1F6
0x14000d1dc  cmp     [rsp+4C0h+var_45C], 3Fh ; '?'
0x14000d1e2  jnz     short loc_14000D1F6
0x14000d1e4  lea     rax, [rsp+4C0h+var_458]
0x14000d1e9  cmp     [rsp+4C0h+var_45A], r13w
0x14000d1ef  cmovnz  rax, rbx
0x14000d1f3  mov     rbx, rax
0x14000d1f6  movzx   ecx, word ptr [rbx]
0x14000d1f9  call    cs:__imp__o_iswalpha
0x14000d1ff  test    eax, eax
0x14000d201  jz      loc_14000D3B9
0x14000d207  cmp     word ptr [rbx+2], 3Ah ; ':'
0x14000d20c  jnz     loc_14000D3B9
0x14000d212  cmp     [rbx+4], r13w
0x14000d217  jnz     loc_14000D3B9
0x14000d21d  add     rbx, 6
0x14000d221  jmp     short loc_14000D256
0x14000d223  cmp     ax, r13w
0x14000d227  jnz     short loc_14000D252
0x14000d229  mov     [rbx], r12w
0x14000d22d  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x14000d232  call    cs:__imp_GetFileAttributesW
0x14000d238  cmp     eax, 0FFFFFFFFh
0x14000d23b  jnz     short loc_14000D24E
0x14000d23d  xor     edx, edx; lpSecurityAttributes
0x14000d23f  lea     rcx, [rsp+4C0h+FileName]; lpPathName
0x14000d244  call    cs:__imp_CreateDirectoryW
0x14000d24a  test    eax, eax
0x14000d24c  jz      short loc_14000D297
0x14000d24e  mov     [rbx], r13w
0x14000d252  add     rbx, 2
0x14000d256  movzx   eax, word ptr [rbx]
0x14000d259  test    ax, ax
0x14000d25c  jnz     short loc_14000D223
0x14000d25e  lea     rcx, [rsp+4C0h+FileName]; lpFileName
0x14000d263  call    cs:__imp_GetFileAttributesW
0x14000d269  cmp     eax, 0FFFFFFFFh
0x14000d26c  jnz     short loc_14000D2DC
0x14000d26e  xor     edx, edx; lpSecurityAttributes
0x14000d270  lea     rcx, [rsp+4C0h+FileName]; lpPathName
0x14000d275  call    cs:__imp_CreateDirectoryW
0x14000d27b  test    eax, eax
0x14000d27d  jnz     short loc_14000D2DC
0x14000d27f  call    cs:__imp_GetLastError
0x14000d285  lea     r9, aCreatedirector; "CreateDirectoryW failed [%d]"
0x14000d28c  mov     r8d, 3Ch ; '<'
0x14000d292  jmp     loc_14000D1A7
0x14000d297  call    cs:__imp_GetLastError
0x14000d29d  mov     [rsp+4C0h+var_4A0], eax
0x14000d2a1  lea     r9, aCreatedirector; "CreateDirectoryW failed [%d]"
0x14000d2a8  mov     r8d, 2Dh ; '-'
0x14000d2ae  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::GetMoreData"...
0x14000d2b5  lea     ecx, [r8-2Ch]
0x14000d2b9  call    AslLogCallPrintf
0x14000d2be  call    cs:__imp_GetLastError
0x14000d2c4  mov     edi, eax
0x14000d2c6  test    eax, eax
0x14000d2c8  jle     loc_14000D3E9
0x14000d2ce  movzx   edi, ax
0x14000d2d1  or      edi, 80070000h
0x14000d2d7  jmp     loc_14000D3E9
0x14000d2dc  mov     r9, rsi
0x14000d2df  lea     r8, aHsCompatgmdTxt; "%hs\\CompatGmd.txt"
0x14000d2e6  mov     edx, 104h; unsigned __int64
0x14000d2eb  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x14000d2f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d2f7  mov     edi, eax
0x14000d2f9  test    eax, eax
0x14000d2fb  jns     short loc_14000D308
0x14000d2fd  mov     r8d, 46h ; 'F'
0x14000d303  jmp     loc_14000D1A0
0x14000d308  mov     rsi, [r14]
0x14000d30b  test    rsi, rsi
0x14000d30e  jz      short loc_14000D329
0x14000d310  call    cs:__imp_GetLastError
0x14000d316  mov     ebx, eax
0x14000d318  mov     rcx, rsi; Stream
0x14000d31b  call    cs:__imp_fclose
0x14000d321  mov     ecx, ebx; dwErrCode
0x14000d323  call    cs:__imp_SetLastError
0x14000d329  mov     [r14], r12
0x14000d32c  lea     r8, aWtCcsUnicode; "wt, ccs=UNICODE"
0x14000d333  lea     rdx, [rbp+3C0h+var_250]; FileName
0x14000d33a  mov     rcx, r14; Stream
0x14000d33d  call    cs:__imp__wfopen_s
0x14000d343  test    eax, eax
0x14000d345  jz      short loc_14000D35E
0x14000d347  mov     edi, 80004005h
0x14000d34c  lea     r9, aFopenSFailedD; "fopen_s failed [%d]"
0x14000d353  mov     r8d, 4Eh ; 'N'
0x14000d359  jmp     loc_14000D1A7
0x14000d35e  mov     rbx, [r14]
0x14000d361  xorps   xmm0, xmm0
0x14000d364  movups  xmmword ptr [rsp+4C0h+SystemTime.wYear], xmm0
0x14000d369  lea     rcx, [rsp+4C0h+SystemTime]; lpSystemTime
0x14000d36e  call    cs:__imp_GetSystemTime
0x14000d374  movzx   eax, [rsp+4C0h+SystemTime.wSecond]
0x14000d379  movzx   edx, [rsp+4C0h+SystemTime.wMinute]
0x14000d37e  movzx   r10d, [rsp+4C0h+SystemTime.wHour]
0x14000d384  movzx   r11d, [rsp+4C0h+SystemTime.wDay]
0x14000d38a  movzx   r9d, [rsp+4C0h+SystemTime.wMonth]
0x14000d390  movzx   r8d, [rsp+4C0h+SystemTime.wYear]
0x14000d396  mov     [rsp+4C0h+var_488], eax
0x14000d39a  mov     [rsp+4C0h+var_490], edx
0x14000d39e  mov     [rsp+4C0h+var_498], r10d
0x14000d3a3  mov     [rsp+4C0h+var_4A0], r11d
0x14000d3a8  lea     rdx, aGmdRunAtD02d02; "GMD run at %d\\%02d\\%02d %02d:%02d:%02"...
0x14000d3af  mov     rcx, rbx; Stream
0x14000d3b2  call    fwprintf
0x14000d3b7  jmp     short loc_14000D3E9
0x14000d3b9  mov     edi, 80004005h
0x14000d3be  mov     [rsp+4C0h+var_498], edi
0x14000d3c2  lea     rax, [rsp+4C0h+FileName]
0x14000d3c7  mov     qword ptr [rsp+4C0h+var_4A0], rax; int
0x14000d3cc  lea     r9, aRelativePathsN; "Relative paths not supported \"%ls\" [%"...
0x14000d3d3  mov     r8d, 1Fh
0x14000d3d9  lea     rdx, aWindowsCompatI; "Windows::Compat::Inventory::GetMoreData"...
0x14000d3e0  lea     ecx, [r8-1Eh]
0x14000d3e4  call    AslLogCallPrintf
0x14000d3e9  mov     rcx, [rbp+3C8h]; this
0x14000d3f0  test    edi, edi
0x14000d3f2  js      short loc_14000D421
0x14000d3f4  mov     rax, r15
0x14000d3f7  mov     rcx, [rbp+3C0h+var_40]
0x14000d3fe  xor     rcx, rsp; StackCookie
0x14000d401  call    __security_check_cookie
0x14000d406  mov     rbx, [rsp+4C0h+arg_10]
0x14000d40e  add     rsp, 490h
0x14000d415  pop     r15
0x14000d417  pop     r14
0x14000d419  pop     r13
0x14000d41b  pop     r12
0x14000d41d  pop     rdi
0x14000d41e  pop     rsi
0x14000d41f  pop     rbp
0x14000d420  retn
0x14000d421  mov     r9d, edi; char *
0x14000d424  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
