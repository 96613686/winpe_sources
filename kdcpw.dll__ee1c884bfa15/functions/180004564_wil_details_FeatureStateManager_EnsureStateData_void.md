# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004564`
- end: `0x180004610`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002740`
- `0x180006a44`
- `0x18000835c`
- `0x180008960`

## callees

- `0x180003d88`
- `0x180004564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800045d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800045f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000457b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000457b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045f9`

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
0x180004564  push    rbx
0x180004566  push    rbp
0x180004567  push    rsi
0x180004568  push    rdi
0x180004569  sub     rsp, 28h
0x18000456d  cmp     qword ptr [rcx+18h], 0
0x180004572  mov     rbx, rcx
0x180004575  jnz     loc_1800045FF
0x18000457b  call    cs:__imp_GetLastError
0x180004581  cmp     qword ptr [rbx+18h], 0
0x180004586  mov     ebp, eax
0x180004588  jz      short loc_18000458E
0x18000458a  xor     esi, esi
0x18000458c  jmp     short loc_1800045D1
0x18000458e  cmp     qword ptr [rbx+10h], 0
0x180004593  jnz     short loc_1800045C0
0x180004595  mov     rcx, [rbx+8]
0x180004599  lea     rdx, [rsp+48h+arg_0]
0x18000459e  mov     [rsp+48h+arg_0], 0
0x1800045a7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800045ac  test    eax, eax
0x1800045ae  js      short loc_1800045C0
0x1800045b0  cmp     qword ptr [rbx+10h], 0
0x1800045b5  jnz     short loc_1800045C0
0x1800045b7  mov     rax, [rsp+48h+arg_0]
0x1800045bc  mov     [rbx+10h], rax
0x1800045c0  mov     rax, [rbx+10h]
0x1800045c4  lea     rcx, [rax+20h]
0x1800045c8  neg     rax
0x1800045cb  sbb     rsi, rsi
0x1800045ce  and     rsi, rcx
0x1800045d1  lea     rdi, [rbx+20h]
0x1800045d5  mov     rcx, rdi; SRWLock
0x1800045d8  call    cs:__imp_AcquireSRWLockExclusive
0x1800045de  cmp     qword ptr [rbx+18h], 0
0x1800045e3  jnz     short loc_1800045E9
0x1800045e5  mov     [rbx+18h], rsi
0x1800045e9  test    rdi, rdi
0x1800045ec  jz      short loc_1800045F7
0x1800045ee  mov     rcx, rdi; SRWLock
0x1800045f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800045f7  mov     ecx, ebp; dwErrCode
0x1800045f9  call    cs:__imp_SetLastError
0x1800045ff  cmp     qword ptr [rbx+18h], 0
0x180004604  setnz   al
0x180004607  add     rsp, 28h
0x18000460b  pop     rdi
0x18000460c  pop     rsi
0x18000460d  pop     rbp
0x18000460e  pop     rbx
0x18000460f  retn
```
