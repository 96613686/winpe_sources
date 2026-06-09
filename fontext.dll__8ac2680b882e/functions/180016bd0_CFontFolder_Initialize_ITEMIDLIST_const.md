# CFontFolder::Initialize(_ITEMIDLIST const *)

- ea: `0x180016bd0`
- end: `0x180016d8b`
- name: `?Initialize@CFontFolder@@UEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `443`
- prototype: `int(CFontFolder *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180008aec`
- `0x18000ae20`
- `0x18000f518`
- `0x180014968`
- `0x180016b50`
- `0x180016bd0`
- `0x1800190b0`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x180016c62`
- `SHELL32!SHGetPathFromIDListW` at `0x180016c62`
- `SHELL32!SHGetKnownFolderPath` at `0x180016c8d`
- `SHELL32!SHGetKnownFolderPath` at `0x180016c8d`
- `SHELL32!__imp_ILClone` at `0x180016d18`
- `SHELL32!__imp_ILClone` at `0x180016d18`
- `SHELL32!__imp_ILFree` at `0x180016cf9`
- `SHELL32!__imp_ILFree` at `0x180016cf9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016cd0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016d07`

## string_xrefs

- `0x180016ca0`: `shell\osshell\fontfldr\fontext2\dll\folder.cpp`
- `0x180016d38`: `shell\osshell\fontfldr\fontext2\dll\folder.cpp`

## pseudocode

```c
__int64 __fastcall CFontFolder::Initialize(LPVOID *this, const struct _ITEMIDLIST *a2)
{
  unsigned int v4; // ebx
  struct _ITEMIDLIST *v5; // rsi
  HRESULT v6; // eax
  LPITEMIDLIST v7; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v11[42]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v11,
    "InitializeFontFolder");
  v11[0] = &FontFldrTraceLoggingTelemetry::InitializeFontFolder::`vftable';
  FontFldrTraceLoggingTelemetry::InitializeFontFolder::StartActivity((FontFldrTraceLoggingTelemetry::InitializeFontFolder *)v11);
  v4 = -2147467259;
  v5 = ILCloneParent(a2);
  if ( !v5 )
    goto LABEL_11;
  memset_0(pszPath, 0, 0x208u);
  if ( SHGetPathFromIDListW(v5, pszPath) )
  {
    ppszPath = 0;
    v6 = SHGetKnownFolderPath(&FOLDERID_Windows, 0x4000u, 0, &ppszPath);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v4 = CompareStringOrdinal(pszPath, -1, ppszPath, -1, 1) != 2 ? 0x80004005 : 0;
      CoTaskMemFree(ppszPath);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5E3,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\folder.cpp",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
    }
  }
  else
  {
    v4 = 0;
  }
  ILFree(v5);
  if ( (v4 & 0x80000000) == 0 )
  {
    CoTaskMemFree(this[10]);
    this[10] = 0;
    v7 = ILClone(a2);
    v4 = -2147024882;
    this[10] = v7;
    if ( v7 )
      v4 = 0;
  }
  else
  {
LABEL_11:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5F3,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\folder.cpp",
      (const char *)v4,
      bIgnoreCase);
  }
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11, v4);
  FontFldrTraceLoggingTelemetry::InitializeFontFolder::~InitializeFontFolder((FontFldrTraceLoggingTelemetry::InitializeFontFolder *)v11);
  return v4;
}

```

## disassembly

```asm
0x180016bd0  mov     [rsp-8+arg_10], rbx
0x180016bd5  mov     [rsp-8+arg_18], rsi
0x180016bda  push    rbp
0x180016bdb  push    rdi
0x180016bdc  push    r14
0x180016bde  lea     rbp, [rsp-2B0h]
0x180016be6  sub     rsp, 3B0h
0x180016bed  mov     rax, cs:__security_cookie
0x180016bf4  xor     rax, rsp
0x180016bf7  mov     [rbp+2C0h+var_20], rax
0x180016bfe  mov     r14, rdx
0x180016c01  mov     rdi, rcx
0x180016c04  lea     rdx, aInitializefont; "InitializeFontFolder"
0x180016c0b  lea     rcx, [rsp+3C0h+var_380]
0x180016c10  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016c15  lea     rax, ??_7InitializeFontFolder@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::InitializeFontFolder::`vftable'
0x180016c1c  lea     rcx, [rsp+3C0h+var_380]; this
0x180016c21  mov     [rsp+3C0h+var_380], rax
0x180016c26  call    ?StartActivity@InitializeFontFolder@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::InitializeFontFolder::StartActivity(void)
0x180016c2b  mov     rcx, r14; struct _ITEMIDLIST *
0x180016c2e  mov     ebx, 80004005h
0x180016c33  call    ?ILCloneParent@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z; ILCloneParent(_ITEMIDLIST const *)
0x180016c38  mov     rsi, rax
0x180016c3b  test    rax, rax
0x180016c3e  jz      loc_180016D31
0x180016c44  xor     edx, edx; Val
0x180016c46  lea     rcx, [rbp+2C0h+pszPath]; void *
0x180016c4d  mov     r8d, 208h; Size
0x180016c53  call    memset_0
0x180016c58  lea     rdx, [rbp+2C0h+pszPath]; pszPath
0x180016c5f  mov     rcx, rsi; pidl
0x180016c62  call    cs:__imp_SHGetPathFromIDListW
0x180016c68  test    eax, eax
0x180016c6a  jz      loc_180016CF4
0x180016c70  lea     r9, [rsp+3C0h+ppszPath]; ppszPath
0x180016c75  mov     [rsp+3C0h+ppszPath], 0
0x180016c7e  xor     r8d, r8d; hToken
0x180016c81  lea     rcx, FOLDERID_Windows; rfid
0x180016c88  mov     edx, 4000h; dwFlags
0x180016c8d  call    cs:__imp_SHGetKnownFolderPath
0x180016c93  mov     ebx, eax
0x180016c95  test    eax, eax
0x180016c97  jns     short loc_180016CB6
0x180016c99  mov     rcx, [rbp+2C8h]; this
0x180016ca0  lea     r8, aShellOsshellFo_2; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180016ca7  mov     r9d, eax; char *
0x180016caa  mov     edx, 5E3h; void *
0x180016caf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016cb4  jmp     short loc_180016CF6
0x180016cb6  mov     r8, [rsp+3C0h+ppszPath]; lpString2
0x180016cbb  lea     rcx, [rbp+2C0h+pszPath]; lpString1
0x180016cc2  or      edx, 0FFFFFFFFh; cchCount1
0x180016cc5  mov     [rsp+3C0h+bIgnoreCase], 1; bIgnoreCase
0x180016ccd  mov     r9d, edx; cchCount2
0x180016cd0  call    cs:__imp_CompareStringOrdinal
0x180016cd6  mov     ecx, 2
0x180016cdb  sub     ecx, eax
0x180016cdd  neg     ecx
0x180016cdf  mov     rcx, [rsp+3C0h+ppszPath]; pv
0x180016ce4  sbb     ebx, ebx
0x180016ce6  and     ebx, 80004005h
0x180016cec  call    cs:__imp_CoTaskMemFree
0x180016cf2  jmp     short loc_180016CF6
0x180016cf4  xor     ebx, ebx
0x180016cf6  mov     rcx, rsi; pidl
0x180016cf9  call    cs:__imp_ILFree
0x180016cff  test    ebx, ebx
0x180016d01  js      short loc_180016D31
0x180016d03  mov     rcx, [rdi+50h]; pv
0x180016d07  call    cs:__imp_CoTaskMemFree
0x180016d0d  mov     rcx, r14; pidl
0x180016d10  mov     qword ptr [rdi+50h], 0
0x180016d18  call    cs:__imp_ILClone
0x180016d1e  xor     ecx, ecx
0x180016d20  mov     ebx, 8007000Eh
0x180016d25  test    rax, rax
0x180016d28  mov     [rdi+50h], rax
0x180016d2c  cmovnz  ebx, ecx
0x180016d2f  jmp     short loc_180016D4C
0x180016d31  mov     rcx, [rbp+2C8h]; this
0x180016d38  lea     r8, aShellOsshellFo_2; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180016d3f  mov     r9d, ebx; char *
0x180016d42  mov     edx, 5F3h; void *
0x180016d47  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016d4c  mov     edx, ebx
0x180016d4e  lea     rcx, [rsp+3C0h+var_380]
0x180016d53  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180016d58  lea     rcx, [rsp+3C0h+var_380]; this
0x180016d5d  call    ??1InitializeFontFolder@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::InitializeFontFolder::~InitializeFontFolder(void)
0x180016d62  mov     eax, ebx
0x180016d64  mov     rcx, [rbp+2C0h+var_20]
0x180016d6b  xor     rcx, rsp; StackCookie
0x180016d6e  call    __security_check_cookie
0x180016d73  lea     r11, [rsp+3C0h+var_10]
0x180016d7b  mov     rbx, [r11+30h]
0x180016d7f  mov     rsi, [r11+38h]
0x180016d83  mov     rsp, r11
0x180016d86  pop     r14
0x180016d88  pop     rdi
0x180016d89  pop     rbp
0x180016d8a  retn
```
