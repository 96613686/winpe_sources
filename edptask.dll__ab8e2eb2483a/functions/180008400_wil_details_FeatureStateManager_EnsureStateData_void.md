# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180008400`
- end: `0x1800084ac`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800070c0`
- `0x18000f624`
- `0x180011498`
- `0x180011810`

## callees

- `0x180007e80`
- `0x180008400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000848d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000848d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008474`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008417`

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
0x180008400  push    rbx
0x180008402  push    rbp
0x180008403  push    rsi
0x180008404  push    rdi
0x180008405  sub     rsp, 28h
0x180008409  cmp     qword ptr [rcx+18h], 0
0x18000840e  mov     rbx, rcx
0x180008411  jnz     loc_18000849B
0x180008417  call    cs:__imp_GetLastError
0x18000841d  cmp     qword ptr [rbx+18h], 0
0x180008422  mov     ebp, eax
0x180008424  jz      short loc_18000842A
0x180008426  xor     esi, esi
0x180008428  jmp     short loc_18000846D
0x18000842a  cmp     qword ptr [rbx+10h], 0
0x18000842f  jnz     short loc_18000845C
0x180008431  mov     rcx, [rbx+8]
0x180008435  lea     rdx, [rsp+48h+arg_0]
0x18000843a  mov     [rsp+48h+arg_0], 0
0x180008443  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180008448  test    eax, eax
0x18000844a  js      short loc_18000845C
0x18000844c  cmp     qword ptr [rbx+10h], 0
0x180008451  jnz     short loc_18000845C
0x180008453  mov     rax, [rsp+48h+arg_0]
0x180008458  mov     [rbx+10h], rax
0x18000845c  mov     rax, [rbx+10h]
0x180008460  lea     rcx, [rax+20h]
0x180008464  neg     rax
0x180008467  sbb     rsi, rsi
0x18000846a  and     rsi, rcx
0x18000846d  lea     rdi, [rbx+20h]
0x180008471  mov     rcx, rdi; SRWLock
0x180008474  call    cs:__imp_AcquireSRWLockExclusive
0x18000847a  cmp     qword ptr [rbx+18h], 0
0x18000847f  jnz     short loc_180008485
0x180008481  mov     [rbx+18h], rsi
0x180008485  test    rdi, rdi
0x180008488  jz      short loc_180008493
0x18000848a  mov     rcx, rdi; SRWLock
0x18000848d  call    cs:__imp_ReleaseSRWLockExclusive
0x180008493  mov     ecx, ebp; dwErrCode
0x180008495  call    cs:__imp_SetLastError
0x18000849b  cmp     qword ptr [rbx+18h], 0
0x1800084a0  setnz   al
0x1800084a3  add     rsp, 28h
0x1800084a7  pop     rdi
0x1800084a8  pop     rsi
0x1800084a9  pop     rbp
0x1800084aa  pop     rbx
0x1800084ab  retn
```
