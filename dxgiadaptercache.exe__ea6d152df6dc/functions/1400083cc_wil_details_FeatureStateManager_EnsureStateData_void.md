# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400083cc`
- end: `0x140008478`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033c0`
- `0x14000b304`
- `0x14000db60`
- `0x14000f6f0`

## callees

- `0x140007738`
- `0x1400083cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008440`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008459`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008461`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008461`

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
0x1400083cc  push    rbx
0x1400083ce  push    rbp
0x1400083cf  push    rsi
0x1400083d0  push    rdi
0x1400083d1  sub     rsp, 28h
0x1400083d5  cmp     qword ptr [rcx+18h], 0
0x1400083da  mov     rbx, rcx
0x1400083dd  jnz     loc_140008467
0x1400083e3  call    cs:__imp_GetLastError
0x1400083e9  cmp     qword ptr [rbx+18h], 0
0x1400083ee  mov     ebp, eax
0x1400083f0  jz      short loc_1400083F6
0x1400083f2  xor     esi, esi
0x1400083f4  jmp     short loc_140008439
0x1400083f6  cmp     qword ptr [rbx+10h], 0
0x1400083fb  jnz     short loc_140008428
0x1400083fd  mov     rcx, [rbx+8]
0x140008401  lea     rdx, [rsp+48h+arg_0]
0x140008406  mov     [rsp+48h+arg_0], 0
0x14000840f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140008414  test    eax, eax
0x140008416  js      short loc_140008428
0x140008418  cmp     qword ptr [rbx+10h], 0
0x14000841d  jnz     short loc_140008428
0x14000841f  mov     rax, [rsp+48h+arg_0]
0x140008424  mov     [rbx+10h], rax
0x140008428  mov     rax, [rbx+10h]
0x14000842c  lea     rcx, [rax+20h]
0x140008430  neg     rax
0x140008433  sbb     rsi, rsi
0x140008436  and     rsi, rcx
0x140008439  lea     rdi, [rbx+20h]
0x14000843d  mov     rcx, rdi; SRWLock
0x140008440  call    cs:__imp_AcquireSRWLockExclusive
0x140008446  cmp     qword ptr [rbx+18h], 0
0x14000844b  jnz     short loc_140008451
0x14000844d  mov     [rbx+18h], rsi
0x140008451  test    rdi, rdi
0x140008454  jz      short loc_14000845F
0x140008456  mov     rcx, rdi; SRWLock
0x140008459  call    cs:__imp_ReleaseSRWLockExclusive
0x14000845f  mov     ecx, ebp; dwErrCode
0x140008461  call    cs:__imp_SetLastError
0x140008467  cmp     qword ptr [rbx+18h], 0
0x14000846c  setnz   al
0x14000846f  add     rsp, 28h
0x140008473  pop     rdi
0x140008474  pop     rsi
0x140008475  pop     rbp
0x140008476  pop     rbx
0x140008477  retn
```
