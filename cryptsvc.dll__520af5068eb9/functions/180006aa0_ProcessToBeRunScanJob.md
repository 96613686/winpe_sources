# ProcessToBeRunScanJob

- ea: `0x180006aa0`
- end: `0x180006cfa`
- name: `ProcessToBeRunScanJob`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD *hMem)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180005460`

## callees

- `0x1800011f4`
- `0x180001ca0`
- `0x180003aa0`
- `0x180004180`
- `0x1800068b0`
- `0x180006aa0`
- `0x180006d00`
- `0x180007980`
- `0x1800079d0`
- `0x180007a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006cdc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006cdc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006af8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006af8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006b1d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006adf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006ac2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006ac2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006b59`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006b59`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006b4f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006bb1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006c49`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006c7b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006b4f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006bb1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006c49`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006c7b`

## pseudocode

```c
__int64 __fastcall ProcessToBeRunScanJob(_QWORD *hMem)
{
  __int64 v1; // rbx
  int v3; // edi
  void **v4; // rax
  void *v5; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  FILETIME *i; // rdi
  ULONGLONG TickCount64; // rax
  __int64 v10; // rcx
  FILETIME v12; // rax
  FILETIME *v13; // rdx
  FILETIME *v14; // rcx
  __int64 dwHighDateTime; // rax
  FILETIME v16; // rax
  HANDLE *v17; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v1 = hMem[4];
  v3 = *(_DWORD *)(v1 + 72);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( v3
    || (*(_DWORD *)(v1 + 96) || *(_DWORD *)(v1 + 100))
    && CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)(v1 + 96)) >= 0 )
  {
    *(_DWORD *)(v1 + 72) = 0;
    v4 = (void **)hMem[5];
    TokenHandle = 0;
    v5 = *v4;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
      || (LastError = GetLastError(), TokenHandle = 0, LastError == 1008) )
    {
      if ( SetThreadToken(0, v5) )
      {
        ResyncPreFetchAndFlush(v1);
        RestoreToken(TokenHandle);
        goto LABEL_6;
      }
      LastError = GetLastError();
    }
    SetLastError(LastError);
    if ( TokenHandle )
      I_UrlCacheCloseHandle(TokenHandle);
  }
LABEL_6:
  for ( i = *(FILETIME **)(v1 + 48); i; i = *(FILETIME **)(v1 + 48) )
  {
    if ( CompareFileTime(&SystemTimeAsFileTime, i + 2) < 0 )
      break;
    v12 = *i;
    v13 = (FILETIME *)i[6];
    v14 = (FILETIME *)i[1];
    if ( *i )
    {
      *(_QWORD *)(*(_QWORD *)&v12 + 8LL) = v14;
      *i = 0;
    }
    if ( v14 )
    {
      *v14 = v12;
      i[1] = 0;
    }
    else
    {
      v13[6] = v12;
    }
    if ( i[22].dwLowDateTime && i[26].dwLowDateTime && CompareFileTime(&SystemTimeAsFileTime, i + 24) >= 0 )
    {
      i[22].dwLowDateTime = 0;
      i[26].dwHighDateTime = 1;
    }
    dwHighDateTime = i[26].dwHighDateTime;
    if ( (unsigned int)dwHighDateTime < i[26].dwLowDateTime
      && CompareFileTime(&SystemTimeAsFileTime, &i[dwHighDateTime + 24]) >= 0 )
    {
      ++i[26].dwHighDateTime;
    }
    v16 = (FILETIME)hMem[5];
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v16 + 8LL));
    i[16] = v16;
    AddRetrievalPreFetchJob(i);
  }
  TickCount64 = GetTickCount64();
  v10 = *(_QWORD *)(v1 + 112);
  if ( !v10 || TickCount64 >= v10 + 172800000 )
  {
    *(_QWORD *)(v1 + 112) = TickCount64;
    v17 = (HANDLE *)hMem[5];
    TokenHandle = 0;
    if ( (unsigned int)ImpersonateToken(*v17, &TokenHandle) )
    {
      FlushCacheDir(v1, *(_QWORD *)hMem[5]);
      RestoreToken(TokenHandle);
    }
  }
  *(_QWORD *)(v1 + 80) = 0;
  ReleaseTokenEntry(hMem + 5);
  PkiFree(hMem);
  return CheckPendingAndScheduleUpdateHpkpJob();
}

```

## disassembly

```asm
0x180006aa0  mov     [rsp+arg_10], rbx
0x180006aa5  push    rbp
0x180006aa6  push    rsi
0x180006aa7  push    rdi
0x180006aa8  sub     rsp, 20h
0x180006aac  mov     rbx, [rcx+20h]
0x180006ab0  mov     rsi, rcx
0x180006ab3  xor     ebp, ebp
0x180006ab5  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006aba  mov     edi, [rbx+48h]
0x180006abd  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x180006ac2  call    cs:__imp_GetSystemTimeAsFileTime
0x180006ac8  test    edi, edi
0x180006aca  jz      loc_180006BA3
0x180006ad0  mov     [rbx+48h], ebp
0x180006ad3  mov     rax, [rsi+28h]
0x180006ad7  mov     [rsp+38h+TokenHandle], rbp
0x180006adc  mov     rdi, [rax]
0x180006adf  call    cs:__imp_GetCurrentThread
0x180006ae5  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180006aea  mov     edx, 0Ch; DesiredAccess
0x180006aef  mov     rcx, rax; ThreadHandle
0x180006af2  mov     r8d, 1; OpenAsSelf
0x180006af8  call    cs:__imp_OpenThreadToken
0x180006afe  test    eax, eax
0x180006b00  jnz     short loc_180006B18
0x180006b02  call    cs:__imp_GetLastError
0x180006b08  mov     [rsp+38h+TokenHandle], rbp
0x180006b0d  cmp     eax, 3F0h
0x180006b12  jnz     loc_180006CDA
0x180006b18  mov     rdx, rdi; Token
0x180006b1b  xor     ecx, ecx; Thread
0x180006b1d  call    cs:__imp_SetThreadToken
0x180006b23  test    eax, eax
0x180006b25  jz      loc_180006CD4
0x180006b2b  mov     rcx, rbx
0x180006b2e  call    ResyncPreFetchAndFlush
0x180006b33  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180006b38  call    ?RestoreToken@@YAXPEAX@Z; RestoreToken(void *)
0x180006b3d  mov     rdi, [rbx+30h]
0x180006b41  test    rdi, rdi
0x180006b44  jz      short loc_180006B59
0x180006b46  lea     rdx, [rdi+10h]; lpFileTime2
0x180006b4a  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x180006b4f  call    cs:__imp_CompareFileTime
0x180006b55  test    eax, eax
0x180006b57  jns     short loc_180006BC0
0x180006b59  call    cs:__imp_GetTickCount64
0x180006b5f  mov     rcx, [rbx+70h]
0x180006b63  test    rcx, rcx
0x180006b66  jz      loc_180006C94
0x180006b6c  add     rcx, 0A4CB800h
0x180006b73  cmp     rax, rcx
0x180006b76  jnb     loc_180006C94
0x180006b7c  lea     rcx, [rsi+28h]
0x180006b80  mov     [rbx+50h], rbp
0x180006b84  call    ReleaseTokenEntry
0x180006b89  mov     rcx, rsi; hMem
0x180006b8c  call    PkiFree
0x180006b91  call    CheckPendingAndScheduleUpdateHpkpJob
0x180006b96  mov     rbx, [rsp+38h+arg_10]
0x180006b9b  add     rsp, 20h
0x180006b9f  pop     rdi
0x180006ba0  pop     rsi
0x180006ba1  pop     rbp
0x180006ba2  retn
0x180006ba3  cmp     [rbx+60h], ebp
0x180006ba6  lea     rdx, [rbx+60h]; lpFileTime2
0x180006baa  jz      short loc_180006C26
0x180006bac  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x180006bb1  call    cs:__imp_CompareFileTime
0x180006bb7  test    eax, eax
0x180006bb9  js      short loc_180006B3D
0x180006bbb  jmp     loc_180006AD0
0x180006bc0  mov     rax, [rdi]
0x180006bc3  mov     rdx, [rdi+30h]
0x180006bc7  mov     rcx, [rdi+8]
0x180006bcb  test    rax, rax
0x180006bce  jz      short loc_180006BD7
0x180006bd0  mov     [rax+8], rcx
0x180006bd4  mov     [rdi], rbp
0x180006bd7  test    rcx, rcx
0x180006bda  jz      loc_180006C65
0x180006be0  mov     [rcx], rax
0x180006be3  mov     [rdi+8], rbp
0x180006be7  cmp     [rdi+0B0h], ebp
0x180006bed  jnz     short loc_180006C34
0x180006bef  mov     eax, [rdi+0D4h]
0x180006bf5  cmp     eax, [rdi+0D0h]
0x180006bfb  jb      short loc_180006C6E
0x180006bfd  mov     rax, [rsi+28h]
0x180006c01  lock inc dword ptr [rax+8]
0x180006c05  mov     rcx, rdi
0x180006c08  mov     [rdi+80h], rax
0x180006c0f  call    AddRetrievalPreFetchJob
0x180006c14  mov     rdi, [rbx+30h]
0x180006c18  test    rdi, rdi
0x180006c1b  jnz     loc_180006B46
0x180006c21  jmp     loc_180006B59
0x180006c26  cmp     [rdx+4], ebp
0x180006c29  jz      loc_180006B3D
0x180006c2f  jmp     loc_180006BAC
0x180006c34  cmp     dword ptr [rdi+0D0h], 1
0x180006c3b  jb      short loc_180006BEF
0x180006c3d  lea     rdx, [rdi+0C0h]; lpFileTime2
0x180006c44  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x180006c49  call    cs:__imp_CompareFileTime
0x180006c4f  test    eax, eax
0x180006c51  js      short loc_180006BEF
0x180006c53  mov     [rdi+0B0h], ebp
0x180006c59  mov     dword ptr [rdi+0D4h], 1
0x180006c63  jmp     short loc_180006BEF
0x180006c65  mov     [rdx+30h], rax
0x180006c69  jmp     loc_180006BE7
0x180006c6e  add     rax, 18h
0x180006c72  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x180006c77  lea     rdx, [rdi+rax*8]; lpFileTime2
0x180006c7b  call    cs:__imp_CompareFileTime
0x180006c81  test    eax, eax
0x180006c83  js      loc_180006BFD
0x180006c89  inc     dword ptr [rdi+0D4h]
0x180006c8f  jmp     loc_180006BFD
0x180006c94  mov     [rbx+70h], rax
0x180006c98  lea     rdx, [rsp+38h+TokenHandle]; void **
0x180006c9d  mov     rcx, [rsi+28h]
0x180006ca1  mov     [rsp+38h+TokenHandle], rbp
0x180006ca6  mov     rcx, [rcx]; Token
0x180006ca9  call    ?ImpersonateToken@@YAHPEAXPEAPEAX@Z; ImpersonateToken(void *,void * *)
0x180006cae  test    eax, eax
0x180006cb0  jz      loc_180006B7C
0x180006cb6  mov     rdx, [rsi+28h]
0x180006cba  mov     rcx, rbx
0x180006cbd  mov     rdx, [rdx]
0x180006cc0  call    FlushCacheDir
0x180006cc5  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180006cca  call    ?RestoreToken@@YAXPEAX@Z; RestoreToken(void *)
0x180006ccf  jmp     loc_180006B7C
0x180006cd4  call    cs:__imp_GetLastError
0x180006cda  mov     ecx, eax; dwErrCode
0x180006cdc  call    cs:__imp_SetLastError
0x180006ce2  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180006ce7  test    rcx, rcx
0x180006cea  jz      loc_180006B3D
0x180006cf0  call    I_UrlCacheCloseHandle
0x180006cf5  jmp     loc_180006B3D
```
