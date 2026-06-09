# CommandLineData::SH_ReadCookieFromFile(int,ushort const *)

- ea: `0x1400582a0`
- end: `0x14005891f`
- name: `?SH_ReadCookieFromFile@CommandLineData@@AEAAPEBGHPEBG@Z`
- size: `1663`
- prototype: `const unsigned __int16 *__fastcall(CommandLineData *this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400574c0`

## callees

- `0x140008a78`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e158`
- `0x140042b94`
- `0x1400563e4`
- `0x140057260`
- `0x1400582a0`
- `0x1400a1c7c`
- `0x1400b3ef0`
- `0x140113390`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x14005851f`
- `KERNEL32!SetFilePointer` at `0x14005851f`
- `KERNEL32!LocalFree` at `0x140058795`
- `KERNEL32!LocalFree` at `0x1400587cd`
- `KERNEL32!LocalFree` at `0x1400588ea`
- `KERNEL32!LocalFree` at `0x140058795`
- `KERNEL32!LocalFree` at `0x1400587cd`
- `KERNEL32!LocalFree` at `0x1400588ea`
- `KERNEL32!ReadFile` at `0x1400586a9`
- `KERNEL32!ReadFile` at `0x1400586a9`
- `KERNEL32!GetFileSize` at `0x140058598`
- `KERNEL32!GetFileSize` at `0x140058598`
- `KERNEL32!CreateFileW` at `0x14005849f`
- `KERNEL32!CreateFileW` at `0x14005849f`
- `KERNEL32!DeleteFileW` at `0x140058777`
- `KERNEL32!DeleteFileW` at `0x140058777`
- `KERNEL32!CloseHandle` at `0x140058763`
- `KERNEL32!CloseHandle` at `0x140058763`
- `KERNEL32!GetLastError` at `0x1400584ae`
- `KERNEL32!GetLastError` at `0x14005852a`
- `KERNEL32!GetLastError` at `0x1400585a6`
- `KERNEL32!GetLastError` at `0x1400585c8`
- `KERNEL32!GetLastError` at `0x1400585f8`
- `KERNEL32!GetLastError` at `0x1400586b7`
- `KERNEL32!GetLastError` at `0x1400584ae`
- `KERNEL32!GetLastError` at `0x14005852a`
- `KERNEL32!GetLastError` at `0x1400585a6`
- `KERNEL32!GetLastError` at `0x1400585c8`
- `KERNEL32!GetLastError` at `0x1400585f8`
- `KERNEL32!GetLastError` at `0x1400586b7`

## string_xrefs

- `0x14005835e`: `CUT::UT_GetKnownLowILSafeTempDir failed`

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
0x1400582a0  mov     [rsp-8+arg_8], rbx
0x1400582a5  push    rbp
0x1400582a6  push    rsi
0x1400582a7  push    rdi
0x1400582a8  push    r12
0x1400582aa  push    r13
0x1400582ac  push    r14
0x1400582ae  push    r15
0x1400582b0  lea     rbp, [rsp-5A0h]
0x1400582b8  sub     rsp, 6A0h
0x1400582bf  mov     rax, cs:__security_cookie
0x1400582c6  xor     rax, rsp
0x1400582c9  mov     [rbp+5D0h+var_40], rax
0x1400582d0  xor     r15d, r15d
0x1400582d3  mov     [rsp+6D0h+var_690], edx
0x1400582d7  mov     r10, r8
0x1400582da  mov     [rsp+6D0h+NumberOfBytesRead], r15d
0x1400582df  mov     esi, edx
0x1400582e1  mov     [rsp+6D0h+FileSizeHigh], r15d
0x1400582e6  mov     r14d, 104h
0x1400582ec  mov     [rsp+6D0h+hMem], r15
0x1400582f1  mov     r9d, r14d; int
0x1400582f4  mov     [rsp+6D0h+FileName], r15w
0x1400582fa  mov     rdx, r10; unsigned __int16 *
0x1400582fd  lea     r8, [rbp+5D0h+var_460]; unsigned __int16 *
0x140058304  mov     rdi, rcx
0x140058307  mov     r13d, r15d
0x14005830a  call    ?SHGetCmdLineString@CommandLineData@@AEAAPEBGPEBGPEAGH@Z; CommandLineData::SHGetCmdLineString(ushort const *,ushort *,int)
0x14005830f  lea     rdx, [rbp+5D0h+var_250]; unsigned __int16 *
0x140058316  mov     [rsp+6D0h+var_678], rax
0x14005831b  call    ?UT_GetKnownLowILSafeTempDir@CClientUtilsWin32@@SAJKPEAG@Z; CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(ulong,ushort *)
0x140058320  lea     r12d, [r15+1]
0x140058324  mov     ebx, eax
0x140058326  test    eax, eax
0x140058328  jns     short loc_14005838D
0x14005832a  mov     rax, cs:WPP_GLOBAL_Control
0x140058331  lea     r14, WPP_GLOBAL_Control
0x140058338  cmp     rax, r14
0x14005833b  jz      loc_140058769
0x140058341  test    byte ptr [rax+1Ch], 8
0x140058345  jz      loc_140058769
0x14005834b  cmp     byte ptr [rax+19h], 2
0x14005834f  jb      loc_140058769
0x140058355  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005835a  lea     edx, [r15+0Bh]
0x14005835e  lea     rcx, aCutUtGetknownl; "CUT::UT_GetKnownLowILSafeTempDir failed"
0x140058365  mov     [rsp+6D0h+dwFlagsAndAttributes], ebx
0x140058369  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140058370  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rcx
0x140058375  mov     r9d, eax
0x140058378  mov     rcx, cs:WPP_GLOBAL_Control
0x14005837f  mov     rcx, [rcx+10h]
0x140058383  call    WPP_SF_DsD
0x140058388  jmp     loc_140058769
0x14005838d  lea     rcx, aAuthcookie; "AUTHCOOKIE"
0x140058394  test    esi, esi
0x140058396  lea     rax, aOtpcookie; "OTPCOOKIE"
0x14005839d  mov     rdx, r14; unsigned __int64
0x1400583a0  cmovz   rax, rcx
0x1400583a4  lea     r9, [rbp+5D0h+var_250]
0x1400583ab  lea     rcx, [rbp+5D0h+var_460]
0x1400583b2  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rcx
0x1400583b7  lea     r8, aSSSTxt; "%s\\%s#%s.txt"
0x1400583be  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x1400583c3  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rax
0x1400583c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400583cd  mov     ebx, eax
0x1400583cf  test    eax, eax
0x1400583d1  jns     short loc_140058414
0x1400583d3  mov     rax, cs:WPP_GLOBAL_Control
0x1400583da  lea     r14, WPP_GLOBAL_Control
0x1400583e1  cmp     rax, r14
0x1400583e4  jz      loc_140058769
0x1400583ea  test    byte ptr [rax+1Ch], 8
0x1400583ee  jz      loc_140058769
0x1400583f4  cmp     byte ptr [rax+19h], 2
0x1400583f8  jb      loc_140058769
0x1400583fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058403  mov     edx, 0Ch
0x140058408  lea     rcx, aStringcchprint_0; "StringCchPrintf failed"
0x14005840f  jmp     loc_140058365
0x140058414  mov     rax, cs:WPP_GLOBAL_Control
0x14005841b  lea     r14, WPP_GLOBAL_Control
0x140058422  cmp     rax, r14
0x140058425  jz      short loc_14005847A
0x140058427  test    [rax+1Ch], r12b
0x14005842b  jz      short loc_14005847A
0x14005842d  cmp     byte ptr [rax+19h], 4
0x140058431  jb      short loc_14005847A
0x140058433  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058438  mov     r9d, eax
0x14005843b  lea     rcx, aAuth; "Auth"
0x140058442  test    esi, esi
0x140058444  lea     rax, aOtp; "OTP"
0x14005844b  mov     edx, 0Dh
0x140058450  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140058457  cmovz   rax, rcx
0x14005845b  lea     rcx, [rsp+6D0h+FileName]
0x140058460  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rcx; __int64
0x140058465  mov     rcx, cs:WPP_GLOBAL_Control
0x14005846c  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rax; __int64
0x140058471  mov     rcx, [rcx+10h]; LoggerHandle
0x140058475  call    WPP_SF_DSS
0x14005847a  mov     [rsp+6D0h+hTemplateFile], r15; hTemplateFile
0x14005847f  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x140058484  mov     [rsp+6D0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x14005848c  xor     r9d, r9d; lpSecurityAttributes
0x14005848f  xor     r8d, r8d; dwShareMode
0x140058492  mov     [rsp+6D0h+dwCreationDisposition], 3; dwCreationDisposition
0x14005849a  mov     edx, 80000000h; dwDesiredAccess
0x14005849f  call    cs:__imp_CreateFileW
0x1400584a5  mov     r15, rax
0x1400584a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400584ac  jnz     short loc_140058514
0x1400584ae  call    cs:__imp_GetLastError
0x1400584b4  mov     ebx, eax
0x1400584b6  test    eax, eax
0x1400584b8  jle     short loc_1400584C3
0x1400584ba  movzx   ebx, ax
0x1400584bd  or      ebx, 80070000h
0x1400584c3  mov     rax, cs:WPP_GLOBAL_Control
0x1400584ca  cmp     rax, r14
0x1400584cd  jz      loc_140058769
0x1400584d3  test    [rax+1Ch], r12b
0x1400584d7  jz      loc_140058769
0x1400584dd  cmp     byte ptr [rax+19h], 2
0x1400584e1  jb      loc_140058769
0x1400584e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400584ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400584f3  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x1400584fa  mov     edx, 0Eh
0x1400584ff  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x140058503  mov     r9d, eax
0x140058506  mov     rcx, [rcx+10h]
0x14005850a  call    WPP_SF_Dd
0x14005850f  jmp     loc_140058769
0x140058514  xor     r9d, r9d; dwMoveMethod
0x140058517  xor     r8d, r8d; lpDistanceToMoveHigh
0x14005851a  xor     edx, edx; lDistanceToMove
0x14005851c  mov     rcx, r15; hFile
0x14005851f  call    cs:__imp_SetFilePointer
0x140058525  cmp     eax, 0FFFFFFFFh
0x140058528  jnz     short loc_140058590
0x14005852a  call    cs:__imp_GetLastError
0x140058530  mov     ebx, eax
0x140058532  test    eax, eax
0x140058534  jle     short loc_14005853F
0x140058536  movzx   ebx, ax
0x140058539  or      ebx, 80070000h
0x14005853f  mov     rax, cs:WPP_GLOBAL_Control
0x140058546  cmp     rax, r14
0x140058549  jz      loc_140058760
0x14005854f  test    [rax+1Ch], r12b
0x140058553  jz      loc_140058760
0x140058559  cmp     byte ptr [rax+19h], 2
0x14005855d  jb      loc_140058760
0x140058563  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058568  mov     rcx, cs:WPP_GLOBAL_Control
0x14005856f  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140058576  mov     edx, 0Fh
0x14005857b  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x14005857f  mov     r9d, eax
0x140058582  mov     rcx, [rcx+10h]
0x140058586  call    WPP_SF_Dd
0x14005858b  jmp     loc_140058760
0x140058590  lea     rdx, [rsp+6D0h+FileSizeHigh]; lpFileSizeHigh
0x140058595  mov     rcx, r15; hFile
0x140058598  call    cs:__imp_GetFileSize
0x14005859e  mov     r13d, eax
0x1400585a1  cmp     eax, 0FFFFFFFFh
0x1400585a4  jnz     short loc_140058616
0x1400585a6  call    cs:__imp_GetLastError
0x1400585ac  test    eax, eax
0x1400585ae  jz      short loc_140058616
0x1400585b0  mov     rax, cs:WPP_GLOBAL_Control
0x1400585b7  cmp     rax, r14
0x1400585ba  jz      short loc_1400585F8
0x1400585bc  test    [rax+1Ch], r12b
0x1400585c0  jz      short loc_1400585F8
0x1400585c2  cmp     byte ptr [rax+19h], 2
0x1400585c6  jb      short loc_1400585F8
0x1400585c8  call    cs:__imp_GetLastError
0x1400585ce  mov     ebx, eax
0x1400585d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400585d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400585dc  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x1400585e3  mov     edx, 10h
0x1400585e8  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x1400585ec  mov     r9d, eax
0x1400585ef  mov     rcx, [rcx+10h]
0x1400585f3  call    WPP_SF_Dd
0x1400585f8  call    cs:__imp_GetLastError
0x1400585fe  mov     ebx, eax
0x140058600  test    eax, eax
0x140058602  jle     loc_140058760
0x140058608  movzx   ebx, ax
0x14005860b  or      ebx, 80070000h
0x140058611  jmp     loc_140058760
0x140058616  mov     esi, [rsp+6D0h+FileSizeHigh]
0x14005861a  test    esi, esi
0x14005861c  jnz     loc_140058712
0x140058622  cmp     r13d, 7FFFFFFFh
0x140058629  ja      loc_140058712
0x14005862f  mov     rcx, r13; size
0x140058632  call    MIDL_user_allocate
0x140058637  mov     rsi, rax
0x14005863a  mov     [rsp+6D0h+hMem], rax
0x14005863f  xor     eax, eax
0x140058641  test    rsi, rsi
0x140058644  jnz     short loc_140058696
0x140058646  mov     rcx, cs:WPP_GLOBAL_Control
0x14005864d  cmp     rcx, r14
0x140058650  jz      short loc_14005868C
0x140058652  test    byte ptr [rcx+1Ch], 8
0x140058656  jz      short loc_14005868C
0x140058658  cmp     byte ptr [rcx+19h], 2
0x14005865c  jb      short loc_14005868C
0x14005865e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058663  lea     rcx, aFilecontents; "fileContents"
0x14005866a  mov     r9d, eax
0x14005866d  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rcx
0x140058672  lea     edx, [rsi+12h]
0x140058675  mov     rcx, cs:WPP_GLOBAL_Control
0x14005867c  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140058683  mov     rcx, [rcx+10h]
0x140058687  call    WPP_SF_Ds
0x14005868c  mov     ebx, 8007000Eh
0x140058691  jmp     loc_14005875C
0x140058696  lea     r9, [rsp+6D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14005869b  mov     qword ptr [rsp+6D0h+dwCreationDisposition], rax; lpOverlapped
0x1400586a0  mov     r8d, r13d; nNumberOfBytesToRead
0x1400586a3  mov     rdx, rsi; lpBuffer
0x1400586a6  mov     rcx, r15; hFile
0x1400586a9  call    cs:__imp_ReadFile
0x1400586af  test    eax, eax
0x1400586b1  jnz     loc_14005875C
0x1400586b7  call    cs:__imp_GetLastError
0x1400586bd  mov     ebx, eax
0x1400586bf  test    eax, eax
0x1400586c1  jle     short loc_1400586CC
0x1400586c3  movzx   ebx, ax
0x1400586c6  or      ebx, 80070000h
0x1400586cc  mov     rax, cs:WPP_GLOBAL_Control
0x1400586d3  cmp     rax, r14
0x1400586d6  jz      loc_14005875C
0x1400586dc  test    [rax+1Ch], r12b
0x1400586e0  jz      short loc_14005875C
0x1400586e2  cmp     byte ptr [rax+19h], 2
0x1400586e6  jb      short loc_14005875C
0x1400586e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400586ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400586f4  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x1400586fb  mov     edx, 13h
0x140058700  mov     [rsp+6D0h+dwCreationDisposition], ebx
0x140058704  mov     r9d, eax
0x140058707  mov     rcx, [rcx+10h]
0x14005870b  call    WPP_SF_Dd
0x140058710  jmp     short loc_14005875C
0x140058712  mov     rax, cs:WPP_GLOBAL_Control
0x140058719  cmp     rax, r14
0x14005871c  jz      short loc_140058757
0x14005871e  test    [rax+1Ch], r12b
0x140058722  jz      short loc_140058757
0x140058724  cmp     byte ptr [rax+19h], 2
0x140058728  jb      short loc_140058757
0x14005872a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005872f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058736  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x14005873d  mov     edx, 11h
0x140058742  mov     [rsp+6D0h+dwFlagsAndAttributes], r13d
0x140058747  mov     r9d, eax
0x14005874a  mov     [rsp+6D0h+dwCreationDisposition], esi
0x14005874e  mov     rcx, [rcx+10h]
0x140058752  call    WPP_SF_DLD
0x140058757  mov     ebx, 80004005h
0x14005875c  mov     esi, [rsp+6D0h+var_690]
0x140058760  mov     rcx, r15; hObject
0x140058763  call    cs:__imp_CloseHandle
0x140058769  xor     eax, eax
0x14005876b  cmp     [rsp+6D0h+FileName], ax
0x140058770  jz      short loc_14005877F
0x140058772  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x140058777  call    cs:__imp_DeleteFileW
0x14005877d  xor     eax, eax
0x14005877f  test    esi, esi
0x140058781  jz      short loc_1400587B4
0x140058783  mov     rcx, [rdi+1280h]; hMem
0x14005878a  mov     [rdi+1288h], eax
0x140058790  test    rcx, rcx
0x140058793  jz      short loc_1400587A4
0x140058795  call    cs:__imp_LocalFree
0x14005879b  xor     eax, eax
0x14005879d  mov     [rdi+1280h], rax
0x1400587a4  lea     r15, [rdi+1298h]
0x1400587ab  lea     rsi, [rdi+1290h]
0x1400587b2  jmp     short loc_1400587D8
0x1400587b4  lea     rsi, [rdi+1290h]
0x1400587bb  mov     rcx, [rsi]; hMem
0x1400587be  lea     r15, [rdi+1298h]
0x1400587c5  mov     [r15], eax
  ... truncated ...
```
