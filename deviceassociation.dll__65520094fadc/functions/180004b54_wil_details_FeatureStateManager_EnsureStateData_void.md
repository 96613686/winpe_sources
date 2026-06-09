# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180004b54`
- end: `0x180004c00`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003090`
- `0x180006664`
- `0x1800079ec`
- `0x180007f60`

## callees

- `0x1800044b0`
- `0x180004b54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004be1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004be1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004bc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004be9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004be9`

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
0x180004b54  push    rbx
0x180004b56  push    rbp
0x180004b57  push    rsi
0x180004b58  push    rdi
0x180004b59  sub     rsp, 28h
0x180004b5d  cmp     qword ptr [rcx+18h], 0
0x180004b62  mov     rbx, rcx
0x180004b65  jnz     loc_180004BEF
0x180004b6b  call    cs:__imp_GetLastError
0x180004b71  cmp     qword ptr [rbx+18h], 0
0x180004b76  mov     ebp, eax
0x180004b78  jz      short loc_180004B7E
0x180004b7a  xor     esi, esi
0x180004b7c  jmp     short loc_180004BC1
0x180004b7e  cmp     qword ptr [rbx+10h], 0
0x180004b83  jnz     short loc_180004BB0
0x180004b85  mov     rcx, [rbx+8]
0x180004b89  lea     rdx, [rsp+48h+arg_0]
0x180004b8e  mov     [rsp+48h+arg_0], 0
0x180004b97  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004b9c  test    eax, eax
0x180004b9e  js      short loc_180004BB0
0x180004ba0  cmp     qword ptr [rbx+10h], 0
0x180004ba5  jnz     short loc_180004BB0
0x180004ba7  mov     rax, [rsp+48h+arg_0]
0x180004bac  mov     [rbx+10h], rax
0x180004bb0  mov     rax, [rbx+10h]
0x180004bb4  lea     rcx, [rax+20h]
0x180004bb8  neg     rax
0x180004bbb  sbb     rsi, rsi
0x180004bbe  and     rsi, rcx
0x180004bc1  lea     rdi, [rbx+20h]
0x180004bc5  mov     rcx, rdi; SRWLock
0x180004bc8  call    cs:__imp_AcquireSRWLockExclusive
0x180004bce  cmp     qword ptr [rbx+18h], 0
0x180004bd3  jnz     short loc_180004BD9
0x180004bd5  mov     [rbx+18h], rsi
0x180004bd9  test    rdi, rdi
0x180004bdc  jz      short loc_180004BE7
0x180004bde  mov     rcx, rdi; SRWLock
0x180004be1  call    cs:__imp_ReleaseSRWLockExclusive
0x180004be7  mov     ecx, ebp; dwErrCode
0x180004be9  call    cs:__imp_SetLastError
0x180004bef  cmp     qword ptr [rbx+18h], 0
0x180004bf4  setnz   al
0x180004bf7  add     rsp, 28h
0x180004bfb  pop     rdi
0x180004bfc  pop     rsi
0x180004bfd  pop     rbp
0x180004bfe  pop     rbx
0x180004bff  retn
```
