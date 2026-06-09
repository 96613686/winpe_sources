# CRdpSettingsFileStream::GetSettingsString(ushort * *)

- ea: `0x1400a7d70`
- end: `0x1400a8254`
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
- `0x1400a7d70`
- `0x1400a8544`
- `0x1400b1d80`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400a7fad`
- `KERNEL32!LocalFree` at `0x1400a819b`
- `KERNEL32!LocalFree` at `0x1400a8249`
- `KERNEL32!LocalFree` at `0x1400a7fad`
- `KERNEL32!LocalFree` at `0x1400a819b`
- `KERNEL32!LocalFree` at `0x1400a8249`
- `KERNEL32!ReadFile` at `0x1400a7e31`
- `KERNEL32!ReadFile` at `0x1400a7fa0`
- `KERNEL32!ReadFile` at `0x1400a7e31`
- `KERNEL32!ReadFile` at `0x1400a7fa0`
- `KERNEL32!GetFileSize` at `0x1400a7de9`
- `KERNEL32!GetFileSize` at `0x1400a7de9`
- `KERNEL32!MultiByteToWideChar` at `0x1400a80d0`
- `KERNEL32!MultiByteToWideChar` at `0x1400a81cf`
- `KERNEL32!MultiByteToWideChar` at `0x1400a80d0`
- `KERNEL32!MultiByteToWideChar` at `0x1400a81cf`
- `KERNEL32!GetLastError` at `0x1400a7e3e`
- `KERNEL32!GetLastError` at `0x1400a81d9`
- `KERNEL32!GetLastError` at `0x1400a7e3e`
- `KERNEL32!GetLastError` at `0x1400a81d9`
- `ADVAPI32!IsTextUnicode` at `0x1400a8050`
- `ADVAPI32!IsTextUnicode` at `0x1400a8050`

## string_xrefs

- `0x1400a7eeb`: `Failed to move pointer to the beginning of the file!`
- `0x1400a7ff8`: `Failed to move pointer to the beginning of the file!`

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
0x1400a7d70  mov     [rsp-38h+arg_0], rbx
0x1400a7d75  mov     [rsp-38h+arg_8], rdx
0x1400a7d7a  push    rbp
0x1400a7d7b  push    rsi
0x1400a7d7c  push    rdi
0x1400a7d7d  push    r12
0x1400a7d7f  push    r13
0x1400a7d81  push    r14
0x1400a7d83  push    r15
0x1400a7d85  mov     rbp, rsp
0x1400a7d88  sub     rsp, 40h
0x1400a7d8c  xor     r15d, r15d
0x1400a7d8f  mov     rsi, rcx
0x1400a7d92  mov     [rdx], r15
0x1400a7d95  xor     edx, edx; int
0x1400a7d97  mov     [rbp+NumberOfBytesRead], r15d
0x1400a7d9b  mov     [rbp+Buffer], r15d
0x1400a7d9f  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x1400a7da4  mov     ebx, eax
0x1400a7da6  test    eax, eax
0x1400a7da8  jns     short loc_1400A7DE3
0x1400a7daa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7db1  lea     rax, WPP_GLOBAL_Control
0x1400a7db8  cmp     rcx, rax
0x1400a7dbb  jz      loc_1400A81A1
0x1400a7dc1  test    byte ptr [rcx+1Ch], 8
0x1400a7dc5  jz      loc_1400A81A1
0x1400a7dcb  cmp     byte ptr [rcx+19h], 2
0x1400a7dcf  jb      loc_1400A81A1
0x1400a7dd5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7dda  lea     edx, [r15+1Ah]
0x1400a7dde  jmp     loc_1400A7EEB
0x1400a7de3  mov     rcx, [rsi+50h]; hFile
0x1400a7de7  xor     edx, edx; lpFileSizeHigh
0x1400a7de9  call    cs:__imp_GetFileSize
0x1400a7def  mov     edi, eax
0x1400a7df1  test    eax, eax
0x1400a7df3  jnz     short loc_1400A7DFF
0x1400a7df5  mov     ebx, 80070018h
0x1400a7dfa  jmp     loc_1400A81A1
0x1400a7dff  cmp     edi, 80000h
0x1400a7e05  jbe     short loc_1400A7E11
0x1400a7e07  mov     ebx, 8007000Dh
0x1400a7e0c  jmp     loc_1400A81A1
0x1400a7e11  mov     rcx, [rsi+50h]; hFile
0x1400a7e15  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400a7e19  mov     r8d, 4; nNumberOfBytesToRead
0x1400a7e1f  mov     [rsp+40h+lpOverlapped], r15; lpOverlapped
0x1400a7e24  lea     rdx, [rbp+Buffer]; lpBuffer
0x1400a7e28  mov     r14, r15
0x1400a7e2b  mov     r13d, r15d
0x1400a7e2e  mov     r12d, r15d
0x1400a7e31  call    cs:__imp_ReadFile
0x1400a7e37  test    eax, eax
0x1400a7e39  jnz     short loc_1400A7E5C
0x1400a7e3b  mov     rdi, r15
0x1400a7e3e  call    cs:__imp_GetLastError
0x1400a7e44  mov     ebx, eax
0x1400a7e46  test    eax, eax
0x1400a7e48  jle     loc_1400A8235
0x1400a7e4e  movzx   ebx, ax
0x1400a7e51  or      ebx, 80070000h
0x1400a7e57  jmp     loc_1400A8235
0x1400a7e5c  mov     eax, [rbp+Buffer]
0x1400a7e5f  cmp     al, 0EFh
0x1400a7e61  jnz     short loc_1400A7E7D
0x1400a7e63  cmp     byte ptr [rbp+Buffer+1], 0BBh
0x1400a7e67  jnz     short loc_1400A7EA5
0x1400a7e69  cmp     byte ptr [rbp+Buffer+2], 0BFh
0x1400a7e6d  jnz     short loc_1400A7EA5
0x1400a7e6f  mov     r15d, 3
0x1400a7e75  mov     r12d, 0FDE9h
0x1400a7e7b  jmp     short loc_1400A7EA5
0x1400a7e7d  cmp     al, 0FEh
0x1400a7e7f  jnz     short loc_1400A7E87
0x1400a7e81  cmp     byte ptr [rbp+Buffer+1], 0FFh
0x1400a7e85  jz      short loc_1400A7E91
0x1400a7e87  cmp     al, 0FFh
0x1400a7e89  jnz     short loc_1400A7EA5
0x1400a7e8b  cmp     byte ptr [rbp+Buffer+1], 0FEh
0x1400a7e8f  jnz     short loc_1400A7EA5
0x1400a7e91  test    dil, 1
0x1400a7e95  jnz     loc_1400A7E07
0x1400a7e9b  mov     r13d, 1
0x1400a7ea1  lea     r15d, [r13+1]
0x1400a7ea5  mov     edx, r15d; int
0x1400a7ea8  mov     rcx, rsi; this
0x1400a7eab  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x1400a7eb0  mov     ebx, eax
0x1400a7eb2  test    eax, eax
0x1400a7eb4  jns     short loc_1400A7F1A
0x1400a7eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7ebd  lea     rax, WPP_GLOBAL_Control
0x1400a7ec4  cmp     rcx, rax
0x1400a7ec7  jz      loc_1400A81A1
0x1400a7ecd  test    byte ptr [rcx+1Ch], 8
0x1400a7ed1  jz      loc_1400A81A1
0x1400a7ed7  cmp     byte ptr [rcx+19h], 2
0x1400a7edb  jb      loc_1400A81A1
0x1400a7ee1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7ee6  mov     edx, 1Bh
0x1400a7eeb  lea     rcx, aFailedToMovePo; "Failed to move pointer to the beginning"...
0x1400a7ef2  mov     [rsp+40h+cchWideChar], ebx
0x1400a7ef6  mov     [rsp+40h+lpOverlapped], rcx
0x1400a7efb  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7f02  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7f09  mov     r9d, eax
0x1400a7f0c  mov     rcx, [rcx+10h]
0x1400a7f10  call    WPP_SF_DsD
0x1400a7f15  jmp     loc_1400A81A1
0x1400a7f1a  sub     edi, r15d
0x1400a7f1d  lea     ebx, [rdi+2]
0x1400a7f20  mov     ecx, ebx; size
0x1400a7f22  mov     r15d, ebx
0x1400a7f25  call    MIDL_user_allocate
0x1400a7f2a  mov     rdi, rax
0x1400a7f2d  test    rax, rax
0x1400a7f30  jnz     short loc_1400A7F7D
0x1400a7f32  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7f39  lea     rax, WPP_GLOBAL_Control
0x1400a7f40  cmp     rcx, rax
0x1400a7f43  jz      short loc_1400A7F73
0x1400a7f45  test    byte ptr [rcx+1Ch], 1
0x1400a7f49  jz      short loc_1400A7F73
0x1400a7f4b  cmp     byte ptr [rcx+19h], 2
0x1400a7f4f  jb      short loc_1400A7F73
0x1400a7f51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7f56  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7f5d  lea     edx, [rdi+1Ch]
0x1400a7f60  mov     r9d, eax
0x1400a7f63  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7f6a  mov     rcx, [rcx+10h]
0x1400a7f6e  call    WPP_SF_d
0x1400a7f73  mov     ebx, 8007000Eh
0x1400a7f78  jmp     loc_1400A81A1
0x1400a7f7d  mov     r8, r15; Size
0x1400a7f80  xor     edx, edx; Val
0x1400a7f82  mov     rcx, rdi; void *
0x1400a7f85  call    memset_0
0x1400a7f8a  mov     rcx, [rsi+50h]; hFile
0x1400a7f8e  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400a7f92  xor     r15d, r15d
0x1400a7f95  mov     r8d, ebx; nNumberOfBytesToRead
0x1400a7f98  mov     rdx, rdi; lpBuffer
0x1400a7f9b  mov     [rsp+40h+lpOverlapped], r15; lpOverlapped
0x1400a7fa0  call    cs:__imp_ReadFile
0x1400a7fa6  test    eax, eax
0x1400a7fa8  jnz     short loc_1400A7FB8
0x1400a7faa  mov     rcx, rdi; hMem
0x1400a7fad  call    cs:__imp_LocalFree
0x1400a7fb3  jmp     loc_1400A7E3B
0x1400a7fb8  xor     edx, edx; int
0x1400a7fba  mov     rcx, rsi; this
0x1400a7fbd  call    ?ResetFilePointerToStart@CRdpSettingsFileStream@@IEAAJJ@Z; CRdpSettingsFileStream::ResetFilePointerToStart(long)
0x1400a7fc2  mov     ebx, eax
0x1400a7fc4  test    eax, eax
0x1400a7fc6  jns     short loc_1400A802C
0x1400a7fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7fcf  lea     rax, WPP_GLOBAL_Control
0x1400a7fd6  cmp     rcx, rax
0x1400a7fd9  jz      loc_1400A8198
0x1400a7fdf  test    byte ptr [rcx+1Ch], 8
0x1400a7fe3  jz      loc_1400A8198
0x1400a7fe9  cmp     byte ptr [rcx+19h], 2
0x1400a7fed  jb      loc_1400A8198
0x1400a7ff3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7ff8  lea     rcx, aFailedToMovePo; "Failed to move pointer to the beginning"...
0x1400a7fff  mov     [rsp+40h+cchWideChar], ebx
0x1400a8003  mov     [rsp+40h+lpOverlapped], rcx
0x1400a8008  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a800f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8016  mov     edx, 1Dh
0x1400a801b  mov     r9d, eax
0x1400a801e  mov     rcx, [rcx+10h]
0x1400a8022  call    WPP_SF_DsD
0x1400a8027  jmp     loc_1400A8198
0x1400a802c  or      esi, 0FFFFFFFFh
0x1400a802f  test    r13d, r13d
0x1400a8032  jnz     loc_1400A816B
0x1400a8038  cmp     r12d, 0FDE9h
0x1400a803f  jz      short loc_1400A80BB
0x1400a8041  mov     ebx, [rbp+NumberOfBytesRead]
0x1400a8044  lea     r8, [rbp+iResult]; lpiResult
0x1400a8048  mov     edx, ebx; iSize
0x1400a804a  mov     [rbp+iResult], esi
0x1400a804d  mov     rcx, rdi; lpv
0x1400a8050  call    cs:__imp_IsTextUnicode
0x1400a8056  test    eax, eax
0x1400a8058  jz      short loc_1400A8070
0x1400a805a  cmp     [rbp+iResult], 2
0x1400a805e  jnz     short loc_1400A8065
0x1400a8060  cmp     ebx, 64h ; 'd'
0x1400a8063  jl      short loc_1400A8070
0x1400a8065  mov     r13d, 1
0x1400a806b  jmp     loc_1400A8178
0x1400a8070  mov     r9d, 1
0x1400a8076  mov     ecx, r15d
0x1400a8079  mov     r8d, r15d
0x1400a807c  cmp     r8d, [rbp+NumberOfBytesRead]
0x1400a8080  jnb     loc_1400A814F
0x1400a8086  mov     eax, r8d
0x1400a8089  mov     dl, [rax+rdi]
0x1400a808c  mov     eax, r15d
0x1400a808f  test    dl, dl
0x1400a8091  cmovns  eax, r9d
0x1400a8095  mov     r9d, eax
0x1400a8098  test    ecx, ecx
0x1400a809a  jnz     loc_1400A8139
0x1400a80a0  cmp     dl, 80h
0x1400a80a3  jb      loc_1400A8147
0x1400a80a9  mov     eax, ecx
0x1400a80ab  inc     ecx
0x1400a80ad  add     dl, dl
0x1400a80af  js      short loc_1400A80A9
0x1400a80b1  mov     ecx, eax
0x1400a80b3  test    eax, eax
0x1400a80b5  jnz     loc_1400A8147
0x1400a80bb  mov     [rsp+40h+cchWideChar], r15d; cchWideChar
0x1400a80c0  mov     r9d, esi; cbMultiByte
0x1400a80c3  mov     r8, rdi; lpMultiByteStr
0x1400a80c6  mov     [rsp+40h+lpOverlapped], r15; lpWideCharStr
0x1400a80cb  xor     edx, edx; dwFlags
0x1400a80cd  mov     ecx, r12d; CodePage
0x1400a80d0  call    cs:__imp_MultiByteToWideChar
0x1400a80d6  movsxd  rbx, eax
0x1400a80d9  mov     rcx, rbx
0x1400a80dc  add     rcx, rcx; size
0x1400a80df  call    MIDL_user_allocate
0x1400a80e4  mov     r14, rax
0x1400a80e7  test    rax, rax
0x1400a80ea  jnz     loc_1400A81BB
0x1400a80f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a80f7  lea     rax, WPP_GLOBAL_Control
0x1400a80fe  cmp     rcx, rax
0x1400a8101  jz      short loc_1400A8132
0x1400a8103  test    byte ptr [rcx+1Ch], 1
0x1400a8107  jz      short loc_1400A8132
0x1400a8109  cmp     byte ptr [rcx+19h], 2
0x1400a810d  jb      short loc_1400A8132
0x1400a810f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8114  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a811b  lea     edx, [r14+1Eh]
0x1400a811f  mov     r9d, eax
0x1400a8122  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a8129  mov     rcx, [rcx+10h]
0x1400a812d  call    WPP_SF_d
0x1400a8132  mov     ebx, 8007000Eh
0x1400a8137  jmp     short loc_1400A8198
0x1400a8139  and     dl, 0C0h
0x1400a813c  cmp     dl, 80h
0x1400a813f  jnz     loc_1400A80BB
0x1400a8145  dec     ecx
0x1400a8147  inc     r8d
0x1400a814a  jmp     loc_1400A807C
0x1400a814f  test    ecx, ecx
0x1400a8151  jnz     loc_1400A80BB
0x1400a8157  test    r9d, r9d
0x1400a815a  jnz     loc_1400A80BB
0x1400a8160  mov     r12d, 0FDE9h
0x1400a8166  jmp     loc_1400A80BB
0x1400a816b  cmp     r12d, 0FDE9h
0x1400a8172  jz      loc_1400A80BB
0x1400a8178  mov     r14, rdi
0x1400a817b  mov     rax, [rbp+arg_8]
0x1400a817f  mov     ebx, r15d
0x1400a8182  mov     [rax], r14
0x1400a8185  test    r13d, r13d
0x1400a8188  jz      short loc_1400A8193
0x1400a818a  cmp     r12d, 0FDE9h
0x1400a8191  jnz     short loc_1400A81A1
0x1400a8193  test    rdi, rdi
0x1400a8196  jz      short loc_1400A81A1
0x1400a8198  mov     rcx, rdi; hMem
0x1400a819b  call    cs:__imp_LocalFree
0x1400a81a1  mov     eax, ebx
0x1400a81a3  mov     rbx, [rsp+40h+arg_0]
0x1400a81ab  add     rsp, 40h
0x1400a81af  pop     r15
0x1400a81b1  pop     r14
0x1400a81b3  pop     r13
0x1400a81b5  pop     r12
0x1400a81b7  pop     rdi
0x1400a81b8  pop     rsi
0x1400a81b9  pop     rbp
0x1400a81ba  retn
0x1400a81bb  mov     [rsp+40h+cchWideChar], ebx; cchWideChar
0x1400a81bf  mov     r9d, esi; cbMultiByte
0x1400a81c2  mov     r8, rdi; lpMultiByteStr
0x1400a81c5  mov     [rsp+40h+lpOverlapped], rax; lpWideCharStr
0x1400a81ca  xor     edx, edx; dwFlags
0x1400a81cc  mov     ecx, r12d; CodePage
0x1400a81cf  call    cs:__imp_MultiByteToWideChar
0x1400a81d5  test    eax, eax
0x1400a81d7  jnz     short loc_1400A817B
0x1400a81d9  call    cs:__imp_GetLastError
0x1400a81df  mov     ebx, eax
0x1400a81e1  test    eax, eax
0x1400a81e3  jle     short loc_1400A81EE
0x1400a81e5  movzx   ebx, ax
0x1400a81e8  or      ebx, 80070000h
  ... truncated ...
```
