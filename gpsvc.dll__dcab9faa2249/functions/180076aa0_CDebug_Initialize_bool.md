# CDebug::Initialize(bool)

- ea: `0x180076aa0`
- end: `0x180076ca7`
- name: `?Initialize@CDebug@@AEAA_N_N@Z`
- size: `519`
- prototype: `bool __fastcall(CDebug *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180076950`
- `0x1800b7dd0`

## callees

- `0x18000a52c`
- `0x180072f8c`
- `0x180076aa0`
- `0x18007d320`
- `0x1800b8408`
- `0x1800b8480`
- `0x1800b8510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076b40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076b40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076aff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076aff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076b35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180076b35`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180076c4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180076c4e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180076bab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180076c00`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180076bab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180076c00`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076c1e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076c1e`

## pseudocode

```c
char __fastcall CDebug::Initialize(CDebug *this, char a2)
{
  BYTE *v2; // rdi
  const WCHAR *v4; // rdx
  const WCHAR *v6; // rdx
  LPCWSTR lpSrc; // [rsp+40h] [rbp-C0h] BYREF
  char v9; // [rsp+4Ch] [rbp-B4h]
  DWORD Type[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Dst[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NewFileName[264]; // [rsp+280h] [rbp+180h] BYREF

  v2 = (BYTE *)this + 68;
  *((_BYTE *)this + 64) = 0;
  *((_DWORD *)this + 17) = 0;
  v4 = *(const WCHAR **)this;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey) )
  {
    v6 = (const WCHAR *)*((_QWORD *)this + 2);
    Type[0] = 0;
    cbData = 4;
    RegQueryValueExW(hKey, v6, 0, Type, v2, &cbData);
    RegCloseKey(hKey);
  }
  if ( *(_DWORD *)v2 && a2 )
  {
    CWString::CWString((CWString *)&lpSrc);
    operator+((CWString *)Type, L"%systemroot%\\debug\\UserMode\\");
    CWString::operator=((CWString *)&lpSrc);
    CWString::Reset((CWString *)Type);
    if ( !v9 )
      goto LABEL_11;
    if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x105u) - 1 > 0x103 )
      goto LABEL_11;
    operator+((CWString *)Type, L"%systemroot%\\debug\\UserMode\\");
    CWString::operator=((CWString *)&lpSrc);
    CWString::Reset((CWString *)Type);
    if ( !v9 || ExpandEnvironmentStringsW(lpSrc, NewFileName, 0x105u) - 1 > 0x103 )
      goto LABEL_11;
    MoveFileExW(Dst, NewFileName, 1u);
    *(_QWORD *)Type = CreateFileW(Dst, 0x40000000u, 1u, 0, 2u, 0, 0);
    if ( *(_QWORD *)Type == -1 )
    {
      XHandle::~XHandle((void **)Type);
LABEL_11:
      CWString::Reset((CWString *)&lpSrc);
      return 0;
    }
    XHandle::~XHandle((void **)Type);
    CWString::Reset((CWString *)&lpSrc);
  }
  *((_BYTE *)this + 64) = 1;
  return 1;
}

```

## disassembly

```asm
0x180076aa0  push    rbp
0x180076aa2  push    rbx
0x180076aa3  push    rsi
0x180076aa4  push    rdi
0x180076aa5  lea     rbp, [rsp-3A8h]
0x180076aad  sub     rsp, 4A8h
0x180076ab4  mov     rax, cs:__security_cookie
0x180076abb  xor     rax, rsp
0x180076abe  mov     [rbp+3C0h+var_30], rax
0x180076ac5  lea     rdi, [rcx+44h]
0x180076ac9  mov     byte ptr [rcx+40h], 0
0x180076acd  mov     sil, dl
0x180076ad0  mov     dword ptr [rdi], 0
0x180076ad6  mov     rdx, [rcx]; lpSubKey
0x180076ad9  lea     rax, [rsp+4C0h+hKey]
0x180076ade  mov     rbx, rcx
0x180076ae1  mov     [rsp+4C0h+hKey], 0
0x180076aea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076af1  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180076af6  mov     r9d, 20019h; samDesired
0x180076afc  xor     r8d, r8d; ulOptions
0x180076aff  call    cs:__imp_RegOpenKeyExW
0x180076b05  test    eax, eax
0x180076b07  jnz     short loc_180076B46
0x180076b09  mov     rdx, [rbx+10h]; lpValueName
0x180076b0d  lea     r9, [rsp+4C0h+Type]; lpType
0x180076b12  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180076b17  xor     r8d, r8d; lpReserved
0x180076b1a  mov     [rsp+4C0h+Type], eax
0x180076b1e  lea     rax, [rsp+4C0h+cbData]
0x180076b23  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x180076b28  mov     [rsp+4C0h+phkResult], rdi; lpData
0x180076b2d  mov     [rsp+4C0h+cbData], 4
0x180076b35  call    cs:__imp_RegQueryValueExW
0x180076b3b  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180076b40  call    cs:__imp_RegCloseKey
0x180076b46  cmp     dword ptr [rdi], 0
0x180076b49  jz      loc_180076C86
0x180076b4f  test    sil, sil
0x180076b52  jz      loc_180076C86
0x180076b58  lea     rcx, [rsp+4C0h+lpSrc]; this
0x180076b5d  call    ??0CWString@@QEAA@XZ; CWString::CWString(void)
0x180076b62  lea     r8, [rbx+20h]
0x180076b66  lea     rdx, aSystemrootDebu_0; "%systemroot%\\debug\\UserMode\\"
0x180076b6d  lea     rcx, [rsp+4C0h+Type]; this
0x180076b72  call    ??H@YA?AVCWString@@PEBGAEBV0@@Z; operator+(ushort const *,CWString const &)
0x180076b77  mov     rdx, rax
0x180076b7a  lea     rcx, [rsp+4C0h+lpSrc]; this
0x180076b7f  call    ??4CWString@@QEAAAEAV0@AEBV0@@Z; CWString::operator=(CWString const &)
0x180076b84  lea     rcx, [rsp+4C0h+Type]; this
0x180076b89  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180076b8e  cmp     [rsp+4C0h+var_474], 0
0x180076b93  jz      loc_180076C69
0x180076b99  mov     rcx, [rsp+4C0h+lpSrc]; lpSrc
0x180076b9e  lea     rdx, [rsp+4C0h+Dst]; lpDst
0x180076ba3  mov     edi, 105h
0x180076ba8  mov     r8d, edi; nSize
0x180076bab  call    cs:__imp_ExpandEnvironmentStringsW
0x180076bb1  dec     eax
0x180076bb3  lea     esi, [rdi-2]
0x180076bb6  cmp     eax, esi
0x180076bb8  ja      loc_180076C69
0x180076bbe  lea     r8, [rbx+30h]
0x180076bc2  lea     rdx, aSystemrootDebu_0; "%systemroot%\\debug\\UserMode\\"
0x180076bc9  lea     rcx, [rsp+4C0h+Type]; this
0x180076bce  call    ??H@YA?AVCWString@@PEBGAEBV0@@Z; operator+(ushort const *,CWString const &)
0x180076bd3  mov     rdx, rax
0x180076bd6  lea     rcx, [rsp+4C0h+lpSrc]; this
0x180076bdb  call    ??4CWString@@QEAAAEAV0@AEBV0@@Z; CWString::operator=(CWString const &)
0x180076be0  lea     rcx, [rsp+4C0h+Type]; this
0x180076be5  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180076bea  cmp     [rsp+4C0h+var_474], 0
0x180076bef  jz      short loc_180076C69
0x180076bf1  mov     rcx, [rsp+4C0h+lpSrc]; lpSrc
0x180076bf6  lea     rdx, [rbp+3C0h+NewFileName]; lpDst
0x180076bfd  mov     r8d, edi; nSize
0x180076c00  call    cs:__imp_ExpandEnvironmentStringsW
0x180076c06  dec     eax
0x180076c08  cmp     eax, esi
0x180076c0a  ja      short loc_180076C69
0x180076c0c  mov     r8d, 1; dwFlags
0x180076c12  lea     rdx, [rbp+3C0h+NewFileName]; lpNewFileName
0x180076c19  lea     rcx, [rsp+4C0h+Dst]; lpExistingFileName
0x180076c1e  call    cs:__imp_MoveFileExW
0x180076c24  xor     r9d, r9d; lpSecurityAttributes
0x180076c27  mov     [rsp+4C0h+hTemplateFile], 0; hTemplateFile
0x180076c30  mov     dword ptr [rsp+4C0h+lpcbData], 0; dwFlagsAndAttributes
0x180076c38  lea     rcx, [rsp+4C0h+Dst]; lpFileName
0x180076c3d  mov     edx, 40000000h; dwDesiredAccess
0x180076c42  mov     dword ptr [rsp+4C0h+phkResult], 2; dwCreationDisposition
0x180076c4a  lea     r8d, [r9+1]; dwShareMode
0x180076c4e  call    cs:__imp_CreateFileW
0x180076c54  mov     qword ptr [rsp+4C0h+Type], rax
0x180076c59  lea     rcx, [rsp+4C0h+Type]; this
0x180076c5e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180076c62  jnz     short loc_180076C77
0x180076c64  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180076c69  lea     rcx, [rsp+4C0h+lpSrc]; this
0x180076c6e  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180076c73  xor     al, al
0x180076c75  jmp     short loc_180076C8C
0x180076c77  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180076c7c  lea     rcx, [rsp+4C0h+lpSrc]; this
0x180076c81  call    ?Reset@CWString@@AEAAXXZ; CWString::Reset(void)
0x180076c86  mov     byte ptr [rbx+40h], 1
0x180076c8a  mov     al, 1
0x180076c8c  mov     rcx, [rbp+3C0h+var_30]
0x180076c93  xor     rcx, rsp; StackCookie
0x180076c96  call    __security_check_cookie
0x180076c9b  add     rsp, 4A8h
0x180076ca2  pop     rdi
0x180076ca3  pop     rsi
0x180076ca4  pop     rbx
0x180076ca5  pop     rbp
0x180076ca6  retn
```
