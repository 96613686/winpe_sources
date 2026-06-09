# CDoc::SaveImgCtxAs(CImgCtx *,int,ushort *,int)

- ea: `0x1808c4150`
- end: `0x1808c453a`
- name: `?SaveImgCtxAs@CDoc@@QEAAXPEAVCImgCtx@@HPEAGH@Z`
- size: `1002`
- prototype: `void __fastcall(CDoc *__hidden this, struct CImgCtx *, int, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800c7650`
- `0x180a66df0`
- `0x180a68928`

## callees

- `0x180282eac`
- `0x1802e5024`
- `0x180370004`
- `0x18043c328`
- `0x180494570`
- `0x1805915d4`
- `0x1805ccd98`
- `0x18073d694`
- `0x180771180`
- `0x1807d659c`
- `0x1807fbe34`
- `0x1808921ec`
- `0x1808c1af0`
- `0x1808c1e48`
- `0x1808c22f0`
- `0x1808c2d18`
- `0x1808c4150`
- `0x180a1f39c`
- `0x180a27614`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1808c4368`
- `msvcrt!wcsrchr` at `0x1808c4368`
- `KERNEL32!GetTempFileNameW` at `0x1808c4414`
- `KERNEL32!GetTempFileNameW` at `0x1808c4414`
- `KERNEL32!DeleteFileW` at `0x1808c42e7`
- `KERNEL32!DeleteFileW` at `0x1808c42e7`
- `KERNEL32!GetLastError` at `0x1808c441e`
- `KERNEL32!GetLastError` at `0x1808c441e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1808c420f`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1808c420f`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1808c43cb`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1808c43cb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808c43da`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808c43da`
- `SHLWAPI!PathUndecorateW` at `0x1808c4265`
- `SHLWAPI!PathUndecorateW` at `0x1808c4265`
- `SHELL32!SHGetFolderPathW` at `0x1808c43bf`
- `SHELL32!SHGetFolderPathW` at `0x1808c43bf`

## pseudocode

```c
void __fastcall CDoc::SaveImgCtxAs(CDoc *this, struct CImgCtx *a2, int a3, unsigned __int16 *a4, int a5)
{
  int v5; // r15d
  int v10; // edx
  int v11; // edi
  const struct MIMEINFO *MimeInfo; // rbx
  CDwnCtx *v13; // rcx
  HINSTANCE MUIHInst; // rax
  int WallpaperFilePath; // ebx
  WCHAR *v16; // rdi
  int v17; // r8d
  wchar_t *v18; // rax
  struct IStream **v19; // r8
  const unsigned __int16 *v20; // r14
  signed int LastError; // eax
  GUID v22; // xmm0
  int v23; // eax
  int pszPath; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h]
  struct IUnknown *v27; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *pv; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[4200]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+10D0h] [rbp+FD0h]
  unsigned __int16 *v33; // [rsp+10D8h] [rbp+FD8h]
  WCHAR Buffer[264]; // [rsp+10E0h] [rbp+FE0h] BYREF
  wchar_t Str[264]; // [rsp+12F0h] [rbp+11F0h] BYREF
  WCHAR FileName[264]; // [rsp+1500h] [rbp+1400h] BYREF
  WCHAR PathName[264]; // [rsp+1710h] [rbp+1610h] BYREF

  v5 = 0;
  v32 = 0;
  v30 = 0;
  v33 = 0;
  memset_0(v31, 0, 0x68u);
  pv = 0;
  if ( a3 == 2264 )
  {
    v11 = 8026;
    v25 = 8026;
    WallpaperFilePath = CDoc::GetWallpaperFilePath(Str, v10);
    if ( WallpaperFilePath )
      goto LABEL_13;
    v16 = 0;
    v5 = 1;
  }
  else
  {
    v11 = 8025;
    v25 = 8025;
    MimeInfo = CDwnCtx::GetMimeInfo(a2);
    if ( (unsigned int)CDwnCtx::GetFile(v13, (struct CUrlCacheEntry *)&v30) )
    {
      MUIHInst = GetMUIHInst();
      if ( !LoadStringW(MUIHInst, 0x1FD0u, Buffer, 260) )
      {
        WallpaperFilePath = GetLastWin32Error();
LABEL_13:
        if ( WallpaperFilePath < 0 )
        {
          CBase::SetErrorInfo(this, WallpaperFilePath);
          CDoc::ShowLastErrorInfo(this, WallpaperFilePath, v11);
          if ( a4 )
          {
            if ( a5 > 0 )
              *a4 = 0;
          }
        }
        goto LABEL_17;
      }
      MimeInfo = GetMimeInfoFromMimeType(L"image/png", 0);
      v16 = Buffer;
      v5 = 1;
    }
    else
    {
      v16 = v33;
      StringCchCopyW(Buffer, 0x104u, v33);
      PathUndecorateW(Buffer);
    }
    if ( MimeInfo )
      v17 = *((_DWORD *)MimeInfo + 6);
    else
      v17 = 0;
    WallpaperFilePath = CDoc::PromptSaveImage(this, Buffer, v17, Str, pszPath, &pv);
    if ( WallpaperFilePath )
    {
      v11 = 8025;
LABEL_12:
      v5 = 0;
      goto LABEL_13;
    }
  }
  v18 = wcsrchr(Str, 0x2Eu);
  v20 = v18;
  if ( v5 || v18 && (unsigned int)_tcsnipre(L".bmp", 4, v18, -1) )
  {
    v27 = 0;
    WallpaperFilePath = SHGetFolderPathW(0, 32, 0, 0, PathName);
    if ( WallpaperFilePath )
      goto LABEL_34;
    if ( !IsProtectedModeProcess() && !(unsigned __int8)IEConfiguration_GetBool(536870915) )
      StringCchCatW(PathName, 0x104u, L"\\Low");
    if ( !GetTempFileNameW(PathName, L"tmp", 0, FileName) )
    {
      LastError = GetLastError();
      WallpaperFilePath = LastError;
      if ( LastError > 0 )
        WallpaperFilePath = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_34;
    }
    WallpaperFilePath = CreateStreamOnFile(FileName, 4130, (struct IStream **)&v27);
    if ( WallpaperFilePath )
    {
LABEL_34:
      v11 = v25;
      goto LABEL_12;
    }
    v5 = 1;
    v29 = GUID_NULL;
    if ( v20 && (unsigned int)_tcsnipre(L".png", 4, v20, -1) )
      v22 = GUID_ContainerFormatPng;
    else
      v22 = GUID_ContainerFormatBmp;
    v29 = v22;
    WallpaperFilePath = CImgCtx::SaveImageToStream(a2, &v29, (struct IStream *)v27);
    ReleaseInterface(v27);
    if ( WallpaperFilePath )
    {
LABEL_50:
      v11 = v25;
      goto LABEL_13;
    }
    v16 = FileName;
  }
  else
  {
    v5 = 0;
  }
  if ( pv )
    v23 = CDoc::FinishImageSaveToStorageFile(v16, pv, v19);
  else
    v23 = CDoc::FinishImageSave(this, v16, Str, a3);
  WallpaperFilePath = v23;
  if ( v23 )
    goto LABEL_50;
  if ( a4 && a5 > 0 )
  {
    *a4 = 0;
    StringCchCopyW(a4, a5, Str);
  }
LABEL_17:
  if ( v5 )
    DeleteFileW(FileName);
  if ( pv )
    ((void (__fastcall *)(struct IUnknown *))pv->lpVtbl->Release)(pv);
  CUrlCacheEntry::~CUrlCacheEntry((CUrlCacheEntry *)&v30);
}

```

## disassembly

```asm
0x1808c4150  mov     [rsp-8+arg_10], rbx
0x1808c4155  push    rbp
0x1808c4156  push    rsi
0x1808c4157  push    rdi
0x1808c4158  push    r12
0x1808c415a  push    r13
0x1808c415c  push    r14
0x1808c415e  push    r15
0x1808c4160  lea     rbp, [rsp-1830h]
0x1808c4168  mov     eax, 1930h
0x1808c416d  call    _alloca_probe
0x1808c4172  sub     rsp, rax
0x1808c4175  mov     rax, cs:__security_cookie
0x1808c417c  xor     rax, rsp
0x1808c417f  mov     [rbp+1860h+var_40], rax
0x1808c4186  xor     r15d, r15d
0x1808c4189  mov     ebx, r8d
0x1808c418c  mov     r13, rdx
0x1808c418f  mov     [rsp+1960h+var_1928], ebx
0x1808c4193  mov     r12, rcx
0x1808c4196  mov     [rsp+1960h+var_192C], r15d
0x1808c419b  xor     edx, edx; Val
0x1808c419d  mov     [rbp+1860h+var_890], r15
0x1808c41a4  lea     r8d, [r15+68h]; Size
0x1808c41a8  mov     [rsp+1960h+var_1900], r15
0x1808c41ad  lea     rcx, [rsp+1960h+var_18F8]; void *
0x1808c41b2  mov     [rbp+1860h+var_888], r15
0x1808c41b9  mov     rsi, r9
0x1808c41bc  call    memset_0
0x1808c41c1  mov     [rsp+1960h+var_1918], r15
0x1808c41c6  mov     r14d, 104h
0x1808c41cc  cmp     ebx, 8D8h
0x1808c41d2  jz      loc_1808C4337
0x1808c41d8  mov     rcx, r13; this
0x1808c41db  call    ?GetMimeInfo@CDwnCtx@@QEAAPEBUMIMEINFO@@XZ; CDwnCtx::GetMimeInfo(void)
0x1808c41e0  mov     edi, 1F59h
0x1808c41e5  lea     rdx, [rsp+1960h+var_1900]; struct CUrlCacheEntry *
0x1808c41ea  mov     [rsp+1960h+var_1930], edi
0x1808c41ee  mov     rbx, rax
0x1808c41f1  call    ?GetFile@CDwnCtx@@QEAAJPEAVCUrlCacheEntry@@@Z; CDwnCtx::GetFile(CUrlCacheEntry *)
0x1808c41f6  test    eax, eax
0x1808c41f8  jz      short loc_1808C4245
0x1808c41fa  call    ?GetMUIHInst@@YAPEAUHINSTANCE__@@XZ; GetMUIHInst(void)
0x1808c41ff  mov     rcx, rax; hInstance
0x1808c4202  lea     r8, [rbp+1860h+Buffer]; lpBuffer
0x1808c4209  mov     r9d, r14d; cchBufferMax
0x1808c420c  lea     edx, [rdi+77h]; uID
0x1808c420f  call    cs:__imp_LoadStringW
0x1808c4215  test    eax, eax
0x1808c4217  jnz     short loc_1808C4225
0x1808c4219  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1808c421e  mov     ebx, eax
0x1808c4220  jmp     loc_1808C42AD
0x1808c4225  xor     edx, edx; bool
0x1808c4227  lea     rcx, aImagePng; "image/png"
0x1808c422e  call    ?GetMimeInfoFromMimeType@@YAPEBUMIMEINFO@@PEBG_N@Z; GetMimeInfoFromMimeType(ushort const *,bool)
0x1808c4233  mov     rbx, rax
0x1808c4236  lea     rdi, [rbp+1860h+Buffer]
0x1808c423d  mov     r15d, 1
0x1808c4243  jmp     short loc_1808C426B
0x1808c4245  mov     rdi, [rbp+1860h+var_888]
0x1808c424c  lea     rcx, [rbp+1860h+Buffer]; unsigned __int16 *
0x1808c4253  mov     r8, rdi; unsigned __int16 *
0x1808c4256  mov     rdx, r14; unsigned __int64
0x1808c4259  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1808c425e  lea     rcx, [rbp+1860h+Buffer]; pszPath
0x1808c4265  call    cs:__imp_PathUndecorateW
0x1808c426b  test    rbx, rbx
0x1808c426e  jz      short loc_1808C4276
0x1808c4270  mov     r8d, [rbx+18h]
0x1808c4274  jmp     short loc_1808C4279
0x1808c4276  xor     r8d, r8d; int
0x1808c4279  lea     rax, [rsp+1960h+var_1918]
0x1808c427e  mov     rcx, r12; this
0x1808c4281  lea     r9, [rbp+1860h+Str]; unsigned __int16 *
0x1808c4288  mov     [rsp+1960h+pv], rax; pv
0x1808c428d  lea     rdx, [rbp+1860h+Buffer]; unsigned __int16 *
0x1808c4294  call    ?PromptSaveImage@CDoc@@AEAAJPEBGHPEAGHPEAPEAUIUnknown@@@Z; CDoc::PromptSaveImage(ushort const *,int,ushort *,int,IUnknown * *)
0x1808c4299  mov     ebx, eax
0x1808c429b  test    eax, eax
0x1808c429d  jz      loc_1808C435C
0x1808c42a3  mov     edi, 1F59h
0x1808c42a8  mov     r15d, [rsp+1960h+var_192C]
0x1808c42ad  test    ebx, ebx
0x1808c42af  jns     short loc_1808C42DB
0x1808c42b1  mov     edx, ebx; int
0x1808c42b3  mov     rcx, r12; this
0x1808c42b6  call    ?SetErrorInfo@CBase@@QEBAJJ@Z; CBase::SetErrorInfo(long)
0x1808c42bb  mov     r8d, edi; int
0x1808c42be  mov     edx, ebx; int
0x1808c42c0  mov     rcx, r12; this
0x1808c42c3  call    ?ShowLastErrorInfo@CDoc@@QEAAJJH@Z; CDoc::ShowLastErrorInfo(long,int)
0x1808c42c8  test    rsi, rsi
0x1808c42cb  jz      short loc_1808C42DB
0x1808c42cd  cmp     [rbp+1860h+arg_20], 0
0x1808c42d4  jle     short loc_1808C42DB
0x1808c42d6  xor     eax, eax
0x1808c42d8  mov     [rsi], ax
0x1808c42db  test    r15d, r15d
0x1808c42de  jz      short loc_1808C42ED
0x1808c42e0  lea     rcx, [rbp+1860h+FileName]; lpFileName
0x1808c42e7  call    cs:__imp_DeleteFileW
0x1808c42ed  mov     rcx, [rsp+1960h+var_1918]
0x1808c42f2  test    rcx, rcx
0x1808c42f5  jz      short loc_1808C4303
0x1808c42f7  mov     rax, [rcx]
0x1808c42fa  mov     rax, [rax+10h]
0x1808c42fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808c4303  lea     rcx, [rsp+1960h+var_1900]; this
0x1808c4308  call    ??1CUrlCacheEntry@@QEAA@XZ; CUrlCacheEntry::~CUrlCacheEntry(void)
0x1808c430d  mov     rcx, [rbp+1860h+var_40]
0x1808c4314  xor     rcx, rsp; StackCookie
0x1808c4317  call    __security_check_cookie
0x1808c431c  mov     rbx, [rsp+1960h+arg_10]
0x1808c4324  add     rsp, 1930h
0x1808c432b  pop     r15
0x1808c432d  pop     r14
0x1808c432f  pop     r13
0x1808c4331  pop     r12
0x1808c4333  pop     rdi
0x1808c4334  pop     rsi
0x1808c4335  pop     rbp
0x1808c4336  retn
0x1808c4337  mov     edi, 1F5Ah
0x1808c433c  lea     rcx, [rbp+1860h+Str]; unsigned __int16 *
0x1808c4343  mov     [rsp+1960h+var_1930], edi
0x1808c4347  call    ?GetWallpaperFilePath@CDoc@@CAJPEAGH@Z; CDoc::GetWallpaperFilePath(ushort *,int)
0x1808c434c  mov     ebx, eax
0x1808c434e  test    eax, eax
0x1808c4350  jnz     loc_1808C42AD
0x1808c4356  xor     edi, edi
0x1808c4358  lea     r15d, [rax+1]
0x1808c435c  mov     edx, 2Eh ; '.'; Ch
0x1808c4361  lea     rcx, [rbp+1860h+Str]; Str
0x1808c4368  call    cs:__imp_wcsrchr
0x1808c436e  mov     r14, rax
0x1808c4371  test    r15d, r15d
0x1808c4374  jnz     short loc_1808C439E
0x1808c4376  test    rax, rax
0x1808c4379  jz      loc_1808C44C9
0x1808c437f  or      r9d, 0FFFFFFFFh; int
0x1808c4383  lea     edx, [r15+4]; cchCount2
0x1808c4387  mov     r8, rax; unsigned __int16 *
0x1808c438a  lea     rcx, aBmp; ".bmp"
0x1808c4391  call    ?_tcsnipre@@YAHPEBGH0H@Z; _tcsnipre(ushort const *,int,ushort const *,int)
0x1808c4396  test    eax, eax
0x1808c4398  jz      loc_1808C44C9
0x1808c439e  xor     r9d, r9d; dwFlags
0x1808c43a1  mov     [rsp+1960h+var_1920], 0
0x1808c43aa  lea     rax, [rbp+1860h+PathName]
0x1808c43b1  xor     r8d, r8d; hToken
0x1808c43b4  xor     ecx, ecx; hwnd
0x1808c43b6  mov     [rsp+1960h+pszPath], rax; pszPath
0x1808c43bb  lea     edx, [r9+20h]; csidl
0x1808c43bf  call    cs:__imp_SHGetFolderPathW
0x1808c43c5  mov     ebx, eax
0x1808c43c7  test    eax, eax
0x1808c43c9  jnz     short loc_1808C4433
0x1808c43cb  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1808c43d1  test    eax, eax
0x1808c43d3  jnz     short loc_1808C43FC
0x1808c43d5  mov     ecx, 20000003h
0x1808c43da  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1808c43e0  test    al, al
0x1808c43e2  jnz     short loc_1808C43FC
0x1808c43e4  lea     r8, aLow; "\\Low"
0x1808c43eb  mov     edx, 104h; unsigned __int64
0x1808c43f0  lea     rcx, [rbp+1860h+PathName]; unsigned __int16 *
0x1808c43f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1808c43fc  lea     r9, [rbp+1860h+FileName]; lpTempFileName
0x1808c4403  xor     r8d, r8d; uUnique
0x1808c4406  lea     rdx, aTmp; "tmp"
0x1808c440d  lea     rcx, [rbp+1860h+PathName]; lpPathName
0x1808c4414  call    cs:__imp_GetTempFileNameW
0x1808c441a  test    eax, eax
0x1808c441c  jnz     short loc_1808C443C
0x1808c441e  call    cs:__imp_GetLastError
0x1808c4424  mov     ebx, eax
0x1808c4426  test    eax, eax
0x1808c4428  jle     short loc_1808C4433
0x1808c442a  movzx   ebx, ax
0x1808c442d  or      ebx, 80070000h
0x1808c4433  mov     edi, [rsp+1960h+var_1930]
0x1808c4437  jmp     loc_1808C42A8
0x1808c443c  lea     r8, [rsp+1960h+var_1920]; struct IStream **
0x1808c4441  mov     edx, 1022h; unsigned int
0x1808c4446  lea     rcx, [rbp+1860h+FileName]; unsigned __int16 *
0x1808c444d  call    ?CreateStreamOnFile@@YAJPEBGKPEAPEAUIStream@@@Z; CreateStreamOnFile(ushort const *,ulong,IStream * *)
0x1808c4452  mov     ebx, eax
0x1808c4454  test    eax, eax
0x1808c4456  jnz     short loc_1808C4433
0x1808c4458  lea     r15d, [rax+1]
0x1808c445c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1808c4463  movdqu  xmmword ptr [rsp+1960h+var_1910.Data1], xmm0
0x1808c4469  test    r14, r14
0x1808c446c  jz      short loc_1808C4491
0x1808c446e  or      r9d, 0FFFFFFFFh; int
0x1808c4472  lea     edx, [rax+4]; cchCount2
0x1808c4475  mov     r8, r14; unsigned __int16 *
0x1808c4478  lea     rcx, aPng; ".png"
0x1808c447f  call    ?_tcsnipre@@YAHPEBGH0H@Z; _tcsnipre(ushort const *,int,ushort const *,int)
0x1808c4484  test    eax, eax
0x1808c4486  jz      short loc_1808C4491
0x1808c4488  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatPng.Data1
0x1808c448f  jmp     short loc_1808C4498
0x1808c4491  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatBmp.Data1
0x1808c4498  mov     r8, [rsp+1960h+var_1920]; struct IStream *
0x1808c449d  lea     rdx, [rsp+1960h+var_1910]; struct _GUID *
0x1808c44a2  mov     rcx, r13; this
0x1808c44a5  movdqu  xmmword ptr [rsp+1960h+var_1910.Data1], xmm0
0x1808c44ab  call    ?SaveImageToStream@CImgCtx@@QEAAJAEBU_GUID@@PEAUIStream@@@Z; CImgCtx::SaveImageToStream(_GUID const &,IStream *)
0x1808c44b0  mov     rcx, [rsp+1960h+var_1920]; struct IUnknown *
0x1808c44b5  mov     ebx, eax
0x1808c44b7  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1808c44bc  test    ebx, ebx
0x1808c44be  jnz     short loc_1808C4531
0x1808c44c0  lea     rdi, [rbp+1860h+FileName]
0x1808c44c7  jmp     short loc_1808C44CE
0x1808c44c9  mov     r15d, [rsp+1960h+var_192C]
0x1808c44ce  mov     rdx, [rsp+1960h+var_1918]; this
0x1808c44d3  test    rdx, rdx
0x1808c44d6  jz      short loc_1808C44E2
0x1808c44d8  mov     rcx, rdi; unsigned __int16 *
0x1808c44db  call    ?FinishImageSaveToStorageFile@CDoc@@CAJPEBGPEAUIUnknown@@@Z; CDoc::FinishImageSaveToStorageFile(ushort const *,IUnknown *)
0x1808c44e0  jmp     short loc_1808C44F9
0x1808c44e2  mov     r9d, [rsp+1960h+var_1928]; int
0x1808c44e7  lea     r8, [rbp+1860h+Str]; pvParam
0x1808c44ee  mov     rdx, rdi; lpExistingFileName
0x1808c44f1  mov     rcx, r12; this
0x1808c44f4  call    ?FinishImageSave@CDoc@@AEAAJPEBG0H@Z; CDoc::FinishImageSave(ushort const *,ushort const *,int)
0x1808c44f9  mov     ebx, eax
0x1808c44fb  test    eax, eax
0x1808c44fd  jnz     short loc_1808C4531
0x1808c44ff  test    rsi, rsi
0x1808c4502  jz      loc_1808C42DB
0x1808c4508  movsxd  rcx, [rbp+1860h+arg_20]
0x1808c450f  test    ecx, ecx
0x1808c4511  jle     loc_1808C42DB
0x1808c4517  mov     rdx, rcx; unsigned __int64
0x1808c451a  mov     [rsi], ax
0x1808c451d  mov     rcx, rsi; unsigned __int16 *
0x1808c4520  lea     r8, [rbp+1860h+Str]; unsigned __int16 *
0x1808c4527  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1808c452c  jmp     loc_1808C42DB
0x1808c4531  mov     edi, [rsp+1960h+var_1930]
0x1808c4535  jmp     loc_1808C42AD
```
