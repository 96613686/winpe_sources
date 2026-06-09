# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140013de4`
- end: `0x140013e90`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140012320`
- `0x1400158f4`
- `0x140016c7c`
- `0x1400171f0`

## callees

- `0x140013740`
- `0x140013de4`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140013e71`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140013e71`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140013e58`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140013e58`
- `KERNEL32!GetLastError` at `0x140013dfb`
- `KERNEL32!GetLastError` at `0x140013dfb`
- `KERNEL32!SetLastError` at `0x140013e79`
- `KERNEL32!SetLastError` at `0x140013e79`

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
0x140013de4  push    rbx
0x140013de6  push    rbp
0x140013de7  push    rsi
0x140013de8  push    rdi
0x140013de9  sub     rsp, 28h
0x140013ded  cmp     qword ptr [rcx+18h], 0
0x140013df2  mov     rbx, rcx
0x140013df5  jnz     loc_140013E7F
0x140013dfb  call    cs:__imp_GetLastError
0x140013e01  cmp     qword ptr [rbx+18h], 0
0x140013e06  mov     ebp, eax
0x140013e08  jz      short loc_140013E0E
0x140013e0a  xor     esi, esi
0x140013e0c  jmp     short loc_140013E51
0x140013e0e  cmp     qword ptr [rbx+10h], 0
0x140013e13  jnz     short loc_140013E40
0x140013e15  mov     rcx, [rbx+8]
0x140013e19  lea     rdx, [rsp+48h+arg_0]
0x140013e1e  mov     [rsp+48h+arg_0], 0
0x140013e27  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140013e2c  test    eax, eax
0x140013e2e  js      short loc_140013E40
0x140013e30  cmp     qword ptr [rbx+10h], 0
0x140013e35  jnz     short loc_140013E40
0x140013e37  mov     rax, [rsp+48h+arg_0]
0x140013e3c  mov     [rbx+10h], rax
0x140013e40  mov     rax, [rbx+10h]
0x140013e44  lea     rcx, [rax+20h]
0x140013e48  neg     rax
0x140013e4b  sbb     rsi, rsi
0x140013e4e  and     rsi, rcx
0x140013e51  lea     rdi, [rbx+20h]
0x140013e55  mov     rcx, rdi; SRWLock
0x140013e58  call    cs:__imp_AcquireSRWLockExclusive
0x140013e5e  cmp     qword ptr [rbx+18h], 0
0x140013e63  jnz     short loc_140013E69
0x140013e65  mov     [rbx+18h], rsi
0x140013e69  test    rdi, rdi
0x140013e6c  jz      short loc_140013E77
0x140013e6e  mov     rcx, rdi; SRWLock
0x140013e71  call    cs:__imp_ReleaseSRWLockExclusive
0x140013e77  mov     ecx, ebp; dwErrCode
0x140013e79  call    cs:__imp_SetLastError
0x140013e7f  cmp     qword ptr [rbx+18h], 0
0x140013e84  setnz   al
0x140013e87  add     rsp, 28h
0x140013e8b  pop     rdi
0x140013e8c  pop     rsi
0x140013e8d  pop     rbp
0x140013e8e  pop     rbx
0x140013e8f  retn
```
