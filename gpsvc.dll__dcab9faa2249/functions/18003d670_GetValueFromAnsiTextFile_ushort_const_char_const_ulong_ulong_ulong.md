# GetValueFromAnsiTextFile(ushort const *,char const *,ulong,ulong,ulong *)

- ea: `0x18003d670`
- end: `0x18003d8c8`
- name: `?GetValueFromAnsiTextFile@@YAKPEBGPEBDKKPEAK@Z`
- size: `600`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR lpFileName@<rcx>, const char *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003a810`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x18003d670`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18003d85b`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18003d85b`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18003d79d`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18003d79d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d842`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d869`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d842`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d883`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d6ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d6ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d891`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d891`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003d749`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003d749`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d710`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d710`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18003d827`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18003d827`

## pseudocode

```c
__int64 __fastcall GetValueFromAnsiTextFile(
        LPCWSTR lpFileName,
        const char *a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5)
{
  unsigned int *v6; // r14
  char *v7; // rdi
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  void *v10; // rbx
  DWORD v11; // esi
  const char *v12; // rsi
  __int64 v13; // r15
  char *v14; // rax
  const char *v15; // r8
  const char *v16; // r15
  __int64 v17; // rcx
  unsigned int v18; // esi
  char *v20; // [rsp+40h] [rbp-10h] BYREF
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF
  const char *v22; // [rsp+88h] [rbp+38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+48h] BYREF

  v22 = a2;
  v20 = 0;
  v21 = -1;
  NumberOfBytesRead = 0;
  if ( !lpFileName || (v6 = a5) == 0 )
  {
LABEL_31:
    LastError = 87;
    goto LABEL_32;
  }
  *a5 = 0;
  v20 = (char *)LocalAlloc(0x40u, 0x401u);
  v7 = v20;
  if ( !v20 )
  {
    LastError = 14;
LABEL_32:
    XHandle::~XHandle((void **)&v21);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v20);
    return LastError;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  v21 = (__int64)FileW;
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_32;
  }
  if ( ReadFile(FileW, v20, 0x400u, &NumberOfBytesRead, 0) )
  {
    v12 = v20;
    v20[NumberOfBytesRead] = 0;
    while ( 1 )
    {
      v13 = 0x100002600LL;
      if ( v12 >= &v7[NumberOfBytesRead] )
        goto LABEL_31;
      v14 = strchr(v12, 61);
      if ( !v14 )
        goto LABEL_31;
      v15 = v14 - 1;
      if ( v14 - 1 < v12 )
        goto LABEL_31;
      do
      {
        if ( *v15 > 0x20u )
          break;
        if ( !_bittest64(&v13, *v15) )
          break;
        --v15;
      }
      while ( v15 >= v12 );
      if ( v15 < v12 )
        goto LABEL_31;
      v16 = v14 + 1;
      *((_BYTE *)v15 + 1) = 0;
      v17 = 0x100002600LL;
      do
      {
        if ( *v15 <= 0x20u && _bittest64(&v17, *v15) )
          break;
        --v15;
      }
      while ( v15 >= v12 );
      if ( CompareStringA(0x7Fu, 1u, v15 + 1, -1, "Version", -1) == 2 )
      {
        v22 = 0;
        *(_DWORD *)_o__errno() = 0;
        v18 = _o_strtoul(v16, &v22, 10);
        if ( v16 != v22 && *(_DWORD *)_o__errno() != 34 )
        {
          *v6 = v18;
          LastError = 0;
          goto LABEL_32;
        }
        if ( v10 )
          CloseHandle(v10);
        v11 = 87;
        goto LABEL_30;
      }
      v12 = v16;
    }
  }
  v11 = GetLastError();
  if ( v10 )
    CloseHandle(v10);
LABEL_30:
  LocalFree(v7);
  return v11;
}

```

## disassembly

```asm
0x18003d670  mov     [rsp-28h+arg_10], rbx
0x18003d675  mov     [rsp-28h+NumberOfBytesRead], r9d
0x18003d67a  mov     [rsp-28h+arg_8], rdx
0x18003d67f  push    rbp
0x18003d680  push    rsi
0x18003d681  push    rdi
0x18003d682  push    r14
0x18003d684  push    r15
0x18003d686  mov     rbp, rsp
0x18003d689  sub     rsp, 50h
0x18003d68d  mov     [rbp+var_10], 0
0x18003d695  mov     rbx, rcx
0x18003d698  mov     [rbp+arg_0], 0FFFFFFFFFFFFFFFFh
0x18003d6a0  mov     [rbp+NumberOfBytesRead], 0
0x18003d6a7  test    rcx, rcx
0x18003d6aa  jz      loc_18003D89B
0x18003d6b0  mov     r14, [rbp+arg_20]
0x18003d6b4  test    r14, r14
0x18003d6b7  jz      loc_18003D89B
0x18003d6bd  mov     edx, 401h; uBytes
0x18003d6c2  mov     dword ptr [r14], 0
0x18003d6c9  mov     ecx, 40h ; '@'; uFlags
0x18003d6ce  call    cs:__imp_LocalAlloc
0x18003d6d4  mov     [rbp+var_10], rax
0x18003d6d8  mov     rdi, rax
0x18003d6db  test    rax, rax
0x18003d6de  jnz     short loc_18003D6E8
0x18003d6e0  lea     ebx, [rax+0Eh]
0x18003d6e3  jmp     loc_18003D8A0
0x18003d6e8  xor     r9d, r9d; lpSecurityAttributes
0x18003d6eb  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18003d6f4  mov     [rsp+50h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18003d6fc  mov     edx, 80000000h; dwDesiredAccess
0x18003d701  mov     rcx, rbx; lpFileName
0x18003d704  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x18003d70c  lea     r8d, [r9+1]; dwShareMode
0x18003d710  call    cs:__imp_CreateFileW
0x18003d716  mov     [rbp+arg_0], rax
0x18003d71a  mov     rbx, rax
0x18003d71d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d721  jnz     short loc_18003D730
0x18003d723  call    cs:__imp_GetLastError
0x18003d729  mov     ebx, eax
0x18003d72b  jmp     loc_18003D8A0
0x18003d730  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003d734  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x18003d73d  mov     r8d, 400h; nNumberOfBytesToRead
0x18003d743  mov     rdx, rdi; lpBuffer
0x18003d746  mov     rcx, rbx; hFile
0x18003d749  call    cs:__imp_ReadFile
0x18003d74f  test    eax, eax
0x18003d751  jnz     short loc_18003D772
0x18003d753  call    cs:__imp_GetLastError
0x18003d759  mov     esi, eax
0x18003d75b  test    rbx, rbx
0x18003d75e  jz      loc_18003D88E
0x18003d764  mov     rcx, rbx; hObject
0x18003d767  call    cs:__imp_CloseHandle
0x18003d76d  jmp     loc_18003D88E
0x18003d772  mov     eax, [rbp+NumberOfBytesRead]
0x18003d775  mov     rsi, rdi
0x18003d778  mov     byte ptr [rax+rdi], 0
0x18003d77c  mov     eax, [rbp+NumberOfBytesRead]
0x18003d77f  mov     r15, 100002600h
0x18003d789  add     rax, rdi
0x18003d78c  cmp     rsi, rax
0x18003d78f  jnb     loc_18003D89B
0x18003d795  mov     edx, 3Dh ; '='; Val
0x18003d79a  mov     rcx, rsi; Str
0x18003d79d  call    cs:__imp_strchr
0x18003d7a3  test    rax, rax
0x18003d7a6  jz      loc_18003D89B
0x18003d7ac  lea     r8, [rax-1]
0x18003d7b0  cmp     r8, rsi
0x18003d7b3  jb      loc_18003D89B
0x18003d7b9  cmp     byte ptr [r8], 20h ; ' '
0x18003d7bd  ja      short loc_18003D7D1
0x18003d7bf  movsx   rcx, byte ptr [r8]
0x18003d7c3  bt      r15, rcx
0x18003d7c7  jnb     short loc_18003D7D1
0x18003d7c9  dec     r8
0x18003d7cc  cmp     r8, rsi
0x18003d7cf  jnb     short loc_18003D7B9
0x18003d7d1  cmp     r8, rsi
0x18003d7d4  jb      loc_18003D89B
0x18003d7da  lea     r15, [rax+1]
0x18003d7de  mov     byte ptr [r8+1], 0
0x18003d7e3  mov     rcx, 100002600h
0x18003d7ed  cmp     byte ptr [r8], 20h ; ' '
0x18003d7f1  ja      short loc_18003D7FD
0x18003d7f3  movsx   rax, byte ptr [r8]
0x18003d7f7  bt      rcx, rax
0x18003d7fb  jb      short loc_18003D805
0x18003d7fd  dec     r8
0x18003d800  cmp     r8, rsi
0x18003d803  jnb     short loc_18003D7ED
0x18003d805  or      r9d, 0FFFFFFFFh; cchCount1
0x18003d809  mov     [rsp+50h+dwFlagsAndAttributes], 0FFFFFFFFh; cchCount2
0x18003d811  lea     rax, aVersion_0; "Version"
0x18003d818  inc     r8; lpString1
0x18003d81b  mov     qword ptr [rsp+50h+dwCreationDisposition], rax; lpString2
0x18003d820  lea     edx, [r9+2]; dwCmpFlags
0x18003d824  lea     ecx, [rdx+7Eh]; Locale
0x18003d827  call    cs:__imp_CompareStringA
0x18003d82d  cmp     eax, 2
0x18003d830  jz      short loc_18003D83A
0x18003d832  mov     rsi, r15
0x18003d835  jmp     loc_18003D77C
0x18003d83a  mov     [rbp+arg_8], 0
0x18003d842  call    cs:__imp__o__errno
0x18003d848  mov     r8d, 0Ah
0x18003d84e  lea     rdx, [rbp+arg_8]
0x18003d852  mov     rcx, r15
0x18003d855  mov     dword ptr [rax], 0
0x18003d85b  call    cs:__imp__o_strtoul
0x18003d861  mov     esi, eax
0x18003d863  cmp     r15, [rbp+arg_8]
0x18003d867  jz      short loc_18003D87B
0x18003d869  call    cs:__imp__o__errno
0x18003d86f  cmp     dword ptr [rax], 22h ; '"'
0x18003d872  jz      short loc_18003D87B
0x18003d874  mov     [r14], esi
0x18003d877  xor     ebx, ebx
0x18003d879  jmp     short loc_18003D8A0
0x18003d87b  test    rbx, rbx
0x18003d87e  jz      short loc_18003D889
0x18003d880  mov     rcx, rbx; hObject
0x18003d883  call    cs:__imp_CloseHandle
0x18003d889  mov     esi, 57h ; 'W'
0x18003d88e  mov     rcx, rdi; hMem
0x18003d891  call    cs:__imp_LocalFree
0x18003d897  mov     eax, esi
0x18003d899  jmp     short loc_18003D8B4
0x18003d89b  mov     ebx, 57h ; 'W'
0x18003d8a0  lea     rcx, [rbp+arg_0]; this
0x18003d8a4  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18003d8a9  lea     rcx, [rbp+var_10]
0x18003d8ad  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18003d8b2  mov     eax, ebx
0x18003d8b4  mov     rbx, [rsp+50h+arg_10]
0x18003d8bc  add     rsp, 50h
0x18003d8c0  pop     r15
0x18003d8c2  pop     r14
0x18003d8c4  pop     rdi
0x18003d8c5  pop     rsi
0x18003d8c6  pop     rbp
0x18003d8c7  retn
```
