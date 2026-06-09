# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x1800072d0`
- end: `0x180007467`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180003d5c`
- `0x18000c110`

## callees

- `0x1800039fc`
- `0x180003b90`
- `0x180003fd4`
- `0x180004ab0`
- `0x180004ce4`
- `0x18000651c`
- `0x1800072d0`
- `0x180007ba0`
- `0x18000844c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007359`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000739c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007359`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000739c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007318`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007318`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007377`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007377`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007385`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000734e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000734e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007369`

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
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  _BYTE v13[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v15[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v13);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v13);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v13);
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
0x1800072d0  mov     [rsp+arg_0], rbx
0x1800072d5  mov     [rsp+arg_8], rsi
0x1800072da  push    rdi
0x1800072db  sub     rsp, 0E0h
0x1800072e2  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800072e9  mov     rbx, rcx
0x1800072ec  jnz     loc_1800073AC
0x1800072f2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800072f9  test    rax, rax
0x1800072fc  jz      short loc_18000730B
0x1800072fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007303  test    al, al
0x180007305  jnz     loc_1800073AC
0x18000730b  mov     rdi, [rbx+8]
0x18000730f  xor     r8d, r8d; bAlertable
0x180007312  mov     rcx, rdi; hHandle
0x180007315  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007318  call    cs:__imp_WaitForSingleObjectEx
0x18000731e  cmp     eax, 102h
0x180007323  jz      short loc_180007332
0x180007325  test    eax, 0FFFFFF7Fh
0x18000732a  jnz     loc_180007446
0x180007330  jmp     short loc_180007334
0x180007332  xor     edi, edi
0x180007334  mov     eax, [rbx]
0x180007336  dec     eax
0x180007338  mov     [rbx], eax
0x18000733a  mov     eax, [rbx]
0x18000733c  test    eax, eax
0x18000733e  jnz     short loc_180007390
0x180007340  lea     rcx, [rbx+10h]; this
0x180007344  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180007349  test    rdi, rdi
0x18000734c  jz      short loc_18000736F
0x18000734e  call    cs:__imp_GetLastError
0x180007354  mov     rcx, rdi; hMutex
0x180007357  mov     esi, eax
0x180007359  call    cs:__imp_ReleaseMutex
0x18000735f  test    eax, eax
0x180007361  jz      loc_180007433
0x180007367  mov     ecx, esi; dwErrCode
0x180007369  call    cs:__imp_SetLastError
0x18000736f  mov     rcx, rbx
0x180007372  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180007377  call    cs:__imp_GetProcessHeap
0x18000737d  mov     r8, rbx; lpMem
0x180007380  xor     edx, edx; dwFlags
0x180007382  mov     rcx, rax; hHeap
0x180007385  call    cs:__imp_HeapFree
0x18000738b  jmp     loc_18000741E
0x180007390  test    rdi, rdi
0x180007393  jz      loc_18000741E
0x180007399  mov     rcx, rdi; hMutex
0x18000739c  call    cs:__imp_ReleaseMutex
0x1800073a2  test    eax, eax
0x1800073a4  jz      loc_180007454
0x1800073aa  jmp     short loc_18000741E
0x1800073ac  mov     eax, [rbx]
0x1800073ae  dec     eax
0x1800073b0  mov     [rbx], eax
0x1800073b2  mov     eax, [rbx]
0x1800073b4  test    eax, eax
0x1800073b6  jnz     short loc_18000741E
0x1800073b8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073bd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800073c2  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x1800073c6  cmp     byte ptr [rdx+38h], 0
0x1800073ca  jz      short loc_1800073D6
0x1800073cc  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800073d1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073d6  cmp     byte ptr [rbx+0A0h], 0
0x1800073dd  jz      short loc_1800073ED
0x1800073df  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x1800073e3  lea     rcx, [rsp+0E8h+var_88]; this
0x1800073e8  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800073ed  cmp     byte ptr [rbx+0E0h], 0
0x1800073f4  jz      short loc_18000740A
0x1800073f6  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x1800073fd  lea     rcx, [rsp+0E8h+var_48]; this
0x180007405  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000740a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000740f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180007414  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007419  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000741e  lea     r11, [rsp+0E8h+var_8]
0x180007426  mov     rbx, [r11+10h]
0x18000742a  mov     rsi, [r11+18h]
0x18000742e  mov     rsp, r11
0x180007431  pop     rdi
0x180007432  retn
0x180007433  mov     rcx, [rsp+0E8h]; this
0x18000743b  mov     edx, 0A15h; void *
0x180007440  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007446  mov     rcx, [rsp+0E8h]; this
0x18000744e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007454  mov     rcx, [rsp+0E8h]; this
0x18000745c  mov     edx, 0A15h; void *
0x180007461  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
