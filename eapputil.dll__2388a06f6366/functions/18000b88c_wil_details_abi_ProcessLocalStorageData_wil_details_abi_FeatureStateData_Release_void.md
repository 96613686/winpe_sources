# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000b88c`
- end: `0x18000ba31`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800095a8`
- `0x180032a80`

## callees

- `0x180004fc0`
- `0x180005218`
- `0x180007a3c`
- `0x180009190`
- `0x180009258`
- `0x1800097d4`
- `0x18000aa00`
- `0x18000b88c`
- `0x18000be90`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b915`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b958`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b915`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b958`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b8d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b8d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b933`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b933`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b941`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b941`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b90a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b90a`

## string_xrefs

- `0x18000ba0c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v9; // r8d
  const char *v10; // r9
  _BYTE v11[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v12[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v13[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v11);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v11,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v12,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v11);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v11);
    }
  }
  else
  {
    v2 = (void *)*((_QWORD *)lpMem + 1);
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v9, v10);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(lpMem);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x18000b88c  mov     [rsp+arg_0], rbx
0x18000b891  mov     [rsp+arg_8], rsi
0x18000b896  push    rdi
0x18000b897  sub     rsp, 0E0h
0x18000b89e  mov     rbx, rcx
0x18000b8a1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b8a8  jnz     loc_18000B968
0x18000b8ae  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b8b5  test    rax, rax
0x18000b8b8  jz      short loc_18000B8C7
0x18000b8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8bf  test    al, al
0x18000b8c1  jnz     loc_18000B968
0x18000b8c7  mov     rdi, [rbx+8]
0x18000b8cb  xor     r8d, r8d; bAlertable
0x18000b8ce  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b8d1  mov     rcx, rdi; hHandle
0x18000b8d4  call    cs:__imp_WaitForSingleObjectEx
0x18000b8da  cmp     eax, 102h
0x18000b8df  jz      short loc_18000B8EE
0x18000b8e1  test    eax, 0FFFFFF7Fh
0x18000b8e6  jnz     loc_18000BA04
0x18000b8ec  jmp     short loc_18000B8F0
0x18000b8ee  xor     edi, edi
0x18000b8f0  mov     eax, [rbx]
0x18000b8f2  dec     eax
0x18000b8f4  mov     [rbx], eax
0x18000b8f6  mov     eax, [rbx]
0x18000b8f8  test    eax, eax
0x18000b8fa  jnz     short loc_18000B94C
0x18000b8fc  lea     rcx, [rbx+10h]; this
0x18000b900  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000b905  test    rdi, rdi
0x18000b908  jz      short loc_18000B92B
0x18000b90a  call    cs:__imp_GetLastError
0x18000b910  mov     esi, eax
0x18000b912  mov     rcx, rdi; hMutex
0x18000b915  call    cs:__imp_ReleaseMutex
0x18000b91b  test    eax, eax
0x18000b91d  jz      loc_18000B9F1
0x18000b923  mov     ecx, esi; dwErrCode
0x18000b925  call    cs:__imp_SetLastError
0x18000b92b  mov     rcx, rbx
0x18000b92e  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000b933  call    cs:__imp_GetProcessHeap
0x18000b939  mov     rcx, rax; hHeap
0x18000b93c  mov     r8, rbx; lpMem
0x18000b93f  xor     edx, edx; dwFlags
0x18000b941  call    cs:__imp_HeapFree
0x18000b947  jmp     loc_18000B9DC
0x18000b94c  test    rdi, rdi
0x18000b94f  jz      loc_18000B9DC
0x18000b955  mov     rcx, rdi; hMutex
0x18000b958  call    cs:__imp_ReleaseMutex
0x18000b95e  test    eax, eax
0x18000b960  jz      loc_18000BA1E
0x18000b966  jmp     short loc_18000B9DC
0x18000b968  mov     eax, [rbx]
0x18000b96a  dec     eax
0x18000b96c  mov     [rbx], eax
0x18000b96e  mov     eax, [rbx]
0x18000b970  test    eax, eax
0x18000b972  jnz     short loc_18000B9DC
0x18000b974  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000b979  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000b97e  nop
0x18000b97f  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000b983  cmp     byte ptr [rdx+38h], 0
0x18000b987  jz      short loc_18000B993
0x18000b989  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000b98e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000b993  cmp     byte ptr [rbx+0A0h], 0
0x18000b99a  jz      short loc_18000B9AA
0x18000b99c  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000b9a0  lea     rcx, [rsp+0E8h+var_88]; this
0x18000b9a5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000b9aa  cmp     byte ptr [rbx+0E0h], 0
0x18000b9b1  jz      short loc_18000B9C7
0x18000b9b3  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000b9ba  lea     rcx, [rsp+0E8h+var_48]; this
0x18000b9c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000b9c7  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000b9cc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000b9d1  nop
0x18000b9d2  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000b9d7  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000b9dc  lea     r11, [rsp+0E8h+var_8]
0x18000b9e4  mov     rbx, [r11+10h]
0x18000b9e8  mov     rsi, [r11+18h]
0x18000b9ec  mov     rsp, r11
0x18000b9ef  pop     rdi
0x18000b9f0  retn
0x18000b9f1  mov     rcx, [rsp+0E8h]; this
0x18000b9f9  mov     edx, 0A15h; void *
0x18000b9fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba04  mov     rcx, [rsp+0E8h]; this
0x18000ba0c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ba13  mov     edx, 0E01h; void *
0x18000ba18  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000ba1e  mov     rcx, [rsp+0E8h]; this
0x18000ba26  mov     edx, 0A15h; void *
0x18000ba2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
