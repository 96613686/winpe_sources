# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000b8d0`
- end: `0x18000ba67`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000835c`
- `0x18000dcc0`

## callees

- `0x180007ffc`
- `0x180008190`
- `0x1800085d4`
- `0x1800090b0`
- `0x1800092e4`
- `0x18000ab1c`
- `0x18000b8d0`
- `0x18000c1a0`
- `0x18000ca4c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b969`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b94e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b918`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b918`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b959`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b99c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b959`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b99c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b985`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b977`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b977`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // esi
  __int64 v8; // r8
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // r8
  const struct wil::details_abi::RawUsageIndex *v14; // r9
  struct wil::details_abi::RawUsageIndex *v15; // rdx
  _BYTE v16[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v17[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v18[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v16);
      v15 = (struct wil::details_abi::RawUsageIndex *)(lpMem + 40);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap((wil::details_abi::RawUsageIndex *)v16, v15);
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v17,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v18,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v16, (__int64)v15, v13, v14);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v16);
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v11, v12);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v8, v9);
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
0x18000b8d0  mov     [rsp+arg_0], rbx
0x18000b8d5  mov     [rsp+arg_8], rsi
0x18000b8da  push    rdi
0x18000b8db  sub     rsp, 0E0h
0x18000b8e2  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b8e9  mov     rbx, rcx
0x18000b8ec  jnz     loc_18000B9AC
0x18000b8f2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b8f9  test    rax, rax
0x18000b8fc  jz      short loc_18000B90B
0x18000b8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b903  test    al, al
0x18000b905  jnz     loc_18000B9AC
0x18000b90b  mov     rdi, [rbx+8]
0x18000b90f  xor     r8d, r8d; bAlertable
0x18000b912  mov     rcx, rdi; hHandle
0x18000b915  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b918  call    cs:__imp_WaitForSingleObjectEx
0x18000b91e  cmp     eax, 102h
0x18000b923  jz      short loc_18000B932
0x18000b925  test    eax, 0FFFFFF7Fh
0x18000b92a  jnz     loc_18000BA46
0x18000b930  jmp     short loc_18000B934
0x18000b932  xor     edi, edi
0x18000b934  mov     eax, [rbx]
0x18000b936  dec     eax
0x18000b938  mov     [rbx], eax
0x18000b93a  mov     eax, [rbx]
0x18000b93c  test    eax, eax
0x18000b93e  jnz     short loc_18000B990
0x18000b940  lea     rcx, [rbx+10h]; this
0x18000b944  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000b949  test    rdi, rdi
0x18000b94c  jz      short loc_18000B96F
0x18000b94e  call    cs:__imp_GetLastError
0x18000b954  mov     rcx, rdi; hMutex
0x18000b957  mov     esi, eax
0x18000b959  call    cs:__imp_ReleaseMutex
0x18000b95f  test    eax, eax
0x18000b961  jz      loc_18000BA33
0x18000b967  mov     ecx, esi; dwErrCode
0x18000b969  call    cs:__imp_SetLastError
0x18000b96f  mov     rcx, rbx
0x18000b972  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000b977  call    cs:__imp_GetProcessHeap
0x18000b97d  mov     r8, rbx; lpMem
0x18000b980  xor     edx, edx; dwFlags
0x18000b982  mov     rcx, rax; hHeap
0x18000b985  call    cs:__imp_HeapFree
0x18000b98b  jmp     loc_18000BA1E
0x18000b990  test    rdi, rdi
0x18000b993  jz      loc_18000BA1E
0x18000b999  mov     rcx, rdi; hMutex
0x18000b99c  call    cs:__imp_ReleaseMutex
0x18000b9a2  test    eax, eax
0x18000b9a4  jz      loc_18000BA54
0x18000b9aa  jmp     short loc_18000BA1E
0x18000b9ac  mov     eax, [rbx]
0x18000b9ae  dec     eax
0x18000b9b0  mov     [rbx], eax
0x18000b9b2  mov     eax, [rbx]
0x18000b9b4  test    eax, eax
0x18000b9b6  jnz     short loc_18000BA1E
0x18000b9b8  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000b9bd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000b9c2  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000b9c6  cmp     byte ptr [rdx+38h], 0
0x18000b9ca  jz      short loc_18000B9D6
0x18000b9cc  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000b9d1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000b9d6  cmp     byte ptr [rbx+0A0h], 0
0x18000b9dd  jz      short loc_18000B9ED
0x18000b9df  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000b9e3  lea     rcx, [rsp+0E8h+var_88]; this
0x18000b9e8  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000b9ed  cmp     byte ptr [rbx+0E0h], 0
0x18000b9f4  jz      short loc_18000BA0A
0x18000b9f6  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000b9fd  lea     rcx, [rsp+0E8h+var_48]; this
0x18000ba05  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000ba0a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ba0f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000ba14  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000ba19  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000ba1e  lea     r11, [rsp+0E8h+var_8]
0x18000ba26  mov     rbx, [r11+10h]
0x18000ba2a  mov     rsi, [r11+18h]
0x18000ba2e  mov     rsp, r11
0x18000ba31  pop     rdi
0x18000ba32  retn
0x18000ba33  mov     rcx, [rsp+0E8h]; this
0x18000ba3b  mov     edx, 0A15h; void *
0x18000ba40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba46  mov     rcx, [rsp+0E8h]; this
0x18000ba4e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000ba54  mov     rcx, [rsp+0E8h]; this
0x18000ba5c  mov     edx, 0A15h; void *
0x18000ba61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
