# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180005b64`
- end: `0x180005c10`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003660`
- `0x180007af4`
- `0x180009820`
- `0x180009e80`

## callees

- `0x180005488`
- `0x180005b64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005bf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b7b`

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
0x180005b64  push    rbx
0x180005b66  push    rbp
0x180005b67  push    rsi
0x180005b68  push    rdi
0x180005b69  sub     rsp, 28h
0x180005b6d  cmp     qword ptr [rcx+18h], 0
0x180005b72  mov     rbx, rcx
0x180005b75  jnz     loc_180005BFF
0x180005b7b  call    cs:__imp_GetLastError
0x180005b81  cmp     qword ptr [rbx+18h], 0
0x180005b86  mov     ebp, eax
0x180005b88  jz      short loc_180005B8E
0x180005b8a  xor     esi, esi
0x180005b8c  jmp     short loc_180005BD1
0x180005b8e  cmp     qword ptr [rbx+10h], 0
0x180005b93  jnz     short loc_180005BC0
0x180005b95  mov     rcx, [rbx+8]
0x180005b99  lea     rdx, [rsp+48h+arg_0]
0x180005b9e  mov     [rsp+48h+arg_0], 0
0x180005ba7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180005bac  test    eax, eax
0x180005bae  js      short loc_180005BC0
0x180005bb0  cmp     qword ptr [rbx+10h], 0
0x180005bb5  jnz     short loc_180005BC0
0x180005bb7  mov     rax, [rsp+48h+arg_0]
0x180005bbc  mov     [rbx+10h], rax
0x180005bc0  mov     rax, [rbx+10h]
0x180005bc4  lea     rcx, [rax+20h]
0x180005bc8  neg     rax
0x180005bcb  sbb     rsi, rsi
0x180005bce  and     rsi, rcx
0x180005bd1  lea     rdi, [rbx+20h]
0x180005bd5  mov     rcx, rdi; SRWLock
0x180005bd8  call    cs:__imp_AcquireSRWLockExclusive
0x180005bde  cmp     qword ptr [rbx+18h], 0
0x180005be3  jnz     short loc_180005BE9
0x180005be5  mov     [rbx+18h], rsi
0x180005be9  test    rdi, rdi
0x180005bec  jz      short loc_180005BF7
0x180005bee  mov     rcx, rdi; SRWLock
0x180005bf1  call    cs:__imp_ReleaseSRWLockExclusive
0x180005bf7  mov     ecx, ebp; dwErrCode
0x180005bf9  call    cs:__imp_SetLastError
0x180005bff  cmp     qword ptr [rbx+18h], 0
0x180005c04  setnz   al
0x180005c07  add     rsp, 28h
0x180005c0b  pop     rdi
0x180005c0c  pop     rsi
0x180005c0d  pop     rbp
0x180005c0e  pop     rbx
0x180005c0f  retn
```
