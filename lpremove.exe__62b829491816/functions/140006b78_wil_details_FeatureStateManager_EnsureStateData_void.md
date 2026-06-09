# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140006b78`
- end: `0x140006c24`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400034f0`
- `0x1400095d4`
- `0x14000bd58`
- `0x14000c7c0`

## callees

- `0x1400060b8`
- `0x140006b78`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140006c0d`
- `KERNEL32!SetLastError` at `0x140006c0d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006bec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006bec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006c05`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006c05`
- `KERNEL32!GetLastError` at `0x140006b8f`
- `KERNEL32!GetLastError` at `0x140006b8f`

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
0x140006b78  push    rbx
0x140006b7a  push    rbp
0x140006b7b  push    rsi
0x140006b7c  push    rdi
0x140006b7d  sub     rsp, 28h
0x140006b81  cmp     qword ptr [rcx+18h], 0
0x140006b86  mov     rbx, rcx
0x140006b89  jnz     loc_140006C13
0x140006b8f  call    cs:__imp_GetLastError
0x140006b95  cmp     qword ptr [rbx+18h], 0
0x140006b9a  mov     ebp, eax
0x140006b9c  jz      short loc_140006BA2
0x140006b9e  xor     esi, esi
0x140006ba0  jmp     short loc_140006BE5
0x140006ba2  cmp     qword ptr [rbx+10h], 0
0x140006ba7  jnz     short loc_140006BD4
0x140006ba9  mov     rcx, [rbx+8]
0x140006bad  lea     rdx, [rsp+48h+arg_0]
0x140006bb2  mov     [rsp+48h+arg_0], 0
0x140006bbb  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x140006bc0  test    eax, eax
0x140006bc2  js      short loc_140006BD4
0x140006bc4  cmp     qword ptr [rbx+10h], 0
0x140006bc9  jnz     short loc_140006BD4
0x140006bcb  mov     rax, [rsp+48h+arg_0]
0x140006bd0  mov     [rbx+10h], rax
0x140006bd4  mov     rax, [rbx+10h]
0x140006bd8  lea     rcx, [rax+20h]
0x140006bdc  neg     rax
0x140006bdf  sbb     rsi, rsi
0x140006be2  and     rsi, rcx
0x140006be5  lea     rdi, [rbx+20h]
0x140006be9  mov     rcx, rdi; SRWLock
0x140006bec  call    cs:__imp_AcquireSRWLockExclusive
0x140006bf2  cmp     qword ptr [rbx+18h], 0
0x140006bf7  jnz     short loc_140006BFD
0x140006bf9  mov     [rbx+18h], rsi
0x140006bfd  test    rdi, rdi
0x140006c00  jz      short loc_140006C0B
0x140006c02  mov     rcx, rdi; SRWLock
0x140006c05  call    cs:__imp_ReleaseSRWLockExclusive
0x140006c0b  mov     ecx, ebp; dwErrCode
0x140006c0d  call    cs:__imp_SetLastError
0x140006c13  cmp     qword ptr [rbx+18h], 0
0x140006c18  setnz   al
0x140006c1b  add     rsp, 28h
0x140006c1f  pop     rdi
0x140006c20  pop     rsi
0x140006c21  pop     rbp
0x140006c22  pop     rbx
0x140006c23  retn
```
