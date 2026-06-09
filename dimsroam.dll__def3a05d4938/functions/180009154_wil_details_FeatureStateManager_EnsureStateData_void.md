# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180009154`
- end: `0x180009200`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007690`
- `0x18000ac64`
- `0x18000bfec`
- `0x18000c560`

## callees

- `0x180008ab0`
- `0x180009154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800091e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000916b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000916b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091c8`

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
0x180009154  push    rbx
0x180009156  push    rbp
0x180009157  push    rsi
0x180009158  push    rdi
0x180009159  sub     rsp, 28h
0x18000915d  cmp     qword ptr [rcx+18h], 0
0x180009162  mov     rbx, rcx
0x180009165  jnz     loc_1800091EF
0x18000916b  call    cs:__imp_GetLastError
0x180009171  cmp     qword ptr [rbx+18h], 0
0x180009176  mov     ebp, eax
0x180009178  jz      short loc_18000917E
0x18000917a  xor     esi, esi
0x18000917c  jmp     short loc_1800091C1
0x18000917e  cmp     qword ptr [rbx+10h], 0
0x180009183  jnz     short loc_1800091B0
0x180009185  mov     rcx, [rbx+8]
0x180009189  lea     rdx, [rsp+48h+arg_0]
0x18000918e  mov     [rsp+48h+arg_0], 0
0x180009197  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x18000919c  test    eax, eax
0x18000919e  js      short loc_1800091B0
0x1800091a0  cmp     qword ptr [rbx+10h], 0
0x1800091a5  jnz     short loc_1800091B0
0x1800091a7  mov     rax, [rsp+48h+arg_0]
0x1800091ac  mov     [rbx+10h], rax
0x1800091b0  mov     rax, [rbx+10h]
0x1800091b4  lea     rcx, [rax+20h]
0x1800091b8  neg     rax
0x1800091bb  sbb     rsi, rsi
0x1800091be  and     rsi, rcx
0x1800091c1  lea     rdi, [rbx+20h]
0x1800091c5  mov     rcx, rdi; SRWLock
0x1800091c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800091ce  cmp     qword ptr [rbx+18h], 0
0x1800091d3  jnz     short loc_1800091D9
0x1800091d5  mov     [rbx+18h], rsi
0x1800091d9  test    rdi, rdi
0x1800091dc  jz      short loc_1800091E7
0x1800091de  mov     rcx, rdi; SRWLock
0x1800091e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800091e7  mov     ecx, ebp; dwErrCode
0x1800091e9  call    cs:__imp_SetLastError
0x1800091ef  cmp     qword ptr [rbx+18h], 0
0x1800091f4  setnz   al
0x1800091f7  add     rsp, 28h
0x1800091fb  pop     rdi
0x1800091fc  pop     rsi
0x1800091fd  pop     rbp
0x1800091fe  pop     rbx
0x1800091ff  retn
```
