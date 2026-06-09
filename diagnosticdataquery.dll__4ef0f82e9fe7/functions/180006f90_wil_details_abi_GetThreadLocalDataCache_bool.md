# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006f90`
- end: `0x18000704b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067b0`

## callees

- `0x1800060c8`
- `0x180006f90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fe6`

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
0x180006f90  mov     [rsp+arg_0], rbx
0x180006f95  push    rdi
0x180006f96  sub     rsp, 20h
0x180006f9a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006fa1  xor     ebx, ebx
0x180006fa3  test    rdi, rdi
0x180006fa6  jz      short loc_180007026
0x180006fa8  cmp     [rdi+8], rbx
0x180006fac  jnz     short loc_180006FD3
0x180006fae  mov     rcx, [rdi]
0x180006fb1  lea     rdx, [rsp+28h+arg_8]
0x180006fb6  mov     [rsp+28h+arg_8], rbx
0x180006fbb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006fc0  test    eax, eax
0x180006fc2  js      short loc_180006FD3
0x180006fc4  cmp     [rdi+8], rbx
0x180006fc8  jnz     short loc_180006FD3
0x180006fca  mov     rax, [rsp+28h+arg_8]
0x180006fcf  mov     [rdi+8], rax
0x180006fd3  mov     rax, [rdi+8]
0x180006fd7  lea     rcx, [rax+20h]
0x180006fdb  neg     rax
0x180006fde  sbb     rdi, rdi
0x180006fe1  and     rdi, rcx
0x180006fe4  jz      short loc_180007026
0x180006fe6  call    cs:__imp_GetCurrentThreadId
0x180006fec  mov     r8d, eax
0x180006fef  mov     r9d, eax
0x180006ff2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006ffc  shr     r8, 2
0x180007000  mul     r8
0x180007003  shr     rdx, 3
0x180007007  lea     rcx, [rdx+rdx*4]
0x18000700b  add     rcx, rcx
0x18000700e  sub     r8, rcx
0x180007011  mov     rbx, [rdi+r8*8+8]
0x180007016  jmp     short loc_180007021
0x180007018  cmp     [rbx], r9d
0x18000701b  jz      short loc_180007034
0x18000701d  mov     rbx, [rbx+8]
0x180007021  test    rbx, rbx
0x180007024  jnz     short loc_180007018
0x180007026  mov     rax, rbx
0x180007029  mov     rbx, [rsp+28h+arg_0]
0x18000702e  add     rsp, 20h
0x180007032  pop     rdi
0x180007033  retn
0x180007034  add     rbx, 10h
0x180007038  jz      short loc_180007026
0x18000703a  cmp     qword ptr [rbx+8], 0
0x18000703f  jnz     short loc_180007026
0x180007041  lea     rax, [rdi+4]
0x180007045  mov     [rbx+8], rax
0x180007049  jmp     short loc_180007026
```
