# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004ee4`
- end: `0x180004f90`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002de0`
- `0x180006fa4`
- `0x180009244`
- `0x180009bf0`

## callees

- `0x1800047e8`
- `0x180004ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004efb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f58`

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
0x180004ee4  push    rbx
0x180004ee6  push    rbp
0x180004ee7  push    rsi
0x180004ee8  push    rdi
0x180004ee9  sub     rsp, 28h
0x180004eed  cmp     qword ptr [rcx+18h], 0
0x180004ef2  mov     rbx, rcx
0x180004ef5  jnz     loc_180004F7F
0x180004efb  call    cs:__imp_GetLastError
0x180004f01  cmp     qword ptr [rbx+18h], 0
0x180004f06  mov     ebp, eax
0x180004f08  jz      short loc_180004F0E
0x180004f0a  xor     esi, esi
0x180004f0c  jmp     short loc_180004F51
0x180004f0e  cmp     qword ptr [rbx+10h], 0
0x180004f13  jnz     short loc_180004F40
0x180004f15  mov     rcx, [rbx+8]
0x180004f19  lea     rdx, [rsp+48h+arg_0]
0x180004f1e  mov     [rsp+48h+arg_0], 0
0x180004f27  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004f2c  test    eax, eax
0x180004f2e  js      short loc_180004F40
0x180004f30  cmp     qword ptr [rbx+10h], 0
0x180004f35  jnz     short loc_180004F40
0x180004f37  mov     rax, [rsp+48h+arg_0]
0x180004f3c  mov     [rbx+10h], rax
0x180004f40  mov     rax, [rbx+10h]
0x180004f44  lea     rcx, [rax+20h]
0x180004f48  neg     rax
0x180004f4b  sbb     rsi, rsi
0x180004f4e  and     rsi, rcx
0x180004f51  lea     rdi, [rbx+20h]
0x180004f55  mov     rcx, rdi; SRWLock
0x180004f58  call    cs:__imp_AcquireSRWLockExclusive
0x180004f5e  cmp     qword ptr [rbx+18h], 0
0x180004f63  jnz     short loc_180004F69
0x180004f65  mov     [rbx+18h], rsi
0x180004f69  test    rdi, rdi
0x180004f6c  jz      short loc_180004F77
0x180004f6e  mov     rcx, rdi; SRWLock
0x180004f71  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f77  mov     ecx, ebp; dwErrCode
0x180004f79  call    cs:__imp_SetLastError
0x180004f7f  cmp     qword ptr [rbx+18h], 0
0x180004f84  setnz   al
0x180004f87  add     rsp, 28h
0x180004f8b  pop     rdi
0x180004f8c  pop     rsi
0x180004f8d  pop     rbp
0x180004f8e  pop     rbx
0x180004f8f  retn
```
