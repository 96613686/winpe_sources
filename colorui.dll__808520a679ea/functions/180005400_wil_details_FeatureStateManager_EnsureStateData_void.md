# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180005400`
- end: `0x1800054ac`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002240`
- `0x180007d94`
- `0x18000a154`
- `0x18000aea0`

## callees

- `0x180003bf8`
- `0x180005400`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005417`
- `KERNEL32!GetLastError` at `0x180005417`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000548d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000548d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005474`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005474`
- `KERNEL32!SetLastError` at `0x180005495`
- `KERNEL32!SetLastError` at `0x180005495`

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
0x180005400  push    rbx
0x180005402  push    rbp
0x180005403  push    rsi
0x180005404  push    rdi
0x180005405  sub     rsp, 28h
0x180005409  cmp     qword ptr [rcx+18h], 0
0x18000540e  mov     rbx, rcx
0x180005411  jnz     loc_18000549B
0x180005417  call    cs:__imp_GetLastError
0x18000541d  cmp     qword ptr [rbx+18h], 0
0x180005422  mov     ebp, eax
0x180005424  jz      short loc_18000542A
0x180005426  xor     esi, esi
0x180005428  jmp     short loc_18000546D
0x18000542a  cmp     qword ptr [rbx+10h], 0
0x18000542f  jnz     short loc_18000545C
0x180005431  mov     rcx, [rbx+8]
0x180005435  lea     rdx, [rsp+48h+arg_0]
0x18000543a  mov     [rsp+48h+arg_0], 0
0x180005443  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180005448  test    eax, eax
0x18000544a  js      short loc_18000545C
0x18000544c  cmp     qword ptr [rbx+10h], 0
0x180005451  jnz     short loc_18000545C
0x180005453  mov     rax, [rsp+48h+arg_0]
0x180005458  mov     [rbx+10h], rax
0x18000545c  mov     rax, [rbx+10h]
0x180005460  lea     rcx, [rax+20h]
0x180005464  neg     rax
0x180005467  sbb     rsi, rsi
0x18000546a  and     rsi, rcx
0x18000546d  lea     rdi, [rbx+20h]
0x180005471  mov     rcx, rdi; SRWLock
0x180005474  call    cs:__imp_AcquireSRWLockExclusive
0x18000547a  cmp     qword ptr [rbx+18h], 0
0x18000547f  jnz     short loc_180005485
0x180005481  mov     [rbx+18h], rsi
0x180005485  test    rdi, rdi
0x180005488  jz      short loc_180005493
0x18000548a  mov     rcx, rdi; SRWLock
0x18000548d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005493  mov     ecx, ebp; dwErrCode
0x180005495  call    cs:__imp_SetLastError
0x18000549b  cmp     qword ptr [rbx+18h], 0
0x1800054a0  setnz   al
0x1800054a3  add     rsp, 28h
0x1800054a7  pop     rdi
0x1800054a8  pop     rsi
0x1800054a9  pop     rbp
0x1800054aa  pop     rbx
0x1800054ab  retn
```
