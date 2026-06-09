# UninitializeLoader

- ea: `0x180006f40`
- end: `0x18000701e`
- name: `UninitializeLoader`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013d38`

## callees

- `0x180005384`
- `0x180006f40`
- `0x180007ca0`
- `0x18000d02c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006fc2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006fc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f58`

## string_xrefs

- `0x180006ff4`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
void __fastcall UninitializeLoader(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rax

  if ( g_fLoaderInitialized )
  {
    EnterCriticalSection(&g_csLoaderLock);
    LeaveCriticalSection(&g_csLoaderLock);
    v3 = g_pLoadedProviderList;
    if ( g_pLoadedProviderList )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_8;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_67679bdabad938a7dfcc8815ccec1def_Traceguids);
      while ( 1 )
      {
        v3 = g_pLoadedProviderList;
LABEL_8:
        if ( !v3 )
          break;
        UnloadProvider(v3);
      }
    }
    DeleteCriticalSection(&g_csLoaderLock);
    g_fLoaderInitialized = 0;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      a3,
      (unsigned int)"NTE_FAIL",
      32,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      195);
  }
}

```

## disassembly

```asm
0x180006f40  sub     rsp, 48h
0x180006f44  cmp     cs:g_fLoaderInitialized, 0
0x180006f4b  jz      loc_180006FD7
0x180006f51  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180006f58  call    cs:__imp_EnterCriticalSection
0x180006f5e  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180006f65  call    cs:__imp_LeaveCriticalSection
0x180006f6b  mov     rax, cs:g_pLoadedProviderList
0x180006f72  test    rax, rax
0x180006f75  jz      short loc_180006FBB
0x180006f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f7e  lea     rdx, WPP_GLOBAL_Control
0x180006f85  cmp     rcx, rdx
0x180006f88  jz      short loc_180006FB6
0x180006f8a  test    byte ptr [rcx+1Ch], 2
0x180006f8e  jz      short loc_180006FB6
0x180006f90  mov     rcx, [rcx+10h]
0x180006f94  lea     r8, WPP_67679bdabad938a7dfcc8815ccec1def_Traceguids
0x180006f9b  mov     edx, 19h
0x180006fa0  call    WPP_SF_
0x180006fa5  jmp     short loc_180006FAF
0x180006fa7  mov     rcx, rax
0x180006faa  call    UnloadProvider
0x180006faf  mov     rax, cs:g_pLoadedProviderList
0x180006fb6  test    rax, rax
0x180006fb9  jnz     short loc_180006FA7
0x180006fbb  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180006fc2  call    cs:__imp_DeleteCriticalSection
0x180006fc8  mov     cs:g_fLoaderInitialized, 0
0x180006fd2  add     rsp, 48h
0x180006fd6  retn
0x180006fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fde  lea     rdx, WPP_GLOBAL_Control
0x180006fe5  cmp     rcx, rdx
0x180006fe8  jz      short loc_180006FD2
0x180006fea  test    byte ptr [rcx+1Ch], 1
0x180006fee  jz      short loc_180006FD2
0x180006ff0  mov     rcx, [rcx+10h]
0x180006ff4  lea     rax, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006ffb  mov     [rsp+48h+var_18], 7C3h
0x180007003  lea     r9, aNteFail; "NTE_FAIL"
0x18000700a  mov     [rsp+48h+var_20], rax
0x18000700f  mov     [rsp+48h+var_28], 80090020h
0x180007017  call    WPP_SF_sDsd
0x18000701c  jmp     short loc_180006FD2
```
