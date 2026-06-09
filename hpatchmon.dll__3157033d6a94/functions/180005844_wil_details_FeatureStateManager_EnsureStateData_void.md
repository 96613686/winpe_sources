# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180005844`
- end: `0x1800058f0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003220`
- `0x180008724`
- `0x18000b8d4`
- `0x18000c040`

## callees

- `0x180004c9c`
- `0x180005844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000585b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000585b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058d1`

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
0x180005844  push    rbx
0x180005846  push    rbp
0x180005847  push    rsi
0x180005848  push    rdi
0x180005849  sub     rsp, 28h
0x18000584d  cmp     qword ptr [rcx+18h], 0
0x180005852  mov     rbx, rcx
0x180005855  jnz     loc_1800058DF
0x18000585b  call    cs:__imp_GetLastError
0x180005861  cmp     qword ptr [rbx+18h], 0
0x180005866  mov     ebp, eax
0x180005868  jz      short loc_18000586E
0x18000586a  xor     esi, esi
0x18000586c  jmp     short loc_1800058B1
0x18000586e  cmp     qword ptr [rbx+10h], 0
0x180005873  jnz     short loc_1800058A0
0x180005875  mov     rcx, [rbx+8]
0x180005879  lea     rdx, [rsp+48h+arg_0]
0x18000587e  mov     [rsp+48h+arg_0], 0
0x180005887  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000588c  test    eax, eax
0x18000588e  js      short loc_1800058A0
0x180005890  cmp     qword ptr [rbx+10h], 0
0x180005895  jnz     short loc_1800058A0
0x180005897  mov     rax, [rsp+48h+arg_0]
0x18000589c  mov     [rbx+10h], rax
0x1800058a0  mov     rax, [rbx+10h]
0x1800058a4  lea     rcx, [rax+20h]
0x1800058a8  neg     rax
0x1800058ab  sbb     rsi, rsi
0x1800058ae  and     rsi, rcx
0x1800058b1  lea     rdi, [rbx+20h]
0x1800058b5  mov     rcx, rdi; SRWLock
0x1800058b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800058be  cmp     qword ptr [rbx+18h], 0
0x1800058c3  jnz     short loc_1800058C9
0x1800058c5  mov     [rbx+18h], rsi
0x1800058c9  test    rdi, rdi
0x1800058cc  jz      short loc_1800058D7
0x1800058ce  mov     rcx, rdi; SRWLock
0x1800058d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800058d7  mov     ecx, ebp; dwErrCode
0x1800058d9  call    cs:__imp_SetLastError
0x1800058df  cmp     qword ptr [rbx+18h], 0
0x1800058e4  setnz   al
0x1800058e7  add     rsp, 28h
0x1800058eb  pop     rdi
0x1800058ec  pop     rsi
0x1800058ed  pop     rbp
0x1800058ee  pop     rbx
0x1800058ef  retn
```
