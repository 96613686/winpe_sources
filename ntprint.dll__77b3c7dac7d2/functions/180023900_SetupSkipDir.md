# SetupSkipDir

- ea: `0x180023900`
- end: `0x180023a16`
- name: `SetupSkipDir`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180012424`

## callees

- `0x180002300`
- `0x1800078f0`
- `0x18000797c`
- `0x18001bc44`
- `0x180023900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800239f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800239f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023922`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023967`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800239b2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800239b2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180023940`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180023940`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800239da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800239da`

## pseudocode

```c
__int64 SetupSkipDir()
{
  DWORD CurrentProcessId; // eax
  WCHAR *v1; // rax
  unsigned int v2; // ebx
  unsigned __int16 v4[32]; // [rsp+20h] [rbp-2B8h] BYREF
  WCHAR Buffer[304]; // [rsp+60h] [rbp-278h] BYREF

  EnterCriticalSection(&SkipCritSect);
  if ( gpszSkipDir )
    goto LABEL_9;
  if ( GetTempPathW(0x104u, Buffer) - 1 <= 0x103 )
  {
    StringCchCatW(Buffer, 0x12Bu, L"\\__SKIP_");
    CurrentProcessId = GetCurrentProcessId();
    StringCchPrintfW(v4, 0x1Eu, L"%lX", CurrentProcessId);
    StringCchCatW(Buffer, 0x12Bu, v4);
    v1 = (WCHAR *)AllocStr(Buffer);
    gpszSkipDir = v1;
    if ( !v1 )
      goto LABEL_7;
    if ( CreateDirectoryW(v1, 0) || GetLastError() == 183 )
    {
LABEL_9:
      v2 = 1;
      goto LABEL_10;
    }
  }
  v1 = (WCHAR *)gpszSkipDir;
LABEL_7:
  v2 = 0;
  if ( v1 )
  {
    LocalFree(v1);
    gpszSkipDir = 0;
  }
LABEL_10:
  LeaveCriticalSection(&SkipCritSect);
  return v2;
}

```

## disassembly

```asm
0x180023900  push    rbx
0x180023902  sub     rsp, 2D0h
0x180023909  mov     rax, cs:__security_cookie
0x180023910  xor     rax, rsp
0x180023913  mov     [rsp+2D8h+var_18], rax
0x18002391b  lea     rcx, SkipCritSect; lpCriticalSection
0x180023922  call    cs:__imp_EnterCriticalSection
0x180023928  cmp     cs:gpszSkipDir, 0
0x180023930  jnz     loc_1800239E9
0x180023936  lea     rdx, [rsp+2D8h+Buffer]; lpBuffer
0x18002393b  mov     ecx, 104h; nBufferLength
0x180023940  call    cs:__imp_GetTempPathW
0x180023946  dec     eax
0x180023948  cmp     eax, 103h
0x18002394d  ja      short loc_1800239C9
0x18002394f  mov     ebx, 12Bh
0x180023954  lea     r8, aSkip; "\\__SKIP_"
0x18002395b  mov     edx, ebx; unsigned __int64
0x18002395d  lea     rcx, [rsp+2D8h+Buffer]; unsigned __int16 *
0x180023962  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023967  call    cs:__imp_GetCurrentProcessId
0x18002396d  lea     r8, aLx; "%lX"
0x180023974  mov     edx, 1Eh; unsigned __int64
0x180023979  mov     r9d, eax
0x18002397c  lea     rcx, [rsp+2D8h+var_2B8]; unsigned __int16 *
0x180023981  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023986  lea     r8, [rsp+2D8h+var_2B8]; unsigned __int16 *
0x18002398b  mov     edx, ebx; unsigned __int64
0x18002398d  lea     rcx, [rsp+2D8h+Buffer]; unsigned __int16 *
0x180023992  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023997  lea     rcx, [rsp+2D8h+Buffer]; unsigned __int16 *
0x18002399c  call    AllocStr
0x1800239a1  mov     cs:gpszSkipDir, rax
0x1800239a8  test    rax, rax
0x1800239ab  jz      short loc_1800239D0
0x1800239ad  xor     edx, edx; lpSecurityAttributes
0x1800239af  mov     rcx, rax; lpPathName
0x1800239b2  call    cs:__imp_CreateDirectoryW
0x1800239b8  test    eax, eax
0x1800239ba  jnz     short loc_1800239E9
0x1800239bc  call    cs:__imp_GetLastError
0x1800239c2  cmp     eax, 0B7h
0x1800239c7  jz      short loc_1800239E9
0x1800239c9  mov     rax, cs:gpszSkipDir
0x1800239d0  xor     ebx, ebx
0x1800239d2  test    rax, rax
0x1800239d5  jz      short loc_1800239EE
0x1800239d7  mov     rcx, rax; hMem
0x1800239da  call    cs:__imp_LocalFree
0x1800239e0  mov     cs:gpszSkipDir, rbx
0x1800239e7  jmp     short loc_1800239EE
0x1800239e9  mov     ebx, 1
0x1800239ee  lea     rcx, SkipCritSect; lpCriticalSection
0x1800239f5  call    cs:__imp_LeaveCriticalSection
0x1800239fb  mov     eax, ebx
0x1800239fd  mov     rcx, [rsp+2D8h+var_18]
0x180023a05  xor     rcx, rsp; StackCookie
0x180023a08  call    __security_check_cookie
0x180023a0d  add     rsp, 2D0h
0x180023a14  pop     rbx
0x180023a15  retn
```
