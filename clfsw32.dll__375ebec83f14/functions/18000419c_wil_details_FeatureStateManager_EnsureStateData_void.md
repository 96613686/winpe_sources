# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000419c`
- end: `0x180004261`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `197`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002800`
- `0x180005d94`
- `0x180007350`
- `0x1800079d0`

## callees

- `0x180003ba0`
- `0x18000419c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004243`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004235`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004235`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004216`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004216`

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
0x18000419c  push    rbx
0x18000419e  push    rbp
0x18000419f  push    rsi
0x1800041a0  push    rdi
0x1800041a1  sub     rsp, 28h
0x1800041a5  cmp     qword ptr [rcx+18h], 0
0x1800041aa  mov     rbx, rcx
0x1800041ad  jnz     loc_18000424F
0x1800041b3  call    cs:__imp_GetLastError
0x1800041ba  nop     dword ptr [rax+rax+00h]
0x1800041bf  cmp     qword ptr [rbx+18h], 0
0x1800041c4  mov     ebp, eax
0x1800041c6  jz      short loc_1800041CC
0x1800041c8  xor     esi, esi
0x1800041ca  jmp     short loc_18000420F
0x1800041cc  cmp     qword ptr [rbx+10h], 0
0x1800041d1  jnz     short loc_1800041FE
0x1800041d3  mov     rcx, [rbx+8]
0x1800041d7  lea     rdx, [rsp+48h+arg_0]
0x1800041dc  mov     [rsp+48h+arg_0], 0
0x1800041e5  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800041ea  test    eax, eax
0x1800041ec  js      short loc_1800041FE
0x1800041ee  cmp     qword ptr [rbx+10h], 0
0x1800041f3  jnz     short loc_1800041FE
0x1800041f5  mov     rax, [rsp+48h+arg_0]
0x1800041fa  mov     [rbx+10h], rax
0x1800041fe  mov     rax, [rbx+10h]
0x180004202  lea     rcx, [rax+20h]
0x180004206  neg     rax
0x180004209  sbb     rsi, rsi
0x18000420c  and     rsi, rcx
0x18000420f  lea     rdi, [rbx+20h]
0x180004213  mov     rcx, rdi; SRWLock
0x180004216  call    cs:__imp_AcquireSRWLockExclusive
0x18000421d  nop     dword ptr [rax+rax+00h]
0x180004222  cmp     qword ptr [rbx+18h], 0
0x180004227  jnz     short loc_18000422D
0x180004229  mov     [rbx+18h], rsi
0x18000422d  test    rdi, rdi
0x180004230  jz      short loc_180004241
0x180004232  mov     rcx, rdi; SRWLock
0x180004235  call    cs:__imp_ReleaseSRWLockExclusive
0x18000423c  nop     dword ptr [rax+rax+00h]
0x180004241  mov     ecx, ebp; dwErrCode
0x180004243  call    cs:__imp_SetLastError
0x18000424a  nop     dword ptr [rax+rax+00h]
0x18000424f  cmp     qword ptr [rbx+18h], 0
0x180004254  setnz   al
0x180004257  add     rsp, 28h
0x18000425b  pop     rdi
0x18000425c  pop     rsi
0x18000425d  pop     rbp
0x18000425e  pop     rbx
0x18000425f  retn
```
