# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800132cc`
- end: `0x180013389`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012cf0`

## callees

- `0x1800124c8`
- `0x1800132cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013326`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013326`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x1800132cc  mov     [rsp+arg_0], rbx
0x1800132d1  push    rdi
0x1800132d2  sub     rsp, 20h
0x1800132d6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800132dd  xor     ebx, ebx
0x1800132df  test    rdi, rdi
0x1800132e2  jz      loc_18001337B
0x1800132e8  cmp     [rdi+8], rbx
0x1800132ec  jnz     short loc_180013313
0x1800132ee  mov     rcx, [rdi]
0x1800132f1  lea     rdx, [rsp+28h+arg_8]
0x1800132f6  mov     [rsp+28h+arg_8], rbx
0x1800132fb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180013300  test    eax, eax
0x180013302  js      short loc_180013313
0x180013304  cmp     [rdi+8], rbx
0x180013308  jnz     short loc_180013313
0x18001330a  mov     rax, [rsp+28h+arg_8]
0x18001330f  mov     [rdi+8], rax
0x180013313  mov     rax, [rdi+8]
0x180013317  lea     rcx, [rax+20h]
0x18001331b  neg     rax
0x18001331e  sbb     rdi, rdi
0x180013321  and     rdi, rcx
0x180013324  jz      short loc_18001337B
0x180013326  call    cs:__imp_GetCurrentThreadId
0x18001332c  mov     r8d, eax
0x18001332f  mov     r9d, eax
0x180013332  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001333c  shr     r8, 2
0x180013340  mul     r8
0x180013343  shr     rdx, 3
0x180013347  lea     rcx, [rdx+rdx*4]
0x18001334b  add     rcx, rcx
0x18001334e  sub     r8, rcx
0x180013351  mov     rbx, [rdi+r8*8+8]
0x180013356  test    rbx, rbx
0x180013359  jz      short loc_18001337B
0x18001335b  cmp     [rbx], r9d
0x18001335e  jz      short loc_180013366
0x180013360  mov     rbx, [rbx+8]
0x180013364  jmp     short loc_180013356
0x180013366  add     rbx, 10h
0x18001336a  jz      short loc_18001337B
0x18001336c  cmp     qword ptr [rbx+8], 0
0x180013371  jnz     short loc_18001337B
0x180013373  lea     rax, [rdi+4]
0x180013377  mov     [rbx+8], rax
0x18001337b  mov     rax, rbx
0x18001337e  mov     rbx, [rsp+28h+arg_0]
0x180013383  add     rsp, 20h
0x180013387  pop     rdi
0x180013388  retn
```
