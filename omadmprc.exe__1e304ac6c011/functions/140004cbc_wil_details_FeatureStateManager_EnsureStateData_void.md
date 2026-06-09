# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140004cbc`
- end: `0x140004d81`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `197`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d20`
- `0x140007284`
- `0x140009118`
- `0x140009880`

## callees

- `0x140004680`
- `0x140004cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004cd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004d63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004d63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004d36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004d55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004d55`

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
0x140004cbc  push    rbx
0x140004cbe  push    rbp
0x140004cbf  push    rsi
0x140004cc0  push    rdi
0x140004cc1  sub     rsp, 28h
0x140004cc5  cmp     qword ptr [rcx+18h], 0
0x140004cca  mov     rbx, rcx
0x140004ccd  jnz     loc_140004D6F
0x140004cd3  call    cs:__imp_GetLastError
0x140004cda  nop     dword ptr [rax+rax+00h]
0x140004cdf  cmp     qword ptr [rbx+18h], 0
0x140004ce4  mov     ebp, eax
0x140004ce6  jz      short loc_140004CEC
0x140004ce8  xor     esi, esi
0x140004cea  jmp     short loc_140004D2F
0x140004cec  cmp     qword ptr [rbx+10h], 0
0x140004cf1  jnz     short loc_140004D1E
0x140004cf3  mov     rcx, [rbx+8]
0x140004cf7  lea     rdx, [rsp+48h+arg_0]
0x140004cfc  mov     [rsp+48h+arg_0], 0
0x140004d05  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140004d0a  test    eax, eax
0x140004d0c  js      short loc_140004D1E
0x140004d0e  cmp     qword ptr [rbx+10h], 0
0x140004d13  jnz     short loc_140004D1E
0x140004d15  mov     rax, [rsp+48h+arg_0]
0x140004d1a  mov     [rbx+10h], rax
0x140004d1e  mov     rax, [rbx+10h]
0x140004d22  lea     rcx, [rax+20h]
0x140004d26  neg     rax
0x140004d29  sbb     rsi, rsi
0x140004d2c  and     rsi, rcx
0x140004d2f  lea     rdi, [rbx+20h]
0x140004d33  mov     rcx, rdi; SRWLock
0x140004d36  call    cs:__imp_AcquireSRWLockExclusive
0x140004d3d  nop     dword ptr [rax+rax+00h]
0x140004d42  cmp     qword ptr [rbx+18h], 0
0x140004d47  jnz     short loc_140004D4D
0x140004d49  mov     [rbx+18h], rsi
0x140004d4d  test    rdi, rdi
0x140004d50  jz      short loc_140004D61
0x140004d52  mov     rcx, rdi; SRWLock
0x140004d55  call    cs:__imp_ReleaseSRWLockExclusive
0x140004d5c  nop     dword ptr [rax+rax+00h]
0x140004d61  mov     ecx, ebp; dwErrCode
0x140004d63  call    cs:__imp_SetLastError
0x140004d6a  nop     dword ptr [rax+rax+00h]
0x140004d6f  cmp     qword ptr [rbx+18h], 0
0x140004d74  setnz   al
0x140004d77  add     rsp, 28h
0x140004d7b  pop     rdi
0x140004d7c  pop     rsi
0x140004d7d  pop     rbp
0x140004d7e  pop     rbx
0x140004d7f  retn
```
