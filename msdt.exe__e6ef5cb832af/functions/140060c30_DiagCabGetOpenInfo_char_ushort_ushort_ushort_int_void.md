# DiagCabGetOpenInfo(char *,ushort *,ushort *,ushort *,int *,void *)

- ea: `0x140060c30`
- end: `0x140060f19`
- name: `?DiagCabGetOpenInfo@@YA_JPEADPEAG11PEAHPEAX@Z`
- size: `745`
- prototype: `INT_PTR __fastcall(const CHAR *pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140060c30`
- `0x140061c90`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x140060e30`
- `KERNEL32!FileTimeToLocalFileTime` at `0x140060e30`
- `KERNEL32!GetFileInformationByHandle` at `0x140060de2`
- `KERNEL32!GetFileInformationByHandle` at `0x140060de2`
- `KERNEL32!MultiByteToWideChar` at `0x140060ca5`
- `KERNEL32!MultiByteToWideChar` at `0x140060d42`
- `KERNEL32!MultiByteToWideChar` at `0x140060ca5`
- `KERNEL32!MultiByteToWideChar` at `0x140060d42`
- `KERNEL32!GetLastError` at `0x140060cb7`
- `KERNEL32!GetLastError` at `0x140060ccb`
- `KERNEL32!GetLastError` at `0x140060d52`
- `KERNEL32!GetLastError` at `0x140060d69`
- `KERNEL32!GetLastError` at `0x140060df7`
- `KERNEL32!GetLastError` at `0x140060e07`
- `KERNEL32!GetLastError` at `0x140060e40`
- `KERNEL32!GetLastError` at `0x140060e50`
- `KERNEL32!GetLastError` at `0x140060e8a`
- `KERNEL32!GetLastError` at `0x140060e9a`
- `KERNEL32!GetLastError` at `0x140060cb7`
- `KERNEL32!GetLastError` at `0x140060ccb`
- `KERNEL32!GetLastError` at `0x140060d52`
- `KERNEL32!GetLastError` at `0x140060d69`
- `KERNEL32!GetLastError` at `0x140060df7`
- `KERNEL32!GetLastError` at `0x140060e07`
- `KERNEL32!GetLastError` at `0x140060e40`
- `KERNEL32!GetLastError` at `0x140060e50`
- `KERNEL32!GetLastError` at `0x140060e8a`
- `KERNEL32!GetLastError` at `0x140060e9a`
- `KERNEL32!HeapAlloc` at `0x140060d0b`
- `KERNEL32!HeapAlloc` at `0x140060d0b`
- `KERNEL32!HeapFree` at `0x140060ed7`
- `KERNEL32!HeapFree` at `0x140060ed7`
- `KERNEL32!GetProcessHeap` at `0x140060cf7`
- `KERNEL32!GetProcessHeap` at `0x140060ec3`
- `KERNEL32!GetProcessHeap` at `0x140060cf7`
- `KERNEL32!GetProcessHeap` at `0x140060ec3`
- `KERNEL32!FileTimeToDosDateTime` at `0x140060e76`
- `KERNEL32!FileTimeToDosDateTime` at `0x140060e76`
- `msvcrt!_errno` at `0x140060dab`
- `msvcrt!_errno` at `0x140060dab`
- `msvcrt!_get_osfhandle` at `0x140060dc8`
- `msvcrt!_get_osfhandle` at `0x140060dc8`
- `msvcrt!_wopen` at `0x140060d98`
- `msvcrt!_wopen` at `0x140060d98`

## pseudocode

```c
INT_PTR __fastcall DiagCabGetOpenInfo(const CHAR *pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err)
{
  int v9; // esi
  int v10; // eax
  int cchWideChar; // edi
  signed int v12; // eax
  int v13; // ebx
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v17; // rbp
  signed int v18; // eax
  int v19; // eax
  void *osfhandle; // rax
  signed int LastError; // eax
  signed int v22; // eax
  signed int v23; // eax
  HANDLE v24; // rax
  INT_PTR result; // rax
  struct _FILETIME LocalFileTime; // [rsp+30h] [rbp-98h] BYREF
  int *v27; // [rsp+38h] [rbp-90h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+40h] [rbp-88h] BYREF

  v27 = err;
  LocalFileTime = 0;
  v9 = -1;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v10 = MultiByteToWideChar(0xFDE9u, 8u, pszName, -1, 0, 0);
  cchWideChar = v10;
  if ( v10 )
  {
    v14 = 2LL * (v10 + 1);
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, v14);
    v17 = lpWideCharStr;
    if ( !lpWideCharStr )
    {
      v13 = -2147024882;
LABEL_36:
      result = -1;
      *v27 = v13;
      return result;
    }
    if ( MultiByteToWideChar(0xFDE9u, 8u, pszName, -1, lpWideCharStr, cchWideChar) )
    {
      v19 = _wopen(v17, 0x8000, 0);
      v9 = v19;
      if ( v19 != -1 )
      {
        osfhandle = (void *)_get_osfhandle(v19);
        if ( osfhandle != (void *)-1LL )
        {
          if ( !GetFileInformationByHandle(osfhandle, &FileInformation) && GetLastError() )
          {
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_34;
          }
          if ( !FileTimeToLocalFileTime(&FileInformation.ftLastWriteTime, &LocalFileTime) && GetLastError() )
          {
            v22 = GetLastError();
            v13 = v22;
            if ( v22 > 0 )
              v13 = (unsigned __int16)v22 | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_34;
          }
          if ( FileTimeToDosDateTime(&LocalFileTime, pdate, ptime) || !GetLastError() )
          {
            v13 = 0;
          }
          else
          {
            v23 = GetLastError();
            v13 = v23;
            if ( v23 > 0 )
              v13 = (unsigned __int16)v23 | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_34;
          }
          *pattribs = FileInformation.dwFileAttributes & 0x27;
LABEL_34:
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v17);
          goto LABEL_35;
        }
      }
      v13 = *_errno();
      if ( v13 <= 0 )
        goto LABEL_34;
      v13 = (unsigned __int16)v13;
    }
    else
    {
      if ( !GetLastError() )
      {
        v13 = 0;
        goto LABEL_34;
      }
      v18 = GetLastError();
      v13 = v18;
      if ( v18 <= 0 )
        goto LABEL_34;
      v13 = (unsigned __int16)v18;
    }
    v13 |= 0x80070000;
    goto LABEL_34;
  }
  if ( !GetLastError() )
    return v9;
  v12 = GetLastError();
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
LABEL_35:
  if ( v13 < 0 )
    goto LABEL_36;
  return v9;
}

```

## disassembly

```asm
0x140060c30  push    rbx
0x140060c32  push    rbp
0x140060c33  push    rsi
0x140060c34  push    rdi
0x140060c35  push    r12
0x140060c37  push    r13
0x140060c39  push    r14
0x140060c3b  push    r15
0x140060c3d  sub     rsp, 88h
0x140060c44  mov     rax, cs:__security_cookie
0x140060c4b  xor     rax, rsp
0x140060c4e  mov     [rsp+0C8h+var_50], rax
0x140060c53  mov     rax, [rsp+0C8h+err]
0x140060c5b  xorps   xmm0, xmm0
0x140060c5e  xor     ebx, ebx
0x140060c60  mov     [rsp+0C8h+var_90], rax
0x140060c65  xor     eax, eax
0x140060c67  mov     [rsp+0C8h+cchWideChar], ebx; cchWideChar
0x140060c6b  mov     r12, r8
0x140060c6e  mov     [rsp+0C8h+FileInformation.nFileIndexLow], eax
0x140060c72  mov     r13, r9
0x140060c75  mov     qword ptr [rsp+0C8h+LocalFileTime.dwLowDateTime], rbx
0x140060c7a  mov     r15, rdx
0x140060c7d  mov     [rsp+0C8h+lpWideCharStr], rbx; lpWideCharStr
0x140060c82  mov     r14, rcx
0x140060c85  lea     edx, [rax+8]; dwFlags
0x140060c88  mov     r8, rcx; lpMultiByteStr
0x140060c8b  or      esi, 0FFFFFFFFh
0x140060c8e  or      r9d, esi; cbMultiByte
0x140060c91  mov     ecx, 0FDE9h; CodePage
0x140060c96  movups  xmmword ptr [rsp+0C8h+FileInformation.dwFileAttributes], xmm0
0x140060c9b  movups  xmmword ptr [rsp+0C8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140060ca0  movups  xmmword ptr [rsp+0C8h+FileInformation.nFileSizeHigh], xmm0
0x140060ca5  call    cs:__imp_MultiByteToWideChar
0x140060cac  nop     dword ptr [rax+rax+00h]
0x140060cb1  mov     edi, eax
0x140060cb3  test    eax, eax
0x140060cb5  jnz     short loc_140060CEF
0x140060cb7  call    cs:__imp_GetLastError
0x140060cbe  nop     dword ptr [rax+rax+00h]
0x140060cc3  test    eax, eax
0x140060cc5  jz      loc_140060EF4
0x140060ccb  call    cs:__imp_GetLastError
0x140060cd2  nop     dword ptr [rax+rax+00h]
0x140060cd7  mov     ebx, eax
0x140060cd9  test    eax, eax
0x140060cdb  jle     loc_140060EE3
0x140060ce1  movzx   ebx, ax
0x140060ce4  or      ebx, 80070000h
0x140060cea  jmp     loc_140060EE3
0x140060cef  inc     eax
0x140060cf1  movsxd  rbx, eax
0x140060cf4  add     rbx, rbx
0x140060cf7  call    cs:__imp_GetProcessHeap
0x140060cfe  nop     dword ptr [rax+rax+00h]
0x140060d03  mov     r8, rbx; dwBytes
0x140060d06  xor     edx, edx; dwFlags
0x140060d08  mov     rcx, rax; hHeap
0x140060d0b  call    cs:__imp_HeapAlloc
0x140060d12  nop     dword ptr [rax+rax+00h]
0x140060d17  mov     rbp, rax
0x140060d1a  test    rax, rax
0x140060d1d  jnz     short loc_140060D29
0x140060d1f  mov     ebx, 8007000Eh
0x140060d24  jmp     loc_140060EE7
0x140060d29  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140060d2d  mov     [rsp+0C8h+cchWideChar], edi; cchWideChar
0x140060d31  mov     r8, r14; lpMultiByteStr
0x140060d34  mov     [rsp+0C8h+lpWideCharStr], rbp; lpWideCharStr
0x140060d39  mov     ecx, 0FDE9h; CodePage
0x140060d3e  lea     edx, [r9+9]; dwFlags
0x140060d42  call    cs:__imp_MultiByteToWideChar
0x140060d49  nop     dword ptr [rax+rax+00h]
0x140060d4e  test    eax, eax
0x140060d50  jnz     short loc_140060D8D
0x140060d52  call    cs:__imp_GetLastError
0x140060d59  nop     dword ptr [rax+rax+00h]
0x140060d5e  test    eax, eax
0x140060d60  jnz     short loc_140060D69
0x140060d62  xor     ebx, ebx
0x140060d64  jmp     loc_140060EC3
0x140060d69  call    cs:__imp_GetLastError
0x140060d70  nop     dword ptr [rax+rax+00h]
0x140060d75  mov     ebx, eax
0x140060d77  test    eax, eax
0x140060d79  jle     loc_140060EC3
0x140060d7f  movzx   ebx, ax
0x140060d82  or      ebx, 80070000h
0x140060d88  jmp     loc_140060EC3
0x140060d8d  xor     r8d, r8d
0x140060d90  mov     edx, 8000h; OpenFlag
0x140060d95  mov     rcx, rbp; FileName
0x140060d98  call    cs:__imp__wopen
0x140060d9f  nop     dword ptr [rax+rax+00h]
0x140060da4  mov     esi, eax
0x140060da6  cmp     eax, 0FFFFFFFFh
0x140060da9  jnz     short loc_140060DC6
0x140060dab  call    cs:__imp__errno
0x140060db2  nop     dword ptr [rax+rax+00h]
0x140060db7  mov     ebx, [rax]
0x140060db9  test    ebx, ebx
0x140060dbb  jle     loc_140060EC3
0x140060dc1  movzx   ebx, bx
0x140060dc4  jmp     short loc_140060D82
0x140060dc6  mov     ecx, eax; FileHandle
0x140060dc8  call    cs:__imp__get_osfhandle
0x140060dcf  nop     dword ptr [rax+rax+00h]
0x140060dd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140060dd8  jz      short loc_140060DAB
0x140060dda  lea     rdx, [rsp+0C8h+FileInformation]; lpFileInformation
0x140060ddf  mov     rcx, rax; hFile
0x140060de2  call    cs:__imp_GetFileInformationByHandle
0x140060de9  nop     dword ptr [rax+rax+00h]
0x140060dee  mov     edi, 80070000h
0x140060df3  test    eax, eax
0x140060df5  jnz     short loc_140060E26
0x140060df7  call    cs:__imp_GetLastError
0x140060dfe  nop     dword ptr [rax+rax+00h]
0x140060e03  test    eax, eax
0x140060e05  jz      short loc_140060E26
0x140060e07  call    cs:__imp_GetLastError
0x140060e0e  nop     dword ptr [rax+rax+00h]
0x140060e13  mov     ebx, eax
0x140060e15  test    eax, eax
0x140060e17  jle     short loc_140060E1E
0x140060e19  movzx   ebx, ax
0x140060e1c  or      ebx, edi
0x140060e1e  test    ebx, ebx
0x140060e20  js      loc_140060EC3
0x140060e26  lea     rdx, [rsp+0C8h+LocalFileTime]; lpLocalFileTime
0x140060e2b  lea     rcx, [rsp+0C8h+FileInformation.ftLastWriteTime]; lpFileTime
0x140060e30  call    cs:__imp_FileTimeToLocalFileTime
0x140060e37  nop     dword ptr [rax+rax+00h]
0x140060e3c  test    eax, eax
0x140060e3e  jnz     short loc_140060E6B
0x140060e40  call    cs:__imp_GetLastError
0x140060e47  nop     dword ptr [rax+rax+00h]
0x140060e4c  test    eax, eax
0x140060e4e  jz      short loc_140060E6B
0x140060e50  call    cs:__imp_GetLastError
0x140060e57  nop     dword ptr [rax+rax+00h]
0x140060e5c  mov     ebx, eax
0x140060e5e  test    eax, eax
0x140060e60  jle     short loc_140060E67
0x140060e62  movzx   ebx, ax
0x140060e65  or      ebx, edi
0x140060e67  test    ebx, ebx
0x140060e69  js      short loc_140060EC3
0x140060e6b  mov     r8, r12; lpFatTime
0x140060e6e  lea     rcx, [rsp+0C8h+LocalFileTime]; lpFileTime
0x140060e73  mov     rdx, r15; lpFatDate
0x140060e76  call    cs:__imp_FileTimeToDosDateTime
0x140060e7d  nop     dword ptr [rax+rax+00h]
0x140060e82  test    eax, eax
0x140060e84  jz      short loc_140060E8A
0x140060e86  xor     ebx, ebx
0x140060e88  jmp     short loc_140060EB5
0x140060e8a  call    cs:__imp_GetLastError
0x140060e91  nop     dword ptr [rax+rax+00h]
0x140060e96  test    eax, eax
0x140060e98  jz      short loc_140060E86
0x140060e9a  call    cs:__imp_GetLastError
0x140060ea1  nop     dword ptr [rax+rax+00h]
0x140060ea6  mov     ebx, eax
0x140060ea8  test    eax, eax
0x140060eaa  jle     short loc_140060EB1
0x140060eac  movzx   ebx, ax
0x140060eaf  or      ebx, edi
0x140060eb1  test    ebx, ebx
0x140060eb3  js      short loc_140060EC3
0x140060eb5  movzx   eax, word ptr [rsp+0C8h+FileInformation.dwFileAttributes]
0x140060eba  and     ax, 27h
0x140060ebe  mov     [r13+0], ax
0x140060ec3  call    cs:__imp_GetProcessHeap
0x140060eca  nop     dword ptr [rax+rax+00h]
0x140060ecf  mov     r8, rbp; lpMem
0x140060ed2  xor     edx, edx; dwFlags
0x140060ed4  mov     rcx, rax; hHeap
0x140060ed7  call    cs:__imp_HeapFree
0x140060ede  nop     dword ptr [rax+rax+00h]
0x140060ee3  test    ebx, ebx
0x140060ee5  jns     short loc_140060EF4
0x140060ee7  mov     rcx, [rsp+0C8h+var_90]
0x140060eec  or      rax, 0FFFFFFFFFFFFFFFFh
0x140060ef0  mov     [rcx], ebx
0x140060ef2  jmp     short loc_140060EF7
0x140060ef4  movsxd  rax, esi
0x140060ef7  mov     rcx, [rsp+0C8h+var_50]
0x140060efc  xor     rcx, rsp; StackCookie
0x140060eff  call    __security_check_cookie
0x140060f04  add     rsp, 88h
0x140060f0b  pop     r15
0x140060f0d  pop     r14
0x140060f0f  pop     r13
0x140060f11  pop     r12
0x140060f13  pop     rdi
0x140060f14  pop     rsi
0x140060f15  pop     rbp
0x140060f16  pop     rbx
0x140060f17  retn
```
