# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005630`
- end: `0x1800056eb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e50`

## callees

- `0x1800046a8`
- `0x180005630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005686`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180005630  mov     [rsp+arg_0], rbx
0x180005635  push    rdi
0x180005636  sub     rsp, 20h
0x18000563a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005641  xor     ebx, ebx
0x180005643  test    rdi, rdi
0x180005646  jz      short loc_1800056C6
0x180005648  cmp     [rdi+8], rbx
0x18000564c  jnz     short loc_180005673
0x18000564e  mov     rcx, [rdi]
0x180005651  lea     rdx, [rsp+28h+arg_8]
0x180005656  mov     [rsp+28h+arg_8], rbx
0x18000565b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005660  test    eax, eax
0x180005662  js      short loc_180005673
0x180005664  cmp     [rdi+8], rbx
0x180005668  jnz     short loc_180005673
0x18000566a  mov     rax, [rsp+28h+arg_8]
0x18000566f  mov     [rdi+8], rax
0x180005673  mov     rax, [rdi+8]
0x180005677  lea     rcx, [rax+20h]
0x18000567b  neg     rax
0x18000567e  sbb     rdi, rdi
0x180005681  and     rdi, rcx
0x180005684  jz      short loc_1800056C6
0x180005686  call    cs:__imp_GetCurrentThreadId
0x18000568c  mov     r8d, eax
0x18000568f  mov     r9d, eax
0x180005692  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000569c  shr     r8, 2
0x1800056a0  mul     r8
0x1800056a3  shr     rdx, 3
0x1800056a7  lea     rcx, [rdx+rdx*4]
0x1800056ab  add     rcx, rcx
0x1800056ae  sub     r8, rcx
0x1800056b1  mov     rbx, [rdi+r8*8+8]
0x1800056b6  jmp     short loc_1800056C1
0x1800056b8  cmp     [rbx], r9d
0x1800056bb  jz      short loc_1800056D4
0x1800056bd  mov     rbx, [rbx+8]
0x1800056c1  test    rbx, rbx
0x1800056c4  jnz     short loc_1800056B8
0x1800056c6  mov     rax, rbx
0x1800056c9  mov     rbx, [rsp+28h+arg_0]
0x1800056ce  add     rsp, 20h
0x1800056d2  pop     rdi
0x1800056d3  retn
0x1800056d4  add     rbx, 10h
0x1800056d8  jz      short loc_1800056C6
0x1800056da  cmp     qword ptr [rbx+8], 0
0x1800056df  jnz     short loc_1800056C6
0x1800056e1  lea     rax, [rdi+4]
0x1800056e5  mov     [rbx+8], rax
0x1800056e9  jmp     short loc_1800056C6
```
