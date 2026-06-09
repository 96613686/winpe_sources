# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180015d6c`
- end: `0x180015f4b`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `479`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000e1a4`
- `0x180036cb0`

## callees

- `0x1800051f0`
- `0x180005b08`
- `0x180005bb8`
- `0x18000864c`
- `0x18000d034`
- `0x18000e0cc`
- `0x18000e700`
- `0x180014f28`
- `0x180015d6c`
- `0x18001b2c0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015def`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015e53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015def`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015e53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015dae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015dae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015de4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015dff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015dff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015e20`

## string_xrefs

- `0x180015eeb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180015f05`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180015f1f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180015f39`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // ebp
  const char *v6; // r9
  void *v7; // rcx
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  const char *v10; // r9
  _BYTE v11[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v12[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v13[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v10);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v6);
        SetLastError(LastError);
      }
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v7 = (void *)*((_QWORD *)lpMem + 1);
      if ( v7 )
      {
        if ( !CloseHandle(v7) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v8);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x180015d6c  push    rbx
0x180015d6e  push    rbp
0x180015d6f  push    rsi
0x180015d70  push    rdi
0x180015d71  sub     rsp, 0E8h
0x180015d78  mov     rbx, rcx
0x180015d7b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180015d82  jnz     loc_180015E63
0x180015d88  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180015d8f  test    rax, rax
0x180015d92  jz      short loc_180015DA1
0x180015d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d99  test    al, al
0x180015d9b  jnz     loc_180015E63
0x180015da1  mov     rdi, [rbx+8]
0x180015da5  xor     r8d, r8d; bAlertable
0x180015da8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015dab  mov     rcx, rdi; hHandle
0x180015dae  call    cs:__imp_WaitForSingleObjectEx
0x180015db4  cmp     eax, 102h
0x180015db9  jz      short loc_180015DC8
0x180015dbb  test    eax, 0FFFFFF7Fh
0x180015dc0  jnz     loc_180015EFD
0x180015dc6  jmp     short loc_180015DCA
0x180015dc8  xor     edi, edi
0x180015dca  mov     eax, [rbx]
0x180015dcc  dec     eax
0x180015dce  mov     [rbx], eax
0x180015dd0  mov     eax, [rbx]
0x180015dd2  test    eax, eax
0x180015dd4  jnz     short loc_180015E47
0x180015dd6  lea     rcx, [rbx+10h]; this
0x180015dda  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180015ddf  test    rdi, rdi
0x180015de2  jz      short loc_180015E05
0x180015de4  call    cs:__imp_GetLastError
0x180015dea  mov     ebp, eax
0x180015dec  mov     rcx, rdi; hMutex
0x180015def  call    cs:__imp_ReleaseMutex
0x180015df5  test    eax, eax
0x180015df7  jz      loc_180015F31
0x180015dfd  mov     ecx, ebp; dwErrCode
0x180015dff  call    cs:__imp_SetLastError
0x180015e05  lea     rcx, [rbx+20h]; this
0x180015e09  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x180015e0e  lea     rcx, [rbx+10h]; this
0x180015e12  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180015e17  mov     rcx, [rbx+8]; hObject
0x180015e1b  test    rcx, rcx
0x180015e1e  jz      short loc_180015E2E
0x180015e20  call    cs:__imp_CloseHandle
0x180015e26  test    eax, eax
0x180015e28  jz      loc_180015EE3
0x180015e2e  call    cs:__imp_GetProcessHeap
0x180015e34  mov     rcx, rax; hHeap
0x180015e37  mov     r8, rbx; lpMem
0x180015e3a  xor     edx, edx; dwFlags
0x180015e3c  call    cs:__imp_HeapFree
0x180015e42  jmp     loc_180015ED7
0x180015e47  test    rdi, rdi
0x180015e4a  jz      loc_180015ED7
0x180015e50  mov     rcx, rdi; hMutex
0x180015e53  call    cs:__imp_ReleaseMutex
0x180015e59  test    eax, eax
0x180015e5b  jz      loc_180015F17
0x180015e61  jmp     short loc_180015ED7
0x180015e63  mov     eax, [rbx]
0x180015e65  dec     eax
0x180015e67  mov     [rbx], eax
0x180015e69  mov     eax, [rbx]
0x180015e6b  test    eax, eax
0x180015e6d  jnz     short loc_180015ED7
0x180015e6f  lea     rcx, [rsp+108h+var_E8]; this
0x180015e74  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180015e79  nop
0x180015e7a  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180015e7e  cmp     byte ptr [rdx+38h], 0
0x180015e82  jz      short loc_180015E8E
0x180015e84  lea     rcx, [rsp+108h+var_E8]; this
0x180015e89  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180015e8e  cmp     byte ptr [rbx+0A0h], 0
0x180015e95  jz      short loc_180015EA5
0x180015e97  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180015e9b  lea     rcx, [rsp+108h+var_A8]; this
0x180015ea0  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180015ea5  cmp     byte ptr [rbx+0E0h], 0
0x180015eac  jz      short loc_180015EC2
0x180015eae  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180015eb5  lea     rcx, [rsp+108h+var_68]; this
0x180015ebd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180015ec2  lea     rcx, [rsp+108h+var_E8]; this
0x180015ec7  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180015ecc  nop
0x180015ecd  lea     rcx, [rsp+108h+var_E8]; this
0x180015ed2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180015ed7  add     rsp, 0E8h
0x180015ede  pop     rdi
0x180015edf  pop     rsi
0x180015ee0  pop     rbp
0x180015ee1  pop     rbx
0x180015ee2  retn
0x180015ee3  mov     rcx, [rsp+108h]; this
0x180015eeb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015ef2  mov     edx, 0A0Bh; void *
0x180015ef7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015efd  mov     rcx, [rsp+108h]; this
0x180015f05  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015f0c  mov     edx, 0E01h; void *
0x180015f11  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015f17  mov     rcx, [rsp+108h]; this
0x180015f1f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015f26  mov     edx, 0A15h; void *
0x180015f2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015f31  mov     rcx, [rsp+108h]; this
0x180015f39  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015f40  mov     edx, 0A15h; void *
0x180015f45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
