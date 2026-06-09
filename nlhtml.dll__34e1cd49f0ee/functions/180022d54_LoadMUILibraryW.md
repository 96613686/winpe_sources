# LoadMUILibraryW

- ea: `0x180022d54`
- end: `0x1800231c3`
- name: `LoadMUILibraryW`
- size: `1135`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180020c00`

## callees

- `0x180013b94`
- `0x180014130`
- `0x180022670`
- `0x1800226f0`
- `0x180022800`
- `0x180022928`
- `0x18002299c`
- `0x180022b10`
- `0x180022d54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023020`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023167`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002319a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023020`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023167`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002319a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022da4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023189`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022da4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023189`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180022e31`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180022e31`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180022deb`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180022deb`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180022e51`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180022e51`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180022f0f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180022f0f`

## string_xrefs

- `0x180022d92`: `nlhtml.dll`
- `0x180022dd3`: `nlhtml.dll`
- `0x180023179`: `nlhtml.dll`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v4; // rdi
  WCHAR *v5; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v21[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v22[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  dword_18003E510 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(L"nlhtml.dll", 0, dword_18003E510 & 0x20 | 2u);
  v4 = result;
  if ( !result )
    return 0;
  if ( (dword_18003E510 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, L"nlhtml.dll", 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v4);
    return 0;
  }
  if ( FilePart )
  {
    v5 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v5 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v4, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_18003E510 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
          if ( MUIFile )
            goto LABEL_41;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v9 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v20, v22, v21) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
              if ( MUIFile )
                goto LABEL_41;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v9 != 1033 )
          {
            LookupLangID(1033, v20, v22, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart);
          if ( MUIFile )
            goto LABEL_41;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (dword_18003E510 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v20, v22, v21) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart)) != 0
          || v21[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v20, v22, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart)) != 0 )
        {
LABEL_41:
          FreeLibrary(v4);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v4 & 1) != 0 )
  {
    FreeLibrary(v4);
    if ( (GetOSType(v11, v10, v12) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v5, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v14, v13, v15);
      return LoadLibraryExW(L"nlhtml.dll", 0, (OSType & 0x26) != 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180022d54  push    rbp
0x180022d56  push    rbx
0x180022d57  push    rsi
0x180022d58  push    rdi
0x180022d59  push    r12
0x180022d5b  push    r14
0x180022d5d  push    r15
0x180022d5f  lea     rbp, [rsp-370h]
0x180022d67  sub     rsp, 470h
0x180022d6e  mov     rax, cs:__security_cookie
0x180022d75  xor     rax, rsp
0x180022d78  mov     [rbp+3A0h+var_40], rax
0x180022d7f  xor     r12d, r12d
0x180022d82  mov     [rsp+4A0h+FilePart], r12
0x180022d87  call    GetOSType
0x180022d8c  mov     cs:dword_18003E510, eax
0x180022d92  lea     rcx, FileName; "nlhtml.dll"
0x180022d99  and     eax, 20h
0x180022d9c  xor     edx, edx; hFile
0x180022d9e  or      eax, 2
0x180022da1  mov     r8d, eax; dwFlags
0x180022da4  call    cs:__imp_LoadLibraryExW
0x180022daa  mov     rdi, rax
0x180022dad  test    rax, rax
0x180022db0  jz      loc_1800231A0
0x180022db6  test    byte ptr cs:dword_18003E510, 20h
0x180022dbd  jnz     loc_1800231A2
0x180022dc3  lea     rax, [rsp+4A0h+FilePart]
0x180022dc8  mov     r9d, 104h; nBufferLength
0x180022dce  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180022dd3  lea     rdx, FileName; "nlhtml.dll"
0x180022dda  lea     rax, [rbp+3A0h+Buffer]
0x180022de1  xor     r8d, r8d; lpExtension
0x180022de4  xor     ecx, ecx; lpPath
0x180022de6  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180022deb  call    cs:__imp_SearchPathW
0x180022df1  test    eax, eax
0x180022df3  jz      loc_180023197
0x180022df9  mov     rcx, [rsp+4A0h+FilePart]
0x180022dfe  test    rcx, rcx
0x180022e01  jnz     short loc_180022E14
0x180022e03  lea     rax, [rbp+3A0h+Buffer]
0x180022e0a  mov     esi, r12d
0x180022e0d  mov     [rsp+4A0h+FilePart], rax
0x180022e12  jmp     short loc_180022E20
0x180022e14  lea     rsi, [rbp+3A0h+Buffer]
0x180022e1b  mov     [rcx-2], r12w
0x180022e20  xor     r9d, r9d; wLanguage
0x180022e23  lea     rdx, Type; "MUI"
0x180022e2a  mov     rcx, rdi; hModule
0x180022e2d  lea     r8d, [r9+1]; lpName
0x180022e31  call    cs:__imp_FindResourceExW
0x180022e37  test    rax, rax
0x180022e3a  jz      loc_180023013
0x180022e40  mov     eax, cs:dword_18003E510
0x180022e46  test    al, 4
0x180022e48  jz      loc_180023070
0x180022e4e  mov     rbx, r12
0x180022e51  call    cs:__imp_GetUserDefaultUILanguage
0x180022e57  mov     r15d, 404h
0x180022e5d  movzx   r14d, ax
0x180022e61  cmp     ax, r15w
0x180022e65  jnz     short loc_180022E70
0x180022e67  call    GetCHTLangauge
0x180022e6c  movzx   r14d, ax
0x180022e70  lea     r9, [rbp+3A0h+var_3B0]
0x180022e74  movzx   ecx, r14w
0x180022e78  lea     r8, [rbp+3A0h+var_300]
0x180022e7f  lea     rdx, [rsp+4A0h+var_460]
0x180022e84  call    LookupLangID
0x180022e89  test    eax, eax
0x180022e8b  jz      loc_18002315B
0x180022e91  mov     r9, [rsp+4A0h+FilePart]
0x180022e96  lea     r8, [rsp+4A0h+var_460]
0x180022e9b  mov     rdx, rsi
0x180022e9e  mov     rcx, rdi
0x180022ea1  call    LoadMUIFile
0x180022ea6  mov     rbx, rax
0x180022ea9  test    rax, rax
0x180022eac  jnz     loc_180023164
0x180022eb2  mov     r9, [rsp+4A0h+FilePart]
0x180022eb7  lea     r8, [rbp+3A0h+var_300]
0x180022ebe  mov     rdx, rsi
0x180022ec1  mov     rcx, rdi
0x180022ec4  call    LoadMUIFile
0x180022ec9  mov     rbx, rax
0x180022ecc  test    rax, rax
0x180022ecf  jnz     loc_180023164
0x180022ed5  cmp     [rbp+3A0h+var_3B0], r12w
0x180022eda  jz      short loc_180022EFC
0x180022edc  mov     r9, [rsp+4A0h+FilePart]
0x180022ee1  lea     r8, [rbp+3A0h+var_3B0]
0x180022ee5  mov     rdx, rsi
0x180022ee8  mov     rcx, rdi
0x180022eeb  call    LoadMUIFile
0x180022ef0  mov     rbx, rax
0x180022ef3  test    rax, rax
0x180022ef6  jnz     loc_180023164
0x180022efc  mov     eax, 0C04h
0x180022f01  cmp     r14w, ax
0x180022f05  jnz     short loc_180022F0F
0x180022f07  mov     r14d, r15d
0x180022f0a  jmp     loc_180022E70
0x180022f0f  call    cs:__imp_GetSystemDefaultUILanguage
0x180022f15  movzx   r15d, ax
0x180022f19  cmp     ax, r14w
0x180022f1d  jz      loc_180022FAE
0x180022f23  lea     r9, [rbp+3A0h+var_3B0]
0x180022f27  movzx   ecx, ax
0x180022f2a  lea     r8, [rbp+3A0h+var_300]
0x180022f31  lea     rdx, [rsp+4A0h+var_460]
0x180022f36  call    LookupLangID
0x180022f3b  test    eax, eax
0x180022f3d  jz      loc_180023013
0x180022f43  mov     r9, [rsp+4A0h+FilePart]
0x180022f48  lea     r8, [rsp+4A0h+var_460]
0x180022f4d  mov     rdx, rsi
0x180022f50  mov     rcx, rdi
0x180022f53  call    LoadMUIFile
0x180022f58  mov     rbx, rax
0x180022f5b  test    rax, rax
0x180022f5e  jnz     loc_180023164
0x180022f64  mov     r9, [rsp+4A0h+FilePart]
0x180022f69  lea     r8, [rbp+3A0h+var_300]
0x180022f70  mov     rdx, rsi
0x180022f73  mov     rcx, rdi
0x180022f76  call    LoadMUIFile
0x180022f7b  mov     rbx, rax
0x180022f7e  test    rax, rax
0x180022f81  jnz     loc_180023164
0x180022f87  cmp     [rbp+3A0h+var_3B0], r12w
0x180022f8c  jz      short loc_180022FAE
0x180022f8e  mov     r9, [rsp+4A0h+FilePart]
0x180022f93  lea     r8, [rbp+3A0h+var_3B0]
0x180022f97  mov     rdx, rsi
0x180022f9a  mov     rcx, rdi
0x180022f9d  call    LoadMUIFile
0x180022fa2  mov     rbx, rax
0x180022fa5  test    rax, rax
0x180022fa8  jnz     loc_180023164
0x180022fae  mov     ecx, 409h
0x180022fb3  cmp     cx, r14w
0x180022fb7  jz      short loc_180022FF4
0x180022fb9  cmp     cx, r15w
0x180022fbd  jz      short loc_180022FF4
0x180022fbf  xor     r9d, r9d
0x180022fc2  lea     r8, [rbp+3A0h+var_300]
0x180022fc9  lea     rdx, [rsp+4A0h+var_460]
0x180022fce  call    LookupLangID
0x180022fd3  mov     r9, [rsp+4A0h+FilePart]
0x180022fd8  lea     r8, [rsp+4A0h+var_460]
0x180022fdd  mov     rdx, rsi
0x180022fe0  mov     rcx, rdi
0x180022fe3  call    LoadMUIFile
0x180022fe8  mov     rbx, rax
0x180022feb  test    rax, rax
0x180022fee  jnz     loc_180023164
0x180022ff4  mov     r9, [rsp+4A0h+FilePart]
0x180022ff9  xor     r8d, r8d
0x180022ffc  mov     rdx, rsi
0x180022fff  mov     rcx, rdi
0x180023002  call    LoadMUIFile
0x180023007  mov     rbx, rax
0x18002300a  test    rax, rax
0x18002300d  jnz     loc_180023164
0x180023013  test    dil, 1
0x180023017  jz      loc_180023192
0x18002301d  mov     rcx, rdi; hLibModule
0x180023020  call    cs:__imp_FreeLibrary
0x180023026  call    GetOSType
0x18002302b  test    al, 38h
0x18002302d  jz      loc_180023172
0x180023033  mov     rax, [rsp+4A0h+FilePart]
0x180023038  lea     r8, aSS; "%s\\%s"
0x18002303f  mov     r9, rsi
0x180023042  mov     [rsp+4A0h+lpBuffer], rax
0x180023047  mov     edx, 104h; unsigned __int64
0x18002304c  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x180023053  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023058  xor     r8d, r8d
0x18002305b  lea     rcx, [rbp+3A0h+Buffer]
0x180023062  lea     edx, [r8+1]
0x180023066  call    MapMUIFile
0x18002306b  jmp     loc_18002318F
0x180023070  test    al, 3
0x180023072  jz      short loc_180023013
0x180023074  call    GetInstallLanguage
0x180023079  lea     r9, [rbp+3A0h+var_3B0]
0x18002307d  movzx   ecx, ax
0x180023080  lea     r8, [rbp+3A0h+var_300]
0x180023087  movzx   r14d, ax
0x18002308b  lea     rdx, [rsp+4A0h+var_460]
0x180023090  call    LookupLangID
0x180023095  test    eax, eax
0x180023097  jz      loc_180023013
0x18002309d  mov     r9, [rsp+4A0h+FilePart]
0x1800230a2  lea     r8, [rsp+4A0h+var_460]
0x1800230a7  mov     rdx, rsi
0x1800230aa  mov     rcx, rdi
0x1800230ad  call    LoadMUIFile
0x1800230b2  mov     rbx, rax
0x1800230b5  test    rax, rax
0x1800230b8  jnz     loc_180023164
0x1800230be  mov     r9, [rsp+4A0h+FilePart]
0x1800230c3  lea     r8, [rbp+3A0h+var_300]
0x1800230ca  mov     rdx, rsi
0x1800230cd  mov     rcx, rdi
0x1800230d0  call    LoadMUIFile
0x1800230d5  mov     rbx, rax
0x1800230d8  test    rax, rax
0x1800230db  jnz     loc_180023164
0x1800230e1  cmp     [rbp+3A0h+var_3B0], r12w
0x1800230e6  jz      short loc_180023104
0x1800230e8  mov     r9, [rsp+4A0h+FilePart]
0x1800230ed  lea     r8, [rbp+3A0h+var_3B0]
0x1800230f1  mov     rdx, rsi
0x1800230f4  mov     rcx, rdi
0x1800230f7  call    LoadMUIFile
0x1800230fc  mov     rbx, rax
0x1800230ff  test    rax, rax
0x180023102  jnz     short loc_180023164
0x180023104  mov     ecx, 409h
0x180023109  cmp     cx, r14w
0x18002310d  jz      short loc_180023140
0x18002310f  xor     r9d, r9d
0x180023112  lea     r8, [rbp+3A0h+var_300]
0x180023119  lea     rdx, [rsp+4A0h+var_460]
0x18002311e  call    LookupLangID
0x180023123  mov     r9, [rsp+4A0h+FilePart]
0x180023128  lea     r8, [rsp+4A0h+var_460]
0x18002312d  mov     rdx, rsi
0x180023130  mov     rcx, rdi
0x180023133  call    LoadMUIFile
0x180023138  mov     rbx, rax
0x18002313b  test    rax, rax
0x18002313e  jnz     short loc_180023164
0x180023140  mov     r9, [rsp+4A0h+FilePart]
0x180023145  xor     r8d, r8d
0x180023148  mov     rdx, rsi
0x18002314b  mov     rcx, rdi
0x18002314e  call    LoadMUIFile
0x180023153  mov     rbx, rax
0x180023156  test    rax, rax
0x180023159  jnz     short loc_180023164
0x18002315b  test    rbx, rbx
0x18002315e  jz      loc_180023013
0x180023164  mov     rcx, rdi; hLibModule
0x180023167  call    cs:__imp_FreeLibrary
0x18002316d  mov     rax, rbx
0x180023170  jmp     short loc_1800231A2
0x180023172  call    GetOSType
0x180023177  test    al, 26h
0x180023179  lea     rcx, FileName; "nlhtml.dll"
0x180023180  mov     r8d, r12d
0x180023183  setnz   r8b; dwFlags
0x180023187  xor     edx, edx; hFile
0x180023189  call    cs:__imp_LoadLibraryExW
0x18002318f  mov     rdi, rax
0x180023192  mov     rax, rdi
0x180023195  jmp     short loc_1800231A2
0x180023197  mov     rcx, rdi; hLibModule
0x18002319a  call    cs:__imp_FreeLibrary
0x1800231a0  xor     eax, eax
0x1800231a2  mov     rcx, [rbp+3A0h+var_40]
0x1800231a9  xor     rcx, rsp; StackCookie
0x1800231ac  call    __security_check_cookie
0x1800231b1  add     rsp, 470h
0x1800231b8  pop     r15
0x1800231ba  pop     r14
0x1800231bc  pop     r12
0x1800231be  pop     rdi
0x1800231bf  pop     rsi
0x1800231c0  pop     rbx
0x1800231c1  pop     rbp
0x1800231c2  retn
```
