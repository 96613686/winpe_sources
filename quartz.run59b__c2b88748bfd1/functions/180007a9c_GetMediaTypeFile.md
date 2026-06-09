# GetMediaTypeFile

- ea: `0x180007a9c`
- end: `0x180007e97`
- name: `GetMediaTypeFile`
- size: `1019`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, struct _GUID *, struct _GUID *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008820`
- `0x1800fcc70`

## callees

- `0x180007a9c`
- `0x180019a30`
- `0x180024640`
- `0x180026aa0`
- `0x1800388a0`
- `0x180058634`
- `0x180058898`
- `0x1800589cc`
- `0x180058bb8`
- `0x180058e5c`
- `0x1800592cc`
- `0x180059428`

## import_xrefs

- `KERNEL32!GetFileType` at `0x180007cd2`
- `KERNEL32!GetFileType` at `0x180007cd2`
- `KERNEL32!CloseHandle` at `0x180007ce6`
- `KERNEL32!CloseHandle` at `0x180007d20`
- `KERNEL32!CloseHandle` at `0x180007df1`
- `KERNEL32!CloseHandle` at `0x180007e29`
- `KERNEL32!CloseHandle` at `0x180007ce6`
- `KERNEL32!CloseHandle` at `0x180007d20`
- `KERNEL32!CloseHandle` at `0x180007df1`
- `KERNEL32!CloseHandle` at `0x180007e29`
- `KERNEL32!GetLastError` at `0x180007cae`
- `KERNEL32!GetLastError` at `0x180007cae`
- `KERNEL32!CreateFileW` at `0x180007c99`
- `KERNEL32!CreateFileW` at `0x180007c99`
- `USER32!CharNextW` at `0x180007afc`
- `USER32!CharNextW` at `0x180007afc`
- `ADVAPI32!RegOpenKeyExW` at `0x180007bf2`
- `ADVAPI32!RegOpenKeyExW` at `0x180007bf2`
- `ADVAPI32!RegCloseKey` at `0x180007c62`
- `ADVAPI32!RegCloseKey` at `0x180007c62`
- `ole32!CLSIDFromString` at `0x180007db5`
- `ole32!CLSIDFromString` at `0x180007dcc`
- `ole32!CLSIDFromString` at `0x180007db5`
- `ole32!CLSIDFromString` at `0x180007dcc`

## string_xrefs

- `0x180007b83`: `Media Type\Extensions\`

## pseudocode

```c
signed int __fastcall GetMediaTypeFile(unsigned __int16 *a1, struct _GUID *a2, struct _GUID *a3, struct _GUID *a4)
{
  LPWSTR v5; // rax
  WCHAR i; // cx
  __int64 v10; // rax
  signed int result; // eax
  const wchar_t *Extension; // rdi
  size_t v13; // r9
  size_t *v14; // r8
  __int64 v15; // r11
  int GUID; // edi
  HKEY v17; // rcx
  HANDLE FileW; // rax
  void *v19; // rdi
  int v20; // ebx
  int v21; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  int URLSource; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  size_t pcchDestLength; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v30; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v31[10]; // [rsp+70h] [rbp-90h] BYREF
  LPCOLESTR lpsz; // [rsp+C0h] [rbp-40h]
  wchar_t pszDest[4]; // [rsp+E0h] [rbp-20h] BYREF
  HKEY v34; // [rsp+E8h] [rbp-18h]
  LPCOLESTR v35; // [rsp+130h] [rbp+30h]

  v30 = 0;
  URLSource = 0;
  v5 = a1;
  for ( i = *a1; i && i != 92 && i != 58; i = *v5 )
    v5 = CharNextW(v5);
  if ( *v5 == 58 )
  {
    v10 = v5 - a1;
    if ( (int)v10 < 0 )
      return -2147418113;
    URLSource = GetURLSource(a1, v10, a4);
    if ( !URLSource )
    {
      *a2 = GUID_NULL;
      *a3 = GUID_NULL;
      return 0;
    }
  }
  if ( a4 )
  {
    Extension = FindExtension(a1);
    if ( Extension )
    {
      StringCbCopyW(pszDest, 0xC8u, L"Media Type\\Extensions\\");
      pcchDestLength = 0;
      if ( StringValidateDestAndLengthW(pszDest, 0x64u, &pcchDestLength, v13) >= 0 )
        StringCopyWorkerW(&pszDest[pcchDestLength], v15 - pcchDestLength, v14, Extension, (size_t)phkResult);
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, pszDest, 0, 0x20019u, &hKey) )
      {
        GUID = ReadGUID(hKey, L"Source Filter", a4);
        if ( GUID )
        {
          v17 = hKey;
          *a2 = GUID_NULL;
          *a3 = GUID_NULL;
          ReadGUID(v17, L"Media Type", a2);
          ReadGUID(hKey, L"Subtype", a3);
        }
        RegCloseKey(hKey);
        if ( GUID )
          return 0;
      }
    }
  }
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v19 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else if ( GetFileType(FileW) == 1 )
  {
    CEnumKey::CEnumKey((CEnumKey *)v31, HKEY_CLASSES_ROOT, L"Media Type", &URLSource, phkResulta, dwFlagsAndAttributes);
    v20 = URLSource;
    if ( URLSource >= 0 )
    {
LABEL_29:
      if ( (unsigned int)CEnumKey::Next((CEnumKey *)v31) )
      {
        CEnumKey::CEnumKey((CEnumKey *)pszDest, (HKEY)v31[1], lpsz, &URLSource, phkResultb, dwFlagsAndAttributesa);
        v20 = URLSource;
        if ( URLSource >= 0 )
        {
          do
          {
            while ( 1 )
            {
              if ( !(unsigned int)CEnumKey::Next((CEnumKey *)pszDest) )
              {
                *(_QWORD *)pszDest = &CEnumKey::`vftable';
                CKey::~CKey((CKey *)pszDest);
                goto LABEL_29;
              }
              v21 = CheckBytes(v19, v34, v35, &v30);
              URLSource = v21;
              v20 = v21;
              if ( !v21 )
                break;
              if ( v21 < 0 )
                goto LABEL_38;
            }
          }
          while ( CLSIDFromString(lpsz, a2) < 0 || CLSIDFromString(v35, a3) < 0 );
          if ( a4 )
            *a4 = v30;
          v20 = 0;
        }
LABEL_38:
        CloseHandle(v19);
        *(_QWORD *)pszDest = &CEnumKey::`vftable';
        CKey::~CKey((CKey *)pszDest);
      }
      else
      {
        CloseHandle(v19);
        *a2 = MEDIATYPE_Stream;
        *a3 = GUID_NULL;
        if ( a4 )
          *a4 = CLSID_AsyncReader;
        v20 = 0;
      }
    }
    else
    {
      CloseHandle(v19);
      if ( v20 == -2147024894 )
        v20 = -2147220494;
    }
    v31[0] = &CEnumKey::`vftable';
    CKey::~CKey((CKey *)v31);
    return v20;
  }
  else
  {
    CloseHandle(v19);
    return -2147024894;
  }
  return result;
}

```

## disassembly

```asm
0x180007a9c  push    rbp
0x180007a9e  push    rbx
0x180007a9f  push    rsi
0x180007aa0  push    rdi
0x180007aa1  push    r12
0x180007aa3  push    r13
0x180007aa5  push    r14
0x180007aa7  push    r15
0x180007aa9  lea     rbp, [rsp-0C8h]
0x180007ab1  sub     rsp, 1C8h
0x180007ab8  mov     rax, cs:__security_cookie
0x180007abf  xor     rax, rsp
0x180007ac2  mov     [rbp+100h+var_50], rax
0x180007ac9  xorps   xmm0, xmm0
0x180007acc  xor     r13d, r13d
0x180007acf  movups  xmmword ptr [rsp+200h+var_1A8.Data1], xmm0
0x180007ad4  mov     rbx, rcx
0x180007ad7  mov     [rsp+200h+var_1C0], r13d
0x180007adc  mov     rax, rcx
0x180007adf  mov     r14, r9
0x180007ae2  movzx   ecx, word ptr [rcx]
0x180007ae5  mov     r12, r8
0x180007ae8  mov     r15, rdx
0x180007aeb  jmp     short loc_180007B0B
0x180007aed  cmp     cx, 5Ch ; '\'
0x180007af1  jz      short loc_180007B10
0x180007af3  cmp     cx, 3Ah ; ':'
0x180007af7  jz      short loc_180007B10
0x180007af9  mov     rcx, rax; lpsz
0x180007afc  call    cs:__imp_CharNextW
0x180007b03  nop     dword ptr [rax+rax+00h]
0x180007b08  movzx   ecx, word ptr [rax]
0x180007b0b  test    cx, cx
0x180007b0e  jnz     short loc_180007AED
0x180007b10  cmp     word ptr [rax], 3Ah ; ':'
0x180007b14  jnz     short loc_180007B5F
0x180007b16  sub     rax, rbx
0x180007b19  sar     rax, 1
0x180007b1c  test    eax, eax
0x180007b1e  jns     short loc_180007B2A
0x180007b20  mov     eax, 8000FFFFh
0x180007b25  jmp     loc_180007E73
0x180007b2a  mov     r8, r14; struct _GUID *
0x180007b2d  mov     edx, eax; int
0x180007b2f  mov     rcx, rbx; unsigned __int16 *
0x180007b32  call    ?GetURLSource@@YAJPEBGHPEAU_GUID@@@Z; GetURLSource(ushort const *,int,_GUID *)
0x180007b37  mov     [rsp+200h+var_1C0], eax
0x180007b3b  test    eax, eax
0x180007b3d  jnz     short loc_180007B5F
0x180007b3f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007b46  movdqu  xmmword ptr [r15], xmm0
0x180007b4b  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180007b52  movdqu  xmmword ptr [r12], xmm1
0x180007b58  xor     eax, eax
0x180007b5a  jmp     loc_180007E73
0x180007b5f  mov     rsi, 0FFFFFFFF80000000h
0x180007b66  test    r14, r14
0x180007b69  jz      loc_180007C76
0x180007b6f  mov     rcx, rbx; unsigned __int16 *
0x180007b72  call    ?FindExtension@@YAPEBGPEBG@Z; FindExtension(ushort const *)
0x180007b77  mov     rdi, rax
0x180007b7a  test    rax, rax
0x180007b7d  jz      loc_180007C76
0x180007b83  lea     r8, aMediaTypeExten; "Media Type\\Extensions\\"
0x180007b8a  mov     edx, 0C8h; unsigned __int64
0x180007b8f  lea     rcx, [rbp+100h+pszDest]; unsigned __int16 *
0x180007b93  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180007b98  mov     r11d, 64h ; 'd'
0x180007b9e  mov     [rsp+200h+pcchDestLength], r13
0x180007ba3  mov     edx, r11d; cchDest
0x180007ba6  lea     r8, [rsp+200h+pcchDestLength]; pcchDestLength
0x180007bab  lea     rcx, [rbp+100h+pszDest]; pszDest
0x180007baf  call    StringValidateDestAndLengthW
0x180007bb4  test    eax, eax
0x180007bb6  js      short loc_180007BD3
0x180007bb8  mov     rax, [rsp+200h+pcchDestLength]
0x180007bbd  lea     rcx, [rbp+100h+pszDest]
0x180007bc1  sub     r11, rax
0x180007bc4  mov     r9, rdi; pszSrc
0x180007bc7  mov     rdx, r11; cchDest
0x180007bca  lea     rcx, [rcx+rax*2]; pszDest
0x180007bce  call    StringCopyWorkerW
0x180007bd3  lea     rax, [rsp+200h+hKey]
0x180007bd8  mov     [rsp+200h+hKey], r13
0x180007bdd  mov     r9d, 20019h; samDesired
0x180007be3  mov     [rsp+200h+phkResult], rax; phkResult
0x180007be8  xor     r8d, r8d; ulOptions
0x180007beb  lea     rdx, [rbp+100h+pszDest]; lpSubKey
0x180007bef  mov     rcx, rsi; hKey
0x180007bf2  call    cs:__imp_RegOpenKeyExW
0x180007bf9  nop     dword ptr [rax+rax+00h]
0x180007bfe  test    eax, eax
0x180007c00  jnz     short loc_180007C76
0x180007c02  mov     rcx, [rsp+200h+hKey]; HKEY
0x180007c07  lea     rdx, aSourceFilter; "Source Filter"
0x180007c0e  mov     r8, r14; struct _GUID *
0x180007c11  call    ?ReadGUID@@YAHPEAUHKEY__@@PEBGPEAU_GUID@@@Z; ReadGUID(HKEY__ *,ushort const *,_GUID *)
0x180007c16  mov     edi, eax
0x180007c18  test    eax, eax
0x180007c1a  jz      short loc_180007C5D
0x180007c1c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007c23  mov     rcx, [rsp+200h+hKey]; HKEY
0x180007c28  lea     rdx, aMediaType; "Media Type"
0x180007c2f  mov     r8, r15; struct _GUID *
0x180007c32  movdqu  xmmword ptr [r15], xmm0
0x180007c37  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180007c3e  movdqu  xmmword ptr [r12], xmm1
0x180007c44  call    ?ReadGUID@@YAHPEAUHKEY__@@PEBGPEAU_GUID@@@Z; ReadGUID(HKEY__ *,ushort const *,_GUID *)
0x180007c49  mov     rcx, [rsp+200h+hKey]; HKEY
0x180007c4e  lea     rdx, aSubtype; "Subtype"
0x180007c55  mov     r8, r12; struct _GUID *
0x180007c58  call    ?ReadGUID@@YAHPEAUHKEY__@@PEBGPEAU_GUID@@@Z; ReadGUID(HKEY__ *,ushort const *,_GUID *)
0x180007c5d  mov     rcx, [rsp+200h+hKey]; hKey
0x180007c62  call    cs:__imp_RegCloseKey
0x180007c69  nop     dword ptr [rax+rax+00h]
0x180007c6e  test    edi, edi
0x180007c70  jnz     loc_180007B58
0x180007c76  mov     [rsp+200h+hTemplateFile], r13; hTemplateFile
0x180007c7b  mov     r8d, 3; dwShareMode
0x180007c81  mov     [rsp+200h+dwFlagsAndAttributes], 80h; unsigned int
0x180007c89  xor     r9d, r9d; lpSecurityAttributes
0x180007c8c  mov     edx, 80000000h; dwDesiredAccess
0x180007c91  mov     dword ptr [rsp+200h+phkResult], r8d; int
0x180007c96  mov     rcx, rbx; lpFileName
0x180007c99  call    cs:__imp_CreateFileW
0x180007ca0  nop     dword ptr [rax+rax+00h]
0x180007ca5  mov     rdi, rax
0x180007ca8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007cac  jnz     short loc_180007CCF
0x180007cae  call    cs:__imp_GetLastError
0x180007cb5  nop     dword ptr [rax+rax+00h]
0x180007cba  test    eax, eax
0x180007cbc  jle     loc_180007E73
0x180007cc2  movzx   eax, ax
0x180007cc5  or      eax, 80070000h
0x180007cca  jmp     loc_180007E73
0x180007ccf  mov     rcx, rdi; hFile
0x180007cd2  call    cs:__imp_GetFileType
0x180007cd9  nop     dword ptr [rax+rax+00h]
0x180007cde  cmp     eax, 1
0x180007ce1  jz      short loc_180007CFC
0x180007ce3  mov     rcx, rdi; hObject
0x180007ce6  call    cs:__imp_CloseHandle
0x180007ced  nop     dword ptr [rax+rax+00h]
0x180007cf2  mov     eax, 80070002h
0x180007cf7  jmp     loc_180007E73
0x180007cfc  lea     r9, [rsp+200h+var_1C0]; int *
0x180007d01  mov     rdx, rsi; HKEY
0x180007d04  lea     r8, aMediaType; "Media Type"
0x180007d0b  lea     rcx, [rsp+200h+var_190]; this
0x180007d10  call    ??0CEnumKey@@QEAA@PEAUHKEY__@@PEBGPEAJHK@Z; CEnumKey::CEnumKey(HKEY__ *,ushort const *,long *,int,ulong)
0x180007d15  mov     ebx, [rsp+200h+var_1C0]
0x180007d19  test    ebx, ebx
0x180007d1b  jns     short loc_180007D46
0x180007d1d  mov     rcx, rdi; hObject
0x180007d20  call    cs:__imp_CloseHandle
0x180007d27  nop     dword ptr [rax+rax+00h]
0x180007d2c  cmp     ebx, 80070002h
0x180007d32  lea     rsi, ??_7CEnumKey@@6B@; const CEnumKey::`vftable'
0x180007d39  mov     eax, 800403F2h
0x180007d3e  cmovz   ebx, eax
0x180007d41  jmp     loc_180007E62
0x180007d46  lea     rsi, ??_7CEnumKey@@6B@; const CEnumKey::`vftable'
0x180007d4d  lea     rcx, [rsp+200h+var_190]; this
0x180007d52  call    ?Next@CEnumKey@@UEAAHXZ; CEnumKey::Next(void)
0x180007d57  test    eax, eax
0x180007d59  jz      loc_180007E26
0x180007d5f  mov     r8, [rbp+100h+lpsz]; unsigned __int16 *
0x180007d63  lea     r9, [rsp+200h+var_1C0]; int *
0x180007d68  mov     rdx, [rsp+200h+var_188]; HKEY
0x180007d6d  lea     rcx, [rbp+100h+pszDest]; this
0x180007d71  call    ??0CEnumKey@@QEAA@PEAUHKEY__@@PEBGPEAJHK@Z; CEnumKey::CEnumKey(HKEY__ *,ushort const *,long *,int,ulong)
0x180007d76  mov     ebx, [rsp+200h+var_1C0]
0x180007d7a  test    ebx, ebx
0x180007d7c  js      short loc_180007DEE
0x180007d7e  lea     rcx, [rbp+100h+pszDest]; this
0x180007d82  call    ?Next@CEnumKey@@UEAAHXZ; CEnumKey::Next(void)
0x180007d87  test    eax, eax
0x180007d89  jz      loc_180007E14
0x180007d8f  mov     r8, [rbp+100h+var_D0]; unsigned __int16 *
0x180007d93  lea     r9, [rsp+200h+var_1A8]; struct _GUID *
0x180007d98  mov     rdx, [rbp+100h+var_118]; HKEY
0x180007d9c  mov     rcx, rdi; hFile
0x180007d9f  call    ?CheckBytes@@YAJPEAXPEAUHKEY__@@PEBGAEAU_GUID@@@Z; CheckBytes(void *,HKEY__ *,ushort const *,_GUID &)
0x180007da4  mov     [rsp+200h+var_1C0], eax
0x180007da8  mov     ebx, eax
0x180007daa  test    eax, eax
0x180007dac  jnz     short loc_180007E0C
0x180007dae  mov     rcx, [rbp+100h+lpsz]; lpsz
0x180007db2  mov     rdx, r15; pclsid
0x180007db5  call    cs:__imp_CLSIDFromString
0x180007dbc  nop     dword ptr [rax+rax+00h]
0x180007dc1  test    eax, eax
0x180007dc3  js      short loc_180007D7E
0x180007dc5  mov     rcx, [rbp+100h+var_D0]; lpsz
0x180007dc9  mov     rdx, r12; pclsid
0x180007dcc  call    cs:__imp_CLSIDFromString
0x180007dd3  nop     dword ptr [rax+rax+00h]
0x180007dd8  test    eax, eax
0x180007dda  js      short loc_180007D7E
0x180007ddc  test    r14, r14
0x180007ddf  jz      short loc_180007DEB
0x180007de1  movups  xmm0, xmmword ptr [rsp+200h+var_1A8.Data1]
0x180007de6  movdqu  xmmword ptr [r14], xmm0
0x180007deb  mov     ebx, r13d
0x180007dee  mov     rcx, rdi; hObject
0x180007df1  call    cs:__imp_CloseHandle
0x180007df8  nop     dword ptr [rax+rax+00h]
0x180007dfd  lea     rcx, [rbp+100h+pszDest]; this
0x180007e01  mov     qword ptr [rbp+100h+pszDest], rsi
0x180007e05  call    ??1CKey@@QEAA@XZ; CKey::~CKey(void)
0x180007e0a  jmp     short loc_180007E62
0x180007e0c  jns     loc_180007D7E
0x180007e12  jmp     short loc_180007DEE
0x180007e14  lea     rcx, [rbp+100h+pszDest]; this
0x180007e18  mov     qword ptr [rbp+100h+pszDest], rsi
0x180007e1c  call    ??1CKey@@QEAA@XZ; CKey::~CKey(void)
0x180007e21  jmp     loc_180007D4D
0x180007e26  mov     rcx, rdi; hObject
0x180007e29  call    cs:__imp_CloseHandle
0x180007e30  nop     dword ptr [rax+rax+00h]
0x180007e35  movups  xmm0, xmmword ptr cs:MEDIATYPE_Stream.Data1
0x180007e3c  movdqu  xmmword ptr [r15], xmm0
0x180007e41  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180007e48  movdqu  xmmword ptr [r12], xmm1
0x180007e4e  test    r14, r14
0x180007e51  jz      short loc_180007E5F
0x180007e53  movups  xmm0, xmmword ptr cs:CLSID_AsyncReader.Data1
0x180007e5a  movdqu  xmmword ptr [r14], xmm0
0x180007e5f  mov     ebx, r13d
0x180007e62  lea     rcx, [rsp+200h+var_190]; this
0x180007e67  mov     [rsp+200h+var_190], rsi
0x180007e6c  call    ??1CKey@@QEAA@XZ; CKey::~CKey(void)
0x180007e71  mov     eax, ebx
0x180007e73  mov     rcx, [rbp+100h+var_50]
0x180007e7a  xor     rcx, rsp; StackCookie
0x180007e7d  call    __security_check_cookie
0x180007e82  add     rsp, 1C8h
0x180007e89  pop     r15
0x180007e8b  pop     r14
0x180007e8d  pop     r13
0x180007e8f  pop     r12
0x180007e91  pop     rdi
0x180007e92  pop     rsi
0x180007e93  pop     rbx
0x180007e94  pop     rbp
0x180007e95  retn
```
