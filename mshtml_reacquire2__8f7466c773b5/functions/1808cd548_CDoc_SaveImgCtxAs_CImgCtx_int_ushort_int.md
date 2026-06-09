# CDoc::SaveImgCtxAs(CImgCtx *,int,ushort *,int)

- ea: `0x1808cd548`
- end: `0x1808cd96d`
- name: `?SaveImgCtxAs@CDoc@@QEAAXPEAVCImgCtx@@HPEAGH@Z`
- size: `1061`
- prototype: `void __fastcall(CDoc *__hidden this, struct CImgCtx *, int, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180410ae0`
- `0x180a7b310`
- `0x180a7ced0`

## callees

- `0x1800ea428`
- `0x18024bed4`
- `0x18030172c`
- `0x18040ac58`
- `0x180413b4c`
- `0x1805be6ec`
- `0x1805c4c24`
- `0x180745a1c`
- `0x180775670`
- `0x1807e1ba4`
- `0x180806aac`
- `0x18089a5b4`
- `0x1808cacf0`
- `0x1808cb088`
- `0x1808cb568`
- `0x1808cc020`
- `0x1808cd548`
- `0x180a31a58`
- `0x180a3a3dc`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1808cd773`
- `msvcrt!wcsrchr` at `0x1808cd773`
- `KERNEL32!GetTempFileNameW` at `0x1808cd83b`
- `KERNEL32!GetTempFileNameW` at `0x1808cd83b`
- `KERNEL32!DeleteFileW` at `0x1808cd6eb`
- `KERNEL32!DeleteFileW` at `0x1808cd6eb`
- `KERNEL32!GetLastError` at `0x1808cd84b`
- `KERNEL32!GetLastError` at `0x1808cd84b`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1808cd607`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1808cd607`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1808cd7e6`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1808cd7e6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808cd7fb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808cd7fb`
- `SHLWAPI!PathUndecorateW` at `0x1808cd663`
- `SHLWAPI!PathUndecorateW` at `0x1808cd663`
- `SHELL32!SHGetFolderPathW` at `0x1808cd7d0`
- `SHELL32!SHGetFolderPathW` at `0x1808cd7d0`

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
  const unsigned __int16 *v19; // r14
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  signed int LastError; // eax
  GUID v24; // xmm0
  int v25; // eax
  int pszPath; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+30h] [rbp-D0h]
  struct IUnknown *v29; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *pv; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[4200]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+10D0h] [rbp+FD0h]
  unsigned __int16 *v35; // [rsp+10D8h] [rbp+FD8h]
  WCHAR Buffer[264]; // [rsp+10E0h] [rbp+FE0h] BYREF
  wchar_t Str[264]; // [rsp+12F0h] [rbp+11F0h] BYREF
  WCHAR FileName[264]; // [rsp+1500h] [rbp+1400h] BYREF
  WCHAR PathName[264]; // [rsp+1710h] [rbp+1610h] BYREF

  v5 = 0;
  v34 = 0;
  v32 = 0;
  v35 = 0;
  memset_0(v33, 0, 0x68u);
  pv = 0;
  if ( a3 == 2264 )
  {
    v11 = 8026;
    v27 = 8026;
    WallpaperFilePath = CDoc::GetWallpaperFilePath(Str, v10);
    if ( WallpaperFilePath )
      goto LABEL_13;
    v16 = 0;
    v5 = 1;
  }
  else
  {
    v11 = 8025;
    v27 = 8025;
    MimeInfo = CDwnCtx::GetMimeInfo(a2);
    if ( (unsigned int)CDwnCtx::GetFile(v13, (struct CUrlCacheEntry *)&v32) )
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
      v16 = v35;
      StringCchCopyW(Buffer, 0x104u, v35);
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
  v19 = v18;
  if ( v5 || v18 && (unsigned int)_tcsnipre(L".bmp", 4, v18, -1) )
  {
    v29 = 0;
    WallpaperFilePath = SHGetFolderPathW(0, 32, 0, 0, PathName);
    if ( WallpaperFilePath )
      goto LABEL_34;
    if ( !IsProtectedModeProcess() && !(unsigned __int8)IEConfiguration_GetBool(536870915, v20, v21, v22) )
      StringCchCatW(PathName, 0x104u, L"\\Low");
    if ( !GetTempFileNameW(PathName, L"tmp", 0, FileName) )
    {
      LastError = GetLastError();
      WallpaperFilePath = LastError;
      if ( LastError > 0 )
        WallpaperFilePath = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_34;
    }
    WallpaperFilePath = CreateStreamOnFile(FileName, 0x1022u, (struct IStream **)&v29);
    if ( WallpaperFilePath )
    {
LABEL_34:
      v11 = v27;
      goto LABEL_12;
    }
    v5 = 1;
    v31 = GUID_NULL;
    if ( v19 && (unsigned int)_tcsnipre(L".png", 4, v19, -1) )
      v24 = GUID_ContainerFormatPng;
    else
      v24 = GUID_ContainerFormatBmp;
    v31 = v24;
    WallpaperFilePath = CImgCtx::SaveImageToStream(a2, &v31, (struct IStream *)v29);
    ReleaseInterface(v29);
    if ( WallpaperFilePath )
    {
LABEL_50:
      v11 = v27;
      goto LABEL_13;
    }
    v16 = FileName;
  }
  else
  {
    v5 = 0;
  }
  if ( pv )
    v25 = CDoc::FinishImageSaveToStorageFile(v16, pv);
  else
    v25 = CDoc::FinishImageSave(this, v16, Str, a3);
  WallpaperFilePath = v25;
  if ( v25 )
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
  CUrlCacheEntry::~CUrlCacheEntry((CUrlCacheEntry *)&v32);
}

```

## disassembly

```asm
0x1808cd548  mov     [rsp-8+arg_10], rbx
0x1808cd54d  push    rbp
0x1808cd54e  push    rsi
0x1808cd54f  push    rdi
0x1808cd550  push    r12
0x1808cd552  push    r13
0x1808cd554  push    r14
0x1808cd556  push    r15
0x1808cd558  lea     rbp, [rsp-1830h]
0x1808cd560  mov     eax, 1930h
0x1808cd565  call    _alloca_probe
0x1808cd56a  sub     rsp, rax
0x1808cd56d  mov     rax, cs:__security_cookie
0x1808cd574  xor     rax, rsp
0x1808cd577  mov     [rbp+1860h+var_40], rax
0x1808cd57e  xor     r15d, r15d
0x1808cd581  mov     ebx, r8d
0x1808cd584  mov     r13, rdx
0x1808cd587  mov     [rsp+1960h+var_1928], ebx
0x1808cd58b  mov     r12, rcx
0x1808cd58e  mov     [rsp+1960h+var_192C], r15d
0x1808cd593  xor     edx, edx; Val
0x1808cd595  mov     [rbp+1860h+var_890], r15
0x1808cd59c  lea     r8d, [r15+68h]; Size
0x1808cd5a0  mov     [rsp+1960h+var_1900], r15
0x1808cd5a5  lea     rcx, [rsp+1960h+var_18F8]; void *
0x1808cd5aa  mov     [rbp+1860h+var_888], r15
0x1808cd5b1  mov     rsi, r9
0x1808cd5b4  call    memset_0
0x1808cd5b9  mov     [rsp+1960h+var_1918], r15
0x1808cd5be  mov     r14d, 104h
0x1808cd5c4  cmp     ebx, 8D8h
0x1808cd5ca  jz      loc_1808CD742
0x1808cd5d0  mov     rcx, r13; this
0x1808cd5d3  call    ?GetMimeInfo@CDwnCtx@@QEAAPEBUMIMEINFO@@XZ; CDwnCtx::GetMimeInfo(void)
0x1808cd5d8  mov     edi, 1F59h
0x1808cd5dd  lea     rdx, [rsp+1960h+var_1900]; struct CUrlCacheEntry *
0x1808cd5e2  mov     [rsp+1960h+var_1930], edi
0x1808cd5e6  mov     rbx, rax
0x1808cd5e9  call    ?GetFile@CDwnCtx@@QEAAJPEAVCUrlCacheEntry@@@Z; CDwnCtx::GetFile(CUrlCacheEntry *)
0x1808cd5ee  test    eax, eax
0x1808cd5f0  jz      short loc_1808CD643
0x1808cd5f2  call    ?GetMUIHInst@@YAPEAUHINSTANCE__@@XZ; GetMUIHInst(void)
0x1808cd5f7  mov     rcx, rax; hInstance
0x1808cd5fa  lea     r8, [rbp+1860h+Buffer]; lpBuffer
0x1808cd601  mov     r9d, r14d; cchBufferMax
0x1808cd604  lea     edx, [rdi+77h]; uID
0x1808cd607  call    cs:__imp_LoadStringW
0x1808cd60e  nop     dword ptr [rax+rax+00h]
0x1808cd613  test    eax, eax
0x1808cd615  jnz     short loc_1808CD623
0x1808cd617  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1808cd61c  mov     ebx, eax
0x1808cd61e  jmp     loc_1808CD6B1
0x1808cd623  xor     edx, edx; bool
0x1808cd625  lea     rcx, aImagePng; "image/png"
0x1808cd62c  call    ?GetMimeInfoFromMimeType@@YAPEBUMIMEINFO@@PEBG_N@Z; GetMimeInfoFromMimeType(ushort const *,bool)
0x1808cd631  mov     rbx, rax
0x1808cd634  lea     rdi, [rbp+1860h+Buffer]
0x1808cd63b  mov     r15d, 1
0x1808cd641  jmp     short loc_1808CD66F
0x1808cd643  mov     rdi, [rbp+1860h+var_888]
0x1808cd64a  lea     rcx, [rbp+1860h+Buffer]; unsigned __int16 *
0x1808cd651  mov     r8, rdi; unsigned __int16 *
0x1808cd654  mov     rdx, r14; unsigned __int64
0x1808cd657  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1808cd65c  lea     rcx, [rbp+1860h+Buffer]; pszPath
0x1808cd663  call    cs:__imp_PathUndecorateW
0x1808cd66a  nop     dword ptr [rax+rax+00h]
0x1808cd66f  test    rbx, rbx
0x1808cd672  jz      short loc_1808CD67A
0x1808cd674  mov     r8d, [rbx+18h]
0x1808cd678  jmp     short loc_1808CD67D
0x1808cd67a  xor     r8d, r8d; int
0x1808cd67d  lea     rax, [rsp+1960h+var_1918]
0x1808cd682  mov     rcx, r12; this
0x1808cd685  lea     r9, [rbp+1860h+Str]; unsigned __int16 *
0x1808cd68c  mov     [rsp+1960h+pv], rax; pv
0x1808cd691  lea     rdx, [rbp+1860h+Buffer]; unsigned __int16 *
0x1808cd698  call    ?PromptSaveImage@CDoc@@AEAAJPEBGHPEAGHPEAPEAUIUnknown@@@Z; CDoc::PromptSaveImage(ushort const *,int,ushort *,int,IUnknown * *)
0x1808cd69d  mov     ebx, eax
0x1808cd69f  test    eax, eax
0x1808cd6a1  jz      loc_1808CD767
0x1808cd6a7  mov     edi, 1F59h
0x1808cd6ac  mov     r15d, [rsp+1960h+var_192C]
0x1808cd6b1  test    ebx, ebx
0x1808cd6b3  jns     short loc_1808CD6DF
0x1808cd6b5  mov     edx, ebx; int
0x1808cd6b7  mov     rcx, r12; this
0x1808cd6ba  call    ?SetErrorInfo@CBase@@QEBAJJ@Z; CBase::SetErrorInfo(long)
0x1808cd6bf  mov     r8d, edi; int
0x1808cd6c2  mov     edx, ebx; int
0x1808cd6c4  mov     rcx, r12; this
0x1808cd6c7  call    ?ShowLastErrorInfo@CDoc@@QEAAJJH@Z; CDoc::ShowLastErrorInfo(long,int)
0x1808cd6cc  test    rsi, rsi
0x1808cd6cf  jz      short loc_1808CD6DF
0x1808cd6d1  cmp     [rbp+1860h+arg_20], 0
0x1808cd6d8  jle     short loc_1808CD6DF
0x1808cd6da  xor     eax, eax
0x1808cd6dc  mov     [rsi], ax
0x1808cd6df  test    r15d, r15d
0x1808cd6e2  jz      short loc_1808CD6F7
0x1808cd6e4  lea     rcx, [rbp+1860h+FileName]; lpFileName
0x1808cd6eb  call    cs:__imp_DeleteFileW
0x1808cd6f2  nop     dword ptr [rax+rax+00h]
0x1808cd6f7  mov     rcx, [rsp+1960h+var_1918]
0x1808cd6fc  test    rcx, rcx
0x1808cd6ff  jz      short loc_1808CD70D
0x1808cd701  mov     rax, [rcx]
0x1808cd704  mov     rax, [rax+10h]
0x1808cd708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808cd70d  lea     rcx, [rsp+1960h+var_1900]; this
0x1808cd712  call    ??1CUrlCacheEntry@@QEAA@XZ; CUrlCacheEntry::~CUrlCacheEntry(void)
0x1808cd717  mov     rcx, [rbp+1860h+var_40]
0x1808cd71e  xor     rcx, rsp; StackCookie
0x1808cd721  call    __security_check_cookie
0x1808cd726  mov     rbx, [rsp+1960h+arg_10]
0x1808cd72e  add     rsp, 1930h
0x1808cd735  pop     r15
0x1808cd737  pop     r14
0x1808cd739  pop     r13
0x1808cd73b  pop     r12
0x1808cd73d  pop     rdi
0x1808cd73e  pop     rsi
0x1808cd73f  pop     rbp
0x1808cd740  retn
0x1808cd742  mov     edi, 1F5Ah
0x1808cd747  lea     rcx, [rbp+1860h+Str]; unsigned __int16 *
0x1808cd74e  mov     [rsp+1960h+var_1930], edi
0x1808cd752  call    ?GetWallpaperFilePath@CDoc@@CAJPEAGH@Z; CDoc::GetWallpaperFilePath(ushort *,int)
0x1808cd757  mov     ebx, eax
0x1808cd759  test    eax, eax
0x1808cd75b  jnz     loc_1808CD6B1
0x1808cd761  xor     edi, edi
0x1808cd763  lea     r15d, [rax+1]
0x1808cd767  mov     edx, 2Eh ; '.'; Ch
0x1808cd76c  lea     rcx, [rbp+1860h+Str]; Str
0x1808cd773  call    cs:__imp_wcsrchr
0x1808cd77a  nop     dword ptr [rax+rax+00h]
0x1808cd77f  mov     r14, rax
0x1808cd782  test    r15d, r15d
0x1808cd785  jnz     short loc_1808CD7AF
0x1808cd787  test    rax, rax
0x1808cd78a  jz      loc_1808CD8FC
0x1808cd790  or      r9d, 0FFFFFFFFh; int
0x1808cd794  lea     edx, [r15+4]; cchCount2
0x1808cd798  mov     r8, rax; unsigned __int16 *
0x1808cd79b  lea     rcx, aBmp; ".bmp"
0x1808cd7a2  call    ?_tcsnipre@@YAHPEBGH0H@Z; _tcsnipre(ushort const *,int,ushort const *,int)
0x1808cd7a7  test    eax, eax
0x1808cd7a9  jz      loc_1808CD8FC
0x1808cd7af  xor     r9d, r9d; dwFlags
0x1808cd7b2  mov     [rsp+1960h+var_1920], 0
0x1808cd7bb  lea     rax, [rbp+1860h+PathName]
0x1808cd7c2  xor     r8d, r8d; hToken
0x1808cd7c5  xor     ecx, ecx; hwnd
0x1808cd7c7  mov     [rsp+1960h+pszPath], rax; pszPath
0x1808cd7cc  lea     edx, [r9+20h]; csidl
0x1808cd7d0  call    cs:__imp_SHGetFolderPathW
0x1808cd7d7  nop     dword ptr [rax+rax+00h]
0x1808cd7dc  mov     ebx, eax
0x1808cd7de  test    eax, eax
0x1808cd7e0  jnz     loc_1808CD866
0x1808cd7e6  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1808cd7ed  nop     dword ptr [rax+rax+00h]
0x1808cd7f2  test    eax, eax
0x1808cd7f4  jnz     short loc_1808CD823
0x1808cd7f6  mov     ecx, 20000003h
0x1808cd7fb  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1808cd802  nop     dword ptr [rax+rax+00h]
0x1808cd807  test    al, al
0x1808cd809  jnz     short loc_1808CD823
0x1808cd80b  lea     r8, aLow; "\\Low"
0x1808cd812  mov     edx, 104h; unsigned __int64
0x1808cd817  lea     rcx, [rbp+1860h+PathName]; unsigned __int16 *
0x1808cd81e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1808cd823  lea     r9, [rbp+1860h+FileName]; lpTempFileName
0x1808cd82a  xor     r8d, r8d; uUnique
0x1808cd82d  lea     rdx, aTmp; "tmp"
0x1808cd834  lea     rcx, [rbp+1860h+PathName]; lpPathName
0x1808cd83b  call    cs:__imp_GetTempFileNameW
0x1808cd842  nop     dword ptr [rax+rax+00h]
0x1808cd847  test    eax, eax
0x1808cd849  jnz     short loc_1808CD86F
0x1808cd84b  call    cs:__imp_GetLastError
0x1808cd852  nop     dword ptr [rax+rax+00h]
0x1808cd857  mov     ebx, eax
0x1808cd859  test    eax, eax
0x1808cd85b  jle     short loc_1808CD866
0x1808cd85d  movzx   ebx, ax
0x1808cd860  or      ebx, 80070000h
0x1808cd866  mov     edi, [rsp+1960h+var_1930]
0x1808cd86a  jmp     loc_1808CD6AC
0x1808cd86f  lea     r8, [rsp+1960h+var_1920]; struct IStream **
0x1808cd874  mov     edx, 1022h; unsigned int
0x1808cd879  lea     rcx, [rbp+1860h+FileName]; unsigned __int16 *
0x1808cd880  call    ?CreateStreamOnFile@@YAJPEBGKPEAPEAUIStream@@@Z; CreateStreamOnFile(ushort const *,ulong,IStream * *)
0x1808cd885  mov     ebx, eax
0x1808cd887  test    eax, eax
0x1808cd889  jnz     short loc_1808CD866
0x1808cd88b  lea     r15d, [rax+1]
0x1808cd88f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1808cd896  movdqu  xmmword ptr [rsp+1960h+var_1910.Data1], xmm0
0x1808cd89c  test    r14, r14
0x1808cd89f  jz      short loc_1808CD8C4
0x1808cd8a1  or      r9d, 0FFFFFFFFh; int
0x1808cd8a5  lea     edx, [rax+4]; cchCount2
0x1808cd8a8  mov     r8, r14; unsigned __int16 *
0x1808cd8ab  lea     rcx, aPng; ".png"
0x1808cd8b2  call    ?_tcsnipre@@YAHPEBGH0H@Z; _tcsnipre(ushort const *,int,ushort const *,int)
0x1808cd8b7  test    eax, eax
0x1808cd8b9  jz      short loc_1808CD8C4
0x1808cd8bb  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatPng.Data1
0x1808cd8c2  jmp     short loc_1808CD8CB
0x1808cd8c4  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatBmp.Data1
0x1808cd8cb  mov     r8, [rsp+1960h+var_1920]; struct IStream *
0x1808cd8d0  lea     rdx, [rsp+1960h+var_1910]; struct _GUID *
0x1808cd8d5  mov     rcx, r13; this
0x1808cd8d8  movdqu  xmmword ptr [rsp+1960h+var_1910.Data1], xmm0
0x1808cd8de  call    ?SaveImageToStream@CImgCtx@@QEAAJAEBU_GUID@@PEAUIStream@@@Z; CImgCtx::SaveImageToStream(_GUID const &,IStream *)
0x1808cd8e3  mov     rcx, [rsp+1960h+var_1920]; struct IUnknown *
0x1808cd8e8  mov     ebx, eax
0x1808cd8ea  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1808cd8ef  test    ebx, ebx
0x1808cd8f1  jnz     short loc_1808CD964
0x1808cd8f3  lea     rdi, [rbp+1860h+FileName]
0x1808cd8fa  jmp     short loc_1808CD901
0x1808cd8fc  mov     r15d, [rsp+1960h+var_192C]
0x1808cd901  mov     rdx, [rsp+1960h+var_1918]; this
0x1808cd906  test    rdx, rdx
0x1808cd909  jz      short loc_1808CD915
0x1808cd90b  mov     rcx, rdi; unsigned __int16 *
0x1808cd90e  call    ?FinishImageSaveToStorageFile@CDoc@@CAJPEBGPEAUIUnknown@@@Z; CDoc::FinishImageSaveToStorageFile(ushort const *,IUnknown *)
0x1808cd913  jmp     short loc_1808CD92C
0x1808cd915  mov     r9d, [rsp+1960h+var_1928]; int
0x1808cd91a  lea     r8, [rbp+1860h+Str]; pvParam
0x1808cd921  mov     rdx, rdi; lpExistingFileName
0x1808cd924  mov     rcx, r12; this
0x1808cd927  call    ?FinishImageSave@CDoc@@AEAAJPEBG0H@Z; CDoc::FinishImageSave(ushort const *,ushort const *,int)
0x1808cd92c  mov     ebx, eax
0x1808cd92e  test    eax, eax
0x1808cd930  jnz     short loc_1808CD964
0x1808cd932  test    rsi, rsi
0x1808cd935  jz      loc_1808CD6DF
0x1808cd93b  movsxd  rcx, [rbp+1860h+arg_20]
0x1808cd942  test    ecx, ecx
0x1808cd944  jle     loc_1808CD6DF
0x1808cd94a  mov     rdx, rcx; unsigned __int64
0x1808cd94d  mov     [rsi], ax
0x1808cd950  mov     rcx, rsi; unsigned __int16 *
0x1808cd953  lea     r8, [rbp+1860h+Str]; unsigned __int16 *
0x1808cd95a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1808cd95f  jmp     loc_1808CD6DF
0x1808cd964  mov     edi, [rsp+1960h+var_1930]
0x1808cd968  jmp     loc_1808CD6B1
```
