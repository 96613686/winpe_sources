# CommandLineData::SH_ReadCookieFromFile(int,ushort const *)

- ea: `0x140056130`
- end: `0x1400567af`
- name: `?SH_ReadCookieFromFile@CommandLineData@@AEAAPEBGHPEBG@Z`
- size: `1663`
- prototype: `const unsigned __int16 *(CommandLineData *__hidden this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140055350`

## callees

- `0x140008a78`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e158`
- `0x140040a2c`
- `0x140054274`
- `0x1400550f0`
- `0x140056130`
- `0x14009fb0c`
- `0x1400b1d80`
- `0x140111220`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1400563af`
- `KERNEL32!SetFilePointer` at `0x1400563af`
- `KERNEL32!LocalFree` at `0x140056625`
- `KERNEL32!LocalFree` at `0x14005665d`
- `KERNEL32!LocalFree` at `0x14005677a`
- `KERNEL32!LocalFree` at `0x140056625`
- `KERNEL32!LocalFree` at `0x14005665d`
- `KERNEL32!LocalFree` at `0x14005677a`
- `KERNEL32!ReadFile` at `0x140056539`
- `KERNEL32!ReadFile` at `0x140056539`
- `KERNEL32!GetFileSize` at `0x140056428`
- `KERNEL32!GetFileSize` at `0x140056428`
- `KERNEL32!CreateFileW` at `0x14005632f`
- `KERNEL32!CreateFileW` at `0x14005632f`
- `KERNEL32!DeleteFileW` at `0x140056607`
- `KERNEL32!DeleteFileW` at `0x140056607`
- `KERNEL32!CloseHandle` at `0x1400565f3`
- `KERNEL32!CloseHandle` at `0x1400565f3`
- `KERNEL32!GetLastError` at `0x14005633e`
- `KERNEL32!GetLastError` at `0x1400563ba`
- `KERNEL32!GetLastError` at `0x140056436`
- `KERNEL32!GetLastError` at `0x140056458`
- `KERNEL32!GetLastError` at `0x140056488`
- `KERNEL32!GetLastError` at `0x140056547`
- `KERNEL32!GetLastError` at `0x14005633e`
- `KERNEL32!GetLastError` at `0x1400563ba`
- `KERNEL32!GetLastError` at `0x140056436`
- `KERNEL32!GetLastError` at `0x140056458`
- `KERNEL32!GetLastError` at `0x140056488`
- `KERNEL32!GetLastError` at `0x140056547`

## string_xrefs

- `0x1400561ee`: `CUT::UT_GetKnownLowILSafeTempDir failed`

## pseudocode

```c
const unsigned __int16 *__fastcall CommandLineData::SH_ReadCookieFromFile(
        CommandLineData *this,
        int a2,
        const unsigned __int16 *a3)
{
  int v3; // esi
  size_t v5; // r13
  unsigned int v6; // ecx
  int v7; // r12d
  signed int KnownLowILSafeTempDir; // ebx
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  const wchar_t *v12; // rax
  const wchar_t *v13; // rax
  HANDLE FileW; // rax
  void *v15; // r15
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v18; // eax
  unsigned int v19; // eax
  DWORD FileSize; // eax
  DWORD v21; // ebx
  unsigned int v22; // eax
  signed int v23; // eax
  DWORD v24; // esi
  void *v25; // rsi
  unsigned int v26; // eax
  signed int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  void *v30; // rcx
  unsigned int *v31; // r15
  unsigned __int16 **v32; // rsi
  unsigned int v33; // eax
  unsigned int v34; // eax
  DWORD FileSizeHigh; // [rsp+44h] [rbp-BCh] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h]
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v40; // [rsp+58h] [rbp-A8h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v42[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v43[264]; // [rsp+480h] [rbp+380h] BYREF

  NumberOfBytesRead = 0;
  v3 = a2;
  FileSizeHigh = 0;
  hMem = 0;
  FileName[0] = 0;
  LODWORD(v5) = 0;
  v40 = CommandLineData::SHGetCmdLineString(this, a3, v42, 260);
  v7 = 1;
  KnownLowILSafeTempDir = CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(v6, v43);
  if ( KnownLowILSafeTempDir >= 0 )
  {
    v12 = L"OTPCOOKIE";
    if ( !v3 )
      v12 = L"AUTHCOOKIE";
    KnownLowILSafeTempDir = StringCchPrintfW(FileName, 0x104u, L"%s\\%s#%s.txt", v43, v12, v42);
    if ( KnownLowILSafeTempDir >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = L"OTP";
        if ( !v3 )
          v13 = (const wchar_t *)L"Auth";
        WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v13, (__int64)FileName);
      }
      FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x8000000u, 0);
      v15 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        KnownLowILSafeTempDir = LastError;
        if ( LastError > 0 )
          KnownLowILSafeTempDir = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
            CurrentThreadActivityIdPrefix,
            KnownLowILSafeTempDir);
        }
      }
      else
      {
        if ( SetFilePointer(FileW, 0, 0, 0) == -1 )
        {
          v18 = GetLastError();
          KnownLowILSafeTempDir = v18;
          if ( v18 > 0 )
            KnownLowILSafeTempDir = (unsigned __int16)v18 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
              v19,
              KnownLowILSafeTempDir);
          }
        }
        else
        {
          FileSize = GetFileSize(v15, &FileSizeHigh);
          v5 = FileSize;
          if ( FileSize == -1 && GetLastError() )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v21 = GetLastError();
              v22 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
                v22,
                v21);
            }
            v23 = GetLastError();
            KnownLowILSafeTempDir = v23;
            if ( v23 > 0 )
              KnownLowILSafeTempDir = (unsigned __int16)v23 | 0x80070000;
          }
          else
          {
            v24 = FileSizeHigh;
            if ( FileSizeHigh || (unsigned int)v5 > 0x7FFFFFFF )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v29 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DLD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  17,
                  WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
                  v29,
                  v24,
                  v5);
              }
              KnownLowILSafeTempDir = -2147467259;
            }
            else
            {
              v25 = MIDL_user_allocate(v5);
              hMem = v25;
              if ( v25 )
              {
                if ( !ReadFile(v15, v25, v5, &NumberOfBytesRead, 0) )
                {
                  v27 = GetLastError();
                  KnownLowILSafeTempDir = v27;
                  if ( v27 > 0 )
                    KnownLowILSafeTempDir = (unsigned __int16)v27 | 0x80070000;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      19,
                      WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
                      v28,
                      KnownLowILSafeTempDir);
                  }
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v26 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    18,
                    (unsigned int)WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
                    v26,
                    (__int64)"fileContents");
                }
                KnownLowILSafeTempDir = -2147024882;
              }
            }
            v3 = a2;
          }
        }
        CloseHandle(v15);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 12;
      v11 = "StringCchPrintf failed";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 11;
    v11 = "CUT::UT_GetKnownLowILSafeTempDir failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
      v9,
      (__int64)v11,
      KnownLowILSafeTempDir);
  }
  if ( FileName[0] )
    DeleteFileW(FileName);
  if ( v3 )
  {
    v30 = (void *)*((_QWORD *)this + 592);
    *((_DWORD *)this + 1186) = 0;
    if ( v30 )
    {
      LocalFree(v30);
      *((_QWORD *)this + 592) = 0;
    }
    v31 = (unsigned int *)((char *)this + 4760);
    v32 = (unsigned __int16 **)((char *)this + 4752);
  }
  else
  {
    v32 = (unsigned __int16 **)((char *)this + 4752);
    v30 = (void *)*((_QWORD *)this + 594);
    v31 = (unsigned int *)((char *)this + 4760);
    *((_DWORD *)this + 1190) = 0;
    if ( v30 )
    {
      LocalFree(v30);
      *v32 = 0;
    }
  }
  if ( KnownLowILSafeTempDir < 0 )
  {
    if ( a2 )
    {
      *((_DWORD *)this + 1182) = 0;
      *((_QWORD *)this + 592) = 0;
      *((_DWORD *)this + 1186) = 0;
      goto LABEL_90;
    }
    goto LABEL_89;
  }
  if ( a2 )
  {
    if ( CommandLineData::ConvertMultiByteToWideChar(
           (CommandLineData *)v30,
           (unsigned __int8 *)hMem,
           v5,
           (unsigned __int16 **)this + 592,
           (unsigned int *)this + 1186) < 0 )
    {
      *((_QWORD *)this + 592) = 0;
      v7 = 0;
      *((_DWORD *)this + 1186) = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids, v33);
    }
    *((_DWORD *)this + 1182) = v7;
    goto LABEL_90;
  }
  if ( CommandLineData::ConvertMultiByteToWideChar((CommandLineData *)v30, (unsigned __int8 *)hMem, v5, v32, v31) < 0 )
  {
LABEL_89:
    *((_DWORD *)this + 1187) = 0;
    *v32 = 0;
    *v31 = 0;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v34 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids, v34);
  }
  *((_DWORD *)this + 1187) = 1;
LABEL_90:
  if ( hMem )
    LocalFree(hMem);
  return v40;
}

```

## disassembly

```asm
0x140056130  mov     [rsp-8+arg_8], rbx
0x140056135  push    rbp
0x140056136  push    rsi
0x140056137  push    rdi
0x140056138  push    r12
0x14005613a  push    r13
0x14005613c  push    r14
0x14005613e  push    r15
0x140056140  lea     rbp, [rsp-5A0h]
0x140056148  sub     rsp, 6A0h
0x14005614f  mov     rax, cs:__security_cookie
0x140056156  xor     rax, rsp
0x140056159  mov     [rbp+5D0h+var_40], rax
0x140056160  xor     r15d, r15d
0x140056163  mov     [rsp+6D0h+var_690], edx
0x140056167  mov     r10, r8
0x14005616a  mov     [rsp+6D0h+NumberOfBytesRead], r15d
0x14005616f  mov     esi, edx
0x140056171  mov     [rsp+6D0h+FileSizeHigh], r15d
0x140056176  mov     r14d, 104h
0x14005617c  mov     [rsp+6D0h+hMem], r15
0x140056181  mov     r9d, r14d; int
0x140056184  mov     [rsp+6D0h+FileName], r15w
0x14005618a  mov     rdx, r10; unsigned __int16 *
0x14005618d  lea     r8, [rbp+5D0h+var_460]; unsigned __int16 *
0x140056194  mov     rdi, rcx
0x140056197  mov     r13d, r15d
0x14005619a  call    ?SHGetCmdLineString@CommandLineData@@AEAAPEBGPEBGPEAGH@Z; CommandLineData::SHGetCmdLineString(ushort const *,ushort *,int)
0x14005619f  lea     rdx, [rbp+5D0h+var_250]; unsigned __int16 *
0x1400561a6  mov     [rsp+6D0h+var_678], rax
0x1400561ab  call    ?UT_GetKnownLowILSafeTempDir@CClientUtilsWin32@@SAJKPEAG@Z; CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(ulong,ushort *)
0x1400561b0  lea     r12d, [r15+1]
0x1400561b4  mov     ebx, eax
0x1400561b6  test    eax, eax
0x1400561b8  jns     short loc_14005621D
0x1400561ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400561c1  lea     r14, WPP_GLOBAL_Control
0x1400561c8  cmp     rax, r14
0x1400561cb  jz      loc_1400565F9
0x1400561d1  test    byte ptr [rax+1Ch], 8
0x1400561d5  jz      loc_1400565F9
0x1400561db  cmp     byte ptr [rax+19h], 2
0x1400561df  jb      loc_1400565F9
0x1400561e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400561ea  lea     edx, [r15+0Bh]
0x1400561ee  lea     rcx, aCutUtGetknownl; "CUT::UT_GetKnownLowILSafeTempDir failed"
0x1400561f5  mov     [rsp+6D0h+dwFlagsAndAttributes], ebx
0x1400561f9  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140056200  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rcx
0x140056205  mov     r9d, eax
0x140056208  mov     rcx, cs:WPP_GLOBAL_Control
0x14005620f  mov     rcx, [rcx+10h]
0x140056213  call    WPP_SF_DsD
0x140056218  jmp     loc_1400565F9
0x14005621d  lea     rcx, aAuthcookie; "AUTHCOOKIE"
0x140056224  test    esi, esi
0x140056226  lea     rax, aOtpcookie; "OTPCOOKIE"
0x14005622d  mov     rdx, r14; unsigned __int64
0x140056230  cmovz   rax, rcx
0x140056234  lea     r9, [rbp+5D0h+var_250]
0x14005623b  lea     rcx, [rbp+5D0h+var_460]
0x140056242  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rcx
0x140056247  lea     r8, aSSSTxt; "%s\\%s#%s.txt"
0x14005624e  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x140056253  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rax
0x140056258  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14005625d  mov     ebx, eax
0x14005625f  test    eax, eax
0x140056261  jns     short loc_1400562A4
0x140056263  mov     rax, cs:WPP_GLOBAL_Control
0x14005626a  lea     r14, WPP_GLOBAL_Control
0x140056271  cmp     rax, r14
0x140056274  jz      loc_1400565F9
0x14005627a  test    byte ptr [rax+1Ch], 8
0x14005627e  jz      loc_1400565F9
0x140056284  cmp     byte ptr [rax+19h], 2
0x140056288  jb      loc_1400565F9
0x14005628e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056293  mov     edx, 0Ch
0x140056298  lea     rcx, aStringcchprint_0; "StringCchPrintf failed"
0x14005629f  jmp     loc_1400561F5
0x1400562a4  mov     rax, cs:WPP_GLOBAL_Control
0x1400562ab  lea     r14, WPP_GLOBAL_Control
0x1400562b2  cmp     rax, r14
0x1400562b5  jz      short loc_14005630A
0x1400562b7  test    [rax+1Ch], r12b
0x1400562bb  jz      short loc_14005630A
0x1400562bd  cmp     byte ptr [rax+19h], 4
0x1400562c1  jb      short loc_14005630A
0x1400562c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400562c8  mov     r9d, eax
0x1400562cb  lea     rcx, aAuth; "Auth"
0x1400562d2  test    esi, esi
0x1400562d4  lea     rax, aOtp; "OTP"
0x1400562db  mov     edx, 0Dh
0x1400562e0  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x1400562e7  cmovz   rax, rcx
0x1400562eb  lea     rcx, [rsp+6D0h+FileName]
0x1400562f0  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rcx; __int64
0x1400562f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400562fc  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rax; __int64
0x140056301  mov     rcx, [rcx+10h]; LoggerHandle
0x140056305  call    WPP_SF_DSS
0x14005630a  mov     [rsp+6D0h+hTemplateFile], r15; hTemplateFile
0x14005630f  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x140056314  mov     [rsp+6D0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x14005631c  xor     r9d, r9d; lpSecurityAttributes
0x14005631f  xor     r8d, r8d; dwShareMode
0x140056322  mov     [rsp+6D0h+dwCreationDisposition], 3; dwCreationDisposition
0x14005632a  mov     edx, 80000000h; dwDesiredAccess
0x14005632f  call    cs:__imp_CreateFileW
0x140056335  mov     r15, rax
0x140056338  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005633c  jnz     short loc_1400563A4
0x14005633e  call    cs:__imp_GetLastError
0x140056344  mov     ebx, eax
0x140056346  test    eax, eax
0x140056348  jle     short loc_140056353
0x14005634a  movzx   ebx, ax
0x14005634d  or      ebx, 80070000h
0x140056353  mov     rax, cs:WPP_GLOBAL_Control
0x14005635a  cmp     rax, r14
0x14005635d  jz      loc_1400565F9
0x140056363  test    [rax+1Ch], r12b
0x140056367  jz      loc_1400565F9
0x14005636d  cmp     byte ptr [rax+19h], 2
0x140056371  jb      loc_1400565F9
0x140056377  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005637c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056383  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x14005638a  mov     edx, 0Eh
0x14005638f  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x140056393  mov     r9d, eax
0x140056396  mov     rcx, [rcx+10h]
0x14005639a  call    WPP_SF_Dd
0x14005639f  jmp     loc_1400565F9
0x1400563a4  xor     r9d, r9d; dwMoveMethod
0x1400563a7  xor     r8d, r8d; lpDistanceToMoveHigh
0x1400563aa  xor     edx, edx; lDistanceToMove
0x1400563ac  mov     rcx, r15; hFile
0x1400563af  call    cs:__imp_SetFilePointer
0x1400563b5  cmp     eax, 0FFFFFFFFh
0x1400563b8  jnz     short loc_140056420
0x1400563ba  call    cs:__imp_GetLastError
0x1400563c0  mov     ebx, eax
0x1400563c2  test    eax, eax
0x1400563c4  jle     short loc_1400563CF
0x1400563c6  movzx   ebx, ax
0x1400563c9  or      ebx, 80070000h
0x1400563cf  mov     rax, cs:WPP_GLOBAL_Control
0x1400563d6  cmp     rax, r14
0x1400563d9  jz      loc_1400565F0
0x1400563df  test    [rax+1Ch], r12b
0x1400563e3  jz      loc_1400565F0
0x1400563e9  cmp     byte ptr [rax+19h], 2
0x1400563ed  jb      loc_1400565F0
0x1400563f3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400563f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400563ff  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140056406  mov     edx, 0Fh
0x14005640b  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x14005640f  mov     r9d, eax
0x140056412  mov     rcx, [rcx+10h]
0x140056416  call    WPP_SF_Dd
0x14005641b  jmp     loc_1400565F0
0x140056420  lea     rdx, [rsp+6D0h+FileSizeHigh]; lpFileSizeHigh
0x140056425  mov     rcx, r15; hFile
0x140056428  call    cs:__imp_GetFileSize
0x14005642e  mov     r13d, eax
0x140056431  cmp     eax, 0FFFFFFFFh
0x140056434  jnz     short loc_1400564A6
0x140056436  call    cs:__imp_GetLastError
0x14005643c  test    eax, eax
0x14005643e  jz      short loc_1400564A6
0x140056440  mov     rax, cs:WPP_GLOBAL_Control
0x140056447  cmp     rax, r14
0x14005644a  jz      short loc_140056488
0x14005644c  test    [rax+1Ch], r12b
0x140056450  jz      short loc_140056488
0x140056452  cmp     byte ptr [rax+19h], 2
0x140056456  jb      short loc_140056488
0x140056458  call    cs:__imp_GetLastError
0x14005645e  mov     ebx, eax
0x140056460  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056465  mov     rcx, cs:WPP_GLOBAL_Control
0x14005646c  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140056473  mov     edx, 10h
0x140056478  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x14005647c  mov     r9d, eax
0x14005647f  mov     rcx, [rcx+10h]
0x140056483  call    WPP_SF_Dd
0x140056488  call    cs:__imp_GetLastError
0x14005648e  mov     ebx, eax
0x140056490  test    eax, eax
0x140056492  jle     loc_1400565F0
0x140056498  movzx   ebx, ax
0x14005649b  or      ebx, 80070000h
0x1400564a1  jmp     loc_1400565F0
0x1400564a6  mov     esi, [rsp+6D0h+FileSizeHigh]
0x1400564aa  test    esi, esi
0x1400564ac  jnz     loc_1400565A2
0x1400564b2  cmp     r13d, 7FFFFFFFh
0x1400564b9  ja      loc_1400565A2
0x1400564bf  mov     rcx, r13; size
0x1400564c2  call    MIDL_user_allocate
0x1400564c7  mov     rsi, rax
0x1400564ca  mov     [rsp+6D0h+hMem], rax
0x1400564cf  xor     eax, eax
0x1400564d1  test    rsi, rsi
0x1400564d4  jnz     short loc_140056526
0x1400564d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400564dd  cmp     rcx, r14
0x1400564e0  jz      short loc_14005651C
0x1400564e2  test    byte ptr [rcx+1Ch], 8
0x1400564e6  jz      short loc_14005651C
0x1400564e8  cmp     byte ptr [rcx+19h], 2
0x1400564ec  jb      short loc_14005651C
0x1400564ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400564f3  lea     rcx, aFilecontents; "fileContents"
0x1400564fa  mov     r9d, eax
0x1400564fd  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rcx
0x140056502  lea     edx, [rsi+12h]
0x140056505  mov     rcx, cs:WPP_GLOBAL_Control
0x14005650c  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140056513  mov     rcx, [rcx+10h]
0x140056517  call    WPP_SF_Ds
0x14005651c  mov     ebx, 8007000Eh
0x140056521  jmp     loc_1400565EC
0x140056526  lea     r9, [rsp+6D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14005652b  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rax; lpOverlapped
0x140056530  mov     r8d, r13d; nNumberOfBytesToRead
0x140056533  mov     rdx, rsi; lpBuffer
0x140056536  mov     rcx, r15; hFile
0x140056539  call    cs:__imp_ReadFile
0x14005653f  test    eax, eax
0x140056541  jnz     loc_1400565EC
0x140056547  call    cs:__imp_GetLastError
0x14005654d  mov     ebx, eax
0x14005654f  test    eax, eax
0x140056551  jle     short loc_14005655C
0x140056553  movzx   ebx, ax
0x140056556  or      ebx, 80070000h
0x14005655c  mov     rax, cs:WPP_GLOBAL_Control
0x140056563  cmp     rax, r14
0x140056566  jz      loc_1400565EC
0x14005656c  test    [rax+1Ch], r12b
0x140056570  jz      short loc_1400565EC
0x140056572  cmp     byte ptr [rax+19h], 2
0x140056576  jb      short loc_1400565EC
0x140056578  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005657d  mov     rcx, cs:WPP_GLOBAL_Control
0x140056584  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x14005658b  mov     edx, 13h
0x140056590  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x140056594  mov     r9d, eax
0x140056597  mov     rcx, [rcx+10h]
0x14005659b  call    WPP_SF_Dd
0x1400565a0  jmp     short loc_1400565EC
0x1400565a2  mov     rax, cs:WPP_GLOBAL_Control
0x1400565a9  cmp     rax, r14
0x1400565ac  jz      short loc_1400565E7
0x1400565ae  test    [rax+1Ch], r12b
0x1400565b2  jz      short loc_1400565E7
0x1400565b4  cmp     byte ptr [rax+19h], 2
0x1400565b8  jb      short loc_1400565E7
0x1400565ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400565bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400565c6  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x1400565cd  mov     edx, 11h
0x1400565d2  mov     [rsp+6D0h+dwFlagsAndAttributes], r13d
0x1400565d7  mov     r9d, eax
0x1400565da  mov     [rsp+6D0h+dwCreationDisposition], esi
0x1400565de  mov     rcx, [rcx+10h]
0x1400565e2  call    WPP_SF_DLD
0x1400565e7  mov     ebx, 80004005h
0x1400565ec  mov     esi, [rsp+6D0h+var_690]
0x1400565f0  mov     rcx, r15; hObject
0x1400565f3  call    cs:__imp_CloseHandle
0x1400565f9  xor     eax, eax
0x1400565fb  cmp     [rsp+6D0h+FileName], ax
0x140056600  jz      short loc_14005660F
0x140056602  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x140056607  call    cs:__imp_DeleteFileW
0x14005660d  xor     eax, eax
0x14005660f  test    esi, esi
0x140056611  jz      short loc_140056644
0x140056613  mov     rcx, [rdi+1280h]; hMem
0x14005661a  mov     [rdi+1288h], eax
0x140056620  test    rcx, rcx
0x140056623  jz      short loc_140056634
0x140056625  call    cs:__imp_LocalFree
0x14005662b  xor     eax, eax
0x14005662d  mov     [rdi+1280h], rax
0x140056634  lea     r15, [rdi+1298h]
0x14005663b  lea     rsi, [rdi+1290h]
0x140056642  jmp     short loc_140056668
0x140056644  lea     rsi, [rdi+1290h]
0x14005664b  mov     rcx, [rsi]; hMem
0x14005664e  lea     r15, [rdi+1298h]
0x140056655  mov     [r15], eax
  ... truncated ...
```
