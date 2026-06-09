# myConsolePrintf(ushort const *,...)

- ea: `0x180021e30`
- end: `0x18002241d`
- name: `?myConsolePrintf@@YAHPEBGZZ`
- size: `1517`
- prototype: `__int64(wchar_t *, ...)`
- caller_count: `14`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180019b68`
- `0x180019cfc`
- `0x180019d90`
- `0x180019e44`
- `0x180019f70`
- `0x18001a0d8`
- `0x18001a1b8`
- `0x18001a254`
- `0x18001a404`
- `0x18001a47c`
- `0x18001a518`
- `0x18001a5d8`
- `0x18001b07c`
- `0x18001bbf0`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000f718`
- `0x180012450`
- `0x180013a86`
- `0x180013a92`
- `0x180014ffc`
- `0x18001d1ec`
- `0x180021d5c`
- `0x180021e30`
- `0x1800382c0`
- `0x180038380`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180022318`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002234b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180022318`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002234b`
- `msvcrt!fprintf` at `0x1800222f0`
- `msvcrt!fprintf` at `0x1800222f0`
- `msvcrt!fflush` at `0x1800222c7`
- `msvcrt!fflush` at `0x180022303`
- `msvcrt!fflush` at `0x1800222c7`
- `msvcrt!fflush` at `0x180022303`
- `msvcrt!vfwprintf` at `0x18002233e`
- `msvcrt!vfwprintf` at `0x18002233e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021f53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800221f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021f53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800221f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022252`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180021fbc`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180021fbc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800220d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800221b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800220d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800221b5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022138`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022138`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x180022248`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x180022248`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180021eb6`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180021eb6`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180022115`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180022157`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180022115`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180022157`

## pseudocode

```c
__int64 myConsolePrintf(wchar_t *a1, ...)
{
  int v1; // edi
  unsigned __int16 *v2; // rsi
  CHAR *v3; // r12
  _BYTE *v4; // r15
  __int64 StdHandle; // r14
  unsigned int v6; // r13d
  int v7; // eax
  int v8; // edx
  unsigned int v9; // ecx
  int v10; // eax
  DWORD v11; // eax
  __int64 v12; // r13
  unsigned int v13; // eax
  _WORD *v14; // r12
  DWORD v15; // ebx
  CHAR *v16; // r13
  int v17; // eax
  unsigned int cbMultiByte; // ebx
  UINT ACP; // eax
  int v20; // eax
  UINT v21; // eax
  int v22; // ebx
  DWORD LastError; // eax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  void (*v27)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  FILE *v28; // rax
  FILE *v29; // rax
  int Buffer; // [rsp+40h] [rbp-1098h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-1094h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-1090h] BYREF
  DWORD v34; // [rsp+50h] [rbp-1088h]
  CHAR *v35; // [rsp+58h] [rbp-1080h]
  _BYTE *v36; // [rsp+60h] [rbp-1078h]
  int v37; // [rsp+68h] [rbp-1070h]
  void (*v38)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+78h] [rbp-1060h]
  const struct _EXCEPTION_POINTERS *v39; // [rsp+80h] [rbp-1058h] BYREF
  _WORD hMem[512]; // [rsp+90h] [rbp-1048h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+490h] [rbp-C48h] BYREF
  _BYTE Src[2048]; // [rsp+890h] [rbp-848h] BYREF
  wchar_t *Format; // [rsp+10E0h] [rbp+8h]
  va_list ArgList; // [rsp+10E8h] [rbp+10h] BYREF

  va_start(ArgList, a1);
  Format = a1;
  v1 = 0;
  NumberOfBytesWritten = 0;
  v2 = hMem;
  v33 = (unsigned __int64)hMem;
  v3 = 0;
  v35 = 0;
  v4 = 0;
  v36 = 0;
  v34 = 0;
  if ( !a1 )
  {
    a1 = L"(null)";
    Format = L"(null)";
  }
  if ( !*a1 )
    goto LABEL_74;
  StdHandle = (__int64)GetStdHandle(0xFFFFFFF5);
  if ( !StdHandle )
    StdHandle = -1;
  hMem[0] = 0;
  if ( byte_1800C4E0F )
    goto LABEL_63;
  v6 = 512;
  if ( StdHandle == -1 )
    goto LABEL_63;
  while ( 1 )
  {
    *v2 = 0;
    v7 = StringCchVPrintfW(v2, v6, Format, ArgList);
    if ( !v7 )
      break;
    if ( v7 != -2147024774 )
    {
      v8 = v7;
      v9 = 54985121;
      goto LABEL_19;
    }
    if ( v6 >= 0x10000 )
    {
      v8 = -2147024785;
      v9 = 55509409;
      goto LABEL_19;
    }
    if ( v2 != hMem )
      LocalFree(v2);
    v6 *= 2;
    if ( v6 > 0x10000 )
      v6 = 0x10000;
    v2 = (unsigned __int16 *)LocalAlloc(0, 2LL * v6);
    v33 = (unsigned __int64)v2;
    if ( !v2 )
    {
      v8 = -2147024882;
      v9 = 56557985;
LABEL_19:
      CSPrintErrorLineFile(v9, v8);
      goto LABEL_63;
    }
  }
  v33 = 0;
  v10 = StringCchLengthW(v2, v6, &v33);
  if ( v10 )
  {
    CSPrintErrorLineFile(0x36B01A1u, v10);
    goto LABEL_74;
  }
  v11 = GetFileType((HANDLE)StdHandle) & 0xFFFF7FFF;
  if ( !v11 )
  {
    CSPrintErrorLineFileData2(0, 0x37F01A1u, -2147418113, -2147418113);
    byte_1800C4E0F = 1;
LABEL_62:
    v33 = (unsigned __int64)v2;
    goto LABEL_63;
  }
  v12 = (int)v33;
  if ( v11 == 2 )
  {
    if ( !WriteConsoleW((HANDLE)StdHandle, v2, v33, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 1 )
        CSPrintErrorLineFileData2(0, 0x39001A1u, LastError, 6);
      StdHandle = -1;
    }
    v33 = (unsigned __int64)v2;
LABEL_59:
    if ( StdHandle != -1 )
      goto LABEL_74;
    goto LABEL_63;
  }
  v13 = 2 * v33 + 2;
  if ( v13 > 0x400 )
  {
    v4 = LocalAlloc(0, 2LL * v13);
    v36 = v4;
    if ( !v4 )
    {
      CSPrintErrorLineFile(0x3A601A1u, -2147024882);
      StdHandle = -1;
    }
  }
  else
  {
    v4 = Src;
    v36 = Src;
  }
  memcpy_0(v4, v2, 2 * v12);
  if ( StdHandle == -1 )
    goto LABEL_62;
  v33 = (unsigned __int64)v2;
  if ( (int)v12 > 0 )
  {
    v14 = v4;
    do
    {
      if ( *v14 == 10 )
      {
        memmove_0(v14 + 1, v14, 2LL * ((int)v12 - v1));
        *v14++ = 13;
        ++v1;
        LODWORD(v12) = v12 + 1;
      }
      ++v1;
      ++v14;
    }
    while ( v1 < (int)v12 );
    v3 = 0;
  }
  v15 = 2 * v12;
  if ( UnicodeEnabled() )
  {
    v16 = v4;
    if ( !byte_1800C4E0D )
    {
      LOWORD(Buffer) = -257;
      if ( WriteFile((HANDLE)StdHandle, &Buffer, 2u, &NumberOfBytesWritten, 0) )
        v34 = NumberOfBytesWritten >> 1;
    }
    goto LABEL_47;
  }
  v17 = 0;
  if ( !(_DWORD)v12 )
    goto LABEL_45;
  cbMultiByte = v15 + 2;
  if ( cbMultiByte > 0x400 )
  {
    v3 = (CHAR *)LocalAlloc(0, cbMultiByte);
    v35 = v3;
    if ( !v3 )
    {
      CSPrintErrorLineFile(0x3EC01A1u, -2147024882);
      v17 = 0;
      goto LABEL_44;
    }
  }
  else
  {
    v3 = MultiByteStr;
    v35 = MultiByteStr;
  }
  ACP = GetACP();
  v17 = WideCharToMultiByte(ACP, 0, (LPCWCH)v4, v12, v3, cbMultiByte, 0, 0);
  Buffer = v17;
  if ( v17 )
    goto LABEL_45;
  v20 = myHLastError();
  CSPrintErrorLineFile(0x3FE01A1u, v20);
  v21 = GetACP();
  CSPrintErrorLineFileData2(v2, 0x3FF01A1u, v21, 0);
  CSPrintErrorLineFileData2(L"Ansi", 0x40001A1u, v12, 0);
  v17 = 0;
LABEL_44:
  StdHandle = -1;
LABEL_45:
  v16 = v3;
  v34 = 0;
  if ( StdHandle != -1 )
  {
    v15 = v17;
LABEL_47:
    if ( WriteFile((HANDLE)StdHandle, v16, v15, &NumberOfBytesWritten, 0) )
    {
      if ( UnicodeEnabled() )
        NumberOfBytesWritten >>= 1;
      goto LABEL_74;
    }
    v22 = myHLastError();
    CSPrintErrorLineFile(0x40D01A1u, v22);
    if ( v22 == -2147024890 )
    {
      StdHandle = -1;
      byte_1800C4E0F = 1;
    }
    goto LABEL_59;
  }
LABEL_63:
  Buffer = 0;
  while ( 2 )
  {
    if ( ((__int64)_acrt_iob_func(1u)->_ptr & 1) != 0 )
    {
      v24 = _acrt_iob_func(1u);
      fflush(v24);
    }
    if ( ((__int64)_acrt_iob_func(1u)->_ptr & 1) != 0 )
    {
      v25 = _acrt_iob_func(1u);
      fprintf(v25, " ");
      v26 = _acrt_iob_func(1u);
      fflush(v26);
    }
    try
    {
      v27 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
      v38 = v27;
      v28 = _acrt_iob_func(1u);
      NumberOfBytesWritten = vfwprintf(v28, Format, ArgList);
      _set_se_translator(v27);
    }
    catch ( const StructuredException *v39 )
    {
      v37 = myHExceptionCodePrint(v39 + 77, 0, 0x1A1u, 0x434u);
      NumberOfBytesWritten = -1;
      if ( !v37 || Buffer )
      {
        v2 = (unsigned __int16 *)v33;
        v3 = v35;
        v4 = v36;
        break;
      }
      v29 = _acrt_iob_func(1u);
      v2 = (unsigned __int16 *)v33;
      v3 = v35;
      v4 = v36;
      if ( ((__int64)v29->_ptr & 1) == 0 )
        break;
      Buffer = 1;
      continue;
    }
    break;
  }
LABEL_74:
  byte_1800C4E0D = 1;
  if ( v2 && hMem != v2 )
    LocalFree(v2);
  if ( v3 && MultiByteStr != v3 )
    LocalFree(v3);
  if ( v4 && Src != v4 )
    LocalFree(v4);
  return v34 + NumberOfBytesWritten;
}

```

## disassembly

```asm
0x180021e30  mov     rax, rsp
0x180021e33  mov     [rax+8], rcx
0x180021e37  mov     [rax+10h], rdx
0x180021e3b  mov     [rax+18h], r8
0x180021e3f  mov     [rax+20h], r9
0x180021e43  push    rbx
0x180021e44  push    rsi
0x180021e45  push    rdi
0x180021e46  push    r12
0x180021e48  push    r13
0x180021e4a  push    r14
0x180021e4c  push    r15
0x180021e4e  mov     eax, 10A0h
0x180021e53  call    _alloca_probe
0x180021e58  sub     rsp, rax
0x180021e5b  mov     rax, cs:__security_cookie
0x180021e62  xor     rax, rsp
0x180021e65  mov     [rsp+10D8h+var_48], rax
0x180021e6d  xor     edi, edi
0x180021e6f  mov     [rsp+10D8h+NumberOfBytesWritten], edi
0x180021e73  lea     rsi, [rsp+10D8h+hMem]
0x180021e7b  mov     [rsp+10D8h+var_1090], rsi
0x180021e80  mov     r12d, edi
0x180021e83  mov     [rsp+10D8h+var_1080], rdi
0x180021e88  mov     r15d, edi
0x180021e8b  mov     [rsp+10D8h+var_1078], rdi
0x180021e90  mov     [rsp+10D8h+var_1088], edi
0x180021e94  test    rcx, rcx
0x180021e97  jnz     short loc_180021EA8
0x180021e99  lea     rcx, aNull; "(null)"
0x180021ea0  mov     [rsp+10D8h+Format], rcx
0x180021ea8  cmp     di, [rcx]
0x180021eab  jz      loc_18002239A
0x180021eb1  mov     ecx, 0FFFFFFF5h; nStdHandle
0x180021eb6  call    cs:__imp_GetStdHandle
0x180021ebc  mov     r14, rax
0x180021ebf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021ec3  test    r14, r14
0x180021ec6  cmovz   r14, rax
0x180021eca  mov     [rsp+10D8h+hMem], di
0x180021ed2  cmp     cs:byte_1800C4E0F, dil
0x180021ed9  jnz     loc_1800222A7
0x180021edf  mov     r13d, 200h
0x180021ee5  cmp     r14, rax
0x180021ee8  jz      loc_1800222A7
0x180021eee  mov     rbx, rsi
0x180021ef1  mov     [rsi], di
0x180021ef4  lea     r9, [rsp+10D8h+ArgList]; char *
0x180021efc  mov     edx, r13d; unsigned __int64
0x180021eff  mov     r8, [rsp+10D8h+Format]; unsigned __int16 *
0x180021f07  mov     rcx, rsi; unsigned __int16 *
0x180021f0a  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180021f0f  test    eax, eax
0x180021f11  jz      short loc_180021F8F
0x180021f13  cmp     eax, 8007007Ah
0x180021f18  jnz     short loc_180021F7E
0x180021f1a  mov     ebx, 10000h
0x180021f1f  cmp     r13d, ebx
0x180021f22  jnb     short loc_180021F72
0x180021f24  lea     rax, [rsp+10D8h+hMem]
0x180021f2c  cmp     rsi, rax
0x180021f2f  jz      short loc_180021F3A
0x180021f31  mov     rcx, rsi; hMem
0x180021f34  call    cs:__imp_LocalFree
0x180021f3a  lea     eax, ds:0[r13*2]
0x180021f42  mov     r13d, eax
0x180021f45  cmp     eax, ebx
0x180021f47  cmova   r13d, ebx
0x180021f4b  mov     edx, r13d
0x180021f4e  add     rdx, rdx; uBytes
0x180021f51  xor     ecx, ecx; uFlags
0x180021f53  call    cs:__imp_LocalAlloc
0x180021f59  mov     rsi, rax
0x180021f5c  mov     [rsp+10D8h+var_1090], rax
0x180021f61  test    rax, rax
0x180021f64  jnz     short loc_180021EEE
0x180021f66  mov     edx, 8007000Eh
0x180021f6b  mov     ecx, 35F01A1h
0x180021f70  jmp     short loc_180021F85
0x180021f72  mov     edx, 8007006Fh
0x180021f77  mov     ecx, 34F01A1h
0x180021f7c  jmp     short loc_180021F85
0x180021f7e  mov     edx, eax; int
0x180021f80  mov     ecx, 34701A1h; unsigned int
0x180021f85  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180021f8a  jmp     loc_1800222A7
0x180021f8f  mov     [rsp+10D8h+var_1090], rdi
0x180021f94  mov     edx, r13d; unsigned __int64
0x180021f97  lea     r8, [rsp+10D8h+var_1090]; unsigned __int64 *
0x180021f9c  mov     rcx, rbx; unsigned __int16 *
0x180021f9f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180021fa4  test    eax, eax
0x180021fa6  jz      short loc_180021FB9
0x180021fa8  mov     edx, eax; int
0x180021faa  mov     ecx, 36B01A1h; unsigned int
0x180021faf  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180021fb4  jmp     loc_18002239A
0x180021fb9  mov     rcx, r14; hFile
0x180021fbc  call    cs:__imp_GetFileType
0x180021fc2  and     eax, 0FFFF7FFFh
0x180021fc7  jz      loc_180022286
0x180021fcd  movsxd  r13, dword ptr [rsp+10D8h+var_1090]
0x180021fd2  cmp     eax, 2
0x180021fd5  jz      loc_180022235
0x180021fdb  lea     eax, ds:2[r13*2]
0x180021fe3  cmp     eax, 400h
0x180021fe8  ja      short loc_180021FF9
0x180021fea  lea     r15, [rsp+10D8h+Src]
0x180021ff2  mov     [rsp+10D8h+var_1078], r15
0x180021ff7  jmp     short loc_180022026
0x180021ff9  mov     edx, eax
0x180021ffb  add     rdx, rdx; uBytes
0x180021ffe  xor     ecx, ecx; uFlags
0x180022000  call    cs:__imp_LocalAlloc
0x180022006  mov     r15, rax
0x180022009  mov     [rsp+10D8h+var_1078], rax
0x18002200e  test    rax, rax
0x180022011  jnz     short loc_180022026
0x180022013  mov     edx, 8007000Eh; int
0x180022018  mov     ecx, 3A601A1h; unsigned int
0x18002201d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180022022  or      r14, 0FFFFFFFFFFFFFFFFh
0x180022026  mov     r8, r13
0x180022029  add     r8, r8; Size
0x18002202c  mov     rdx, rbx; Src
0x18002202f  mov     rcx, r15; void *
0x180022032  call    memcpy_0
0x180022037  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002203b  jz      loc_1800222A2
0x180022041  mov     [rsp+10D8h+var_1090], rsi
0x180022046  test    r13d, r13d
0x180022049  jle     short loc_18002208E
0x18002204b  mov     r12, r15
0x18002204e  cmp     word ptr [r12], 0Ah
0x180022054  jnz     short loc_18002207E
0x180022056  mov     eax, r13d
0x180022059  sub     eax, edi
0x18002205b  movsxd  r8, eax
0x18002205e  add     r8, r8; Size
0x180022061  mov     rdx, r12; Src
0x180022064  lea     rcx, [r12+2]; void *
0x180022069  call    memmove_0
0x18002206e  mov     word ptr [r12], 0Dh
0x180022075  add     r12, 2
0x180022079  inc     edi
0x18002207b  inc     r13d
0x18002207e  inc     edi
0x180022080  add     r12, 2
0x180022084  cmp     edi, r13d
0x180022087  jl      short loc_18002204E
0x180022089  xor     edi, edi
0x18002208b  mov     r12d, edi
0x18002208e  lea     ebx, ds:0[r13*2]
0x180022096  call    ?UnicodeEnabled@@YA_NXZ; UnicodeEnabled(void)
0x18002209b  test    al, al
0x18002209d  jz      short loc_1800220EE
0x18002209f  mov     r13, r15
0x1800220a2  cmp     cs:byte_1800C4E0D, dil
0x1800220a9  jnz     loc_1800221A2
0x1800220af  mov     eax, 0FEFFh
0x1800220b4  mov     word ptr [rsp+10D8h+Buffer], ax
0x1800220b9  mov     [rsp+10D8h+lpOverlapped], rdi; lpOverlapped
0x1800220be  lea     r9, [rsp+10D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800220c3  mov     r8d, 2; nNumberOfBytesToWrite
0x1800220c9  lea     rdx, [rsp+10D8h+Buffer]; lpBuffer
0x1800220ce  mov     rcx, r14; hFile
0x1800220d1  call    cs:__imp_WriteFile
0x1800220d7  test    eax, eax
0x1800220d9  jz      loc_1800221A2
0x1800220df  mov     eax, [rsp+10D8h+NumberOfBytesWritten]
0x1800220e3  shr     eax, 1
0x1800220e5  mov     [rsp+10D8h+var_1088], eax
0x1800220e9  jmp     loc_1800221A2
0x1800220ee  mov     eax, edi
0x1800220f0  test    r13d, r13d
0x1800220f3  jz      loc_18002218F
0x1800220f9  add     ebx, 2
0x1800220fc  cmp     ebx, 400h
0x180022102  ja      loc_1800221EE
0x180022108  lea     r12, [rsp+10D8h+MultiByteStr]
0x180022110  mov     [rsp+10D8h+var_1080], r12
0x180022115  call    cs:__imp_GetACP
0x18002211b  mov     ecx, eax; CodePage
0x18002211d  mov     [rsp+10D8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180022122  mov     [rsp+10D8h+lpDefaultChar], rdi; lpDefaultChar
0x180022127  mov     [rsp+10D8h+cbMultiByte], ebx; cbMultiByte
0x18002212b  mov     [rsp+10D8h+lpOverlapped], r12; lpMultiByteStr
0x180022130  mov     r9d, r13d; cchWideChar
0x180022133  mov     r8, r15; lpWideCharStr
0x180022136  xor     edx, edx; dwFlags
0x180022138  call    cs:__imp_WideCharToMultiByte
0x18002213e  mov     [rsp+10D8h+Buffer], eax
0x180022142  test    eax, eax
0x180022144  jnz     short loc_18002218F
0x180022146  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002214b  mov     edx, eax; int
0x18002214d  mov     ecx, 3FE01A1h; unsigned int
0x180022152  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180022157  call    cs:__imp_GetACP
0x18002215d  xor     r9d, r9d; int
0x180022160  mov     r8d, eax; int
0x180022163  mov     edx, 3FF01A1h; unsigned int
0x180022168  mov     rcx, rsi; unsigned __int16 *
0x18002216b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180022170  xor     r9d, r9d; int
0x180022173  mov     r8d, r13d; int
0x180022176  mov     edx, 40001A1h; unsigned int
0x18002217b  lea     rcx, aAnsi; "Ansi"
0x180022182  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180022187  mov     eax, [rsp+10D8h+Buffer]
0x18002218b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002218f  mov     r13, r12
0x180022192  mov     [rsp+10D8h+var_1088], edi
0x180022196  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002219a  jz      loc_1800222A7
0x1800221a0  mov     ebx, eax
0x1800221a2  mov     [rsp+10D8h+lpOverlapped], rdi; lpOverlapped
0x1800221a7  lea     r9, [rsp+10D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800221ac  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800221af  mov     rdx, r13; lpBuffer
0x1800221b2  mov     rcx, r14; hFile
0x1800221b5  call    cs:__imp_WriteFile
0x1800221bb  test    eax, eax
0x1800221bd  jnz     short loc_18002221F
0x1800221bf  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800221c4  mov     ebx, eax
0x1800221c6  mov     edx, eax; int
0x1800221c8  mov     ecx, 40D01A1h; unsigned int
0x1800221cd  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800221d2  cmp     ebx, 80070006h
0x1800221d8  jnz     loc_18002227B
0x1800221de  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800221e2  mov     cs:byte_1800C4E0F, 1
0x1800221e9  jmp     loc_18002227B
0x1800221ee  mov     edx, ebx; uBytes
0x1800221f0  xor     ecx, ecx; uFlags
0x1800221f2  call    cs:__imp_LocalAlloc
0x1800221f8  mov     r12, rax
0x1800221fb  mov     [rsp+10D8h+var_1080], rax
0x180022200  test    rax, rax
0x180022203  jnz     loc_180022115
0x180022209  mov     edx, 8007000Eh; int
0x18002220e  mov     ecx, 3EC01A1h; unsigned int
0x180022213  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180022218  mov     eax, edi
0x18002221a  jmp     loc_18002218B
0x18002221f  call    ?UnicodeEnabled@@YA_NXZ; UnicodeEnabled(void)
0x180022224  test    al, al
0x180022226  jz      loc_18002239A
0x18002222c  shr     [rsp+10D8h+NumberOfBytesWritten], 1
0x180022230  jmp     loc_18002239A
0x180022235  mov     [rsp+10D8h+lpOverlapped], rdi; lpReserved
0x18002223a  lea     r9, [rsp+10D8h+NumberOfBytesWritten]; lpNumberOfCharsWritten
0x18002223f  mov     r8d, r13d; nNumberOfCharsToWrite
0x180022242  mov     rdx, rbx; lpBuffer
0x180022245  mov     rcx, r14; hConsoleOutput
0x180022248  call    cs:__imp_WriteConsoleW
0x18002224e  test    eax, eax
0x180022250  jnz     short loc_180022276
0x180022252  call    cs:__imp_GetLastError
0x180022258  cmp     eax, 1
0x18002225b  jz      short loc_180022272
0x18002225d  mov     r9d, 6; int
0x180022263  mov     r8d, eax; int
0x180022266  mov     edx, 39001A1h; unsigned int
0x18002226b  xor     ecx, ecx; unsigned __int16 *
0x18002226d  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180022272  or      r14, 0FFFFFFFFFFFFFFFFh
0x180022276  mov     [rsp+10D8h+var_1090], rbx
0x18002227b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002227f  jz      short loc_1800222A7
0x180022281  jmp     loc_18002239A
0x180022286  mov     r8d, 8000FFFFh; int
0x18002228c  mov     r9d, r8d; int
0x18002228f  mov     edx, 37F01A1h; unsigned int
0x180022294  xor     ecx, ecx; unsigned __int16 *
0x180022296  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002229b  mov     cs:byte_1800C4E0F, 1
0x1800222a2  mov     [rsp+10D8h+var_1090], rbx
0x1800222a7  mov     [rsp+10D8h+Buffer], edi
0x1800222ab  mov     ecx, 1; Ix
0x1800222b0  call    __acrt_iob_func
0x1800222b5  test    byte ptr [rax], 1
0x1800222b8  jz      short loc_1800222CD
0x1800222ba  mov     ecx, 1; Ix
0x1800222bf  call    __acrt_iob_func
0x1800222c4  mov     rcx, rax; Stream
0x1800222c7  call    cs:__imp_fflush
0x1800222cd  mov     ecx, 1; Ix
0x1800222d2  call    __acrt_iob_func
0x1800222d7  test    byte ptr [rax], 1
0x1800222da  jz      short loc_180022309
0x1800222dc  mov     ecx, 1; Ix
0x1800222e1  call    __acrt_iob_func
0x1800222e6  mov     rcx, rax; Stream
0x1800222e9  lea     rdx, asc_180063428; " "
0x1800222f0  call    cs:__imp_fprintf
0x1800222f6  mov     ecx, 1; Ix
0x1800222fb  call    __acrt_iob_func
0x180022300  mov     rcx, rax; Stream
  ... truncated ...
```
