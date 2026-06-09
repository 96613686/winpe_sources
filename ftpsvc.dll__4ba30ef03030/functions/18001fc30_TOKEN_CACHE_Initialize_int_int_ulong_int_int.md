# TOKEN_CACHE::Initialize(int,int,ulong,int,int)

- ea: `0x18001fc30`
- end: `0x18001fec0`
- name: `?Initialize@TOKEN_CACHE@@QEAAJHHKHH@Z`
- size: `656`
- prototype: `__int64 __usercall@<rax>(TOKEN_CACHE *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800029fc`

## callees

- `0x180001210`
- `0x180001250`
- `0x18001fc30`
- `0x180020138`
- `0x180047050`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18001fd62`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001fd62`
- `KERNEL32!GetLastError` at `0x18001fcdd`
- `KERNEL32!GetLastError` at `0x18001fd70`
- `KERNEL32!GetLastError` at `0x18001fdae`
- `KERNEL32!GetLastError` at `0x18001fcdd`
- `KERNEL32!GetLastError` at `0x18001fd70`
- `KERNEL32!GetLastError` at `0x18001fdae`
- `KERNEL32!LoadLibraryW` at `0x18001fe4f`
- `KERNEL32!LoadLibraryW` at `0x18001fe4f`
- `ADVAPI32!CryptAcquireContextW` at `0x18001fcd3`
- `ADVAPI32!CryptAcquireContextW` at `0x18001fcd3`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001fd95`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001fd95`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001fc93`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001fc93`
- `iisutil!PuDbgPrint` at `0x18001fdf7`
- `iisutil!PuDbgPrint` at `0x18001fe3d`
- `iisutil!PuDbgPrint` at `0x18001fdf7`
- `iisutil!PuDbgPrint` at `0x18001fe3d`
- `iisutil!PuDbgPrintError` at `0x18001fe95`
- `iisutil!PuDbgPrintError` at `0x18001fe95`

## string_xrefs

- `0x18001fc89`: `TOKEN_CACHE_ENTRY`
- `0x18001fdcc`: `Error initializing sm_pachTokenCacheEntry. hr = 0x%x\n`
- `0x18001fde2`: `TOKEN_CACHE_ENTRY::Initialize`
- `0x18001fde9`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18001fe2f`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18001fe87`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18001fe16`: `Token cache entry init failed. hr = 0x%x\n`
- `0x18001fe22`: `TOKEN_CACHE::Initialize`
- `0x18001fe7a`: `TOKEN_CACHE::Initialize`
- `0x18001fe48`: `secur32.dll`
- `0x18001fe6a`: `Error loading secur32.dll.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TOKEN_CACHE::Initialize(void **this, __int64 a2, __int64 a3, int a4, int a5)
{
  ALLOC_CACHE_HANDLER *v7; // rax
  ALLOC_CACHE_HANDLER *v8; // rbx
  signed int LastError; // eax
  unsigned int v10; // ebx
  const char *v11; // rax
  __int64 v12; // r8
  signed int v13; // eax
  signed int v14; // eax
  HMODULE LibraryW; // rax
  _DWORD v17[4]; // [rsp+48h] [rbp-20h] BYREF

  v17[0] = 1;
  v17[1] = 100;
  v17[2] = 456;
  v7 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v7 )
    v8 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
           v7,
           "TOKEN_CACHE_ENTRY",
           (const struct ALLOC_CACHE_CONFIGURATION *)v17,
           1);
  else
    v8 = 0;
  TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry = v8;
  if ( v8 )
  {
    if ( *(_DWORD *)v8 )
    {
      if ( CryptAcquireContextW(&TOKEN_CACHE_ENTRY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
      {
        v10 = 0;
        goto LABEL_12;
      }
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v11 = "CryptAcquireContext() failed. hr = 0x%x\n";
        v12 = 414;
LABEL_24:
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
          v12,
          "TOKEN_CACHE_ENTRY::Initialize",
          v11,
          v10);
        goto LABEL_25;
      }
      goto LABEL_25;
    }
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(v8);
    operator delete(v8);
    TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry = 0;
  }
  v14 = GetLastError();
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v11 = "Error initializing sm_pachTokenCacheEntry. hr = 0x%x\n";
    v12 = 395;
    goto LABEL_24;
  }
LABEL_25:
  if ( (v10 & 0x80000000) != 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
        896,
        "TOKEN_CACHE::Initialize",
        "Token cache entry init failed. hr = 0x%x\n",
        v10);
LABEL_18:
    TOKEN_CACHE::Terminate((TOKEN_CACHE *)this);
    return v10;
  }
LABEL_12:
  if ( !a4 )
    a4 = 900;
  *((_DWORD *)this + 26) &= ~2u;
  *((_DWORD *)this + 26) |= a5 != 0 ? 2 : 0;
  if ( a5 && !CreateTimerQueueTimer(this + 12, 0, TOKEN_CACHE::ScavengerCallback, this, 1000 * a4, 1000 * a4, 0x10u) )
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_18;
  }
  LibraryW = LoadLibraryW(L"secur32.dll");
  this[18] = LibraryW;
  if ( !LibraryW )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
        1057,
        "TOKEN_CACHE::Initialize",
        v10,
        "Error loading secur32.dll.\n");
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x18001fc30  mov     [rsp+arg_8], rbx
0x18001fc35  mov     [rsp+arg_10], rsi
0x18001fc3a  push    rdi
0x18001fc3b  sub     rsp, 60h
0x18001fc3f  mov     rax, cs:__security_cookie
0x18001fc46  xor     rax, rsp
0x18001fc49  mov     [rsp+68h+var_10], rax
0x18001fc4e  mov     esi, r9d
0x18001fc51  mov     rdi, rcx
0x18001fc54  mov     ebx, 1
0x18001fc59  mov     [rsp+68h+var_20], ebx
0x18001fc5d  mov     [rsp+68h+var_1C], 64h ; 'd'
0x18001fc65  mov     [rsp+68h+var_18], 1C8h
0x18001fc6d  mov     ecx, 100h; Size
0x18001fc72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fc77  mov     [rsp+68h+var_28], rax
0x18001fc7c  test    rax, rax
0x18001fc7f  jz      short loc_18001FC9E
0x18001fc81  mov     r9d, ebx
0x18001fc84  lea     r8, [rsp+68h+var_20]
0x18001fc89  lea     rdx, aTokenCacheEntr_0; "TOKEN_CACHE_ENTRY"
0x18001fc90  mov     rcx, rax
0x18001fc93  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18001fc99  mov     rbx, rax
0x18001fc9c  jmp     short loc_18001FCA0
0x18001fc9e  xor     ebx, ebx
0x18001fca0  mov     cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, rbx; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001fca7  test    rbx, rbx
0x18001fcaa  jz      loc_18001FDAE
0x18001fcb0  cmp     dword ptr [rbx], 0
0x18001fcb3  jz      loc_18001FD92
0x18001fcb9  mov     [rsp+68h+dwFlags], 0F0000000h; dwFlags
0x18001fcc1  mov     r9d, 18h; dwProvType
0x18001fcc7  xor     r8d, r8d; szProvider
0x18001fcca  xor     edx, edx; szContainer
0x18001fccc  lea     rcx, ?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; phProv
0x18001fcd3  call    cs:__imp_CryptAcquireContextW
0x18001fcd9  test    eax, eax
0x18001fcdb  jnz     short loc_18001FD11
0x18001fcdd  call    cs:__imp_GetLastError
0x18001fce3  mov     ebx, eax
0x18001fce5  test    eax, eax
0x18001fce7  jle     short loc_18001FCF2
0x18001fce9  movzx   ebx, ax
0x18001fcec  or      ebx, 80070000h
0x18001fcf2  test    byte ptr cs:g_dwDebugFlags, 3
0x18001fcf9  jz      loc_18001FDFD
0x18001fcff  lea     rax, aCryptacquireco_0; "CryptAcquireContext() failed. hr = 0x%x"...
0x18001fd06  mov     r8d, 19Eh
0x18001fd0c  jmp     loc_18001FDD9
0x18001fd11  xor     ebx, ebx
0x18001fd13  mov     eax, 384h
0x18001fd18  test    esi, esi
0x18001fd1a  cmovz   esi, eax
0x18001fd1d  and     dword ptr [rdi+68h], 0FFFFFFFDh
0x18001fd21  mov     edx, [rsp+68h+arg_20]
0x18001fd28  mov     eax, edx
0x18001fd2a  neg     eax
0x18001fd2c  sbb     ecx, ecx
0x18001fd2e  and     ecx, 2
0x18001fd31  or      [rdi+68h], ecx
0x18001fd34  test    edx, edx
0x18001fd36  jz      loc_18001FE48
0x18001fd3c  imul    eax, esi, 3E8h
0x18001fd42  lea     rcx, [rdi+60h]; phNewTimer
0x18001fd46  mov     [rsp+68h+Flags], 10h; Flags
0x18001fd4e  mov     [rsp+68h+Period], eax; Period
0x18001fd52  mov     [rsp+68h+dwFlags], eax; DueTime
0x18001fd56  mov     r9, rdi; Parameter
0x18001fd59  lea     r8, ?ScavengerCallback@TOKEN_CACHE@@CAXPEAXE@Z; Callback
0x18001fd60  xor     edx, edx; TimerQueue
0x18001fd62  call    cs:__imp_CreateTimerQueueTimer
0x18001fd68  test    eax, eax
0x18001fd6a  jnz     loc_18001FE48
0x18001fd70  call    cs:__imp_GetLastError
0x18001fd76  mov     ebx, eax
0x18001fd78  test    eax, eax
0x18001fd7a  jle     short loc_18001FD85
0x18001fd7c  movzx   ebx, ax
0x18001fd7f  or      ebx, 80070000h
0x18001fd85  mov     rcx, rdi; this
0x18001fd88  call    ?Terminate@TOKEN_CACHE@@QEAAXXZ; TOKEN_CACHE::Terminate(void)
0x18001fd8d  jmp     loc_18001FE9B
0x18001fd92  mov     rcx, rbx
0x18001fd95  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18001fd9b  mov     rcx, rbx; Block
0x18001fd9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fda3  mov     cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001fdae  call    cs:__imp_GetLastError
0x18001fdb4  mov     ebx, eax
0x18001fdb6  test    eax, eax
0x18001fdb8  jle     short loc_18001FDC3
0x18001fdba  movzx   ebx, ax
0x18001fdbd  or      ebx, 80070000h
0x18001fdc3  test    byte ptr cs:g_dwDebugFlags, 3
0x18001fdca  jz      short loc_18001FDFD
0x18001fdcc  lea     rax, aErrorInitializ_1; "Error initializing sm_pachTokenCacheEnt"...
0x18001fdd3  mov     r8d, 18Bh
0x18001fdd9  mov     [rsp+68h+Period], ebx
0x18001fddd  mov     qword ptr [rsp+68h+dwFlags], rax
0x18001fde2  lea     r9, aTokenCacheEntr_2; "TOKEN_CACHE_ENTRY::Initialize"
0x18001fde9  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001fdf0  mov     rcx, cs:g_pDebug
0x18001fdf7  call    cs:__imp_PuDbgPrint
0x18001fdfd  test    ebx, ebx
0x18001fdff  jns     loc_18001FD13
0x18001fe05  test    byte ptr cs:g_dwDebugFlags, 3
0x18001fe0c  jz      loc_18001FD85
0x18001fe12  mov     [rsp+68h+Period], ebx
0x18001fe16  lea     rax, aTokenCacheEntr_1; "Token cache entry init failed. hr = 0x%"...
0x18001fe1d  mov     qword ptr [rsp+68h+dwFlags], rax
0x18001fe22  lea     r9, aTokenCacheInit; "TOKEN_CACHE::Initialize"
0x18001fe29  mov     r8d, 380h
0x18001fe2f  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001fe36  mov     rcx, cs:g_pDebug
0x18001fe3d  call    cs:__imp_PuDbgPrint
0x18001fe43  jmp     loc_18001FD85
0x18001fe48  lea     rcx, LibFileName; "secur32.dll"
0x18001fe4f  call    cs:__imp_LoadLibraryW
0x18001fe55  mov     [rdi+90h], rax
0x18001fe5c  test    rax, rax
0x18001fe5f  jnz     short loc_18001FE9F
0x18001fe61  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001fe68  jz      short loc_18001FE9B
0x18001fe6a  lea     rax, aErrorLoadingSe; "Error loading secur32.dll.\n"
0x18001fe71  mov     qword ptr [rsp+68h+Period], rax
0x18001fe76  mov     [rsp+68h+dwFlags], ebx
0x18001fe7a  lea     r9, aTokenCacheInit; "TOKEN_CACHE::Initialize"
0x18001fe81  mov     r8d, 421h
0x18001fe87  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001fe8e  mov     rcx, cs:g_pDebug
0x18001fe95  call    cs:__imp_PuDbgPrintError
0x18001fe9b  mov     eax, ebx
0x18001fe9d  jmp     short loc_18001FEA1
0x18001fe9f  xor     eax, eax
0x18001fea1  mov     rcx, [rsp+68h+var_10]
0x18001fea6  xor     rcx, rsp; StackCookie
0x18001fea9  call    __security_check_cookie
0x18001feae  lea     r11, [rsp+68h+var_8]
0x18001feb3  mov     rbx, [r11+18h]
0x18001feb7  mov     rsi, [r11+20h]
0x18001febb  mov     rsp, r11
0x18001febe  pop     rdi
0x18001febf  retn
```
