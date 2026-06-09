# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004e64`
- end: `0x180004f10`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c50`
- `0x180006f74`
- `0x180008ecc`
- `0x180009510`

## callees

- `0x1800047cc`
- `0x180004e64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ed8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ed8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ef1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ef9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e7b`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(wil::details::FeatureStateManager *this)
{
  DWORD LastError; // ebp
  __int64 v3; // rsi
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 3) )
  {
    LastError = GetLastError();
    if ( *((_QWORD *)this + 3) )
    {
      v3 = 0;
    }
    else
    {
      if ( !*((_QWORD *)this + 2) )
      {
        v5 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
                    *((_QWORD *)this + 1),
                    &v5) >= 0
          && !*((_QWORD *)this + 2) )
        {
          *((_QWORD *)this + 2) = v5;
        }
      }
      v3 = (*((_QWORD *)this + 2) + 32LL) & -(__int64)(*((_QWORD *)this + 2) != 0);
    }
    AcquireSRWLockExclusive((PSRWLOCK)this + 4);
    if ( !*((_QWORD *)this + 3) )
      *((_QWORD *)this + 3) = v3;
    if ( this != (wil::details::FeatureStateManager *)-32LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 4);
    SetLastError(LastError);
  }
  return *((_QWORD *)this + 3) != 0;
}

```

## disassembly

```asm
0x180004e64  push    rbx
0x180004e66  push    rbp
0x180004e67  push    rsi
0x180004e68  push    rdi
0x180004e69  sub     rsp, 28h
0x180004e6d  mov     rbx, rcx
0x180004e70  cmp     qword ptr [rcx+18h], 0
0x180004e75  jnz     loc_180004EFF
0x180004e7b  call    cs:__imp_GetLastError
0x180004e81  mov     ebp, eax
0x180004e83  cmp     qword ptr [rbx+18h], 0
0x180004e88  jz      short loc_180004E8E
0x180004e8a  xor     esi, esi
0x180004e8c  jmp     short loc_180004ED1
0x180004e8e  cmp     qword ptr [rbx+10h], 0
0x180004e93  jnz     short loc_180004EC0
0x180004e95  mov     [rsp+48h+arg_0], 0
0x180004e9e  lea     rdx, [rsp+48h+arg_0]
0x180004ea3  mov     rcx, [rbx+8]
0x180004ea7  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004eac  test    eax, eax
0x180004eae  js      short loc_180004EC0
0x180004eb0  cmp     qword ptr [rbx+10h], 0
0x180004eb5  jnz     short loc_180004EC0
0x180004eb7  mov     rax, [rsp+48h+arg_0]
0x180004ebc  mov     [rbx+10h], rax
0x180004ec0  mov     rcx, [rbx+10h]
0x180004ec4  lea     rax, [rcx+20h]
0x180004ec8  neg     rcx
0x180004ecb  sbb     rsi, rsi
0x180004ece  and     rsi, rax
0x180004ed1  lea     rdi, [rbx+20h]
0x180004ed5  mov     rcx, rdi; SRWLock
0x180004ed8  call    cs:__imp_AcquireSRWLockExclusive
0x180004ede  cmp     qword ptr [rbx+18h], 0
0x180004ee3  jnz     short loc_180004EE9
0x180004ee5  mov     [rbx+18h], rsi
0x180004ee9  test    rdi, rdi
0x180004eec  jz      short loc_180004EF7
0x180004eee  mov     rcx, rdi; SRWLock
0x180004ef1  call    cs:__imp_ReleaseSRWLockExclusive
0x180004ef7  mov     ecx, ebp; dwErrCode
0x180004ef9  call    cs:__imp_SetLastError
0x180004eff  cmp     qword ptr [rbx+18h], 0
0x180004f04  setnz   al
0x180004f07  add     rsp, 28h
0x180004f0b  pop     rdi
0x180004f0c  pop     rsi
0x180004f0d  pop     rbp
0x180004f0e  pop     rbx
0x180004f0f  retn
```
