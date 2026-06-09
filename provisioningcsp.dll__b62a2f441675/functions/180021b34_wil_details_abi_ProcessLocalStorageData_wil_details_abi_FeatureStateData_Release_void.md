# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180021b34`
- end: `0x180021d33`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `511`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180013e98`
- `0x180037ad0`

## callees

- `0x180004988`
- `0x1800051a4`
- `0x18000526c`
- `0x180007834`
- `0x180013c58`
- `0x180013db0`
- `0x1800140a8`
- `0x180020ecc`
- `0x180021b34`
- `0x180022400`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021bdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021bdd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021b76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180021b76`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021bc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021c49`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021bc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180021c49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021c2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021c2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021c18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021c18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c04`

## string_xrefs

- `0x180021cfb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // ebp
  unsigned int v6; // r8d
  const char *v7; // r9
  void *v8; // rcx
  unsigned int v9; // r8d
  const char *v10; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  _BYTE v14[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v15[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v16[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v14);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v16,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v14);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v14);
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v12, v13);
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
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v8 = (void *)*((_QWORD *)lpMem + 1);
      if ( v8 )
      {
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x180021b34  push    rbx
0x180021b36  push    rbp
0x180021b37  push    rsi
0x180021b38  push    rdi
0x180021b39  sub     rsp, 0E8h
0x180021b40  mov     rbx, rcx
0x180021b43  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180021b4a  jnz     loc_180021C5F
0x180021b50  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180021b57  test    rax, rax
0x180021b5a  jz      short loc_180021B69
0x180021b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b61  test    al, al
0x180021b63  jnz     loc_180021C5F
0x180021b69  mov     rdi, [rbx+8]
0x180021b6d  xor     r8d, r8d; bAlertable
0x180021b70  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021b73  mov     rcx, rdi; hHandle
0x180021b76  call    cs:__imp_WaitForSingleObjectEx
0x180021b7d  nop     dword ptr [rax+rax+00h]
0x180021b82  cmp     eax, 102h
0x180021b87  jz      short loc_180021B96
0x180021b89  test    eax, 0FFFFFF7Fh
0x180021b8e  jnz     loc_180021CF3
0x180021b94  jmp     short loc_180021B98
0x180021b96  xor     edi, edi
0x180021b98  mov     eax, [rbx]
0x180021b9a  dec     eax
0x180021b9c  mov     [rbx], eax
0x180021b9e  mov     eax, [rbx]
0x180021ba0  test    eax, eax
0x180021ba2  jnz     loc_180021C3D
0x180021ba8  lea     rcx, [rbx+10h]; this
0x180021bac  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180021bb1  test    rdi, rdi
0x180021bb4  jz      short loc_180021BE9
0x180021bb6  call    cs:__imp_GetLastError
0x180021bbd  nop     dword ptr [rax+rax+00h]
0x180021bc2  mov     ebp, eax
0x180021bc4  mov     rcx, rdi; hMutex
0x180021bc7  call    cs:__imp_ReleaseMutex
0x180021bce  nop     dword ptr [rax+rax+00h]
0x180021bd3  test    eax, eax
0x180021bd5  jz      loc_180021D20
0x180021bdb  mov     ecx, ebp; dwErrCode
0x180021bdd  call    cs:__imp_SetLastError
0x180021be4  nop     dword ptr [rax+rax+00h]
0x180021be9  lea     rcx, [rbx+20h]; this
0x180021bed  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x180021bf2  lea     rcx, [rbx+10h]; this
0x180021bf6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180021bfb  mov     rcx, [rbx+8]; hObject
0x180021bff  test    rcx, rcx
0x180021c02  jz      short loc_180021C18
0x180021c04  call    cs:__imp_CloseHandle
0x180021c0b  nop     dword ptr [rax+rax+00h]
0x180021c10  test    eax, eax
0x180021c12  jz      loc_180021CE0
0x180021c18  call    cs:__imp_GetProcessHeap
0x180021c1f  nop     dword ptr [rax+rax+00h]
0x180021c24  mov     rcx, rax; hHeap
0x180021c27  mov     r8, rbx; lpMem
0x180021c2a  xor     edx, edx; dwFlags
0x180021c2c  call    cs:__imp_HeapFree
0x180021c33  nop     dword ptr [rax+rax+00h]
0x180021c38  jmp     loc_180021CD3
0x180021c3d  test    rdi, rdi
0x180021c40  jz      loc_180021CD3
0x180021c46  mov     rcx, rdi; hMutex
0x180021c49  call    cs:__imp_ReleaseMutex
0x180021c50  nop     dword ptr [rax+rax+00h]
0x180021c55  test    eax, eax
0x180021c57  jz      loc_180021D0D
0x180021c5d  jmp     short loc_180021CD3
0x180021c5f  mov     eax, [rbx]
0x180021c61  dec     eax
0x180021c63  mov     [rbx], eax
0x180021c65  mov     eax, [rbx]
0x180021c67  test    eax, eax
0x180021c69  jnz     short loc_180021CD3
0x180021c6b  lea     rcx, [rsp+108h+var_E8]; this
0x180021c70  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180021c75  nop
0x180021c76  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180021c7a  cmp     byte ptr [rdx+38h], 0
0x180021c7e  jz      short loc_180021C8A
0x180021c80  lea     rcx, [rsp+108h+var_E8]; this
0x180021c85  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180021c8a  cmp     byte ptr [rbx+0A0h], 0
0x180021c91  jz      short loc_180021CA1
0x180021c93  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180021c97  lea     rcx, [rsp+108h+var_A8]; this
0x180021c9c  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180021ca1  cmp     byte ptr [rbx+0E0h], 0
0x180021ca8  jz      short loc_180021CBE
0x180021caa  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180021cb1  lea     rcx, [rsp+108h+var_68]; this
0x180021cb9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180021cbe  lea     rcx, [rsp+108h+var_E8]; this
0x180021cc3  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180021cc8  nop
0x180021cc9  lea     rcx, [rsp+108h+var_E8]; this
0x180021cce  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180021cd3  add     rsp, 0E8h
0x180021cda  pop     rdi
0x180021cdb  pop     rsi
0x180021cdc  pop     rbp
0x180021cdd  pop     rbx
0x180021cde  retn
0x180021ce0  mov     rcx, [rsp+108h]; this
0x180021ce8  mov     edx, 0A0Bh; void *
0x180021ced  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021cf3  mov     rcx, [rsp+108h]; this
0x180021cfb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021d02  mov     edx, 0E01h; void *
0x180021d07  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180021d0d  mov     rcx, [rsp+108h]; this
0x180021d15  mov     edx, 0A15h; void *
0x180021d1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180021d20  mov     rcx, [rsp+108h]; this
0x180021d28  mov     edx, 0A15h; void *
0x180021d2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
