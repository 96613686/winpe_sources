# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180003d34`
- end: `0x180003de0`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002050`
- `0x1800058e4`
- `0x180006dac`
- `0x180007340`

## callees

- `0x1800034b8`
- `0x180003d34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003da8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003da8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003dc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003dc9`

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
0x180003d34  push    rbx
0x180003d36  push    rbp
0x180003d37  push    rsi
0x180003d38  push    rdi
0x180003d39  sub     rsp, 28h
0x180003d3d  cmp     qword ptr [rcx+18h], 0
0x180003d42  mov     rbx, rcx
0x180003d45  jnz     loc_180003DCF
0x180003d4b  call    cs:__imp_GetLastError
0x180003d51  cmp     qword ptr [rbx+18h], 0
0x180003d56  mov     ebp, eax
0x180003d58  jz      short loc_180003D5E
0x180003d5a  xor     esi, esi
0x180003d5c  jmp     short loc_180003DA1
0x180003d5e  cmp     qword ptr [rbx+10h], 0
0x180003d63  jnz     short loc_180003D90
0x180003d65  mov     rcx, [rbx+8]
0x180003d69  lea     rdx, [rsp+48h+arg_0]
0x180003d6e  mov     [rsp+48h+arg_0], 0
0x180003d77  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180003d7c  test    eax, eax
0x180003d7e  js      short loc_180003D90
0x180003d80  cmp     qword ptr [rbx+10h], 0
0x180003d85  jnz     short loc_180003D90
0x180003d87  mov     rax, [rsp+48h+arg_0]
0x180003d8c  mov     [rbx+10h], rax
0x180003d90  mov     rax, [rbx+10h]
0x180003d94  lea     rcx, [rax+20h]
0x180003d98  neg     rax
0x180003d9b  sbb     rsi, rsi
0x180003d9e  and     rsi, rcx
0x180003da1  lea     rdi, [rbx+20h]
0x180003da5  mov     rcx, rdi; SRWLock
0x180003da8  call    cs:__imp_AcquireSRWLockExclusive
0x180003dae  cmp     qword ptr [rbx+18h], 0
0x180003db3  jnz     short loc_180003DB9
0x180003db5  mov     [rbx+18h], rsi
0x180003db9  test    rdi, rdi
0x180003dbc  jz      short loc_180003DC7
0x180003dbe  mov     rcx, rdi; SRWLock
0x180003dc1  call    cs:__imp_ReleaseSRWLockExclusive
0x180003dc7  mov     ecx, ebp; dwErrCode
0x180003dc9  call    cs:__imp_SetLastError
0x180003dcf  cmp     qword ptr [rbx+18h], 0
0x180003dd4  setnz   al
0x180003dd7  add     rsp, 28h
0x180003ddb  pop     rdi
0x180003ddc  pop     rsi
0x180003ddd  pop     rbp
0x180003dde  pop     rbx
0x180003ddf  retn
```
