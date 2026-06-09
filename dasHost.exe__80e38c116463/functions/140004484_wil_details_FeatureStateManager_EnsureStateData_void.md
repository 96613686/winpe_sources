# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140004484`
- end: `0x140004530`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002310`
- `0x140005cf4`
- `0x1400078d8`
- `0x140007ed0`

## callees

- `0x140003da8`
- `0x140004484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400044f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400044f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000449b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000449b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004519`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004519`

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
0x140004484  push    rbx
0x140004486  push    rbp
0x140004487  push    rsi
0x140004488  push    rdi
0x140004489  sub     rsp, 28h
0x14000448d  cmp     qword ptr [rcx+18h], 0
0x140004492  mov     rbx, rcx
0x140004495  jnz     loc_14000451F
0x14000449b  call    cs:__imp_GetLastError
0x1400044a1  cmp     qword ptr [rbx+18h], 0
0x1400044a6  mov     ebp, eax
0x1400044a8  jz      short loc_1400044AE
0x1400044aa  xor     esi, esi
0x1400044ac  jmp     short loc_1400044F1
0x1400044ae  cmp     qword ptr [rbx+10h], 0
0x1400044b3  jnz     short loc_1400044E0
0x1400044b5  mov     rcx, [rbx+8]
0x1400044b9  lea     rdx, [rsp+48h+arg_0]
0x1400044be  mov     [rsp+48h+arg_0], 0
0x1400044c7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400044cc  test    eax, eax
0x1400044ce  js      short loc_1400044E0
0x1400044d0  cmp     qword ptr [rbx+10h], 0
0x1400044d5  jnz     short loc_1400044E0
0x1400044d7  mov     rax, [rsp+48h+arg_0]
0x1400044dc  mov     [rbx+10h], rax
0x1400044e0  mov     rax, [rbx+10h]
0x1400044e4  lea     rcx, [rax+20h]
0x1400044e8  neg     rax
0x1400044eb  sbb     rsi, rsi
0x1400044ee  and     rsi, rcx
0x1400044f1  lea     rdi, [rbx+20h]
0x1400044f5  mov     rcx, rdi; SRWLock
0x1400044f8  call    cs:__imp_AcquireSRWLockExclusive
0x1400044fe  cmp     qword ptr [rbx+18h], 0
0x140004503  jnz     short loc_140004509
0x140004505  mov     [rbx+18h], rsi
0x140004509  test    rdi, rdi
0x14000450c  jz      short loc_140004517
0x14000450e  mov     rcx, rdi; SRWLock
0x140004511  call    cs:__imp_ReleaseSRWLockExclusive
0x140004517  mov     ecx, ebp; dwErrCode
0x140004519  call    cs:__imp_SetLastError
0x14000451f  cmp     qword ptr [rbx+18h], 0
0x140004524  setnz   al
0x140004527  add     rsp, 28h
0x14000452b  pop     rdi
0x14000452c  pop     rsi
0x14000452d  pop     rbp
0x14000452e  pop     rbx
0x14000452f  retn
```
