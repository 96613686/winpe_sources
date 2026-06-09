# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800055e0`
- end: `0x18000569b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e00`

## callees

- `0x180004528`
- `0x1800055e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005636`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005636`

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
0x1800055e0  mov     [rsp+arg_0], rbx
0x1800055e5  push    rdi
0x1800055e6  sub     rsp, 20h
0x1800055ea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800055f1  xor     ebx, ebx
0x1800055f3  test    rdi, rdi
0x1800055f6  jz      short loc_180005676
0x1800055f8  cmp     [rdi+8], rbx
0x1800055fc  jnz     short loc_180005623
0x1800055fe  mov     rcx, [rdi]
0x180005601  lea     rdx, [rsp+28h+arg_8]
0x180005606  mov     [rsp+28h+arg_8], rbx
0x18000560b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005610  test    eax, eax
0x180005612  js      short loc_180005623
0x180005614  cmp     [rdi+8], rbx
0x180005618  jnz     short loc_180005623
0x18000561a  mov     rax, [rsp+28h+arg_8]
0x18000561f  mov     [rdi+8], rax
0x180005623  mov     rax, [rdi+8]
0x180005627  lea     rcx, [rax+20h]
0x18000562b  neg     rax
0x18000562e  sbb     rdi, rdi
0x180005631  and     rdi, rcx
0x180005634  jz      short loc_180005676
0x180005636  call    cs:__imp_GetCurrentThreadId
0x18000563c  mov     r8d, eax
0x18000563f  mov     r9d, eax
0x180005642  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000564c  shr     r8, 2
0x180005650  mul     r8
0x180005653  shr     rdx, 3
0x180005657  lea     rcx, [rdx+rdx*4]
0x18000565b  add     rcx, rcx
0x18000565e  sub     r8, rcx
0x180005661  mov     rbx, [rdi+r8*8+8]
0x180005666  jmp     short loc_180005671
0x180005668  cmp     [rbx], r9d
0x18000566b  jz      short loc_180005684
0x18000566d  mov     rbx, [rbx+8]
0x180005671  test    rbx, rbx
0x180005674  jnz     short loc_180005668
0x180005676  mov     rax, rbx
0x180005679  mov     rbx, [rsp+28h+arg_0]
0x18000567e  add     rsp, 20h
0x180005682  pop     rdi
0x180005683  retn
0x180005684  add     rbx, 10h
0x180005688  jz      short loc_180005676
0x18000568a  cmp     qword ptr [rbx+8], 0
0x18000568f  jnz     short loc_180005676
0x180005691  lea     rax, [rdi+4]
0x180005695  mov     [rbx+8], rax
0x180005699  jmp     short loc_180005676
```
