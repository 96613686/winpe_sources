# CNovInterDlg::SetWallpaper(ushort *,int)

- ea: `0x140025314`
- end: `0x14002552b`
- name: `?SetWallpaper@CNovInterDlg@@QEAAJPEAGH@Z`
- size: `535`
- prototype: `int(CNovInterDlg *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140025138`

## callees

- `0x140002463`
- `0x140025314`
- `0x1400289a8`
- `0x140034ce4`
- `0x140035e8c`
- `0x140036070`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14002541c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14002541c`
- `KERNEL32!HeapFree` at `0x1400254ed`
- `KERNEL32!HeapFree` at `0x1400254ed`
- `KERNEL32!GetProcessHeap` at `0x1400254d9`
- `KERNEL32!GetProcessHeap` at `0x1400254d9`
- `USER32!SystemParametersInfoW` at `0x140025371`
- `USER32!SystemParametersInfoW` at `0x14002548e`
- `USER32!SystemParametersInfoW` at `0x140025371`
- `USER32!SystemParametersInfoW` at `0x14002548e`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::SetWallpaper(unsigned __int16 **this, unsigned __int16 *a2, int a3)
{
  unsigned int v6; // edi
  CEventLogger *v7; // rcx
  unsigned int v8; // r9d
  signed int v9; // eax
  CEventLogger *v10; // rcx
  const WCHAR **v11; // rbx
  signed int v12; // eax
  const WCHAR *v13; // rbx
  CEventLogger *v14; // rcx
  unsigned int v15; // r9d
  unsigned __int16 *v16; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v19; // [rsp+28h] [rbp-240h]
  WCHAR pvParam[264]; // [rsp+30h] [rbp-238h] BYREF

  v6 = 0;
  memset_0(pvParam, 0, 0x208u);
  if ( a3 == 1 )
  {
    if ( !SystemParametersInfoW(0x73u, 0x104u, pvParam, 0) )
    {
      v8 = 3585;
LABEL_21:
      CEventLogger::LogError(
        v7,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        v8,
        L"CNovInterDlg::SetWallpaper",
        0);
      v6 = -2147467259;
      goto LABEL_22;
    }
    v9 = SetRegistryValue((unsigned __int16 *)v7, pvParam);
    v6 = v9;
    if ( v9 < 0 )
    {
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0xE09u,
        L"CNovInterDlg::SetWallpaper",
        v9);
      goto LABEL_22;
    }
    v11 = (const WCHAR **)(this + 16);
    v12 = DuplicateString(pvParam, this + 16);
    v6 = v12;
    if ( v12 < 0 )
    {
      CEventLogger::LogError(
        v7,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0xE0Fu,
        L"CNovInterDlg::SetWallpaper",
        v12);
      goto LABEL_22;
    }
  }
  else
  {
    v11 = (const WCHAR **)(this + 16);
  }
  v13 = *v11;
  if ( !v13 )
  {
    v8 = 3611;
    goto LABEL_21;
  }
  if ( !*v13 )
  {
    v8 = 3621;
    goto LABEL_21;
  }
  memset_0(pvParam, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(v13, pvParam, 0x104u) - 1 <= 0x103 )
  {
    if ( (unsigned int)FileExists(pvParam) )
    {
      if ( SystemParametersInfoW(0x14u, 0, a2, 3u) )
        return v6;
      v8 = 3671;
      goto LABEL_21;
    }
    v19 = 0;
    v15 = 3659;
  }
  else
  {
    v19 = -2147467259;
    v15 = 3642;
  }
  v6 = -2147467259;
  CEventLogger::LogError(
    v14,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
    v15,
    L"CNovInterDlg::SetWallpaper",
    v19);
LABEL_22:
  v16 = this[16];
  if ( v16 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
    this[16] = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x140025314  mov     [rsp+arg_10], rbx
0x140025319  mov     [rsp+arg_18], rbp
0x14002531e  push    rsi
0x14002531f  push    rdi
0x140025320  push    r14
0x140025322  sub     rsp, 250h
0x140025329  mov     rax, cs:__security_cookie
0x140025330  xor     rax, rsp
0x140025333  mov     [rsp+268h+var_28], rax
0x14002533b  mov     ebx, r8d
0x14002533e  mov     rbp, rdx
0x140025341  mov     rsi, rcx
0x140025344  xor     r14d, r14d
0x140025347  xor     edx, edx; Val
0x140025349  lea     rcx, [rsp+268h+pvParam]; void *
0x14002534e  mov     r8d, 208h; Size
0x140025354  mov     edi, r14d
0x140025357  call    memset_0
0x14002535c  cmp     ebx, 1
0x14002535f  jnz     short loc_1400253D1
0x140025361  xor     r9d, r9d; fWinIni
0x140025364  lea     r8, [rsp+268h+pvParam]; pvParam
0x140025369  mov     edx, 104h; uiParam
0x14002536e  lea     ecx, [rbx+72h]; uiAction
0x140025371  call    cs:__imp_SystemParametersInfoW
0x140025378  nop     dword ptr [rax+rax+00h]
0x14002537d  test    eax, eax
0x14002537f  jnz     short loc_14002538C
0x140025381  mov     r9d, 0E01h
0x140025387  jmp     loc_1400254A4
0x14002538c  lea     rdx, [rsp+268h+pvParam]; unsigned __int16 *
0x140025391  call    ?SetRegistryValue@@YAJPEAG0@Z; SetRegistryValue(ushort *,ushort *)
0x140025396  mov     edi, eax
0x140025398  test    eax, eax
0x14002539a  jns     short loc_1400253AB
0x14002539c  mov     [rsp+268h+var_240], eax
0x1400253a0  mov     r9d, 0E09h
0x1400253a6  jmp     loc_140025444
0x1400253ab  lea     rbx, [rsi+80h]
0x1400253b2  mov     rdx, rbx; unsigned __int16 **
0x1400253b5  lea     rcx, [rsp+268h+pvParam]; Src
0x1400253ba  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x1400253bf  mov     edi, eax
0x1400253c1  test    eax, eax
0x1400253c3  jns     short loc_1400253D8
0x1400253c5  mov     [rsp+268h+var_240], eax
0x1400253c9  mov     r9d, 0E0Fh
0x1400253cf  jmp     short loc_140025444
0x1400253d1  lea     rbx, [rsi+80h]
0x1400253d8  mov     rbx, [rbx]
0x1400253db  test    rbx, rbx
0x1400253de  jnz     short loc_1400253EB
0x1400253e0  mov     r9d, 0E1Bh
0x1400253e6  jmp     loc_1400254A4
0x1400253eb  cmp     [rbx], r14w
0x1400253ef  jnz     short loc_1400253FC
0x1400253f1  mov     r9d, 0E25h
0x1400253f7  jmp     loc_1400254A4
0x1400253fc  xor     edx, edx; Val
0x1400253fe  lea     rcx, [rsp+268h+pvParam]; void *
0x140025403  mov     r8d, 208h; Size
0x140025409  call    memset_0
0x14002540e  mov     r8d, 104h; nSize
0x140025414  lea     rdx, [rsp+268h+pvParam]; lpDst
0x140025419  mov     rcx, rbx; lpSrc
0x14002541c  call    cs:__imp_ExpandEnvironmentStringsW
0x140025423  nop     dword ptr [rax+rax+00h]
0x140025428  dec     eax
0x14002542a  cmp     eax, 103h
0x14002542f  jbe     short loc_140025465
0x140025431  mov     [rsp+268h+var_240], 80004005h; unsigned int
0x140025439  mov     r9d, 0E3Ah; unsigned int
0x14002543f  mov     edi, 80004005h
0x140025444  lea     rax, aCnovinterdlgSe_0; "CNovInterDlg::SetWallpaper"
0x14002544b  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140025452  mov     [rsp+268h+var_248], rax; unsigned __int16 *
0x140025457  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002545e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140025463  jmp     short loc_1400254CD
0x140025465  lea     rcx, [rsp+268h+pvParam]; lpFileName
0x14002546a  call    ?FileExists@@YAHPEAG@Z; FileExists(ushort *)
0x14002546f  test    eax, eax
0x140025471  jnz     short loc_140025480
0x140025473  mov     [rsp+268h+var_240], r14d
0x140025478  mov     r9d, 0E4Bh
0x14002547e  jmp     short loc_14002543F
0x140025480  xor     edx, edx; uiParam
0x140025482  mov     r9d, 3; fWinIni
0x140025488  mov     r8, rbp; pvParam
0x14002548b  lea     ecx, [rdx+14h]; uiAction
0x14002548e  call    cs:__imp_SystemParametersInfoW
0x140025495  nop     dword ptr [rax+rax+00h]
0x14002549a  test    eax, eax
0x14002549c  jnz     short loc_140025500
0x14002549e  mov     r9d, 0E57h; unsigned int
0x1400254a4  lea     rax, aCnovinterdlgSe_0; "CNovInterDlg::SetWallpaper"
0x1400254ab  mov     [rsp+268h+var_240], r14d; unsigned int
0x1400254b0  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x1400254b7  mov     [rsp+268h+var_248], rax; unsigned __int16 *
0x1400254bc  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400254c3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400254c8  mov     edi, 80004005h
0x1400254cd  mov     rbx, [rsi+80h]
0x1400254d4  test    rbx, rbx
0x1400254d7  jz      short loc_140025500
0x1400254d9  call    cs:__imp_GetProcessHeap
0x1400254e0  nop     dword ptr [rax+rax+00h]
0x1400254e5  mov     r8, rbx; lpMem
0x1400254e8  xor     edx, edx; dwFlags
0x1400254ea  mov     rcx, rax; hHeap
0x1400254ed  call    cs:__imp_HeapFree
0x1400254f4  nop     dword ptr [rax+rax+00h]
0x1400254f9  mov     [rsi+80h], r14
0x140025500  mov     eax, edi
0x140025502  mov     rcx, [rsp+268h+var_28]
0x14002550a  xor     rcx, rsp; StackCookie
0x14002550d  call    __security_check_cookie
0x140025512  lea     r11, [rsp+268h+var_18]
0x14002551a  mov     rbx, [r11+30h]
0x14002551e  mov     rbp, [r11+38h]
0x140025522  mov     rsp, r11
0x140025525  pop     r14
0x140025527  pop     rdi
0x140025528  pop     rsi
0x140025529  retn
```
