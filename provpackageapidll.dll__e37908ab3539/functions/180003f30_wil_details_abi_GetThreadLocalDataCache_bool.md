# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003f30`
- end: `0x180003feb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003750`

## callees

- `0x180003068`
- `0x180003f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f86`

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
0x180003f30  mov     [rsp+arg_0], rbx
0x180003f35  push    rdi
0x180003f36  sub     rsp, 20h
0x180003f3a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003f41  xor     ebx, ebx
0x180003f43  test    rdi, rdi
0x180003f46  jz      short loc_180003FC6
0x180003f48  cmp     [rdi+8], rbx
0x180003f4c  jnz     short loc_180003F73
0x180003f4e  mov     rcx, [rdi]
0x180003f51  lea     rdx, [rsp+28h+arg_8]
0x180003f56  mov     [rsp+28h+arg_8], rbx
0x180003f5b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003f60  test    eax, eax
0x180003f62  js      short loc_180003F73
0x180003f64  cmp     [rdi+8], rbx
0x180003f68  jnz     short loc_180003F73
0x180003f6a  mov     rax, [rsp+28h+arg_8]
0x180003f6f  mov     [rdi+8], rax
0x180003f73  mov     rax, [rdi+8]
0x180003f77  lea     rcx, [rax+20h]
0x180003f7b  neg     rax
0x180003f7e  sbb     rdi, rdi
0x180003f81  and     rdi, rcx
0x180003f84  jz      short loc_180003FC6
0x180003f86  call    cs:__imp_GetCurrentThreadId
0x180003f8c  mov     r8d, eax
0x180003f8f  mov     r9d, eax
0x180003f92  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003f9c  shr     r8, 2
0x180003fa0  mul     r8
0x180003fa3  shr     rdx, 3
0x180003fa7  lea     rcx, [rdx+rdx*4]
0x180003fab  add     rcx, rcx
0x180003fae  sub     r8, rcx
0x180003fb1  mov     rbx, [rdi+r8*8+8]
0x180003fb6  jmp     short loc_180003FC1
0x180003fb8  cmp     [rbx], r9d
0x180003fbb  jz      short loc_180003FD4
0x180003fbd  mov     rbx, [rbx+8]
0x180003fc1  test    rbx, rbx
0x180003fc4  jnz     short loc_180003FB8
0x180003fc6  mov     rax, rbx
0x180003fc9  mov     rbx, [rsp+28h+arg_0]
0x180003fce  add     rsp, 20h
0x180003fd2  pop     rdi
0x180003fd3  retn
0x180003fd4  add     rbx, 10h
0x180003fd8  jz      short loc_180003FC6
0x180003fda  cmp     qword ptr [rbx+8], 0
0x180003fdf  jnz     short loc_180003FC6
0x180003fe1  lea     rax, [rdi+4]
0x180003fe5  mov     [rbx+8], rax
0x180003fe9  jmp     short loc_180003FC6
```
