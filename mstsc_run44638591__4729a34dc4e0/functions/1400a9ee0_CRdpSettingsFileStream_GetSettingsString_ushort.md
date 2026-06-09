# CRdpSettingsFileStream::GetSettingsString(ushort * *)

- ea: `0x1400a9ee0`
- end: `0x1400aa3c4`
- name: `?GetSettingsString@CRdpSettingsFileStream@@UEAAJPEAPEAG@Z`
- size: `1252`
- prototype: `__int64 __fastcall(CRdpSettingsFileStream *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400a9ee0`
- `0x1400aa6b4`
- `0x1400b3ef0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400aa11d`
- `KERNEL32!LocalFree` at `0x1400aa30b`
- `KERNEL32!LocalFree` at `0x1400aa3b9`
- `KERNEL32!LocalFree` at `0x1400aa11d`
- `KERNEL32!LocalFree` at `0x1400aa30b`
- `KERNEL32!LocalFree` at `0x1400aa3b9`
- `KERNEL32!ReadFile` at `0x1400a9fa1`
- `KERNEL32!ReadFile` at `0x1400aa110`
- `KERNEL32!ReadFile` at `0x1400a9fa1`
- `KERNEL32!ReadFile` at `0x1400aa110`
- `KERNEL32!GetFileSize` at `0x1400a9f59`
- `KERNEL32!GetFileSize` at `0x1400a9f59`
- `KERNEL32!MultiByteToWideChar` at `0x1400aa240`
- `KERNEL32!MultiByteToWideChar` at `0x1400aa33f`
- `KERNEL32!MultiByteToWideChar` at `0x1400aa240`
- `KERNEL32!MultiByteToWideChar` at `0x1400aa33f`
- `KERNEL32!GetLastError` at `0x1400a9fae`
- `KERNEL32!GetLastError` at `0x1400aa349`
- `KERNEL32!GetLastError` at `0x1400a9fae`
- `KERNEL32!GetLastError` at `0x1400aa349`
- `ADVAPI32!IsTextUnicode` at `0x1400aa1c0`
- `ADVAPI32!IsTextUnicode` at `0x1400aa1c0`

## string_xrefs

- `0x1400aa05b`: `Failed to move pointer to the beginning of the file!`
- `0x1400aa168`: `Failed to move pointer to the beginning of the file!`

## pseudocode

```c
__int64 __fastcall CRdpSettingsFileStream::GetSettingsString(HANDLE *this, unsigned __int16 **a2)
{
  int v2; // r15d
  signed int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  DWORD FileSize; // edi
  WCHAR *v8; // r14
  int v9; // r13d
  UINT v10; // r12d
  void *v11; // rdi
  signed int LastError; // eax
  DWORD v13; // ebx
  void *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  signed int v17; // ebx
  int v18; // r9d
  int v19; // ecx
  DWORD i; // r8d
  char v21; // dl
  int v22; // eax
  int v23; // eax
  bool v24; // sf
  int cchWideChar; // ebx
  WCHAR *v26; // rax
  unsigned int v27; // eax
  signed int v29; // eax
  unsigned int v30; // eax
  int iResult[4]; // [rsp+30h] [rbp-10h] BYREF
  int Buffer; // [rsp+90h] [rbp+50h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  *a2 = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v4 = CRdpSettingsFileStream::ResetFilePointerToStart((CRdpSettingsFileStream *)this, 0);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 26;
LABEL_25:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed to move pointer to the beginning of the file!",
        v4);
      return (unsigned int)v4;
    }
    return (unsigned int)v4;
  }
  FileSize = GetFileSize(this[10], 0);
  if ( !FileSize )
    return (unsigned int)-2147024872;
  if ( FileSize > 0x80000 )
    return (unsigned int)-2147024883;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !ReadFile(this[10], &Buffer, 4u, &NumberOfBytesRead, 0) )
    goto LABEL_11;
  if ( (_BYTE)Buffer == 0xEF )
  {
    if ( *(_WORD *)((char *)&Buffer + 1) == 0xBFBB )
    {
      v2 = 3;
      v10 = 65001;
    }
  }
  else if ( (_WORD)Buffer == 0xFFFE || (_WORD)Buffer == 0xFEFF )
  {
    if ( (FileSize & 1) != 0 )
      return (unsigned int)-2147024883;
    v9 = 1;
    v2 = 2;
  }
  v4 = CRdpSettingsFileStream::ResetFilePointerToStart((CRdpSettingsFileStream *)this, v2);
  if ( v4 >= 0 )
  {
    v13 = FileSize - v2 + 2;
    v14 = MIDL_user_allocate(v13);
    v11 = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v15);
      }
      return (unsigned int)-2147024882;
    }
    memset_0(v14, 0, v13);
    if ( !ReadFile(this[10], v11, v13, &NumberOfBytesRead, 0) )
    {
      LocalFree(v11);
LABEL_11:
      v11 = 0;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_80;
    }
    v4 = CRdpSettingsFileStream::ResetFilePointerToStart((CRdpSettingsFileStream *)this, 0);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          v16,
          (__int64)"Failed to move pointer to the beginning of the file!",
          v4);
      }
      goto LABEL_71;
    }
    if ( v9 )
    {
      if ( v10 != 65001 )
        goto LABEL_66;
    }
    else if ( v10 != 65001 )
    {
      v17 = NumberOfBytesRead;
      iResult[0] = -1;
      if ( IsTextUnicode(v11, NumberOfBytesRead, iResult) && (iResult[0] != 2 || v17 >= 100) )
      {
        v9 = 1;
LABEL_66:
        v8 = (WCHAR *)v11;
        goto LABEL_67;
      }
      v18 = 1;
      v19 = 0;
      for ( i = 0; i < NumberOfBytesRead; ++i )
      {
        v21 = *((_BYTE *)v11 + i);
        v22 = 0;
        if ( v21 >= 0 )
          v22 = v18;
        v18 = v22;
        if ( v19 )
        {
          if ( (v21 & 0xC0) != 0x80 )
            goto LABEL_53;
          --v19;
        }
        else if ( (unsigned __int8)v21 >= 0x80u )
        {
          do
          {
            v23 = v19++;
            v24 = (v21 & 0x40) != 0;
            v21 *= 2;
          }
          while ( v24 );
          v19 = v23;
          if ( !v23 )
            goto LABEL_53;
        }
      }
      if ( !v19 && !v18 )
        v10 = 65001;
    }
LABEL_53:
    cchWideChar = MultiByteToWideChar(v10, 0, (LPCCH)v11, -1, 0, 0);
    v26 = (WCHAR *)MIDL_user_allocate(2LL * cchWideChar);
    v8 = v26;
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v27);
      }
      v4 = -2147024882;
      goto LABEL_71;
    }
    if ( !MultiByteToWideChar(v10, 0, (LPCCH)v11, -1, v26, cchWideChar) )
    {
      v29 = GetLastError();
      v4 = v29;
      if ( v29 > 0 )
        v4 = (unsigned __int16)v29 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v30, v4);
      }
LABEL_80:
      if ( v4 < 0 )
      {
        if ( v8 )
          LocalFree(v8);
LABEL_70:
        if ( !v11 )
          return (unsigned int)v4;
LABEL_71:
        LocalFree(v11);
        return (unsigned int)v4;
      }
LABEL_68:
      if ( v9 && v10 != 65001 )
        return (unsigned int)v4;
      goto LABEL_70;
    }
LABEL_67:
    v4 = 0;
    *a2 = v8;
    goto LABEL_68;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 27;
    goto LABEL_25;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400a9ee0  mov     [rsp-38h+arg_0], rbx
0x1400a9ee5  mov     [rsp-38h+arg_8], rdx
0x1400a9eea  push    rbp
0x1400a9eeb  push    rsi
0x1400a9eec  push    rdi
0x1400a9eed  push    r12
0x1400a9eef  push    r13
0x1400a9ef1  push    r14
0x1400a9ef3  push    r15
0x1400a9ef5  mov     rbp, rsp
0x1400a9ef8  sub     rsp, 40h
0x1400a9efc  xor     r15d, r15d
0x1400a9eff  mov     rsi, rcx
0x1400a9f02  mov     [rdx], r15
0x1400a9f05  xor     edx, edx; int
0x1400a9f07  mov     [rbp+NumberOfBytesRead], r15d
0x1400a9f0b  mov     [rbp+Buffer], r15d
0x1400a9f0f  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x1400a9f14  mov     ebx, eax
0x1400a9f16  test    eax, eax
0x1400a9f18  jns     short loc_1400A9F53
0x1400a9f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9f21  lea     rax, WPP_GLOBAL_Control
0x1400a9f28  cmp     rcx, rax
0x1400a9f2b  jz      loc_1400AA311
0x1400a9f31  test    byte ptr [rcx+1Ch], 8
0x1400a9f35  jz      loc_1400AA311
0x1400a9f3b  cmp     byte ptr [rcx+19h], 2
0x1400a9f3f  jb      loc_1400AA311
0x1400a9f45  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9f4a  lea     edx, [r15+1Ah]
0x1400a9f4e  jmp     loc_1400AA05B
0x1400a9f53  mov     rcx, [rsi+50h]; hFile
0x1400a9f57  xor     edx, edx; lpFileSizeHigh
0x1400a9f59  call    cs:__imp_GetFileSize
0x1400a9f5f  mov     edi, eax
0x1400a9f61  test    eax, eax
0x1400a9f63  jnz     short loc_1400A9F6F
0x1400a9f65  mov     ebx, 80070018h
0x1400a9f6a  jmp     loc_1400AA311
0x1400a9f6f  cmp     edi, 80000h
0x1400a9f75  jbe     short loc_1400A9F81
0x1400a9f77  mov     ebx, 8007000Dh
0x1400a9f7c  jmp     loc_1400AA311
0x1400a9f81  mov     rcx, [rsi+50h]; hFile
0x1400a9f85  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400a9f89  mov     r8d, 4; nNumberOfBytesToRead
0x1400a9f8f  mov     [rsp+40h+lpOverlapped], r15; lpOverlapped
0x1400a9f94  lea     rdx, [rbp+Buffer]; lpBuffer
0x1400a9f98  mov     r14, r15
0x1400a9f9b  mov     r13d, r15d
0x1400a9f9e  mov     r12d, r15d
0x1400a9fa1  call    cs:__imp_ReadFile
0x1400a9fa7  test    eax, eax
0x1400a9fa9  jnz     short loc_1400A9FCC
0x1400a9fab  mov     rdi, r15
0x1400a9fae  call    cs:__imp_GetLastError
0x1400a9fb4  mov     ebx, eax
0x1400a9fb6  test    eax, eax
0x1400a9fb8  jle     loc_1400AA3A5
0x1400a9fbe  movzx   ebx, ax
0x1400a9fc1  or      ebx, 80070000h
0x1400a9fc7  jmp     loc_1400AA3A5
0x1400a9fcc  mov     eax, [rbp+Buffer]
0x1400a9fcf  cmp     al, 0EFh
0x1400a9fd1  jnz     short loc_1400A9FED
0x1400a9fd3  cmp     byte ptr [rbp+Buffer+1], 0BBh
0x1400a9fd7  jnz     short loc_1400AA015
0x1400a9fd9  cmp     byte ptr [rbp+Buffer+2], 0BFh
0x1400a9fdd  jnz     short loc_1400AA015
0x1400a9fdf  mov     r15d, 3
0x1400a9fe5  mov     r12d, 0FDE9h
0x1400a9feb  jmp     short loc_1400AA015
0x1400a9fed  cmp     al, 0FEh
0x1400a9fef  jnz     short loc_1400A9FF7
0x1400a9ff1  cmp     byte ptr [rbp+Buffer+1], 0FFh
0x1400a9ff5  jz      short loc_1400AA001
0x1400a9ff7  cmp     al, 0FFh
0x1400a9ff9  jnz     short loc_1400AA015
0x1400a9ffb  cmp     byte ptr [rbp+Buffer+1], 0FEh
0x1400a9fff  jnz     short loc_1400AA015
0x1400aa001  test    dil, 1
0x1400aa005  jnz     loc_1400A9F77
0x1400aa00b  mov     r13d, 1
0x1400aa011  lea     r15d, [r13+1]
0x1400aa015  mov     edx, r15d; int
0x1400aa018  mov     rcx, rsi; this
0x1400aa01b  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x1400aa020  mov     ebx, eax
0x1400aa022  test    eax, eax
0x1400aa024  jns     short loc_1400AA08A
0x1400aa026  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa02d  lea     rax, WPP_GLOBAL_Control
0x1400aa034  cmp     rcx, rax
0x1400aa037  jz      loc_1400AA311
0x1400aa03d  test    byte ptr [rcx+1Ch], 8
0x1400aa041  jz      loc_1400AA311
0x1400aa047  cmp     byte ptr [rcx+19h], 2
0x1400aa04b  jb      loc_1400AA311
0x1400aa051  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa056  mov     edx, 1Bh
0x1400aa05b  lea     rcx, aFailedToMovePo; "Failed to move pointer to the beginning"...
0x1400aa062  mov     [rsp+40h+cchWideChar], ebx
0x1400aa066  mov     [rsp+40h+lpOverlapped], rcx
0x1400aa06b  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa072  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa079  mov     r9d, eax
0x1400aa07c  mov     rcx, [rcx+10h]
0x1400aa080  call    WPP_SF_DsD
0x1400aa085  jmp     loc_1400AA311
0x1400aa08a  sub     edi, r15d
0x1400aa08d  lea     ebx, [rdi+2]
0x1400aa090  mov     ecx, ebx; size
0x1400aa092  mov     r15d, ebx
0x1400aa095  call    MIDL_user_allocate
0x1400aa09a  mov     rdi, rax
0x1400aa09d  test    rax, rax
0x1400aa0a0  jnz     short loc_1400AA0ED
0x1400aa0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa0a9  lea     rax, WPP_GLOBAL_Control
0x1400aa0b0  cmp     rcx, rax
0x1400aa0b3  jz      short loc_1400AA0E3
0x1400aa0b5  test    byte ptr [rcx+1Ch], 1
0x1400aa0b9  jz      short loc_1400AA0E3
0x1400aa0bb  cmp     byte ptr [rcx+19h], 2
0x1400aa0bf  jb      short loc_1400AA0E3
0x1400aa0c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa0cd  lea     edx, [rdi+1Ch]
0x1400aa0d0  mov     r9d, eax
0x1400aa0d3  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa0da  mov     rcx, [rcx+10h]
0x1400aa0de  call    WPP_SF_d
0x1400aa0e3  mov     ebx, 8007000Eh
0x1400aa0e8  jmp     loc_1400AA311
0x1400aa0ed  mov     r8, r15; Size
0x1400aa0f0  xor     edx, edx; Val
0x1400aa0f2  mov     rcx, rdi; void *
0x1400aa0f5  call    memset_0
0x1400aa0fa  mov     rcx, [rsi+50h]; hFile
0x1400aa0fe  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400aa102  xor     r15d, r15d
0x1400aa105  mov     r8d, ebx; nNumberOfBytesToRead
0x1400aa108  mov     rdx, rdi; lpBuffer
0x1400aa10b  mov     [rsp+40h+lpOverlapped], r15; lpOverlapped
0x1400aa110  call    cs:__imp_ReadFile
0x1400aa116  test    eax, eax
0x1400aa118  jnz     short loc_1400AA128
0x1400aa11a  mov     rcx, rdi; hMem
0x1400aa11d  call    cs:__imp_LocalFree
0x1400aa123  jmp     loc_1400A9FAB
0x1400aa128  xor     edx, edx; int
0x1400aa12a  mov     rcx, rsi; this
0x1400aa12d  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x1400aa132  mov     ebx, eax
0x1400aa134  test    eax, eax
0x1400aa136  jns     short loc_1400AA19C
0x1400aa138  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa13f  lea     rax, WPP_GLOBAL_Control
0x1400aa146  cmp     rcx, rax
0x1400aa149  jz      loc_1400AA308
0x1400aa14f  test    byte ptr [rcx+1Ch], 8
0x1400aa153  jz      loc_1400AA308
0x1400aa159  cmp     byte ptr [rcx+19h], 2
0x1400aa15d  jb      loc_1400AA308
0x1400aa163  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa168  lea     rcx, aFailedToMovePo; "Failed to move pointer to the beginning"...
0x1400aa16f  mov     [rsp+40h+cchWideChar], ebx
0x1400aa173  mov     [rsp+40h+lpOverlapped], rcx
0x1400aa178  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa17f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa186  mov     edx, 1Dh
0x1400aa18b  mov     r9d, eax
0x1400aa18e  mov     rcx, [rcx+10h]
0x1400aa192  call    WPP_SF_DsD
0x1400aa197  jmp     loc_1400AA308
0x1400aa19c  or      esi, 0FFFFFFFFh
0x1400aa19f  test    r13d, r13d
0x1400aa1a2  jnz     loc_1400AA2DB
0x1400aa1a8  cmp     r12d, 0FDE9h
0x1400aa1af  jz      short loc_1400AA22B
0x1400aa1b1  mov     ebx, [rbp+NumberOfBytesRead]
0x1400aa1b4  lea     r8, [rbp+iResult]; lpiResult
0x1400aa1b8  mov     edx, ebx; iSize
0x1400aa1ba  mov     [rbp+iResult], esi
0x1400aa1bd  mov     rcx, rdi; lpv
0x1400aa1c0  call    cs:__imp_IsTextUnicode
0x1400aa1c6  test    eax, eax
0x1400aa1c8  jz      short loc_1400AA1E0
0x1400aa1ca  cmp     [rbp+iResult], 2
0x1400aa1ce  jnz     short loc_1400AA1D5
0x1400aa1d0  cmp     ebx, 64h ; 'd'
0x1400aa1d3  jl      short loc_1400AA1E0
0x1400aa1d5  mov     r13d, 1
0x1400aa1db  jmp     loc_1400AA2E8
0x1400aa1e0  mov     r9d, 1
0x1400aa1e6  mov     ecx, r15d
0x1400aa1e9  mov     r8d, r15d
0x1400aa1ec  cmp     r8d, [rbp+NumberOfBytesRead]
0x1400aa1f0  jnb     loc_1400AA2BF
0x1400aa1f6  mov     eax, r8d
0x1400aa1f9  mov     dl, [rax+rdi]
0x1400aa1fc  mov     eax, r15d
0x1400aa1ff  test    dl, dl
0x1400aa201  cmovns  eax, r9d
0x1400aa205  mov     r9d, eax
0x1400aa208  test    ecx, ecx
0x1400aa20a  jnz     loc_1400AA2A9
0x1400aa210  cmp     dl, 80h
0x1400aa213  jb      loc_1400AA2B7
0x1400aa219  mov     eax, ecx
0x1400aa21b  inc     ecx
0x1400aa21d  add     dl, dl
0x1400aa21f  js      short loc_1400AA219
0x1400aa221  mov     ecx, eax
0x1400aa223  test    eax, eax
0x1400aa225  jnz     loc_1400AA2B7
0x1400aa22b  mov     [rsp+40h+cchWideChar], r15d; cchWideChar
0x1400aa230  mov     r9d, esi; cbMultiByte
0x1400aa233  mov     r8, rdi; lpMultiByteStr
0x1400aa236  mov     [rsp+40h+lpOverlapped], r15; lpWideCharStr
0x1400aa23b  xor     edx, edx; dwFlags
0x1400aa23d  mov     ecx, r12d; CodePage
0x1400aa240  call    cs:__imp_MultiByteToWideChar
0x1400aa246  movsxd  rbx, eax
0x1400aa249  mov     rcx, rbx
0x1400aa24c  add     rcx, rcx; size
0x1400aa24f  call    MIDL_user_allocate
0x1400aa254  mov     r14, rax
0x1400aa257  test    rax, rax
0x1400aa25a  jnz     loc_1400AA32B
0x1400aa260  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa267  lea     rax, WPP_GLOBAL_Control
0x1400aa26e  cmp     rcx, rax
0x1400aa271  jz      short loc_1400AA2A2
0x1400aa273  test    byte ptr [rcx+1Ch], 1
0x1400aa277  jz      short loc_1400AA2A2
0x1400aa279  cmp     byte ptr [rcx+19h], 2
0x1400aa27d  jb      short loc_1400AA2A2
0x1400aa27f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aa284  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aa28b  lea     edx, [r14+1Eh]
0x1400aa28f  mov     r9d, eax
0x1400aa292  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400aa299  mov     rcx, [rcx+10h]
0x1400aa29d  call    WPP_SF_d
0x1400aa2a2  mov     ebx, 8007000Eh
0x1400aa2a7  jmp     short loc_1400AA308
0x1400aa2a9  and     dl, 0C0h
0x1400aa2ac  cmp     dl, 80h
0x1400aa2af  jnz     loc_1400AA22B
0x1400aa2b5  dec     ecx
0x1400aa2b7  inc     r8d
0x1400aa2ba  jmp     loc_1400AA1EC
0x1400aa2bf  test    ecx, ecx
0x1400aa2c1  jnz     loc_1400AA22B
0x1400aa2c7  test    r9d, r9d
0x1400aa2ca  jnz     loc_1400AA22B
0x1400aa2d0  mov     r12d, 0FDE9h
0x1400aa2d6  jmp     loc_1400AA22B
0x1400aa2db  cmp     r12d, 0FDE9h
0x1400aa2e2  jz      loc_1400AA22B
0x1400aa2e8  mov     r14, rdi
0x1400aa2eb  mov     rax, [rbp+arg_8]
0x1400aa2ef  mov     ebx, r15d
0x1400aa2f2  mov     [rax], r14
0x1400aa2f5  test    r13d, r13d
0x1400aa2f8  jz      short loc_1400AA303
0x1400aa2fa  cmp     r12d, 0FDE9h
0x1400aa301  jnz     short loc_1400AA311
0x1400aa303  test    rdi, rdi
0x1400aa306  jz      short loc_1400AA311
0x1400aa308  mov     rcx, rdi; hMem
0x1400aa30b  call    cs:__imp_LocalFree
0x1400aa311  mov     eax, ebx
0x1400aa313  mov     rbx, [rsp+40h+arg_0]
0x1400aa31b  add     rsp, 40h
0x1400aa31f  pop     r15
0x1400aa321  pop     r14
0x1400aa323  pop     r13
0x1400aa325  pop     r12
0x1400aa327  pop     rdi
0x1400aa328  pop     rsi
0x1400aa329  pop     rbp
0x1400aa32a  retn
0x1400aa32b  mov     [rsp+40h+cchWideChar], ebx; cchWideChar
0x1400aa32f  mov     r9d, esi; cbMultiByte
0x1400aa332  mov     r8, rdi; lpMultiByteStr
0x1400aa335  mov     [rsp+40h+lpOverlapped], rax; lpWideCharStr
0x1400aa33a  xor     edx, edx; dwFlags
0x1400aa33c  mov     ecx, r12d; CodePage
0x1400aa33f  call    cs:__imp_MultiByteToWideChar
0x1400aa345  test    eax, eax
0x1400aa347  jnz     short loc_1400AA2EB
0x1400aa349  call    cs:__imp_GetLastError
0x1400aa34f  mov     ebx, eax
0x1400aa351  test    eax, eax
0x1400aa353  jle     short loc_1400AA35E
0x1400aa355  movzx   ebx, ax
0x1400aa358  or      ebx, 80070000h
  ... truncated ...
```
