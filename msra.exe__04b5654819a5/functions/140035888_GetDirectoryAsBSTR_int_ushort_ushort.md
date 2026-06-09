# GetDirectoryAsBSTR(int,ushort * *,ushort *)

- ea: `0x140035888`
- end: `0x140035a07`
- name: `?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z`
- size: `383`
- prototype: `__int64 __fastcall(int csidl, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a350`
- `0x140016bd4`
- `0x14001d430`
- `0x14001ffb8`
- `0x140026c48`
- `0x140029334`
- `0x14002b3c8`
- `0x14002b4a0`
- `0x14002c0a4`
- `0x14002e288`
- `0x14002ea50`
- `0x14002f0d0`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140034ce4`
- `0x140035888`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x140035930`
- `KERNEL32!GetTempPath2W` at `0x140035930`
- `OLEAUT32!__imp_SysAllocString` at `0x1400359a3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400359a3`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1400358e8`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1400358e8`

## string_xrefs

- `0x1400358fc`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x1400359d1`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x140035903`: `GetDirectoryAsBSTR`
- `0x1400359ca`: `GetDirectoryAsBSTR`

## pseudocode

```c
__int64 __fastcall GetDirectoryAsBSTR(int csidl, unsigned __int16 **a2, unsigned __int16 *a3)
{
  CEventLogger *v6; // rcx
  CEventLogger *v7; // rcx
  signed int v8; // eax
  CEventLogger *v9; // rcx
  unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rax
  CEventLogger *v12; // rcx
  WCHAR pszPath[264]; // [rsp+30h] [rbp-A38h] BYREF
  unsigned __int16 v15[1024]; // [rsp+240h] [rbp-828h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(v15, 0, sizeof(v15));
  if ( csidl )
  {
    if ( !SHGetSpecialFolderPathW(0, pszPath, csidl, 1) )
    {
      CEventLogger::LogError(
        v6,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
        0xE9u,
        L"GetDirectoryAsBSTR",
        0);
      LODWORD(a3) = -2147467259;
      return (unsigned int)a3;
    }
  }
  else if ( (unsigned int)GetTempPath2W(260, pszPath) - 1 > 0x103 )
  {
    LODWORD(a3) = -2147467259;
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0xF1u,
      L"GetDirectoryAsBSTR",
      0x80004005);
    return (unsigned int)a3;
  }
  if ( a3 )
  {
    v8 = StringCchPrintfW(v15, 0x400u, L"%s\\%s", pszPath, a3);
    LODWORD(a3) = v8;
    if ( v8 < 0 )
    {
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
        0xFDu,
        L"GetDirectoryAsBSTR",
        v8);
      return (unsigned int)a3;
    }
    v10 = v15;
  }
  else
  {
    v10 = pszPath;
  }
  v11 = SysAllocString(v10);
  *a2 = v11;
  if ( !v11 )
  {
    LODWORD(a3) = -2147024882;
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x106u,
      L"GetDirectoryAsBSTR",
      0x8007000E);
  }
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x140035888  push    rbx
0x14003588a  push    rsi
0x14003588b  push    rdi
0x14003588c  sub     rsp, 0A50h
0x140035893  mov     rax, cs:__security_cookie
0x14003589a  xor     rax, rsp
0x14003589d  mov     [rsp+0A68h+var_28], rax
0x1400358a5  mov     rbx, r8
0x1400358a8  mov     rsi, rdx
0x1400358ab  mov     edi, ecx
0x1400358ad  xor     edx, edx; Val
0x1400358af  mov     r8d, 208h; Size
0x1400358b5  lea     rcx, [rsp+0A68h+pszPath]; void *
0x1400358ba  call    memset_0
0x1400358bf  xor     edx, edx; Val
0x1400358c1  lea     rcx, [rsp+0A68h+var_828]; void *
0x1400358c9  mov     r8d, 800h; Size
0x1400358cf  call    memset_0
0x1400358d4  lea     rdx, [rsp+0A68h+pszPath]; pszPath
0x1400358d9  test    edi, edi
0x1400358db  jz      short loc_14003592B
0x1400358dd  mov     r9d, 1; fCreate
0x1400358e3  mov     r8d, edi; csidl
0x1400358e6  xor     ecx, ecx; hwnd
0x1400358e8  call    cs:__imp_SHGetSpecialFolderPathW
0x1400358ef  nop     dword ptr [rax+rax+00h]
0x1400358f4  test    eax, eax
0x1400358f6  jnz     short loc_14003595A
0x1400358f8  mov     [rsp+0A68h+var_A40], eax; unsigned int
0x1400358fc  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x140035903  lea     rax, aGetdirectoryas; "GetDirectoryAsBSTR"
0x14003590a  mov     r9d, 0E9h; unsigned int
0x140035910  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140035917  mov     [rsp+0A68h+var_A48], rax; unsigned __int16 *
0x14003591c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140035921  mov     ebx, 80004005h
0x140035926  jmp     loc_1400359E9
0x14003592b  mov     ecx, 104h
0x140035930  call    cs:__imp_GetTempPath2W
0x140035937  nop     dword ptr [rax+rax+00h]
0x14003593c  dec     eax
0x14003593e  cmp     eax, 103h
0x140035943  jbe     short loc_14003595A
0x140035945  mov     ebx, 80004005h
0x14003594a  mov     [rsp+0A68h+var_A40], 80004005h
0x140035952  mov     r9d, 0F1h
0x140035958  jmp     short loc_1400359CA
0x14003595a  test    rbx, rbx
0x14003595d  jz      short loc_14003599E
0x14003595f  lea     r9, [rsp+0A68h+pszPath]
0x140035964  mov     [rsp+0A68h+var_A48], rbx
0x140035969  lea     r8, aSS; "%s\\%s"
0x140035970  mov     edx, 400h; unsigned __int64
0x140035975  lea     rcx, [rsp+0A68h+var_828]; unsigned __int16 *
0x14003597d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140035982  mov     ebx, eax
0x140035984  test    eax, eax
0x140035986  jns     short loc_140035994
0x140035988  mov     [rsp+0A68h+var_A40], eax
0x14003598c  mov     r9d, 0FDh
0x140035992  jmp     short loc_1400359CA
0x140035994  lea     rcx, [rsp+0A68h+var_828]
0x14003599c  jmp     short loc_1400359A3
0x14003599e  lea     rcx, [rsp+0A68h+pszPath]; psz
0x1400359a3  call    cs:__imp_SysAllocString
0x1400359aa  nop     dword ptr [rax+rax+00h]
0x1400359af  mov     [rsi], rax
0x1400359b2  test    rax, rax
0x1400359b5  jnz     short loc_1400359E9
0x1400359b7  mov     ebx, 8007000Eh
0x1400359bc  mov     [rsp+0A68h+var_A40], 8007000Eh; unsigned int
0x1400359c4  mov     r9d, 106h; unsigned int
0x1400359ca  lea     rax, aGetdirectoryas; "GetDirectoryAsBSTR"
0x1400359d1  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x1400359d8  mov     [rsp+0A68h+var_A48], rax; unsigned __int16 *
0x1400359dd  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400359e4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400359e9  mov     eax, ebx
0x1400359eb  mov     rcx, [rsp+0A68h+var_28]
0x1400359f3  xor     rcx, rsp; StackCookie
0x1400359f6  call    __security_check_cookie
0x1400359fb  add     rsp, 0A50h
0x140035a02  pop     rdi
0x140035a03  pop     rsi
0x140035a04  pop     rbx
0x140035a05  retn
```
