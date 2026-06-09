# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005cd0`
- end: `0x180005d8b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054f0`

## callees

- `0x180004418`
- `0x180005cd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d26`

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
0x180005cd0  mov     [rsp+arg_0], rbx
0x180005cd5  push    rdi
0x180005cd6  sub     rsp, 20h
0x180005cda  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005ce1  xor     ebx, ebx
0x180005ce3  test    rdi, rdi
0x180005ce6  jz      short loc_180005D66
0x180005ce8  cmp     [rdi+8], rbx
0x180005cec  jnz     short loc_180005D13
0x180005cee  mov     rcx, [rdi]
0x180005cf1  lea     rdx, [rsp+28h+arg_8]
0x180005cf6  mov     [rsp+28h+arg_8], rbx
0x180005cfb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005d00  test    eax, eax
0x180005d02  js      short loc_180005D13
0x180005d04  cmp     [rdi+8], rbx
0x180005d08  jnz     short loc_180005D13
0x180005d0a  mov     rax, [rsp+28h+arg_8]
0x180005d0f  mov     [rdi+8], rax
0x180005d13  mov     rax, [rdi+8]
0x180005d17  lea     rcx, [rax+20h]
0x180005d1b  neg     rax
0x180005d1e  sbb     rdi, rdi
0x180005d21  and     rdi, rcx
0x180005d24  jz      short loc_180005D66
0x180005d26  call    cs:__imp_GetCurrentThreadId
0x180005d2c  mov     r8d, eax
0x180005d2f  mov     r9d, eax
0x180005d32  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005d3c  shr     r8, 2
0x180005d40  mul     r8
0x180005d43  shr     rdx, 3
0x180005d47  lea     rcx, [rdx+rdx*4]
0x180005d4b  add     rcx, rcx
0x180005d4e  sub     r8, rcx
0x180005d51  mov     rbx, [rdi+r8*8+8]
0x180005d56  jmp     short loc_180005D61
0x180005d58  cmp     [rbx], r9d
0x180005d5b  jz      short loc_180005D74
0x180005d5d  mov     rbx, [rbx+8]
0x180005d61  test    rbx, rbx
0x180005d64  jnz     short loc_180005D58
0x180005d66  mov     rax, rbx
0x180005d69  mov     rbx, [rsp+28h+arg_0]
0x180005d6e  add     rsp, 20h
0x180005d72  pop     rdi
0x180005d73  retn
0x180005d74  add     rbx, 10h
0x180005d78  jz      short loc_180005D66
0x180005d7a  cmp     qword ptr [rbx+8], 0
0x180005d7f  jnz     short loc_180005D66
0x180005d81  lea     rax, [rdi+4]
0x180005d85  mov     [rbx+8], rax
0x180005d89  jmp     short loc_180005D66
```
