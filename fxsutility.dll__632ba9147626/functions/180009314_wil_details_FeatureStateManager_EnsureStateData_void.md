# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180009314`
- end: `0x1800093c0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007450`
- `0x18000ad74`
- `0x18000c458`
- `0x18000ca10`

## callees

- `0x180008bcc`
- `0x180009314`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800093a9`
- `KERNEL32!SetLastError` at `0x1800093a9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800093a1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800093a1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009388`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009388`
- `KERNEL32!GetLastError` at `0x18000932b`
- `KERNEL32!GetLastError` at `0x18000932b`

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
0x180009314  push    rbx
0x180009316  push    rbp
0x180009317  push    rsi
0x180009318  push    rdi
0x180009319  sub     rsp, 28h
0x18000931d  cmp     qword ptr [rcx+18h], 0
0x180009322  mov     rbx, rcx
0x180009325  jnz     loc_1800093AF
0x18000932b  call    cs:__imp_GetLastError
0x180009331  cmp     qword ptr [rbx+18h], 0
0x180009336  mov     ebp, eax
0x180009338  jz      short loc_18000933E
0x18000933a  xor     esi, esi
0x18000933c  jmp     short loc_180009381
0x18000933e  cmp     qword ptr [rbx+10h], 0
0x180009343  jnz     short loc_180009370
0x180009345  mov     rcx, [rbx+8]
0x180009349  lea     rdx, [rsp+48h+arg_0]
0x18000934e  mov     [rsp+48h+arg_0], 0
0x180009357  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000935c  test    eax, eax
0x18000935e  js      short loc_180009370
0x180009360  cmp     qword ptr [rbx+10h], 0
0x180009365  jnz     short loc_180009370
0x180009367  mov     rax, [rsp+48h+arg_0]
0x18000936c  mov     [rbx+10h], rax
0x180009370  mov     rax, [rbx+10h]
0x180009374  lea     rcx, [rax+20h]
0x180009378  neg     rax
0x18000937b  sbb     rsi, rsi
0x18000937e  and     rsi, rcx
0x180009381  lea     rdi, [rbx+20h]
0x180009385  mov     rcx, rdi; SRWLock
0x180009388  call    cs:__imp_AcquireSRWLockExclusive
0x18000938e  cmp     qword ptr [rbx+18h], 0
0x180009393  jnz     short loc_180009399
0x180009395  mov     [rbx+18h], rsi
0x180009399  test    rdi, rdi
0x18000939c  jz      short loc_1800093A7
0x18000939e  mov     rcx, rdi; SRWLock
0x1800093a1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800093a7  mov     ecx, ebp; dwErrCode
0x1800093a9  call    cs:__imp_SetLastError
0x1800093af  cmp     qword ptr [rbx+18h], 0
0x1800093b4  setnz   al
0x1800093b7  add     rsp, 28h
0x1800093bb  pop     rdi
0x1800093bc  pop     rsi
0x1800093bd  pop     rbp
0x1800093be  pop     rbx
0x1800093bf  retn
```
