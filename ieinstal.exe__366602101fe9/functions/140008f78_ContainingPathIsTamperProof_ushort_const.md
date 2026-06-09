# ContainingPathIsTamperProof(ushort const *)

- ea: `0x140008f78`
- end: `0x140009237`
- name: `?ContainingPathIsTamperProof@@YAHPEBG@Z`
- size: `703`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140004738`
- `0x140004c88`
- `0x140004e20`
- `0x140005188`
- `0x140005630`
- `0x140005b10`
- `0x14000747c`

## callees

- `0x140008f78`
- `0x140009900`
- `0x140009a08`
- `0x140009e84`
- `0x14000b8e0`
- `0x1400105d8`
- `0x140010768`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400091e8`
- `KERNEL32!CloseHandle` at `0x1400091e8`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140009137`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14000916e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140009137`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14000916e`
- `KERNEL32!LocalFree` at `0x1400091fc`
- `KERNEL32!LocalFree` at `0x1400091fc`
- `KERNEL32!GetFileAttributesW` at `0x14000905b`
- `KERNEL32!GetFileAttributesW` at `0x1400090ac`
- `KERNEL32!GetFileAttributesW` at `0x14000905b`
- `KERNEL32!GetFileAttributesW` at `0x1400090ac`
- `KERNEL32!CreateFileW` at `0x140009110`
- `KERNEL32!CreateFileW` at `0x140009110`
- `KERNEL32!GetLastError` at `0x140009069`
- `KERNEL32!GetLastError` at `0x1400090ba`
- `KERNEL32!GetLastError` at `0x140009069`
- `KERNEL32!GetLastError` at `0x1400090ba`
- `ole32!CoTaskMemAlloc` at `0x140008fce`
- `ole32!CoTaskMemAlloc` at `0x14000914e`
- `ole32!CoTaskMemAlloc` at `0x140008fce`
- `ole32!CoTaskMemAlloc` at `0x14000914e`
- `ole32!CoTaskMemFree` at `0x140009210`
- `ole32!CoTaskMemFree` at `0x140009210`
- `iertutil!__imp_?IsProtectedModeCOMCaller@@YAJPEAH@Z` at `0x140008ffb`
- `iertutil!__imp_?IsProtectedModeCOMCaller@@YAJPEAH@Z` at `0x140008ffb`

## pseudocode

```c
__int64 __fastcall ContainingPathIsTamperProof(const unsigned __int16 *a1)
{
  void *v2; // r14
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rbp
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  unsigned int IsNotLowIL; // ebx
  int CallerSid; // eax
  DWORD FileAttributesW; // esi
  DWORD LastError; // eax
  size_t v11; // rdx
  size_t v12; // rdx
  HANDLE FileW; // rax
  void *v14; // r15
  DWORD FinalPathNameByHandleW; // eax
  DWORD v16; // ebp
  WCHAR *v17; // rax
  WCHAR *v18; // rsi
  DWORD v19; // ebp
  unsigned int v20; // ebp
  HRESULT v21; // eax
  __int64 v22; // rbp
  unsigned __int16 **dwCreationDisposition; // [rsp+20h] [rbp-58h]
  unsigned __int64 *dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  unsigned int hTemplateFile; // [rsp+30h] [rbp-48h]
  int v27; // [rsp+80h] [rbp+8h] BYREF
  void *v28; // [rsp+88h] [rbp+10h] BYREF

  v27 = 0;
  v28 = 0;
  v2 = 0;
  if ( !a1 )
    goto LABEL_10;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  v4 = v3 + 1;
  if ( v3 + 1 >= v3 && is_mul_ok(v4, 2u) )
  {
    v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v4);
    v6 = v5;
    if ( v5 )
    {
      StringCchCopyNExW(v5, v3 + 1, a1, v3, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
      if ( (int)IsProtectedModeCOMCaller(&v27) < 0 )
      {
        IsNotLowIL = 0;
LABEL_48:
        CoTaskMemFree(v6);
        return IsNotLowIL;
      }
      IsNotLowIL = 1;
      goto LABEL_12;
    }
  }
  else
  {
LABEL_10:
    v6 = 0;
  }
  IsNotLowIL = 0;
LABEL_12:
  if ( v27 )
  {
    CallerSid = GetCallerSid(&v28);
    v2 = v28;
    if ( CallerSid < 0 || !v28 )
      goto LABEL_29;
  }
  if ( !IsNotLowIL )
    goto LABEL_45;
  FileAttributesW = GetFileAttributesW(v6);
  LastError = GetLastError();
  if ( FileAttributesW != -1 )
    goto LABEL_27;
  do
  {
    if ( LastError - 2 > 1 )
      break;
    if ( PathCchIsRoot(v6) )
      break;
    v11 = -1;
    do
      ++v11;
    while ( v6[v11] );
    if ( PathCchRemoveFileSpec(v6, v11) < 0 )
      break;
    FileAttributesW = GetFileAttributesW(v6);
    LastError = GetLastError();
  }
  while ( FileAttributesW == -1 );
  if ( FileAttributesW != -1 )
  {
LABEL_27:
    if ( (FileAttributesW & 0x10) == 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v6[v12] );
      if ( PathCchRemoveFileSpec(v6, v12) < 0 )
        goto LABEL_29;
    }
  }
  FileW = CreateFileW(v6, 0x20000u, 0, 0, 3u, 0x2000000u, 0);
  v14 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
    v16 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW
      && (v17 = (WCHAR *)CoTaskMemAlloc(2LL * FinalPathNameByHandleW), (v18 = v17) != 0)
      && (v19 = GetFinalPathNameByHandleW(v14, v17, v16, 0)) != 0 )
    {
      v20 = v19 + 1;
      do
      {
        if ( v20 < 8 )
          break;
        IsNotLowIL = DirectoryIsNotLowIL(v18);
        if ( IsNotLowIL && v27 )
          IsNotLowIL = DirectoryIsNotWritableBySid(v18, v2);
        if ( PathCchIsRoot(v18) )
          break;
        if ( !IsNotLowIL )
          break;
        v21 = PathCchRemoveFileSpec(v18, v20);
        v22 = -1;
        IsNotLowIL = v21 >= 0;
        do
          ++v22;
        while ( v18[v22] );
        v20 = v22 + 1;
      }
      while ( v21 >= 0 );
    }
    else
    {
      IsNotLowIL = 0;
    }
    CloseHandle(v14);
  }
  else
  {
LABEL_29:
    IsNotLowIL = 0;
  }
LABEL_45:
  if ( v2 )
    LocalFree(v2);
  if ( v6 )
    goto LABEL_48;
  return IsNotLowIL;
}

```

## disassembly

```asm
0x140008f78  mov     rax, rsp
0x140008f7b  mov     [rax+20h], rbx
0x140008f7f  push    rbp
0x140008f80  push    rsi
0x140008f81  push    rdi
0x140008f82  push    r12
0x140008f84  push    r13
0x140008f86  push    r14
0x140008f88  push    r15
0x140008f8a  sub     rsp, 40h
0x140008f8e  xor     r12d, r12d
0x140008f91  or      r13, 0FFFFFFFFFFFFFFFFh
0x140008f95  mov     [rax+8], r12d
0x140008f99  mov     rsi, rcx
0x140008f9c  mov     [rax+10h], r12
0x140008fa0  mov     r14d, r12d
0x140008fa3  test    rcx, rcx
0x140008fa6  jz      short loc_14000901A
0x140008fa8  mov     rbx, r13
0x140008fab  inc     rbx
0x140008fae  cmp     [rcx+rbx*2], r12w
0x140008fb3  jnz     short loc_140008FAB
0x140008fb5  lea     rbp, [rbx+1]
0x140008fb9  cmp     rbp, rbx
0x140008fbc  jb      short loc_14000901A
0x140008fbe  mov     eax, 2
0x140008fc3  mul     rbp
0x140008fc6  test    rdx, rdx
0x140008fc9  jnz     short loc_14000901A
0x140008fcb  mov     rcx, rax; cb
0x140008fce  call    cs:__imp_CoTaskMemAlloc
0x140008fd5  nop     dword ptr [rax+rax+00h]
0x140008fda  mov     rdi, rax
0x140008fdd  test    rax, rax
0x140008fe0  jz      short loc_14000901D
0x140008fe2  mov     r9, rbx; unsigned __int64
0x140008fe5  mov     r8, rsi; unsigned __int16 *
0x140008fe8  mov     rdx, rbp; unsigned __int64
0x140008feb  mov     rcx, rax; unsigned __int16 *
0x140008fee  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x140008ff3  lea     rcx, [rsp+78h+arg_0]
0x140008ffb  call    cs:__imp_?IsProtectedModeCOMCaller@@YAJPEAH@Z; IsProtectedModeCOMCaller(int *)
0x140009002  nop     dword ptr [rax+rax+00h]
0x140009007  test    eax, eax
0x140009009  jns     short loc_140009013
0x14000900b  mov     ebx, r12d
0x14000900e  jmp     loc_14000920D
0x140009013  mov     ebx, 1
0x140009018  jmp     short loc_140009020
0x14000901a  mov     rdi, r12
0x14000901d  mov     ebx, r12d
0x140009020  cmp     [rsp+78h+arg_0], r12d
0x140009028  jz      short loc_140009050
0x14000902a  lea     rcx, [rsp+78h+arg_8]
0x140009032  call    GetCallerSid
0x140009037  mov     r14, [rsp+78h+arg_8]
0x14000903f  test    eax, eax
0x140009041  js      loc_140009124
0x140009047  test    r14, r14
0x14000904a  jz      loc_140009124
0x140009050  test    ebx, ebx
0x140009052  jz      loc_1400091F4
0x140009058  mov     rcx, rdi; lpFileName
0x14000905b  call    cs:__imp_GetFileAttributesW
0x140009062  nop     dword ptr [rax+rax+00h]
0x140009067  mov     esi, eax
0x140009069  call    cs:__imp_GetLastError
0x140009070  nop     dword ptr [rax+rax+00h]
0x140009075  or      ebp, 0FFFFFFFFh
0x140009078  cmp     esi, ebp
0x14000907a  jnz     short loc_1400090CE
0x14000907c  lea     ecx, [rax-2]
0x14000907f  cmp     ecx, 1
0x140009082  ja      short loc_1400090CA
0x140009084  mov     rcx, rdi; pszPath
0x140009087  call    PathCchIsRoot
0x14000908c  test    eax, eax
0x14000908e  jnz     short loc_1400090CA
0x140009090  mov     rdx, r13
0x140009093  inc     rdx; cchPath
0x140009096  cmp     [rdi+rdx*2], r12w
0x14000909b  jnz     short loc_140009093
0x14000909d  mov     rcx, rdi; pszPath
0x1400090a0  call    PathCchRemoveFileSpec
0x1400090a5  test    eax, eax
0x1400090a7  js      short loc_1400090CA
0x1400090a9  mov     rcx, rdi; lpFileName
0x1400090ac  call    cs:__imp_GetFileAttributesW
0x1400090b3  nop     dword ptr [rax+rax+00h]
0x1400090b8  mov     esi, eax
0x1400090ba  call    cs:__imp_GetLastError
0x1400090c1  nop     dword ptr [rax+rax+00h]
0x1400090c6  cmp     esi, ebp
0x1400090c8  jz      short loc_14000907C
0x1400090ca  cmp     esi, ebp
0x1400090cc  jz      short loc_1400090ED
0x1400090ce  test    sil, 10h
0x1400090d2  jnz     short loc_1400090ED
0x1400090d4  mov     rdx, r13
0x1400090d7  inc     rdx; cchPath
0x1400090da  cmp     [rdi+rdx*2], r12w
0x1400090df  jnz     short loc_1400090D7
0x1400090e1  mov     rcx, rdi; pszPath
0x1400090e4  call    PathCchRemoveFileSpec
0x1400090e9  test    eax, eax
0x1400090eb  js      short loc_140009124
0x1400090ed  mov     qword ptr [rsp+78h+hTemplateFile], r12; hTemplateFile
0x1400090f2  xor     r9d, r9d; lpSecurityAttributes
0x1400090f5  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400090fd  xor     r8d, r8d; dwShareMode
0x140009100  mov     edx, 20000h; dwDesiredAccess
0x140009105  mov     dword ptr [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x14000910d  mov     rcx, rdi; lpFileName
0x140009110  call    cs:__imp_CreateFileW
0x140009117  nop     dword ptr [rax+rax+00h]
0x14000911c  mov     r15, rax
0x14000911f  cmp     rax, r13
0x140009122  jnz     short loc_14000912C
0x140009124  mov     ebx, r12d
0x140009127  jmp     loc_1400091F4
0x14000912c  xor     r9d, r9d; dwFlags
0x14000912f  xor     r8d, r8d; cchFilePath
0x140009132  xor     edx, edx; lpszFilePath
0x140009134  mov     rcx, r15; hFile
0x140009137  call    cs:__imp_GetFinalPathNameByHandleW
0x14000913e  nop     dword ptr [rax+rax+00h]
0x140009143  mov     ebp, eax
0x140009145  test    eax, eax
0x140009147  jz      short loc_140009180
0x140009149  mov     ecx, ebp
0x14000914b  add     rcx, rcx; cb
0x14000914e  call    cs:__imp_CoTaskMemAlloc
0x140009155  nop     dword ptr [rax+rax+00h]
0x14000915a  mov     rsi, rax
0x14000915d  test    rax, rax
0x140009160  jz      short loc_140009180
0x140009162  xor     r9d, r9d; dwFlags
0x140009165  mov     r8d, ebp; cchFilePath
0x140009168  mov     rdx, rax; lpszFilePath
0x14000916b  mov     rcx, r15; hFile
0x14000916e  call    cs:__imp_GetFinalPathNameByHandleW
0x140009175  nop     dword ptr [rax+rax+00h]
0x14000917a  mov     ebp, eax
0x14000917c  test    eax, eax
0x14000917e  jnz     short loc_140009185
0x140009180  mov     ebx, r12d
0x140009183  jmp     short loc_1400091E5
0x140009185  inc     ebp
0x140009187  cmp     ebp, 8
0x14000918a  jb      short loc_1400091E5
0x14000918c  mov     rcx, rsi; pszPath
0x14000918f  call    DirectoryIsNotLowIL
0x140009194  mov     ebx, eax
0x140009196  test    eax, eax
0x140009198  jz      short loc_1400091B1
0x14000919a  cmp     [rsp+78h+arg_0], r12d
0x1400091a2  jz      short loc_1400091B1
0x1400091a4  mov     rdx, r14
0x1400091a7  mov     rcx, rsi
0x1400091aa  call    DirectoryIsNotWritableBySid
0x1400091af  mov     ebx, eax
0x1400091b1  mov     rcx, rsi; pszPath
0x1400091b4  call    PathCchIsRoot
0x1400091b9  test    eax, eax
0x1400091bb  jnz     short loc_1400091E5
0x1400091bd  test    ebx, ebx
0x1400091bf  jz      short loc_1400091E5
0x1400091c1  mov     edx, ebp; cchPath
0x1400091c3  mov     rcx, rsi; pszPath
0x1400091c6  call    PathCchRemoveFileSpec
0x1400091cb  mov     ebx, eax
0x1400091cd  mov     rbp, r13
0x1400091d0  not     ebx
0x1400091d2  shr     ebx, 1Fh
0x1400091d5  inc     rbp
0x1400091d8  cmp     [rsi+rbp*2], r12w
0x1400091dd  jnz     short loc_1400091D5
0x1400091df  inc     ebp
0x1400091e1  test    ebx, ebx
0x1400091e3  jnz     short loc_140009187
0x1400091e5  mov     rcx, r15; hObject
0x1400091e8  call    cs:__imp_CloseHandle
0x1400091ef  nop     dword ptr [rax+rax+00h]
0x1400091f4  test    r14, r14
0x1400091f7  jz      short loc_140009208
0x1400091f9  mov     rcx, r14; hMem
0x1400091fc  call    cs:__imp_LocalFree
0x140009203  nop     dword ptr [rax+rax+00h]
0x140009208  test    rdi, rdi
0x14000920b  jz      short loc_14000921C
0x14000920d  mov     rcx, rdi; pv
0x140009210  call    cs:__imp_CoTaskMemFree
0x140009217  nop     dword ptr [rax+rax+00h]
0x14000921c  mov     eax, ebx
0x14000921e  mov     rbx, [rsp+78h+arg_18]
0x140009226  add     rsp, 40h
0x14000922a  pop     r15
0x14000922c  pop     r14
0x14000922e  pop     r13
0x140009230  pop     r12
0x140009232  pop     rdi
0x140009233  pop     rsi
0x140009234  pop     rbp
0x140009235  retn
```
