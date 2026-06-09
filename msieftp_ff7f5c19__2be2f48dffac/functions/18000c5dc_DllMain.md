# DllMain

- ea: `0x18000c5dc`
- end: `0x18000c8e7`
- name: `DllMain`
- size: `779`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800020b4`

## callees

- `0x180001950`
- `0x180001b2c`
- `0x180002610`
- `0x18000c0e4`
- `0x18000c5dc`
- `0x180019108`
- `0x18001965c`
- `0x1800266cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c617`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c617`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c60e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000c60e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c8a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c8a8`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000c873`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000c873`
- `KERNEL32!ReleaseActCtx` at `0x18000c8be`
- `KERNEL32!ReleaseActCtx` at `0x18000c8be`
- `USER32!RegisterClipboardFormatW` at `0x18000c6a3`
- `USER32!RegisterClipboardFormatW` at `0x18000c6b0`
- `USER32!RegisterClipboardFormatW` at `0x18000c6c4`
- `USER32!RegisterClipboardFormatW` at `0x18000c6d8`
- `USER32!RegisterClipboardFormatW` at `0x18000c6ec`
- `USER32!RegisterClipboardFormatW` at `0x18000c700`
- `USER32!RegisterClipboardFormatW` at `0x18000c714`
- `USER32!RegisterClipboardFormatW` at `0x18000c728`
- `USER32!RegisterClipboardFormatW` at `0x18000c73c`
- `USER32!RegisterClipboardFormatW` at `0x18000c750`
- `USER32!RegisterClipboardFormatW` at `0x18000c764`
- `USER32!RegisterClipboardFormatW` at `0x18000c778`
- `USER32!RegisterClipboardFormatW` at `0x18000c78c`
- `USER32!RegisterClipboardFormatW` at `0x18000c7a0`
- `USER32!RegisterClipboardFormatW` at `0x18000c7b4`
- `USER32!RegisterClipboardFormatW` at `0x18000c6a3`
- `USER32!RegisterClipboardFormatW` at `0x18000c6b0`
- `USER32!RegisterClipboardFormatW` at `0x18000c6c4`
- `USER32!RegisterClipboardFormatW` at `0x18000c6d8`
- `USER32!RegisterClipboardFormatW` at `0x18000c6ec`
- `USER32!RegisterClipboardFormatW` at `0x18000c700`
- `USER32!RegisterClipboardFormatW` at `0x18000c714`
- `USER32!RegisterClipboardFormatW` at `0x18000c728`
- `USER32!RegisterClipboardFormatW` at `0x18000c73c`
- `USER32!RegisterClipboardFormatW` at `0x18000c750`
- `USER32!RegisterClipboardFormatW` at `0x18000c764`
- `USER32!RegisterClipboardFormatW` at `0x18000c778`
- `USER32!RegisterClipboardFormatW` at `0x18000c78c`
- `USER32!RegisterClipboardFormatW` at `0x18000c7a0`
- `USER32!RegisterClipboardFormatW` at `0x18000c7b4`

## string_xrefs

- `0x18000c65c`: `Loading msieftp.dll`
- `0x18000c6b6`: `TargetCLSID`
- `0x18000c822`: `Unloading msieftp.dll`
- `0x18000c6f2`: `FileGroupDescriptor`
- `0x18000c6de`: `FileGroupDescriptorW`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // r9
  int v5; // r8d
  __int64 v6; // r9
  int v7; // ecx
  REGHANDLE v9; // rcx
  CCookieList *v10; // rbx
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hinst = hinstDLL;
      SHFusionInitializeFromModuleID(hinstDLL);
      InitializeCriticalSection(&g_csDll);
      DisableThreadLibraryCalls(hinstDLL);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180032000);
      if ( (unsigned int)dword_180032000 > 5
        && (qword_180032010 & 0x400000000000LL) != 0
        && (qword_180032018 & 0x400000000000LL) == qword_180032018 )
      {
        v11[0] = "Loading msieftp.dll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          0,
          (unsigned int)&dword_18002CC94,
          v5,
          v6,
          (__int64)v11);
      }
      g_hthWorker = 0;
      RegisterClipboardFormatW(L"Shell Object Offsets");
      g_formatPasteSucceeded.cfFormat = RegisterClipboardFormatW(L"Paste Succeeded");
      g_cfTargetCLSID = RegisterClipboardFormatW(L"TargetCLSID");
      g_dropTypes.cfFormat = RegisterClipboardFormatW(L"FileContents");
      word_180032360 = RegisterClipboardFormatW(L"FileGroupDescriptorW");
      word_180032380 = RegisterClipboardFormatW(L"FileGroupDescriptor");
      word_1800323A0 = RegisterClipboardFormatW(L"Shell IDList Array");
      word_1800324A0 = RegisterClipboardFormatW(L"FileNameMap");
      word_1800324C0 = RegisterClipboardFormatW(L"FileNameMapW");
      word_1800323E0 = RegisterClipboardFormatW(L"Preferred DropEffect");
      word_180032400 = RegisterClipboardFormatW(L"Performed DropEffect");
      word_180032420 = RegisterClipboardFormatW(L"FtpPrivateData");
      word_1800323C0 = RegisterClipboardFormatW(L"UniformResourceLocator");
      word_180032440 = RegisterClipboardFormatW(L"OleClipboardPersistOnFlush");
      word_180032460 = RegisterClipboardFormatW(L"Paste Succeeded");
      if ( !g_FtpSiteCache )
        return CFtpList_Create(v7, 0, 0xAu, &g_FtpSiteCache) >= 0;
    }
  }
  else
  {
    if ( (unsigned int)dword_180032000 > 5
      && (qword_180032010 & 0x400000000000LL) != 0
      && (qword_180032018 & 0x400000000000LL) == qword_180032018 )
    {
      v11[0] = "Unloading msieftp.dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        0,
        (unsigned int)byte_18002CC43,
        (_DWORD)lpvReserved,
        v3,
        (__int64)v11);
    }
    v9 = RegHandle;
    dword_180032000 = 0;
    RegHandle = 0;
    EventUnregister(v9);
    v10 = (CCookieList *)_InterlockedExchange64((volatile __int64 *)&g_pCookieList, 0);
    if ( v10 )
    {
      CCookieList::~CCookieList(v10);
      operator delete(v10, 8u);
    }
    PurgeDelayedActions();
    DeleteCriticalSection(&g_csDll);
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( hModule )
      hModule = (HMODULE)-1LL;
  }
  return 1;
}

```

## disassembly

```asm
0x18000c5dc  push    rbx
0x18000c5de  sub     rsp, 40h
0x18000c5e2  mov     rbx, rcx
0x18000c5e5  test    edx, edx
0x18000c5e7  jz      loc_18000C7EF
0x18000c5ed  cmp     edx, 1
0x18000c5f0  jnz     loc_18000C8DC
0x18000c5f6  mov     edx, 7Bh ; '{'
0x18000c5fb  mov     cs:?g_hinst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hinst
0x18000c602  call    SHFusionInitializeFromModuleID
0x18000c607  lea     rcx, g_csDll; lpCriticalSection
0x18000c60e  call    cs:__imp_InitializeCriticalSection
0x18000c614  mov     rcx, rbx; hLibModule
0x18000c617  call    cs:__imp_DisableThreadLibraryCalls
0x18000c61d  lea     rcx, dword_180032000; CallbackContext
0x18000c624  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000c629  mov     eax, cs:dword_180032000
0x18000c62f  cmp     eax, 5
0x18000c632  jbe     short loc_18000C691
0x18000c634  mov     rdx, cs:qword_180032018
0x18000c63b  mov     rcx, 400000000000h
0x18000c645  mov     rax, cs:qword_180032010
0x18000c64c  test    rcx, rax
0x18000c64f  jz      short loc_18000C691
0x18000c651  mov     rax, rdx
0x18000c654  and     rax, rcx
0x18000c657  cmp     rax, rdx
0x18000c65a  jnz     short loc_18000C691
0x18000c65c  lea     rax, aLoadingMsieftp; "Loading msieftp.dll"
0x18000c663  mov     [rsp+48h+arg_18], 2000000h
0x18000c66c  mov     [rsp+48h+var_18], rax
0x18000c671  lea     rdx, dword_18002CC94
0x18000c678  lea     rax, [rsp+48h+arg_18]
0x18000c67d  mov     [rsp+48h+var_20], rax
0x18000c682  lea     rax, [rsp+48h+var_18]
0x18000c687  mov     [rsp+48h+var_28], rax
0x18000c68c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c691  lea     rcx, szFormat; "Shell Object Offsets"
0x18000c698  mov     cs:?g_hthWorker@@3PEAXEA, 0; void * g_hthWorker
0x18000c6a3  call    cs:__imp_RegisterClipboardFormatW
0x18000c6a9  lea     rcx, aPasteSucceeded; "Paste Succeeded"
0x18000c6b0  call    cs:__imp_RegisterClipboardFormatW
0x18000c6b6  lea     rcx, aTargetclsid; "TargetCLSID"
0x18000c6bd  mov     cs:?g_formatPasteSucceeded@@3UtagFORMATETC@@A, ax; tagFORMATETC g_formatPasteSucceeded
0x18000c6c4  call    cs:__imp_RegisterClipboardFormatW
0x18000c6ca  lea     rcx, aFilecontents; "FileContents"
0x18000c6d1  mov     cs:?g_cfTargetCLSID@@3GA, ax; ushort g_cfTargetCLSID
0x18000c6d8  call    cs:__imp_RegisterClipboardFormatW
0x18000c6de  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x18000c6e5  mov     cs:?g_dropTypes@@3PAUtagFORMATETC@@A.cfFormat, ax; tagFORMATETC near * g_dropTypes ...
0x18000c6ec  call    cs:__imp_RegisterClipboardFormatW
0x18000c6f2  lea     rcx, aFilegroupdescr_0; "FileGroupDescriptor"
0x18000c6f9  mov     cs:word_180032360, ax
0x18000c700  call    cs:__imp_RegisterClipboardFormatW
0x18000c706  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x18000c70d  mov     cs:word_180032380, ax
0x18000c714  call    cs:__imp_RegisterClipboardFormatW
0x18000c71a  lea     rcx, aFilenamemap; "FileNameMap"
0x18000c721  mov     cs:word_1800323A0, ax
0x18000c728  call    cs:__imp_RegisterClipboardFormatW
0x18000c72e  lea     rcx, aFilenamemapw; "FileNameMapW"
0x18000c735  mov     cs:word_1800324A0, ax
0x18000c73c  call    cs:__imp_RegisterClipboardFormatW
0x18000c742  lea     rcx, aPreferredDrope; "Preferred DropEffect"
0x18000c749  mov     cs:word_1800324C0, ax
0x18000c750  call    cs:__imp_RegisterClipboardFormatW
0x18000c756  lea     rcx, aPerformedDrope; "Performed DropEffect"
0x18000c75d  mov     cs:word_1800323E0, ax
0x18000c764  call    cs:__imp_RegisterClipboardFormatW
0x18000c76a  lea     rcx, aFtpprivatedata; "FtpPrivateData"
0x18000c771  mov     cs:word_180032400, ax
0x18000c778  call    cs:__imp_RegisterClipboardFormatW
0x18000c77e  lea     rcx, aUniformresourc; "UniformResourceLocator"
0x18000c785  mov     cs:word_180032420, ax
0x18000c78c  call    cs:__imp_RegisterClipboardFormatW
0x18000c792  lea     rcx, aOleclipboardpe; "OleClipboardPersistOnFlush"
0x18000c799  mov     cs:word_1800323C0, ax
0x18000c7a0  call    cs:__imp_RegisterClipboardFormatW
0x18000c7a6  lea     rcx, aPasteSucceeded; "Paste Succeeded"
0x18000c7ad  mov     cs:word_180032440, ax
0x18000c7b4  call    cs:__imp_RegisterClipboardFormatW
0x18000c7ba  cmp     cs:?g_FtpSiteCache@@3PEAVCFtpList@@EA, 0; CFtpList * g_FtpSiteCache
0x18000c7c2  mov     cs:word_180032460, ax
0x18000c7c9  jnz     loc_18000C8DC
0x18000c7cf  xor     edx, edx; int (*)(void *, void *)
0x18000c7d1  lea     r9, ?g_FtpSiteCache@@3PEAVCFtpList@@EA; struct CFtpList **
0x18000c7d8  lea     r8d, [rdx+0Ah]; unsigned int
0x18000c7dc  call    ?CFtpList_Create@@YAJHP6AHPEAX0@ZIPEAPEAVCFtpList@@@Z; CFtpList_Create(int,int (*)(void *,void *),uint,CFtpList * *)
0x18000c7e1  xor     ecx, ecx
0x18000c7e3  test    eax, eax
0x18000c7e5  setns   cl
0x18000c7e8  mov     eax, ecx
0x18000c7ea  jmp     loc_18000C8E1
0x18000c7ef  mov     eax, cs:dword_180032000
0x18000c7f5  cmp     eax, 5
0x18000c7f8  jbe     short loc_18000C857
0x18000c7fa  mov     rdx, cs:qword_180032018
0x18000c801  mov     rcx, 400000000000h
0x18000c80b  mov     rax, cs:qword_180032010
0x18000c812  test    rcx, rax
0x18000c815  jz      short loc_18000C857
0x18000c817  mov     rax, rdx
0x18000c81a  and     rax, rcx
0x18000c81d  cmp     rax, rdx
0x18000c820  jnz     short loc_18000C857
0x18000c822  lea     rax, aUnloadingMsief; "Unloading msieftp.dll"
0x18000c829  mov     [rsp+48h+arg_18], 2000000h
0x18000c832  mov     [rsp+48h+var_18], rax
0x18000c837  lea     rdx, byte_18002CC43
0x18000c83e  lea     rax, [rsp+48h+arg_18]
0x18000c843  mov     [rsp+48h+var_20], rax
0x18000c848  lea     rax, [rsp+48h+var_18]
0x18000c84d  mov     [rsp+48h+var_28], rax
0x18000c852  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c857  mov     rcx, cs:RegHandle; RegHandle
0x18000c85e  mov     cs:dword_180032000, 0
0x18000c868  mov     cs:RegHandle, 0
0x18000c873  call    cs:__imp_EventUnregister
0x18000c879  xor     ebx, ebx
0x18000c87b  xchg    rbx, cs:?g_pCookieList@@3PEAVCCookieList@@EA; CCookieList * g_pCookieList
0x18000c882  test    rbx, rbx
0x18000c885  jz      short loc_18000C89C
0x18000c887  mov     rcx, rbx; this
0x18000c88a  call    ??1CCookieList@@QEAA@XZ; CCookieList::~CCookieList(void)
0x18000c88f  mov     edx, 8; unsigned __int64
0x18000c894  mov     rcx, rbx; void *
0x18000c897  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c89c  call    ?PurgeDelayedActions@@YAJXZ; PurgeDelayedActions(void)
0x18000c8a1  lea     rcx, g_csDll; lpCriticalSection
0x18000c8a8  call    cs:__imp_DeleteCriticalSection
0x18000c8ae  mov     rcx, cs:g_hActCtx; hActCtx
0x18000c8b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c8b9  cmp     rcx, rbx
0x18000c8bc  jz      short loc_18000C8CB
0x18000c8be  call    cs:__imp_ReleaseActCtx
0x18000c8c4  mov     cs:g_hActCtx, rbx
0x18000c8cb  cmp     cs:hModule, 0
0x18000c8d3  jz      short loc_18000C8DC
0x18000c8d5  mov     cs:hModule, rbx
0x18000c8dc  mov     eax, 1
0x18000c8e1  add     rsp, 40h
0x18000c8e5  pop     rbx
0x18000c8e6  retn
```
