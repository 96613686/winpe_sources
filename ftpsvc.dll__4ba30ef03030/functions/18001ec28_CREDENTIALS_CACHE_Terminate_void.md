# CREDENTIALS_CACHE::Terminate(void)

- ea: `0x18001ec28`
- end: `0x18001ecf4`
- name: `?Terminate@CREDENTIALS_CACHE@@QEAAXXZ`
- size: `204`
- prototype: `void __fastcall(CREDENTIALS_CACHE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180004a18`
- `0x18001e53c`

## callees

- `0x180001250`
- `0x18001ec28`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18001ec40`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18001ec40`
- `KERNEL32!GetLastError` at `0x18001ec53`
- `KERNEL32!GetLastError` at `0x18001ec53`
- `ADVAPI32!CryptReleaseContext` at `0x18001ecdd`
- `ADVAPI32!CryptReleaseContext` at `0x18001ecdd`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001eca1`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001eca1`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001ecb6`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001ecb6`
- `iisutil!PuDbgPrintError` at `0x18001ec90`
- `iisutil!PuDbgPrintError` at `0x18001ec90`

## string_xrefs

- `0x18001ec65`: `DeleteTimerQueueTimer failed\n`
- `0x18001ec85`: `inetsrv\iis\iisrearc\ftp\server\core\credentials_cache.cxx`
- `0x18001ec77`: `CREDENTIALS_CACHE::Terminate`

## pseudocode

```c
void __fastcall CREDENTIALS_CACHE::Terminate(CREDENTIALS_CACHE *this)
{
  void *v1; // rdx
  signed int LastError; // eax
  void *v4; // rbx

  v1 = (void *)*((_QWORD *)this + 10);
  if ( v1 )
  {
    if ( !DeleteTimerQueueTimer(0, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 0xF) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\credentials_cache.cxx",
        508,
        "CREDENTIALS_CACHE::Terminate",
        LastError,
        "DeleteTimerQueueTimer failed\n");
    }
    *((_QWORD *)this + 10) = 0;
  }
  CLKRHashTable::Clear(this);
  v4 = CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry;
  if ( CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry);
    operator delete(v4);
    CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry = 0;
  }
  if ( CREDENTIALS_CACHE_ENTRY::sm_hCryptProv )
  {
    CryptReleaseContext(CREDENTIALS_CACHE_ENTRY::sm_hCryptProv, 0);
    CREDENTIALS_CACHE_ENTRY::sm_hCryptProv = 0;
  }
}

```

## disassembly

```asm
0x18001ec28  push    rbx
0x18001ec2a  sub     rsp, 30h
0x18001ec2e  mov     rdx, [rcx+50h]; Timer
0x18001ec32  mov     rbx, rcx
0x18001ec35  test    rdx, rdx
0x18001ec38  jz      short loc_18001EC9E
0x18001ec3a  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001ec3e  xor     ecx, ecx; TimerQueue
0x18001ec40  call    cs:__imp_DeleteTimerQueueTimer
0x18001ec46  test    eax, eax
0x18001ec48  jnz     short loc_18001EC96
0x18001ec4a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001ec51  jz      short loc_18001EC96
0x18001ec53  call    cs:__imp_GetLastError
0x18001ec59  test    eax, eax
0x18001ec5b  jle     short loc_18001EC65
0x18001ec5d  movzx   eax, ax
0x18001ec60  or      eax, 80070000h
0x18001ec65  lea     rcx, aDeletetimerque; "DeleteTimerQueueTimer failed\n"
0x18001ec6c  mov     r8d, 1FCh
0x18001ec72  mov     [rsp+38h+var_10], rcx
0x18001ec77  lea     r9, aCredentialsCac_2; "CREDENTIALS_CACHE::Terminate"
0x18001ec7e  mov     rcx, cs:g_pDebug
0x18001ec85  lea     rdx, aInetsrvIisIisr_21; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ec8c  mov     [rsp+38h+var_18], eax
0x18001ec90  call    cs:__imp_PuDbgPrintError
0x18001ec96  mov     qword ptr [rbx+50h], 0
0x18001ec9e  mov     rcx, rbx
0x18001eca1  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18001eca7  mov     rbx, cs:?sm_pachCredentialCacheEntry@CREDENTIALS_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry
0x18001ecae  test    rbx, rbx
0x18001ecb1  jz      short loc_18001ECCF
0x18001ecb3  mov     rcx, rbx
0x18001ecb6  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18001ecbc  mov     rcx, rbx; Block
0x18001ecbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ecc4  mov     cs:?sm_pachCredentialCacheEntry@CREDENTIALS_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry
0x18001eccf  mov     rcx, cs:?sm_hCryptProv@CREDENTIALS_CACHE_ENTRY@@0_KA; hProv
0x18001ecd6  test    rcx, rcx
0x18001ecd9  jz      short loc_18001ECEE
0x18001ecdb  xor     edx, edx; dwFlags
0x18001ecdd  call    cs:__imp_CryptReleaseContext
0x18001ece3  mov     cs:?sm_hCryptProv@CREDENTIALS_CACHE_ENTRY@@0_KA, 0; unsigned __int64 CREDENTIALS_CACHE_ENTRY::sm_hCryptProv
0x18001ecee  add     rsp, 30h
0x18001ecf2  pop     rbx
0x18001ecf3  retn
```
