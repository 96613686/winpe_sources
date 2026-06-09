# TrControl::GetTraceFileName(void)

- ea: `0x18009c35c`
- end: `0x18009c5f8`
- name: `?GetTraceFileName@TrControl@@AEAAJXZ`
- size: `668`
- prototype: `int __fastcall(TrControl *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18009ccbc`

## callees

- `0x18000bb04`
- `0x180019364`
- `0x18009aa2c`
- `0x18009c35c`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009c47f`
- `KERNEL32!GetLastError` at `0x18009c47f`
- `KERNEL32!GetLocalTime` at `0x18009c560`
- `KERNEL32!GetLocalTime` at `0x18009c560`
- `KERNEL32!MoveFileExW` at `0x18009c548`
- `KERNEL32!MoveFileExW` at `0x18009c548`
- `KERNEL32!GetFileAttributesW` at `0x18009c474`
- `KERNEL32!GetFileAttributesW` at `0x18009c474`

## pseudocode

```c
int __fastcall TrControl::GetTraceFileName(TrControl *this)
{
  char *v1; // r15
  char *v3; // r14
  __int64 v4; // r11
  const WCHAR *v5; // rdi
  int result; // eax
  const wchar_t *v7; // rbx
  int v8; // ebx
  unsigned __int64 v9; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v10; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v11; // [rsp+78h] [rbp-88h] BYREF
  int v12; // [rsp+80h] [rbp-80h] BYREF
  char *v13; // [rsp+88h] [rbp-78h]
  char *v14; // [rsp+90h] [rbp-70h]
  int v15; // [rsp+98h] [rbp-68h]
  __int64 v16; // [rsp+A0h] [rbp-60h]
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR NewFileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = (char *)this + 526;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  if ( (unsigned int)StringCchLengthW((const wchar_t *)this + 263, 0x105u, &v9) )
    return -2147467259;
  if ( !v9 )
    return -2147467259;
  v3 = (char *)this + 1048;
  if ( (unsigned int)StringCchLengthW((const wchar_t *)this + 524, 0x105u, &v10)
    || !v10
    || (unsigned int)StringCchLengthW((const wchar_t *)this + 785, 0x105u, &v11)
    || !v11 )
  {
    return -2147467259;
  }
  v5 = (const WCHAR *)((char *)this + 7748);
  result = StringCchPrintfW((wchar_t *)this + 3874, 0x105u, L"%s\\%s%s", v1, (char *)this + 1048, v4);
  if ( result < 0 )
    return result;
  if ( (unsigned int)StringCchLengthW((const wchar_t *)this + 3874, 0x105u, (unsigned __int64 *)this + 1034) )
  {
LABEL_17:
    *((_DWORD *)this + 2068) = 0;
    return 87;
  }
  if ( GetFileAttributesW((LPCWSTR)this + 3874) == -1 && GetLastError() == 2 )
  {
    result = StringCchLengthW((const wchar_t *)this + 3874, 0x105u, (unsigned __int64 *)this + 1034);
    if ( !result )
      return result;
    goto LABEL_17;
  }
  v12 = 0;
  v13 = (char *)this + 2628;
  v15 = 0;
  v16 = 0;
  v14 = (char *)this + 6724;
  QueryValueInternal((struct RegEntry *)&v12);
  v7 = (const wchar_t *)((char *)this + 2092);
  if ( (unsigned int)StringCchLengthW(v7, 0x105u, (unsigned __int64 *)&SystemTime.wYear)
    || !*(_QWORD *)&SystemTime.wYear )
  {
    return 87;
  }
  result = StringCchPrintfW(NewFileName, 0x105u, L"%s\\%s%s", v1, v3, v7);
  v8 = result;
  if ( result >= 0 )
  {
    MoveFileExW(v5, NewFileName, 1u);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18009c35c  push    rbp
0x18009c35e  push    rbx
0x18009c35f  push    rsi
0x18009c360  push    rdi
0x18009c361  push    r12
0x18009c363  push    r13
0x18009c365  push    r14
0x18009c367  push    r15
0x18009c369  lea     rbp, [rsp-1E8h]
0x18009c371  sub     rsp, 2E8h
0x18009c378  mov     rax, cs:__security_cookie
0x18009c37f  xor     rax, rsp
0x18009c382  mov     [rbp+220h+var_50], rax
0x18009c389  xor     r12d, r12d
0x18009c38c  lea     r15, [rcx+20Eh]
0x18009c393  mov     rbx, rcx
0x18009c396  mov     [rsp+320h+var_2B8], r12
0x18009c39b  mov     r13d, 105h
0x18009c3a1  mov     [rsp+320h+var_2B0], r12
0x18009c3a6  mov     edx, r13d; unsigned __int64
0x18009c3a9  mov     [rsp+320h+var_2A8], r12
0x18009c3ae  mov     rcx, r15; wchar_t *
0x18009c3b1  mov     qword ptr [rbp+220h+SystemTime.wYear], r12
0x18009c3b5  lea     r8, [rsp+320h+var_2B8]; unsigned __int64 *
0x18009c3ba  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18009c3bf  test    eax, eax
0x18009c3c1  jnz     loc_18009C5D0
0x18009c3c7  cmp     [rsp+320h+var_2B8], r12
0x18009c3cc  jz      loc_18009C5D0
0x18009c3d2  lea     r14, [rbx+418h]
0x18009c3d9  mov     edx, r13d; unsigned __int64
0x18009c3dc  mov     rcx, r14; wchar_t *
0x18009c3df  lea     r8, [rsp+320h+var_2B0]; unsigned __int64 *
0x18009c3e4  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18009c3e9  test    eax, eax
0x18009c3eb  jnz     loc_18009C5D0
0x18009c3f1  cmp     [rsp+320h+var_2B0], r12
0x18009c3f6  jz      loc_18009C5D0
0x18009c3fc  lea     r11, [rbx+622h]
0x18009c403  mov     edx, r13d; unsigned __int64
0x18009c406  mov     rcx, r11; wchar_t *
0x18009c409  lea     r8, [rsp+320h+var_2A8]; unsigned __int64 *
0x18009c40e  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18009c413  test    eax, eax
0x18009c415  jnz     loc_18009C5D0
0x18009c41b  cmp     [rsp+320h+var_2A8], r12
0x18009c420  jz      loc_18009C5D0
0x18009c426  mov     [rsp+320h+var_2F8], r11
0x18009c42b  lea     rdi, [rbx+1E44h]
0x18009c432  mov     rcx, rdi; wchar_t *
0x18009c435  mov     [rsp+320h+var_300], r14
0x18009c43a  mov     r9, r15
0x18009c43d  lea     r8, aSSS_2; "%s\\%s%s"
0x18009c444  mov     edx, r13d; unsigned __int64
0x18009c447  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009c44c  test    eax, eax
0x18009c44e  js      loc_18009C5D5
0x18009c454  lea     rsi, [rbx+2050h]
0x18009c45b  mov     edx, r13d; unsigned __int64
0x18009c45e  mov     r8, rsi; unsigned __int64 *
0x18009c461  mov     rcx, rdi; wchar_t *
0x18009c464  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18009c469  test    eax, eax
0x18009c46b  jnz     loc_18009C5C6
0x18009c471  mov     rcx, rdi; lpFileName
0x18009c474  call    cs:__imp_GetFileAttributesW
0x18009c47a  cmp     eax, 0FFFFFFFFh
0x18009c47d  jnz     short loc_18009C4A5
0x18009c47f  call    cs:__imp_GetLastError
0x18009c485  cmp     eax, 2
0x18009c488  jnz     short loc_18009C4A5
0x18009c48a  mov     r8, rsi; unsigned __int64 *
0x18009c48d  mov     edx, r13d; unsigned __int64
0x18009c490  mov     rcx, rdi; wchar_t *
0x18009c493  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18009c498  test    eax, eax
0x18009c49a  jnz     loc_18009C5C6
0x18009c4a0  jmp     loc_18009C5D5
0x18009c4a5  lea     rax, [rbx+0A44h]
0x18009c4ac  mov     [rbp+220h+var_2A0], r12d
0x18009c4b0  mov     [rbp+220h+var_298], rax
0x18009c4b4  lea     r8, [rsp+320h+var_2C0]
0x18009c4b9  mov     edx, 4
0x18009c4be  mov     [rbp+220h+var_288], r12d
0x18009c4c2  lea     rax, [rbx+1A44h]
0x18009c4c9  mov     [rbp+220h+var_280], r12
0x18009c4cd  mov     r9d, edx
0x18009c4d0  mov     [rbp+220h+var_290], rax
0x18009c4d4  lea     rcx, [rbp+220h+var_2A0]; struct RegEntry *
0x18009c4d8  mov     [rsp+320h+var_2C0], r12d
0x18009c4dd  call    QueryValueInternal
0x18009c4e2  cmp     [rsp+320h+var_2C0], r12d
0x18009c4e7  jnz     short loc_18009C555
0x18009c4e9  add     rbx, 82Ch
0x18009c4f0  lea     r8, [rbp+220h+SystemTime]; unsigned __int64 *
0x18009c4f4  mov     rcx, rbx; wchar_t *
0x18009c4f7  mov     rdx, r13; unsigned __int64
0x18009c4fa  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18009c4ff  test    eax, eax
0x18009c501  jnz     loc_18009C5C9
0x18009c507  cmp     qword ptr [rbp+220h+SystemTime.wYear], r12
0x18009c50b  jz      loc_18009C5C9
0x18009c511  mov     [rsp+320h+var_2F8], rbx
0x18009c516  lea     r8, aSSS_2; "%s\\%s%s"
0x18009c51d  mov     r9, r15
0x18009c520  mov     [rsp+320h+var_300], r14
0x18009c525  mov     rdx, r13; unsigned __int64
0x18009c528  lea     rcx, [rbp+220h+NewFileName]; wchar_t *
0x18009c52c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009c531  mov     ebx, eax
0x18009c533  test    eax, eax
0x18009c535  js      loc_18009C5D5
0x18009c53b  mov     r8d, 1; dwFlags
0x18009c541  lea     rdx, [rbp+220h+NewFileName]; lpNewFileName
0x18009c545  mov     rcx, rdi; lpExistingFileName
0x18009c548  call    cs:__imp_MoveFileExW
0x18009c54e  mov     eax, ebx
0x18009c550  jmp     loc_18009C5D5
0x18009c555  xorps   xmm0, xmm0
0x18009c558  lea     rcx, [rbp+220h+SystemTime]; lpSystemTime
0x18009c55c  movups  xmmword ptr [rbp+220h+SystemTime.wYear], xmm0
0x18009c560  call    cs:__imp_GetLocalTime
0x18009c566  movzx   ecx, [rbp+220h+SystemTime.wSecond]
0x18009c56a  movzx   edx, [rbp+220h+SystemTime.wMinute]
0x18009c56e  movzx   r8d, [rbp+220h+SystemTime.wHour]
0x18009c573  movzx   r9d, [rbp+220h+SystemTime.wDay]
0x18009c578  movzx   eax, [rbp+220h+SystemTime.wMilliseconds]
0x18009c57c  movzx   r10d, [rbp+220h+SystemTime.wMonth]
0x18009c581  movzx   r11d, [rbp+220h+SystemTime.wYear]
0x18009c586  mov     [rsp+320h+var_2C8], eax
0x18009c58a  mov     [rsp+320h+var_2D0], ecx
0x18009c58e  lea     rcx, [rbp+220h+NewFileName]; wchar_t *
0x18009c592  mov     [rsp+320h+var_2D8], edx
0x18009c596  mov     rdx, r13; unsigned __int64
0x18009c599  mov     [rsp+320h+var_2E0], r8d
0x18009c59e  lea     r8, aSS04d02d02d02d; "%s\\%s%04d-%02d-%02d-%02d-%02d-%02d-%04"...
0x18009c5a5  mov     [rsp+320h+var_2E8], r9d
0x18009c5aa  mov     r9, r15
0x18009c5ad  mov     [rsp+320h+var_2F0], r10d
0x18009c5b2  mov     dword ptr [rsp+320h+var_2F8], r11d
0x18009c5b7  mov     [rsp+320h+var_300], r14
0x18009c5bc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009c5c1  jmp     loc_18009C531
0x18009c5c6  mov     [rsi], r12d
0x18009c5c9  mov     eax, 57h ; 'W'
0x18009c5ce  jmp     short loc_18009C5D5
0x18009c5d0  mov     eax, 80004005h
0x18009c5d5  mov     rcx, [rbp+220h+var_50]
0x18009c5dc  xor     rcx, rsp; StackCookie
0x18009c5df  call    __security_check_cookie
0x18009c5e4  add     rsp, 2E8h
0x18009c5eb  pop     r15
0x18009c5ed  pop     r14
0x18009c5ef  pop     r13
0x18009c5f1  pop     r12
0x18009c5f3  pop     rdi
0x18009c5f4  pop     rsi
0x18009c5f5  pop     rbx
0x18009c5f6  pop     rbp
0x18009c5f7  retn
```
