# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18001c5d8`
- end: `0x18001c77d`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180010fe0`
- `0x180046d50`

## callees

- `0x180008320`
- `0x1800083c4`
- `0x18000ad18`
- `0x18000fbfc`
- `0x18000fe14`
- `0x18001150c`
- `0x18001b998`
- `0x18001c5d8`
- `0x1800200c0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c67f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c67f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c68d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c68d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c661`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c6a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c661`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c6a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c620`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c620`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c671`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c656`

## string_xrefs

- `0x18001c758`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  __int64 v6; // r8
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  __int64 v9; // r8
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
0x18001c5d8  mov     [rsp+arg_0], rbx
0x18001c5dd  mov     [rsp+arg_8], rsi
0x18001c5e2  push    rdi
0x18001c5e3  sub     rsp, 0E0h
0x18001c5ea  mov     rbx, rcx
0x18001c5ed  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c5f4  jnz     loc_18001C6B4
0x18001c5fa  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c601  test    rax, rax
0x18001c604  jz      short loc_18001C613
0x18001c606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c60b  test    al, al
0x18001c60d  jnz     loc_18001C6B4
0x18001c613  mov     rdi, [rbx+8]
0x18001c617  xor     r8d, r8d; bAlertable
0x18001c61a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c61d  mov     rcx, rdi; hHandle
0x18001c620  call    cs:__imp_WaitForSingleObjectEx
0x18001c626  cmp     eax, 102h
0x18001c62b  jz      short loc_18001C63A
0x18001c62d  test    eax, 0FFFFFF7Fh
0x18001c632  jnz     loc_18001C750
0x18001c638  jmp     short loc_18001C63C
0x18001c63a  xor     edi, edi
0x18001c63c  mov     eax, [rbx]
0x18001c63e  dec     eax
0x18001c640  mov     [rbx], eax
0x18001c642  mov     eax, [rbx]
0x18001c644  test    eax, eax
0x18001c646  jnz     short loc_18001C698
0x18001c648  lea     rcx, [rbx+10h]; this
0x18001c64c  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18001c651  test    rdi, rdi
0x18001c654  jz      short loc_18001C677
0x18001c656  call    cs:__imp_GetLastError
0x18001c65c  mov     esi, eax
0x18001c65e  mov     rcx, rdi; hMutex
0x18001c661  call    cs:__imp_ReleaseMutex
0x18001c667  test    eax, eax
0x18001c669  jz      loc_18001C73D
0x18001c66f  mov     ecx, esi; dwErrCode
0x18001c671  call    cs:__imp_SetLastError
0x18001c677  mov     rcx, rbx
0x18001c67a  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18001c67f  call    cs:__imp_GetProcessHeap
0x18001c685  mov     rcx, rax; hHeap
0x18001c688  mov     r8, rbx; lpMem
0x18001c68b  xor     edx, edx; dwFlags
0x18001c68d  call    cs:__imp_HeapFree
0x18001c693  jmp     loc_18001C728
0x18001c698  test    rdi, rdi
0x18001c69b  jz      loc_18001C728
0x18001c6a1  mov     rcx, rdi; hMutex
0x18001c6a4  call    cs:__imp_ReleaseMutex
0x18001c6aa  test    eax, eax
0x18001c6ac  jz      loc_18001C76A
0x18001c6b2  jmp     short loc_18001C728
0x18001c6b4  mov     eax, [rbx]
0x18001c6b6  dec     eax
0x18001c6b8  mov     [rbx], eax
0x18001c6ba  mov     eax, [rbx]
0x18001c6bc  test    eax, eax
0x18001c6be  jnz     short loc_18001C728
0x18001c6c0  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c6c5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001c6ca  nop
0x18001c6cb  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18001c6cf  cmp     byte ptr [rdx+38h], 0
0x18001c6d3  jz      short loc_18001C6DF
0x18001c6d5  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c6da  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001c6df  cmp     byte ptr [rbx+0A0h], 0
0x18001c6e6  jz      short loc_18001C6F6
0x18001c6e8  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18001c6ec  lea     rcx, [rsp+0E8h+var_88]; this
0x18001c6f1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001c6f6  cmp     byte ptr [rbx+0E0h], 0
0x18001c6fd  jz      short loc_18001C713
0x18001c6ff  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18001c706  lea     rcx, [rsp+0E8h+var_48]; this
0x18001c70e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001c713  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c718  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18001c71d  nop
0x18001c71e  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001c723  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001c728  lea     r11, [rsp+0E8h+var_8]
0x18001c730  mov     rbx, [r11+10h]
0x18001c734  mov     rsi, [r11+18h]
0x18001c738  mov     rsp, r11
0x18001c73b  pop     rdi
0x18001c73c  retn
0x18001c73d  mov     rcx, [rsp+0E8h]; this
0x18001c745  mov     edx, 0A15h; void *
0x18001c74a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c750  mov     rcx, [rsp+0E8h]; this
0x18001c758  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c75f  mov     edx, 0E01h; void *
0x18001c764  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001c76a  mov     rcx, [rsp+0E8h]; this
0x18001c772  mov     edx, 0A15h; void *
0x18001c777  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
