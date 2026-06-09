# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400163bc`
- end: `0x140016481`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `197`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400159d0`
- `0x1400170f0`
- `0x140018058`
- `0x140018430`

## callees

- `0x140015fb4`
- `0x1400163bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016436`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016436`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016455`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016463`

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
0x1400163bc  push    rbx
0x1400163be  push    rbp
0x1400163bf  push    rsi
0x1400163c0  push    rdi
0x1400163c1  sub     rsp, 28h
0x1400163c5  cmp     qword ptr [rcx+18h], 0
0x1400163ca  mov     rbx, rcx
0x1400163cd  jnz     loc_14001646F
0x1400163d3  call    cs:__imp_GetLastError
0x1400163da  nop     dword ptr [rax+rax+00h]
0x1400163df  cmp     qword ptr [rbx+18h], 0
0x1400163e4  mov     ebp, eax
0x1400163e6  jz      short loc_1400163EC
0x1400163e8  xor     esi, esi
0x1400163ea  jmp     short loc_14001642F
0x1400163ec  cmp     qword ptr [rbx+10h], 0
0x1400163f1  jnz     short loc_14001641E
0x1400163f3  mov     rcx, [rbx+8]
0x1400163f7  lea     rdx, [rsp+48h+arg_0]
0x1400163fc  mov     [rsp+48h+arg_0], 0
0x140016405  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x14001640a  test    eax, eax
0x14001640c  js      short loc_14001641E
0x14001640e  cmp     qword ptr [rbx+10h], 0
0x140016413  jnz     short loc_14001641E
0x140016415  mov     rax, [rsp+48h+arg_0]
0x14001641a  mov     [rbx+10h], rax
0x14001641e  mov     rax, [rbx+10h]
0x140016422  lea     rcx, [rax+20h]
0x140016426  neg     rax
0x140016429  sbb     rsi, rsi
0x14001642c  and     rsi, rcx
0x14001642f  lea     rdi, [rbx+20h]
0x140016433  mov     rcx, rdi; SRWLock
0x140016436  call    cs:__imp_AcquireSRWLockExclusive
0x14001643d  nop     dword ptr [rax+rax+00h]
0x140016442  cmp     qword ptr [rbx+18h], 0
0x140016447  jnz     short loc_14001644D
0x140016449  mov     [rbx+18h], rsi
0x14001644d  test    rdi, rdi
0x140016450  jz      short loc_140016461
0x140016452  mov     rcx, rdi; SRWLock
0x140016455  call    cs:__imp_ReleaseSRWLockExclusive
0x14001645c  nop     dword ptr [rax+rax+00h]
0x140016461  mov     ecx, ebp; dwErrCode
0x140016463  call    cs:__imp_SetLastError
0x14001646a  nop     dword ptr [rax+rax+00h]
0x14001646f  cmp     qword ptr [rbx+18h], 0
0x140016474  setnz   al
0x140016477  add     rsp, 28h
0x14001647b  pop     rdi
0x14001647c  pop     rsi
0x14001647d  pop     rbp
0x14001647e  pop     rbx
0x14001647f  retn
```
