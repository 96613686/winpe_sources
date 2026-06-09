# UninitializeLoader

- ea: `0x180017160`
- end: `0x180017209`
- name: `UninitializeLoader`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b584`

## callees

- `0x180003cf0`
- `0x180006a70`
- `0x180017160`
- `0x180017210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800171f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800171f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017196`

## string_xrefs

- `0x180017173`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
void UninitializeLoader()
{
  __int64 v0; // rax

  if ( g_fLoaderInitialized )
  {
    EnterCriticalSection(&g_csLoaderLock);
    LeaveCriticalSection(&g_csLoaderLock);
    v0 = g_pLoadedProviderList;
    if ( g_pLoadedProviderList )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_9;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
      while ( 1 )
      {
        v0 = g_pLoadedProviderList;
LABEL_9:
        if ( !v0 )
          break;
        UnloadProvider(v0);
      }
    }
    DeleteCriticalSection(&g_csLoaderLock);
    g_fLoaderInitialized = 0;
  }
  else
  {
    DebugTraceError(2148073504LL, "NTE_FAIL", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 1987);
  }
}

```

## disassembly

```asm
0x180017160  sub     rsp, 28h
0x180017164  cmp     cs:g_fLoaderInitialized, 0
0x18001716b  jnz     short loc_18001718F
0x18001716d  mov     r9d, 7C3h
0x180017173  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001717a  lea     rdx, aNteFail; "NTE_FAIL"
0x180017181  mov     ecx, 80090020h
0x180017186  add     rsp, 28h
0x18001718a  jmp     DebugTraceError
0x18001718f  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180017196  call    cs:__imp_EnterCriticalSection
0x18001719c  lea     rcx, g_csLoaderLock; lpCriticalSection
0x1800171a3  call    cs:__imp_LeaveCriticalSection
0x1800171a9  mov     rax, cs:g_pLoadedProviderList
0x1800171b0  test    rax, rax
0x1800171b3  jz      short loc_1800171ED
0x1800171b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171bc  lea     rdx, WPP_GLOBAL_Control
0x1800171c3  cmp     rcx, rdx
0x1800171c6  jz      short loc_1800171E8
0x1800171c8  test    byte ptr [rcx+1Ch], 2
0x1800171cc  jz      short loc_1800171E8
0x1800171ce  mov     rcx, [rcx+10h]
0x1800171d2  call    WPP_SF_
0x1800171d7  jmp     short loc_1800171E1
0x1800171d9  mov     rcx, rax
0x1800171dc  call    UnloadProvider
0x1800171e1  mov     rax, cs:g_pLoadedProviderList
0x1800171e8  test    rax, rax
0x1800171eb  jnz     short loc_1800171D9
0x1800171ed  lea     rcx, g_csLoaderLock; lpCriticalSection
0x1800171f4  call    cs:__imp_DeleteCriticalSection
0x1800171fa  mov     cs:g_fLoaderInitialized, 0
0x180017204  add     rsp, 28h
0x180017208  retn
```
