# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000e24c`
- end: `0x18000e2f8`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c8e0`
- `0x180010090`
- `0x180010e54`
- `0x1800111d0`

## callees

- `0x18000cf30`
- `0x18000e24c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e263`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e2e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e2e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e2c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e2c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2d9`

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
0x18000e24c  push    rbx
0x18000e24e  push    rbp
0x18000e24f  push    rsi
0x18000e250  push    rdi
0x18000e251  sub     rsp, 28h
0x18000e255  cmp     qword ptr [rcx+18h], 0
0x18000e25a  mov     rbx, rcx
0x18000e25d  jnz     loc_18000E2E7
0x18000e263  call    cs:__imp_GetLastError
0x18000e269  cmp     qword ptr [rbx+18h], 0
0x18000e26e  mov     ebp, eax
0x18000e270  jz      short loc_18000E276
0x18000e272  xor     esi, esi
0x18000e274  jmp     short loc_18000E2B9
0x18000e276  cmp     qword ptr [rbx+10h], 0
0x18000e27b  jnz     short loc_18000E2A8
0x18000e27d  mov     rcx, [rbx+8]
0x18000e281  lea     rdx, [rsp+48h+arg_0]
0x18000e286  mov     [rsp+48h+arg_0], 0
0x18000e28f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000e294  test    eax, eax
0x18000e296  js      short loc_18000E2A8
0x18000e298  cmp     qword ptr [rbx+10h], 0
0x18000e29d  jnz     short loc_18000E2A8
0x18000e29f  mov     rax, [rsp+48h+arg_0]
0x18000e2a4  mov     [rbx+10h], rax
0x18000e2a8  mov     rax, [rbx+10h]
0x18000e2ac  lea     rcx, [rax+20h]
0x18000e2b0  neg     rax
0x18000e2b3  sbb     rsi, rsi
0x18000e2b6  and     rsi, rcx
0x18000e2b9  lea     rdi, [rbx+20h]
0x18000e2bd  mov     rcx, rdi; SRWLock
0x18000e2c0  call    cs:__imp_AcquireSRWLockExclusive
0x18000e2c6  cmp     qword ptr [rbx+18h], 0
0x18000e2cb  jnz     short loc_18000E2D1
0x18000e2cd  mov     [rbx+18h], rsi
0x18000e2d1  test    rdi, rdi
0x18000e2d4  jz      short loc_18000E2DF
0x18000e2d6  mov     rcx, rdi; SRWLock
0x18000e2d9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e2df  mov     ecx, ebp; dwErrCode
0x18000e2e1  call    cs:__imp_SetLastError
0x18000e2e7  cmp     qword ptr [rbx+18h], 0
0x18000e2ec  setnz   al
0x18000e2ef  add     rsp, 28h
0x18000e2f3  pop     rdi
0x18000e2f4  pop     rsi
0x18000e2f5  pop     rbp
0x18000e2f6  pop     rbx
0x18000e2f7  retn
```
