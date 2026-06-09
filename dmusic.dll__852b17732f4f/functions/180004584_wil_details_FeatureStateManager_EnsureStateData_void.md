# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004584`
- end: `0x180004630`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002490`
- `0x1800067a4`
- `0x180008324`
- `0x180008980`

## callees

- `0x180003e98`
- `0x180004584`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004611`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000459b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000459b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004619`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 Ptr; // rcx
  void *v6; // [rsp+50h] [rbp+8h] BYREF

  if ( !this[3].Ptr )
  {
    LastError = GetLastError();
    if ( this[3].Ptr )
    {
      v3 = 0;
    }
    else
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(Ptr, &v6) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v6;
        }
      }
      v3 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    }
    AcquireSRWLockExclusive(this + 4);
    if ( !this[3].Ptr )
      this[3].Ptr = (PVOID)v3;
    if ( this != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(this + 4);
    SetLastError(LastError);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x180004584  push    rbx
0x180004586  push    rbp
0x180004587  push    rsi
0x180004588  push    rdi
0x180004589  sub     rsp, 28h
0x18000458d  cmp     qword ptr [rcx+18h], 0
0x180004592  mov     rbx, rcx
0x180004595  jnz     loc_18000461F
0x18000459b  call    cs:__imp_GetLastError
0x1800045a1  cmp     qword ptr [rbx+18h], 0
0x1800045a6  mov     ebp, eax
0x1800045a8  jz      short loc_1800045AE
0x1800045aa  xor     esi, esi
0x1800045ac  jmp     short loc_1800045F1
0x1800045ae  cmp     qword ptr [rbx+10h], 0
0x1800045b3  jnz     short loc_1800045E0
0x1800045b5  mov     rcx, [rbx+8]
0x1800045b9  lea     rdx, [rsp+48h+arg_0]
0x1800045be  mov     [rsp+48h+arg_0], 0
0x1800045c7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800045cc  test    eax, eax
0x1800045ce  js      short loc_1800045E0
0x1800045d0  cmp     qword ptr [rbx+10h], 0
0x1800045d5  jnz     short loc_1800045E0
0x1800045d7  mov     rax, [rsp+48h+arg_0]
0x1800045dc  mov     [rbx+10h], rax
0x1800045e0  mov     rax, [rbx+10h]
0x1800045e4  lea     rcx, [rax+20h]
0x1800045e8  neg     rax
0x1800045eb  sbb     rsi, rsi
0x1800045ee  and     rsi, rcx
0x1800045f1  lea     rdi, [rbx+20h]
0x1800045f5  mov     rcx, rdi; SRWLock
0x1800045f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800045fe  cmp     qword ptr [rbx+18h], 0
0x180004603  jnz     short loc_180004609
0x180004605  mov     [rbx+18h], rsi
0x180004609  test    rdi, rdi
0x18000460c  jz      short loc_180004617
0x18000460e  mov     rcx, rdi; SRWLock
0x180004611  call    cs:__imp_ReleaseSRWLockExclusive
0x180004617  mov     ecx, ebp; dwErrCode
0x180004619  call    cs:__imp_SetLastError
0x18000461f  cmp     qword ptr [rbx+18h], 0
0x180004624  setnz   al
0x180004627  add     rsp, 28h
0x18000462b  pop     rdi
0x18000462c  pop     rsi
0x18000462d  pop     rbp
0x18000462e  pop     rbx
0x18000462f  retn
```
