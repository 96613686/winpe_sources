# _pSpUtilsLogInitialize

- ea: `0x180007458`
- end: `0x1800074f4`
- name: `_pSpUtilsLogInitialize`
- size: `156`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800063bc`
- `0x180006590`

## callees

- `0x1800061d8`
- `0x18000735c`
- `0x18000740c`
- `0x180007458`
- `0x1800076d4`
- `0x1800077d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074b4`

## pseudocode

```c
__int64 pSpUtilsLogInitialize()
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  DWORD LastError; // ebx
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  v5 = 0;
  v6 = 0;
  if ( !dword_180011770 )
  {
    SetLastError(0x15u);
    return 0;
  }
  if ( !(unsigned int)AcquireInitMutex(&v5) )
    return 0;
  LastError = 0;
  if ( !g_sputils_LogInitialized )
  {
    if ( g_sputils_IsOnlineWindowsDirectory && pSpUtilsSetLogPathFromRegKey()
      || (unsigned int)pSpUtilsSetLogPath(v2, v1, v3) )
    {
      if ( (unsigned int)pSpUtilsTextLogInitialize(v2, v1, v3) )
        g_sputils_LogInitialized = 1;
      else
        LastError = 13;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  ReleaseInitMutex(&v5);
  SetLastError(LastError);
  return (unsigned int)g_sputils_LogInitialized;
}

```

## disassembly

```asm
0x180007458  push    rbx
0x18000745a  sub     rsp, 40h
0x18000745e  xor     eax, eax
0x180007460  xorps   xmm0, xmm0
0x180007463  cmp     cs:dword_180011770, eax
0x180007469  movups  [rsp+48h+var_28], xmm0
0x18000746e  mov     [rsp+48h+var_18], rax
0x180007473  jnz     short loc_180007482
0x180007475  lea     ecx, [rax+15h]; dwErrCode
0x180007478  call    cs:__imp_SetLastError
0x18000747e  xor     eax, eax
0x180007480  jmp     short loc_1800074EE
0x180007482  lea     rcx, [rsp+48h+var_28]
0x180007487  call    _AcquireInitMutex
0x18000748c  test    eax, eax
0x18000748e  jz      short loc_18000747E
0x180007490  xor     ebx, ebx
0x180007492  cmp     cs:g_sputils_LogInitialized, ebx
0x180007498  jnz     short loc_1800074D6
0x18000749a  cmp     cs:g_sputils_IsOnlineWindowsDirectory, ebx
0x1800074a0  jz      short loc_1800074AB
0x1800074a2  call    pSpUtilsSetLogPathFromRegKey
0x1800074a7  test    eax, eax
0x1800074a9  jnz     short loc_1800074BE
0x1800074ab  call    pSpUtilsSetLogPath
0x1800074b0  test    eax, eax
0x1800074b2  jnz     short loc_1800074BE
0x1800074b4  call    cs:__imp_GetLastError
0x1800074ba  mov     ebx, eax
0x1800074bc  jmp     short loc_1800074D6
0x1800074be  call    _pSpUtilsTextLogInitialize
0x1800074c3  test    eax, eax
0x1800074c5  jnz     short loc_1800074CC
0x1800074c7  lea     ebx, [rax+0Dh]
0x1800074ca  jmp     short loc_1800074D6
0x1800074cc  mov     cs:g_sputils_LogInitialized, 1
0x1800074d6  lea     rcx, [rsp+48h+var_28]
0x1800074db  call    _ReleaseInitMutex
0x1800074e0  mov     ecx, ebx; dwErrCode
0x1800074e2  call    cs:__imp_SetLastError
0x1800074e8  mov     eax, cs:g_sputils_LogInitialized
0x1800074ee  add     rsp, 40h
0x1800074f2  pop     rbx
0x1800074f3  retn
```
