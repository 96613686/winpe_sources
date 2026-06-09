# CTscComHelper::WriteCookieToFile(int,uchar *,ulong,uint *)

- ea: `0x1804aad5c`
- end: `0x1804ab105`
- name: `?WriteCookieToFile@CTscComHelper@@CAJHPEAEKPEAI@Z`
- size: `937`
- prototype: `static int(int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1804aa430`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180085e04`
- `0x1800e9b1c`
- `0x1800fa030`
- `0x1804aab54`
- `0x1804aad5c`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1804ab059`
- `KERNEL32!CloseHandle` at `0x1804ab059`
- `KERNEL32!GetLastError` at `0x1804aaf43`
- `KERNEL32!GetLastError` at `0x1804aaf8c`
- `KERNEL32!GetLastError` at `0x1804aaff7`
- `KERNEL32!GetLastError` at `0x1804ab061`
- `KERNEL32!GetLastError` at `0x1804ab076`
- `KERNEL32!GetLastError` at `0x1804aaf43`
- `KERNEL32!GetLastError` at `0x1804aaf8c`
- `KERNEL32!GetLastError` at `0x1804aaff7`
- `KERNEL32!GetLastError` at `0x1804ab061`
- `KERNEL32!GetLastError` at `0x1804ab076`
- `KERNEL32!CreateFileW` at `0x1804aaf11`
- `KERNEL32!CreateFileW` at `0x1804aaf11`
- `KERNEL32!WriteFile` at `0x1804aafed`
- `KERNEL32!WriteFile` at `0x1804aafed`
- `KERNEL32!GetFileAttributesW` at `0x1804aaf31`
- `KERNEL32!GetFileAttributesW` at `0x1804aaf31`
- `KERNEL32!SetFileAttributesW` at `0x1804aaf82`
- `KERNEL32!SetFileAttributesW` at `0x1804aaf82`

## string_xrefs

- `0x1804ab0a2`: `Failed to create file`
- `0x1804aaddf`: `CUT::UT_GetKnownLowILSafeTempDir failed`

## pseudocode

```c
__int64 __fastcall CTscComHelper::WriteCookieToFile(__int64 a1, unsigned __int8 *a2, DWORD a3, unsigned int *a4)
{
  DWORD v5; // esi
  int v8; // edi
  int KnownLowILSafeTempDir; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  const wchar_t *v13; // rax
  HANDLE FileW; // rbp
  DWORD FileAttributesW; // eax
  DWORD v16; // r14d
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  signed int LastError; // eax
  DWORD v21; // ebp
  unsigned int v22; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-490h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-490h]
  DWORD NumberOfBytesWritten[4]; // [rsp+40h] [rbp-478h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-468h] BYREF
  unsigned __int16 v28[264]; // [rsp+260h] [rbp-258h] BYREF

  v5 = 0;
  NumberOfBytesWritten[0] = 0;
  *a4 = 0;
  v8 = a1;
  KnownLowILSafeTempDir = CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(a1, v28);
  if ( KnownLowILSafeTempDir < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 66;
      v12 = "CUT::UT_GetKnownLowILSafeTempDir failed";
LABEL_6:
      LODWORD(dwFlagsAndAttributes) = KnownLowILSafeTempDir;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v12,
        dwFlagsAndAttributes);
    }
    return (unsigned int)KnownLowILSafeTempDir;
  }
  while ( !v5 )
  {
    KnownLowILSafeTempDir = CTscComHelper::GetRandomNumber(NumberOfBytesWritten);
    if ( KnownLowILSafeTempDir < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 67;
        v12 = "GetRandomNumber failed";
        goto LABEL_6;
      }
      return (unsigned int)KnownLowILSafeTempDir;
    }
    v5 = NumberOfBytesWritten[0];
  }
  v13 = L"OTPCookie";
  if ( !v8 )
    v13 = L"AuthCookie";
  KnownLowILSafeTempDir = StringCchPrintfW(FileName, 0x104u, L"%s\\%s#%d.txt", v28, v13, v5);
  if ( KnownLowILSafeTempDir >= 0 )
  {
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 4u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      KnownLowILSafeTempDir = LastError;
      if ( LastError > 0 )
        KnownLowILSafeTempDir = (unsigned __int16)LastError | 0x80070000;
      v21 = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(dwFlagsAndAttributesa) = v21;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          (unsigned int)WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
          v22,
          (__int64)"Failed to create file",
          dwFlagsAndAttributesa);
      }
      goto LABEL_50;
    }
    NumberOfBytesWritten[0] = 0;
    FileAttributesW = GetFileAttributesW(FileName);
    if ( FileAttributesW == -1 )
    {
      v16 = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 69;
    }
    else
    {
      if ( (FileAttributesW & 0x2000) != 0 )
        goto LABEL_34;
      if ( SetFileAttributesW(FileName, FileAttributesW | 0x2000) )
        goto LABEL_34;
      v16 = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 70;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids, v17, v16);
LABEL_34:
    if ( !WriteFile(FileW, a2, a3, NumberOfBytesWritten, 0) )
    {
      KnownLowILSafeTempDir = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids,
          v19,
          KnownLowILSafeTempDir);
      }
      if ( KnownLowILSafeTempDir > 0 )
        KnownLowILSafeTempDir = (unsigned __int16)KnownLowILSafeTempDir | 0x80070000;
      if ( KnownLowILSafeTempDir >= 0 )
        KnownLowILSafeTempDir = -2147467259;
    }
    CloseHandle(FileW);
LABEL_50:
    if ( KnownLowILSafeTempDir >= 0 )
      *a4 = v5;
    return (unsigned int)KnownLowILSafeTempDir;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 68;
    v12 = "StringCchPrintf failed";
    goto LABEL_6;
  }
  return (unsigned int)KnownLowILSafeTempDir;
}

```

## disassembly

```asm
0x1804aad5c  mov     [rsp+arg_0], rbx
0x1804aad61  push    rbp
0x1804aad62  push    rsi
0x1804aad63  push    rdi
0x1804aad64  push    r12
0x1804aad66  push    r13
0x1804aad68  push    r14
0x1804aad6a  push    r15
0x1804aad6c  sub     rsp, 480h
0x1804aad73  mov     rax, cs:__security_cookie
0x1804aad7a  xor     rax, rsp
0x1804aad7d  mov     [rsp+4B8h+var_48], rax
0x1804aad85  mov     r12, rdx
0x1804aad88  xor     esi, esi
0x1804aad8a  lea     rdx, [rsp+4B8h+var_258]; unsigned __int16 *
0x1804aad92  mov     [rsp+4B8h+NumberOfBytesWritten], esi
0x1804aad96  mov     [r9], esi
0x1804aad99  mov     r15, r9
0x1804aad9c  mov     r13d, r8d
0x1804aad9f  mov     edi, ecx
0x1804aada1  call    ?UT_GetKnownLowILSafeTempDir@CClientUtilsWin32@@SAJKPEAG@Z; CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(ulong,ushort *)
0x1804aada6  mov     ebx, eax
0x1804aada8  test    eax, eax
0x1804aadaa  jns     short loc_1804AAE0E
0x1804aadac  mov     rax, cs:WPP_GLOBAL_Control
0x1804aadb3  lea     rdi, WPP_GLOBAL_Control
0x1804aadba  cmp     rax, rdi
0x1804aadbd  jz      loc_1804AB0D8
0x1804aadc3  test    byte ptr [rax+1Ch], 8
0x1804aadc7  jz      loc_1804AB0D8
0x1804aadcd  cmp     byte ptr [rax+19h], 2
0x1804aadd1  jb      loc_1804AB0D8
0x1804aadd7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804aaddc  lea     edx, [rsi+42h]
0x1804aaddf  lea     rcx, aCutUtGetknownl; "CUT::UT_GetKnownLowILSafeTempDir failed"
0x1804aade6  mov     dword ptr [rsp+4B8h+dwFlagsAndAttributes], ebx
0x1804aadea  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1804aadf1  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rcx
0x1804aadf6  mov     r9d, eax
0x1804aadf9  mov     rcx, cs:WPP_GLOBAL_Control
0x1804aae00  mov     rcx, [rcx+10h]
0x1804aae04  call    WPP_SF_DsD
0x1804aae09  jmp     loc_1804AB0D8
0x1804aae0e  test    esi, esi
0x1804aae10  jnz     short loc_1804AAE66
0x1804aae12  lea     rcx, [rsp+4B8h+NumberOfBytesWritten]; unsigned int *
0x1804aae17  call    ?GetRandomNumber@CTscComHelper@@CAJPEAI@Z; CTscComHelper::GetRandomNumber(uint *)
0x1804aae1c  mov     ebx, eax
0x1804aae1e  test    eax, eax
0x1804aae20  js      short loc_1804AAE28
0x1804aae22  mov     esi, [rsp+4B8h+NumberOfBytesWritten]
0x1804aae26  jmp     short loc_1804AAE0E
0x1804aae28  mov     rax, cs:WPP_GLOBAL_Control
0x1804aae2f  lea     rdi, WPP_GLOBAL_Control
0x1804aae36  cmp     rax, rdi
0x1804aae39  jz      loc_1804AB0D8
0x1804aae3f  test    byte ptr [rax+1Ch], 8
0x1804aae43  jz      loc_1804AB0D8
0x1804aae49  cmp     byte ptr [rax+19h], 2
0x1804aae4d  jb      loc_1804AB0D8
0x1804aae53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804aae58  mov     edx, 43h ; 'C'
0x1804aae5d  lea     rcx, aGetrandomnumbe; "GetRandomNumber failed"
0x1804aae64  jmp     short loc_1804AADE6
0x1804aae66  lea     rcx, aAuthcookie; "AuthCookie"
0x1804aae6d  mov     dword ptr [rsp+4B8h+dwFlagsAndAttributes], esi
0x1804aae71  test    edi, edi
0x1804aae73  lea     rax, aOtpcookie; "OTPCookie"
0x1804aae7a  lea     r9, [rsp+4B8h+var_258]
0x1804aae82  mov     edx, 104h; unsigned __int64
0x1804aae87  cmovz   rax, rcx
0x1804aae8b  lea     r8, aSSDTxt; "%s\\%s#%d.txt"
0x1804aae92  lea     rcx, [rsp+4B8h+FileName]; unsigned __int16 *
0x1804aae97  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rax
0x1804aae9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1804aaea1  mov     ebx, eax
0x1804aaea3  test    eax, eax
0x1804aaea5  jns     short loc_1804AAEE8
0x1804aaea7  mov     rax, cs:WPP_GLOBAL_Control
0x1804aaeae  lea     rdi, WPP_GLOBAL_Control
0x1804aaeb5  cmp     rax, rdi
0x1804aaeb8  jz      loc_1804AB0D8
0x1804aaebe  test    byte ptr [rax+1Ch], 8
0x1804aaec2  jz      loc_1804AB0D8
0x1804aaec8  cmp     byte ptr [rax+19h], 2
0x1804aaecc  jb      loc_1804AB0D8
0x1804aaed2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804aaed7  mov     edx, 44h ; 'D'
0x1804aaedc  lea     rcx, aStringcchprint_7; "StringCchPrintf failed"
0x1804aaee3  jmp     loc_1804AADE6
0x1804aaee8  mov     [rsp+4B8h+hTemplateFile], 0; hTemplateFile
0x1804aaef1  lea     rcx, [rsp+4B8h+FileName]; lpFileName
0x1804aaef6  mov     dword ptr [rsp+4B8h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x1804aaefe  xor     r9d, r9d; lpSecurityAttributes
0x1804aaf01  xor     r8d, r8d; dwShareMode
0x1804aaf04  mov     [rsp+4B8h+dwCreationDisposition], 2; dwCreationDisposition
0x1804aaf0c  mov     edx, 40000000h; dwDesiredAccess
0x1804aaf11  call    cs:__imp_CreateFileW
0x1804aaf17  mov     rbp, rax
0x1804aaf1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804aaf1e  jz      loc_1804AB061
0x1804aaf24  lea     rcx, [rsp+4B8h+FileName]; lpFileName
0x1804aaf29  mov     [rsp+4B8h+NumberOfBytesWritten], 0
0x1804aaf31  call    cs:__imp_GetFileAttributesW
0x1804aaf37  lea     rdi, WPP_GLOBAL_Control
0x1804aaf3e  cmp     eax, 0FFFFFFFFh
0x1804aaf41  jnz     short loc_1804AAF70
0x1804aaf43  call    cs:__imp_GetLastError
0x1804aaf49  mov     r14d, eax
0x1804aaf4c  mov     rcx, cs:WPP_GLOBAL_Control
0x1804aaf53  cmp     rcx, rdi
0x1804aaf56  jz      short loc_1804AAFD6
0x1804aaf58  test    byte ptr [rcx+1Ch], 8
0x1804aaf5c  jz      short loc_1804AAFD6
0x1804aaf5e  cmp     byte ptr [rcx+19h], 2
0x1804aaf62  jb      short loc_1804AAFD6
0x1804aaf64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804aaf69  mov     edx, 45h ; 'E'
0x1804aaf6e  jmp     short loc_1804AAFB7
0x1804aaf70  mov     ecx, 2000h
0x1804aaf75  test    ecx, eax
0x1804aaf77  jnz     short loc_1804AAFD6
0x1804aaf79  or      eax, ecx
0x1804aaf7b  lea     rcx, [rsp+4B8h+FileName]; lpFileName
0x1804aaf80  mov     edx, eax; dwFileAttributes
0x1804aaf82  call    cs:__imp_SetFileAttributesW
0x1804aaf88  test    eax, eax
0x1804aaf8a  jnz     short loc_1804AAFD6
0x1804aaf8c  call    cs:__imp_GetLastError
0x1804aaf92  mov     r14d, eax
0x1804aaf95  mov     rcx, cs:WPP_GLOBAL_Control
0x1804aaf9c  cmp     rcx, rdi
0x1804aaf9f  jz      short loc_1804AAFD6
0x1804aafa1  test    byte ptr [rcx+1Ch], 8
0x1804aafa5  jz      short loc_1804AAFD6
0x1804aafa7  cmp     byte ptr [rcx+19h], 2
0x1804aafab  jb      short loc_1804AAFD6
0x1804aafad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804aafb2  mov     edx, 46h ; 'F'
0x1804aafb7  mov     rcx, cs:WPP_GLOBAL_Control
0x1804aafbe  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1804aafc5  mov     r9d, eax
0x1804aafc8  mov     [rsp+4B8h+dwCreationDisposition], r14d
0x1804aafcd  mov     rcx, [rcx+10h]
0x1804aafd1  call    WPP_SF_Dd
0x1804aafd6  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804aafdb  mov     qword ptr [rsp+4B8h+dwCreationDisposition], 0; lpOverlapped
0x1804aafe4  mov     r8d, r13d; nNumberOfBytesToWrite
0x1804aafe7  mov     rdx, r12; lpBuffer
0x1804aafea  mov     rcx, rbp; hFile
0x1804aafed  call    cs:__imp_WriteFile
0x1804aaff3  test    eax, eax
0x1804aaff5  jnz     short loc_1804AB056
0x1804aaff7  call    cs:__imp_GetLastError
0x1804aaffd  mov     ebx, eax
0x1804aafff  mov     rax, cs:WPP_GLOBAL_Control
0x1804ab006  cmp     rax, rdi
0x1804ab009  jz      short loc_1804AB03F
0x1804ab00b  test    byte ptr [rax+1Ch], 8
0x1804ab00f  jz      short loc_1804AB03F
0x1804ab011  cmp     byte ptr [rax+19h], 2
0x1804ab015  jb      short loc_1804AB03F
0x1804ab017  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804ab01c  mov     rcx, cs:WPP_GLOBAL_Control
0x1804ab023  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1804ab02a  mov     edx, 47h ; 'G'
0x1804ab02f  mov     [rsp+4B8h+dwCreationDisposition], ebx
0x1804ab033  mov     r9d, eax
0x1804ab036  mov     rcx, [rcx+10h]
0x1804ab03a  call    WPP_SF_Dd
0x1804ab03f  test    ebx, ebx
0x1804ab041  jle     short loc_1804AB04C
0x1804ab043  movzx   ebx, bx
0x1804ab046  or      ebx, 80070000h
0x1804ab04c  test    ebx, ebx
0x1804ab04e  mov     eax, 80004005h
0x1804ab053  cmovns  ebx, eax
0x1804ab056  mov     rcx, rbp; hObject
0x1804ab059  call    cs:__imp_CloseHandle
0x1804ab05f  jmp     short loc_1804AB0D1
0x1804ab061  call    cs:__imp_GetLastError
0x1804ab067  mov     ebx, eax
0x1804ab069  test    eax, eax
0x1804ab06b  jle     short loc_1804AB076
0x1804ab06d  movzx   ebx, ax
0x1804ab070  or      ebx, 80070000h
0x1804ab076  call    cs:__imp_GetLastError
0x1804ab07c  mov     ebp, eax
0x1804ab07e  mov     rcx, cs:WPP_GLOBAL_Control
0x1804ab085  lea     rdi, WPP_GLOBAL_Control
0x1804ab08c  cmp     rcx, rdi
0x1804ab08f  jz      short loc_1804AB0D1
0x1804ab091  test    byte ptr [rcx+1Ch], 8
0x1804ab095  jz      short loc_1804AB0D1
0x1804ab097  cmp     byte ptr [rcx+19h], 2
0x1804ab09b  jb      short loc_1804AB0D1
0x1804ab09d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804ab0a2  lea     rcx, aFailedToCreate_128; "Failed to create file"
0x1804ab0a9  mov     dword ptr [rsp+4B8h+dwFlagsAndAttributes], ebp
0x1804ab0ad  mov     qword ptr [rsp+4B8h+dwCreationDisposition], rcx
0x1804ab0b2  lea     r8, WPP_f26928dadb7134b42cce7b3475abc9e0_Traceguids
0x1804ab0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1804ab0c0  mov     edx, 48h ; 'H'
0x1804ab0c5  mov     r9d, eax
0x1804ab0c8  mov     rcx, [rcx+10h]
0x1804ab0cc  call    WPP_SF_DsD
0x1804ab0d1  test    ebx, ebx
0x1804ab0d3  js      short loc_1804AB0D8
0x1804ab0d5  mov     [r15], esi
0x1804ab0d8  mov     eax, ebx
0x1804ab0da  mov     rcx, [rsp+4B8h+var_48]
0x1804ab0e2  xor     rcx, rsp; StackCookie
0x1804ab0e5  call    __security_check_cookie
0x1804ab0ea  mov     rbx, [rsp+4B8h+arg_0]
0x1804ab0f2  add     rsp, 480h
0x1804ab0f9  pop     r15
0x1804ab0fb  pop     r14
0x1804ab0fd  pop     r13
0x1804ab0ff  pop     r12
0x1804ab101  pop     rdi
0x1804ab102  pop     rsi
0x1804ab103  pop     rbp
0x1804ab104  retn
```
