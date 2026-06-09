# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800059d4`
- end: `0x180005a80`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ac0`
- `0x1800086f4`
- `0x180009a44`
- `0x18000a030`

## callees

- `0x1800050c0`
- `0x1800059d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005a48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005a48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005a61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005a61`

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
0x1800059d4  push    rbx
0x1800059d6  push    rbp
0x1800059d7  push    rsi
0x1800059d8  push    rdi
0x1800059d9  sub     rsp, 28h
0x1800059dd  cmp     qword ptr [rcx+18h], 0
0x1800059e2  mov     rbx, rcx
0x1800059e5  jnz     loc_180005A6F
0x1800059eb  call    cs:__imp_GetLastError
0x1800059f1  cmp     qword ptr [rbx+18h], 0
0x1800059f6  mov     ebp, eax
0x1800059f8  jz      short loc_1800059FE
0x1800059fa  xor     esi, esi
0x1800059fc  jmp     short loc_180005A41
0x1800059fe  cmp     qword ptr [rbx+10h], 0
0x180005a03  jnz     short loc_180005A30
0x180005a05  mov     rcx, [rbx+8]
0x180005a09  lea     rdx, [rsp+48h+arg_0]
0x180005a0e  mov     [rsp+48h+arg_0], 0
0x180005a17  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180005a1c  test    eax, eax
0x180005a1e  js      short loc_180005A30
0x180005a20  cmp     qword ptr [rbx+10h], 0
0x180005a25  jnz     short loc_180005A30
0x180005a27  mov     rax, [rsp+48h+arg_0]
0x180005a2c  mov     [rbx+10h], rax
0x180005a30  mov     rax, [rbx+10h]
0x180005a34  lea     rcx, [rax+20h]
0x180005a38  neg     rax
0x180005a3b  sbb     rsi, rsi
0x180005a3e  and     rsi, rcx
0x180005a41  lea     rdi, [rbx+20h]
0x180005a45  mov     rcx, rdi; SRWLock
0x180005a48  call    cs:__imp_AcquireSRWLockExclusive
0x180005a4e  cmp     qword ptr [rbx+18h], 0
0x180005a53  jnz     short loc_180005A59
0x180005a55  mov     [rbx+18h], rsi
0x180005a59  test    rdi, rdi
0x180005a5c  jz      short loc_180005A67
0x180005a5e  mov     rcx, rdi; SRWLock
0x180005a61  call    cs:__imp_ReleaseSRWLockExclusive
0x180005a67  mov     ecx, ebp; dwErrCode
0x180005a69  call    cs:__imp_SetLastError
0x180005a6f  cmp     qword ptr [rbx+18h], 0
0x180005a74  setnz   al
0x180005a77  add     rsp, 28h
0x180005a7b  pop     rdi
0x180005a7c  pop     rsi
0x180005a7d  pop     rbp
0x180005a7e  pop     rbx
0x180005a7f  retn
```
