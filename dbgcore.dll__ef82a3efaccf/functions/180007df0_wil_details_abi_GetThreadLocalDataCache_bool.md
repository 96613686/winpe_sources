# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007df0`
- end: `0x180007eab`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006fd0`

## callees

- `0x180004c68`
- `0x180007df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e46`

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
0x180007df0  mov     [rsp+arg_0], rbx
0x180007df5  push    rdi
0x180007df6  sub     rsp, 20h
0x180007dfa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007e01  xor     ebx, ebx
0x180007e03  test    rdi, rdi
0x180007e06  jz      short loc_180007E86
0x180007e08  cmp     [rdi+8], rbx
0x180007e0c  jnz     short loc_180007E33
0x180007e0e  mov     rcx, [rdi]
0x180007e11  lea     rdx, [rsp+28h+arg_8]
0x180007e16  mov     [rsp+28h+arg_8], rbx
0x180007e1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007e20  test    eax, eax
0x180007e22  js      short loc_180007E33
0x180007e24  cmp     [rdi+8], rbx
0x180007e28  jnz     short loc_180007E33
0x180007e2a  mov     rax, [rsp+28h+arg_8]
0x180007e2f  mov     [rdi+8], rax
0x180007e33  mov     rax, [rdi+8]
0x180007e37  lea     rcx, [rax+20h]
0x180007e3b  neg     rax
0x180007e3e  sbb     rdi, rdi
0x180007e41  and     rdi, rcx
0x180007e44  jz      short loc_180007E86
0x180007e46  call    cs:__imp_GetCurrentThreadId
0x180007e4c  mov     r8d, eax
0x180007e4f  mov     r9d, eax
0x180007e52  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007e5c  shr     r8, 2
0x180007e60  mul     r8
0x180007e63  shr     rdx, 3
0x180007e67  lea     rcx, [rdx+rdx*4]
0x180007e6b  add     rcx, rcx
0x180007e6e  sub     r8, rcx
0x180007e71  mov     rbx, [rdi+r8*8+8]
0x180007e76  jmp     short loc_180007E81
0x180007e78  cmp     [rbx], r9d
0x180007e7b  jz      short loc_180007E94
0x180007e7d  mov     rbx, [rbx+8]
0x180007e81  test    rbx, rbx
0x180007e84  jnz     short loc_180007E78
0x180007e86  mov     rax, rbx
0x180007e89  mov     rbx, [rsp+28h+arg_0]
0x180007e8e  add     rsp, 20h
0x180007e92  pop     rdi
0x180007e93  retn
0x180007e94  add     rbx, 10h
0x180007e98  jz      short loc_180007E86
0x180007e9a  cmp     qword ptr [rbx+8], 0
0x180007e9f  jnz     short loc_180007E86
0x180007ea1  lea     rax, [rdi+4]
0x180007ea5  mov     [rbx+8], rax
0x180007ea9  jmp     short loc_180007E86
```
