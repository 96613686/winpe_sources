# MyGetComputerName(EXTENDED_NAME_FORMAT)

- ea: `0x1800b30a0`
- end: `0x1800b3233`
- name: `?MyGetComputerName@@YAPEAGW4EXTENDED_NAME_FORMAT@@@Z`
- size: `403`
- prototype: `unsigned __int16 *__fastcall(EXTENDED_NAME_FORMAT NameFormat)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180019fb4`
- `0x18005ce5c`
- `0x1800af3c0`

## callees

- `0x180075ec0`
- `0x1800b30a0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3221`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b30d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b315e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b320a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b30d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b315e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b320a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b30ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b30ca`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800b3188`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800b3188`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b316e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b316e`
- `Secur32!GetComputerObjectNameW` at `0x1800b3150`
- `Secur32!GetComputerObjectNameW` at `0x1800b3200`
- `Secur32!GetComputerObjectNameW` at `0x1800b3150`
- `Secur32!GetComputerObjectNameW` at `0x1800b3200`

## string_xrefs

- `0x1800b30fb`: `MyGetComputerName:  Failed to allocate memory with %d`
- `0x1800b312e`: `MyGetComputerName:  Failed to allocate memory with %d`
- `0x1800b31b5`: `MyGetComputerName:  Failed to realloc memory with %d`
- `0x1800b31dd`: `MyGetComputerName:  Failed to realloc memory with %d`

## pseudocode

```c
unsigned __int16 *__fastcall MyGetComputerName(EXTENDED_NAME_FORMAT NameFormat)
{
  __int64 v1; // rdx
  WCHAR *v3; // rax
  WCHAR *v4; // rdi
  DWORD LastError; // ebx
  WCHAR *v6; // rcx
  WCHAR *v7; // rax
  WCHAR *v8; // rsi
  ULONG nSize; // [rsp+50h] [rbp+8h] BYREF

  v1 = 75;
  nSize = 75;
  if ( (NameFormat & 1) != 0 )
  {
    v1 = 200;
    nSize = 200;
  }
  v3 = (WCHAR *)LocalAlloc(0x40u, 2 * v1);
  v4 = v3;
  if ( v3 )
  {
    LastError = 0;
    if ( !GetComputerObjectNameW(NameFormat, v3, &nSize) )
    {
      LastError = GetLastError();
      v6 = v4;
      if ( LastError == 122 )
      {
        v7 = (WCHAR *)LocalReAlloc(v4, 2LL * nSize, 2u);
        v8 = v7;
        if ( v7 )
        {
          if ( GetComputerObjectNameW(NameFormat, v7, &nSize) )
          {
            v4 = v8;
            LastError = 0;
            goto LABEL_24;
          }
          LastError = GetLastError();
          v6 = v8;
        }
        else
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"MyGetComputerName:  Failed to realloc memory with %d", LastError);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"MyGetComputerName:  Failed to realloc memory with %d", LastError);
            }
          }
          v6 = v4;
        }
      }
      LocalFree(v6);
      v4 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"MyGetComputerName:  Failed to allocate memory with %d", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"MyGetComputerName:  Failed to allocate memory with %d", LastError);
      }
    }
  }
LABEL_24:
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x1800b30a0  push    rbx
0x1800b30a2  push    rbp
0x1800b30a3  push    rsi
0x1800b30a4  push    rdi
0x1800b30a5  sub     rsp, 28h
0x1800b30a9  mov     edx, 4Bh ; 'K'
0x1800b30ae  mov     ebp, ecx
0x1800b30b0  mov     [rsp+48h+nSize], edx
0x1800b30b4  test    cl, 1
0x1800b30b7  jz      short loc_1800B30C2
0x1800b30b9  mov     edx, 0C8h
0x1800b30be  mov     [rsp+48h+nSize], edx
0x1800b30c2  add     rdx, rdx; uBytes
0x1800b30c5  mov     ecx, 40h ; '@'; uFlags
0x1800b30ca  call    cs:__imp_LocalAlloc
0x1800b30d0  mov     rdi, rax
0x1800b30d3  test    rax, rax
0x1800b30d6  jnz     short loc_1800B3144
0x1800b30d8  call    cs:__imp_GetLastError
0x1800b30de  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x1800b30e4  mov     ebx, eax
0x1800b30e6  jz      loc_1800B321F
0x1800b30ec  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b30f3  test    rax, rax
0x1800b30f6  jz      short loc_1800B310F
0x1800b30f8  mov     r8d, ebx
0x1800b30fb  lea     rdx, aMygetcomputern; "MyGetComputerName:  Failed to allocate "...
0x1800b3102  lea     ecx, [rdi+2]
0x1800b3105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b310a  jmp     loc_1800B321F
0x1800b310f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800b3117  jz      loc_1800B321F
0x1800b311d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3125  jz      loc_1800B321F
0x1800b312b  mov     r8d, ebx
0x1800b312e  lea     rdx, aMygetcomputern; "MyGetComputerName:  Failed to allocate "...
0x1800b3135  mov     ecx, 2; unsigned int
0x1800b313a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b313f  jmp     loc_1800B321F
0x1800b3144  lea     r8, [rsp+48h+nSize]; nSize
0x1800b3149  mov     rdx, rdi; lpNameBuffer
0x1800b314c  mov     ecx, ebp; NameFormat
0x1800b314e  xor     ebx, ebx
0x1800b3150  call    cs:__imp_GetComputerObjectNameW
0x1800b3156  test    al, al
0x1800b3158  jnz     loc_1800B321F
0x1800b315e  call    cs:__imp_GetLastError
0x1800b3164  mov     ebx, eax
0x1800b3166  mov     rcx, rdi; hMem
0x1800b3169  cmp     eax, 7Ah ; 'z'
0x1800b316c  jz      short loc_1800B317B
0x1800b316e  call    cs:__imp_LocalFree
0x1800b3174  xor     edi, edi
0x1800b3176  jmp     loc_1800B321F
0x1800b317b  mov     edx, [rsp+48h+nSize]
0x1800b317f  mov     r8d, 2; uFlags
0x1800b3185  add     rdx, rdx; uBytes
0x1800b3188  call    cs:__imp_LocalReAlloc
0x1800b318e  mov     rsi, rax
0x1800b3191  test    rax, rax
0x1800b3194  jnz     short loc_1800B31F6
0x1800b3196  call    cs:__imp_GetLastError
0x1800b319c  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800b31a2  mov     ebx, eax
0x1800b31a4  jz      short loc_1800B31EE
0x1800b31a6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b31ad  test    rax, rax
0x1800b31b0  jz      short loc_1800B31C6
0x1800b31b2  mov     r8d, ebx
0x1800b31b5  lea     rdx, aMygetcomputern_0; "MyGetComputerName:  Failed to realloc m"...
0x1800b31bc  lea     ecx, [rsi+2]
0x1800b31bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31c4  jmp     short loc_1800B31EE
0x1800b31c6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800b31ce  jz      short loc_1800B31EE
0x1800b31d0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b31d8  jz      short loc_1800B31EE
0x1800b31da  mov     r8d, ebx
0x1800b31dd  lea     rdx, aMygetcomputern_0; "MyGetComputerName:  Failed to realloc m"...
0x1800b31e4  mov     ecx, 2; unsigned int
0x1800b31e9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b31ee  mov     rcx, rdi
0x1800b31f1  jmp     loc_1800B316E
0x1800b31f6  lea     r8, [rsp+48h+nSize]; nSize
0x1800b31fb  mov     rdx, rsi; lpNameBuffer
0x1800b31fe  mov     ecx, ebp; NameFormat
0x1800b3200  call    cs:__imp_GetComputerObjectNameW
0x1800b3206  test    al, al
0x1800b3208  jnz     short loc_1800B321A
0x1800b320a  call    cs:__imp_GetLastError
0x1800b3210  mov     ebx, eax
0x1800b3212  mov     rcx, rsi
0x1800b3215  jmp     loc_1800B316E
0x1800b321a  mov     rdi, rsi
0x1800b321d  xor     ebx, ebx
0x1800b321f  mov     ecx, ebx; dwErrCode
0x1800b3221  call    cs:__imp_SetLastError
0x1800b3227  mov     rax, rdi
0x1800b322a  add     rsp, 28h
0x1800b322e  pop     rdi
0x1800b322f  pop     rsi
0x1800b3230  pop     rbp
0x1800b3231  pop     rbx
0x1800b3232  retn
```
