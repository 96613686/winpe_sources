# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000a258`
- end: `0x18000a3fd`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180006740`
- `0x180060650`

## callees

- `0x180006224`
- `0x1800063f0`
- `0x180006adc`
- `0x180007710`
- `0x180007a5c`
- `0x180009230`
- `0x18000a258`
- `0x18000b434`
- `0x18000be2c`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a324`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a2e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a324`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a2a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a2a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a30d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a30d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a2f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2d6`

## string_xrefs

- `0x18000a3d8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      wil::details::in1diag3::_FailFast_Unexpected(
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
0x18000a258  mov     [rsp+arg_0], rbx
0x18000a25d  mov     [rsp+arg_8], rsi
0x18000a262  push    rdi
0x18000a263  sub     rsp, 0E0h
0x18000a26a  mov     rbx, rcx
0x18000a26d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a274  jnz     loc_18000A334
0x18000a27a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a281  test    rax, rax
0x18000a284  jz      short loc_18000A293
0x18000a286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28b  test    al, al
0x18000a28d  jnz     loc_18000A334
0x18000a293  mov     rdi, [rbx+8]
0x18000a297  xor     r8d, r8d; bAlertable
0x18000a29a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a29d  mov     rcx, rdi; hHandle
0x18000a2a0  call    cs:__imp_WaitForSingleObjectEx
0x18000a2a6  cmp     eax, 102h
0x18000a2ab  jz      short loc_18000A2BA
0x18000a2ad  test    eax, 0FFFFFF7Fh
0x18000a2b2  jnz     loc_18000A3D0
0x18000a2b8  jmp     short loc_18000A2BC
0x18000a2ba  xor     edi, edi
0x18000a2bc  mov     eax, [rbx]
0x18000a2be  dec     eax
0x18000a2c0  mov     [rbx], eax
0x18000a2c2  mov     eax, [rbx]
0x18000a2c4  test    eax, eax
0x18000a2c6  jnz     short loc_18000A318
0x18000a2c8  lea     rcx, [rbx+10h]; this
0x18000a2cc  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a2d1  test    rdi, rdi
0x18000a2d4  jz      short loc_18000A2F7
0x18000a2d6  call    cs:__imp_GetLastError
0x18000a2dc  mov     esi, eax
0x18000a2de  mov     rcx, rdi; hMutex
0x18000a2e1  call    cs:__imp_ReleaseMutex
0x18000a2e7  test    eax, eax
0x18000a2e9  jz      loc_18000A3BD
0x18000a2ef  mov     ecx, esi; dwErrCode
0x18000a2f1  call    cs:__imp_SetLastError
0x18000a2f7  mov     rcx, rbx
0x18000a2fa  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000a2ff  call    cs:__imp_GetProcessHeap
0x18000a305  mov     rcx, rax; hHeap
0x18000a308  mov     r8, rbx; lpMem
0x18000a30b  xor     edx, edx; dwFlags
0x18000a30d  call    cs:__imp_HeapFree
0x18000a313  jmp     loc_18000A3A8
0x18000a318  test    rdi, rdi
0x18000a31b  jz      loc_18000A3A8
0x18000a321  mov     rcx, rdi; hMutex
0x18000a324  call    cs:__imp_ReleaseMutex
0x18000a32a  test    eax, eax
0x18000a32c  jz      loc_18000A3EA
0x18000a332  jmp     short loc_18000A3A8
0x18000a334  mov     eax, [rbx]
0x18000a336  dec     eax
0x18000a338  mov     [rbx], eax
0x18000a33a  mov     eax, [rbx]
0x18000a33c  test    eax, eax
0x18000a33e  jnz     short loc_18000A3A8
0x18000a340  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a345  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a34a  nop
0x18000a34b  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000a34f  cmp     byte ptr [rdx+38h], 0
0x18000a353  jz      short loc_18000A35F
0x18000a355  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a35a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a35f  cmp     byte ptr [rbx+0A0h], 0
0x18000a366  jz      short loc_18000A376
0x18000a368  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000a36c  lea     rcx, [rsp+0E8h+var_88]; this
0x18000a371  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a376  cmp     byte ptr [rbx+0E0h], 0
0x18000a37d  jz      short loc_18000A393
0x18000a37f  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000a386  lea     rcx, [rsp+0E8h+var_48]; this
0x18000a38e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a393  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a398  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a39d  nop
0x18000a39e  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a3a3  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a3a8  lea     r11, [rsp+0E8h+var_8]
0x18000a3b0  mov     rbx, [r11+10h]
0x18000a3b4  mov     rsi, [r11+18h]
0x18000a3b8  mov     rsp, r11
0x18000a3bb  pop     rdi
0x18000a3bc  retn
0x18000a3bd  mov     rcx, [rsp+0E8h]; this
0x18000a3c5  mov     edx, 0A15h; void *
0x18000a3ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a3d0  mov     rcx, [rsp+0E8h]; this
0x18000a3d8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a3df  mov     edx, 0E01h; void *
0x18000a3e4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a3ea  mov     rcx, [rsp+0E8h]; this
0x18000a3f2  mov     edx, 0A15h; void *
0x18000a3f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
