# GetFileActivePath(_GPOINFO *,int,ushort * *)

- ea: `0x180073a5c`
- end: `0x1800741e4`
- name: `?GetFileActivePath@@YAHPEAU_GPOINFO@@HPEAPEAG@Z`
- size: `1928`
- prototype: `__int64 __fastcall(struct _GPOINFO *, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f104`
- `0x18002e5a0`

## callees

- `0x18000a504`
- `0x18001ee6c`
- `0x180022c30`
- `0x180045690`
- `0x180048bb0`
- `0x180073a5c`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800740fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800741ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800741ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800740fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800741ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800741ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073acd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073c99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073acd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073c99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180073b52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180073b52`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180073d27`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180073d27`

## string_xrefs

- `0x180073b08`: `GetMachineCacheRoot: Failed to allocate memory.`
- `0x180073b36`: `GetMachineCacheRoot: Failed to allocate memory.`
- `0x180073b7f`: `GetMachineCacheRoot: Failed to get system directory after allocated memory.`
- `0x180073b9e`: `GetMachineCacheRoot: Failed to get system directory after allocated memory.`
- `0x180073bda`: `GetMachineCacheRoot: Failed to get system directory: %d`
- `0x180073c00`: `GetMachineCacheRoot: Failed to get system directory: %d`
- `0x180073cd7`: `GetUserCacheRoot: Failed to allocate memory.`
- `0x180073d05`: `GetUserCacheRoot: Failed to allocate memory.`
- `0x180073d61`: `GetMachineCacheRoot: GetBasicProfileFolderPath Failed to expand FOLDER_PROGRAM_DATA with error: %d.`
- `0x180073d92`: `GetMachineCacheRoot: GetBasicProfileFolderPath Failed to expand FOLDER_PROGRAM_DATA with error: %d.`
- `0x180073dda`: `GetUserCacheRoot: Failed to Concat <%s> and <Microsoft\GroupPolicy\Users>: %d`
- `0x180073e01`: `GetUserCacheRoot: Failed to Concat <%s> and <Microsoft\GroupPolicy\Users>: %d`
- `0x180073e55`: `GetUserCacheRoot: Failed to concatenate <%s> and userName <%s>: %d`
- `0x180073e88`: `GetUserCacheRoot: Failed to concatenate <%s> and userName <%s>: %d`
- `0x180073c47`: `GetCacheRoot: Failed to Machine cache root with error: %d.`
- `0x180073c78`: `GetCacheRoot: Failed to Machine cache root with error: %d.`
- `0x180073eca`: `GetCacheRoot: Failed to user cache root with error: %d.`
- `0x180073ee8`: `GetCacheRoot: Failed to user cache root with error: %d.`
- `0x180073f1f`: `GetFileActivePath: GetCacheRoot returned <%s>.`
- `0x180073f47`: `GetFileActivePath: GetCacheRoot returned <%s>.`
- `0x180073f78`: `GetFileActivePath: Failed to get root directory: %d`
- `0x180073fa9`: `GetFileActivePath: Failed to get root directory: %d`
- `0x180073ff1`: `GetFileActivePath: After appending DataStore <%s>.`
- `0x180074018`: `GetFileActivePath: After appending DataStore <%s>.`
- `0x18007404c`: `GetFileActivePath: Failed to concant <%s> and <DataStore> : %d`
- `0x180074078`: `GetFileActivePath: Failed to concant <%s> and <DataStore> : %d`
- `0x1800740b2`: `GetFileActivePath: Failed to get current active bit.`
- `0x1800740d5`: `GetFileActivePath: Failed to get current active bit.`
- `0x18007413d`: `GetFileActivePath: Failed to build szActivePath`
- `0x180074160`: `GetFileActivePath: Failed to build szActivePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetFileActivePath(const unsigned __int16 **a1, unsigned int a2, unsigned __int16 **a3)
{
  DWORD LastError; // r14d
  const unsigned __int16 *v6; // rsi
  LPWSTR v7; // rdi
  HLOCAL v8; // rax
  const unsigned __int16 *v9; // rbx
  DWORD v10; // r15d
  void (*v11)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v12; // rdx
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v14; // rdx
  HLOCAL v15; // rax
  const unsigned __int16 *v16; // rbx
  int BasicProfileFolderPath; // eax
  unsigned int v18; // eax
  void (*v19)(unsigned int, const unsigned __int16 *, ...); // rax
  unsigned int v20; // edi
  int v21; // r8d
  unsigned __int16 *v22; // rbx
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rax
  LPWSTR v24; // rax
  unsigned __int16 *v26; // [rsp+30h] [rbp-28h] BYREF
  LPWSTR v27; // [rsp+38h] [rbp-20h] BYREF
  LPWSTR v28; // [rsp+40h] [rbp-18h] BYREF
  void *v29[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 **v31; // [rsp+B0h] [rbp+58h]
  LPWSTR lpBuffer; // [rsp+B8h] [rbp+60h] BYREF

  v31 = a3;
  v30 = a2;
  v29[0] = 0;
  LastError = GetLastError();
  v6 = 0;
  v28 = 0;
  v26 = 0;
  if ( !a1 || !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v7 = 0;
  v27 = 0;
  lpBuffer = 0;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    v8 = LocalAlloc(0x40u, 0x208u);
    XPtrLF<unsigned short>::operator=((void **)&lpBuffer, v8);
    v9 = lpBuffer;
    if ( lpBuffer )
    {
      if ( GetSystemDirectoryW(lpBuffer, 0x104u) )
      {
        v10 = StringCatPath(v9, L"GroupPolicy", &lpBuffer);
        if ( v10 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"GetMachineCacheRoot: Failed to get system directory: %d", v10);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"GetMachineCacheRoot: Failed to get system directory: %d", v10);
            }
          }
        }
        else
        {
          v7 = lpBuffer;
          lpBuffer = 0;
          v27 = v7;
        }
      }
      else
      {
        v10 = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v11 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v12 = L"GetMachineCacheRoot: Failed to get system directory after allocated memory.";
            goto LABEL_8;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"GetMachineCacheRoot: Failed to get system directory after allocated memory.");
        }
      }
    }
    else
    {
      v10 = 14;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_28;
      v11 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v12 = L"GetMachineCacheRoot: Failed to allocate memory.";
LABEL_8:
        v11(2u, v12);
        goto LABEL_28;
      }
      if ( g_lpDebugMsgContextInstance != lpBuffer && (char *)g_lpDebugMsgContext != (char *)lpBuffer )
        RedirectDebugMsg(2u, L"GetMachineCacheRoot: Failed to allocate memory.");
    }
LABEL_28:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpBuffer);
    if ( v10 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_77;
      v13 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v14 = L"GetCacheRoot: Failed to Machine cache root with error: %d.";
LABEL_32:
        v13(2u, v14, v10);
        goto LABEL_77;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"GetCacheRoot: Failed to Machine cache root with error: %d.", v10);
      goto LABEL_77;
    }
LABEL_76:
    v6 = v7;
    v27 = 0;
    v28 = v7;
    goto LABEL_77;
  }
  v15 = LocalAlloc(0x40u, 0x208u);
  XPtrLF<unsigned short>::operator=((void **)&lpBuffer, v15);
  v16 = lpBuffer;
  if ( lpBuffer )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, lpBuffer, 260);
    v10 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath >= 0 )
    {
      v18 = StringCatPath(v16, L"Microsoft\\GroupPolicy\\Users", &lpBuffer);
      if ( v18 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"GetUserCacheRoot: Failed to Concat <%s> and <Microsoft\\GroupPolicy\\Users>: %d",
              lpBuffer,
              v18);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"GetUserCacheRoot: Failed to Concat <%s> and <Microsoft\\GroupPolicy\\Users>: %d",
              lpBuffer,
              v18);
          }
        }
      }
      else
      {
        v10 = StringCatPath(lpBuffer, a1[9], &lpBuffer);
        if ( !v10 )
        {
          v7 = lpBuffer;
          lpBuffer = 0;
          v27 = v7;
          goto LABEL_69;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"GetUserCacheRoot: Failed to concatenate <%s> and userName <%s>: %d",
              lpBuffer,
              a1[26],
              v10);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"GetUserCacheRoot: Failed to concatenate <%s> and userName <%s>: %d",
              lpBuffer,
              a1[26],
              v10);
          }
        }
      }
      v10 = 0;
      goto LABEL_69;
    }
    if ( (BasicProfileFolderPath & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)BasicProfileFolderPath;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          2u,
          L"GetMachineCacheRoot: GetBasicProfileFolderPath Failed to expand FOLDER_PROGRAM_DATA with error: %d.",
          v10);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"GetMachineCacheRoot: GetBasicProfileFolderPath Failed to expand FOLDER_PROGRAM_DATA with error: %d.",
          v10);
      }
    }
  }
  else
  {
    v10 = 14;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetUserCacheRoot: Failed to allocate memory.");
      }
      else if ( g_lpDebugMsgContextInstance != lpBuffer && (char *)g_lpDebugMsgContext != (char *)lpBuffer )
      {
        RedirectDebugMsg(2u, L"GetUserCacheRoot: Failed to allocate memory.");
      }
    }
  }
LABEL_69:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpBuffer);
  if ( !v10 )
    goto LABEL_76;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v13 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v14 = L"GetCacheRoot: Failed to user cache root with error: %d.";
      goto LABEL_32;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(2u, L"GetCacheRoot: Failed to user cache root with error: %d.", v10);
  }
LABEL_77:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v27);
  v19 = g_lpDebugMsg;
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_84;
  if ( g_lpDebugMsg )
  {
    g_lpDebugMsg(4u, L"GetFileActivePath: GetCacheRoot returned <%s>.", v6);
LABEL_83:
    v19 = g_lpDebugMsg;
    goto LABEL_84;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    RedirectDebugMsg(4u, L"GetFileActivePath: GetCacheRoot returned <%s>.", v6);
    goto LABEL_83;
  }
LABEL_84:
  if ( !v10 )
  {
    v20 = StringCatPath(v6, L"DataStore", &v26);
    v22 = v26;
    v23 = g_lpDebugMsg;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_98;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"GetFileActivePath: After appending DataStore <%s>.", v26);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_98:
        if ( v20 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( v23 )
            {
              v23(2u, L"GetFileActivePath: Failed to concant <%s> and <DataStore> : %d", v6, v20);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"GetFileActivePath: Failed to concant <%s> and <DataStore> : %d", v6, v20);
            }
          }
        }
        else
        {
          v30 = 0;
          if ( (unsigned int)GetCurrentActiveBit((struct _GPOINFO *)a1, &v30, v21) )
          {
            lpBuffer = 0;
            if ( (unsigned int)BuildActivePath(v22, v30, &lpBuffer) )
            {
              v24 = lpBuffer;
              lpBuffer = 0;
              *v31 = v24;
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpBuffer);
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v26);
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v28);
              SetLastError(LastError);
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(v29);
              return 1;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"GetFileActivePath: Failed to build szActivePath");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"GetFileActivePath: Failed to build szActivePath");
              }
            }
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpBuffer);
          }
          else if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"GetFileActivePath: Failed to get current active bit.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"GetFileActivePath: Failed to get current active bit.");
            }
          }
        }
        goto LABEL_112;
      }
      RedirectDebugMsg(4u, L"GetFileActivePath: After appending DataStore <%s>.", v26);
    }
    v23 = g_lpDebugMsg;
    goto LABEL_98;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( v19 )
    {
      v19(2u, L"GetFileActivePath: Failed to get root directory: %d", v10);
    }
    else if ( g_lpDebugMsgContextInstance )
    {
      if ( g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"GetFileActivePath: Failed to get root directory: %d", v10);
    }
  }
LABEL_112:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v26);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v28);
  SetLastError(LastError);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(v29);
  return 0;
}

```

## disassembly

```asm
0x180073a5c  mov     [rsp-40h+arg_10], r8
0x180073a61  mov     [rsp-40h+arg_8], edx
0x180073a65  push    rbp
0x180073a66  push    rbx
0x180073a67  push    rsi
0x180073a68  push    rdi
0x180073a69  push    r12
0x180073a6b  push    r13
0x180073a6d  push    r14
0x180073a6f  push    r15
0x180073a71  mov     rbp, rsp
0x180073a74  sub     rsp, 58h
0x180073a78  mov     rbx, r8
0x180073a7b  mov     r13, rcx
0x180073a7e  xor     r15d, r15d
0x180073a81  mov     [rbp+var_10], r15
0x180073a85  call    cs:__imp_GetLastError
0x180073a8b  mov     r14d, eax
0x180073a8e  mov     [rbp+arg_0], eax
0x180073a91  mov     esi, r15d
0x180073a94  mov     [rbp+var_18], r15
0x180073a98  mov     [rbp+var_28], r15
0x180073a9c  test    r13, r13
0x180073a9f  jz      loc_1800741C5
0x180073aa5  test    rbx, rbx
0x180073aa8  jz      loc_1800741C5
0x180073aae  mov     edi, r15d
0x180073ab1  mov     [rbp+var_20], r15
0x180073ab5  mov     [rbp+lpBuffer], r15
0x180073ab9  test    byte ptr [r13+0], 1
0x180073abe  jz      loc_180073C8F
0x180073ac4  mov     edx, 208h; uBytes
0x180073ac9  lea     ecx, [r15+40h]; uFlags
0x180073acd  call    cs:__imp_LocalAlloc
0x180073ad3  mov     rdx, rax
0x180073ad6  lea     rcx, [rbp+lpBuffer]
0x180073ada  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180073adf  lea     r12d, [r15+2]
0x180073ae3  mov     rbx, [rbp+lpBuffer]
0x180073ae7  test    rbx, rbx
0x180073aea  jnz     short loc_180073B4A
0x180073aec  lea     r15d, [rdi+0Eh]
0x180073af0  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073af6  jz      loc_180073C1D
0x180073afc  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073b03  test    rax, rax
0x180073b06  jz      short loc_180073B1C
0x180073b08  lea     rdx, aGetmachinecach_0; "GetMachineCacheRoot: Failed to allocate"...
0x180073b0f  mov     ecx, r12d
0x180073b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b17  jmp     loc_180073C1D
0x180073b1c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073b23  jz      loc_180073C1D
0x180073b29  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073b30  jz      loc_180073C1D
0x180073b36  lea     rdx, aGetmachinecach_0; "GetMachineCacheRoot: Failed to allocate"...
0x180073b3d  mov     ecx, r12d; unsigned int
0x180073b40  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073b45  jmp     loc_180073C1D
0x180073b4a  mov     edx, 104h; uSize
0x180073b4f  mov     rcx, rbx; lpBuffer
0x180073b52  call    cs:__imp_GetSystemDirectoryW
0x180073b58  test    eax, eax
0x180073b5a  jnz     short loc_180073BA7
0x180073b5c  call    cs:__imp_GetLastError
0x180073b62  mov     r15d, eax
0x180073b65  xor     ebx, ebx
0x180073b67  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073b6d  jz      loc_180073C1D
0x180073b73  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073b7a  test    rax, rax
0x180073b7d  jz      short loc_180073B88
0x180073b7f  lea     rdx, aGetmachinecach; "GetMachineCacheRoot: Failed to get syst"...
0x180073b86  jmp     short loc_180073B0F
0x180073b88  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073b8f  jz      loc_180073C1D
0x180073b95  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073b9c  jz      short loc_180073C1D
0x180073b9e  lea     rdx, aGetmachinecach; "GetMachineCacheRoot: Failed to get syst"...
0x180073ba5  jmp     short loc_180073B3D
0x180073ba7  lea     r8, [rbp+lpBuffer]; unsigned __int16 **
0x180073bab  lea     rdx, aGrouppolicy; "GroupPolicy"
0x180073bb2  mov     rcx, rbx; unsigned __int16 *
0x180073bb5  call    ?StringCatPath@@YAKPEBG0PEAPEAG@Z; StringCatPath(ushort const *,ushort const *,ushort * *)
0x180073bba  mov     r15d, eax
0x180073bbd  xor     ebx, ebx
0x180073bbf  test    eax, eax
0x180073bc1  jz      short loc_180073C11
0x180073bc3  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073bc9  jz      short loc_180073C1D
0x180073bcb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073bd2  test    rax, rax
0x180073bd5  jz      short loc_180073BEB
0x180073bd7  mov     r8d, r15d
0x180073bda  lea     rdx, aGetmachinecach_2; "GetMachineCacheRoot: Failed to get syst"...
0x180073be1  mov     ecx, r12d
0x180073be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073be9  jmp     short loc_180073C1D
0x180073beb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073bf2  jz      short loc_180073C1D
0x180073bf4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073bfb  jz      short loc_180073C1D
0x180073bfd  mov     r8d, r15d
0x180073c00  lea     rdx, aGetmachinecach_2; "GetMachineCacheRoot: Failed to get syst"...
0x180073c07  mov     ecx, r12d; unsigned int
0x180073c0a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073c0f  jmp     short loc_180073C1D
0x180073c11  mov     rdi, [rbp+lpBuffer]
0x180073c15  mov     [rbp+lpBuffer], rbx
0x180073c19  mov     [rbp+var_20], rdi
0x180073c1d  lea     rcx, [rbp+lpBuffer]
0x180073c21  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180073c26  test    r15d, r15d
0x180073c29  jz      loc_180073EF4
0x180073c2f  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073c35  jz      loc_180073EFF
0x180073c3b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073c42  test    rax, rax
0x180073c45  jz      short loc_180073C5E
0x180073c47  lea     rdx, aGetcacherootFa; "GetCacheRoot: Failed to Machine cache r"...
0x180073c4e  mov     r8d, r15d
0x180073c51  mov     ecx, r12d
0x180073c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073c59  jmp     loc_180073EFF
0x180073c5e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073c65  jz      loc_180073EFF
0x180073c6b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073c72  jz      loc_180073EFF
0x180073c78  lea     rdx, aGetcacherootFa; "GetCacheRoot: Failed to Machine cache r"...
0x180073c7f  mov     r8d, r15d
0x180073c82  mov     ecx, r12d; unsigned int
0x180073c85  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073c8a  jmp     loc_180073EFF
0x180073c8f  mov     edx, 208h; uBytes
0x180073c94  mov     ecx, 40h ; '@'; uFlags
0x180073c99  call    cs:__imp_LocalAlloc
0x180073c9f  mov     rdx, rax
0x180073ca2  lea     rcx, [rbp+lpBuffer]
0x180073ca6  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180073cab  mov     r12d, 2
0x180073cb1  mov     rbx, [rbp+lpBuffer]
0x180073cb5  test    rbx, rbx
0x180073cb8  jnz     short loc_180073D19
0x180073cba  lea     r15d, [r12+0Ch]
0x180073cbf  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073cc5  jz      loc_180073EA8
0x180073ccb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073cd2  test    rax, rax
0x180073cd5  jz      short loc_180073CEB
0x180073cd7  lea     rdx, aGetusercachero_0; "GetUserCacheRoot: Failed to allocate me"...
0x180073cde  mov     ecx, r12d
0x180073ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ce6  jmp     loc_180073EA8
0x180073ceb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073cf2  jz      loc_180073EA8
0x180073cf8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073cff  jz      loc_180073EA8
0x180073d05  lea     rdx, aGetusercachero_0; "GetUserCacheRoot: Failed to allocate me"...
0x180073d0c  mov     ecx, r12d; unsigned int
0x180073d0f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073d14  jmp     loc_180073EA8
0x180073d19  mov     r9d, 104h
0x180073d1f  mov     r8, rbx
0x180073d22  xor     edx, edx
0x180073d24  lea     ecx, [rdx+4]
0x180073d27  call    cs:__imp_GetBasicProfileFolderPath
0x180073d2d  mov     r15d, eax
0x180073d30  test    eax, eax
0x180073d32  jns     short loc_180073DA6
0x180073d34  and     eax, 1FFF0000h
0x180073d39  cmp     eax, 70000h
0x180073d3e  jnz     short loc_180073D44
0x180073d40  movzx   r15d, r15w
0x180073d44  xor     ebx, ebx
0x180073d46  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073d4c  jz      loc_180073EA8
0x180073d52  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073d59  test    rax, rax
0x180073d5c  jz      short loc_180073D75
0x180073d5e  mov     r8d, r15d
0x180073d61  lea     rdx, aGetmachinecach_1; "GetMachineCacheRoot: GetBasicProfileFol"...
0x180073d68  mov     ecx, r12d
0x180073d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d70  jmp     loc_180073EA8
0x180073d75  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073d7c  jz      loc_180073EA8
0x180073d82  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073d89  jz      loc_180073EA8
0x180073d8f  mov     r8d, r15d
0x180073d92  lea     rdx, aGetmachinecach_1; "GetMachineCacheRoot: GetBasicProfileFol"...
0x180073d99  mov     ecx, r12d; unsigned int
0x180073d9c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073da1  jmp     loc_180073EA8
0x180073da6  lea     r8, [rbp+lpBuffer]; unsigned __int16 **
0x180073daa  lea     rdx, aMicrosoftGroup_0; "Microsoft\\GroupPolicy\\Users"
0x180073db1  mov     rcx, rbx; unsigned __int16 *
0x180073db4  call    ?StringCatPath@@YAKPEBG0PEAPEAG@Z; StringCatPath(ushort const *,ushort const *,ushort * *)
0x180073db9  mov     r9d, eax
0x180073dbc  xor     ebx, ebx
0x180073dbe  test    eax, eax
0x180073dc0  jz      short loc_180073E19
0x180073dc2  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073dc8  jz      short loc_180073E11
0x180073dca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073dd1  test    rax, rax
0x180073dd4  jz      short loc_180073DEB
0x180073dd6  mov     r8, [rbp+lpBuffer]
0x180073dda  lea     rdx, aGetusercachero; "GetUserCacheRoot: Failed to Concat <%s>"...
0x180073de1  mov     ecx, r12d
0x180073de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073de9  jmp     short loc_180073E11
0x180073deb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073df2  jz      short loc_180073E11
0x180073df4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073dfb  jz      short loc_180073E11
0x180073dfd  mov     r8, [rbp+lpBuffer]
0x180073e01  lea     rdx, aGetusercachero; "GetUserCacheRoot: Failed to Concat <%s>"...
0x180073e08  mov     ecx, r12d; unsigned int
0x180073e0b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073e10  nop
0x180073e11  mov     r15d, ebx
0x180073e14  jmp     loc_180073EA8
0x180073e19  lea     r8, [rbp+lpBuffer]; unsigned __int16 **
0x180073e1d  mov     rdx, [r13+48h]; unsigned __int16 *
0x180073e21  mov     rcx, [rbp+lpBuffer]; unsigned __int16 *
0x180073e25  call    ?StringCatPath@@YAKPEBG0PEAPEAG@Z; StringCatPath(ushort const *,ushort const *,ushort * *)
0x180073e2a  mov     r15d, eax
0x180073e2d  test    eax, eax
0x180073e2f  jz      short loc_180073E9C
0x180073e31  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073e37  jz      short loc_180073E11
0x180073e39  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073e40  test    rax, rax
0x180073e43  jz      short loc_180073E66
0x180073e45  mov     [rsp+58h+var_38], r15d
0x180073e4a  mov     r9, [r13+0D0h]
0x180073e51  mov     r8, [rbp+lpBuffer]
0x180073e55  lea     rdx, aGetusercachero_1; "GetUserCacheRoot: Failed to concatenate"...
0x180073e5c  mov     ecx, r12d
0x180073e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e64  jmp     short loc_180073E11
0x180073e66  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073e6d  jz      short loc_180073E11
0x180073e6f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073e76  jz      short loc_180073E11
0x180073e78  mov     [rsp+58h+var_38], r15d
0x180073e7d  mov     r9, [r13+0D0h]
0x180073e84  mov     r8, [rbp+lpBuffer]
0x180073e88  lea     rdx, aGetusercachero_1; "GetUserCacheRoot: Failed to concatenate"...
0x180073e8f  mov     ecx, r12d; unsigned int
0x180073e92  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073e97  jmp     loc_180073E11
0x180073e9c  mov     rdi, [rbp+lpBuffer]
0x180073ea0  mov     [rbp+lpBuffer], rbx
0x180073ea4  mov     [rbp+var_20], rdi
0x180073ea8  lea     rcx, [rbp+lpBuffer]
0x180073eac  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180073eb1  test    r15d, r15d
0x180073eb4  jz      short loc_180073EF4
0x180073eb6  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073ebc  jz      short loc_180073EFF
0x180073ebe  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073ec5  test    rax, rax
0x180073ec8  jz      short loc_180073ED6
0x180073eca  lea     rdx, aGetcacherootFa_0; "GetCacheRoot: Failed to user cache root"...
0x180073ed1  jmp     loc_180073C4E
0x180073ed6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073edd  jz      short loc_180073EFF
0x180073edf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073ee6  jz      short loc_180073EFF
0x180073ee8  lea     rdx, aGetcacherootFa_0; "GetCacheRoot: Failed to user cache root"...
0x180073eef  jmp     loc_180073C7F
0x180073ef4  mov     rsi, rdi
0x180073ef7  mov     [rbp+var_20], rbx
0x180073efb  mov     [rbp+var_18], rdi
0x180073eff  lea     rcx, [rbp+var_20]
0x180073f03  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180073f08  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073f0f  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073f15  jz      short loc_180073F5F
0x180073f17  test    rax, rax
0x180073f1a  jz      short loc_180073F32
0x180073f1c  mov     r8, rsi
0x180073f1f  lea     rdx, aGetfileactivep; "GetFileActivePath: GetCacheRoot returne"...
0x180073f26  mov     ecx, 4
0x180073f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f30  jmp     short loc_180073F58
0x180073f32  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180073f39  jz      short loc_180073F5F
0x180073f3b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180073f42  jz      short loc_180073F5F
0x180073f44  mov     r8, rsi
0x180073f47  lea     rdx, aGetfileactivep; "GetFileActivePath: GetCacheRoot returne"...
0x180073f4e  mov     ecx, 4; unsigned int
0x180073f53  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180073f58  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180073f5f  test    r15d, r15d
0x180073f62  jz      short loc_180073FBD
0x180073f64  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180073f6a  jz      loc_1800740E5
  ... truncated ...
```
