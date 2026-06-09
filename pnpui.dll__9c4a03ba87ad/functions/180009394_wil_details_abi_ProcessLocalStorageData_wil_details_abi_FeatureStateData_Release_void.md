# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180009394`
- end: `0x18000952b`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000496c`
- `0x18000d260`

## callees

- `0x1800044c0`
- `0x180004654`
- `0x180004be4`
- `0x180005930`
- `0x180005c30`
- `0x1800083f8`
- `0x180009394`
- `0x180009bf8`
- `0x18000a57c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000942d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000942d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009412`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800093dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800093dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000941d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009460`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000941d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009460`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000943b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000943b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009449`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009449`

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
0x180009394  mov     [rsp+arg_0], rbx
0x180009399  mov     [rsp+arg_8], rsi
0x18000939e  push    rdi
0x18000939f  sub     rsp, 0E0h
0x1800093a6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800093ad  mov     rbx, rcx
0x1800093b0  jnz     loc_180009470
0x1800093b6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800093bd  test    rax, rax
0x1800093c0  jz      short loc_1800093CF
0x1800093c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c7  test    al, al
0x1800093c9  jnz     loc_180009470
0x1800093cf  mov     rdi, [rbx+8]
0x1800093d3  xor     r8d, r8d; bAlertable
0x1800093d6  mov     rcx, rdi; hHandle
0x1800093d9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800093dc  call    cs:__imp_WaitForSingleObjectEx
0x1800093e2  cmp     eax, 102h
0x1800093e7  jz      short loc_1800093F6
0x1800093e9  test    eax, 0FFFFFF7Fh
0x1800093ee  jnz     loc_18000950A
0x1800093f4  jmp     short loc_1800093F8
0x1800093f6  xor     edi, edi
0x1800093f8  mov     eax, [rbx]
0x1800093fa  dec     eax
0x1800093fc  mov     [rbx], eax
0x1800093fe  mov     eax, [rbx]
0x180009400  test    eax, eax
0x180009402  jnz     short loc_180009454
0x180009404  lea     rcx, [rbx+10h]; this
0x180009408  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000940d  test    rdi, rdi
0x180009410  jz      short loc_180009433
0x180009412  call    cs:__imp_GetLastError
0x180009418  mov     rcx, rdi; hMutex
0x18000941b  mov     esi, eax
0x18000941d  call    cs:__imp_ReleaseMutex
0x180009423  test    eax, eax
0x180009425  jz      loc_1800094F7
0x18000942b  mov     ecx, esi; dwErrCode
0x18000942d  call    cs:__imp_SetLastError
0x180009433  mov     rcx, rbx
0x180009436  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000943b  call    cs:__imp_GetProcessHeap
0x180009441  mov     r8, rbx; lpMem
0x180009444  xor     edx, edx; dwFlags
0x180009446  mov     rcx, rax; hHeap
0x180009449  call    cs:__imp_HeapFree
0x18000944f  jmp     loc_1800094E2
0x180009454  test    rdi, rdi
0x180009457  jz      loc_1800094E2
0x18000945d  mov     rcx, rdi; hMutex
0x180009460  call    cs:__imp_ReleaseMutex
0x180009466  test    eax, eax
0x180009468  jz      loc_180009518
0x18000946e  jmp     short loc_1800094E2
0x180009470  mov     eax, [rbx]
0x180009472  dec     eax
0x180009474  mov     [rbx], eax
0x180009476  mov     eax, [rbx]
0x180009478  test    eax, eax
0x18000947a  jnz     short loc_1800094E2
0x18000947c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009481  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009486  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000948a  cmp     byte ptr [rdx+38h], 0
0x18000948e  jz      short loc_18000949A
0x180009490  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009495  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000949a  cmp     byte ptr [rbx+0A0h], 0
0x1800094a1  jz      short loc_1800094B1
0x1800094a3  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x1800094a7  lea     rcx, [rsp+0E8h+var_88]; this
0x1800094ac  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094b1  cmp     byte ptr [rbx+0E0h], 0
0x1800094b8  jz      short loc_1800094CE
0x1800094ba  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x1800094c1  lea     rcx, [rsp+0E8h+var_48]; this
0x1800094c9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094ce  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094d3  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800094d8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094dd  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800094e2  lea     r11, [rsp+0E8h+var_8]
0x1800094ea  mov     rbx, [r11+10h]
0x1800094ee  mov     rsi, [r11+18h]
0x1800094f2  mov     rsp, r11
0x1800094f5  pop     rdi
0x1800094f6  retn
0x1800094f7  mov     rcx, [rsp+0E8h]; this
0x1800094ff  mov     edx, 0A15h; void *
0x180009504  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000950a  mov     rcx, [rsp+0E8h]; this
0x180009512  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009518  mov     rcx, [rsp+0E8h]; this
0x180009520  mov     edx, 0A15h; void *
0x180009525  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
