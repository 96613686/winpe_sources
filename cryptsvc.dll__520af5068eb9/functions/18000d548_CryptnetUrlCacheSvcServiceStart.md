# CryptnetUrlCacheSvcServiceStart

- ea: `0x18000d548`
- end: `0x18000d624`
- name: `CryptnetUrlCacheSvcServiceStart`
- size: `220`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cb10`

## callees

- `0x180001eac`
- `0x18000c46c`
- `0x18000d548`
- `0x18000fc78`
- `0x180010f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d5f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d568`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d568`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5ff`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000d5ea`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000d5ea`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000d5c4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000d5c4`

## pseudocode

```c
__int64 CryptnetUrlCacheSvcServiceStart()
{
  unsigned int v0; // ebx
  __int64 result; // rax
  DWORD LastError; // edi

  v0 = 1;
  if ( _InterlockedExchange(&lUrlCacheSvcStartOrStop, 1) )
  {
    SetLastError(0x420u);
    return 0;
  }
  if ( !fUrlCacheSvcStarted )
  {
    InitPreFetchPara();
    if ( PreFetchPara != -1 )
    {
      InitHpkpPara();
      if ( (unsigned int)Pki_InitializeCriticalSection(&JobsCriticalSection) )
      {
        LastError = BCryptOpenAlgorithmProvider(&hAlgSha256, L"SHA256", 0, 0);
        if ( !LastError )
        {
          if ( (unsigned int)CreatePreFetchJobLruCache() )
          {
            fUrlCacheSvcStarted = 1;
            goto LABEL_13;
          }
          LastError = GetLastError();
          BCryptCloseAlgorithmProvider(hAlgSha256, 0);
        }
        DeleteCriticalSection(&JobsCriticalSection);
      }
      else
      {
        LastError = GetLastError();
      }
      SetLastError(LastError);
      v0 = 0;
    }
  }
LABEL_13:
  result = v0;
  _InterlockedExchange(&lUrlCacheSvcStartOrStop, 0);
  return result;
}

```

## disassembly

```asm
0x18000d548  mov     [rsp+arg_0], rbx
0x18000d54d  push    rdi
0x18000d54e  sub     rsp, 20h
0x18000d552  mov     ebx, 1
0x18000d557  mov     eax, ebx
0x18000d559  xchg    eax, cs:?lUrlCacheSvcStartOrStop@@3JC; long volatile lUrlCacheSvcStartOrStop
0x18000d55f  test    eax, eax
0x18000d561  jz      short loc_18000D575
0x18000d563  mov     ecx, 420h; dwErrCode
0x18000d568  call    cs:__imp_SetLastError
0x18000d56e  xor     eax, eax
0x18000d570  jmp     loc_18000D619
0x18000d575  mov     eax, cs:?fUrlCacheSvcStarted@@3HC; int volatile fUrlCacheSvcStarted
0x18000d57b  test    eax, eax
0x18000d57d  jnz     loc_18000D60F
0x18000d583  call    ?InitPreFetchPara@@YAXXZ; InitPreFetchPara(void)
0x18000d588  cmp     cs:?PreFetchPara@@3U_CUCS_PRE_FETCH_PARA@@A, 0FFFFFFFFh; _CUCS_PRE_FETCH_PARA PreFetchPara
0x18000d58f  jz      short loc_18000D60F
0x18000d591  call    InitHpkpPara
0x18000d596  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000d59d  call    Pki_InitializeCriticalSection
0x18000d5a2  test    eax, eax
0x18000d5a4  jnz     short loc_18000D5B0
0x18000d5a6  call    cs:__imp_GetLastError
0x18000d5ac  mov     edi, eax
0x18000d5ae  jmp     short loc_18000D5FD
0x18000d5b0  xor     r9d, r9d; dwFlags
0x18000d5b3  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x18000d5ba  xor     r8d, r8d; pszImplementation
0x18000d5bd  lea     rcx, ?hAlgSha256@@3PEAXEA; phAlgorithm
0x18000d5c4  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000d5ca  mov     edi, eax
0x18000d5cc  test    eax, eax
0x18000d5ce  jnz     short loc_18000D5F0
0x18000d5d0  call    CreatePreFetchJobLruCache
0x18000d5d5  test    eax, eax
0x18000d5d7  jnz     short loc_18000D609
0x18000d5d9  call    cs:__imp_GetLastError
0x18000d5df  mov     edi, eax
0x18000d5e1  mov     rcx, cs:?hAlgSha256@@3PEAXEA; hAlgorithm
0x18000d5e8  xor     edx, edx; dwFlags
0x18000d5ea  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000d5f0  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d5f7  call    cs:__imp_DeleteCriticalSection
0x18000d5fd  mov     ecx, edi; dwErrCode
0x18000d5ff  call    cs:__imp_SetLastError
0x18000d605  xor     ebx, ebx
0x18000d607  jmp     short loc_18000D60F
0x18000d609  mov     cs:?fUrlCacheSvcStarted@@3HC, ebx; int volatile fUrlCacheSvcStarted
0x18000d60f  xor     ecx, ecx
0x18000d611  mov     eax, ebx
0x18000d613  xchg    ecx, cs:?lUrlCacheSvcStartOrStop@@3JC; long volatile lUrlCacheSvcStartOrStop
0x18000d619  mov     rbx, [rsp+28h+arg_0]
0x18000d61e  add     rsp, 20h
0x18000d622  pop     rdi
0x18000d623  retn
```
