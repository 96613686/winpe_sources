# CREDENTIALS_CACHE::Initialize(void)

- ea: `0x18001e53c`
- end: `0x18001e672`
- name: `?Initialize@CREDENTIALS_CACHE@@QEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(CREDENTIALS_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800029fc`

## callees

- `0x18001e53c`
- `0x18001e678`
- `0x18001ea20`
- `0x18001ec28`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18001e5fc`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001e5fc`
- `KERNEL32!GetLastError` at `0x18001e606`
- `KERNEL32!GetLastError` at `0x18001e606`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x18001e549`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x18001e549`
- `iisutil!PuDbgPrintError` at `0x18001e5a0`
- `iisutil!PuDbgPrintError` at `0x18001e64f`
- `iisutil!PuDbgPrintError` at `0x18001e5a0`
- `iisutil!PuDbgPrintError` at `0x18001e64f`

## string_xrefs

- `0x18001e595`: `inetsrv\iis\iisrearc\ftp\server\core\credentials_cache.cxx`
- `0x18001e648`: `inetsrv\iis\iisrearc\ftp\server\core\credentials_cache.cxx`
- `0x18001e575`: `Credentials cache entry init failed\n`
- `0x18001e589`: `CREDENTIALS_CACHE::Initialize`
- `0x18001e637`: `CREDENTIALS_CACHE::Initialize`
- `0x18001e5c6`: `Failed to read credentials cache configuration\n`
- `0x18001e62b`: `CreateTimerQueueTimer() failed\n`

## pseudocode

```c
__int64 __fastcall CREDENTIALS_CACHE::Initialize(void **this)
{
  signed int CredentialsCacheConfig; // ebx
  signed int LastError; // eax

  if ( !CLKRHashTable::IsValid((CLKRHashTable *)this) )
  {
    CredentialsCacheConfig = -2147024882;
LABEL_16:
    CREDENTIALS_CACHE::Terminate((CREDENTIALS_CACHE *)this);
    return (unsigned int)CredentialsCacheConfig;
  }
  CredentialsCacheConfig = CREDENTIALS_CACHE_ENTRY::Initialize();
  if ( CredentialsCacheConfig < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
        432,
        "CREDENTIALS_CACHE::Initialize",
        CredentialsCacheConfig,
        "Credentials cache entry init failed\n");
    goto LABEL_16;
  }
  CredentialsCacheConfig = CREDENTIALS_CACHE::ReadCredentialsCacheConfig((CREDENTIALS_CACHE *)this);
  if ( CredentialsCacheConfig < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
        442,
        "CREDENTIALS_CACHE::Initialize",
        CredentialsCacheConfig,
        "Failed to read credentials cache configuration\n");
    goto LABEL_16;
  }
  if ( CreateTimerQueueTimer(
         this + 10,
         0,
         (WAITORTIMERCALLBACK)CREDENTIALS_CACHE::CredentialsCacheScavengerCallback,
         this,
         1000 * *((_DWORD *)this + 18),
         1000 * *((_DWORD *)this + 18),
         0x10u) )
  {
    return 0;
  }
  LastError = GetLastError();
  CredentialsCacheConfig = LastError;
  if ( LastError > 0 )
    CredentialsCacheConfig = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
      463,
      "CREDENTIALS_CACHE::Initialize",
      CredentialsCacheConfig,
      "CreateTimerQueueTimer() failed\n");
  if ( CredentialsCacheConfig < 0 )
    goto LABEL_16;
  return (unsigned int)CredentialsCacheConfig;
}

```

## disassembly

```asm
0x18001e53c  mov     [rsp+arg_0], rbx
0x18001e541  push    rdi
0x18001e542  sub     rsp, 40h
0x18001e546  mov     rdi, rcx
0x18001e549  call    cs:__imp_?IsValid@CLKRHashTable@@QEBA_NXZ; CLKRHashTable::IsValid(void)
0x18001e54f  test    al, al
0x18001e551  jnz     short loc_18001E55D
0x18001e553  mov     ebx, 8007000Eh
0x18001e558  jmp     loc_18001E659
0x18001e55d  call    ?Initialize@CREDENTIALS_CACHE_ENTRY@@SAJXZ; CREDENTIALS_CACHE_ENTRY::Initialize(void)
0x18001e562  mov     ebx, eax
0x18001e564  test    eax, eax
0x18001e566  jns     short loc_18001E5AB
0x18001e568  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e56f  jz      loc_18001E659
0x18001e575  lea     rax, aCredentialsCac_3; "Credentials cache entry init failed\n"
0x18001e57c  mov     r8d, 1B0h
0x18001e582  mov     rcx, cs:g_pDebug
0x18001e589  lea     r9, aCredentialsCac_0; "CREDENTIALS_CACHE::Initialize"
0x18001e590  mov     qword ptr [rsp+48h+Period], rax
0x18001e595  lea     rdx, aInetsrvIisIisr_21; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001e59c  mov     [rsp+48h+DueTime], ebx
0x18001e5a0  call    cs:__imp_PuDbgPrintError
0x18001e5a6  jmp     loc_18001E659
0x18001e5ab  mov     rcx, rdi; this
0x18001e5ae  call    ?ReadCredentialsCacheConfig@CREDENTIALS_CACHE@@AEAAJXZ; CREDENTIALS_CACHE::ReadCredentialsCacheConfig(void)
0x18001e5b3  mov     ebx, eax
0x18001e5b5  test    eax, eax
0x18001e5b7  jns     short loc_18001E5D5
0x18001e5b9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e5c0  jz      loc_18001E659
0x18001e5c6  lea     rax, aFailedToReadCr; "Failed to read credentials cache config"...
0x18001e5cd  mov     r8d, 1BAh
0x18001e5d3  jmp     short loc_18001E582
0x18001e5d5  imul    eax, [rdi+48h], 3E8h
0x18001e5dc  lea     rcx, [rdi+50h]; phNewTimer
0x18001e5e0  mov     [rsp+48h+Flags], 10h; Flags
0x18001e5e8  lea     r8, ?CredentialsCacheScavengerCallback@CREDENTIALS_CACHE@@CAXPEAXH@Z; Callback
0x18001e5ef  mov     r9, rdi; Parameter
0x18001e5f2  xor     edx, edx; TimerQueue
0x18001e5f4  mov     [rsp+48h+Period], eax; Period
0x18001e5f8  mov     [rsp+48h+DueTime], eax; DueTime
0x18001e5fc  call    cs:__imp_CreateTimerQueueTimer
0x18001e602  test    eax, eax
0x18001e604  jnz     short loc_18001E663
0x18001e606  call    cs:__imp_GetLastError
0x18001e60c  mov     ebx, eax
0x18001e60e  test    eax, eax
0x18001e610  jle     short loc_18001E61B
0x18001e612  movzx   ebx, ax
0x18001e615  or      ebx, 80070000h
0x18001e61b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e622  jz      short loc_18001E655
0x18001e624  mov     rcx, cs:g_pDebug
0x18001e62b  lea     rax, aCreatetimerque; "CreateTimerQueueTimer() failed\n"
0x18001e632  mov     qword ptr [rsp+48h+Period], rax
0x18001e637  lea     r9, aCredentialsCac_0; "CREDENTIALS_CACHE::Initialize"
0x18001e63e  mov     r8d, 1CFh
0x18001e644  mov     [rsp+48h+DueTime], ebx
0x18001e648  lea     rdx, aInetsrvIisIisr_21; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001e64f  call    cs:__imp_PuDbgPrintError
0x18001e655  test    ebx, ebx
0x18001e657  jns     short loc_18001E665
0x18001e659  mov     rcx, rdi; this
0x18001e65c  call    ?Terminate@CREDENTIALS_CACHE@@QEAAXXZ; CREDENTIALS_CACHE::Terminate(void)
0x18001e661  jmp     short loc_18001E665
0x18001e663  xor     ebx, ebx
0x18001e665  mov     eax, ebx
0x18001e667  mov     rbx, [rsp+48h+arg_0]
0x18001e66c  add     rsp, 40h
0x18001e670  pop     rdi
0x18001e671  retn
```
