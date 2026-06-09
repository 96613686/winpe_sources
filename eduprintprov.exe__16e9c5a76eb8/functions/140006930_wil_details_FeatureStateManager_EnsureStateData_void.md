# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140006930`
- end: `0x1400069dc`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003470`
- `0x140008884`
- `0x14000a398`
- `0x14000a9d0`

## callees

- `0x140005b08`
- `0x140006930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400069a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400069a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400069bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400069bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006947`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400069c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400069c5`

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
0x140006930  push    rbx
0x140006932  push    rbp
0x140006933  push    rsi
0x140006934  push    rdi
0x140006935  sub     rsp, 28h
0x140006939  cmp     qword ptr [rcx+18h], 0
0x14000693e  mov     rbx, rcx
0x140006941  jnz     loc_1400069CB
0x140006947  call    cs:__imp_GetLastError
0x14000694d  cmp     qword ptr [rbx+18h], 0
0x140006952  mov     ebp, eax
0x140006954  jz      short loc_14000695A
0x140006956  xor     esi, esi
0x140006958  jmp     short loc_14000699D
0x14000695a  cmp     qword ptr [rbx+10h], 0
0x14000695f  jnz     short loc_14000698C
0x140006961  mov     rcx, [rbx+8]
0x140006965  lea     rdx, [rsp+48h+arg_0]
0x14000696a  mov     [rsp+48h+arg_0], 0
0x140006973  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140006978  test    eax, eax
0x14000697a  js      short loc_14000698C
0x14000697c  cmp     qword ptr [rbx+10h], 0
0x140006981  jnz     short loc_14000698C
0x140006983  mov     rax, [rsp+48h+arg_0]
0x140006988  mov     [rbx+10h], rax
0x14000698c  mov     rax, [rbx+10h]
0x140006990  lea     rcx, [rax+20h]
0x140006994  neg     rax
0x140006997  sbb     rsi, rsi
0x14000699a  and     rsi, rcx
0x14000699d  lea     rdi, [rbx+20h]
0x1400069a1  mov     rcx, rdi; SRWLock
0x1400069a4  call    cs:__imp_AcquireSRWLockExclusive
0x1400069aa  cmp     qword ptr [rbx+18h], 0
0x1400069af  jnz     short loc_1400069B5
0x1400069b1  mov     [rbx+18h], rsi
0x1400069b5  test    rdi, rdi
0x1400069b8  jz      short loc_1400069C3
0x1400069ba  mov     rcx, rdi; SRWLock
0x1400069bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1400069c3  mov     ecx, ebp; dwErrCode
0x1400069c5  call    cs:__imp_SetLastError
0x1400069cb  cmp     qword ptr [rbx+18h], 0
0x1400069d0  setnz   al
0x1400069d3  add     rsp, 28h
0x1400069d7  pop     rdi
0x1400069d8  pop     rsi
0x1400069d9  pop     rbp
0x1400069da  pop     rbx
0x1400069db  retn
```
