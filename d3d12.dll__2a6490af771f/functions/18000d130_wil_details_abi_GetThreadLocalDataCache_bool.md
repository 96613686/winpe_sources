# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d130`
- end: `0x18000d1ed`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc80`

## callees

- `0x18000a498`
- `0x18000d130`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d18a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d18a`

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
0x18000d130  mov     [rsp+arg_0], rbx
0x18000d135  push    rdi
0x18000d136  sub     rsp, 20h
0x18000d13a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d141  xor     ebx, ebx
0x18000d143  test    rdi, rdi
0x18000d146  jz      loc_18000D1DF
0x18000d14c  cmp     [rdi+8], rbx
0x18000d150  jnz     short loc_18000D177
0x18000d152  mov     rcx, [rdi]
0x18000d155  lea     rdx, [rsp+28h+arg_8]
0x18000d15a  mov     [rsp+28h+arg_8], rbx
0x18000d15f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d164  test    eax, eax
0x18000d166  js      short loc_18000D177
0x18000d168  cmp     [rdi+8], rbx
0x18000d16c  jnz     short loc_18000D177
0x18000d16e  mov     rax, [rsp+28h+arg_8]
0x18000d173  mov     [rdi+8], rax
0x18000d177  mov     rax, [rdi+8]
0x18000d17b  lea     rcx, [rax+20h]
0x18000d17f  neg     rax
0x18000d182  sbb     rdi, rdi
0x18000d185  and     rdi, rcx
0x18000d188  jz      short loc_18000D1DF
0x18000d18a  call    cs:__imp_GetCurrentThreadId
0x18000d190  mov     r8d, eax
0x18000d193  mov     r9d, eax
0x18000d196  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d1a0  shr     r8, 2
0x18000d1a4  mul     r8
0x18000d1a7  shr     rdx, 3
0x18000d1ab  lea     rcx, [rdx+rdx*4]
0x18000d1af  add     rcx, rcx
0x18000d1b2  sub     r8, rcx
0x18000d1b5  mov     rbx, [rdi+r8*8+8]
0x18000d1ba  test    rbx, rbx
0x18000d1bd  jz      short loc_18000D1DF
0x18000d1bf  cmp     [rbx], r9d
0x18000d1c2  jz      short loc_18000D1CA
0x18000d1c4  mov     rbx, [rbx+8]
0x18000d1c8  jmp     short loc_18000D1BA
0x18000d1ca  add     rbx, 10h
0x18000d1ce  jz      short loc_18000D1DF
0x18000d1d0  cmp     qword ptr [rbx+8], 0
0x18000d1d5  jnz     short loc_18000D1DF
0x18000d1d7  lea     rax, [rdi+4]
0x18000d1db  mov     [rbx+8], rax
0x18000d1df  mov     rax, rbx
0x18000d1e2  mov     rbx, [rsp+28h+arg_0]
0x18000d1e7  add     rsp, 20h
0x18000d1eb  pop     rdi
0x18000d1ec  retn
```
